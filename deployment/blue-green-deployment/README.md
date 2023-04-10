This explains Blue Green Delpoyment

Step 1:
  Create a deployment named : bg-nginx-deployment-v1 with the image version 1.
  kubectl apply -f bluegreen-deploy-v1.yml

Step 2: Create a service named: bg-nginx-svc with the selector targetting the pods of created by      deployment 1 and pods with the label app: web_v1
  kubectl expose deployment bg-nginx-deployment-v1 --name bg-nginx-svc

Step 3:
  Create another deployment named : bg-nginx-deployment-v2 with the image version 2.
  kubectl apply -f bluegreen-deploy-v2.yml

Step 4:
  Edit the service and set the selector to the labels of the pod created by deployment 2 i.e app: web_v2
  kubectl edit service bg-nginx-svc
  Edit the selector
