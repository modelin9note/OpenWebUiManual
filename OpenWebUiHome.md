Open WebUI
Open WebUI is an extensible, feature-rich, and user-friendly self-hosted WebUI designed to operate entirely offline. 
It supports various LLM runners, including Ollama and OpenAI-compatible APIs.

Features ⭐
🖥️ Intuitive Interface: Our chat interface takes inspiration from ChatGPT, ensuring a user-friendly experience.
📱 Responsive Design: Enjoy a seamless experience on both desktop and mobile devices.
⚡ Swift Responsiveness: Enjoy fast and responsive performance.
🚀 Effortless Setup: Install seamlessly using Docker or Kubernetes (kubectl, kustomize or helm) for a hassle-free experience.
💻 Code Syntax Highlighting: Enjoy enhanced code readability with our syntax highlighting feature.
✒️🔢 Full Markdown and LaTeX Support: Elevate your LLM experience with comprehensive Markdown and LaTeX capabilities for enriched interaction.
📚 Local RAG Integration: Dive into the future of chat interactions with the groundbreaking Retrieval Augmented Generation (RAG) support. This feature seamlessly integrates document interactions into your chat experience. You can load documents directly into the chat or add files to your document library, effortlessly accessing them using # command in the prompt. In its alpha phase, occasional issues may arise as we actively refine and enhance this feature to ensure optimal performance and reliability.
🌐 Web Browsing Capability: Seamlessly integrate websites into your chat experience using the # command followed by the URL. This feature allows you to incorporate web content directly into your conversations, enhancing the richness and depth of your interactions.
📜 Prompt Preset Support: Instantly access preset prompts using the / command in the chat input. Load predefined conversation starters effortlessly and expedite your interactions. Effortlessly import prompts through Open WebUI Community integration.
👍👎 RLHF Annotation: Empower your messages by rating them with thumbs up and thumbs down, facilitating the creation of datasets for Reinforcement Learning from Human Feedback (RLHF). Utilize your messages to train or fine-tune models, all while ensuring the confidentiality of locally saved data.
🏷️ Conversation Tagging: Effortlessly categorize and locate specific chats for quick reference and streamlined data collection.
📥🗑️ Download/Delete Models: Easily download or remove models directly from the web UI.
⬆️ GGUF File Model Creation: Effortlessly create Ollama models by uploading GGUF files directly from the web UI. Streamlined process with options to upload from your machine or download GGUF files from Hugging Face.
🤖 Multiple Model Support: Seamlessly switch between different chat models for diverse interactions.
🔄 Multi-Modal Support: Seamlessly engage with models that support multimodal interactions, including images (e.g., LLava).
🧩 Modelfile Builder: Easily create Ollama modelfiles via the web UI. Create and add characters/agents, customize chat elements, and import modelfiles effortlessly through Open WebUI Community integration.
⚙️ Many Models Conversations: Effortlessly engage with various models simultaneously, harnessing their unique strengths for optimal responses. Enhance your experience by leveraging a diverse set of models in parallel.
💬 Collaborative Chat: Harness the collective intelligence of multiple models by seamlessly orchestrating group conversations. Use the @ command to specify the model, enabling dynamic and diverse dialogues within your chat interface. Immerse yourself in the collective intelligence woven into your chat environment.
🔄 Regeneration History Access: Easily revisit and explore your entire regeneration history.
📜 Chat History: Effortlessly access and manage your conversation history.
📤📥 Import/Export Chat History: Seamlessly move your chat data in and out of the platform.
🗣️ Voice Input Support: Engage with your model through voice interactions; enjoy the convenience of talking to your model directly. Additionally, explore the option for sending voice input automatically after 3 seconds of silence for a streamlined experience.
⚙️ Fine-Tuned Control with Advanced Parameters: Gain a deeper level of control by adjusting parameters such as temperature and defining your system prompts to tailor the conversation to your specific preferences and needs.
🎨🤖 Image Generation Integration: Seamlessly incorporate image generation capabilities using AUTOMATIC1111 API (local) and DALL-E, enriching your chat experience with dynamic visual content.
🤝 OpenAI API Integration: Effortlessly integrate OpenAI-compatible API for versatile conversations alongside Ollama models. Customize the API Base URL to link with LMStudio, Mistral, OpenRouter, and more.
✨ Multiple OpenAI-Compatible API Support: Seamlessly integrate and customize various OpenAI-compatible APIs, enhancing the versatility of your chat interactions.
🔗 External Ollama Server Connection: Seamlessly link to an external Ollama server hosted on a different address by configuring the environment variable.
🔀 Multiple Ollama Instance Load Balancing: Effortlessly distribute chat requests across multiple Ollama instances for enhanced performance and reliability.
👥 Multi-User Management: Easily oversee and administer users via our intuitive admin panel, streamlining user management processes.
🔐 Role-Based Access Control (RBAC): Ensure secure access with restricted permissions; only authorized individuals can access your Ollama, and exclusive model creation/pulling rights are reserved for administrators.
🔒 Backend Reverse Proxy Support: Bolster security through direct communication between Open WebUI backend and Ollama. This key feature eliminates the need to expose Ollama over LAN. Requests made to the '/ollama/api' route from the web UI are seamlessly redirected to Ollama from the backend, enhancing overall system security.
🌟 Continuous Updates: We are committed to improving Open WebUI with regular updates and new features.



