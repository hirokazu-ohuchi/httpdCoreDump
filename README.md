httpdCoreDump
=============

yum install gdb

vi /etc/sysctl.conf
  + kernel.core_pattern = /tmp/core
  + kernel.core_uses_pid = 1

sysctl -p

vi /etc/sysconfig/httpd
 + DAEMON_COREFILE_LIMIT=unlimited

vi /etc/httpd/conf/httpd.conf
 + CoreDumpDirectory /tmp

/etc/init.d/httpd restart

gdb httpd -c /tmp/core.xxxx

(gdb) where
