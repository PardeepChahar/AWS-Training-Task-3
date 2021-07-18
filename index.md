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
```yum install httpd```
![image](https://user-images.githubusercontent.com/75135128/126074053-15da8507-a23a-4c56-afc9-730ad8b92992.png)

##### Check installed version of webserver
```rpm -q httpd```
![image](https://user-images.githubusercontent.com/75135128/126073981-29f7cf52-8cda-4ebf-b665-d53c80d86d1e.png)

##### Start and enable webserver

```systemctl start httpd```
```systemctl enable httpd```

![image](https://user-images.githubusercontent.com/75135128/126074148-76c4ab8e-0310-49cb-a313-4ad14097e751.png)

#### Step 3: Download php application 
```yum install php -y```
![image](https://user-images.githubusercontent.com/75135128/126075935-1afe19c5-6a60-43b0-af02-c9b578c0773f.png)

#### Step 4: Download MySQL
```yum install mysql -y```
![image](https://user-images.githubusercontent.com/75135128/126076040-c206118f-da8e-42c3-8edf-c7554552938b.png)

#### Step 5: Download "WordPress"
##### Download Wordpress
```wget https://wordpress.org/latest.tar.gz```
##### Extract Wordpress
```tar -xzvf latest.tar.gz```

##### Move wordpress to /var/www/html/
```mv -vf wordpress/ /var/www/html/```

![image](https://user-images.githubusercontent.com/75135128/126076343-afc000c0-85f6-4a39-898e-19ddf4254419.png)

#### Step 6: Creat RDS DataBase in AWS



https://user-images.githubusercontent.com/75135128/126077287-d42d1047-19f0-4152-924e-e4015d82193d.mp4



Therefore, you need to setup a MySQL server using AWS RDS service using Free Tier.
#### Step 6: Provide the endpoint/connection string to the WordPress application to make it work. 