🔗 Also Check Out Open WebUI Community!
Don't forget to explore our sibling project, Open WebUI Community, where you can discover, download, and explore customized Modelfiles. 
Open WebUI Community offers a wide range of exciting possibilities for enhancing your chat interactions with Ollama! 🚀


Quick Start with Docker 🐳

INFO
When using Docker to install Open WebUI, make sure to include the -v open-webui:/app/backend/data in your Docker command. This step is crucial as it ensures your database is properly mounted and prevents any loss of data.

Please note that the following instructions assume that the latest version of Ollama is already installed on your machine. If not, please refer to our full getting started documentation for comprehensive installation steps.

If Ollama is on your computer, use this command:

docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main


If Ollama is on a Different Server, use this command:

To connect to Ollama on another server, change the OLLAMA_BASE_URL to the server's URL:

docker run -d -p 3000:8080 -e OLLAMA_BASE_URL=https://example.com -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main


After installation, you can access Open WebUI at http://localhost:3000. Enjoy! 😄

Open WebUI: Server Connection Error
If you're experiencing connection issues, it’s often due to the WebUI docker container not being able to reach the Ollama server at 127.0.0.1:11434 (host.docker.internal:11434) inside the container . Use the --network=host flag in your docker command to resolve this. Note that the port changes from 3000 to 8080, resulting in the link: http://localhost:8080.

Example Docker Command:

docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main


Troubleshooting
If you're facing various issues like "Open WebUI: Server Connection Error", see TROUBLESHOOTING for information on how to troubleshoot and/or join our Open WebUI Discord community.

Continue with the full getting started guide.



---
---

🚀 Getting Started
How to Install 🚀
IMPORTANT NOTE ON USER ROLES AND PRIVACY
Admin Creation: The very first account to sign up on Open WebUI will be granted Administrator privileges. This account will have comprehensive control over the platform, including user management and system settings.

User Registrations: All subsequent users signing up will initially have their accounts set to Pending status by default. These accounts will require approval from the Administrator to gain access to the platform functionalities.

Privacy and Data Security: We prioritize your privacy and data security above all. Please be reassured that all data entered into Open WebUI is stored locally on your device. Our system is designed to be privacy-first, ensuring that no external requests are made, and your data does not leave your local environment. We are committed to maintaining the highest standards of data privacy and security, ensuring that your information remains confidential and under your control.

Before You Begin
One-line Command to Install Ollama and Open WebUI Together
Using Docker Compose
If you don't have Ollama yet, use Docker Compose for easy installation. Run this command:

docker compose up -d --build

For GPU Support: Use an additional Docker Compose file:

