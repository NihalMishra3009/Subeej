# Subeej AI

Subeej AI is an agriculture intelligence platform built to help users make practical decisions around crop selection, seed choice, soil suitability, field conditions, and yield guidance. It combines a web interface, dataset-driven recommendation logic, and an LLM-powered assistant to deliver responses that are more useful than a generic chatbot.

The application is designed for agriculture-focused conversations. Instead of only generating text, it interprets user intent, extracts field details, grounds responses in available data, and returns actionable guidance through a structured workflow.

## What This Project Does

- Recommends crops and seeds based on field and location context
- Checks soil and season suitability for farming decisions
- Supports agriculture chat workflows with grounded responses
- Provides field and image-related intelligence features
- Uses local LLM serving with Ollama and supports optional Mistral API integration

## Core Highlights

- Built with Next.js, React, and TypeScript
- Agriculture-focused conversational assistant
- Dataset-backed recommendation pipeline
- Modular API and library structure
- Local-first LLM support through Ollama

## Tech Stack

### Frontend

- Next.js
- React
- TypeScript
- Tailwind CSS
- Recharts
- Leaflet
- Three.js

### AI and Backend Logic

- Ollama for local model serving
- Optional Mistral API fallback/provider support
- Custom recommendation engine in `lib/`
- Python utilities for training and data-processing workflows

## How It Works

1. The user interacts with the web interface.
2. The backend identifies the user intent such as crop recommendation, soil suitability, or seed guidance.
3. The system extracts useful field details from the prompt.
4. Dataset context and rule-based logic are combined with the LLM call.
5. The application returns a grounded answer with better structure and relevance.

## Project Structure

```text
Subeej-demo/
├─ components/            Reusable UI blocks for chat, maps, dashboards, and field views
├─ data/
│  └─ source/             Agriculture dataset used for recommendation grounding
├─ lib/                   Core business logic, LLM client, prompts, and recommendation engine
├─ outputs/               Ollama model definition and model-related generated assets
├─ pages/                 Next.js pages and API routes
│  └─ api/                Server-side endpoints for chat, recommendations, and analysis
├─ public/                Static assets such as maps and generated CSS
├─ scripts/               Development, build, export, and training helper scripts
├─ seed-intelligence-ai/  Python-side AI pipeline, training, vector store, and RAG utilities
├─ styles/                Global styling
├─ .env.local.example     Example environment configuration
├─ launch-subeej.cmd      Windows launcher for the packaged app
├─ package.json           Node scripts and dependency manifest
└─ README.md              Project overview and setup guide
```

## Main Directories Explained

### `pages/`

Contains the app routes and API endpoints. This is the entry point for the web UI and server-side request handling.

### `components/`

Contains reusable frontend UI components such as chat panels, maps, cards, charts, and layout elements.

### `lib/`

Contains the main application logic, including:

- LLM provider integration
- prompt construction
- recommendation logic
- dataset grounding
- chat orchestration

### `scripts/`

Contains support scripts for:

- development startup
- clean builds
- training data preparation
- Ollama export workflows

### `seed-intelligence-ai/`

Contains the Python-side experimentation and AI pipeline, including dataset loading, training helpers, vector store logic, and retrieval-related utilities.

## Local Setup

### Prerequisites

- Node.js installed
- npm installed
- Ollama installed if you want local model inference

### Installation

```bash
npm install
```

### Environment Setup

Create a local environment file from the example:

```bash
cp .env.local.example .env.local
```

Then update values as needed for your setup.

### Run in Development

```bash
npm run dev
```

### Run Production Build

```bash
npm run build
npm run start
```

## Environment Notes

The project supports two LLM execution styles:

- Ollama for local model execution
- Mistral API for optional cloud-based inference

Typical environment values include:

- `LLM_PROVIDER`
- `OLLAMA_BASE_URL`
- `OLLAMA_MODEL`
- `MISTRAL_API_KEY`
- `MISTRAL_MODEL`

## Repository Notes

- Large generated files are excluded from GitHub
- Local model binaries such as `.gguf` files are not committed
- `.env.local` is ignored to avoid leaking local secrets
- The repository is structured for source code, not packaged binary distribution

## Summary

Subeej AI is a structured agriculture decision-support system, not just a chatbot. It combines a modern web app, recommendation logic, and LLM-based reasoning to give users more relevant and grounded farming guidance.
