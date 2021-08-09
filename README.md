# Apache2_problem_solve

sometime you will face this problem..I will try to solve this problem today.

step 1:

$ sudo service apache2 start
Job for apache2.service failed because the control process exited with error code. See "systemctl status apache2.service" and "journalctl -xe" for details.

apache2.service Failed Because the Control Process Exited with Error Code and apache2 service activation:failed perfect solution.

$ systemctl restart apache2</br>
$ journal -xe </br>
$ sudo apt-get purge apache2</br>
$ sudo apt autoremove apache2</br>
$ sudo apt-get purge apache2</br>
$ sudo apt-get purge apache2*</br>
$ sudo apt-get install apache2</br>
$ sudo service apache2 start</br>

if step 1 is not working for you then you will follow step 2.</br>

step 2:</br>
Firstly check-in your machine is there Nginx service is running in your system using</br>

sudo systemctl status nginx.service</br>
if it is running stop the service using</br>

sudo systemctl stop nginx.service</br>
and then check port 80 is there any process running on that port using</br>

sudo lsof -i tcp:80</br>
output:</br>

    COMMAND PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME</br>
anydesk 950 root   22u  IPv4  39398      0t0  TCP bitcot-Latitude-7480:35993->hosted.by.datacamp.co.uk:http (ESTABLISHED)</br>
kill the process using</br>

sudo kill 950</br>
Now your apache2 is ready, To start service open a new terminal Ctrl + Ail + T and start service using</br>

sudo systemctl  start apache2</br>
sudo service apache2 stop</br>
sudo service apache2 start</br>

here you go
