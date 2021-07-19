# Welcome to AWS-Training-Task-3


## Task 3
1. Create an AWS EC2 instance
2. Configure the instance with Apache Webserver.
3. Download php application name "WordPress".
4. As wordpress stores data at the backend in MySQL
5. Database server. Therefore, you need to setup a MySQL server using AWS RDS service using Free Tier.
6. Provide the endpoint/connection string to the WordPress application to make it work. 


### Step by step Implementation:
#### Step 1: Create an AWS EC2 instance 

![image](https://user-images.githubusercontent.com/75135128/126073880-2eebc7be-a25c-4bf8-97bb-2c02314f84c2.png)


#### Step 2: Configure the instance with Apache Webserver.
##### Install webserver
```
yum install httpd
```
![image](https://user-images.githubusercontent.com/75135128/126074053-15da8507-a23a-4c56-afc9-730ad8b92992.png)

##### Check installed version of webserver
```
rpm -q httpd
```
![image](https://user-images.githubusercontent.com/75135128/126073981-29f7cf52-8cda-4ebf-b665-d53c80d86d1e.png)

##### Start and enable webserver

```
systemctl start httpd
systemctl enable httpd
```

![image](https://user-images.githubusercontent.com/75135128/126074148-76c4ab8e-0310-49cb-a313-4ad14097e751.png)

#### Step 3: Download MySQL
```
yum install mysql -y
```
![image](https://user-images.githubusercontent.com/75135128/126076040-c206118f-da8e-42c3-8edf-c7554552938b.png)

#### Step 4: Download and install php application 
```
yum install php -y \
amazon-linux-extras enable php7.4 \
yum clean metadata
yum install php php-common php-pear 
yum install php-{cgi,curl,mbstring,gd,mysqlnd,gettext,json,xml,fpm,intl,zip} -y
php -v
```
![image](https://user-images.githubusercontent.com/75135128/126075935-1afe19c5-6a60-43b0-af02-c9b578c0773f.png)


#### Step 5: Download "WordPress"
##### Download Wordpress
```
wget https://wordpress.org/latest.tar.gz
```
##### Extract Wordpress
```
tar -xzvf latest.tar.gz
```

##### Move content of wordpress folder into /var/www/html/
```
mv -vf wordpress/* /var/www/html/
```

![image](https://user-images.githubusercontent.com/75135128/126200250-f5bfa260-cc6b-4dd8-973b-81c742184229.png)

#### Step 6: Creat RDS DataBase in AWS

Setup a MySQL server using AWS RDS service using Free Tier.

https://user-images.githubusercontent.com/75135128/126077287-d42d1047-19f0-4152-924e-e4015d82193d.mp4

#### Step 6: Provide the endpoint/connection string to the WordPress application to make it work.

##### Check the connectivity of your RDS database
```
mysql -h  endpoint  -u username -p
```
##### Create one database for wordpress
```
create database wordpressT3;
```
![image](https://user-images.githubusercontent.com/75135128/126208085-4b485f62-3eff-4ddd-9af8-601e6b762c88.png)

##### Hit your webserver with your public ip{ you got **/wp-admin/setup-config.php** in url automatically} click let's go button

![image](https://user-images.githubusercontent.com/75135128/126204050-480d3e56-bda6-4a6d-9f11-354e828d2081.png)

##### Fill your credentials and sumbit
```
Database Name:  Name of the database you created above
Username: username of your RDS databse
Password: Password of yourd RDS database
Database Host:  End point of your RDS databse
```
![image](https://user-images.githubusercontent.com/75135128/126207891-b575fbe8-6dfc-47c6-a77f-319ae1798e4e.png)

##### You got this page
![image](https://user-images.githubusercontent.com/75135128/126208755-1d071b67-1a41-432d-bbb1-d8ecd57801af.png)

##### Save the content of the page into wp-config.php file
```
vim wp-config.php
```
![image](https://user-images.githubusercontent.com/75135128/126209114-38f5ff87-8b4a-4cf6-9a61-f6d28c26f251.png)

![image](https://user-images.githubusercontent.com/75135128/126209182-ee133c19-1490-49ad-a0eb-ae7507ec264f.png)

##### Restart your webserver and go back to your web browser and Hit Run the Installation button
```
systemctl restart httpd
```

##### Enter details here and install wordpress
![image](https://user-images.githubusercontent.com/75135128/126213917-c0f7c199-0263-4777-9d8d-b265e93f7ea7.png)

##### After Successful installation you got Success page

![image](https://user-images.githubusercontent.com/75135128/126214132-f01566f0-c0f2-4d3e-a72a-cfc518580018.png)

##### Login page 
![image](https://user-images.githubusercontent.com/75135128/126214319-b7da59de-b160-4d5d-8a34-c6a4f8b27739.png)

##### After login 
![image](https://user-images.githubusercontent.com/75135128/126214388-7c0f54e1-8da0-4812-9e0b-69a90e18213c.png)

##### If you hit you ip then you get
![image](https://user-images.githubusercontent.com/75135128/126214553-c261fee4-b21c-49a8-ab30-00edcf3692bb.png)


#### So following these steps you can deploy WordPress into the AWS and connect to the database in the RDS service provided by AWS. 

### Thank you for reading this article
