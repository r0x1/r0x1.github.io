---
layout: post
title: Faraday IPE 二次开发 (1) 安装
date: 2020-06-07T00:00:00.000Z
tags:
  - faraday
image: null
---
> 
2020-06-07，faraday最新版是3.11.1。但是，只有服务器端，没有客户端。
因为faraday正在将client分离到一个单独的项目中：faraday-client，但是目前没有release版本。
faraday的上一个稳定版本是3.10.2，包含服务器端和客户端，所以这里采用3.10.2进行二次开发的探(踩)索(坑)。

***友情提示***  
*faraday安装成功之后，会创建一个 /home/zhangsan/.faraday 目录，
如果你发现你的系统中多出了一个 faraday 用户和组，或者多出了一个 /home/faraday/ 目录，
或者你在控制台可以自动完成命令 $ faraday-server 等 带有 faraday 的任何东西，
那么恭喜你，你的二次开发环境就算安装失败了，因为这个是通过deb安装才会出现的，不是源码安装的。
用我下面提供的完全删除faraday的sh来删除faraday，重新安装吧。*

*我的操作系统：ParrotOS 4.9.1，理论上与Kali的操作相同  
一定部署在虚拟机上，快照是个好东西，我拍了20个快照，才把faraday装好。  
建议先仔细看一遍官方 Development setup 的 wiki：https://github.com/infobyte/faraday/wiki/Development-setup*


## 服务器端安装和运行


- 下载代码
```
访问 https://github.com/infobyte/faraday/releases
我下载的是 https://github.com/infobyte/faraday/archive/v3.10.2.zip
下载 faraday-3.10.2.zip 到本地，解压得到 /home/zhangsan/Workspace/faraday-3.10.2 目录
```

- 进入目录
```
$ cd faraday-3.10.2
```

- 更新apt

```
$ sudo apt-get update
```

- 安装一些依赖
```
$ sudo apt-get install build-essential ipython python-setuptools \
                python-pip python-dev libssl-dev \
                libffi-dev pkg-config libxml2-dev \
                libxslt1-dev libfreetype6-dev libpng-dev
```

- 安装虚拟环境virtualenv
```
$ pip install virtualenv
```

- 创建虚拟环境venv
```
$ virtualenv -p python3 venv
```

- 激活虚拟环境venv
```
$ source venv/bin/activat
```

- 安装依赖项
```
$ python setup.py develop
```

- 安装依赖项
```
$ pip install -r requirements.txt
$ pip install -r requirements_server.txt
$ pip install -r requirements_dev.txt
```

- 这期间会遇到一些错误提示：
- 例如：cairo的错误
```
$ sudo apt-get install libcairo2-dev libjpeg-dev libgif-dev
```

- 例如：email-validator的错误
```
$ pip install email-validator
```

- 例如：psycopg2的错误，psycopg: Python.h: No such file or directory：
```
$ sudo apt-get install libpq-dev python-dev
```


- 需要根据你的python版本，安装对应的包，例如我的是3.7，则要安装python3.7-dev
```  
$ sudo apt-get install python3.7-dev  
$ pip install psycopg2  
```  


- 例如：syslog_rfc5424_formatter的错误
```
$ pip install rfc5424syslog
```

- 例如：Import Error: no module named 'past'
```
$ pip install future
```

- 例如：No package 'gobject-introspection-1.0' found
```
$ sudo apt install libgirepository1.0-dev
```


- 启动postgresql数据库
```
$ sudo service postgresql start
```

- 进入目录
```
$ cd home/zhangsan/Workspace/faraday-3.10.2/faraday
```

- 初始化数据库
```
$ python faraday/manage.py initdb
```
- 这里会显示用户名：faraday，和一个随机创建的密码，一定要记录保存下来。


- 启动服务端
```
$ python faraday/start_server.py
```

- 打开网页：localhost:5985/
- 输入用户名密码登录，提示密码错误，这是个bug，需要安装指定版本的包：
```
https://github.com/infobyte/faraday/issues/394
```


- 回到终端，激活虚拟环境faraday_venv，安装指定版本的包，必须安装这个版本，否则在登录网页的时候，会提示密码错误
```
$ source venv/bin/activat
$ pip install Flask-Login==0.4.1
$ pip install Werkzeug==0.16.0
```

## 以下是我的pip包列表：

- faraday_requirements.txt

