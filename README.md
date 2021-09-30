# helm-chart
Deploy a helloworld web-app using Helm Chart to minikube

## Start minikub
```
minikube start
```
Check minikube status with:
```
minikube status
```
You will receive as a result:

> minikube
> type: Control Plane
> host: Running
> kubelet: Running
> apiserver: Running
> kubeconfig: Configured


## Install the Helm Chart
To install the helm chart use this command:
```
helm install -f values.yaml nginx-app .
```
Result:
> NAME: nginx-app
LAST DEPLOYED: Wed Sep 29 23:02:36 2021
NAMESPACE: default
STATUS: deployed
> REVISION: 1
> NOTES:
> Get the application URL by running these commands:
  - ``` export NODE_PORT=$(kubectl get --namespace default -o jsonpath="{.spec.ports[0].nodePort}" services helloworld-chart) ```
  - ``` export NODE_IP=$(kubectl get nodes --namespace default -o jsonpath="{.items[0].status.addresses[0].address}") ```
>  - ``` echo http://$NODE_IP:$NODE_PORT ```

The aboce command deploys our application. Now we will export the NODE_IP and NODE_PORT, so we can use them to check our application.

``` echo http://$NODE_IP:$NODE_PORT ```
> http://192.168.49.2:30186
