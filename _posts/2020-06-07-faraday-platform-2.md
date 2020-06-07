---
layout: post
title: 'Faraday Platform 二次开发 (2) 感兴趣的功能与目录结构[未完成]'
date: 2020-06-07T13:15:43.800Z
tags:
  - faraday
image: null
---
> 基于 faraday 3.10.2，因为3.11的faraday_client分到了单独的项目，而且暂时没有release。

faraday-3.10.2



```

.
├── absolutize
│   ├── fix_files_structure.sh
│   ├── fix_nontrivial_imports.sh
│   └── fix_trivial_imports.sh
├── AUTHORS
├── buildpth.nix
├── buildpth.sh
├── CHANGELOG
├── credentials.json
├── data
│   ├── cwe.csv
│   ├── cwe_en.csv
│   ├── cwe_es.csv
│   └── fix_severities.py
├── debian
│   ├── changelog
│   ├── compat
│   ├── control
│   ├── copyright
│   ├── docs
│   ├── faraday-client.install
│   ├── faraday.desktop
│   ├── faraday-server.install
│   ├── faraday-server.postinst
│   ├── faraday-server.service
│   ├── helper-script
│   │   ├── faraday
│   │   └── faraday-server
│   ├── rules
│   ├── source
│   │   ├── format
│   │   └── options
│   └── watch
├── doc
│   ├── conf.py
│   ├── creating_views.rst
│   ├── index.rst
│   ├── LIBRARY_LICENSE
│   ├── LICENSE
│   ├── LICENSE_FILE
│   ├── Makefile
│   ├── overview.rst
│   ├── recipes.rst
│   └── reference.rst
├── faraday
│   ├── alembic.ini
│   ├── client
│   │   ├── apis
│   │   │   ├── __init__.py
│   │   │   ├── __pycache__
│   │   │   │   └── __init__.cpython-37.pyc
│   │   │   └── rest
│   │   │       ├── api.py
│   │   │       ├── client.py
│   │   │       ├── __init__.py
│   │   │       └── __pycache__
│   │   │           ├── api.cpython-37.pyc
│   │   │           └── __init__.cpython-37.pyc
│   │   ├── bin
│   │   │   ├── autoclose_vulns.py
│   │   │   ├── change_vuln_status.py
│   │   │   ├── create_cred.py
│   │   │   ├── create_host.py
│   │   │   ├── create_service.py
│   │   │   ├── create_vuln.py
│   │   │   ├── create_vulnweb.py
│   │   │   ├── del_all_hosts.py
│   │   │   ├── del_all_services_closed.py
│   │   │   ├── del_all_vulns_with.py
│   │   │   ├── fbruteforce_services.py
│   │   │   ├── filter_services.py
│   │   │   ├── fplugin.py
│   │   │   ├── get_all_ips.py
│   │   │   ├── get_severitiy_by_cwe.py
│   │   │   ├── import_csv.py
│   │   │   ├── import_pcap.py
│   │   │   ├── __init__.py
│   │   │   ├── list_creds.py
│   │   │   ├── list_hosts.py
│   │   │   ├── list_ips.py
│   │   │   ├── list_os.py
│   │   │   ├── __pycache__
│   │   │   │   ├── autoclose_vulns.cpython-37.pyc
│   │   │   │   ├── change_vuln_status.cpython-37.pyc
│   │   │   │   ├── create_cred.cpython-37.pyc
│   │   │   │   ├── create_host.cpython-37.pyc
│   │   │   │   ├── create_service.cpython-37.pyc
│   │   │   │   ├── create_vuln.cpython-37.pyc
│   │   │   │   ├── create_vulnweb.cpython-37.pyc
│   │   │   │   ├── del_all_hosts.cpython-37.pyc
│   │   │   │   ├── del_all_services_closed.cpython-37.pyc
│   │   │   │   ├── del_all_vulns_with.cpython-37.pyc
│   │   │   │   ├── fbruteforce_services.cpython-37.pyc
│   │   │   │   ├── filter_services.cpython-37.pyc
│   │   │   │   ├── get_all_ips.cpython-37.pyc
│   │   │   │   ├── get_severitiy_by_cwe.cpython-37.pyc
│   │   │   │   ├── import_csv.cpython-37.pyc
│   │   │   │   ├── import_pcap.cpython-37.pyc
│   │   │   │   ├── list_creds.cpython-37.pyc
│   │   │   │   ├── list_hosts.cpython-37.pyc
│   │   │   │   ├── list_ips.cpython-37.pyc
│   │   │   │   ├── list_os.cpython-37.pyc
│   │   │   │   └── screenshot_server.cpython-37.pyc
│   │   │   └── screenshot_server.py
│   │   ├── data
│   │   │   └── images
│   │   ├── gui
│   │   │   ├── customevents.py
│   │   │   ├── gtk
│   │   │   │   ├── application.py
│   │   │   │   ├── appwindow.py
│   │   │   │   ├── compatibility.py
│   │   │   │   ├── decorators.py
│   │   │   │   ├── dialogs.py
│   │   │   │   ├── __init__.py
│   │   │   │   ├── mainwidgets.py
│   │   │   │   ├── menubar.xml
│   │   │   │   ├── __pycache__
│   │   │   │   │   ├── application.cpython-37.pyc
│   │   │   │   │   ├── appwindow.cpython-37.pyc
│   │   │   │   │   ├── compatibility.cpython-37.pyc
│   │   │   │   │   ├── decorators.cpython-37.pyc
│   │   │   │   │   ├── dialogs.cpython-37.pyc
│   │   │   │   │   ├── __init__.cpython-37.pyc
│   │   │   │   │   ├── mainwidgets.cpython-37.pyc
│   │   │   │   │   └── server.cpython-37.pyc
│   │   │   │   └── server.py
│   │   │   ├── gui_app.py
│   │   │   ├── __init__.py
│   │   │   ├── loghandler.py
│   │   │   ├── nogui
│   │   │   │   ├── application.py
│   │   │   │   ├── eventwatcher.py
│   │   │   │   └── __init__.py
│   │   │   ├── notifier.py
│   │   │   └── __pycache__
│   │   │       ├── customevents.cpython-37.pyc
│   │   │       ├── gui_app.cpython-37.pyc
│   │   │       ├── __init__.cpython-37.pyc
│   │   │       ├── loghandler.cpython-37.pyc
│   │   │       └── notifier.cpython-37.pyc
│   │   ├── helpers
│   │   │   ├── cfdbToCsv.py
│   │   │   ├── cleanXML.py
│   │   │   ├── plugins
│   │   │   │   └── canvas
│   │   │   │       └── faraday_report
│   │   │   │           ├── dialog.glade2
│   │   │   │           └── faraday_report.py
│   │   │   └── vulndbToCsv.py
│   │   ├── __init__.py
│   │   ├── managers
│   │   │   ├── all.py
│   │   │   ├── __init__.py
│   │   │   ├── mapper_manager.py
│   │   │   ├── __pycache__
│   │   │   │   ├── __init__.cpython-37.pyc
│   │   │   │   ├── mapper_manager.cpython-37.pyc
│   │   │   │   ├── reports_managers.cpython-37.pyc
│   │   │   │   └── workspace_manager.cpython-37.pyc
│   │   │   ├── reports_managers.py
│   │   │   └── workspace_manager.py
│   │   ├── model
│   │   │   ├── api.py
│   │   │   ├── application.py
│   │   │   ├── cli_app.py
│   │   │   ├── commands_history.py
│   │   │   ├── common.py
│   │   │   ├── conflict.py
│   │   │   ├── container.py
│   │   │   ├── controller.py
│   │   │   ├── diff.py
│   │   │   ├── guiapi.py
│   │   │   ├── __init__.py
│   │   │   ├── log.py
│   │   │   ├── __pycache__
│   │   │   ├── session.py
│   │   │   ├── timeline.py
│   │   │   ├── views.py
│   │   │   ├── visitor.py
│   │   │   └── workspace.py
│   │   ├── persistence
│   │   │   ├── __init__.py
│   │   │   ├── __pycache__
│   │   │   └── server
│   │   │       ├── changes_stream.py
│   │   │       ├── docs
│   │   │       │   ├── _build
│   │   │       │   │   ├── doctrees
│   │   │       │   │   │   ├── environment.pickle
│   │   │       │   │   │   ├── index.doctree
│   │   │       │   │   │   ├── modules.doctree
│   │   │       │   │   │   └── server.doctree
│   │   │       │   │   └── html
│   │   │       │   │       ├── genindex.html
│   │   │       │   │       ├── index.html
│   │   │       │   │       ├── _modules
│   │   │       │   │       │   ├── index.html
│   │   │       │   │       │   ├── persistence
│   │   │       │   │       │   │   └── server
│   │   │       │   │       │   │       └── server.html
│   │   │       │   │       │   ├── server
│   │   │       │   │       │   │   └── models.html
│   │   │       │   │       │   ├── server.html
│   │   │       │   │       │   └── sqlalchemy
│   │   │       │   │       │       └── orm
│   │   │       │   │       │           └── attributes.html
│   │   │       │   │       ├── modules.html
│   │   │       │   │       ├── objects.inv
│   │   │       │   │       ├── py-modindex.html
│   │   │       │   │       ├── search.html
│   │   │       │   │       ├── searchindex.js
│   │   │       │   │       ├── server.html
│   │   │       │   │       ├── _sources
│   │   │       │   │       │   ├── index.rst.txt
│   │   │       │   │       │   ├── index.txt
│   │   │       │   │       │   ├── modules.rst.txt
│   │   │       │   │       │   ├── modules.txt
│   │   │       │   │       │   ├── server.rst.txt
│   │   │       │   │       │   └── server.txt
│   │   │       │   │       └── _static
│   │   │       │   │           ├── ajax-loader.gif
│   │   │       │   │           ├── alabaster.css
│   │   │       │   │           ├── basic.css
│   │   │       │   │           ├── comment-bright.png
│   │   │       │   │           ├── comment-close.png
│   │   │       │   │           ├── comment.png
│   │   │       │   │           ├── css
│   │   │       │   │           │   ├── badge_only.css
│   │   │       │   │           │   └── theme.css
│   │   │       │   │           ├── custom.css
│   │   │       │   │           ├── doctools.js
│   │   │       │   │           ├── down.png
│   │   │       │   │           ├── down-pressed.png
│   │   │       │   │           ├── file.png
│   │   │       │   │           ├── fonts
│   │   │       │   │           │   ├── fontawesome-webfont.eot
│   │   │       │   │           │   ├── fontawesome-webfont.svg
│   │   │       │   │           │   ├── fontawesome-webfont.ttf
│   │   │       │   │           │   ├── fontawesome-webfont.woff
│   │   │       │   │           │   ├── Inconsolata-Bold.ttf
│   │   │       │   │           │   ├── Inconsolata-Regular.ttf
│   │   │       │   │           │   ├── Lato-Bold.ttf
│   │   │       │   │           │   ├── Lato-Regular.ttf
│   │   │       │   │           │   ├── RobotoSlab-Bold.ttf
│   │   │       │   │           │   └── RobotoSlab-Regular.ttf
│   │   │       │   │           ├── jquery-1.11.1.js
│   │   │       │   │           ├── jquery-3.1.0.js
│   │   │       │   │           ├── jquery.js
│   │   │       │   │           ├── js
│   │   │       │   │           │   ├── modernizr.min.js
│   │   │       │   │           │   └── theme.js
│   │   │       │   │           ├── minus.png
│   │   │       │   │           ├── plus.png
│   │   │       │   │           ├── pygments.css
│   │   │       │   │           ├── searchtools.js
│   │   │       │   │           ├── underscore-1.3.1.js
│   │   │       │   │           ├── underscore.js
│   │   │       │   │           ├── up.png
│   │   │       │   │           ├── up-pressed.png
│   │   │       │   │           └── websupport.js
│   │   │       │   ├── conf.py
│   │   │       │   ├── index.rst
│   │   │       │   ├── make.bat
│   │   │       │   ├── Makefile
│   │   │       │   └── server.rst
│   │   │       ├── __init__.py
│   │   │       ├── models.py
│   │   │       ├── __pycache__
│   │   │       │   ├── changes_stream.cpython-37.pyc
│   │   │       │   ├── __init__.cpython-37.pyc
│   │   │       │   ├── models.cpython-37.pyc
│   │   │       │   ├── server.cpython-37.pyc
│   │   │       │   ├── server_io_exceptions.cpython-37.pyc
│   │   │       │   └── utils.cpython-37.pyc
│   │   │       ├── server_io_exceptions.py
│   │   │       ├── server.py
│   │   │       └── utils.py
│   │   ├── plugins
│   │   │   ├── controller.py
│   │   │   ├── core.py
│   │   │   ├── fplugin_utils.py
│   │   │   ├── __init__.py
│   │   │   ├── manager.py
│   │   │   ├── plugin.py
│   │   │   ├── plugins_utils.py
│   │   │   ├── plugin_utils.py
│   │   │   ├── port_mapper.txt
│   │   │   ├── __pycache__
│   │   │   │   ├── controller.cpython-37.pyc
│   │   │   │   ├── core.cpython-37.pyc
│   │   │   │   ├── fplugin_utils.cpython-37.pyc
│   │   │   │   ├── __init__.cpython-37.pyc
│   │   │   │   ├── manager.cpython-37.pyc
│   │   │   │   ├── plugin.cpython-37.pyc
│   │   │   │   ├── plugins_utils.cpython-37.pyc
│   │   │   │   └── plugin_utils.cpython-37.pyc
│   │   │   └── repo
│   │   │       ├── acunetix
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── amap
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── appscan
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── arachni
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── arp-scan
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── beef
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── brutexss
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── burp
│   │   │       │   ├── burp-2.0-SNAPSHOT.jar
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── dig
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── dirb
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── dirsearch
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── dnsenum
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── dnsmap
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── dnsrecon
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── dnswalk
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── fierce
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── fortify
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── fruitywifi
│   │   │       │   ├── fruitywifi.py
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── ftp
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── goohost
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── hping3
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── hydra
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── impact
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── __init__.py
│   │   │       ├── ip360
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── junit
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── listurl
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── lynis
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── maltego
│   │   │       │   ├── Graph1.graphml
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── masscan
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── medusa
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── metagoofil
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── metasploit
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── metasploiton
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── ndiff
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── nessus
│   │   │       │   ├── dotnessus_v2.py
│   │   │       │   ├── __init__.py
│   │   │       │   ├── plugin.py
│   │   │       │   ├── __pycache__
│   │   │       │   │   ├── dotnessus_v2.cpython-37.pyc
│   │   │       │   │   └── __init__.cpython-37.pyc
│   │   │       │   └── pynessus.py
│   │   │       ├── netcat
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── netdiscover
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── netsparker
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── netsparkercloud
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── nexpose-full
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── nikto
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── nmap
│   │   │       │   ├── __init__.py
│   │   │       │   ├── plugin.py
│   │   │       │   └── __pycache__
│   │   │       │       ├── __init__.cpython-37.pyc
│   │   │       │       └── plugin.cpython-37.pyc
│   │   │       ├── openvas
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── pasteanalyzer
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── peepingtom
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── ping
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── propecia
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── __pycache__
│   │   │       │   └── __init__.cpython-37.pyc
│   │   │       ├── qualysguard
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── reconng
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── retina
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── reverseraider
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── sentinel
│   │   │       │   └── plugin.py
│   │   │       ├── skipfish
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── sqlmap
│   │   │       │   ├── __init__.py
│   │   │       │   ├── plugin.py
│   │   │       │   └── queries.xml
│   │   │       ├── sshdefaultscan
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── sslcheck
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── sslyze
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── sublist3r
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── telnet
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── theharvester
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── traceroute
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── w3af
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── wapiti
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── wcscan
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── webfuzzer
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── webinspect
│   │   │       │   └── plugin.py
│   │   │       ├── wfuzz
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── whois
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── wpscan
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── x1
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       ├── xsssniper
│   │   │       │   ├── __init__.py
│   │   │       │   └── plugin.py
│   │   │       └── zap
│   │   │           ├── __init__.py
│   │   │           ├── java
│   │   │           │   ├── ConfigurationDialog.java
│   │   │           │   ├── Configuration.java
│   │   │           │   ├── FaradayClient.java
│   │   │           │   ├── FaradayExtension.java
│   │   │           │   ├── Messages.properties
│   │   │           │   ├── PopupMenuItemSendAlert.java
│   │   │           │   ├── PopupMenuItemSendRequest.java
│   │   │           │   └── ZapAddOn.xml
│   │   │           ├── plugin.py
│   │   │           ├── report.xml
│   │   │           └── zap-plugin.zap
│   │   ├── __pycache__
│   │   │   ├── __init__.cpython-37.pyc
│   │   │   └── start_client.cpython-37.pyc
│   │   ├── start_client.py
│   │   └── zsh
│   │       ├── faraday-terminal.zsh
│   │       ├── faraday.zsh
│   │       ├── __init__.py
│   │       └── plugin_controller_client.py
│   ├── config
│   │   ├── configuration.py
│   │   ├── constant.py
│   │   ├── default.xml
│   │   ├── __init__.py
│   │   └── __pycache__
│   │       ├── configuration.cpython-37.pyc
│   │       ├── constant.cpython-37.pyc
│   │       └── __init__.cpython-37.pyc
│   ├── __init__.py
│   ├── manage.py
│   ├── migrations
│   │   ├── env.py
│   │   ├── __pycache__
│   │   │   └── env.cpython-37.pyc
│   │   ├── README
│   │   ├── script.py.mako
│   │   └── versions
│   │       ├── 085188e0a016_create_rules_tables.py
│   │       ├── 0d216660da28_add_notification_table.py
│   │       ├── 1b2533cc16fe_fix_custom_fields_display_name_was_used_.py
│   │       ├── 1dbe9e8e4247_add_rule_execution_start_and_end_fields.py
│   │       ├── 2a0de6132377_add_searchfilter_table.py
│   │       ├── 2ca03a8feef5_workspace_readonly.py
│   │       ├── 2db31733fb78_unique_field_name_in_customfield.py
│   │       ├── 3f771124f0a2_add_metadata_to_cf_schema.py
│   │       ├── 526aa91cac98_vulnerability_merge_model.py
│   │       ├── 5272b3f5a820_add_markdown_column_to_exectuive_reports.py
│   │       ├── 59bed5515407_vuln_external_id.py
│   │       ├── 8a10ff3926a5_2fa_columns.py
│   │       ├── 904a517a2f0c_create_executor_table.py
│   │       ├── 9c4091d1a09b_create_agent_table.py
│   │       ├── be89aa03e35e_add_severities_column_to_executive_.py
│   │       ├── e61afb450465_add_custom_fields.py
│   │       ├── f8a44acd0e41_add_new_user_role.py
│   │       └── __pycache__
│   ├── __pycache__
│   │   ├── __init__.cpython-37.pyc
│   │   └── manage.cpython-37.pyc
│   ├── requirements_server.txt -> ../requirements_server.txt
│   ├── requirements.txt -> ../requirements.txt
│   ├── searcher
│   │   ├── api.py
│   │   ├── __init__.py
│   │   ├── searcher.py
│   │   ├── sqlapi.py
│   │   └── validator.py
│   ├── server
│   │   ├── api
│   │   │   ├── base.py
│   │   │   ├── __init__.py
│   │   │   ├── modules
│   │   │   │   ├── activity_feed.py
│   │   │   │   ├── agent_auth_token.py
│   │   │   │   ├── agent.py
│   │   │   │   ├── bulk_create.py
│   │   │   │   ├── commandsrun.py
│   │   │   │   ├── comments.py
│   │   │   │   ├── credentials.py
│   │   │   │   ├── custom_fields.py
│   │   │   │   ├── get_exploits.py
│   │   │   │   ├── handlers.py
│   │   │   │   ├── hosts.py
│   │   │   │   ├── info.py
│   │   │   │   ├── __init__.py
│   │   │   │   ├── licenses.py
│   │   │   │   ├── __pycache__
│   │   │   │   ├── search_filter.py
│   │   │   │   ├── services.py
│   │   │   │   ├── session.py
│   │   │   │   ├── token.py
│   │   │   │   ├── upload_reports.py
│   │   │   │   ├── vulnerability_template.py
│   │   │   │   ├── vulns.py
│   │   │   │   ├── websocket_auth.py
│   │   │   │   └── workspaces.py
│   │   │   └── __pycache__
│   │   ├── app.py
│   │   ├── commands
│   │   │   ├── app_urls.py
│   │   │   ├── change_password.py
│   │   │   ├── change_username.py
│   │   │   ├── custom_fields.py
│   │   │   ├── faraday_schema_display.py
│   │   │   ├── initdb.py
│   │   │   ├── __init__.py
│   │   │   ├── __pycache__
│   │   │   ├── reset_db.py
│   │   │   ├── status_check.py
│   │   │   └── support.py
│   │   ├── config.py
│   │   ├── default.ini
│   │   ├── events.py
│   │   ├── fields.py
│   │   ├── __init__.py
│   │   ├── models.py
│   │   ├── __pycache__
│   │   ├── schemas.py
│   │   ├── threads
│   │   │   ├── __init__.py
│   │   │   ├── __pycache__
│   │   │   │   ├── __init__.cpython-37.pyc
│   │   │   │   └── reports_processor.cpython-37.pyc
│   │   │   └── reports_processor.py
│   │   ├── utils
│   │   │   ├── cache.py
│   │   │   ├── daemonize.py
│   │   │   ├── database.py
│   │   │   ├── debug.py
│   │   │   ├── export.py
│   │   │   ├── __init__.py
│   │   │   ├── invalid_chars.py
│   │   │   ├── logger.py
│   │   │   ├── py3.py
│   │   │   ├── __pycache__
│   │   │   └── web.py
│   │   ├── web.py
│   │   ├── websocket_factories.py
│   │   ├── workspaces
│   │   └── www
│   ├── start_server.py
│   └── utils
│       ├── common.py
│       ├── decorators.py
│       ├── dependencies.py
│       ├── error_report.py
│       ├── __init__.py
│       ├── __pycache__
│       └── user_input.py
├── faraday_requirements.txt
├── faradaysec.egg-info
│   ├── dependency_links.txt
│   ├── entry_points.txt
│   ├── PKG-INFO
│   ├── requires.txt
│   ├── SOURCES.txt
│   └── top_level.txt
├── faraday-server.py
├── fplugin.spec
├── manage.py
├── manage.spec
├── MANIFEST.in
├── merge-conflict-detector3.py
├── merge-conflict-detector.py
├── py3-checker.py
├── README.md
├── RELEASE.md
├── requirements_dev.txt
├── requirements_extras.txt
├── requirements_server.txt
├── requirements.txt
├── scripts
│   ├── cscan
│   │   ├── CHANGES.txt
│   │   ├── cscan_conf.ini
│   │   ├── cscan.py
│   │   ├── ips.txt
│   │   ├── plugin
│   │   │   ├── carbonator
│   │   │   │   └── carbonator.py
│   │   │   ├── msfrpc.py
│   │   │   ├── nessus.py
│   │   │   ├── w3af.py
│   │   │   └── zap.py
│   │   ├── README.md
│   │   ├── scripts
│   │   │   ├── extra
│   │   │   │   ├── msf-autobrute.sh
│   │   │   │   ├── msf-auto-cred-checker.sh
│   │   │   │   ├── msf-autoexploit-check.sh
│   │   │   │   ├── msf-autoexploit-dry.sh
│   │   │   │   ├── msf-autoexploit.sh
│   │   │   │   ├── msf-autosploit.sh
│   │   │   │   ├── msf-modules-list.sh
│   │   │   │   ├── msf-mssql-brute.sh
│   │   │   │   ├── msf-nessus-vulns-cleaner.sh
│   │   │   │   └── msf-port-cleaner.sh
│   │   │   ├── network
│   │   │   │   ├── msf-autoscan.sh
│   │   │   │   ├── msf-basic-discovery-nmap.sh
│   │   │   │   ├── msf-basic-discovery.sh
│   │   │   │   ├── msf-portscan-nmap.sh
│   │   │   │   ├── msf-portscan.sh
│   │   │   │   ├── nessus.sh
│   │   │   │   ├── nmap.sh
│   │   │   │   └── openvas.sh
│   │   │   ├── resources
│   │   │   │   ├── autoscan.rc
│   │   │   │   └── autosploit.rc
│   │   │   └── web
│   │   │       ├── burp.sh
│   │   │       ├── msf-autocrawler.sh
│   │   │       ├── msf-http-dir.sh
│   │   │       ├── msf-wmap-autotest.sh
│   │   │       ├── nikto.sh
│   │   │       ├── w3af.sh
│   │   │       └── zap.sh
│   │   └── websites.txt
│   ├── fix_vulnweb_without_service.py
│   ├── reposify
│   │   ├── reposify_api.py
│   │   └── reposify.py
│   ├── shodan_faraday.py
│   ├── shodan_strings
│   │   ├── router.txt
│   │   ├── scada.txt
│   │   └── webcam.txt
│   ├── sslcheck.py
│   ├── wcscan.py
│   └── wcscans
│       ├── DotNetConfig.xsd
│       ├── __init__.py
│       ├── phpini.py
│       └── webconfig.py
├── searcher.spec
├── setup.cfg
├── setup.py
├── shell.nix
├── start_client.spec
├── start_server.spec
├── tests
└── tests_web



```


