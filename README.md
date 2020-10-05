# jaxlondon-deployment
Deployment for JAX London Service A and Service B
This repo is about how to deploy the two microservices to Kubernetes. 

## Checkout service a 
  git clone git@github.com:Emily-Jiang/jaxlondon-service-a.git
  cd jaxlondon-service-a
  mvn verify
  docker build -t liberty-service-a:1.0 .

## Checkout service b 
  git clone git@github.com:Emily-Jiang/jaxlondon-service-b.git
  cd jaxlondon-service-b
  mvn verify
  docker build -t liberty-service-b:1.0 .

## Checkout the deployment
  git clone git@github.com:Emily-Jiang/jaxlondon-deployment.git
  kubectl apply -f deployment-liberty.mf

  kubectl get pods
  

emilyjiang@Emilys-MBP Deployment % kubectl get pods
NAME                                         READY   STATUS    RESTARTS   AGE
12factor-app-a-deployment-7c85569d77-2qmv4   2/2     Running   0          26s
12factor-app-a-deployment-7c85569d77-xmlm8   2/2     Running   0          26s
12factor-app-b-deployment-649f7f7c78-fwvqt   2/2     Running   0          26s
12factor-app-b-deployment-649f7f7c78-m6qql   2/2     Running   0          26s

Test your microservices by hitting the following url http://localhost:30080
