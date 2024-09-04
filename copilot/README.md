## Step 1: Ask Copilot Chat to generate the workspace:

> @workspace /new inside copilot-jenkins-k8s repository in the copilot directory. Create a simple node js app. Dockerfile to run it. And k8s manifests to run it locally

- Click on Create Workspace.

![new](./images/new.png)

## Step 2: Ask Copilot Chat how to run this app locally:

> @workspace how to build this Docker Image? Give me instructions to build and test it locally in my machine

![run](./images/run.png)

#### Build the Docker Image:

    docker build -t my-node-app .

### Deploy to Kubernetes

#### Apply the Deployment and Service:

    kubectl apply -f k8s/deployment.yaml
    kubectl apply -f k8s/service.yaml

#### Access the Application:

    kubectl port-forward service/my-node-app 8080:80

## Step 3: Ask Copilot Chat how to update k8s manifest:

> @workspace update service.yaml, i need to be clusterip type. update deployment, to load image locally and not going to external repository, use policy type to never go to registry

![k8s](./images/k8s.png)