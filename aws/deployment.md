## STEP 1
lauch EC2 instance   
install docker  
build docker image 

### connect to EC2
ssh -i my-student-test.pem ec2-user@3.144.130.83  
//切换到root  
sudo su
//安装docker
curl -fsSL https://get.docker.com -o get-docker.sh  
yum install docker  
//验证是否安装成功，出现版本信息
docker --version
//启动docker
systemctl start docker
//查看docker状态
systemctl status docker
别忘了启动本地docker
[本地构建springboot项目镜像](https://zhuanlan.zhihu.com/p/478905946)
//本地构建springboot项目镜像
mvn spring-boot:build-image
//启动镜像程序
docker run -p 9090:9090 -t demo-application:0.0.1-SNAPSHOT
//构建mysql
docker-compose up -d
//进入指定容器
docker exec -it CONTAINER_ID /bin/bash












## STEP 2
Creating ECR
Login to ECR
Tag existing image as AWS ECR repo
Push image into ECR

## STEP 3
Creaing Application Load Balancer

## STEP 4
Creating Task definition | Create AWS ECS cluster | Create Service

## STEP 5 
validation
ssh -i my-student-test.pem ec2-user@3.144.130.83





