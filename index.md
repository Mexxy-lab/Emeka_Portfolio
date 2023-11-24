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

<img src="images/project-architecture.png?raw=true" alt=""/>

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