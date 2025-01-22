# My Python Project

## Overview
This project is a Python application that demonstrates how to perform searches using the Bing API and generate responses using the Azure OpenAI API. It includes examples of how to load environment variables, define functions for API calls, and store messages.

## Project Structure
\`\`\`
my-python-project
├── .venv
│   └── .env
├── src
│   ├── __init__.py
│   ├── main.py
│   ├── country_data.py
│   └── Function_Calling.ipynb
├── requirements.txt
└── README.md
\`\`\`

## Installation
To install the required dependencies, run the following command:

\`\`\`sh
pip install -r requirements.txt
%pip install pymupdf==1.23.22
%pip install transformers tiktoken
\`\`\`

## Environment Variables
Create a \`.env\` file in the \`.venv\` directory with the following content:

\`\`\`plaintext
AZURE_OPENAI_ENDPOINT_URL=
AZURE_OPENAI_API_KEY=
AZURE_OPENAI_EMBEDDINGS_DEPLOYMENT_NAME=t
BING_API_KEY=
\`\`\`

## Usage
To run the application, execute the following command:

\`\`\`sh
python src/main.py
\`\`\`

## Jupyter Notebooks
This project includes Jupyter Notebooks for demonstrating API calls:

- \`Function_Calling.ipynb\`: Demonstrates how to perform searches using the Bing API and generate responses using the Azure OpenAI API.

To run the notebooks, start Jupyter Notebook or JupyterLab:

\`\`\`sh
jupyter notebook
# or
jupyter lab
\`\`\`

## Example Functions
### Search Bing
\`\`\`python
def search_bing(query):
    headers = {
        'Ocp-Apim-Subscription-Key': bing_api_key
    }
    params = {
        'q': query,
        'count': 10
    }
    response = requests.get('https://api.bing.microsoft.com/v7.0/search', headers=headers, params=params)
    response.raise_for_status()
    return response.json()
\`\`\`

### Call Azure OpenAI
\`\`\`python
def call_azure_openai(prompt):
    openai.api_key = azure_openai_api_key
    openai.api_base = azure_openai_endpoint_url
    openai.api_type = 'azure'
    openai.api_version = 'v1'

    response = openai.Completion.create(
        engine="davinci",
        prompt=prompt,
        max_tokens=100
    )
    return response.choices[0].text.strip()
\`\`\`

## Contributing
Feel free to submit issues or pull requests for improvements or bug fixes.

## License
This project is licensed under the MIT License.
EOF