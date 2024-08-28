<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Plural Workflow</title>
</head>
<body>

    <h1>PLURAL WORKFLOW</h1>

    <h2>What is Plural?</h2>
    <p>
        Plural is a self-hosted, open-source, unified application deployment platform that deploys your selected applications into a Kubernetes cluster in the cloud provider of your choice. Plural is designed for DevOps and platform engineering teams to automate and streamline the lifecycle management of Kubernetes fleets.
    </p>

    <h2>Why Plural?</h2>
    <p>
        In order to deploy infrastructure, we often need a combination of an open-source platform, a cloud provider, and a software platform. Plural provides all of these as a single deployment platform, making the process easy and time-saving. It acts as:
    </p>
    <ul>
        <li>An infrastructure provisioner, spinning up new clusters as needed</li>
        <li>A continuous deployment solution, allowing you to deploy services across environments</li>
        <li>A single pane of glass for complete visibility into what's deployed where</li>
        <li>An open-source marketplace to deploy 3rd party software into your clusters</li>
    </ul>

    <h2>How is Plural Better?</h2>
    <p>
        Plural simplifies the deployment of open-source third-party and proprietary first-party applications into clusters within your cloud environment. It offers:
    </p>
    <ul>
        <li>Open source, self-hosted solutions</li>
        <li>Bring your own cloud and clusters</li>
        <li>Automated testing</li>
        <li>Portability</li>
    </ul>
    <p>
        For open-source applications, Plural deploys a new cluster; for proprietary applications, you can use either a new or an existing cluster for deployments. Plural creates two types of clusters:
    </p>
    <ul>
        <li><strong>Management Cluster:</strong> Where the Plural control plane and Cluster API (CAPI) controllers reside</li>
        <li><strong>Workload Clusters:</strong> Where main production/staging services are hosted</li>
    </ul>
    <p>Plural will deploy open-source applications into a Management Cluster.</p>

    <h2>Architecture</h2>
    <ul>
        <li><strong>Plural Console:</strong> The operational hub for all applications managed by Plural.</li>
        <li><strong>Plural CLI:</strong> Used for interaction with the Plural API and Plural Console, effectively functioning as a higher-level build tool on top of supported DevOps packages.</li>
        <li><strong>Plural API:</strong> Stores packages needed for open-source application installation (Terraform, Helm) and ingests high-level dependency information.</li>
    </ul>

    <h2>Deployment Options</h2>
    <p>
        Plural provides two deployment options:
    </p>
    <ul>
        <li><strong>Plural CLI:</strong> A command-line tool for deploying applications</li>
        <li><strong>Plural Cloud Shell:</strong> A cloud-based environment that includes all the necessary dependencies and tools to run Plural</li>
    </ul>

    <h2>Plural Workflow Steps</h2>
    <p>
        A typical Plural workflow involves the following steps:
    </p>
    <ol>
        <li><strong>Selecting Applications:</strong> Choose from a marketplace of pre-configured applications or add your own. Plural offers a variety of applications, including databases, CI/CD tools, monitoring solutions, and more.</li>
        <li><strong>Configuration:</strong> Customize the application and infrastructure settings. Plural allows you to configure settings like DNS, storage, networking, and security according to your needs.</li>
        <li><strong>Provisioning Infrastructure:</strong> Plural automates the provisioning of the required infrastructure on your chosen cloud provider (e.g., AWS, GCP, Azure) using Infrastructure as Code (IaC) tools like Terraform.</li>
        <li><strong>Deployment:</strong> Plural deploys the applications onto your Kubernetes cluster, handling tasks like resource allocation, networking, and scaling.</li>
        <li><strong>Monitoring and Management:</strong> Plural provides integrated monitoring, logging, and alerting solutions to help you manage and maintain your applications.</li>
        <li><strong>Updates and Scaling:</strong> Easily update applications and scale resources as needed. Plural workflows ensure that updates and scaling operations are smooth and do not disrupt your services.</li>
        <li><strong>Backup and Recovery:</strong> Plural offers tools for backing up your applications and data, as well as disaster recovery options to ensure business continuity.</li>
    </ol>
    <p>
        This workflow is designed to streamline the process of deploying, managing, and scaling complex open-source applications on Kubernetes, making it accessible even to those who might not have deep Kubernetes expertise.
    </p>

    <h2>Getting Started with Plural</h2>
    <p>
        Follow these steps to get started with Plural in a beginner-friendly manner:
    </p>
    <ol>
        <li>Install the Plural CLI or access the Plural Cloud Shell.</li>
        <li>Browse the available open-source applications in the Plural Marketplace.</li>
        <li>Set up a Management Cluster using the Plural CLI or Cloud Shell.</li>
        <li>Deploy your desired application into the Kubernetes cluster.</li>
        <li>Manage and monitor your deployment using the Plural Console.</li>
    </ol>

</body>
</html>
