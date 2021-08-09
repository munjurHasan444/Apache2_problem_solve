# Apache2_problem_solve

sometime you will face this problem..I will try to solve this problem today.

step 1:

$ sudo service apache2 start
Job for apache2.service failed because the control process exited with error code. See "systemctl status apache2.service" and "journalctl -xe" for details.

apache2.service Failed Because the Control Process Exited with Error Code and apache2 service activation:failed perfect solution.

$ systemctl restart apache2
$ journal -xe 
$ sudo apt-get purge apache2
$ sudo apt autoremove apache2
$ sudo apt-get purge apache2
$ sudo apt-get purge apache2*
$ sudo apt-get install apache2
$ sudo service apache2 start

if step 1 is not working for you then you will follow step 2.

step 2:
Firstly check-in your machine is there Nginx service is running in your system using

sudo systemctl status nginx.service
if it is running stop the service using

sudo systemctl stop nginx.service
and then check port 80 is there any process running on that port using

sudo lsof -i tcp:80
output:

    COMMAND PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
anydesk 950 root   22u  IPv4  39398      0t0  TCP bitcot-Latitude-7480:35993->hosted.by.datacamp.co.uk:http (ESTABLISHED)
kill the process using

sudo kill 950
Now your apache2 is ready, To start service open a new terminal Ctrl + Ail + T and start service using

sudo systemctl  start apache2
sudo service apache2 stop
sudo service apache2 start

here you go
