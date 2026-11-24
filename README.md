# Jarvis Assistant

A personal, locally-run voice assistant for Windows, built in Python. Say **"Hey Jarvis"** and talk to it hands-free. Most of the processing happens on your own computer.

## Features

- **Wake word:** "Hey Jarvis" detection using openWakeWord
- **Speech-to-text:** OpenAI Whisper, running locally
- **Local AI:** Ollama models for conversation (llama3.1), technical questions (qwen2.5-coder) and vision (llava), with an optional Gemini backend
- **Text-to-speech:** pyttsx3
- **Holographic GUI:** a Three.js interface (via pywebview) with state-based colors for sleeping, listening, thinking and speaking
- **Voice recognition:** only responds to commands from the enrolled owner's voice
- **Plugin skills:** each ability is a separate file in `skills/`, loaded dynamically
- **Runs in the background:** starts automatically with Windows

## Skills

Apps and websites, calculator and unit conversion, notes, shopping list, timers, recurring reminders, weather, news briefing, translation, file search, volume and brightness control, media control, system control, screen awareness, memory (remembers facts you tell it), and Gmail, Calendar and Contacts integration.

## Google integration

Jarvis can connect to the user's own Google account through OAuth, only when the user signs in and grants permission. It uses:

- **Gmail:** read unread emails, send emails (with spoken confirmation before sending), and reply to, archive or delete emails by voice
- **Google Calendar:** read and add events
- **Google Contacts:** look up names, emails and phone numbers so commands can use names instead of addresses

Google user data is used only to carry out commands the user gives. It is processed locally and never collected, sold, shared with third parties, or used for advertising or AI training. The sign-in token is stored only on the user's own computer. See [PRIVACY.md](PRIVACY.md).

## Tech stack

Python, Ollama, Whisper, openWakeWord, pyttsx3, pywebview, Three.js, Google Gmail / Calendar / People APIs.

## Setup (overview)

1. Install Python and [Ollama](https://ollama.com), then pull the models (`llama3.1`, `qwen2.5-coder`, `llava`).
2. Create a virtual environment and install the dependencies from `requirements.txt`.
3. Add your own API keys to `secrets.json` (not included in this repo).
4. Create your own Google Cloud OAuth credentials if you want Gmail, Calendar and Contacts features.
5. Run `python Assistant.py`. On first launch, Jarvis walks you through voice enrollment.

## Project structure

```
Assistant.py       main loop: wake word, listening, LLM routing, speech
jarvis_gui.py      pywebview wrapper and JS-Python bridge
jarvis_ui.html     holographic Three.js interface
skill_loader.py    loads skills dynamically
skills/            one file per ability
```

## Status

Personal project, actively developed.

## Author

Arth Vaghela, B.Tech CSE, Navrachana University, Vadodara.
Contact: arthvaghela545@gmail.com
