<h2>Complete Airbyte API Workflow: A Step-by-Step Guide</h2>

<h3>Table of Contents</h3>
<ul>
    <li><a href="#introduction">Introduction</a></li>
    <li><a href="#prerequisites">Prerequisites</a></li>
    <li><a href="#step-by-step-instructions">Step-by-Step Instructions</a>
        <ul>
            <li><a href="#creating-an-application">Creating an Application</a></li>
            <li><a href="#obtain-an-access-token">Obtain an Access Token</a></li>
            <li><a href="#create-a-source">Create a Source</a></li>
            <li><a href="#create-a-destination">Create a Destination</a></li>
            <li><a href="#create-a-connection">Create a Connection</a></li>
        </ul>
    </li>
    <li><a href="#conclusion">Conclusion</a></li>
</ul>

<h3 id="introduction">Introduction</h3>
<p>In this guide, we’ll walk through a comprehensive step-by-step process to complete the Airbyte API workflow. The Airbyte API empowers users to manage and automate data transfers between a wide array of sources and destinations. By offering a robust set of endpoints, it simplifies the orchestration of complex data workflows, making data integration seamless and efficient.</p>

<h3 id="prerequisites">Prerequisites</h3>
<p>Before you begin, ensure you have the following:</p>
<ul>
    <li>An AWS account</li>
    <li>AWS CLI installed and configured</li>
    <li>Basic knowledge of AWS EC2 and Docker</li>
    <li>Docker installed on your EC2 Instance</li>
    <li>Airbyte installed on your EC2 Instance</li>
</ul>

<h4>Preparation Steps:</h4>
<ol>
    <li><strong>Launch the Airbyte Container:</strong> Start the Airbyte container on your EC2 instance.
    <img src="#" alt="Image of launching Airbyte container" /></li>
    <li><strong>Access the Airbyte UI:</strong> Navigate to the Airbyte UI by entering <code>http://&lt;instance_IP_address&gt;:&lt;port_number&gt;</code> in your web browser.
    <img src="#" alt="Image of Airbyte UI" /></li>
    <li><strong>Retrieve the Workspace ID:</strong> Obtain the Workspace ID from the URL in your developer portal. The Workspace ID is found between "workspace/" and the following "/".
    <img src="#" alt="Image showing how to find Workspace ID" /></li>
</ol>

<h3 id="step-by-step-instructions">Step-by-Step Instructions</h3>

<h4 id="creating-an-application">1. Creating an Application</h4>
<ol>
    <li><strong>Access the Airbyte UI:</strong> Log into the Airbyte UI.</li>
    <li><strong>Navigate to Settings:</strong> Go to the 'Settings' section and select 'Create Application.'
    <img src="#" alt="Image of Create Application Screen" /></li>
    <li><strong>Create the Application:</strong> Enter a name for your application and complete the creation process.</li>
    <li><strong>Secure Your Credentials:</strong> Copy and securely store the <code>Client ID</code> and <code>Client Secret</code>, as these are essential for generating tokens.</li>
</ol>

<h4 id="obtain-an-access-token">2. Obtain an Access Token</h4>
<ol>
    <li><strong>Visit Airbyte Documentation:</strong> Refer to the <a href="https://airbyte.com/reference/getting-started" target="_blank">Airbyte Reference - Getting Started</a>.</li>
    <li><strong>Generate Token:</strong>
        <ul>
            <li>Navigate to the "Application" tab and click on "Get an Access Token."</li>
            <li>In the Body Params section, enter the <code>client_id</code> and <code>client_secret</code> obtained earlier, and set the <code>grant_type</code> to <code>client_credentials</code>.</li>
            <li>Choose your preferred programming language (e.g., Python) to generate the code.
            <img src="#" alt="Image of API Documentation for Access Token" /></li>
        </ul>
    </li>
    <li><strong>Run the Code:</strong>
        <ul>
            <li>Copy the generated code into a new file in Visual Studio Code (VSCode).</li>
            <li>Run the code using the command: <code>docker-compose up</code>.
            <img src="#" alt="Image of Code Running in VSCode" /></li>
        </ul>
        <pre><code>import requests

client_id = 'your_client_id'
client_secret = 'your_client_secret'

response = requests.post(
    'https://api.airbyte.com/oauth/token',
    data={
        'grant_type': 'client_credentials',
        'client_id': client_id,
        'client_secret': client_secret,
    }
)

token = response.json()['access_token']
print(token)</code></pre>
    </li>
    <li><strong>Store the Token:</strong> The output will include an access token in JSON format. Save this token, noting that it is valid for only 3 minutes.
    <img src="#" alt="Image of Token Output" /></li>
</ol>