docker compose -f docker-compose.yaml -f docker-compose.gpu.yaml up -d --build

To Expose Ollama API: Use another Docker Compose file:

docker compose -f docker-compose.yaml -f docker-compose.api.yaml up -d --build

Using run-compose.sh Script (Linux or Docker-Enabled WSL2 on Windows)
Give execute permission to the script:

chmod +x run-compose.sh

For CPU-only container:

./run-compose.sh

For GPU support (read the note about GPU compatibility):

./run-compose.sh --enable-gpu

To build the latest local version, add --build:

./run-compose.sh --enable-gpu --build

Quick Start with Docker 🐳
INFO
When using Docker to install Open WebUI, make sure to include the -v open-webui:/app/backend/data in your Docker command. This step is crucial as it ensures your database is properly mounted and prevents any loss of data.

If Ollama is on your computer, use this command:

docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main


If Ollama is on a Different Server, use this command:

To connect to Ollama on another server, change the OLLAMA_BASE_URL to the server's URL:

docker run -d -p 3000:8080 -e OLLAMA_BASE_URL=https://example.com -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main


After installation, you can access Open WebUI at http://localhost:3000. Enjoy! 😄

Open WebUI: Server Connection Error
Encountering connection issues between the Open WebUI Docker container and the Ollama server? This problem often arises because distro-packaged versions of Docker—like those from the Ubuntu repository—do not support the host.docker.internal alias for reaching the host directly. Inside a container, referring to localhost or 127.0.0.1 typically points back to the container itself, not the host machine.

To address this, we recommend using the --network=host flag in your Docker command. This flag allows the container to use the host's networking stack, effectively making localhost or 127.0.0.1 in the container refer to the host machine. As a result, the WebUI can successfully connect to the Ollama server at 127.0.0.1:11434. Please note, with --network=host, the container's port configuration aligns directly with the host, changing the access link to http://localhost:8080.

Here's how you can modify your Docker command:

docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main


For more details on networking in Docker and addressing common connectivity issues, visit our FAQ page. This page provides additional context and solutions for frequently encountered problems, ensuring a smoother operation of Open WebUI in various environments.

Installing with Podman
Rootless (Podman) local-only Open WebUI with Systemd service and auto-update
Alternative Installation Methods
For other ways to install, like using Kustomize or Helm, check out INSTALLATION. Join our Open WebUI Discord community for more help and information.

Updating your Docker Installation
For detailed instructions on manually updating your local Docker installation of Open WebUI, including steps for those not using Watchtower and updates via Docker Compose, please refer to our dedicated guide: UPDATING.

For a quick update with Watchtower, use the command below. Remember to replace open-webui with your actual container name if it differs.

docker run --rm --volume /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower --run-once open-webui


In the last part of the command, replace open-webui with your container name if it is different.

INFO
After updating Open WebUI, you might need to refresh your browser cache to see the changes.

How to Install Without Docker
While we strongly recommend using our convenient Docker container installation for optimal support, we understand that some situations may require a non-Docker setup, especially for development purposes. Please note that non-Docker installations are not officially supported, and you might need to troubleshoot on your own.

Project Components
Open WebUI consists of two primary components: the frontend and the backend (which serves as a reverse proxy, handling static frontend files, and additional features). Both need to be running concurrently for the development environment.

INFO
The backend is required for proper functionality

Requirements 📦
🐰 Node.js >= 20.10 or Bun >= 1.0.21
🐍 Python >= 3.11
Build and Install 🛠️
Run the following commands to install:

git clone https://github.com/open-webui/open-webui.git
cd open-webui/

# Copying required .env file
cp -RPp .env.example .env

# Building Frontend Using Node
npm i
npm run build

# Serving Frontend with the Backend
cd ./backend
pip install -r requirements.txt -U
bash start.sh

You should have Open WebUI up and running at http://localhost:8080/. Enjoy! 😄



---
---


Alternative Installation
Installing Both Ollama and Open WebUI Using Kustomize
For cpu-only pod

