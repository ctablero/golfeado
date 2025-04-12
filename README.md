# Golfeado

An approach to bootstrap an ArgoCD cluster using gitops approach, the app-of-apps pattern and Kustomize tool.

## Estructure

You will have:

1. A base folder with all CRDs organized by type
2. An environments folder where you from base and overlay

Feel free to explore the different combinations and experiment with deploying them to start ArgoCD.

## Getting Started

To get started with this repository, follow these steps:

1. Install ArgoCD on your Kubernetes cluster. You can find installation instructions in the official ArgoCD documentation.

2. Clone the repository to your local machine:

    ```bash
    git clone https://github.com/ctablero/golfeado.git
    ```

3. Execute the bootstrap according the environment:

    ```bash
    k apply -k environments/<ENVIRONMENT>/
    ```

5. Monitor the deployment status using the ArgoCD UI or CLI.

Happy practicing!