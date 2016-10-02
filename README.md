# DS8001
Additional Course materials for DS8001

# Up and Running with Spark
You can either use a pre-loaded VM or build one from scratch. It's also possible to install spark locally in your machine. 
## Using a pre-loaded VM
1. [Download and Install Virtualbox] (https://www.virtualbox.org/wiki/Downloads "VirtualBox Download Page") (In case, you don't have it installed in your computer)
2. [Download the Pre-loaded VM] (https://drive.google.com/a/ryerson.ca/file/d/0B0HtI5JG2QR8RmNrbHVXVnh1bm8/view?usp=sharing) (Must be logged in to google drive using your ryerson account) 
3. Open VirtualBox and import the downloaded appliance 
4. Go to the settings of the VM and set your network adapter. Select Bridged Adapter and your network interface. The following link might help:
  http://www.hacking-tutorial.com/tips-and-trick/how-to-enable-the-network-in-kali-linux-virtual-box/#sthash.HkrupgGD.dpbs
5. Start the VM with `username: user` and `password: user`
6. You can launch any of the spark-shells (Scala, Python, R) from the /spark-2.0.0-bin-hadoop2.7/bin directory. For example,
  `/home/user/spark-2.0.0-bin-hadoop2.7/bin/spark-shell`
  `/home/user/spark-2.0.0-bin-hadoop2.7/bin/pyspark`
  `/home/user/spark-2.0.0-bin-hadoop2.7/bin/sparkR`
7. You can connect to Spark from rStudio with the sparklyr package (http://spark.rstudio.com/)
8. To connect to rStudio server using your browser

  First Check if rStudio server is running or not
  
  ```sudo rstudio-server status```
  
  You can also start, stop and restart rStudio manually:
  
  ```sudo rstudio-server start```
  
  ```sudo rstudio-server stop```
  
  ```sudo rstudio-server restart```
  
  Now, Check the ip address of the VM using `ifconfig`
  
  Note the ip address (use the first one) and open a browser on your host machine. use the ip and port 8787 as url to access rStudio 
  server from the browser (i.e. 10.0.2.15:8787)
  
  
  
  
  
  
-------------------------------------
## Building a Ubuntu VM for Spark from scratch
Download and install Virtualbox

Download Ubuntu server

[Create a new VM using the ubuntu server iso file](http://hussainweb.me/install-ubuntu-server-14-04-virtualbox/)

*[64-bit](http://www.ubuntu.com/download/alternative-downloads)
*[32-bit](http://www.ubuntu.com/download/alternative-downloads)

Set your network adapter to "Bridged" in your VM's settings in Virtualbox.

### Installing JAVA 
```
sudo apt-add-repository ppa:webupd8team/java

sudo apt-get update

sudo apt-get install oracle-java7-installer

java -version
```

### Installing SPARK 
```
wget http://d3kbcqa49mib13.cloudfront.net/spark-2.0.0-bin-hadoop2.7.tgz

tar xvf spark-2.0.0-bin-hadoop2.7.tgz
```

### Installing Python 
```
sudo apt-get install build-essential checkinstall

sudo apt-get install libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev

cd /usr/src

sudo wget https://www.python.org/ftp/python/2.7.12/Python-2.7.12.tgz

sudo tar xzf Python-2.7.12.tgz

cd Python-2.7.12

sudo ./configure

sudo make altinstall

python2.7 -V
```

### Installing R 
```
sudo sh -c 'echo "deb http://cran.rstudio.com/bin/linux/ubuntu trusty/" >> /etc/apt/sources.list'

sudo sh -c 'echo "deb http://cran.rstudio.com/bin/linux/ubuntu xenial/" >> /etc/apt/sources.list'

gpg --keyserver keyserver.ubuntu.com --recv-key E084DAB9

gpg -a --export E084DAB9 | sudo apt-key add -

sudo apt-get update

sudo apt-get -y install r-base

R
```

### Installing RStudio Server
```
sudo apt-get install gdebi-core
wget https://download2.rstudio.org/rstudio-server-0.99.903-amd64.deb
sudo gdebi rstudio-server-0.99.903-amd64.deb
```

### Installing sparklyr 
```
sudo apt-get install libcurl4-openssl-dev libssl-dev
```

### Installing ssh 
```
sudo apt-get install openssh-server
```
