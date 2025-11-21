# BotPenguin Website Chatbot
## Overview
This project is a console-based chatbot developed as part of the technical assessment for the AI/ML Engineer position at **Relinns Technologies**.

The application scrapes content from [BotPenguin.com](https://botpenguin.com/) and utilizes the **Hugging Face Inference API** (specifically the `Zephyr-7b-beta` model) to answer user queries based strictly on the information available on the website.

## Features
* **Web Scraping:** Automatically fetches and cleans text data from the target URL using `BeautifulSoup`.
* **Context Retrieval:** Implements a keyword-based retrieval mechanism to fetch relevant website sections for the LLM.
* **AI Integration:** Uses the Hugging Face API to generate natural language responses.
* **Console Interface:** Interactive command-line interface for real-time testing.

## Tech Stack
* **Language:** Python 3.x
* **Libraries:** `requests`, `beautifulsoup4`
* **API:** Hugging Face Inference API

## Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd <repository-name>
    ```

2.  **Install dependencies:**
    Run the following command to install the required Python packages:
    ```bash
    pip install requests beautifulsoup4
    ```

## How to Run

1.  Open the terminal in the project directory.
2.  Run the script using Python:
    ```bash
    python chatbot.py
    ```
3.  Wait for the bot to scrape the website (a confirmation message will appear).
4.  Type your questions into the console.
    * *Example:* "What features does BotPenguin offer?"
    * Type `exit` or `quit` to close the application.

## Step-by-Step Process (Assessment Documentation)

As per the assessment guidelines, here is the breakdown of the development process:

**1. Environment Setup**
* Selected Python for its robust scraping and API support.
* Configured the development environment in PyCharm.
* Integrated the `requests` library for HTTP calls and `beautifulsoup4` for HTML parsing.

**2. Data Extraction (Web Scraping)**
* Developed a function `scrape_website(url)` that fetches the HTML content of the target URL.
* Parsed the HTML to remove non-essential elements (scripts, styles, navbars) to ensure clean text extraction.

**3. Processing Data**
* Since LLMs have token limits, I implemented a context retrieval system.
* The script identifies paragraphs in the scraped text that match keywords in the user's query and passes only the most relevant context to the API.

**4. Implementing the Chatbot**
* Utilized the Hugging Face Inference API (`HuggingFaceH4/zephyr-7b-beta`) as the LLM backend.
* Designed a strict system prompt to ensure the bot only answers based on the provided website context, minimizing hallucinations.

**5. Console Demonstration**
* Wrapped the application in a continuous `while` loop to allow for a seamless conversation flow in the terminal.

## ⚠️ Note
This project uses a Hugging Face API token. If you fork this repository, please replace the `HF_API_TOKEN` in `chatbot.py` with your own API key.
