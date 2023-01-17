### Build from the YAML file

<blockquote>
docker-compose up -d --build
</blockquote>

Change to users-api, build the image

docker build -t [user_name]/kube-data-demo .

kubectl apply -f users-deployment.yml
kubectl apply -f users-service.yml
kubectl apply -f auth-deployment.yml
kubectl apply -f auth-service.yml
kubectl apply -f tasks-deployment.yml
kubectl apply -f tasks-service.yml
minikube service users-service

docker build -t [user_name]/kube-demo-auth .
docker build -t [user_name]/kube-demo-users .
docker build -t [user_name]/kube-demo-tasks .
docker build -t [user_name]/kube-demo-frontend .

# For testing purpose to run frontend
docker run -p 80:80 --rm -d howcool/kube-demo-frontend