# structural_llama 🦙

## Your AI Assistant for Structural Engineering 🏗️

Structural_Llama 🦙 leverages advanced language modelling to aid structural engineers. It offers insights and assistance with common tasks. This open-source project brings the power of large language models like Llama2 directly to your machine with a user-friendly interface. Expand functionality even further by connecting your OpenAI API key for full ChatGPT capabilities – all within a single platform.

💻 This app runs locally on Docker for enhanced privacy. Your data is analyzed directly on your device using a local model.

Whether you're a student, practicing engineer, or researcher, Structural_Llama can help you:

📘 Understand complex concepts: Get in-depth explanations of structural design principles, analysis methods, failure modes, and code requirements.
💡 Solve problems efficiently: Receive guidance on design calculations, optimization approaches, and troubleshooting structural issues.
💻 Enhance your code: Get Python code suggestions (using NumPy, SciPy, and other relevant libraries) for analysis, visualization, and automating calculations.
📚 Stay code-compliant: Get references to relevant design standards and regulations (AISC, ACI, CSA, Eurocode, etc.).
📢 Important Note: Do not rely on this model for creating correct structural calculations. It still has a long way to go! (Note: the model is primed for Python, VS Code and Poetry; this can be easily modified).

![image](https://github.com/joreilly86/structual_llama/assets/44675992/954cb0c7-d6c4-466e-94a8-b201d8893593)

## Requirements 📋

- Model size: 7.4GB (llama2-13b)
- A GPU and some decent RAM are highly recommended for solid performance. 🖥️
- Docker engine running locally to host the app and your models.

## Installation 💾

- You have a few options to get up and running. I recommend installing and managing through [Open WebUI](https://openwebui.com/) and using [Docker](https://www.docker.com/) to install, run and manage your models.
- See the [GitHub repo](https://github.com/open-webui/open-webui) for detailed steps on installation via Docker and other tools.

- If you just want the model, you can run:\
     ```ollama run joreilly86/structural_llama```

**Key Capabilities 🔑**

* 🏛️ **Technical Expertise:** Provides explanations tailored to structural engineering topics. 
* 🖥️ **Code Integration:** Understands and suggests Python code relevant to engineering problems.
* 📖 **Knowledge Access:** References authoritative sources like design manuals and building codes.
* 🛠️ **Contextual Awareness:** Considers code requirements and practical constructability when offering solutions.

**How to Use Structural_Llama 🤖**

* Ask precise questions and break down complex problems into smaller steps for best results.

**Example Interactions 💬**

* **Question:** "How do I calculate the buckling capacity of a steel column?"
* **Potential Response:** Provides a theoretical explanation, references AISC specifications, and potentially a Python code snippet for calculation.

* **Prompt:** "Can you optimize this code for readability and efficiency?" (Include your code snippet)
* **Potential Response:** Suggests refactoring, explains algorithm choice, and demonstrates improvements.

**Important Notes 📝**

* Structural_Llama is a powerful tool, but it's not a replacement for professional judgment. Always validate results and ensure compliance with local regulations.
* The model is continuously evolving. If you have feedback or suggestions, reach out at [email address removed].

**Get Started! 🚀**

We're excited to see how Structural_Llama assists you with your structural engineering projects!

**For more Python engineering tips and insights 🐍**

* Subscribe to the Flocode newsletter and visit flocode.dev.

**From James 🌊** 


---

# Info below is forked from [OpenWebUI](https://github.com/open-webui/open-webui/tree/main) 

# Open WebUI (Formerly Ollama WebUI) 👋

![GitHub stars](https://img.shields.io/github/stars/open-webui/open-webui?style=social)
![GitHub forks](https://img.shields.io/github/forks/open-webui/open-webui?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/open-webui/open-webui?style=social)
![GitHub repo size](https://img.shields.io/github/repo-size/open-webui/open-webui)
![GitHub language count](https://img.shields.io/github/languages/count/open-webui/open-webui)
![GitHub top language](https://img.shields.io/github/languages/top/open-webui/open-webui)
![GitHub last commit](https://img.shields.io/github/last-commit/open-webui/open-webui?color=red)
![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Follama-webui%2Follama-wbui&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)
[![Discord](https://img.shields.io/badge/Discord-Open_WebUI-blue?logo=discord&logoColor=white)](https://discord.gg/5rJgQTnV4s)
[![](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/tjbck)

ChatGPT-Style Web Interface for Ollama 🦙

![Open WebUI Demo](./demo.gif)

Also check our sibling project, [Open WebUI Community](https://openwebui.com/), where you can discover, download, and explore customized Modelfiles for Ollama! 🦙🔍

## Features ⭐

- 🖥️ **Intuitive Interface**: Our chat interface takes inspiration from ChatGPT, ensuring a user-friendly experience.

- 📱 **Responsive Design**: Enjoy a seamless experience on both desktop and mobile devices.

- ⚡ **Swift Responsiveness**: Enjoy fast and responsive performance.

- 🚀 **Effortless Setup**: Install seamlessly using Docker or Kubernetes (kubectl, kustomize or helm) for a hassle-free experience.

- 💻 **Code Syntax Highlighting**: Enjoy enhanced code readability with our syntax highlighting feature.

- ✒️🔢 **Full Markdown and LaTeX Support**: Elevate your LLM experience with comprehensive Markdown and LaTeX capabilities for enriched interaction.

- 📚 **Local RAG Integration**: Dive into the future of chat interactions with the groundbreaking Retrieval Augmented Generation (RAG) support. This feature seamlessly integrates document interactions into your chat experience. You can load documents directly into the chat or add files to your document library, effortlessly accessing them using `#` command in the prompt. In its alpha phase, occasional issues may arise as we actively refine and enhance this feature to ensure optimal performance and reliability.

- 🌐 **Web Browsing Capability**: Seamlessly integrate websites into your chat experience using the `#` command followed by the URL. This feature allows you to incorporate web content directly into your conversations, enhancing the richness and depth of your interactions.

- 📜 **Prompt Preset Support**: Instantly access preset prompts using the `/` command in the chat input. Load predefined conversation starters effortlessly and expedite your interactions. Effortlessly import prompts through [Open WebUI Community](https://openwebui.com/) integration.

- 👍👎 **RLHF Annotation**: Empower your messages by rating them with thumbs up and thumbs down, facilitating the creation of datasets for Reinforcement Learning from Human Feedback (RLHF). Utilize your messages to train or fine-tune models, all while ensuring the confidentiality of locally saved data.

- 🏷️ **Conversation Tagging**: Effortlessly categorize and locate specific chats for quick reference and streamlined data collection.

- 📥🗑️ **Download/Delete Models**: Easily download or remove models directly from the web UI.

- ⬆️ **GGUF File Model Creation**: Effortlessly create Ollama models by uploading GGUF files directly from the web UI. Streamlined process with options to upload from your machine or download GGUF files from Hugging Face.

- 🤖 **Multiple Model Support**: Seamlessly switch between different chat models for diverse interactions.

- 🔄 **Multi-Modal Support**: Seamlessly engage with models that support multimodal interactions, including images (e.g., LLava).

- 🧩 **Modelfile Builder**: Easily create Ollama modelfiles via the web UI. Create and add characters/agents, customize chat elements, and import modelfiles effortlessly through [Open WebUI Community](https://openwebui.com/) integration.

- ⚙️ **Many Models Conversations**: Effortlessly engage with various models simultaneously, harnessing their unique strengths for optimal responses. Enhance your experience by leveraging a diverse set of models in parallel.

- 💬 **Collaborative Chat**: Harness the collective intelligence of multiple models by seamlessly orchestrating group conversations. Use the `@` command to specify the model, enabling dynamic and diverse dialogues within your chat interface. Immerse yourself in the collective intelligence woven into your chat environment.

- 🤝 **OpenAI API Integration**: Effortlessly integrate OpenAI-compatible API for versatile conversations alongside Ollama models. Customize the API Base URL to link with **LMStudio, Mistral, OpenRouter, and more**.

- 🔄 **Regeneration History Access**: Easily revisit and explore your entire regeneration history.

- 📜 **Chat History**: Effortlessly access and manage your conversation history.

- 📤📥 **Import/Export Chat History**: Seamlessly move your chat data in and out of the platform.

- 🗣️ **Voice Input Support**: Engage with your model through voice interactions; enjoy the convenience of talking to your model directly. Additionally, explore the option for sending voice input automatically after 3 seconds of silence for a streamlined experience.

- ⚙️ **Fine-Tuned Control with Advanced Parameters**: Gain a deeper level of control by adjusting parameters such as temperature and defining your system prompts to tailor the conversation to your specific preferences and needs.

- 🔗 **External Ollama Server Connection**: Seamlessly link to an external Ollama server hosted on a different address by configuring the environment variable.

- 🔐 **Role-Based Access Control (RBAC)**: Ensure secure access with restricted permissions; only authorized individuals can access your Ollama, and exclusive model creation/pulling rights are reserved for administrators.

- 🔒 **Backend Reverse Proxy Support**: Bolster security through direct communication between Open WebUI backend and Ollama. This key feature eliminates the need to expose Ollama over LAN. Requests made to the '/ollama/api' route from the web UI are seamlessly redirected to Ollama from the backend, enhancing overall system security.

- 🌟 **Continuous Updates**: We are committed to improving Open WebUI with regular updates and new features.

## 🔗 Also Check Out Open WebUI Community!

Don't forget to explore our sibling project, [Open WebUI Community](https://openwebui.com/), where you can discover, download, and explore customized Modelfiles. Open WebUI Community offers a wide range of exciting possibilities for enhancing your chat interactions with Ollama! 🚀

## How to Install 🚀

🌟 **Important Note on User Roles and Privacy:**

- **Admin Creation:** The very first account to sign up on Open WebUI will be granted **Administrator privileges**. This account will have comprehensive control over the platform, including user management and system settings.

- **User Registrations:** All subsequent users signing up will initially have their accounts set to **Pending** status by default. These accounts will require approval from the Administrator to gain access to the platform functionalities.

- **Privacy and Data Security:** We prioritize your privacy and data security above all. Please be reassured that all data entered into Open WebUI is stored locally on your device. Our system is designed to be privacy-first, ensuring that no external requests are made, and your data does not leave your local environment. We are committed to maintaining the highest standards of data privacy and security, ensuring that your information remains confidential and under your control.

### Steps to Install Open WebUI

#### Before You Begin

1. **Installing Docker:**

   - **For Windows and Mac Users:**

     - Download Docker Desktop from [Docker's official website](https://www.docker.com/products/docker-desktop).
     - Follow the installation instructions provided on the website. After installation, open Docker Desktop to ensure it's running properly.

   - **For Ubuntu and Other Linux Users:**
     - Open your terminal.
     - Set up your Docker apt repository according to the [Docker documentation](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)
     - Update your package index:
       ```bash
       sudo apt-get update
       ```
     - Install Docker using the following command:
       ```bash
       sudo apt-get install docker-ce docker-ce-cli containerd.io
       ```
     - Verify the Docker installation with:
       ```bash
       sudo docker run hello-world
       ```
       This command downloads a test image and runs it in a container, which prints an informational message.

2. **Ensure You Have the Latest Version of Ollama:**

   - Download the latest version from [https://ollama.com/](https://ollama.com/).

3. **Verify Ollama Installation:**
   - After installing Ollama, check if it's working by visiting [http://127.0.0.1:11434/](http://127.0.0.1:11434/) in your web browser. Remember, the port number might be different for you.

#### Installing with Docker 🐳

- **Important:** When using Docker to install Open WebUI, make sure to include the `-v open-webui:/app/backend/data` in your Docker command. This step is crucial as it ensures your database is properly mounted and prevents any loss of data.

- **If Ollama is on your computer**, use this command:

  ```bash
  docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```

- **To build the container yourself**, follow these steps:

  ```bash
  docker build -t open-webui .
  docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always open-webui
  ```

- After installation, you can access Open WebUI at [http://localhost:3000](http://localhost:3000).

#### Using Ollama on a Different Server

- To connect to Ollama on another server, change the `OLLAMA_API_BASE_URL` to the server's URL:

  ```bash
  docker run -d -p 3000:8080 -e OLLAMA_API_BASE_URL=https://example.com/api -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```

  Or for a self-built container:

  ```bash
  docker build -t open-webui .
  docker run -d -p 3000:8080 -e OLLAMA_API_BASE_URL=https://example.com/api -v open-webui:/app/backend/data --name open-webui --restart always open-webui
  ```

### Installing Ollama and Open WebUI Together

#### Using Docker Compose

- If you don't have Ollama yet, use Docker Compose for easy installation. Run this command:

  ```bash
  docker compose up -d --build
  ```

- **For GPU Support:** Use an additional Docker Compose file:

  ```bash
  docker compose -f docker-compose.yaml -f docker-compose.gpu.yaml up -d --build
  ```

- **To Expose Ollama API:** Use another Docker Compose file:

  ```bash
  docker compose -f docker-compose.yaml -f docker-compose.api.yaml up -d --build
  ```

#### Using `run-compose.sh` Script (Linux or Docker-Enabled WSL2 on Windows)

- Give execute permission to the script:

  ```bash
  chmod +x run-compose.sh
  ```

- For CPU-only container:

  ```bash
  ./run-compose.sh
  ```

- For GPU support (read the note about GPU compatibility):

  ```bash
  ./run-compose.sh --enable-gpu
  ```

- To build the latest local version, add `--build`:

  ```bash
  ./run-compose.sh --enable-gpu --build
  ```

### Alternative Installation Methods

For other ways to install, like using Kustomize or Helm, check out [INSTALLATION.md](/INSTALLATION.md). Join our [Open WebUI Discord community](https://discord.gg/5rJgQTnV4s) for more help and information.

### Updating your Docker Installation

In case you want to update your local Docker installation to the latest version, you can do it with [Watchtower](https://containrrr.dev/watchtower/):

```bash
docker run --rm --volume /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower --run-once open-webui
```

In the last part of the command, replace `open-webui` with your container name if it is different.

### Moving from Ollama WebUI to Open WebUI

Given recent name changes, the docker image has been renamed. Additional steps are required to update for those people that used Ollama WebUI previously and want to start using the new images.

#### Updating to Open WebUI without keeping your data

If you want to update to the new image but don't want to keep any previous data like conversations, prompts, documents, etc. you can perform the following steps:

```bash
docker rm -f ollama-webui
docker pull ghcr.io/open-webui/open-webui:main
[insert the equivalent command that you used to install with the new Docker image name]
docker volume rm ollama-webui
```

For example, for local installation it would be `docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main`. For other installation commands, check the relevant parts of this README document.

#### Migrating your contents from Ollama WebUI to Open WebUI

If you want to update to the new image migrating all your previous settings like conversations, prompts, documents, etc. you can perform the following steps:

```bash
docker rm -f ollama-webui
docker pull ghcr.io/open-webui/open-webui:main
# Creates a new volume and uses a temporary container to copy from one volume to another as per https://github.com/moby/moby/issues/31154#issuecomment-360531460
docker volume create --name open-webui
docker run --rm -v ollama-webui:/from -v open-webui:/to alpine ash -c "cd /from ; cp -av . /to"
[insert the equivalent command that you used to install with the new Docker image name]
```

Once you verify that all the data has been migrated you can erase the old volumen using the following command:

```bash
docker volume rm ollama-webui
```

## How to Install Without Docker

While we strongly recommend using our convenient Docker container installation for optimal support, we understand that some situations may require a non-Docker setup, especially for development purposes. Please note that non-Docker installations are not officially supported, and you might need to troubleshoot on your own.

### Project Components

Open WebUI consists of two primary components: the frontend and the backend (which serves as a reverse proxy, handling static frontend files, and additional features). Both need to be running concurrently for the development environment.

> [!IMPORTANT]
> The backend is required for proper functionality

### Requirements 📦

- 🐰 [Bun](https://bun.sh) >= 1.0.21 or 🐢 [Node.js](https://nodejs.org/en) >= 20.10
- 🐍 [Python](https://python.org) >= 3.11

### Build and Install 🛠️

Run the following commands to install:

```sh
git clone https://github.com/open-webui/open-webui.git
cd open-webui/

# Copying required .env file
cp -RPp .env.example .env

# Building Frontend Using Node
npm i
npm run build

# or Building Frontend Using Bun
# bun install
# bun run build

# Serving Frontend with the Backend
cd ./backend
pip install -r requirements.txt -U
sh start.sh
```

You should have Open WebUI up and running at http://localhost:8080/. Enjoy! 😄

## Troubleshooting

See [TROUBLESHOOTING.md](/TROUBLESHOOTING.md) for information on how to troubleshoot and/or join our [Open WebUI Discord community](https://discord.gg/5rJgQTnV4s).

## What's Next? 🚀

### Roadmap 📝

Here are some exciting tasks on our roadmap:

- 🔊 **Local Text-to-Speech Integration**: Seamlessly incorporate text-to-speech functionality directly within the platform, allowing for a smoother and more immersive user experience.
- 🛡️ **Granular Permissions and User Groups**: Empower administrators to finely control access levels and group users according to their roles and responsibilities. This feature ensures robust security measures and streamlined management of user privileges, enhancing overall platform functionality.
- 🔄 **Function Calling**: Empower your interactions by running code directly within the chat. Execute functions and commands effortlessly, enhancing the functionality of your conversations.
- ⚙️ **Custom Python Backend Actions**: Empower your Open WebUI by creating or downloading custom Python backend actions. Unleash the full potential of your web interface with tailored actions that suit your specific needs, enhancing functionality and versatility.
- 🔧 **Fine-tune Model (LoRA)**: Fine-tune your model directly from the user interface. This feature allows for precise customization and optimization of the chat experience to better suit your needs and preferences.
- 🧠 **Long-Term Memory**: Witness the power of persistent memory in our agents. Enjoy conversations that feel continuous as agents remember and reference past interactions, creating a more cohesive and personalized user experience.
- 🧪 **Research-Centric Features**: Empower researchers in the fields of LLM and HCI with a comprehensive web UI for conducting user studies. Stay tuned for ongoing feature enhancements (e.g., surveys, analytics, and participant tracking) to facilitate their research.
- 📈 **User Study Tools**: Providing specialized tools, like heat maps and behavior tracking modules, to empower researchers in capturing and analyzing user behavior patterns with precision and accuracy.
- 📚 **Enhanced Documentation**: Elevate your setup and customization experience with improved, comprehensive documentation.

Feel free to contribute and help us make Open WebUI even better! 🙌

## Supporters ✨

A big shoutout to our amazing supporters who's helping to make this project possible! 🙏

### Platinum Sponsors 🤍

- We're looking for Sponsors!

### Acknowledgments

Special thanks to [Prof. Lawrence Kim](https://www.lhkim.com/) and [Prof. Nick Vincent](https://www.nickmvincent.com/) for their invaluable support and guidance in shaping this project into a research endeavor. Grateful for your mentorship throughout the journey! 🙌

## License 📜

This project is licensed under the [MIT License](LICENSE) - see the [LICENSE](LICENSE) file for details. 📄

## Support 💬

If you have any questions, suggestions, or need assistance, please open an issue or join our
[Open WebUI Discord community](https://discord.gg/5rJgQTnV4s) to connect with us! 🤝

---

Created by [Timothy J. Baek](https://github.com/tjbck) - Let's make Open Web UI even more amazing together! 💪
