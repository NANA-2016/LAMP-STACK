# LAMP-STACK

## Lamp stack project

WEBSTACK IMPLEMENTATION ON AWS

## Prepairing pre-requisites

in order the project to run a virtual server  and an aws account have to be set up which i have already n set up and are running. Below is a sammple 

instance which has been set up and is running.

![Screenshot 2023-09-15 225304](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/3b7553bc-2227-484a-b208-274367e850d1)

The second step involves connecting the vurtual server to AWS instance using the .PEM key via ssh as well as the public ip address.  To achieve 
 
 these , two steps are involved which are  -cd Downloads


                                           -ssh -i <private-key-name>.pem ubuntu@<Public-IP-address

 The screen shot below shows the expected results verifying creation of linux server into the cloud

![connect to instance ](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/09dee193-367b-42fa-8011-897a7db418fe)

## STEP 1- Installing apache2 and updating the fire wall.

Apache is free and its open source hence it is widely used  as a webserver .

To install Apache , we use commands seen below .

   -'$ sudo apt update' these is used to ensure system update.

   ![sudo apt update](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/2c433af7-7470-478d-99fe-75179c1717d1)

   -'$ sudo apt install apache2' as these helps install apache2
   
![sudo apt install apache-2](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/ee1fa59a-3d81-4a62-8fc1-d25b3565fe57)

   

    To ensure the apache2 is running as as a service in our OS, a command that is used gives results highlighted in green to show *active and running*

 the comand is as shown below as well as on the screen shot with the expected outcome .

 '$ sudo systemctl status apache2'
 
![apache2 status](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/671226b7-9323-42f3-9639-7df17fcf5bac)
 
We now need to activate TCP 80 which web browser use as an acess to web pages on the internet. This is done by changing the inbound rules and 
 
 selecting TCP 80 to access it via ssh. Now you will have Port 22 which is open on default on AWS and port 80 .
 
![inbound connection through port 80](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/b98a276c-ecb5-4c8f-98b1-d3142e953d3b)

 Then now we can move to the curl command which helps us request our Apacche HTTP Server on port 80 using the DNS name or the IP address. Here  the command I used is' $ curl http://localhost'

 ![curl command](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/3bd8e0fc-2ee5-44f4-aa08-68a61ef467d2)

 It demonstrates a very interesting pattern.

   LASTLY WE NEED TO CHECK ON OUR BROWSER IF OUR OUT "Apache http server can be found on the internet using any browser."

   ![apache2 installed](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/938d4a91-b1b0-42a7-9327-7fa923075f78)

    **IT WORKS  !!**

    
 ## Step 2-Installing Mysql

  Mysql has to be installed using the command  'sudo apt install mysql-server'. as it is running, there is always a prompt asking  if you want to
  
   continue with the installation. hence if you want to continue you type Y then ENTER.

   $ sudo mysql

    This is a command run that comnnects mysql server as the administrativedata base root. For security purposes on the data base a password reset 
    
    is needeed for the root user . Fot this prooject the password used is PassWord.1 Which was done with the command shown below before exiting 
    
    mysql.
    
![install mysqp,change password and exit console -1](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/f0ce490c-9bcb-424e-8670-8f40aa598011)

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';- allows change of password as demonstrated on the above 
   
   screen shot on line 10 just after the word  msql.

    All the other commands are preceded by green highlighted text . 

     These commands are 
     
- sudo apt install mysql-server

     -  sudo mysql
     
       -  mysql> exit


    ## Step 3 -Installing PHP

  
Installing PHP involves only 2 steps. 

   The first step is running command 'sudo apt install php libapache2-mod-php php-mysql'.

    this command ensures the 3packages which help ensure PHP is running smoothly all at once . 

These parkages are 
- php- procasses data which is relayed to the end user .

- php-mysql-allows communication between php and mysql data

 - libapache2-mod-php- enables PHP handles its files.

Attached below is a screen shot of the  the two coammands used  to show php installation plus proving  which php version has been installed with 

the command 'php -v'

![php packages installation and php -v](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/e38286d2-c07a-4dd1-8576-971c8ebe1c75)


## Step-4 Creating a virtual host using apache

 The domain set up here is called *projectlamp*
 
 We first start by creating a directory then assisgn the ownership of the directory referencing the current system user . The command below is used as demonstrated in the screenshot below.

  After creating a directory a file new file in Apaches sites available . Thes commands are 'sudo mkdir /var/www/projectlamp',' sudo chown -R 
  
  $USER:$USER /var/www/projectlamp', 'sudo chown -R $USER:$USER /var/www/project.conf

![directory and file creation,](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/e307bbe5-7ad3-4bdd-ad22-4dd16a93f15b)

 Next step involve enabling the vitual host  with a2ensite and disabling the Apache Default website by use of a2dissite as demonstrated below.

![a2ensite,a2dissite,ctl, config and ctl reload-1](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/7e369684-e38b-4822-831a-5e8e2f6f8794)
 
 APart from that we also need to reload and and check for any syntax errors ,run using the commands below as demostrated on the two last commands 
    
    on the above screenshot.

- sudo systemctl reload apache2

-  sudo apache2ctl configtest

  This long command helps use test if the virtual host is wirkinhf by creating an echo on the browser which can bee seen when you open the website
  
   using your ip adress.

   'sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html'

   ![echo](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/cec4e58f-46be-4e40-aeb4-76eb0f47ff50)

   ![hello lamp](https://github.com/NANA-2016/LAMP-STACK/assets/141503408/20a1b050-f3f5-4c9a-8584-1c2d2458004f)


 
  
  
    

    


 









