# Golfeado

A collection of argocd CRDs resources grouped in charts.

Every chart represents a common use case or scenarios for argocd config.

## Estructure

You will find chart folders each one with different combination of configuration for the argocd. Every subfolder will have everything needed to apply the argocd and particular documentation.

Feel free to explore the different combinations and experiment with deploying them to start ArgoCD.

## Helmfile

Even though we can use helm commands to deploy a chart, this repo is using helmfile for learning purposes, feel free to use the same or other.

## Getting Started

To get started with this repository, follow these steps:

1. Clone the repository to your local machine:

    ```bash
    git clone https://github.com/ctablero/argocd.git
    ```

2. Change into any `custom-config` directory:

    ```bash
    cd custom-config
    ```

3. Install ArgoCD on your Kubernetes cluster. You can find installation instructions in the official ArgoCD documentation.

4. Deploy customized argocd resources using kubectl.

    ```bash
    cd custom-config
    kubectl apply -f .
    ```

5. Monitor the deployment status using the ArgoCD UI or CLI.

Happy practicing!