# Golfeado

A collection of Kubernetes manifests to bootstrap environment-ready ArgoCD resources using the declarative setup and the app-of-apps pattern.

## The problem

By design the ArgCD installation provides defaults minimum configurations to start from scratch. On the other hand performing configurations for real environments using commands and the ArgoCD UI can become high time consuming tasks.

## The solution

Use the declarative setup feature of ArgoCD to prepare a collection of resources configured in the context of real environments covering situations like:

1. K8s running in multi-cluster setup
2. Private repositories
3. Several apps
4. RBAC for teams  

## Setup instructions

1. Install ArgoCD on your Kubernetes cluster. You can find installation instructions in the official ArgoCD documentation
2. Clone this repository and checkout the convenient branch or tag
3. Modify files in the environments folder(overlays) with configurations specific to your organization or project, for example urls or names

For example, you can change the environments/staging/child-apps-source.yaml patch file to configure the source of your child apps in the staging environment of your project:

```yaml
spec:
    source:
        path: <add-here-the-target-folder-name>
        repoURL: <add-here-the-url-to-your-repo>
        targetRevision: <add-here-the-target-revision>
```

4. Execute the next command to create ArgoCD resources according the target environment:

```bash
kubectl apply -k environments/<ENVIRONMENT>/
```

5. Monitor the deployment status using the ArgoCD UI or CLI.

## Structure

You will have:

1. A base folder with all ArgoCD resources organized by type
2. An environments folder where you can overlay/patch from base using kustomize

Feel free to explore the different combinations and experiment with deploying them.

## Safe upload of Secrets to Repository

Secrets definitions in this repo are using https://github.com/bitnami-labs/sealed-secrets to safely upload secrets resource code to the repo. Follow that guide to Prepare the Cluster to manage SealedSecrets.

Notice that you will not be able to apply sealed resources in this repo as it was prepared using a specific sealed secret controller during development. Instead you have to prepare your own sealedSecrets. To find out more please check the sealed secrets documentation.

## Tools

- Customize Kubernetes objects: https://kustomize.io/
- ArgoCD: https://argo-cd.readthedocs.io/en/stable/