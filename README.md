# Intelligrader

An AI tool that grades AP History short-answer questions. Students paste in their answer and get a score and feedback in seconds. It was used by AP History classes at Eleanor Roosevelt High School.

**Live app:** https://intelligrader.vercel.app · **API docs:** https://peral.one/docs

## How it works
```
Next.js website  →  FastAPI server (Docker, AWS)  →  fine-tuned grading model
```
The website sends the student's answer to our API, which runs a fine-tuned language model and returns a score and feedback.

**Model:** we fine-tuned Gemma-3 for grading. The live site currently runs a fine-tuned Qwen model while the Gemma-3 version is being rolled out.

## Highlights
- Requests wait in a queue, so the server stays stable under load instead of crashing
- Models are listed in one config file, so we can switch models without changing code
- Every push to `main` deploys automatically and checks that the server is healthy

## What's in this repo
- `api/`: the FastAPI server and grading logic
- `deploy/`: Docker, nginx, and the GitHub Actions deploy workflow
- `frontend/`: how the website calls the API

## Tech
Python · FastAPI · llama.cpp · Docker · nginx · GitHub Actions · AWS Lightsail · Next.js · Vercel

## Team
Praneet Dumpa · Devom Brahmbhatt · Satya Lakkaraju · Jacob Wu · Preston Lee