```
alabaster==0.7.12
alembic==1.4.2
attrs==19.3.0
autobahn==20.4.3
Automat==20.2.0
Babel==2.8.0
bcrypt==3.1.7
beautifulsoup4==4.7.1
blinker==1.4
cachelib==0.1
cairocffi==0.9.0
certifi==2020.4.5.1
cffi==1.14.0
chardet==3.0.4
cli-helpers==2.0.1
click==7.1.2
colorama==0.4.3
configobj==5.0.6
constantly==15.1.0
cryptography==2.9.2
deprecation==2.1.0
distro==1.4.0
dnspython==1.16.0
docutils==0.16
email-validator==1.1.1
factory-boy==2.12.0
Faker==4.1.0
faraday-plugins==1.2
# Editable install with no version control (faradaysec==3.10.2)
-e /home/zhangsan/Workspace/faraday-3.10.2
filedepot==0.7.1
filteralchemy-fork==0.1.0
Flask==1.1.2
Flask-BabelEx==0.9.4
Flask-Classful==0.14.2
Flask-KVSession-fork==0.6.3
Flask-Login==0.4.1
Flask-Mail==0.9.1
Flask-Principal==0.4.0
Flask-Restless==0.17.0
Flask-Security==3.0.0
Flask-Session==0.3.2
Flask-SQLAlchemy==2.4.3
Flask-WTF==0.14.3
future==0.18.2
html2text==2019.8.11
humanize==2.4.0
hyperlink==19.0.0
hypothesis==4.18.3
idna==2.9
imagesize==1.2.0
importlib-metadata==1.6.0
incremental==17.5.0
inflection==0.4.0
IPy==1.0
itsdangerous==1.1.0
Jinja2==2.11.2
lxml==4.3.3
Mako==1.1.3
MarkupSafe==1.1.1
marshmallow==2.21.0
marshmallow-sqlalchemy==0.15.0
mimerender==0.6.0
mockito==1.2.1
more-itertools==8.3.0
nplusone==1.0.0
packaging==20.4
passlib==1.7.2
pgcli==2.1.1
pgspecial==1.11.10
Pillow==7.1.2
pluggy==0.13.1
prompt-toolkit==2.0.10
psycopg2==2.8.5
psycopg2-binary==2.8.4
py==1.8.1
pyasn1==0.4.8
pyasn1-modules==0.2.8
pycairo==1.18.1
pycparser==2.20
pydot==1.4.1
Pygments==2.6.1
PyGObject==3.32.1
PyHamcrest==2.0.2
pyOpenSSL==19.1.0
pyparsing==2.4.7
pypcapfile==0.12.0
pytest==5.4.2
pytest-factoryboy==2.0.3
python-dateutil==2.8.1
python-editor==1.0.4
python-mimeparse==1.6.0
pytz==2020.1
requests==2.23.0
responses==0.10.14
service-identity==18.1.0
setproctitle==1.1.10
simplejson==3.17.0
simplekv==0.13.0
six==1.15.0
snowballstemmer==2.0.0
soupsieve==2.0.1
speaklater==1.3
Sphinx==3.0.4
sphinxcontrib-applehelp==1.0.2
sphinxcontrib-devhelp==1.0.2
sphinxcontrib-htmlhelp==1.0.3
sphinxcontrib-jsmath==1.0.1
sphinxcontrib-qthelp==1.0.3
sphinxcontrib-serializinghtml==1.1.4
SQLAlchemy==1.3.17
sqlalchemy-schemadisplay==1.3
sqlparse==0.3.1
syslog-rfc5424-formatter==1.1.1
tabulate==0.8.7
terminaltables==3.1.0
text-unidecode==1.3
tornado==6.0.4
tqdm==4.46.0
Twisted==20.3.0
txaio==20.4.1
Unidecode==1.1.1
urllib3==1.25.9
wcwidth==0.1.9
webargs==5.5.3
websocket-client==0.57.0
Werkzeug==0.16.1
Whoosh==2.7.4
WTForms==2.3.1
zipp==3.1.0
zope.interface==5.1.0
```


## 客户端的安装和运行
将 /home/zhangsan/Workspace/faraday-3.10.2 目录，
复制粘贴出一份，命名为 /home/zhangsan/Workspace/faraday-client 。


- 激活客户端的虚拟环境venv
```
$ source venv/bin/activat
```

- 启动 faraday 服务器端，保持正常运行

```
$ cd home/zhangsan/Workspace/faraday-client/faraday
```

- 启动 faraday 客户端，理论上客户端会自动连接到服务器端，不需要输入用户名和密码
```
$ python client/start_client.py
```


## 附上完全删除faraday的sh，方便重新安装...
- clean_faraday_all.sh

```
#!/bin/bash

echo "## apt删除faraday-server"
sudo apt purge -y faraday-server
echo ""

echo "## 启动postgresql"
sudo service postgresql start
echo ""

echo "## 登录postgresql后，请手动执行："
echo "# 1. drop database faraday ;"
echo "# 2. drop role faraday_postgresql ;"

sudo -u postgres psql
# drop database faraday ;
# drop role  faraday_postgresql ;
echo ""

echo "## 从faraday组删除你当前的登录用户zhangsan"
sudo gpasswd -d zhangsan faraday
echo ""
sudo groupdel faraday
echo ""
sudo usermod -G faraday faraday
echo ""

echo "## 删除faraday用户"
sudo userdel -r faraday
echo ""
echo ""
echo "## 删除/home/faraday/.faraday目录"
sudo rm -rf /home/faraday/.faraday
echo ""
echo "## 删除/home/zhangsan/.faraday目录"
sudo rm -rf /home/zhangsan/.faraday
echo ""
echo "done!"
echo ""
```








