# SeleniumGrid
## Creating selenium grid and registering nodes to that grid
## Creating a hub VM
1. goto hub-vm folder and run vagrant
2. you can see in the vagrant file that we have done following tasks
    * download selenium-stand-alone-server jar file
    * start selenium server using that downloaded jar file by running following command
    ```
    java -jar selenium-server-standalone-3.141.59.jar -role hub
    ```
    * after starting it, you can access the server through url "http://192.168.33.13:4444/grid/console"
    
## Creating a node and registering it in the node
1. go to node-vm folder and run vagrant
2. you can see in the vagrant file that we have done following tasks
    * download selenium-stand-alone-server jar file
    * downloaded all the necessary browsers
    * downloaded all the binary driver files for each browsers
    * installed xvfb & java to run test cases headlessly
    * register a node by running following command
    ```
    java -Dwebdriver.gecko.driver="/home/vagrant/geckodriver" -Dwebdriver.chrome.driver="/home/vagrant/chromedriver" -jar selenium-server-standalone-3.141.59.jar -role webdriver -hub http://192.168.33.13:4444/grid/register -port 4445
    ```
    * change the location of binary drivers, hub ip and port & node's port if necessary
    * after starting it, you can access the node through url "http://192.168.33.11:4445/wd/hub/static/resource/hub.html"
    * you can create a browser session using that interface to check if everything works fine
