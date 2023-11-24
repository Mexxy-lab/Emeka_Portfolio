# Dev-Ops Portfolio

Here are some of my best Devops Projects. I have explored various devops tools for different deployments. Feel free to contact me to learn more about my experience working with these tools.

***

[(1) End to end full automation deployment of a Javascript app (Amazon clone web app)](https://github.com/Mexxy-lab/Pumej_amazon-clone-app.git)

<img src="images/project-architecture.png?raw=true" alt=""/>

**Tools used:** Javascript, Jenkins, ArgoCD, Gitops, Docker, Containerization, Github, AWS. Digital Ocean, Terraform. 

**Project Objective / Keys steps:** To automate the deployment of a sample amazon website application written in Javascript using GitOps-ArgoCD and CD tool jenkins to Digital Ocean kubernetes cluster.

- Provisioned Kubernetes cluster using Digital Ocean as cloud provider. Deployed ArgoCD to the cluster.(You can do this via CLI / UI / Terraform).
- Created Docker file & jenkins pipeline job to automate the build process. The pipeline triggers a second job which updates the repository for ArgoCD deployment.
- Pushed imaged to docker hub using the jenkins pipeline job. Deployed the application using Argocd.
- Added Ingress (Ingress.yml) rules using nginx to the deployment namespace to control traffic from outside world using Ingress controller.
- Added Cert manager/jet-stack (issuer.yml) to the deployment to make the website look secured respectively. Cluster issuer type was used.
- Added monitoring tools Prometheus and Grafana via helm charts for monitoring purposes.

**Output result:** Webapp deployed and running with domain name amazon.pumej.com [**Build time 184** minutes](https://github.com/Mexxy-lab/Pumej_amazon-clone-app.git).

<img src="images/amazon-app.png?raw=true"/>

- Picture showing deployed pods running in ArgoCD

<img src="images/Pod.png?raw=true"/>

- Picture showing monitoring tool grafana

<img src="images/cluster-monitoring.png?raw=true"/>

***

[(2) End to end full automation deployment of a Javascript app (Amazon clone web app)](https://github.com/Mexxy-lab/Pumej_amazon-clone-app.git)

<img src="images/project-architecture.png?raw=true" alt=""/>

**Tools used:** Javascript, Jenkins, ArgoCD, Gitops, Docker, Containerization, Github, AWS. Digital Ocean, Terraform.

**Project Objective / Keys steps:** To automate the deployment of a sample amazon website application written in Javascript using GitOps-ArgoCD and CD tool jenkins to Digital Ocean kubernetes cluster.

- Provisioned Kubernetes cluster using Digital Ocean as cloud provider. Deployed ArgoCD to the cluster.(You can do this via CLI / UI / Terraform).
- Created Docker file & jenkins pipeline job to automate the build process. The pipeline triggers a second job which updates the repository for ArgoCD deployment.
- Pushed imaged to docker hub using the jenkins pipeline job. Deployed the application using Argocd.
- Added Ingress (Ingress.yml) rules using nginx to the deployment namespace to control traffic from outside world using Ingress controller.
- Added Cert manager/jet-stack (issuer.yml) to the deployment to make the website look secured respectively. Cluster issuer type was used.
- Added monitoring tools Prometheus and Grafana via helm charts for monitoring purposes.

**Output result:** Webapp deployed and running with domain name amazon.pumej.com [**Build time 184** minutes](https://github.com/Mexxy-lab/Pumej_amazon-clone-app.git).

<img src="images/amazon-app.png?raw=true"/>

- Picture showing deployed pods running in ArgoCD

<img src="images/Pod.png?raw=true"/>

- Picture showing monitoring tool grafana

<img src="images/cluster-monitoring.png?raw=true"/>

***

[(3) End to end full automation deployment of a Javascript app (Amazon clone web app)](https://github.com/Mexxy-lab/Pumej_amazon-clone-app.git)

<img src="images/project-architecture.png?raw=true" alt=""/>

**Tools used:** Javascript, Jenkins, ArgoCD, Gitops, Docker, Containerization, Github, AWS. Digital Ocean, Terraform.

**Project Objective / Keys steps:** To automate the deployment of a sample amazon website application written in Javascript using GitOps-ArgoCD and CD tool jenkins to Digital Ocean kubernetes cluster.

- Provisioned Kubernetes cluster using Digital Ocean as cloud provider. Deployed ArgoCD to the cluster.(You can do this via CLI / UI / Terraform).
- Created Docker file & jenkins pipeline job to automate the build process. The pipeline triggers a second job which updates the repository for ArgoCD deployment.
- Pushed imaged to docker hub using the jenkins pipeline job. Deployed the application using Argocd.
- Added Ingress (Ingress.yml) rules using nginx to the deployment namespace to control traffic from outside world using Ingress controller.
- Added Cert manager/jet-stack (issuer.yml) to the deployment to make the website look secured respectively. Cluster issuer type was used.
- Added monitoring tools Prometheus and Grafana via helm charts for monitoring purposes.

**Output result:** Webapp deployed and running with domain name amazon.pumej.com [**Build time 184** minutes](https://github.com/Mexxy-lab/Pumej_amazon-clone-app.git).

<img src="images/amazon-app.png?raw=true"/>

- Picture showing deployed pods running in ArgoCD

<img src="images/Pod.png?raw=true"/>

- Picture showing monitoring tool grafana

<img src="images/cluster-monitoring.png?raw=true"/>

***