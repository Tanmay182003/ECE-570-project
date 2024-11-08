# Software Failure Analysis with GPT and Gemini Models

## Overview
This project leverages Large Language Models (LLMs) like GPT-4 and Gemini to classify and analyze software failure incidents. The primary objective is to automate the summarization, categorization, and extraction of key information from articles related to software vulnerabilities, supply chain attacks, and other cyber incidents.

The project uses multiple APIs, including OpenAI's GPT API and Google's Gemini API, to generate content, categorize articles, and perform data analysis. It utilizes environment variables to securely manage API keys.

## Table of Contents
- [Files Overview](#files-overview)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [Future Work](#future-work)

## Files Overview
### In src:
### 1. `Geminiprompts.py`
This script utilizes the Google Gemini API for generating content and analyzing software-related articles. It connects to the Gemini API using the `gemini-1.5-pro-latest` model to generate summaries, identify key vulnerabilities, and classify information.

**Key Features:**
- Configures Gemini models using an API key stored in environment variables.
- Summarizes articles to extract critical insights.
- Lists available models for content generation.
- Demonstrates the usage of the Gemini models for content generation and analysis.

### 2. `Gpt4oPrompts.py`
This script focuses on utilizing the OpenAI GPT API for content generation. It uses the `gpt-4o` model to analyze software articles, classify incidents, and generate summaries.

**Key Features:**
- Configures GPT models using environment variables for secure access.
- Extracts insights from articles related to software vulnerabilities and incidents.
- Includes functionality for categorizing incidents into predefined categories like negligence, malicious maintainers, attack chaining, etc.
- Uses metrics like Cohen's Kappa Score for evaluating classification consistency.

### In data:

### 3. `articles.py`
Contains a collection of software-related articles used for testing the Gemini and GPT models. These articles describe real-world incidents involving software vulnerabilities, supply chain attacks, and other cybersecurity issues.

### 4. `articles.csv`
A dataset containing articles with metadata used for training and evaluating the models.

### 5. `Classifying articles_analysis.xlsx`, `LLM Data.xlsx`, `Manual Labels.xlsx`
Excel files used for manual classification, data analysis, and evaluation of model performance. These files help in comparing the automated classification results with human-labeled data.

## Setup Instructions

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/YourUsername/YourRepository.git
   cd YourRepository
   ```

2. **Create a `.env` File:**
   - Add the following lines to your `.env` file:
     ```
     API_KEY=your_gemini_api_key
     OPENAI_API_KEY=your_openai_api_key
     ```

3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Run the `Geminiprompts.py` script:**
   ```bash
   python Geminiprompts.py
   ```
   This will generate summaries and analyze the articles using the Gemini API.

2. **Run the `Gpt4oPrompts.py` script:**
   ```bash
   python Gpt4oPrompts.py
   ```
   This will categorize articles and extract insights using the GPT API.

## Dependencies

- Python 3.8+
- `openai`
- `bardapi`
- `google-generativeai`
- `openpyxl`
- `matplotlib`
- `scikit-learn`
- `dotenv`

Install the dependencies using:
```bash
pip install openai bardapi google-generativeai openpyxl matplotlib scikit-learn python-dotenv
```

## Future Work
- Improve the classification accuracy by fine-tuning the prompts for GPT and Gemini models.
- Expand the dataset with more articles to enhance model training.
- Integrate additional metrics for performance evaluation.
