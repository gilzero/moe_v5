# Multi-Agent Orchestration System (MOE - Mixture of Experts)
## Overview
The **Multi-Agent Orchestration System (MOE)** is a framework designed to collaboratively leverage multiple Large Language Models (LLMs), each acting as an expert with unique styles. This system facilitates enhanced query analysis by orchestrating experts to provide diverse perspectives and performing insightful analyses. It incorporates consensus-building, visualization, related question generation, and meta-analysis, enabling users to make more informed and creative decisions.
## Features
- **Multi-Expert Collaboration**: Combines the capabilities of OpenAI, Anthropic, xAI, and Google Generative AI-based LLMs.
- **Diverse Expert Styles**:
    - **Technical**: Detailed technical explanations.
    - **Creative**: Storytelling and imaginative approaches.
    - **Business**: Strategic and economic viewpoints.

- **Asynchronous Processing**: Efficient handling of multiple expert LLM responses.
- **Flexible Workflow**: Incorporates tasks like consensus analysis, visualization, tool-based insights, and more.
- **Rich Results Display**: Outputs are presented with well-structured formatting using the `rich` library in Python.

## Workflow Description
The system orchestrates the following steps:
1. **Expert Setup**:
    - Initializes multiple expert LLMs with unique styles, each powered by specified APIs and configurations.
    - Creates LLM instances dynamically for OpenAI, Anthropic, xAI, and Google Generative AI.

2. **Expert Response Gathering**:
    - Distributes a query to all experts asynchronously.
    - Collects responses styled according to each expert's respective configurations.

3. **Response Analysis**:
    - **Consensus Analysis**: Synthesizes insights into cohesive conclusions and highlights differing opinions.
    - **Charts and Mindmaps**: Generates visual component descriptions for chart/mindmap creation.
    - **Analysis Tools**: Performs sentiment analysis, bias detection, jargon explanation, and more.
    - **Related Questions**: Provides suggestions for deeper exploration.
    - **Meta-Analysis**: Evaluates quality metrics and reveals overarching patterns.

4. **Results Display**:
    - Presents the workflow outcomes in a user-friendly, Markdown-based format within Jupyter Notebook.

## File Structure
- **`main.ipynb` **: The Jupyter Notebook containing code for implementing the MOE system.
- **`config.yaml` **: The configuration file that defines model settings, expert styles, and task-specific prompts.
- **`moe_v5.log` **: Log file generated during execution for debugging and tracking system events.

## Prerequisites
1. **Environment Setup**:
    - Python 3.13 or a compatible environment.
    - Required Python libraries:
        - `os`, `dotenv`, `logging`, `asyncio`, `yaml`, `dataclasses`, `rich`, `IPython.display`.

2. **API Keys**:
    - Obtain API keys for the following services:
        - OpenAI API
        - Anthropic API
        - xAI API
        - Google Generative AI API

    - Configure the `.env` file or ensure these keys are available as environment variables.

## Configuration
The **`config.yaml` **file outlines model-specific settings, API configurations, and expert prompt templates. Examples include:
``` yaml
openai_config:
  temperature: 0.1
  max_tokens: 512

anthropic_config:
  temperature: 0.2
  max_tokens: 512

expert_styles:
  technical: "Focus on detailed technical explanations."
  creative: "Use imaginative, broad storytelling approaches."
  business: "Emphasize strategic and economic impacts."
```
Update **`config.yaml` **based on your specific requirements.
## Installation Steps
1. Clone or download the repository.
2. Install dependencies:
``` bash
   pip install -r requirements.txt
```
1. Configure the `.env` file with your API keys:
``` 
   OPENAI_API_KEY=<your-openai-api-key>
   ANTHROPIC_API_KEY=<your-anthropic-api-key>
   XAI_API_KEY=<your-xai-api-key>
   GOOGLE_API_KEY=<your-google-api-key>
```
1. Add or modify the **`config.yaml` **file as needed.

## Usage
1. Launch the Jupyter Notebook:
``` bash
   jupyter notebook main.ipynb
```
1. Replace the example query in the notebook (variable: `query_example`) with your desired question or topic.
2. Run the cells to execute the full workflow:
    - API keys and configuration files are loaded.
    - The query is distributed to experts.
    - Insights are processed, analyzed, and displayed.

3. View the results in both console output and rich-formatted Markdown.

## Example Query
Query Example:
``` text
Explain how Data Analysis and Data Science are different.
```
Output Highlights:
- **Expert Responses**: Insights from OpenAI, Anthropic, and xAI models.
- **Consensus Analysis**: Summarized agreement and disagreements.
- **Charts and Mindmaps**: Suggestions to create meaningful visualizations.
- **Analysis Tools**: Detailed output using advanced analytical tools.
- **Related Questions**: New questions for extending the current exploration.
- **Meta-Analysis**: Reflections and patterns detected in expert responses.

## Logs and Debugging
Execution logs are stored in **`moe_v5.log` **for review. Ensure proper logging levels are configured in the code:
``` python
logging.basicConfig(level=logging.INFO)
```
## Key Components
### 1. **Expert Setup**
- Dynamically initializes models like `ChatOpenAI`, `ChatAnthropic`, `ChatXAI`, and `ChatGoogleGenerativeAI`.

### 2. **Analysis**
- Combines LLM outputs, processes asynchronous tasks, and analyzes via the supervisor model.

### 3. **Rich Results Display**
- Presents data using the `rich` and `IPython.display` libraries.

### 4. **Asynchronous Workflow**
- Leverages Python's `asyncio` for concurrent querying and analysis.

## Future Enhancements
- Add support for additional LLMs and APIs.
- Extend visualization capabilities (e.g., automated chart generation using libraries like Matplotlib or Plotly).
- Optimize configuration-based role assignment for more flexibility.

## License and Contributions
- Open Source: **MIT License**
- Contributions: Developers are encouraged to fork and contribute to the project. Submit feature requests or pull requests via GitHub.

This README serves as a guide to understanding, configuring, and using the MOE system effectively for advanced multi-LLM orchestration tasks.