kubectl apply -f ./kubernetes/manifest/base

For gpu-enabled pod

kubectl apply -k ./kubernetes/manifest

Installing Both Ollama and Open WebUI Using Helm
Package Helm file first

helm package ./kubernetes/helm/

For cpu-only pod

helm install open-webui ./open-webui-*.tgz

For gpu-enabled pod

helm install open-webui ./open-webui-*.tgz --set ollama.resources.limits.nvidia.com/gpu="1"

Check the kubernetes/helm/values.yaml file to know which parameters are available for customization


---
---


Understanding the Open WebUI Architecture
The Open WebUI system is designed to streamline interactions between the client (your browser) and the Ollama API. At the heart of this design is a backend reverse proxy, enhancing security and resolving CORS issues.

How it Works: The Open WebUI is designed to interact with the Ollama API through a specific route. When a request is made from the WebUI to Ollama, it is not directly sent to the Ollama API. Initially, the request is sent to the Open WebUI backend via /ollama route. From there, the backend is responsible for forwarding the request to the Ollama API. This forwarding is accomplished by using the route specified in the OLLAMA_BASE_URL environment variable. Therefore, a request made to /ollama in the WebUI is effectively the same as making a request to OLLAMA_BASE_URL in the backend. For instance, a request to /ollama/api/tags in the WebUI is equivalent to OLLAMA_BASE_URL/api/tags in the backend.

Security Benefits: This design prevents direct exposure of the Ollama API to the frontend, safeguarding against potential CORS (Cross-Origin Resource Sharing) issues and unauthorized access. Requiring authentication to access the Ollama API further enhances this security layer.

Open WebUI: Server Connection Error
If you're experiencing connection issues, it’s often due to the WebUI docker container not being able to reach the Ollama server at 127.0.0.1:11434 (host.docker.internal:11434) inside the container . Use the --network=host flag in your docker command to resolve this. Note that the port changes from 3000 to 8080, resulting in the link: http://localhost:8080.

Example Docker Command:

docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main


General Connection Errors
Ensure Ollama Version is Up-to-Date: Always start by checking that you have the latest version of Ollama. Visit Ollama's official site for the latest updates.

Troubleshooting Steps:

