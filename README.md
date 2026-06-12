# AI-Powered Technical Interview Prepper (AI Proctor)

An advanced, AI-driven mock interview platform designed to help candidates prepare for technical interviews. The platform dynamically generates role-specific interview questions, supports both coding and conceptual questions, and provides real-time, comprehensive evaluation of the candidate's answers.

## 🚀 Features

- **Dynamic Question Generation**: Automatically generates interview questions tailored to the candidate's specific role (e.g., MERN Stack Developer) and experience level (e.g., Junior, Senior).
- **Coding & Conceptual Challenges**: Supports a mix of hands-on coding challenges and conceptual oral questions.
- **Adaptive Follow-up Questions**: Dynamically generates follow-up questions based on the candidate's previous answers and code quality.
- **Real-time Audio Transcription**: Uses OpenAI's Whisper model to transcribe verbal answers seamlessly.
- **AI-Powered Evaluation**: Analyzes candidate responses using Ollama (Mistral) to provide a Technical Score, Confidence Score, AI Feedback, and an Ideal Answer.
- **Live Proctoring & Analytics**: Integrates TensorFlow.js (COCO-SSD) for candidate monitoring and Chart.js for visualizing performance metrics.
- **Real-Time Communication**: Uses Socket.io for live syncing between the client and backend.

## 🛠️ Technology Stack

### Frontend
- **Framework**: React 19 + Vite
- **Styling**: Tailwind CSS + PostCSS
- **State Management**: Redux Toolkit
- **Code Editor**: Monaco Editor
- **Machine Learning**: TensorFlow.js (COCO-SSD)
- **Charts**: Chart.js & React-Chartjs-2
- **Authentication**: Google OAuth (@react-oauth/google) + JWT

### Backend (Node.js API)
- **Framework**: Node.js + Express
- **Database**: MongoDB (Mongoose)
- **Real-time**: Socket.io
- **Authentication**: JWT & Google Auth Library
- **File Uploads**: Multer

### AI Service (Python Microservice)
- **Framework**: FastAPI
- **LLM Engine**: Ollama (running `mistral` model)
- **Speech-to-Text**: OpenAI Whisper
- **Audio Processing**: Pydub & FFmpeg-Python

## 📁 Project Structure

```
.
├── frontend/             # React/Vite Frontend application
├── backend/              # Node.js/Express Main API server
├── ai-service/           # Python/FastAPI Microservice for AI evaluations and STT
├── start-all.bat         # Script to launch all services concurrently
└── for-first-time.bat    # Initial setup script
```

## ⚙️ Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v18 or higher)
- [Python](https://www.python.org/) (3.9 or higher)
- [MongoDB](https://www.mongodb.com/) (Local or Atlas)
- [Ollama](https://ollama.com/) (Must be installed and running on your machine)
- [FFmpeg](https://ffmpeg.org/) (Must be installed and added to your system's PATH)

### 1. Clone the repository
```bash
git clone <repository-url>
cd "ai interviewer prepper"
```

### 2. Install Dependencies

**Frontend:**
```bash
cd frontend
npm install
```

**Backend:**
```bash
cd backend
npm install
```

**AI Service:**
```bash
cd ai-service
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Setup Ollama
Make sure you have Ollama installed and pull the required Mistral model:
```bash
ollama run mistral
```

### 4. Environment Variables
You will need to set up `.env` files in each of the respective directories (`frontend`, `backend`, `ai-service`). 
- **Backend `.env`**: Needs MongoDB URI, JWT Secret, Google Client ID, Port, etc.
- **Frontend `.env`**: Needs Backend API URLs and Google Client ID.
- **AI-Service `.env`**: Needs `AI_SERVICE_PORT` (default 8000) and `OLLAMA_MODEL_NAME` (default mistral).

### 5. Run the Application
You can easily start the entire application (Frontend, Backend, AI-Service, and Ollama) using the provided batch script on Windows:

```cmd
start-all.bat
```

Alternatively, you can run them manually:
- **Backend**: `cd backend && npm run dev`
- **Frontend**: `cd frontend && npm run dev`
- **AI Service**: `cd ai-service && venv\Scripts\activate && python main.py`

## 📝 License
ISC License
