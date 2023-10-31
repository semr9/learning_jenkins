# learning_jenkins
learning jenkins

Steps to deploy Jenkis in Kubernetes:
1) Create the namespace
    kubectl create namespace devops-tools
2) Create the serviceAccount.yaml 
    kubectl apply -f serviceAccount.yaml
3) Create the persistent volume manifest (Replace 'worker-node01' with any one of your cluster worker nodes hostname.)
    kubectl get nodes
    kubectl create -f volume.yaml
4) Deploy jenkis
    kubectl apply -f deployment.yaml
5) Check the deployment status
    kubectl get deployments -n devops-tools
6) Get the deployment details
    kubectl describe deployments --namespace=devops-tools


How to get the access Pasword for Jnekis??
1)  kubectl get pods --namespace=devops-tools
2)  kubectl logs <node-name> --namespace=devops-tools

or

1) kubectl exec -it <node-name> cat /var/jenkins_home/secrets/initialAdminPassword -n devops-tools


Improvements::
1) search the node name automatically
