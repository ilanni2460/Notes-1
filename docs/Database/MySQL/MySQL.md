# MySQL

：一个关系型数据库。
- [官方文档](https://dev.mysql.com/doc/refman/5.7/en/)
- 基于 C++ 开发。
- 采用 C/S 架构、TCP 通信。

## 版本

MySQL 存在多个分支：
- MySQL ：于 1995 年由 MySQL 公司发布。2008 年 MySQL 公司被 Sun 公司收购，2010 年 Sun 公司被 Oracle 公司收购。
  - v5.5 ：于 2010 年发布。
    - 将默认的数据库引擎从 MyISAM 改为 InnoDB 。
    - 支持半同步复制。
    - 增加字符集 utf16、utf32、utf8mb4 。
  - v5.6 ：于 2013 年发布。
    - 支持全文索引。
  - v5.7 ：于 2015 年发布。
    - 增加 JSON 数据类型。
  - v8.0 ：于 2018 年发布。
- MariaDB ：2010 年，因为抗议 Oracle 公司的收购，MySQL 的创始人之一 Monty Widenius 在 MySQL 5.5 的基础上分叉出 MariaDB ，以开源的方式提供与 MySQL 兼容的功能。
- Percona ：与 MySQL 完全兼容，还提供了 XtraDB 引擎。
- Drizzle ：与 MySQL 的差异较大。

## 服务器

运行 mysqld 进程的主机即可担任 MySQL 服务器。
- 通常作为守护进程运行，监听 3306 端口，供 MySQL 客户端连接。

### 安装 Percona

- yum 默认源的 MySQL 版本很老，建议这样安装：
  ```sh
  wget https://www.percona.com/downloads/Percona-Server-5.7/Percona-Server-5.7.28-31/binary/redhat/7/x86_64/Percona-Server-5.7.28-31-rd14ef86-el7-x86_64-bundle.tar
  tar -xvf Percona-Server-5.7.26-29-r11ad961-el7-x86_64-bundle.tar
  yum install -y Percona-Server*.rpm
  rm -f Percona-Server*
  systemctl start mysqld
  ```
  启动之后要修改密码：
  ```sh
  cat /var/log/mysqld.log | grep password   # 查看初始密码
  mysql -u root -p                          # 登录，输入初始密码
  set password for 'root'@'localhost' = password('******');  # 设置新密码
  ```

- 或者运行 Docker 镜像：
  ```sh
  docker run -d --name mysql -p 3306:3306   \
          -e MYSQL_ROOT_PASSWORD=******     \   # root 用户的密码（必须设置该环境变量）
          # -e MYSQL_ROOT_HOST=%            \   # root 用户的登录地址
          # -e MYSQL_DATABASE=db1           \   # 创建一个数据库
          # -e MYSQL_USER=leo               \   # 创建一个用户（会自动授予该用户对上面数据库的全部权限）
          # -e MYSQL_PASSWORD=******        \
          -v /opt/mysql/my.cnf:/etc/my.cnf  \   # 挂载配置文件
          -v /opt/mysql:/var/lib/mysql      \   # 挂载数据目录
          percona:5.7.26-centos
  ```
  该 Docker 镜像默认以 mysql 用户（uid 为 999）运行服务器，对于挂载文件可能没有访问权限，需要先在宿主机上修改文件的权限：
  ```sh
  mkdir -p /data/mysql
  touch /data/mysql/my.cnf
  chown -R 999:999 mysql
  ```

### 配置

MySQL 服务器启动时，默认会使用以下位置的配置文件。如果前一个配置文件不存在则使用后一个，如果都不存在则使用默认配置。
```sh
/etc/my.cnf
/etc/mysql/my.cnf
/usr/etc/my.cnf
~/.my.cnf 
```
- 这些配置文件的扩展名为 .cnf ，采用 ini 的语法。
- Mysql 会将用户输入的所有命令保存在 `~/.mysql_history` 文件中。

配置示例：
```ini
[mysqld]                              # 这部分配置会被 mysqld 命令读取
bind-address=0.0.0.0                  # 允许从任何 IP 地址访问
port=3306
datadir=/var/lib/mysql                # 数据目录，用于存放 MySQL 的数据文件
socket=/var/lib/mysql/mysql.sock
pid-file=/var/run/mysqld/mysqld.pid
log-error=/var/log/mysqld.log

default_storage_engine=InnoDB         # 设置 MySQL 默认使用的引擎
character-set-server=utf8mb4          # 默认的字符集
init-connect='set names utf8mb4'      # 设置一条 SQL 命令，让客户端每次建立连接时执行，从而初始化连接

default-time_zone='+8:00'             # 设置时区，默认采用主机的时区
symbolic-links=0                      # 在数据目录中禁止使用符号链接

# skip-grant-tables                   # 跳过权限验证，此时不需要密码就能访问所有数据库

[client]                              # 这部分配置会被 mysql、mysqldump 等命令读取
# port=3306                           # 设置连接服务器的默认端口
# socket=/var/lib/mysql/mysql.sock
# user=root                           # 设置默认用户名
# password=******                     # 设置默认密码
```

## 客户端

### 安装

- 安装的 MySQL 服务器会自带客户端，也可单独安装 MySQL 客户端：
  ```sh
  yum install mysql
  ```

- 或者运行 Docker 镜像：
  ```sh
  docker run -it --rm percona:5.7.26-centos mysql -h 127.0.0.1 -u root -p
  ```

### 用法

```sh
mysql                    # 启动 MySQL 客户端
      -h <host>          # 要连接的 MySQL 服务器的 IP 地址（默认是 localhost）
      -P <port>          # 连接的端口号（默认为 3306）
      -u <user>          # 连接的用户名（默认为 root）
      -p                 # 以带密码的方式连接（接下来会提示输入密码）
      --password=******  # 以带密码的方式连接（直接传入密码）
      -D <db>            # 打开一个 database
```
- 执行 mysql 命令时，如果不能成功连接并登录 MySQL 服务器，就不会进入 MySQL 客户端的终端。
- 刚安装 mysql 服务器时，执行 `mysql -u root -p` 即可登录。
  - 如果不使用 -p 选项，则默认以免密的方式连接，就不能通过 MySQL 服务器的身份认证。

进入 MySQL 客户端的终端之后，可以执行 SQL 命令，也可以执行内置命令。
- 执行 SQL 命令时必须以分号 ; 结尾，执行内置命令时则不必。
- 执行 SQL 命令时，有时显示结果是一个字段太多的表格，排版混乱、难以阅读。可以在执行的 SQL 命令的末尾加上 \G ，将显示结果从横向表格变成纵向列表，方便阅读。例如：`select * from mysql.user\G;`
- 常用的内置命令：
  ```sh
  connect [db]   # 重新连接到 MySQL 服务器
  status         # 显示 MySQL 服务器的状态
  exit           # 退出 MySQL 客户端（相当于 quit）
  ```

### mysqladmin

：一个能够管理 MySQL 服务器的工具，使用时不需要进入 MySQL 客户端的终端。

```sh
mysqladmin [OPTIONS] [command]...   # 连接到 MySQL 服务器，执行某种操作
          -h <host>         # 输入主机名等信息，连接到 MySQL 服务器
          -P <port>
          -u <user>
          -p
          --password=****** 

          password ******   # 修改该用户的密码
          create <db>       # 创建一个 datebase
          drop <db>         # 删除一个 datebase
          processlist       # 显示 MySQL 服务器上所有线程的状态
          kill <id>...      # 终止一个线程
          status            # 查看 MySQL 服务器的状态
          shutdown          # 关闭 MySQL 服务器

          -c 10 -i 1        # 重复执行 10 次操作，每次间隔 1s
```
