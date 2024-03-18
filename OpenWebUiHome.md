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

















