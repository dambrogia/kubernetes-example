# Kubernetes Example
This is a kubernetes proof of concept to show how a PHP Service and Database Service can work together.

This is expected to be run locally.

### Requirements
- [minikube](https://minikube.sigs.k8s.io/docs/start/)
    - This creates a docker container to manage your local cluster
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
    - This is the CLI API to manage your services within your cluster

### Getting Started
1. Install requirements
2. Clone this repository
3. Start minikube -- `minikube start`
4. Provision your cluster -- `kubectl apply -k .`
    - This needs to be run in the project root.
    - The `-k` flag denotes which directory to look for a `kustomization.yaml` file in.
5. Tunnel into your cluster -- `minikube tunnel`
6. Install WordPress:
    - Go to `localhost` in your browser. Complete the installation.
    - Database values are:
        - Database: `wordpress`
        - User: `username`
        - Password: `password`
        - Host: `mariadb-service`
            - This relates to the `.metadata.name` of the `services/mariadb/service.yaml` file.
        - Prefix: `wp_`
7. Open the kubernetes dashboard -- `minikube dashboard`
8. Follow the images below to deploy a new version of your web nodes (WordPress).
