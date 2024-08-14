<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
    <h1>Complete Airbyte_API_Workflow Step-Step-Guide</h1>
    <h2>Table of Contents</h2>
    <nav id="toc">
        <ul>
            <li><a href="#introduction">Introduction</a></li>
            <li><a href="#prerequisites">Prerequisites</a></li>
            <li><a href="#step-by-step-instructions">Step-by-Step Instructions</a>
                <ul>
                    <li><a href="#Create-Application">1. Creating Application</a></li>
                    <li><a href="#Obtain-Access-token">2. Obtain an Access Token</a></li>
                    <li><a href="#Creating_Source">3. Create a Source</a></li>
                    <li><a href="#Creating_Destination">4. Create Destination</a></li>
                    <li><a href="#creating_connection">5. Create Connection</a></li>
                    <li><a href="Conclusion">6. Conclusion </a></li>
                </ul>
            </li>
            <li><a href="#conclusion">Conclusion</a></li>
        </ul>
    </nav>
    <h2 id="introduction">Introduction</h2>
    <p>This blog offers a comprehensive step-by-step guide to the complete Airbyte API workflow. The Airbyte API facilitates seamless data integration, enabling users to programmatically manage and automate the transfer of data between diverse sources and destinations. It delivers a robust set of endpoints for configuring, monitoring, and orchestrating data pipelines, simplifying the handling of complex data workflows.</p>
    <h2 id="prerequisites">Pre-requisites</h2>
    <p>Before you begin, ensure you have the following:</p>
    <ul>
        <li>An AWS account</li>
        <li>AWS CLI installed and configured</li>
        <li>Basic knowledge of AWS EC2 and Docker</li>
        <li>Docker installed on your EC2 Instance</li>
        <li>Airbyte installed in your EC2 Instance</li>
    </ul>
    <h3>Steps to Complete Before Creating the Application:</h3>
     <ol>
    <li><strong>Launch the Airbyte Container</strong>: Begin by starting the Airbyte container.</li>
    <li><strong>Access the Airbyte UI</strong>: Open the Airbyte UI web application by navigating to <code>http://&lt;instance_IP_address&gt;:&lt;port_number&gt;</code> in your web browser.</li>
    <li><strong>Retrieve the Workspace ID</strong>: Collect the Workspace ID, which can be found in the URL of your developer portal. It is the segment of the URL between <code>"workspace/"</code> and the following <code>"/"</code>.</li>
     </ol>


<h2 id="Create-Application">Create Application</h2>
<p>Open the airbyte UI :</p>
    <ul>
        <li>Open the settings option and click on create application.</li>
        <li>Enter a name for your new application and complete the creation process.</li>
        <li>Make sure to copy and securely store the Client ID and Client Secret, as these are essential for generating tokens.</li>
    </ul>
<h2 id="Obtain-Access-Token">Obtain an Access Token</h2>
<p>Follow the steps below to obtain an access token from the Airbyte reference documentation:</p>
<ul>
    <li>Visit the link: <a href="https://reference.airbyte.com/reference/getting-started" target="_blank">Airbyte Reference - Getting Started</a>.</li>
    <li>Navigate to the "Application" tab and click on "Get an Access Token."</li>
    <li>In the Body Params section, paste the <code>client_id</code> and <code>client_secret</code> you received after creating the application, and set the <code>grant_type</code> to <code>client_credentials</code>.</li>
    <li>Select your preferred programming language (e.g., Python), so you can save and clone the code from Git for future use.</li>
    <li>Copy the generated code, open a new file in Visual Studio Code (VSCode), paste the Python code, and run it using the command: <code>docker-compose up</code>.</li>
    <li>You will receive the access token as output in JSON format. Copy and save this token, as it is valid for only 3 minutes.</li>
</ul>

<h2 id="Creating_Source">Create a Source</h2>
<p>Follow these steps to create a source in Airbyte:</p>
<ul>
    <li>Navigate to the "Source" tab using the link provided in the previous section and click on "Create a Source."</li>
    <li>Enter a name for the source and paste your <code>workspace_id</code>.</li>
    <li>Select your source configuration and provide the necessary credentials to access your Google Sheets.</li>
    <li>Paste the token in the authorization tab and copy the generated Python code.</li>
    <li>Open a terminal or text editor (such as VI), paste the Python code, and execute it.</li>
    <li>The output will include a <code>sourceId</code>. Copy and store this <code>sourceId</code> for future reference.</li>
</ul>
<p>You can also create, update, or delete sources using the tabs provided in the portal.</p>
<h2 id="Creating_Destination">Create Destination</h2>
<p>Steps to create destination:</p>
    <ul>
        <li>Open destination tab using the above link provided in above paragraph. Click on create a destination</li>
        <li>Provide the name and paste your workspace_id.</li>
        <li>Select your destination configuration and provide the necessary credentials to access your destination for example postgres.</li>
        <li>Paste the token in the authorization tab and copy the python code.</li>
        <li>Open VI, paste the python code and then run the code.</li>
        <li>This will give you the destinationId output, copy and store the destinationId.</li>
    </ul>
<p>You can also create, update, delete the destination using the tabs given the portal</p>
<h2 id="creating_connection">Create Connection</h2>
<p>Steps to create Connection:</p>
    <ul>
        <li>Open connection tab and click on create connection tab</li>
        <li>Provide the Name, SourceId and DestinationId which you have copied in the above process</li>
        <li>This generates the code, and follow the similar process given above.</li>
        <li>Run the code, this process will connect your source and destination.</li>
    </ul>
<h2 id="Conclusion">Conclusion</h2>
<p>You've successfully deployed the Airbyte API on an EC2 instance using Docker. You can now use the Airbyte dashboard to manage your data integrations. For more advanced configurations and integrations, refer to the Airbyte documentation.</p>
</body>
</html>
