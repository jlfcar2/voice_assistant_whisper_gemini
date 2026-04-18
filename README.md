# voice_assistant_whisper_gemini
A voice assistant that record and recognizes your voice with Whisper, and automatically prompt your question to Gemini via API. At the end, returns the AI agent answer in a audio, sinthetized by gTTS.

# Multi-Language Voice Assistant with Whisper & Gemini
This project is a sophisticated voice-controlled assistant capable of understanding multiple
languages, processing requests through advanced AI models, and responding with synthesized
speech. It integrates OpenAI's Whisper for high-accuracy speech-to-text and Google's Gemini
Pro for intelligent natural language processing.
## Overview
The assistant works in a three-step pipeline:
1. Speech-to-Text: Captures audio via the microphone and utilizes the openai-whisper
model to transcribe the speech into text, regardless of the language spoken.
2. Inteligent Processing: The transcribed text is sent to the Gemini 1.5 Pro model, which
interprets the intent and generates a contextually relevant response.
3. Text-to-Speech: The generated response is converted back into audio using gTTS
(Google Text-to-Speech) and played back to the user.
## Key Features
● Multi-language Support: Seamlessly switch between languages for both input and
output.
● State-of-the-art AI: Leverages Gemini 1.5 Pro for deep reasoning and logical responses.
● Low Latency: Optimized for use in Google Colab environments with GPU acceleration.
● Automated Audio Handling: Built-in JavaScript integration for direct browser-based
recording.
## Requirements & Setup
To run this project, you will need to install the following dependencies:
pip install openai-whisper google-generativeai gTTS
### Configuration
This project requires a Google Cloud API Key to access the Gemini model. For security, do not
hardcode your API key. In Google Colab, it is recommended to use the "Secrets" (UserData)
feature:
1. Open the Secrets tab in Colab (key icon).
2. Add a new secret named GOOGLE_API_KEY with your personal key.
3. Enable notebook access for this secret.
## Technical Architecture
The core logic is structured to maintain a clean data pipeline, ensuring that audio buffers are
correctly processed into tensors for Whisper and that the LLM response is streamed for a better
user experience.

Component      |  Technology              |  Role
=======================================================================================
Transcription  |  Whisper (Small/Medium)  |  Converts audio bytes to text.
Reasoning      |  Gemini 1.5 Pro          |  Processes logic and generates answers.
Synthesis      |  gTTS                    |  Converts text back to natural speech.
Interface      |  IPython/JS              |  Handles microphone input and audio output.

## How to Use
1. Open the .ipynb notebook in Google Colab.
2. Ensure the runtime is set to GPU (T4 or better) for faster Whisper processing.
3. Run all cells to initialize the models.
4. Execute the voice assistant cell and follow the prompts to record your question.
Note: This project was developed as part of a technical exploration into B2B automation and
data optimization.
