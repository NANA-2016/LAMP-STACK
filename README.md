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

   

   










