---
layout: post
title: 'Faraday IPE 二次开发 (3) 数据库结构[未完成]'
date: 2020-06-14T11:17:57.500Z
tags:
  - faraday
image: null
---
> 基于 faraday 3.10.2，因为3.11的faraday_client分到了单独的项目，而且暂时没有release。



```
$sudo -u postgres psql「登录postgresql」
psql (12.3 (Debian 12.3-1+b1))
Type "help" for help.

postgres=# \l「列出所有数据库」
                                   List of databases
   Name    |       Owner        | Encoding | Collate |  Ctype  |   Access privileges   
-----------+--------------------+----------+---------+---------+-----------------------
 faraday   | faraday_postgresql | UTF8     | C.UTF-8 | C.UTF-8 | 
 postgres  | postgres           | UTF8     | C.UTF-8 | C.UTF-8 | 
 template0 | postgres           | UTF8     | C.UTF-8 | C.UTF-8 | =c/postgres          +
           |                    |          |         |         | postgres=CTc/postgres
 template1 | postgres           | UTF8     | C.UTF-8 | C.UTF-8 | =c/postgres          +
           |                    |          |         |         | postgres=CTc/postgres
(4 rows)

postgres=# \c faraday 「连接数据库」
You are now connected to database "faraday" as user "postgres".
faraday=# \dt「列出所有表」

                                     List of relations
 Schema |                        Name                         | Type  |       Owner        
--------+-----------------------------------------------------+-------+--------------------
 public | action                                              | table | faraday_postgresql
 public | agent                                               | table | faraday_postgresql
 public | agent_execution                                     | table | faraday_postgresql
 public | agent_schedule                                      | table | faraday_postgresql
 public | alembic_version                                     | table | faraday_postgresql
 public | command                                             | table | faraday_postgresql「客户端执行的命令，例如nmap，masscan，w3af等」
 public | command_object                                      | table | faraday_postgresql「客户端执行命令后，返回的对象，例如namp返回主机host信息，返回服务service信息」
 public | comment                                             | table | faraday_postgresql
 public | condition                                           | table | faraday_postgresql
 public | credential                                          | table | faraday_postgresql
 public | custom_fields_schema                                | table | faraday_postgresql
 public | db_metadata                                         | table | faraday_postgresql
 public | executive_report                                    | table | faraday_postgresql
 public | executor                                            | table | faraday_postgresql
 public | faraday_user                                        | table | faraday_postgresql「faraday自身的用户信息」
 public | file                                                | table | faraday_postgresql
 public | host                                                | table | faraday_postgresql「扫描后，得到的有效的主机host」
 public | hostname                                            | table | faraday_postgresql「扫描后，得到的hostname」
 public | knowledge_base                                      | table | faraday_postgresql
 public | license                                             | table | faraday_postgresql
 public | methodology                                         | table | faraday_postgresql
 public | methodology_template                                | table | faraday_postgresql
 public | notification                                        | table | faraday_postgresql
 public | policy_violation                                    | table | faraday_postgresql
 public | policy_violation_template                           | table | faraday_postgresql
 public | policy_violation_template_vulnerability_association | table | faraday_postgresql
 public | policy_violation_vulnerability_association          | table | faraday_postgresql
 public | reference                                           | table | faraday_postgresql
 public | reference_template                                  | table | faraday_postgresql
 public | reference_template_vulnerability_association        | table | faraday_postgresql
 public | reference_vulnerability_association                 | table | faraday_postgresql
 public | rule                                                | table | faraday_postgresql
 public | rule_action                                         | table | faraday_postgresql
 public | rule_execution                                      | table | faraday_postgresql
 public | scope                                               | table | faraday_postgresql
 public | search_filter                                       | table | faraday_postgresql
 public | service                                             | table | faraday_postgresql「扫描后，得到的有效的服务service信息」
 public | source_code                                         | table | faraday_postgresql
 public | tag                                                 | table | faraday_postgresql
 public | tag_object                                          | table | faraday_postgresql
 public | task                                                | table | faraday_postgresql
 public | task_assigned_to_association                        | table | faraday_postgresql
 public | task_template                                       | table | faraday_postgresql
 public | user_avatar                                         | table | faraday_postgresql
 public | vulnerability                                       | table | faraday_postgresql
 public | vulnerability_template                              | table | faraday_postgresql
 public | workspace                                           | table | faraday_postgresql「工作空间」
 public | workspace_permission_association                    | table | faraday_postgresql
(48 rows)

(END)



```




