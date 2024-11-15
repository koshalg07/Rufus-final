# Rufus: Intelligent Web Data Extraction for LLMs

## Introduction

Rufus is an AI-powered web data extraction tool designed to dynamically scrape and synthesize relevant web content into structured documents. Built with scalability and maintainability in mind, Rufus allows users to input instructions and a URL, intelligently crawling the web to extract and refine data, making it immediately usable in Retrieval-Augmented Generation (RAG) pipelines.

This project demonstrates the power of combining state-of-the-art AI with robust web scraping to handle complex data retrieval tasks. While designed for a test case, the tool showcases significant potential for scaling up to handle more sophisticated use cases.

---

## Features

- **AI-Powered Keyword Extraction**: Utilizes Google’s Gemini 1.5 LLM to extract relevant keywords from user-provided instructions, ensuring precise and targeted data extraction.
- **Dynamic Web Crawling**: Employs an intelligent crawler to retrieve content from nested links with a configurable depth (default: 2).
- **Content Filtering**: Extracts and synthesizes relevant information using an LLM to ensure data aligns with the user's instructions.
- **Scalable Design**: Modular code structure allows for easy scaling and integration into larger RAG pipelines.

---

## Technologies Used

1. **FastAPI**:
   - A modern, high-performance web framework used to build the API for handling user requests and returning responses.
   - Chosen for its ease of use, speed, and robust asynchronous capabilities.

2. **LangChain with Google Gemini 1.5**:
   - Powers the AI-driven content extraction and filtering.
   - LangChain simplifies interaction with advanced LLMs, while Google Gemini ensures accuracy and scalability in data processing.

3. **BeautifulSoup**:
   - Used for parsing HTML content and extracting relevant text and links.
   - Offers a reliable and flexible way to handle web scraping.

4. **aiohttp**:
   - Enables asynchronous HTTP requests, allowing the crawler to efficiently fetch web pages and manage nested links.

5. **Environment Variables**:
   - API keys and service account credentials are securely stored, ensuring easy deployment while keeping sensitive information safe.

---

## Installation and Setup

### Prerequisites
- Python 3.9 or higher installed on your system.

### Steps to Run

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-repo/rufus.git
   cd rufus
   ```

2. **Create a Virtual Environment**:
    ```bash
    python -m venv env
    source env/bin/activate # On Windows: env\Scripts\Activate.psl
    ```

3. **Install requirements**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Run the application**:
    ```bash
    python app.py
    ```

## How to use

### Request body
The API expects a POST request to '/scrape' with the following JSON structure:

```bash
    {
        "url": "https://en.wikipedia.org/wiki/Virat_Kohli",
        "instructions": "how many awards has virat kohli won and what are those"
    }
```

---

### Response

```bash
    {
        "url": "https://en.wikipedia.org/wiki/Virat_Kohli",
        "title": "Virat Kohli - Wikipedia",
        "filtered_content": "Virat Kohli has won 10 ICC awards. Awards include: ICC ODI Player of the Year (4 times in 2012, 2017, 2018, and 2023), Sir Garfield Sobers Trophy (2 times in 2017 and 2018), ICC Test Player of the Year (2018). He was also named the Wisden Leading Cricketer in the World for three consecutive years (2016-2018)."
    }
```

## Scalability and Future Potential

- Configurable Depth: The crawler's depth is set to 2 by default but can be scaled up to handle more complex web structures.

- Optimized Filtering: The filtering process is built to handle large datasets and can be extended to include additional LLM models or domain-specific constraints.


- Enterprise Integration: Rufus's modular design makes it suitable for integration into enterprise-level RAG pipelines or chatbot systems.


- Performance Enhancements: By leveraging asynchronous operations, Rufus can scale to handle multiple simultaneous requests, making it ideal for production environments.

## Notes

- The repository includes the required API key and service account credentials for test purposes. Ensure you replace these with your own credentials for production use.

- The project is a proof of concept but demonstrates the potential for real-world applications with minor enhancements.

