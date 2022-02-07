# MYSQL node on Kubernetes using Kubernetes Artifacts 

we need to install the MYSQL database on kubernetes using kubernetes artifact files i.e 

mysql-deployment.yaml 

mysql-configmap.yaml => Store host & port in configmap

mysql-service.yaml =>  is used so that it is accessible only inside the cluster.

mysql-secret.yaml => Store MySQL root password in secret.

# Steps to follow :

# Step 1 : Clone github repository
  git clone https://github.com/18Jaspal01/MYSQL-node-on-Kubernetes-using-Kubernetes-Artifacts-.git
  
# Step 2 : Go to directory
 cd MYSQL-node-on-Kubernetes-using-Kubernetes-Artifacts-/

# Step 3 : Create namespace
kubectl create namespace mysql

# Step 4 : Set current namespace to mysql
kubectl config set-context --current --namespace=mysql

# Step 5 : Create secret db-secret
kubectl create -f mysql-secret.yaml

# Step 6 : Create deployment
kubectl create -f mysql-deployment.yaml

# Step 7 : Create configmap db-config
kubectl create -f mysql-configmap.yaml 

# Step 8 : Create service
kubectl create -f mysql-service.yaml

# Step 9 :
kubectl get pods --watch

NAME                        READY   STATUS    RESTARTS   AGE
mysql-db-7d8f7889fc-j8shj   0/1     Pending   0          84s


![Screenshot](https://user-images.githubusercontent.com/86924458/152532153-5970e8af-0aa2-4171-89d8-97edf66c969e.png)


