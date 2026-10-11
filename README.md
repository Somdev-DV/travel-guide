# AI Travel Guide – Multilingual Audio Companion

An AI-powered travel guide that provides informative descriptions of famous Indian tourist destinations and converts them into audio guides in multiple languages. Users can explore historical landmarks, choose the level of detail, select a language and voice, and listen to AI-generated explanations.

## 🌐 Live Demo

**Live Website:** https://graceful-arithmetic-27c89f.netlify.app/

## ✨ Features

- **Explore Tourist Destinations:** Browse popular Indian landmarks, including the Taj Mahal, Red Fort, Gateway of India, Hawa Mahal, Golden Temple, and Mysore Palace.
- **AI-Generated Descriptions:** Generate engaging explanations using Google Gemini.
- **Summary and Detailed Modes:** Choose between a concise overview and a more detailed historical explanation.
- **Multilingual Support:** Generate guides in English, Hindi, Tamil, and Telugu.
- **Voice Selection:** Select a male or female voice for supported languages.
- **Text-to-Speech:** Convert generated descriptions into audio using the Murf API.
- **Audio Playback:** Listen to the generated guide directly on the website.
- **Transcript Display:** Read the generated description alongside the audio.

## 🛠️ Technologies Used

| Component | Technologies |
|---|---|
| Frontend | HTML, JavaScript, Tailwind CSS |
| Backend | Python, Flask |
| AI Text Generation | Google Gemini API |
| Text-to-Speech | Murf API |
| API Communication | REST API, JSON |
| Backend Hosting | Render |
| Frontend Hosting | Netlify |
| Version Control | Git, GitHub |

## 📁 Project Structure

```text
travel-guide/
├── Backend/
│   ├── app.py
│   └── requirements.txt
├── Frontend/
│   ├── index.html
│   └── index.js
└── README.md
```

## ⚙️ How It Works

1. The user selects a tourist destination.
2. The user chooses the description type, language, and voice.
3. The frontend sends a POST request to the Flask backend.
4. Google Gemini generates a destination description.
5. The backend sends the generated text to the Murf text-to-speech API.
6. The backend returns the description and audio data to the frontend.
7. The website displays the transcript and plays the generated audio.

## 🚀 Run the Project Locally

### Prerequisites

- Python 3.10 or later
- A Google Gemini API key
- A Murf API key
- Git (optional)

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd travel-guide
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your actual GitHub repository URL.

### 2. Install Backend Dependencies

Open a terminal in the project directory and run:

```bash
cd Backend
pip install -r requirements.txt
```

### 3. Configure API Keys

Set the following environment variables before starting the backend.

**Windows PowerShell:**

```powershell
$env:GEMINI_API_KEY="your_gemini_api_key"
$env:MURF_API_KEY="your_murf_api_key"
```

Replace the placeholder values with your own API keys. Never commit actual keys to GitHub.

### 4. Start the Backend

From the `Backend` directory, run:

```bash
python app.py
```

The backend should start on:

```text
http://127.0.0.1:5000
```

### 5. Start the Frontend

Open `Frontend/index.html` in your browser or serve the `Frontend` directory using a local static web server.

For local testing, ensure the API URL in `Frontend/index.js` points to the local Flask endpoint:

```javascript
const GENERATE_AUDIO_GUIDE_API_URL =
  "http://127.0.0.1:5000/generate-audio-guide";
```

For the deployed website, use the production Render API URL instead.

## 🔌 API Endpoint

### Generate Audio Guide

**Endpoint:** `/generate-audio-guide`

**Method:** `POST`

**Request Body:**

```json
{
  "place": "Taj Mahal",
  "answerType": "Summary",
  "language": "English",
  "voiceId": "Matthew",
  "locale": "en-US"
}
```

**Response:** A JSON object containing:

- `description`: AI-generated tourist guide text.
- `audioBase64`: Base64-encoded MP3 audio.

## ☁️ Deployment

The application is deployed using separate hosting services.

- **Frontend:** Netlify
- **Backend:** Render
- **AI text generation:** Google Gemini API
- **Audio generation:** Murf API

The frontend communicates with the deployed Flask backend through an HTTPS API request.

## 🔐 Security

- Store API keys in environment variables.
- Do not commit API keys, passwords, or `.env` files to GitHub.
- Configure production secrets through the hosting provider's environment settings.
- Use valid, rotated API keys and monitor API usage and quotas.

## 🔮 Future Enhancements

- Add more tourist destinations and countries.
- Integrate maps, routes, and nearby attractions.
- Add audio download functionality.
- Improve error handling and loading indicators.
- Add user accounts and personalized travel recommendations.
- Optimize audio delivery for large responses.

## 👨‍💻 Author

Developed as an AI-powered travel companion project using web technologies, generative AI, and text-to-speech.

## 📄 License

Choose an appropriate open-source license before distributing or reusing this project. If no license is specified, the repository's default copyright protections apply.
