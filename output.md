Email Q&A.

*Kubernetes Namespace
  Q. What is a namespace?
  A. Namespace provides a mechanism for isolating groups of resources within a single cluster. 
  
  Q. Why would you use a namespace?
  A. A Kubernetes namespace helps separate a cluster into logical units

*Kubernetes Pods
  Q. What are pods?
  A. Pods are the smallest, most basic deployable objects in Kubernetes. 
     A Pod represents a single instance of a running process in your cluster.
     Kubernetes doesn’t run containers directly, instead it wraps one or more 
     containers into a higher-level structure called a pod.
     Any containers in the same pod will share the same resources and local network. 
     Containers can easily communicate with other containers in the same pod as 
     though they were on the same machine while maintaining a degree of isolation from others.
 
* Kubernetes Deployments
  Q.What are deployments?
  A. A Kubernetes Deployment is used to tell Kubernetes how to create or modify instances 
     of the pods that hold a containerized application.
  
  Q. Why would you use a deployment?
  A. Using a deployment, you don’t have to deal with pods manually.
     You can just declare the desired state of the system, and it will be managed 
     for you automatically.

*Kubernetes Commands
  Q. How do you get the logs of a pod?
  A. kubectl logs pod-name-here 
     kubectl logs pod-name-here --all-containers to get logs for all containers in the pod.
     kubectl logs pod-name-here container-name to get logs for a spexific container within the pod.
  
  Q. How do you get a list of the pods for a specific namespace?
  A. kubectl --namespace your-space-name  get pods
  
  Q. How do you get a list of events for a pod?
  A. kubectl describe pod pod-name-here

Service installation:
1. I first crerated a test kubernetes cluster with 3 nodes on Linode.
2. Installed kubectl on my mac and configured it to work with the cluster that I have created earlier on Linode.
3. Installed git on my mac
4. Pulled the robot-shop from forked repo that i've created earlier
5. Installed helm on my mac
6. Configured helm following instruction from here https://artifacthub.io/packages/helm/cloud-native-toolkit/robot-shop
7. Created new namespace on my cluster by using kubectl create ns robot-shop
8. Installed robot shop to my cluster with this command$ helm install robot-shop --namespace robot-shop .
9. Tested the shop on the following URL http://172.104.255.157:8080/
10. Screenshot file RoboShopAfterinstallationScreenshot.png is included in the repo

