# OpenAI Realtime Translation App

A real-time one-way translation application using the OpenAI Realtime API. This project demonstrates how to build a multilingual translation system where a speaker talks in one language and listeners can hear live translations in their selected languages.

## Features

- 🎤 Real-time speech input from speaker
- 🌍 Multi-language translation support (French, Spanish, English, Mandarin, Tagalog)
- 🎧 Live audio output for listeners
- 🔄 Voice Activity Detection (VAD) or manual push-to-talk
- 🔊 Real-time audio streaming with WebSockets

## How It Works

1. **Speaker App**: Captures audio input and sends it to OpenAI Realtime API for translation
2. **Mirror Server**: Handles audio streaming between speaker and listener components
3. **Listener App**: Receives translated audio streams and plays them in the selected language

## Prerequisites

- Node.js (v16 or higher)
- OpenAI API key with Realtime API access
- Modern browser with microphone support

## Setup

1. **Clone this repository**
   ```bash
   git clone <your-repo-url>
   cd openai-realtime-translation
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   - Copy `.env.example` to `.env`
   - Add your OpenAI API key:
     ```
     REACT_APP_OPENAI_API_KEY=your_api_key_here
     ```

4. **Start the mirror server**
   ```bash
   node mirror-server/mirror-server.mjs
   ```

5. **Start the React app** (in a new terminal)
   ```bash
   npm start
   ```

## Usage

1. **Open the applications**:
   - Speaker App: `http://localhost:3000/speaker`
   - Listener App: `http://localhost:3000/listener`

2. **Connect as Speaker**:
   - Click "Connect" in the Speaker App
   - Choose VAD or Manual mode
   - Start speaking (pause to allow translation processing)

3. **Listen in Different Languages**:
   - Open the Listener App
   - Select your preferred language from the dropdown
   - Hear live translations

## Supported Languages

- French
- Spanish  
- English
- Mandarin Chinese
- Tagalog

## Technical Details

- **Frontend**: React with TypeScript
- **Audio Processing**: Web Audio API with custom worklets
- **Real-time Communication**: WebSockets with Socket.IO
- **Translation**: OpenAI Realtime API
- **Audio Streaming**: Custom mirror server for multi-listener support

## Important Notes

- The model is turn-based, so speakers should pause briefly between phrases
- Requires microphone permissions in the browser
- Best performance with clear audio input
- Internet connection required for API calls

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is based on the OpenAI Cookbook examples.
