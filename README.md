# Text Autocompletion with Hugging Face Transformers
This repository demonstrates how to use the Hugging Face Transformers library to implement text autocompletion in a Jupyter Notebook environment.

## Getting Started
### Prerequisites
- Python 3.6 or higher
- Jupyter Notebook
- Hugging Face Transformers library

### Installation
1. Clone this repository:
```bash
git clone https://github.com/shaadclt/TextAutocomplete-HuggingFace.git
```

Install the required dependencies:
bash
Copy code
pip install transformers
pip install jupyter
Usage
Launch Jupyter Notebook:
bash
Copy code
jupyter notebook
Open the Text_Autocompletion.ipynb notebook.
Follow the instructions in the notebook to see text autocompletion in action.
Model Used
We use the pszemraj/opt-350m-email-generation model for text autocompletion. This model is fine-tuned on a large dataset and is capable of generating coherent text based on prompts.

Example
python
Copy code
from transformers import pipeline

model_tag = "pszemraj/opt-350m-email-generation"
generator = pipeline(
    'text-generation',
    model=model_tag,
    use_fast=False,
    do_sample=False,
    early_stopping=True,
)

prompt = "My arm is broken so I should"

output = generator(
    prompt,
    max_length=10,
    truncation=True
)

print(output[0]['generated_text'])
License
This project is licensed under the MIT License - see the LICENSE file for details.

Acknowledgments
Hugging Face for providing the Transformers library.
Authors of the pszemraj/opt-350m-email-generation model.
