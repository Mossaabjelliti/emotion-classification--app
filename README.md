# Emotion Classification API 🧠

> A Flask-based text emotion classification application with a browser interface, JSON API, confidence scores, and a configurable inference pipeline.

This project demonstrates how a machine-learning classifier can be wrapped in a usable web application instead of remaining only inside a notebook.

## What it does

The application accepts text and returns a predicted emotion together with model confidence. It also exposes application workflows for interacting with the classifier through a web interface and API endpoints.

The repository includes:

- Flask web application
- JSON/API responses
- reusable `EmotionClassifier` model wrapper
- emotion-label mapping
- configurable application/model settings
- CORS support for API consumers
- authentication scaffolding
- model loading and runtime inference
- deployment configuration for Render

## Architecture

```text
Client / Browser
       ↓
   Flask routes
       ↓
EmotionClassifier
       ↓
Trained emotion model
       ↓
Emotion + confidence
```

## Tech stack

| Layer | Technology |
|---|---|
| Language | Python |
| Web framework | Flask |
| Data processing | pandas / NumPy |
| Configuration | YAML |
| ML inference | Custom `EmotionClassifier` wrapper |
| API | Flask JSON endpoints |
| Deployment | Render configuration included |

## Repository structure

```text
├── app.py                 # Flask application and routes
├── model.py               # Emotion classifier abstraction
├── config.yaml            # Application/model configuration
├── emotion_mapping.json   # Model-label → emotion mapping
├── requirements.txt       # Python dependencies
├── render.yaml            # Render deployment configuration
└── templates/             # Web UI templates
```

## Running locally

### Requirements

- Python 3.x
- pip
- Git

### Installation

```bash
git clone https://github.com/Mossaabjelliti/emotion-classification--app.git
cd emotion-classification--app

python -m venv venv
```

Windows:

```bash
.\venv\Scripts\activate
```

Linux/macOS:

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the Flask application:

```bash
python app.py
```

## Security and production notes

Local runtime files such as logs, interaction data, user files, model artifacts, virtual environments, and IDE metadata are intentionally excluded from version control.

The application should be configured with a real `SECRET_KEY` in production rather than relying on the development fallback. Authentication credentials should never be committed to the repository.

## Current status

This is a portfolio project demonstrating ML inference integrated into a web application. Production hardening would include automated tests, stronger secret/configuration management, structured API documentation, model versioning, and observability.

## Roadmap

- [ ] Add unit tests for model inference and Flask routes
- [ ] Add API schema/OpenAPI documentation
- [ ] Move model artifact configuration fully into environment variables
- [ ] Add model/version metadata to predictions
- [ ] Add structured error handling
- [ ] Add CI for linting and tests
- [ ] Add a public demo URL when deployment is stable

## Author

**Mossaab Jelliti**

Software engineering, data science, and AI portfolio project.

- GitHub: [@Mossaabjelliti](https://github.com/Mossaabjelliti)
