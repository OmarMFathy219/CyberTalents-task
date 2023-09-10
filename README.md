# CyberTalents-task

This project is a sample template for deploying a Flask web application on Amazon EKS (Elastic Kubernetes Service) using Terraform for infrastructure provisioning. 

It also includes IAM-related files for configuring permissions. Below is an overview of the project structure and instructions on how to use it.

## Project Structure

- **flask-app**: This directory contains a Flask web application.
  - `app`: Python code for the Flask application.
  - `templates`: HTML templates for the web pages.
  - `Dockerfile`: Dockerfile for containerizing the Flask app.

- **terraform**: This directory contains Terraform configuration for provisioning an Amazon EKS cluster.
  - `eks.tf`: Terraform configuration for creating an EKS cluster.
  - `provider.tf`: Terraform provider configuration.
  - `variables.tf`: Terraform variables definition.
  - `vpc.tf`: Terraform configuration for the VPC.

- **Kubernetes Manifests**: These YAML files define Kubernetes resources.
  - `flask-app.yaml`: Kubernetes manifest for deploying the first release for the flask app.
  - `flask-app2.yaml`: Another manifest for a  second release for the flask app.
  - `my-service-account.yaml`: Kubernetes ServiceAccount definition.
  - `role-binding.yaml`: RoleBinding definition.
  - `my-policy.json`: JSON policy document.
  - `trust-relationship.json`: JSON trust relationship document.

## Usage

1. **Flask Application**:
   - You can build and run the Flask application using the provided Dockerfile.
   - Customize the Flask app as needed, and update the templates in the `templates` directory.

2. **Terraform (Amazon EKS)**:
   - Configure your AWS credentials using the AWS CLI.
   - Update the Terraform variables in `terraform/variables.tf` as needed.
   - Run `terraform init`, `terraform plan`, and `terraform apply` to provision the EKS cluster.

3. **Kubernetes Manifests**:
   - Apply the Kubernetes manifests using `kubectl apply -f <file.yaml>`.
   - Modify the manifests to suit your application's requirements.

4. **IAM Configuration**:
   - Use `my-policy.json` and `trust-relationship.json` to configure IAM roles and policies for your AWS resources.

## IAM Permissions

Ensure that the IAM roles and permissions are configured correctly for your AWS resources. Use `my-policy.json` as a reference for defining the necessary permissions.

## Resources I Used

- [IAM roles for service accounts](https://docs.aws.amazon.com/eks/latest/userguide/iam-roles-for-service-accounts.html/): A guide to:
-- Creating an IAM OIDC provider for your cluster.
-- Configuring a Kubernetes service account to assume an IAM role.
-- Configuring Pods to use a Kubernetes service account.

- [Kubernetes Using RBAC Authorization](https://kubernetes.io/docs/reference/access-authn-authz/rbac/)
- [Deploy a sample application](https://aws.amazon.com/eks/): AWS documentation to deploy a sample application to the cluster.
- [Node taints on managed node groups](https://docs.aws.amazon.com/eks/latest/userguide/node-taints-managed-node-groups.html)
