# fss-cloud
 Step-1 : Code
You may develop code or download from a existing repo into your favourite IDE

Step-2 : Build the executable
Build the executable from the code using the build tool you are familiar with (e.g. ant,maven,gradle etc.)

Step-3 : Create a Dockerfile
Create the docker file using your IDE and put the instructions as required by the container

Step-4 : Build a docker image  - docker build, docker image ls
Build the image using docker command and verify the image

Step 5 : Spin a container from the image and test – docker run, docker container ls, docker container ls –a, docker exec, docker logs, docker history, docker commit
Spin a container on the image being built and test the application. Enter to the container in interactive mode and
run various O/S commands. Stop the container


Step 6(Optional) : Push the image to Docker Hub – docker login, docker image push
Create an account in Docker Hub . Create a private repo. Login to docker hub in your cli command prompt.
Push image to the repo  docker push <<uid>>/<<repo name>>:tagname
  
Step 7 : Docker Compose – docker-compose up, docker-compose down
Create a docker compose file having multiple containers, make use of storage volumes, and run the docker compose 
file. Test the application. Get inside the containers. Then pull down the containers using docker compose

Step 7 : Optional
>Pull an image from a public/ your private repo
>Remove an image pulled from docker registry and try to run it
>Remove a container
>See the top processes running within a container

 
# KUBERNETES--K8
                    
Step 1 : Docker Images to be used
Take the cardsapp docker image created in the docker assignment and the mongo db docker image

Step 2 : Start a Kubernetes cluster
Use minikube or any Kubernetes service on public cloud

Step 3 : Create a namespace
Create a namespace and make sure the objects created hereafter are in that namespace

Step 4 : Create Kubernetes objects (Use yaml files and kubectl commands to create and maintain resources)
Create two replicas of MongoDB pods using Deployment object and expose the PODs via a Cluster IP service. Make sure the Data is persistent outside the life of container suing persistent volume and persistent volume claims.
Create Configmaps/Secrets for the application configuration files. Run two replicas of Application(cardsapp) Pods. Make sure the Pods are highly available and resilient, create using Deployment. Make sure the application pods take the application configuration from Config Maps. Connect the app pods to mongo db via the clusterIP service IP/Port. Expose the application pods via NodePort service, so that they are available externally.

Step 5 : Scale the number of Application Pods (Edit Deployments or use scale command and rollout commands)
Scale up the number of application pods from 2 to 4
Scale down the number of pods from 4 to 3
Check the deployment rollout history
Undo the last deployment rollout and see that the number of pods are back to 4
Manually remove a pod and see of the number of pods are maintained as 4



# Assessment MiniShift - OpenShift
                    
Step 1: install minishift Follow the steps given in the presentation (Slide 9-10) given during Session 3 (you can find the same as pinned items in fss-cloud-garage slack channel)

Step 2: Code You may develop a Springboot microservice in your favourite IDE or download from an existing repo (given in reference) . In case you intend to write the code yourself, then check-in the code into a git repo. 

Step 3: Add data repository to the code Add data repository to persist the contracts exposed into the mongo db, along with other necessary configurations 

Step 4: Deploy Deploy Database: Inside the same project, spawn up a MongoDB and verify the persistent volume created 

Deploy Code: Use the s2i feature to deploy your microservice onto minishift cluster (follow the steps in Slide 11 of the ppt mentioned in Step 1) which should have following features: 
• Replica – 2 
• Define Resource limits which each pod should use

Step 5: Add persistent volume Use the web console or command line to create a new persistent volume and add it as storage to the deployment created in Step 4 of the mongodb.

