```

// manual run 

EC2 | Amazon linux | t3.medium | key.pem 
try ssh 
SG: 5000 (Inbound)

sudo yum update -y 
sudo yum install git python -y 
sudo yum install pip 
pip install flask
git clone https://github.com/atulkamble/Inventory-Manager.git
cd /Inventory-Manager
cd app
python3 main.py

// go out of running code using Cntrl+C


// docker phase 

sudo yum install docker -y 
sudo systemctl start docker 
sudo systemctl enable docker 
sudo docker login 

sudo docker build -t username/inventory-management .
sudo docker images 
sudo docker push username/inventory-management

sudo docker run -d -p 5000:5000 username/inventory-management

sudo docker logs log-id 
sudo docker container ls 
sudo docker container stop container-id 

sudo mkdir -p /usr/local/lib/docker/cli-plugins
sudo curl -SL https://github.com/docker/compose/releases/download/v2.27.0/docker-compose-linux-x86_64 -o /usr/local/lib/docker/cli-plugins/docker-compose
sudo chmod +x /usr/local/lib/docker/cli-plugins/docker-compose

docker compose version

sudo docker compose up --build

http://instance-ip:5000

cd k8s 

// on minikube 

// docker desktop running in background 

minikube start

kubetcl apply -f deployment.yaml 
kubectl apply -f service.yaml 

kubectl get deployments 
kubectl get pods
kubectl get services 

minikube dashboard 

http://127.0.0.1:5000/

// on eks 

eksctl create cluster \
--name mycluster \
--region us-east-1 \
--nodegroup-name mynodes \
--node-type t3.micro \
--nodes 2 \
--nodes-min 2 \
--nodes-max 2 \
--managed

eksctl create cluster --name mycluster --region us-east-1 --nodegroup-name mynodes --node-type t3.micro --nodes 2 --nodes-min 2 --nodes-max 2 --managed
```
