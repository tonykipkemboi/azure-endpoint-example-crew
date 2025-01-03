# HelloWorld Crew

Welcome to the HelloWorld Crew project, powered by [crewAI](https://crewai.com). This template is designed to help you set up a multi-agent AI system with ease, leveraging the powerful and flexible framework provided by crewAI. Our goal is to enable your agents to collaborate effectively on complex tasks, maximizing their collective intelligence and capabilities.

## Installation

Ensure you have Python >=3.10 <=3.13 installed on your system. This project uses [UV](https://docs.astral.sh/uv/) for dependency management and package handling, offering a seamless setup and execution experience.

First, if you haven't already, install uv:

```bash
pip install uv
```

Next, navigate to your project directory and install the dependencies:

(Optional) Lock the dependencies and install them by using the CLI command:
```bash
crewai install
```
### Customizing

**Add your `OPENAI_API_KEY` into the `.env` file**

- Modify `src/hello_world/config/agents.yaml` to define your agents
- Modify `src/hello_world/config/tasks.yaml` to define your tasks
- Modify `src/hello_world/crew.py` to add your own logic, tools and specific args
- Modify `src/hello_world/main.py` to add custom inputs for your agents and tasks

## Azure OpenAI Setup

1. **Azure OpenAI Setup**
   - Create an Azure OpenAI resource in Azure Portal
   - Deploy a model (e.g., GPT-4 or GPT-3.5-Turbo) in your Azure OpenAI resource
   - Note down your deployment name

2. **Configure Azure Credentials**
   Create a `.env` file in the root directory with the following:
   ```env
   AZURE_API_KEY=your_azure_api_key
   AZURE_API_BASE=https://your-resource-name.openai.azure.com/ 
   AZURE_API_VERSION=2024-08-01-preview 
   ```
   Where:
   - `AZURE_API_KEY`: Your Azure OpenAI API key
   - `AZURE_API_BASE`: Your Azure OpenAI endpoint URL
   - `AZURE_API_VERSION`: Azure OpenAI API version 

3. **Update Configuration**
   In `src/hello_world/config/agents.yaml`, ensure the `llm` field matches your Azure deployment name:
   ```yaml
   llm: azure/your-deployment-name
   ```

4. **Run the Project**
   ```bash
   crewai run
   ```

### Troubleshooting

- If you get a 404 error, verify that:
  - Your deployment name in `agents.yaml` matches exactly with your Azure OpenAI deployment
  - Your Azure credentials in `.env` are correct
  - You have successfully deployed the model in Azure OpenAI
- If you get an authentication error, check your `AZURE_API_KEY`
- If you get an endpoint error, verify your `AZURE_API_BASE` URL

## Running the Project

To kickstart your crew of AI agents and begin task execution, run this from the root folder of your project:

```bash
$ crewai run
```

This command initializes the hello-world Crew, assembling the agents and assigning them tasks as defined in your configuration.

This example, unmodified, will run the create a `report.md` file with the output of a research on LLMs in the root folder.

## Understanding Your Crew

The hello-world Crew is composed of multiple AI agents, each with unique roles, goals, and tools. These agents collaborate on a series of tasks, defined in `config/tasks.yaml`, leveraging their collective skills to achieve complex objectives. The `config/agents.yaml` file outlines the capabilities and configurations of each agent in your crew.

## Support

For support, questions, or feedback regarding the HelloWorld Crew or crewAI.
- Visit our [documentation](https://docs.crewai.com)
- Reach out to us through our [GitHub repository](https://github.com/joaomdmoura/crewai)
- [Join our Discord](https://discord.com/invite/X4JWnZnxPb)
- [Chat with our docs](https://chatg.pt/DWjSBZn)

Let's create wonders together with the power and simplicity of CrewAI.
