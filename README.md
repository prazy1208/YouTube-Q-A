# 🎥 YouTube Q&A

Ask questions about any YouTube video and get answers directly from its content using AI.

## Overview

YouTube videos often contain valuable information, but finding specific details in long videos can be time-consuming. This project converts a YouTube video into a searchable knowledge source, allowing users to ask questions in natural language and receive answers based on the video's content.

Instead of manually searching through a one-hour tutorial, lecture, interview, or podcast, users can simply ask a question and get an answer grounded in the video transcript.

---

## Problem Statement

Finding information within long-form video content can be difficult and inefficient. Traditional keyword searches often fail to capture context, forcing users to spend significant time navigating through videos.

This project addresses that challenge by using Retrieval-Augmented Generation (RAG) to understand video content and provide context-aware answers.

---

## How It Works

1. Enter a YouTube video URL.
2. The audio is extracted from the video.
3. The audio is transcribed into text using OpenAI Whisper.
4. The transcript is divided into smaller chunks.
5. AI-generated embeddings are created for each chunk.
6. The embeddings are stored in a vector database.
7. When a user asks a question, the most relevant transcript sections are retrieved.
8. An AI model generates an answer using only the retrieved content.

### Workflow

```text
YouTube Video
      ↓
Audio Extraction
      ↓
Transcription (Whisper)
      ↓
Transcript Processing
      ↓
Vector Database (Pinecone)
      ↓
User Question
      ↓
Relevant Transcript Chunks
      ↓
AI-Generated Answer
```

---

## Example Questions

For a Python tutorial video, users can ask:

* What are the different types of loops in Python?
* How do variables work?
* What is the difference between a list and a tuple?
* How does the input function work?
* What are Python data types?

The system retrieves the most relevant sections from the transcript and generates answers based on the video content.

---

## Features

* Ask questions about any YouTube video
* AI-powered semantic search
* Answers grounded in video content
* Supports long-form educational content
* Retrieval-Augmented Generation (RAG)
* Pinecone vector database integration
* Dynamic support for different YouTube videos

---

## Technology Stack

| Category               | Technology          |
| ---------------------- | ------------------- |
| Programming Language   | Python              |
| LLM                    | OpenAI GPT-4.1-mini |
| Framework              | LangChain           |
| Embeddings             | OpenAI Embeddings   |
| Transcription          | OpenAI Whisper      |
| Vector Database        | Pinecone            |
| Video Download         | yt-dlp              |
| Environment Management | python-dotenv       |

---

## Installation

### Clone the Repository

```bash
git clone https://github.com/prazy1208/YouTube-Q-A.git
cd YouTube-Q-A
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Configure Environment Variables

Create a `.env` file:

```env
OPENAI_API_KEY=your_openai_api_key
PINECONE_API_KEY=your_pinecone_api_key
```

---

## Usage

Specify the YouTube video URL:

```python
YOUTUBE_VIDEO = "https://youtu.be/kqtD5dpn9C8"
```

Run the notebook and ask questions about the video content.

Example:

```python
question = "What are the different types of loops in Python?"
```

The system retrieves relevant transcript sections and generates an answer based on the video.

---

## Project Structure

```text
YouTube-Q-A/
│
├── yt_rag.ipynb
├── README.md
├── requirements.txt
├── .env.example
├── .gitignore
└── transcripts/
```

---

## Future Enhancements

* Support multiple videos simultaneously
* Add a Streamlit or Gradio web interface
* Use YouTube captions when available for faster processing
* Add transcript summarization
* Support conversational follow-up questions
* Cache embeddings for improved performance

---

## Author

**Prazy Jindal**

GitHub: https://github.com/prazy1208

---

## GitHub Topics

```text
rag
langchain
openai
whisper
youtube
pinecone
vector-database
python
question-answering
```
