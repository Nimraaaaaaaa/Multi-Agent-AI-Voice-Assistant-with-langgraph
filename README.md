#  JARVIS AI Multi-Agent Voice Assistant (LangGraph)

A JARVIS-inspired voice assistant powered by a **LangGraph multi-agent system**. It can greet users using facial recognition, open applications and websites, send emails, and remember conversations.

**UI:** A black glowing orb with a waveform — using a distinctive ember-colored accent instead of the commonly used blue.

**Author:** Nimra Abdulhaq

## Project Structure

```text
jarvis-ai/
├── backend/
│   ├── main.py
│   ├── config.py
│   ├── agents/
│   │   ├── router_agent.py
│   │   ├── email_agent.py
│   │   ├── app_launcher_agent.py
│   │   └── general_agent.py
│   └── core/
│       ├── state.py
│       ├── graph.py
│       ├── stt.py
│       ├── tts.py
│       └── face_greet.py
├── frontend/
│   ├── index.html
│   ├── style.css
│   └── script.js
├── known_faces/
├── requirements.txt
└── .env.example
```

## Step 1 — Create a Virtual Environment

```bash
python -m venv venv
```

**Windows:**
```bash
venv\Scripts\activate
```

**Mac/Linux:**
```bash
source venv/bin/activate
```

## Step 2 — Install Dependencies

```bash
pip install -r requirements.txt
```

The `face_recognition` library requires compilation because it depends on `dlib`.

**Windows:** Install CMake and the Visual Studio **Desktop development with C++** workload, then run:

```bash
pip install cmake dlib face_recognition
```

**Mac:**
```bash
brew install cmake
pip install dlib face_recognition
```

**Linux:**
```bash
sudo apt install cmake build-essential
```

### If PyAudio Installation Fails

**Windows:**
```bash
pip install pipwin
pipwin install pyaudio
```

**Mac:**
```bash
brew install portaudio
pip install pyaudio
```

**Linux:**
```bash
sudo apt install python3-pyaudio
```

## Step 3 — Configure Environment Variables

Copy `.env.example` and save the copy as `.env`.

Add your Anthropic API key, preferred name, and Gmail App Password to the appropriate environment variables.

To generate a Gmail App Password, enable **2-Step Verification** in your Google Account and open the **App Passwords** section.

Keep your `.env` file private. Never upload your API keys or email credentials to GitHub.

## Step 4 — Add Your Photo

Place your photo inside the `known_faces/` directory.

For example:

```text
known_faces/nimra.jpg
```

The filename determines the name used in the greeting.

## Step 5 — Run the Project

```bash
python -m backend.main
```

The application will check the camera and open the web interface in your browser.

Open the following URL if it does not open automatically:

`http://127.0.0.1:5050`

Click the glowing orb to start speaking, or use the text input box below it.

## Try These Commands

- "Open Chrome"
- "Open YouTube"
- "Open my email"
- "Email Nimra with subject job update and body interview tomorrow"
- "How are you?"

## Customization

- **Add new applications:** Update `APP_COMMANDS` in `backend/agents/app_launcher_agent.py`.
- **Add new contacts:** Update `CONTACTS` in `backend/agents/email_agent.py`.
- **Change the orb color:** Modify `--accent-ember` in `frontend/style.css`.
- **Use offline speech recognition:** Replace the `speech_recognition` implementation in `backend/core/stt.py` with Vosk.

## Tech Stack

- **AI Orchestration:** LangGraph
- **Language Model:** Claude (Anthropic)
- **Backend:** Flask-SocketIO
- **Speech Recognition:** Speech-to-Text (STT)
- **Voice Output:** Text-to-Speech (TTS)
- **Facial Recognition:** `face_recognition`
- **Frontend:** HTML, CSS, JavaScript

**Developed by Nimra Abdulhaq**
