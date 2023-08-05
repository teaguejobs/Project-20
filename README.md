**MIGRATION TO THE СLOUD WITH CONTAINERIZATION**

Until now, we have been using VMs (AWS EC2) in Amazon Virtual Private Cloud (AWS VPC) to deploy your web solutions, and it works well in many cases.

We have learned how easy to spin up and configure a new EC2 manually or with such tools as Terraform and Ansible to automate provisioning and configuration.

We have also deployed two different websites on the same VM; this approach is scalable, but to some extent; imagine what if you need to deploy many small applications (it can be web front-end, web-backend, processing jobs, monitoring, logging solutions, etc.) and some of the applications will require various OS and runtimes of different versions and conflicting dependencies – in such case you would need to spin up serves for each group of applications with the exact OS/runtime/dependencies requirements. When it scales out to tens/hundreds and even thousands of applications (e.g., when we talk of microservice architecture), this approach becomes very tedious and challenging to maintain.

In this project, we will learn how to solve this problem and practice the technology that revolutionized application distribution and deployment back in 2013! We are talking of Containers and imply Docker. Even though there are other application containerization technologies, Docker is the standard and the default choice for shipping your app in a container!

**Deploying Application Using Docker**

***MySQL in container***

**Step 1: Pull MySQL Docker Image from Docker Hub Registry**

We pull the mysql image from the dockerhub repository(public) into our local server machine.

We run a container from this image and setup the mysqldb environment variables

docker run --name <container_name> -e `MYSQL_ROOT_PASSWORD=<my-secret-pw> -d mysql/mysql-server:latest`

![alt text](./images/mysql.PNG)

**CONNECTING TO THE MYSQL DOCKER CONTAINER**

`$ docker exec -it mysql bash`

or

`$ docker exec -it mysql mysql -uroot -p`

![alt text](./images/verify1.PNG)

