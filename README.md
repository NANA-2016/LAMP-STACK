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

 









