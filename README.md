# ingress-example

This ingress example is tested on Openshift & Plain Kubernetes platform

## How To Deploy App?

In app.yaml file,

1) Replace ${APPLICATION_NAME} with any app name eg. java-quarkus
2) Add your cluster hostname in place of ${HOST_NAME}
3) In this example, I am using Java Quarks docker image & the 8080 container port is exposed. Just replace the image with your image name & update the container port

```bash
# after doing the above changes run the below command to create an app
kubectl apply -f app.yaml
```
Checkout How To Deploy App On AKS Cluster: [CLICK HERE](https://github.com/pratik10596/ingress-example/blob/main/aks-setup.md#aks-setup)

