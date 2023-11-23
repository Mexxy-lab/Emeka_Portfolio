# Dev-Ops Portfolio

Here are some of my best Devops Projects. I have explored various devops tools for different deployments. Feel free to contact me to learn more about my experience working with these tools.

***

[End to end full automation deployment of a Javascript app (Amazon clone web app)](https://github.com/Mexxy-lab/Pumej_amazon-clone-app.git)

<img src="images/project-architecture.png?raw=true"/>

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

[Diagnosis of breast cancer using a logistic classifier](https://github.com/suvo-gh/Orthopedic-Patients-Classification)

<img src="images/breast-cancer.jpeg?raw=true"/>

**Skills used:** Python, Pandas, SKlearn, Matplotlib

**Project Objective:** Identification of the type of Breast Cancer for quicker diagnosis. This assists professionals in the medical field to take appropiate measures to accurately diagnose, treat and save lives. 

**Quantifiable result:** We could Classify the type of tumor resulting in [**80%** accuracy using K-means algorithm](https://github.com/suvo-gh/Orthopedic-Patients-Classification).

- Used logistic regression to identify a tumour as malignant or benign based on various attributes
- Classified tumors as benign or malignant by studying patterns in measured attributes of those tumors
- Used Logistic regression classifier & optimized the accuracy by using the ROC curve
- Explored a machine learning approach to medical diagnosis

***

[Identifying given picture is a Cat or a Dog](https://github.com/suvo-gh/Cat_or_Dog_prediction/blob/main/CNN_Project%20(Image_Classification).ipynb)

<img src="images/Dog-and-Cat.jpeg?raw=true"/>

**Skills used:** Python, Keras, Tensorflow

**Project Objective:** Prediction of whether a given image is a Cat or a Dog using Convolutional Neural Networks which may be further implemented as a feature in a bigger project.

**Quantifiable result:** We could train the Convolutional Neural Network to attain a accuracy of [**80%** using **23** epochs](https://github.com/suvo-gh/Cat_or_Dog_prediction/blob/main/CNN_Project%20(Image_Classification).ipynb).

- Added multiple convolution and pooling layers
- Training model on basis of given data
- Fitting the CNN to see if the provided image is dog or cat
- Data Source: https://drive.google.com/drive/folders/15SG-chdqEwcrNAY39RTZJjvl-UwiZo_e?usp=sharing