# Dobby File Summarizer

Dobby File Summarizer is a web application that allows users to upload documents (PDF, DOCX, or TXT) and receive concise summaries, either as a paragraph or as bullet points. The summarization is powered by an AI model via the Fireworks API.

## Features

- **File Upload:** Supports PDF, DOCX, and plain text files.
- **Summarization Modes:** Choose between a single-paragraph summary or bullet-point summary.
- **Modern UI:** Responsive and clean interface.
- **AI-Powered:** Uses the Fireworks AI API for high-quality document summarization.

## Project Structure

```
summarizer-app/
│
├── package.json
├── backend/
│   ├── .env
│   ├── package.json
│   └── server.js
└── frontend/
    ├── app.js
    ├── index.html
    ├── logor.svg
    └── style.css
```

- **backend/**: Node.js Express server that handles summarization requests and communicates with the Fireworks API.
- **frontend/**: Static files for the web interface (HTML, CSS, JS, and assets).

## Setup Instructions

### Prerequisites

- [Node.js](https://nodejs.org/) (v16+ recommended)
- [npm](https://www.npmjs.com/)

### 1. Clone the Repository

```sh
git clone https://github.com/DOREGO-dev/sentient-summarizer
cd d
```

### 2. Install Backend Dependencies

```sh
cd backend
npm install
```

### 3. Set Up API Key

- The backend uses a Fireworks AI API key.
- By default, the key is in [`backend/server.js`](backend/server.js) as `API_KEY`.
- As this is for testing,you can find it in the server.js but for security and future purpose.It is recommended to hardoded it in server.js as 'API_KEY' while it is being stored in .env

### 4. Start the Backend Server

```sh
npm start
```

- The server will run on port `5000` by default.

### 5. Open the Frontend

- The backend serves the frontend automatically.
- Visit [http://localhost:5000](http://localhost:5000) in your browser.

## Usage

1. **Upload a file:** Click the file input and select a PDF, DOCX, or TXT file.
2. **Choose summary mode:** Select either "One Paragraph" or "Bullet Points".
3. **Click "Summarize":** The summary will appear below.

## File Details

- [`frontend/index.html`](frontend/index.html): Main HTML page, includes file input, mode selector, and output area.
- [`frontend/app.js`](frontend/app.js): Handles file reading (PDF, DOCX, TXT), sends text to backend, and displays summary.
- [`frontend/style.css`](frontend/style.css): Responsive and modern styling.
- [`backend/server.js`](backend/server.js): Express server, serves frontend, handles `/summarize` POST endpoint, communicates with Fireworks API.
- [`backend/package.json`](backend/package.json): Backend dependencies and scripts.
- [`package.json`](package.json): Root-level dependencies (not used for backend).

## Supported File Types

- **PDF:** Uses [PDF.js](https://mozilla.github.io/pdf.js/) in the browser to extract text.
- **DOCX:** Uses [Mammoth.js](https://github.com/mwilliamson/mammoth.js) (must be included if you want DOCX support).
- **TXT:** Plain text files.

## Customization

- **API Model:** The model used is set in [`backend/server.js`](backend/server.js) as `MODEL`. You can change this to another Fireworks model if desired.
- **Frontend Assets:** Replace `logor.svg` with your own logo if needed.


## Troubleshooting

- **CORS Issues:** The backend enables CORS for development.
- **API Errors:** Check the backend console for error messages if summarization fails.
- **File Type Not Supported:** Only PDF, DOCX, and TXT are supported.



---

**Made by Dee Figure using Express, Fireworks AI.
