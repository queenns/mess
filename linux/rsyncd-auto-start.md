1. 确认系统版本,systemd是否可用,需要CentOS >= 7
cat /etc/redhat-release
2. 查看rsyncd系统文件
cat /usr/lib/systemd/system/rsyncd.service
3. 查看rsyncd配置文件
cat /etc/rsyncd.conf
4. 设置开机自启动
systemctl enable rsyncd
5. 验证是否正常
kill -9 pid
6. 启动
systemctl start rsyncd
7. 不正常时查看系统日志
tail -fn 200 /var/log/message
8. 当前发现/var/run/rsyncd.pid存在不能创建
rm -f /var/run/rsyncd.pid
9. 启动
systemctl start rsyncd
10. 验证启动正常,重启验证开机自启动是否正常即可
