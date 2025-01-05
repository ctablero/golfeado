# Argocd projects to practise

This repository contains a collection of subprojects that you can use to practice working with ArgoCD.

## Subproject Apps

The `apps` subproject is designed to showcase various applications that can be deployed and managed using ArgoCD. Each subdirectory within the `apps` directory represents a different application, and contains the necessary configuration files and deployment manifests.

Feel free to explore the different applications and experiment with deploying them using ArgoCD.

## Getting Started

To get started with this repository, follow these steps:

1. Clone the repository to your local machine:

    ```bash
    git clone https://github.com/your-username/argocd-projects.git
    ```

2. Change into the `argocd-projects` directory:

    ```bash
    cd argocd-projects
    ```

3. Install ArgoCD on your Kubernetes cluster. You can find installation instructions in the official ArgoCD documentation.

4. Deploy an application using ArgoCD. For example, to deploy the `my-app` application, run the following command:

    ```bash
    argocd app create my-app --repo https://github.com/your-username/argocd-projects.git --path apps/my-app --dest-server https://kubernetes.default.svc --dest-namespace default
    ```

    Replace `your-username` with your GitHub username, and adjust the application name, repository URL, and destination server/namespace as needed.

5. Monitor the deployment status using the ArgoCD UI or CLI.

Happy practicing!