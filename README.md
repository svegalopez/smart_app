# Video Analysis Service

This project provides a comprehensive solution for video analysis, enabling users to upload videos, extract transcripts and OCR (Optical Character Recognition) data, and interact with the processed data by asking questions. It utilizes Node.js, Express, Multer for handling file uploads, crypto for generating unique keys, worker threads for processing tasks in the background, and the OpenAI API for generating responses based on the video content analysis.

## Features

- **Video Uploads**: Users can upload videos, which are then processed in the background.
- **Transcription and OCR**: The system extracts audio for transcription and performs OCR to detect text in video frames.
- **Interactive Querying**: After processing, users can ask questions about the video content, receiving answers generated by OpenAI's model.
- **Worker Threads**: Utilizes worker threads for heavy lifting tasks like video processing, ensuring the main server remains responsive.
- **Secure and Unique Access**: Each video upload is associated with a unique key, ensuring secure and isolated access to the processed data.

## Getting Started

### Prerequisites

- Node.js (v14 or newer recommended)
- ffmpeg (for video and audio processing)
- An OpenAI API key for using GPT models

### Installation

1. Clone the repository to your local machine:

   ```sh
   git clone https://your-repository-link-here.git
   ```

2. Navigate to the project directory:

   ```sh
   cd video-analysis-service
   ```

3. Install NPM packages:

   ```sh
   npm install
   ```

4. Set up your environment variables:
   - Rename `.env.example` to `.env`
   - Populate `OPENAI_API_KEY` with your OpenAI API key

### Running the Server

1. Start the server with:

   ```sh
   npm start
   ```

2. The server will start, and by default, it listens on port 5078. You can access it by navigating to `http://localhost:5078` in your browser.

## Start the client

`cd client && npm run dev`

## Instructions & Demo

Demo can be found [here](https://20240401t145522-dot-smart-app-419018.uc.r.appspot.com/).

1. Upload a video
2. Wait until the video is done processing
3. Ask anything about the video's content

## Usage

### Uploading a Video

- Send a `POST` request to `/upload` with the video file in the form data under the key `video`.
- The response will be a unique key associated with your video upload.

### Checking Video Processing Status

- To check the status of the video processing, send a `GET` request to `/video/:key`, replacing `:key` with your unique video key.
- If processing is complete, the response will include data about the video.

### Asking Questions About the Video

- After processing, you can ask questions by sending a `POST` request to `/completions/:key`, including a JSON body with your question. For example:
  ```json
  {
    "question": "What is the first step I need to take in order to build the app?"
  }
  ```

## Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Contact

Your Name - [@Code\_\_Head](https://twitter.com/Code__Head)

---

This README provides a general overview and setup instructions for the project. Adjustments may be necessary to accommodate specific setup or operational nuances of your environment.
