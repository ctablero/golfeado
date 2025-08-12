# Golfeado

An approach to bootstrap an ArgoCD cluster using gitops approach, the app-of-apps pattern and Kustomize tool.

## Estructure

You will have:

1. A base folder with all CRDs organized by type
2. An environments folder where you can overlay from base

Feel free to explore the different combinations and experiment with deploying them to start ArgoCD.

## Safe upload of Secrets to Repository

Secrets definitions in this repo are using https://github.com/bitnami-labs/sealed-secrets to safely upload secrets resource code to the repo. Follow that guide to Prepare the Cluster to manage SealedSecrets.

Notice that you will not be able to apply those sealed resources as it was prepared the version of the sealed secret controller I installed. Instead you have to create your own. More notes in the sealed secrets repo.

## Getting Started

To get started with this repository, follow these steps:

1. Install ArgoCD on your Kubernetes cluster. You can find installation instructions in the official ArgoCD documentation.

2. Clone the repository to your local machine:

    ```bash
    git clone https://github.com/ctablero/golfeado.git
    ```

3. Modify patch files according your necesities per environment.
   
   For example, edit the environments/staging/child-apps-source.yaml patch file to configure the source of your child apps:

    ```yaml
    spec:
        source:
            path: apps
            repoURL: https://github.com/ctablero/bienmesabe.git
            targetRevision: HEAD
    ```

4. Execute the bootstrap according the environment:

    ```bash
    k apply -k environments/<ENVIRONMENT>/
    ```

5. Monitor the deployment status using the ArgoCD UI or CLI.

Happy practicing!