<h4 id="create-a-source">3. Create a Source</h4>
<ol>
    <li><strong>Access Source Creation:</strong>
        <ul>
            <li>Navigate to the "Source" tab within the Airbyte UI.</li>
            <li>Click on "Create a Source."
            <img src="#" alt="Image of Source Creation Screen" /></li>
        </ul>
    </li>
    <li><strong>Configure the Source:</strong>
        <ul>
            <li>Enter a name for your source and paste your <code>workspace_id</code>.</li>
            <li>Select the source configuration and provide credentials (e.g., for Google Sheets).</li>
        </ul>
    </li>
    <li><strong>Authorize and Run:</strong>
        <ul>
            <li>Paste the access token in the authorization tab.</li>
            <li>Copy the generated Python code, paste it into a terminal or text editor, and execute it.</li>
            <li><pre><code>import requests

token = 'your_access_token'
workspace_id = 'your_workspace_id'

response = requests.post(
    'https://api.airbyte.com/sources/create',
    headers={'Authorization': f'Bearer {token}'},
    json={
        'workspaceId': workspace_id,
        'sourceDefinitionId': 'your_source_definition_id',
        'connectionConfiguration': {
            'credentials': 'your_credentials'
        },
        'name': 'your_source_name'
    }
)

source_id = response.json()['sourceId']
print(source_id)</code></pre></li>
        </ul>
    </li>
    <li><strong>Save the Source ID:</strong> The output will include a <code>sourceId</code>. Copy and securely store this ID for future use.
    <img src="#" alt="Image of Code Running and Output" /></li>
</ol>

<h4 id="create-a-destination">4. Create a Destination</h4>
<ol>
    <li><strong>Access Destination Creation:</strong>
        <ul>
            <li>Navigate to the "Destination" tab in the Airbyte UI.</li>
            <li>Click on "Create a Destination."
            <img src="#" alt="Image of Destination Creation Screen" /></li>
        </ul>
    </li>
    <li><strong>Configure the Destination:</strong>
        <ul>
            <li>Enter a name for your destination and paste your <code>workspace_id</code>.</li>
            <li>Select your destination configuration and provide the necessary credentials (e.g., PostgreSQL).</li>
        </ul>
    </li>
    <li><strong>Authorize and Run:</strong>
        <ul>
            <li>Paste the access token in the authorization tab.</li>
            <li>Copy the generated Python code, paste it into your text editor, and execute it.</li>
            <li><pre><code>import requests

token = 'your_access_token'
workspace_id = 'your_workspace_id'

response = requests.post(
    'https://api.airbyte.com/destinations/create',
    headers={'Authorization': f'Bearer {token}'},
    json={
        'workspaceId': workspace_id,
        'destinationDefinitionId': 'your_destination_definition_id',
        'connectionConfiguration': {
            'credentials': 'your_credentials'
        },
        'name': 'your_destination_name'
    }
)

destination_id = response.json()['destinationId']
print(destination_id)</code></pre></li>
        </ul>
    </li>
    <li><strong>Save the Destination ID:</strong> The output will include a <code>destinationId</code>. Copy and securely store this ID.
    <img src="#" alt="Image of Code Running and Output" /></li>
</ol>

<h4 id="create-a-connection">5. Create a Connection</h4>
<ol>
    <li><strong>Access Connection Creation:</strong>
        <ul>
            <li>Navigate to the "Connection" tab and click on "Create Connection."
            <img src="#" alt="Image of Connection Creation Screen" /></li>
        </ul>
    </li>
    <li><strong>Configure the Connection:</strong>
        <ul>
            <li>Provide a name for the connection, along with the <code>sourceId</code> and <code>destinationId</code> obtained in previous steps.</li>
        </ul>
    </li>
    <li><strong>Generate and Run Code:</strong>
        <ul>
            <li>Follow the process outlined previously to generate the code.</li>
            <li>Execute the code to establish a connection between your source and destination.</li>
            <li><pre><code>import requests

token = 'your_access_token'
source_id = 'your_source_id'
destination_id = 'your_destination_id'

response = requests.post(
    'https://api.airbyte.com/connections/create',
    headers={'Authorization': f'Bearer {token}'},
    json={
        'sourceId': source_id,
        'destinationId': destination_id,
        'name': 'your_connection_name',
        'status': 'active'
    }
)

connection_id = response.json()['connectionId']
print(connection_id)</code></pre></li>
        </ul>
    </li>
</ol>

<h3 id="conclusion">Conclusion</h3>
<p>Congratulations! You’ve successfully deployed the Airbyte API on an EC2 instance using Docker. With the setup complete, you can now use the Airbyte dashboard to manage your data integrations effortlessly. For more advanced configurations and integrations, refer to the <a href="https://airbyte.com/docs" target="_blank">Airbyte documentation</a>.</p>
