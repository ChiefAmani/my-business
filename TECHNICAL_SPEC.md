# TECHNICAL_SPEC.md

## Project Overview
This project defines the core game code scope for a 2D joke game. It outlines the technical stack, file structure, and key dependencies required for development, building upon previous sprint's successful game development.

## Tech Stack
- Python==3.10.12
- pygame==2.6.1

## File Tree
```
.
|-- game/
|   |-- __init__.py
|   |-- main.py
|   |-- config.py
|   |-- assets/
|   |   |-- images/
|   |   |   |-- background.png
|   |   |-- sounds/
|   |   |   |-- laugh.wav
|   |-- data/
|   |   |-- jokes.json
|-- tests/
|   |-- __init__.py
|   |-- test_game.py
|-- requirements.txt
```

## API Endpoints
(No external API endpoints for this standalone game. Internal game logic functions are defined below.)

## Environment Variables
(No specific environment variables required for this project scope.)

## Dependencies
```
pygame==2.6.1
```

## Core Game Logic - Function Signatures

### game/main.py
- `def initialize_game():` -> Initializes Pygame, sets up display, loads assets.
- `def load_assets():` -> Loads images, sounds, and joke data.
- `def display_joke(joke_text: str):` -> Renders and displays a joke on screen.
- `def handle_input():` -> Processes user input (e.g., pressing a key to get next joke).
- `def game_loop():` -> Main game loop, handles events, updates game state, renders.

### game/config.py
- `SCREEN_WIDTH: int = 800`
- `SCREEN_HEIGHT: int = 600`
- `CAPTION: str = "Johnny Bravo Joke Game"`
- `JOKE_FILE: str = "data/jokes.json"`

### game/data/jokes.json
```json
[
  {
    "id": 1,
    "joke": "Why did the scarecrow win an award? Because he was outstanding in his field!"
  },
  {
    "id": 2,
    "joke": "What do you call a fake noodle? An impasta!"
  }
]
```

### tests/test_game.py
- `def test_load_jokes():` -> Tests if jokes are loaded correctly from `jokes.json`.
- `def test_display_joke_rendering():` -> (Mocked) Tests if joke text is rendered on screen without errors.