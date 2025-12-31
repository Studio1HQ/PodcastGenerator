# Article to Podcast Generator

This project demonstrates a simple end-to-end pipeline that converts an online article into a short podcast. It uses Tensorlake for web scraping and data preparation, Gemini for summarization, and ElevenLabs for text-to-speech.

---

## Project Overview

The workflow follows these key phases:

1. **Web Scraping and Data Preparation**  
   A Tensorlake application crawls the given article URL, fetches the page content, and extracts clean, readable text.

2. **Summarization**  
   The cleaned text is summarized into a podcast-style script using Gemini.

3. **Audio Generation**  
   The generated script is converted into audio using ElevenLabs text-to-speech.

4. **User Interface**  
   A Streamlit app ties everything together and allows the entire flow to be run from a browser.

---

## Project Structure

- `main.py`  
  Defines the Tensorlake web scraper and clean text extraction logic.

- `summarize.py`  
  Uses Gemini to generate a podcast-style summary from the cleaned text.

- `audio.py`  
  Converts the generated podcast script into audio using ElevenLabs.

- `app.py`  
  Streamlit application that runs the full pipeline from URL input to audio output.

- `.env`  
  Stores API keys for Gemini and ElevenLabs.

---

## Prerequisites

- Python 3.10 or later
- Virtual environment (recommended)
- API keys for:
  - Gemini
  - ElevenLabs

---

## Setup

1. Create and activate a virtual environment:
```
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```
2. Install dependencies
```
pip install tensorlake streamlit python-dotenv requests google-genai
```
Or you can also use `pip install -r requirements.txt.`

3. Create a .env file in the project root
```
GEMINI_API_KEY=your_gemini_api_key
ELEVENLABS_API_KEY=your_elevenlabs_api_key
```

## Running the Project

Run the Streamlit App

```
streamlit run app.py
```

From the UI:
- Enter an article URL.
- Provide your Gemini and ElevenLabs API keys.
- Click Generate Podcast.
- View the generated script and listen to the podcast audio.
