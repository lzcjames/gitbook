# Set up a Web Server on Oracle Cloud

## Usesful links
1. [Create free ubuntu vps in oraclecloud with nginx “always free”](https://medium.com/@saiful103a/create-free-ubuntu-vps-in-oraclecloud-with-nginx-always-free-f07d9d7fad40)

2. [使用免費的 Oracle Cloud 架設 Ubuntu Web Server](https://yanagiragi.wordpress.com/2019/09/19/%E4%BD%BF%E7%94%A8%E5%85%8D%E8%B2%BB%E7%9A%84-oracle-cloud-%E6%9E%B6%E8%A8%AD-ubuntu-web-server/)

3. [How to connect remote oracle VM (Linux/Mac, Windows)](https://docs.oracle.com/en-us/iaas/Content/GSG/Tasks/testingconnection.htm) 
4. [Use an SSH Key with Non-root Users](https://www.vultr.com/docs/using-your-ssh-key-to-login-to-non-root-users)

## Set a custom domain name for VM
1. Chose a free domain name in freenom.com
2. Click panel `Service` -> `My domain` -> `Manage domain` -> `Manage Freenom DNS` than add a record.
3. A record can be :**Name**: *(empty)*,  **Type**: A,  **TTL**: 3600,  **Target**: *Your VM public IP*
