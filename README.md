# AI Support Engine

An AI-powered customer support analysis engine that uses multiple foundation models to analyze customer inquiries and return structured, machine-readable results.

## Overview

AI Support Engine is primarily designed as a backend AI service.

It analyzes customer messages and generates structured information such as:

- Summary of the customer's message
- Sentiment score
- Inquiry category
- Recommended action for a support representative

The project also includes a web-based AI assistant interface. The interface provides a practical way to interact with and demonstrate the backend system, making it easier to see the models and their outputs working in real time.

The structured responses are designed so that other applications and services can consume the AI-generated information, for example through JSON responses from the backend API.

## Features

- Multiple foundation models
- AI-powered customer inquiry analysis
- Structured JSON output
- Sentiment analysis
- Inquiry categorization
- Recommended support actions
- Backend API
- Web-based demonstration interface
- Model selection
- Response generation time measurement

## Architecture

The application follows a simple backend-oriented architecture.

User / External Service  
↓  
Backend API  
↓  
Model Selection  
↓  
Llama / Granite / Mistral  
↓  
Structured AI Response  
↓  
JSON / Application Output

The web interface acts as a demonstration client of the backend rather than being the primary purpose of the project.

## Models

The project currently supports:

- Meta Llama
- IBM Granite
- Mistral

Different models can be selected through the application interface.

## Technologies

- Python
- Flask
- LangChain
- IBM watsonx.ai
- Pydantic
- HTML
- CSS
- JavaScript

## Project Structure

    ai-support-engine/
    │
    ├── app.py
    ├── model.py
    ├── config.py
    ├── llm_test.py
    ├── requirements.txt
    ├── README.md
    ├── .gitignore
    │
    ├── templates/
    │   └── index.html
    │
    └── static/
        ├── script.js
        └── styles.css

## Installation

Clone the repository:

    git clone https://github.com/YOUR_USERNAME/ai-support-engine.git
    cd ai-support-engine

Create a virtual environment:

    python -m venv venv

Activate it on Linux/macOS:

    source venv/bin/activate

On Windows:

    venv\Scripts\activate

Install the dependencies:

    pip install -r requirements.txt

## Configuration

The application requires access to IBM watsonx.ai.

Configure your IBM watsonx.ai credentials through environment variables rather than placing API keys directly in the source code.

Do not commit API keys, passwords, tokens, or other secrets to the repository.

The model configuration can be found in:

    config.py

## Running the Application

Start the backend:

    python app.py

The application will start a local web server.

Open the address shown in the terminal in your browser to use the web-based demonstration interface.

## API

The main backend endpoint is:

    POST /generate

Example request:

    {
        "message": "My product arrived damaged and I would like a replacement.",
        "model": "llama"
    }

The backend processes the message using the selected foundation model and returns structured information.

Example response:

    {
        "summary": "Customer received a damaged product and wants a replacement.",
        "sentiment": 20,
        "category": "complaint",
        "action": "Arrange a replacement for the damaged product."
    }

The exact response depends on the model's analysis.

## Why the Web Interface?

Although the core of the project is the backend AI processing system, the web interface provides a convenient demonstration layer.

It allows the backend functionality to be tested interactively and makes the model outputs easier to visualize.

The same backend functionality can be consumed by other applications, websites, or services that require structured AI-generated customer support information.

## Testing Multiple Models

`llm_test.py` provides a simple way to test the supported models programmatically.

This makes it possible to compare how different foundation models respond to the same customer inquiry.

## Security

API keys and other credentials should never be committed to GitHub.

Use environment variables or a secure secrets-management system when configuring the application.

## Future Improvements

- Improve structured output validation
- Add conversation history
- Add authentication
- Add database support
- Add automated API tests
- Add model performance comparison
- Add production deployment
- Add monitoring and logging
- Improve error handling
- Expand customer inquiry categories

## License

This project is provided for educational and portfolio purposes.