Verify Ollama URL Format:
When running the Web UI container, ensure the OLLAMA_BASE_URL is correctly set. (e.g., http://192.168.1.1:11434 for different host setups).
In the Open WebUI, navigate to "Settings" > "General".
Confirm that the Ollama Server URL is correctly set to [OLLAMA URL] (e.g., http://localhost:11434).
By following these enhanced troubleshooting steps, connection issues should be effectively resolved. For further assistance or queries, feel free to reach out to us on our community Discord.


---
---


Updating
Updating your Docker Installation
Keeping your Open WebUI Docker installation up-to-date ensures you have the latest features and security updates. You can update your installation manually or use Watchtower for automatic updates.

Manual Update
Follow these steps to manually update your Open WebUI:

Pull the Latest Docker Image:

docker pull ghcr.io/open-webui/open-webui:main

Stop and Remove the Existing Container:

This step ensures that you can create a new container from the updated image.
docker stop open-webui
docker rm open-webui

Create a New Container with the Updated Image:

Use the same docker run command you used initially to create the container, ensuring all your configurations remain the same.
docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main


This process updates your Open WebUI container to the latest version while preserving your data stored in Docker volumes.

Updating with Watchtower
For those who prefer automated updates, Watchtower can monitor your Open WebUI container and automatically update it to the latest version. You have two options with Watchtower: running it once for an immediate update, or deploying it persistently to automate future updates.

Running Watchtower Once
To update your container immediately without keeping Watchtower running continuously, use the following command. Replace open-webui with your container name if it differs.

docker run --rm --volume /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower --run-once open-webui


Deploying Watchtower Persistently
If you prefer Watchtower to continuously monitor and update your container whenever a new version is available, you can run Watchtower as a persistent service. This method ensures your Open WebUI always stays up to date without any manual intervention. Use the command below to deploy Watchtower in this manner:

docker run -d --name watchtower --volume /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower open-webui


Remember to replace open-webui with the name of your container if you have named it differently. This configuration allows you to benefit from the latest improvements and security patches with minimal downtime and manual effort.

Updating Docker Compose Installation
If you installed Open WebUI using Docker Compose, follow these steps to update:

Pull the Latest Images:

This command fetches the latest versions of the images specified in your docker-compose.yml files.
docker compose pull

Recreate the Containers with the Latest Images:

This command recreates the containers based on the newly pulled images, ensuring your installation is up-to-date. No build step is required for updates.
docker compose up -d

This method ensures your Docker Compose-based installation of Open WebUI (and any associated services, like Ollama) is updated efficiently and without the need for manual container management.

Updating Your Direct Install
For those who have installed Open WebUI directly without using Docker, updates are just as important to ensure access to the latest features and security patches. Remember, direct installations are not officially supported, and you might need to troubleshoot on your own. Here's how to update your installation:

Pull the Latest Changes
Navigate to your Open WebUI project directory and pull the latest changes from the repository:

cd path/to/open-webui/
git pull origin main

Replace path/to/open-webui/ with the actual path to your Open WebUI installation.

Update Dependencies
After pulling the latest changes, update your project dependencies. This step ensures that both frontend and backend dependencies are up to date.

For Node.js (Frontend):
npm install
npm run build

For Python (Backend):
cd backend
pip install -r requirements.txt -U

Restart the Backend Server
To apply the updates, you need to restart the backend server. If you have a running instance, stop it first and then start it again using the provided script.

bash start.sh

This command should be run from within the backend directory of your Open WebUI project.

INFO
Direct installations require more manual effort to update compared to Docker-based installations. If you frequently need updates and want to streamline the process, consider transitioning to a Docker-based setup for easier management.

By following these steps, you can update your direct installation of Open WebUI, ensuring you're running the latest version with all its benefits. Remember to back up any critical data or custom configurations before starting the update process to prevent any unintended loss.


---
---

Ollama Load Balancing Setup
This guide demonstrates how to configure Open WebUI to connect to multiple Ollama instances for load balancing within your deployment. This approach enables you to distribute processing loads across several nodes, enhancing both performance and reliability. The configuration leverages environment variables to manage connections between container updates, rebuilds, or redeployments seamlessly.

Docker Run
To connect to multiple Ollama instances with Docker, use the following example command:

docker run -d -p 3000:8080 \
  -v open-webui:/app/backend/data \
  -e OLLAMA_BASE_URLS="http://ollama-one:11434;http://ollama-two:11434" \
  --name open-webui \
  --restart always \
  ghcr.io/open-webui/open-webui:main

This command configures your Docker container with these key environment variables:

OLLAMA_BASE_URLS: Specifies the base URLs for each Ollama instance, separated by semicolons (;). This example uses two instances, but you can adjust this to fit your setup.
Ensure both Ollama instances are of the same version and have matching tags for each model they share. Discrepancies in model versions or tags across instances can lead to errors due to how WebUI de-duplicates and merges model lists.

Docker Compose
For those preferring docker-compose, here's an abridged version of a docker-compose.yaml file:

services:
  open-webui:
    environment:
      - OLLAMA_BASE_URLS=http://ollama-one:11434;http://ollama-two:11434

To further streamline this setup, you can define OLLAMA_BASE_URLS in an .env file located in the same directory as your docker-compose.yaml. Your .env file might look like this:

OLLAMA_BASE_URLS="http://ollama-one:11434;http://ollama-two:11434"

Ensuring Model Consistency
Both Ollama instances must run identical versions and tags for each shared model to prevent issues. The system allows for models to be present on one server and not the other, smartly routing requests to the server containing the requested model. However, having different versions or hashes for the same model tag across instances can cause inconsistencies.

Utilize the Update All Models button beside the server selector drop-down within the Settings > Models screen to keep models synchronized across instances.

By following these steps, you can effectively distribute the computational load across multiple Ollama instances, ensuring a robust and efficient deployment with Open WebUI.


---
---


OpenAI Connections
In this tutorial, we will demonstrate how to configure multiple OpenAI (or compatible) API endpoints using environment variables. This setup allows you to easily switch between different API providers or use multiple providers simultaneously, while keeping your configuration between container updates, rebuilds or redeployments.

Docker Run
Here's an example docker run command similar to what you might use for Open WebUI:

docker run -d -p 3000:8080 \
  -v open-webui:/app/backend/data \
  -e OPENAI_API_BASE_URLS="https://api.openai.com/v1;https://api.mistral.ai/v1" \
  -e OPENAI_API_KEYS="<OPENAI_API_KEY_1>;<OPENAI_API_KEY_2>" \
  --name open-webui \
  --restart always \
  ghcr.io/open-webui/open-webui:main

This command sets the following environment variables:

OPENAI_API_BASE_URLS: A list of API base URLs separated by semicolons (;). In this example, we use OpenAI and Mistral.
OPENAI_API_KEYS: A list of API keys corresponding to the base URLs specified in OPENAI_API_BASE_URLS. Make sure to replace <OPENAI_API_KEY_1> and <OPENAI_API_KEY_2> with your actual API keys.
You can adapt this command to your own needs, and add even more endpoint/key pairs, but make sure to include the environment variables as shown above.

Docker Compose
Alternatively, you can use a docker-compose.yaml file to define and run the Open WebUI container. Here's an abridged version of what that might look like:

services:
  open-webui:
    environment:
      - 'OPENAI_API_BASE_URLS=${OPENAI_API_BASE_URLS}'
      - 'OPENAI_API_KEYS=${OPENAI_API_KEYS}'

You can edit the ${VARIABLES} directly, or optionally define the values of these variables in an .env file, which should be placed in the same directory as the docker-compose.yaml file:

OPENAI_API_BASE_URLS="https://api.openai.com/v1;https://api.mistral.ai/v1"
OPENAI_API_KEYS="<OPENAI_API_KEY_1>;<OPENAI_API_KEY_2>"

 

---
---


Image Generation
Open WebUI now supports image generation through the AUTOMATIC1111 API. To set this up, follow these steps:

Initial Setup
Ensure that you have AUTOMATIC1111 installed.
Launch AUTOMATIC1111 with additional flags to enable API access:
./webui.sh --api --listen

For Docker installations of Open WebUI, use the --listen flag to allow connections outside of localhost.
Configuring Open WebUI
In Open WebUI, navigate to Settings > Images.
In the API URL field, enter the address where AUTOMATIC1111's API is accessible, following this format:
http://<your_automatic1111_address>:7860

If you're running a Docker installation of Open WebUI and AUTOMATIC1111 on the same host, replace <your_automatic1111_address> with host.docker.internal.
Using Image Generation
Image Generation Tutorial

First, use a text generation model to write a prompt for image generation.
After the response has finished, you can click the Picture icon to generate an image.
Please note that, as of now, only AUTOMATIC1111's API is supported for image generation within Open WebUI.

Edit this page


---
---


LiteLLM Configuration
LiteLLM supports a variety of APIs, both OpenAI-compatible and others. To integrate a new API model, follow these instructions:

Initial Setup
To allow editing of your config.yaml file, use -v /path/to/litellm/config.yaml:/app/backend/data/litellm/config.yaml to bind-mount it with your docker run command:

docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data -v /path/to/litellm/config.yaml:/app/backend/data/litellm/config.yaml --name open-webui --restart always ghcr.io/open-webui/open-webui:main


Note: config.yaml does not need to exist on the host before running for the first time.

Configuring Open WebUI
Go to the Settings > Models > Manage LiteLLM Models.

In 'Simple' mode, you will only see the option to enter a Model.

For additional configuration options, click on the 'Simple' toggle to switch to 'Advanced' mode. Here you can enter:

Model Name: The name of the model as you want it to appear in the models list.
API Base URL: The base URL for your API provider. This field can usually be left blank unless your provider specifies a custom endpoint URL.
API Key: Your unique API key. Replace with the key provided by your API provider.
API RPM: The allowed requests per minute for your API. Replace with the appropriate value for your API plan.
After entering all the required information, click the '+' button to add the new model to LiteLLM.

Examples
Ollama API (from inside Docker): LiteLLM Config Ollama

Gemini API (MakerSuite/AI Studio): LiteLLM Config Gemini

Advanced configuration options not covered in the settings interface can be edited in the config.yaml file manually. For more information on the specific providers and advanced settings, consult the LiteLLM Providers Documentation.


---
---

Deployment
INFO
Seeking Contributors!
👋 Calling all youtubers! Want to showcase Open WebUI's features in a video? We'll feature it at the top of our guide section!

   
Edit this page

---
---

📋 Frequently Asked Questions
Q: Why am I asked to sign up? Where are my data being sent to?
A: We require you to sign up to become the admin user for enhanced security. This ensures that if the Open WebUI is ever exposed to external access, your data remains secure. It's important to note that everything is kept local. We do not collect your data. When you sign up, all information stays within your server and never leaves your device. Your privacy and security are our top priorities, ensuring that your data remains under your control at all times.

Q: Why can't my Docker container connect to services on the host using localhost?
A: Inside a Docker container, localhost refers to the container itself, not the host machine. This distinction is crucial for networking. To establish a connection from your container to services running on the host, you should use the DNS name host.docker.internal instead of localhost. This DNS name is specially recognized by Docker to facilitate such connections, effectively treating the host as a reachable entity from within the container, thus bypassing the usual localhost scope limitation.

Q: How do I make my host's services accessible to Docker containers?
A: To make services running on the host accessible to Docker containers, configure these services to listen on all network interfaces, using the IP address 0.0.0.0, instead of 127.0.0.1 which is limited to localhost only. This configuration allows the services to accept connections from any IP address, including Docker containers. It's important to be aware of the security implications of this setup, especially when operating in environments with potential external access. Implementing appropriate security measures, such as firewalls and authentication, can help mitigate risks.

Q: Why isn't my Open WebUI updating? I've re-pulled/restarted the container, and nothing changed.
A: Updating Open WebUI requires more than just pulling the new Docker image. Here’s why your updates might not be showing and how to ensure they do:

Updating the Docker Image: The command docker pull ghcr.io/open-webui/open-webui:main updates the Docker image but not the running container or its data.
Persistent Data in Docker Volumes: Docker volumes store data independently of container lifecycles, preserving your data (like chat histories) through updates.
Applying the Update: Ensure your update takes effect by removing the existing container (which doesn't delete the volume) and creating a new one with the updated image and existing volume attached.
This process updates the app while keeping your data safe.

Q: Wait, delete my container, won't I lose my data?
A: It's a common concern, but deleting a container doesn't mean you'll lose your data, provided you're using Docker volumes correctly. Here’s why:

Volumes Preserve Data: Docker volumes are designed to persist data outside of container lifecycles. As long as your data is stored in a volume, it remains intact, regardless of what happens to the container.
Safe Update Process: When updating Open WebUI, removing the old container and creating a new one with the updated image does not affect the data stored in volumes. The key is not to explicitly delete the volume with commands like docker volume rm.
By following the correct update steps—pulling the new image, removing the old container without deleting the volume, and creating a new container with the updated image and the existing volume—your application code is updated while your data remains unchanged and safe.

Q: Should I use the distro-packaged Docker or the official Docker package?
A: We recommend using the official Docker package over distro-packaged versions for running Open WebUI. The official Docker package is frequently updated with the latest features, bug fixes, and security patches, ensuring optimal performance and security. Additionally, it supports important functionalities like host.docker.internal, which may not be available in distro-packaged versions. This feature is essential for proper network configurations and connectivity within Docker containers.

By choosing the official Docker package, you benefit from consistent behavior across different environments, more reliable troubleshooting support, and access to the latest Docker advancements. The broader Docker community and resources are also more aligned with the official package, providing you with a wealth of information and support for any issues you might encounter.

Everything you need to run Open WebUI, including your data, remains within your control and your server environment, emphasizing our commitment to your privacy and security. For instructions on installing the official Docker package, please refer to the Install Docker Engine guide on Docker's official documentation site.

If you have any further questions or concerns, please don't hesitate to reach out! 🛡️

Edit this page

---
---

🛣️ Roadmap
Here are some exciting tasks on our roadmap:

🔊 Local Text-to-Speech Integration: Seamlessly incorporate text-to-speech functionality directly within the platform, allowing for a smoother and more immersive user experience.
🛡️ Granular Permissions and User Groups: Empower administrators to finely control access levels and group users according to their roles and responsibilities. This feature ensures robust security measures and streamlined management of user privileges, enhancing overall platform functionality.
🔄 Function Calling: Empower your interactions by running code directly within the chat. Execute functions and commands effortlessly, enhancing the functionality of your conversations.
⚙️ Custom Python Backend Actions: Empower your Open WebUI by creating or downloading custom Python backend actions. Unleash the full potential of your web interface with tailored actions that suit your specific needs, enhancing functionality and versatility.
🔧 Fine-tune Model (LoRA): Fine-tune your model directly from the user interface. This feature allows for precise customization and optimization of the chat experience to better suit your needs and preferences.
🧠 Long-Term Memory: Witness the power of persistent memory in our agents. Enjoy conversations that feel continuous as agents remember and reference past interactions, creating a more cohesive and personalized user experience.
📚 Enhanced Documentation: Elevate your setup and customization experience with improved, comprehensive documentation.
🧑‍🔬 Research Tools
🧪 Research-Centric Features: Empower researchers in the fields of LLM and HCI with a comprehensive web UI for conducting user studies. Stay tuned for ongoing feature enhancements (e.g., surveys, analytics, and participant tracking) to facilitate their research.
📈 User Study Tools: Providing specialized tools, like heat maps and behavior tracking modules, to empower researchers in capturing and analyzing user behavior patterns with precision and accuracy.
Read more about our research offerings

Feel free to contribute and help us make Open WebUI even better! 🙌

Edit this page

---
---
On this page
🧑‍🔬 Open WebUI for Research
Interested in Using Open WebUI for Research?
🔍 Are you interested in leveraging Open WebUI for your research? We're excited about the prospect of collaborating with you! Alongside our continuous work on maintaining the Open WebUI repository, we're keen on developing a customized pipeline featuring a tailored UI crafted specifically to fulfill your research needs.

🧪 Research-Centric Features:

Our goal is to provide a comprehensive web UI catering to the demands of conducting user studies, especially in the dynamic fields of AI and HCI.
Features include surveys, analytics, and participant tracking, all meticulously crafted to streamline your research processes.
📈 User Study Tools:

We empower researchers with precision and accuracy by offering specialized tools such as heat maps and behavior tracking modules.
These tools are indispensable in capturing and analyzing intricate user behavior patterns.
Moreover, we are committed to supporting survey and analytics features. Our approach involves building custom pipelines, complete with an intuitive UI, tailored to the unique requirements of each project. We understand that one size does not fit all when it comes to research, and thus, our solutions are custom-made and exclusive to each case.

Please note that for custom projects, we adhere to our regular rate as listed on the sponsorship page. Additionally, we kindly request being listed as one of the co-authors. This ensures that our collaboration yields the best possible outcome, leveraging my expertise as a core maintainer to deliver high-quality results. We provide continuous support throughout the project lifecycle to ensure smooth integration and satisfaction with the final deliverables.

However, we are open to exploring collaborative opportunities free of charge under certain circumstances, such as projects with significant potential for mutual benefit or those aligned with our research interests. So, don't hesitate to reach out if you're interested in collaborating!


















