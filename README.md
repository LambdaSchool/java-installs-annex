# Lambda School Web API: Java Course 
## Software installations for Week 1 

<details><summary>For All Operating Systems</summary>
<p>

### Nothing to install that is NOT operating system specific. See your OS link for installation instructions

</p>
</details>


<details><summary>For Windows 10 Operating System</summary>
<p>

---
### *** OPTIONALLY *** Install RabbitMQ on a Windows 10 based computer

[![Video to Install RabbitMQ](http://img.youtube.com/vi/EjSuWP7m0kk/0.jpg)](http://www.youtube.com/watch?v=EjSuWP7m0kk)

Install the Erlang software. RabbitMQ requires this development system to be installed first:
* Surf to [http://www.erlang.org/downloads](http://www.erlang.org/downloads)
* Download the 64 bit software for Windows
* Install the software as an Administrator

Now install the actual RabbitMQ Server
* Surf to [https://www.rabbitmq.com/install-windows.html](https://www.rabbitmq.com/install-windows.html) and install the software
* Add the RabbitMQ installation directory to your path
* Test by running from the command prompt: rabbitmqctl version. You should get a response showing the version of rabbitmq installed.

---
### *** OPTIONALLY *** Install Redis on a Windows 10 based computer

[![Video to Install Redis](http://img.youtube.com/vi/EjSuWP7m0kk/0.jpg)](http://www.youtube.com/watch?v=EjSuWP7m0kk)

Redis only runs on Linux. In order to run a Windows 10 based computer, a Linux subsystem must first be installed.
* Verify that the Windows 10 version is greater than 1709 by running winver from a command prompt. If the Windows version is less than 1709, upgrade the system. The upgrade is available free from Microsoft through the Windows Update Process.
* From a Powershell prompt being run as Administrator, enable a Linux subsystem with the command: 
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
* Surf to [https://www.microsoft.com/en-us/p/ubuntu-1804/9n9tngvndl3q](https://www.microsoft.com/en-us/p/ubuntu-1804/9n9tngvndl3q)
* Download and install the Ubuntu 18 subsystem. Ubuntu is a version of Linux

After launching the subsystem, run the following commands to install Redis
* sudo apt-get update
* sudo apt-get upgrade
* sudo apt-get install redis-server
* sudo service redis-server restart

To verify the installation:
* from a command prompt, run redis-cli -v  
This should return the version of Redis installed on the computer.
* from a command prompt, run redis-cli ping  
Redis should respond with pong

---
</p>
</details>


<details><summary>For Mac OS</summary>
<p>

### *** OPTIONALLY *** Install RabbitMQ on a Mac OS Computer

[![Video to Install RabbitMQ](http://img.youtube.com/vi/KygNhA0-VQk/0.jpg)](http://www.youtube.com/watch?v=KygNhA0-VQk)

Using Homebrew from a terminal prompt, enter
* brew update
* brew install rabbitmq

* Go to your home directory. Enter  
```cd ```
* Edit your user profile. Enter  
```nano .bash_profile```
* At the end of the file, add  
```export PATH=$PATH:/usr/local/opt/rabbitmq/sbin```
* Exit nano and restart your computer.  
* After machine has restarted and from a terminal prompt, enter  
```brew services start rabbitmq```

To test RabbitMQ, from a terminal prompt enter  
```rabbitmqctl version```  
A version number should be the response.

NOTE:

If you are still having trouble running rabbitmqctl, try adding another export PATH statement to your .bash_profile  
```export PATH=$PATH:/usr/local/sbin```

---
### *** OPTIONALLY *** Install Redis on a Mac OS Computer

[![Video to Install Redis](http://img.youtube.com/vi/8o8CWZTb1j0/0.jpg)](http://www.youtube.com/watch?v=8o8CWZTb1j0)

Using Homebrew from a terminal prompt enter
* brew update
* brew install redis
* brew services start redis

To test the installation from a terminal prompt enter
* redis-cli ping   
Redis will respond with pong

---
</details>


<details><summary>For Linux specifically Ubuntu 18</summary>
<p>

---
### *** OPTIONALLY *** Install RabbitMQ on a Linux Computer

[![Video to Install RabbitMQ](http://img.youtube.com/vi/jDPsisgWpr0/0.jpg)](http://www.youtube.com/watch?v=jDPsisgWpr0)

To install the software, first install Erlang and then the RabbitMQ server by doing the following from a terminal prompt:

* sudo apt update
* sudo apt install curl
* wget -O - "https://github.com/rabbitmq/signing-keys/releases/download/2.0/rabbitmq-release-signing-key.asc" | sudo apt-key add -
* sudo apt install apt-transport-https
* sudo nano /etc/apt/sources.list.d/bintray.erlang.list
  * Add the line   
```deb http://dl.bintray.com/rabbitmq-erlang/debian bionic erlang```
  * exit nano
* sudo apt update
* sudo apt install erlang-nox
* sudo nano /etc/apt/preferences.d/erlang
  * Add the three lines   
```
Package: erlang*
Pin: release o=Bintray
Pin-Priority: 1000
```
  * exit nano
* sudo apt update
* sudo apt-cache policy
* curl -s https://packagecloud.io/install/repositories/rabbitmq/rabbitmq-server/script.deb.sh | sudo bash
* sudo apt update
* sudo apt install rabbitmq-server
* sudo service rabbitmq-server start

Test the installation by entering the following at a terminal prompt
* sudo rabbitmqctl version
RabbitMQ should respond with a version number

---
### *** OPTIONALLY *** Install Redis on a Linux Computer

[![Video to Install Redis](http://img.youtube.com/vi/wWRxgPFO1zE/0.jpg)](http://www.youtube.com/watch?v=wWRxgPFO1zE)

To install Redis, enter the following at a terminal prompt

* sudo apt update
* sudo apt install redis-server
* sudo nano /etc/redis/redis.conf
  * search for supervised change line to supervised systemd
  * exit nano
* sudo systemctl restart redis.service

To test Redis, enter the following at a terminal prompt
* redis-cli ping   
Redis will respond with pong

---
</p>
</details>
