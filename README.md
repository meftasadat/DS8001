# DS8001
Additional Course materials for DS8001

# Up and Running with Spark

## Using a pre-loaded VM
1. [Download and Install Virtualbox] (https://www.virtualbox.org/wiki/Downloads "VirtualBox Download Page") (In case, you don't have it installed in your computer)
2. [Download the Pre-loaded VM] (https://drive.google.com/a/ryerson.ca/file/d/0B0HtI5JG2QR8SkFqV29FUXVzMTQ/view?usp=sharing) (Must be logged in to google drive using your ryerson account) 
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


  
  
