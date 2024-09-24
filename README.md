# Speaker Detection

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation and Setup](#installation-and-setup)
- [Usage](#usage)
- [Future Improvements](#future-improvements)

## Project Overview
**Speaker Detection** is a tool that allows users to upload audio files, associate them with a speaker, and train the system to recognize that speaker in future audio samples. The project uses **SpeechBrain/ECAPA**[https://huggingface.co/speechbrain/spkrec-ecapa-voxceleb] for embedding generation and **Qdrant vector database** for efficient speaker recognition via cosine similarity.

The project consists of two main functionalities:
1. **Speaker Upload Tab:** Users can upload audio samples and name the speakers. These samples are preprocessed, and embeddings are generated and stored in the Qdrant vector database for future comparisons.
2. **Speaker Detect Tab:** Users can upload an audio file to detect the speaker by comparing the embeddings of the uploaded file with the existing ones using cosine similarity.

## Features
- Upload and train with multiple speaker audio files.
- Efficient speaker recognition using cosine similarity.
- Fast processing of audio embeddings via SpeechBrain/ECAPA model.
- Storage and retrieval of embeddings using Qdrant vector database.
- User-friendly interface built with **Gradio**.
- Easy setup with **Docker** and **FastAPI** backend integration.

## Technologies Used
- **Gradio**: For creating the user interface.
- **FastAPI**: As the backend framework to handle API requests.
- **SpeechBrain/ECAPA**: For generating speaker embeddings from audio files.
- **Qdrant**: Vector database for storing and retrieving speaker embeddings.
- **Docker**: Containerization for easy setup and deployment.
- **Cosine Similarity**: Used for comparing audio embeddings to detect speakers.

## Installation and Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/vaibhavsingh-materialplus/SpeakerDetection.git
   ```

2. **Build and Start the Docker Containers**
   Make sure you have Docker and Docker Compose installed.

   ```bash
   docker-compose build
   docker-compose up
   ```

3. **Access the Application**
   - **Qdrant Database**: `http://localhost:6333`
   - **Backend (FastAPI)**: `http://localhost:8000`
   - **User Interface (Gradio)**: `http://localhost:7860`

## Usage

1. **Speaker Upload Tab**:  
   - Upload audio files of the speaker you want to train.
   - Enter the speaker's name.
   - Once the audio is processed, embeddings will be stored in the Qdrant database.

2. **Speaker Detect Tab**:  
   - Upload an audio file for detection.
   - The system will find the most similar embeddings from the Qdrant database and display the best match.

## Future Improvements
- Add support for more speaker embedding models.
- Improve the UI with more detailed feedback during training and detection.
- Optimize processing speed for large datasets.
- Add real-time speaker detection functionality.
