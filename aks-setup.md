# aks-setup

# Deploy Kubernetes Service on Azure

1. Select Kubernetes Service from the list of available services

2. Click on Add -> Add Kubernetes Cluster

3. Enter required cluster configuration details & click on Review + Create. It will take around 2-3 minutes to deploy cluster based on the number of nodes

4. Once the cluster is up & running click on the connect button

5. Copy az commands to get logged into the AKS cluster

# Deploy App

Before deploying artisan runner app, we need to enable AKS cluster routing so that application is accessible using url instead of public ip
```bash
az aks enable-addons --resource-group RGForSAP --name KubeCluster --addons http_application_routing
```

Now get AKS cluster app routing zone name
```bash
az aks show --resource-group RGForSAP --name KubeCluster --query addonProfiles.httpApplicationRouting.config.HTTPApplicationRoutingZoneName -o table

```

Output Format: 70e74a97963e4f81a821.eastus.aksapp.io

Note:- Replace the above output with ${HOST_NAME} in app.yaml
