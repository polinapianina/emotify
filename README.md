![Lint-free](https://github.com/software-students-spring2025/5-final-five-timers-club/actions/workflows/lint.yml/badge.svg?branch=main)
![Machine Learning Client CI](https://github.com/software-students-spring2025/5-final-five-timers-club/actions/workflows/ml-client-ci.yml/badge.svg?branch=main)
![Web App CI](https://github.com/software-students-spring2025/5-final-five-timers-club/actions/workflows/webapp-ci.yml/badge.svg?branch=main)

# Emotify: Emotion Detection and Music Recommendation

## Description

This project is an application that detects a user's emotions from their facial expressions and recommends music based on their expression. The system processes webcam images to identify emotions and uses Spotify's API to play songs that match the detected emotion.

## Team Members

[Oluwapelumi Adesiyan](https://github.com/oadesiyan) <br />
[Polina Belova](https://github.com/polinapianina) <br />
[Gabriella Codrington](https://github.com/gabriella-codrington) <br />
[Maya Mabry](https://github.com/mam10023) <br />

## Overview of System Architecture

This system consists of three interconnected components:

- **Machine Learning Client** - Captures webcam images, detects facial emotions using DeepFace, and requests matching songs from Spotify's API.
- **Web Application** - A Flask-based frontend that lets users capture images, trigger emotion detection, and view their emotion history with recommended songs.
- **MongoDB Database** - Stores emotion detection history and song recommendations for user tracking and review.

## Prerequisites

Ensure the following tools are installed:

- Python 3.11+
- MongoDB
- Spotify Developer Account (for API access)
- Docker and Docker Compose

## 🗂️ Project Structure

```
.
├── web-app/ # Flask frontend
│ ├── app.py # Main web app logic
│ ├── auth.py # User authentication
│ ├── requirements.txt
│ ├── templates/ # HTML templates
│ ├── Dockerfile
│ └── static/ # CSS and JavaScript
├── machine-learning/ # Emotion detection service
│ ├── face_recog.py # Facial emotion detection
│ ├── get_playlist.py # Spotify API integration
│ └── requirements.txt
│ ├── Dockerfile
└── README.md # You are here
└── docker-compose.yml
```

## 🔐 Environment Configuration

Create a `.env` file in your project root folder with the following variables:

```
CLIENT_ID=your_client_ID
CLIENT_SECRET=your_client_secret
MONGO_URI=mongodb+srv://username:password@cluster.example.mongodb.net/?retryWrites=true&w=majority
SECRET_KEY=your_secret_key
```

## Development Setup

### Local Development with Docker

1. Clone the repository:

   ```
   git clone https://github.com/software-students-spring2025/5-final-five-timers-club.git
   cd 5-final-five-timers-club
   ```

2. Create environment variables file:
   cp .env.example .env

3. Edit the `.env` file with your development configuration.

4. Build and start the containers using Docker Compose:
   docker-compose up -d --build

5. The application will be running at http://127.0.0.1:5001

6. To stop the containers:
   docker-compose down

## Running Unit Tests

Make sure to install pytest

```
pip install pytest
cd web-app
pytest tests
```

```
cd machine-learning
pytest tests
```

## Features

- **User Authentication** - Register and login to track your history
- **Facial Emotion Detection** - Detects emotions from webcam images (happy, sad, angry, fearful, surprised, disgusted, neutral)
- **Music Recommendations** - Suggests songs from Spotify based on your detected emotion
- **History** - Review your past detected emotions and recommended songs

## Technologies Used

- **Flask** - Python web framework
- **DeepFace** - Deep learning facial recognition and emotion detection
- **Spotify Web API** - Music recommendation engine
- **MongoDB** - Database for emotion and song history
- **Flask-Login** - User authentication system
- **OpenCV** - Image processing
