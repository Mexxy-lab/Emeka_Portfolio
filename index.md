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

[(6) Real Time Blue Green Deployment with argocd and argo-rollout using Jenkins](https://github.com/Mexxy-lab/pumej-argo-rollout_nodejs.git)

<img src="images/argocdarchitecture.png?raw=true" alt=""/>

**Tools used:** Terraform, Jenkins, Gitops, Docker, Docker Containerization, Github, Dockerhub repository, K8s, ArgoCD, Argocd rollout, argocd cli.

**Project Objective / Keys steps:** To demonstrate Real time Blue Green Deployment of an application using argocd and argo-rollout using Jenkins. Argo Rollouts is a Kubernetes controller and set of CRDs which provide advanced deployment capabilities such as blue-green, canary, canary analysis, experimentation, and progressive delivery features to Kubernetes.

- Confirmed source code works locally by running node server.js to run application locally.
- Created a CI/CD pipeline job to build and push image to dockerhub repository. This was done with Jenkins pipeline job triggering a second manifest.  
- Set up terraform files to provision k8s cluster in AWS. Ran terraform commands init, validate, plan to confirm code is okay and applied it. 
- Created a rollout.yml file with strategy type as bluegreen for our progressive deployment. Also set up 2 service.yml files svc-active and svc-preview, both running same version.
- Deployed the rollout.yml file using ArgoCD to the provisioned cluster.
- Installed Argo Rollouts controller onto the provisioned Cluster using standard commands for deployment. Confirmed both services running version 1 of our application. 
- Applied changes to our application and pushed to GitHub repository, argocd picked up changes automatically. 
- You can now access rollout dashboard to promote the new deployment and see how it migrates it. Refer to below pictures. 

**Output result:** Webapp deployed using ArgoCD and running on localhost [**Build time 2mins 7secs** minutes](https://github.com/Mexxy-lab/rollout-manifests.git).

- Picture showing deployed pods running in argocd

<img src="images/podsdeployed.png?raw=true"/>

- Picture showing CI/CD pipeline build of deployed application

<img src="images/pipelinebuild.png?raw=true"/>

- Picture showing webpage running version 1

<img src="images/appversion1.png?raw=true"/>

- Picture showing services running both svc-active and svc-preview 

<img src="images/svc-preview.png?raw=true"/>
<img src="images/svc-active.png?raw=true"/>

- Picture showing rollout dashboard prior to upgrade, running revision 1 and argocd deploying the updated app

<img src="images/rollout-dashboard.png?raw=true"/>
<img src="images/argocd-delpoymentwip.png?raw=true"/>

- Picture showing rollout dashboard after upgrade, running revision 1/2 and argocd deployed pods all running

<img src="images/pod-deployed.png?raw=true"/>
<img src="images/rollout-completed.png?raw=true"/>

- Picture showing rollout dashboard after upgrade, running revision 1/2 and argocd deployed pods all running version 2

<img src="images/completeddeployment.png?raw=true"/>
<img src="images/rolloutdashboard-done.png?raw=true"/>

- Picture showing webpage running version 2 of deployed application

<img src="images/webpage-v2.png?raw=true"/>

***

[(7) Deploying springboot javatype petclinic app using a remote Dital Ocean server/droplet using Terraform](https://github.com/Mexxy-lab/springboot-app_project.git)

<img src="images/springbook-archit.png?raw=true" alt=""/>

**Tools used:** Terraform, java, maven, Gitops, Docker, Docker Containerization, Github, Dockerhub repository, K8s cluster DO, ArgoCD, argocd cli.

**Project Objective / Keys steps:** To deploying the springbook petclinic application using a remote server provisioned via terraform from local host. 

- Created terraform files for provisioning of DO droplet in cloud Digital Ocean (main.tf, providers.tf, variables.tf and terraform.tfvars files).
- Connected to remote server using ssh protocol. You can also connect via DO console. Created a user and assigned user to sudo group. 
- Created a shell script -petclinic.sh file to install dependents (Java 17, Maven, Docker, Python VENV, PIP, terraform, kubectl, and Doctl), ran script using sh command.
- Authenticated CLI with docker and also added user to docker group. Git cloned repository with source codes and tested app locally using mvn/java commands. 
- Created docker file for building the image and ran build successfully as pumejlab/petclinic:latest and pushed image to dockerhub using docker build/push commands. 
- Created terraform file main.tf to provision a DO k8s cluster, and updated kubeconfig file. 
- Created the deployment.yml manifest file to deploy application to cluster with target port set to 8080. 
- Deployed application to provisioned cluster using kubectl apply -f command.

**Output result:** Webapp deployed successfully running on localhost [**Build time 2mins 7secs** minutes](https://github.com/Mexxy-lab/springboot-app_project.git).

- Picture showing app test/build successful on local premise 

<img src="images/apptestlocally.png?raw=true"/>
<img src="images/apptest.png?raw=true"/>
<img src="images/apptest2.png?raw=true"/>

- Picture showing springbook petclinic application on localhost 8085

<img src="images/webpagelocal.png?raw=true"/>

- Picture showing docker build was successful

<img src="images/buildimage.png?raw=true"/>

- Picture showing image successfully pushed to dockerhub repository

<img src="images/dockerpush.png?raw=true"/>
<img src="images/imageondockerhub.png?raw=true"/>

- Picture showing pods running on the K8s cluster provisioned on minikube

<img src="images/docluster.png?raw=true"/>

- Picture showing rollout dashboard after upgrade, running revision 1/2 and argocd deployed pods all running

<img src="images/webapponminkube.png?raw=true"/>

***