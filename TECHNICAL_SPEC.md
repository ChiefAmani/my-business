# TECHNICAL_SPEC.md

## Project Overview
A simple web-based "Guess the Number" game where a user tries to guess a randomly generated number within a specified range. The system provides feedback (too high, too low, correct) and tracks the number of attempts.

## Tech Stack
- fastapi==0.110.0
- pydantic==2.6.1

## File Tree
- backend/
  - main.py
  - requirements.txt

## API Endpoints
- Method: POST
- Path: /api/game/start
- Request body: { "min_number": int, "max_number": int }
- Response: { "game_id": str, "message": str }
- Auth: None

- Method: POST
- Path: /api/game/guess
- Request body: { "game_id": str, "guess": int }
- Response: { "message": str, "attempts": int, "is_correct": bool }
- Auth: None

## Environment Variables
None

## Dependencies
fastapi==0.110.0
pydantic==2.6.1
uvicorn==0.29.0
