# Dev-Ops Portfolio

Here are some of my best Devops Projects. I have explored various devops tools for different deployments. Feel free to contact me to learn more about my experience working with these tools.

***

[(1) End to end full automation deployment of a Javascript app (Amazon clone web app)](https://github.com/Mexxy-lab/Pumej_amazon-clone-app.git)

<img src="images/project-architecture.png?raw=true" alt=""/>

**Tools used:** Javascript, Jenkins, ArgoCD, Gitops, Docker, Containerization, DOCTL, Github, AWS. Digital Ocean, Terraform. 

**Project Objective / Keys steps:** To automate the deployment of a sample amazon website application written in Javascript using GitOps-ArgoCD and CD tool jenkins to Digital Ocean kubernetes cluster.

- Provisioned Kubernetes cluster using Digital Ocean as cloud provider. Deployed ArgoCD to the cluster.(You can do this via CLI / UI / Terraform).
- Created Docker file & jenkins pipeline job to automate the build process. The pipeline triggers a second job which updates the repository for ArgoCD deployment.
- Pushed imaged to docker hub using the jenkins pipeline job. Deployed the application using Argocd.
- Added Ingress (Ingress.yml) rules using nginx to the deployment namespace to control traffic from outside world using Ingress controller.
- Added Cert manager/jet-stack (issuer.yml) to the deployment to make the website look secured respectively. Cluster issuer type was used.
- Added monitoring tools Prometheus and Grafana via helm charts for monitoring purposes.

**Output result:** Webapp deployed and running with domain name amazon.pumej.com [**Build time 2mins 9secs**](https://github.com/Mexxy-lab/Pumej_amazon-clone-app.git).

<img src="images/amazon-app.png?raw=true"/>

- Picture showing deployed pods running in ArgoCD

<img src="images/Pod.png?raw=true"/>

- Picture showing monitoring tool grafana

<img src="images/cluster-monitoring.png?raw=true"/>

***

[(2) React Netflix app Containerized and Pushed to Amazon ECR locally](https://github.com/Mexxy-lab/Netflix_react-cloneapp.git)

<img src="images/projectdiagram.png?raw=true" alt=""/>

**Tools used:** React, npm, yarn, Jenkins, Gitops, Docker, Containerization, Github, AWS ECR, AWS CLI.

**Project Objective / Keys steps:** Automating the deployment of a sample netflix website application written in React using CD tool jenkins / Terraform to AWS kubernetes cluster.

- Installed dependencies using yarn install or npm install command.
- Run app locally to confirm code is functioning correctly. Used yarn start or npm start, confirm app listening on port 3000.
- Created terraform files to provision AKS cluster with AWS as provider using Fargate. Also set this up with jenkins pipeline job.
- Created a docker file to dockerize the application. Has 2 stages Node image for building frontend assets, nginx stage to serve frontend assets.
- Build the docker image using docker build command..... docker build -t pumej/netflix:v1.0.0 .
- Containerize the application using the built image. Use docker run command - docker run -itd --name mexy-netflix -p 3000:80 pumej/netflix:v1.0.0
- Created a jenkins pipeline job to automate the entire process, pushing image to an ECR repo.
- Created a deployment.yaml file to deploy application to AWS EKS cluster.

**Output result:** Webapp deployed and running with load balancer IP aadr. [**Build time 3mins 8secs** minutes](https://github.com/Mexxy-lab/Netflix_react-cloneapp.git).

<img src="images/pipeline-job.png?raw=true"/>

- Picture showing deployed website running with load balancer IP address of AWS cluster

<img src="images/website-ipaddr.png?raw=true"/>

<img src="images/aws-ipaddr.png?raw=true"/>

- Picture showing terraform apply command completed successfully the provisioning of AWS cluster with Fargate service

<img src="images/terraform-apply.png?raw=true"/>

**Opportunities / Improvements:** You can improve this job with following steps

- Adding an ingress rule to the deployment to manage incoming traffic.
- You can also add a DNS configuration to make the site look prune. 
- You can also make use of the lets encrypt feature to make the website look secure. 

***

[(3) Containerization of a python web application using Docker containerization (Cabana website)](https://github.com/Mexxy-lab/Cabana-website-project.git)

<img src="images/project-architecture.png?raw=true" alt=""/>

**Tools used:** Python, Jenkins, Gitops, Docker Desktop, Docker Containerization, Github, Dockerhub repository, K8s, ArgoCD.

**Project Objective / Keys steps:** To containerize a website application written in python using Docker and CD tool jenkins to push image to DH repo.

- Created Docker file & jenkins pipeline job to automate the build process. The pipeline triggers a second job which updates the repository for ArgoCD deployment. docker build -t mycabanapp22:v1.0.0 .
- Created a MySQL container and connected this to our running container to access DB. docker run -d --name mysql-container -e MYSQL_ROOT_PASSWORD=mekulus -p 3306:3306 mysql:latest
- Pushed imaged to docker hub using the jenkins pipeline job. 
- Created a docker container using docker run command. docker run -d -p 8339:3000 mycabanapp22:v1.0.0

**Output result:** Webapp deployed and running on localhost port 3000 [**Build time 2mins 7secs** minutes](https://github.com/Mexxy-lab/Cabana-website-project.git).

<img src="images/webpage-localhost.png?raw=true"/>

- Picture showing Container running on localhost:3000

<img src="images/containerlogs.png?raw=true"/>

- Picture showing Container logs for MySQL container

<img src="images/mysqlcontainerlogs.png?raw=true"/>

***

[(4) Setting up Jenkins on an Ubuntu server using Terraform on Digital Ocean Cloud platform](https://github.com/Mexxy-lab/pumej_jenkins-project.git)

<img src="images/jenkins.png?raw=true" alt=""/>

**Tools used:** Terraform, Jenkins, Gitops, bash, Github, Digital Ocean, Ubuntu terminal, Linux.

**Project Objective / Keys steps:** Setting up Jenkins on an Ubuntu server using Terraform to provision resource in Digital Ocean cloud platform.

- Created the provider main and variable .tf files for terraform deployment, also created the terraform.tfvars file.
- main.tf file: contains the resources we are asking to be deployed to cloud. In our case would be a droplet server.
- variables.tf file: Has all variables assigned in your main file.
- terraform.tfvars file: this files holds the config details of the server we are looking to create for a specific environment. Enables you to provision your resources to different environment or namespace.
- Ran terraform commands terraform fmt, init, validate, plan and apply. To spin up the resource. In our case a single droplet.
- SSH into the server using its public IP address, do this from the .ssh directory on your local PC.
- Installed all dependencies need for jenkins to run, then added a jenkins user to sudo group.
- By default, username is admin and jenkins runs on port 8080, use sudo cat /var/lib/jenkins/secrets/initialAdminPassword to get initial password 
- Added a nginx reverse proxy server and installed certbot package. Certbot provides a variety of ways to obtain SSL certificates through plugins.

**Output result:** Jenkins installed and running with customized domain name jenkinsweb.pumej.com & jenkins.pumej.com. [**Run time 3mins 8secs** minutes](https://github.com/Mexxy-lab/pumej_jenkins-project.git).

<img src="images/jenkins.png?raw=true"/>

- Picture showing deployed website running with server IP address not secured

<img src="images/jenkinsunsecure.png?raw=true"/>

- Picture showing terraform apply / plan command completed successfully provisioning droplet with IP 159.223.180.236

<img src="images/terraformapply.png?raw=true"/>

<img src="images/terraformplan.png?raw=true"/>

- Picture showing plugins installation on the deployed jenkins server 

<img src="images/plugins.png?raw=true"/>

***

[(5) Creating a Terraform Module for EKS Cluster and publishing to Github ](https://github.com/Mexxy-lab/terraform-aws-pumej_modules-eks.git)

<img src="images/jenkins.png?raw=true" alt=""/>

**Tools used:** Terraform, Gitops, bash, Github, AWS, Linux/Ubuntu terminal.

**Project Objective / Keys steps:** To create a Module for EKS Cluster provisioning using terraform and publishing it to Github project. Modules in terraform is like a container which enables you to reuse your code in different environments.

- Created the provider, main, output and variable .tf files for terraform deployment in sub-directory called modules.
- main.tf file: contains the resources we are asking to be deployed to cloud. In this case would be an EKS cluster.
- cd out of working directory and create a main.tf calling your modules folder. Specify the path to your modules subdirectory. 
- Run terraform commands terraform fmt, init, validate, plan to ensure no errors in same directory. 
- Created a new directory pumej-modules and copied all files from the subdirectory to new directory, added a README.md file also and pushed the to remote repository.
- Also added the final module to terraform cloud platform. You would see it listed as "pumej_modules-eks".

**Output result:** Module created and pushed to GitHub and also published on terraform cloud platform as pumej_modules-eks. [**Active**](https://github.com/Mexxy-lab/terraform-aws-pumej_modules-eks.git).

<img src="images/module.png?raw=true"/>

- Picture showing module pushed to Github

<img src="images/module.png?raw=true"/>

- Picture showing module listed on terraform page

<img src="images/eksmodule.png?raw=true"/>

- Picture showing created module published on terraform cloud platform 

<img src="images/module-onterraformcld.png?raw=true"/>

***

[(3) Containerization of a python web application using Docker containerization (Cabana website)](https://github.com/Mexxy-lab/Cabana-website-project.git)

<img src="images/project-architecture.png?raw=true" alt=""/>

**Tools used:** Python, Jenkins, Gitops, Docker Desktop, Docker Containerization, Github, Dockerhub repository, K8s, ArgoCD.

**Project Objective / Keys steps:** To containerize a website application written in python using Docker and CD tool jenkins to push image to DH repo.

- Created Docker file & jenkins pipeline job to automate the build process. The pipeline triggers a second job which updates the repository for ArgoCD deployment. docker build -t mycabanapp22:v1.0.0 .
- Created a MySQL container and connected this to our running container to access DB. docker run -d --name mysql-container -e MYSQL_ROOT_PASSWORD=mekulus -p 3306:3306 mysql:latest
- Pushed imaged to docker hub using the jenkins pipeline job.
- Created a docker container using docker run command. docker run -d -p 8339:3000 mycabanapp22:v1.0.0

**Output result:** Webapp deployed and running on localhost port 3000 [**Build time 2mins 7secs** minutes](https://github.com/Mexxy-lab/Cabana-website-project.git).

<img src="images/webpage-localhost.png?raw=true"/>

- Picture showing Container running on localhost:3000

<img src="images/containerlogs.png?raw=true"/>

- Picture showing Container logs for MySQL container

<img src="images/mysqlcontainerlogs.png?raw=true"/>

***