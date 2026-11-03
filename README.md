# Voice Agent with Groq and Edge TTS

A Python voice-assistant project with two interaction modes: a local microphone-based application and a Streamlit web interface. Groq provides language-model responses; the web interface also uses Groq Whisper for speech transcription and Microsoft Edge TTS for spoken responses.

## Applications

| File | Purpose |
|---|---|
| main.py | Local microphone and speaker-based voice assistant |
| app.py | Streamlit interface with audio recording, transcription, chat, and browser playback |
| agent.py | Groq chat-completion helper |
| voice_agent.py / test_tts.py | Supporting voice and TTS utilities |

## Features

- Microphone input for the local assistant.
- Text chat and recorded-audio input in the Streamlit interface.
- Speech-to-text through Groq Whisper (whisper-large-v3) in the web app.
- LLM responses through Groq-hosted Llama models.
- Speech output through Microsoft Edge TTS.
- Conversation history during the active Streamlit session.

## Requirements

- Python 3.10+
- Groq API key
- Microphone and speaker for local voice mode
- Windows is recommended for the local audio workflow; browser mode depends on Streamlit audio support.

## Setup

1. Clone the repository:

```bash
git clone https://github.com/M-Abdullah-Shahzad/1st-voice-agent.git
cd 1st-voice-agent
```

2. Create and activate a virtual environment:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

3. Install dependencies:

```bash
python -m pip install -r requirements.txt
```

4. Copy .env.example to .env and set GROQ_API_KEY:

```env
GROQ_API_KEY=your_groq_api_key_here
```

## Run

Local microphone assistant:

```bash
python main.py
```

Streamlit web interface:

```bash
streamlit run app.py
```

## Current limitations

- The web interface currently requests English transcription.
- Conversation history is stored in Streamlit session state and is not a persistent chat database.
- The web interface uses a fixed English neural TTS voice.
- Microphone permissions, audio drivers, and browser playback support vary by operating system.
- External Groq and Edge TTS services require network access.

## Security

Keep .env private. Never commit API keys, access tokens, or personal audio recordings. Review external speech and LLM provider data-handling terms before sending sensitive audio.

## License

No license is currently declared. Contact the repository owner before redistributing this project.