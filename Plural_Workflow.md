# PLURAL WORKFLOW

## What is Plural?
Plural is a self-hosted, open-source, unified application deployment platform that deploys your selected applications into a Kubernetes cluster in the cloud provider of your choice. Plural is designed for DevOps and platform engineering teams to automate and streamline the lifecycle management of Kubernetes fleets.

## Why Plural?
In order to deploy infrastructure, we often need a combination of an open-source platform, a cloud provider, and a software platform. Plural provides all of these as a single deployment platform, making the process easy and time-saving. It acts as:

- An infrastructure provisioner, spinning up new clusters as needed
- A continuous deployment solution, allowing you to deploy services across environments
- A single pane of glass for complete visibility into what's deployed where
- An open-source marketplace to deploy 3rd party software into your clusters

## How is Plural Better?
Plural simplifies the deployment of open-source third-party and proprietary first-party applications into clusters within your cloud environment. It offers:

- Open source, self-hosted solutions
- Bring your own cloud and clusters
- Automated testing
- Portability

For open-source applications, Plural deploys a new cluster; for proprietary applications, you can use either a new or an existing cluster for deployments. Plural creates two types of clusters:

- **Management Cluster:** Where the Plural control plane and Cluster API (CAPI) controllers reside
- **Workload Clusters:** Where main production/staging services are hosted

Plural will deploy open-source applications into a Management Cluster.

## Architecture
- **Plural Console:** The operational hub for all applications managed by Plural.
- **Plural CLI:** Used for interaction with the Plural API and Plural Console, effectively functioning as a higher-level build tool on top of supported DevOps packages.
- **Plural API:** Stores packages needed for open-source application installation (Terraform, Helm) and ingests high-level dependency information.

## Deployment Options
Plural provides two deployment options:

- **Plural CLI:** A command-line tool for deploying applications
- **Plural Cloud Shell:** A cloud-based environment that includes all the necessary dependencies and tools to run Plural

## Plural Workflow Steps
A typical Plural workflow involves the following steps:

1. **Selecting Applications:** Choose from a marketplace of pre-configured applications or add your own. Plural offers a variety of applications, including databases, CI/CD tools, monitoring solutions, and more.
2. **Configuration:** Customize the application and infrastructure settings. Plural allows you to configure settings like DNS, storage, networking, and security according to your needs.
3. **Provisioning Infrastructure:** Plural automates the provisioning of the required infrastructure on your chosen cloud provider (e.g., AWS, GCP, Azure) using Infrastructure as Code (IaC) tools like Terraform.
4. **Deployment:** Plural deploys the applications onto your Kubernetes cluster, handling tasks like resource allocation, networking, and scaling.
5. **Monitoring and Management:** Plural provides integrated monitoring, logging, and alerting solutions to help you manage and maintain your applications.
6. **Updates and Scaling:** Easily update applications and scale resources as needed. Plural workflows ensure that updates and scaling operations are smooth and do not disrupt your services.
7. **Backup and Recovery:** Plural offers tools for backing up your applications and data, as well as disaster recovery options to ensure business continuity.

This workflow is designed to streamline the process of deploying, managing, and scaling complex open-source applications on Kubernetes, making it accessible even to those who might not have deep Kubernetes expertise.

## Getting Started with Plural
Follow these steps to get started with Plural in a beginner-friendly manner:

1. Install the Plural CLI or access the Plural Cloud Shell.
2. Browse the available open-source applications in the Plural Marketplace.
3. Set up a Management Cluster using the Plural CLI or Cloud Shell.
4. Deploy your desired application into the Kubernetes cluster.
5. Manage and monitor your deployment using the Plural Console.
