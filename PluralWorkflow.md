<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    
</head>
<body>

<!-- Heading -->
<h1>Plural Workflow</h1>

<!-- Introduction -->
<p>Plural is a self-hosted, open-source, unified application deployment platform that deploys your selected applications into a Kubernetes cluster in the cloud provider of your choice.</p>
<p>In order to deploy infrastructure, all you need is an open-source platform, a cloud, or a software platform. Plural provides all of these as a single deployment platform, making it easy and time-saving for you.</p>

<!-- Subheading -->
<h2>What is Plural?</h2>

<!-- Paragraph -->
<p>Plural is designed for DevOps and platform engineering teams to automate and streamline the lifecycle management of Kubernetes fleets. It acts as:</p>
<ul>
    <li>An infrastructure provisioner, spinning up new clusters as needed.</li>
    <li>A continuous deployment solution, allowing you to deploy your services across environments.</li>
    <li>A single pane of glass for complete visibility into what's deployed where.</li>
    <li>An open-source marketplace to deploy third-party software into your clusters.</li>
</ul>
<p>Plural uses Terraform and Cluster API to create and manage clusters and employs Helm charts to deploy and update applications.</p>

<!-- Subheading -->
<h2>Architecture</h2>

<!-- Subheading -->
<h3>Plural Console</h3>
<p>The Plural Console is the operational hub for all applications managed by Plural.</p>

<!-- Subheading -->
<h3>Plural CLI</h3>
<p>The Plural CLI can be used for interaction with the Plural API and Console. It acts as a higher-level build tool on top of DevOps packages.</p>

<!-- Subheading -->
<h3>Plural API</h3>
<p>The Plural API stores the packages needed for open-source application installation and handles high-level dependency information about them.</p>

<!-- Subheading -->
<h2>Advantages of Plural</h2>

<!-- Paragraph -->
<ul>
    <li>Open-source and self-hosted.</li>
    <li>Bring your own cloud and clusters.</li>
    <li>Automated testing and portable.</li>
    <li>Deploys both open-source and proprietary applications into clusters.</li>
</ul>
<p>Plural creates two types of clusters:</p>
<ul>
    <li><strong>Management Cluster:</strong> Hosts the Plural control plane and CAPI controllers.</li>
    <li><strong>Workload Clusters:</strong> Hosts main production/staging services. Plural deploys open-source applications into a Management Cluster.</li>
</ul>

<!-- Subheading -->
<h2>Plural Workflow</h2>

<!-- Steps List -->
<ol>
    <li>
        <h3>Selecting Applications</h3>
        <p>Choose from a marketplace of pre-configured applications or add your own. Plural offers a variety of applications, including databases, CI/CD tools, monitoring solutions, and more.</p>
    </li>
    <li>
        <h3>Configuration</h3>
        <p>Customize the application and infrastructure settings. Plural allows you to configure settings like DNS, storage, networking, and security according to your needs.</p>
    </li>
    <li>
        <h3>Provisioning Infrastructure</h3>
        <p>Plural automates the provisioning of the required infrastructure on your chosen cloud provider (e.g., AWS, GCP, Azure) using Infrastructure as Code (IaC) tools like Terraform.</p>
    </li>
    <li>
        <h3>Deployment</h3>
        <p>Plural deploys the applications onto your Kubernetes cluster, handling tasks like resource allocation, networking, and scaling.</p>
    </li>
    <li>
        <h3>Monitoring and Management</h3>
        <p>Plural provides integrated monitoring, logging, and alerting solutions to help you manage and maintain your applications.</p>
    </li>
    <li>
        <h3>Updates and Scaling</h3>
        <p>Easily update applications and scale resources as needed. Plural workflows ensure that updates and scaling operations are smooth and do not disrupt your services.</p>
    </li>
    <li>
        <h3>Backup and Recovery</h3>
        <p>Plural offers tools for backing up your applications and data, as well as disaster recovery options to ensure business continuity.</p>
    </li>
</ol>

<p>The workflow is designed to streamline the process of deploying, managing, and scaling complex open-source applications on Kubernetes, making it accessible even to those who might not have deep Kubernetes expertise.</p>

</body>
</html>
