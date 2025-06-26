Colour naming game
# Color Game: Gameplay Scenarios and Options

## Overview
This game is a web-based color recognition and reaction game. The player is shown a color and hears a spoken color name. 
The goal is to quickly decide if the spoken color matches the displayed color and respond accordingly. 
The game tracks your score, total games played, and provides audio feedback.

---

## Gameplay Scenarios

### 1. Standard Play
- **Start Game:**
  - Click the "Start Game" button to begin a new round.
  - A color is displayed on the screen, and a color name is spoken (audio file plays).
- **Player Response:**
  - If the spoken color matches the displayed color, press the `Enter` key.
  - If the spoken color does NOT match the displayed color, press the `Space` key.
- **Scoring:**
  - Correct answer: +1 point, "You were right" audio plays.
  - Incorrect answer: No penalty, "Wrong" audio plays.
- **Game Progression:**
  - After each answer, the next round starts automatically after a delay (see Delay Options below).
  - The game tracks your score, total games played, and displays your score percentage.

### 2. Delay Options (Settings)
- **Delay Between Rounds:**
  - Below the Start Game button, select the delay between rounds: 5, 10, or 20 seconds.
  - The selected delay is saved in a browser cookie and persists across sessions.
  - Changing the delay takes effect immediately for subsequent rounds.

### 3. Automated Testing Mode
- **TEST Checkbox:**
  - Enable the "TEST" checkbox to activate automated testing.
  - In TEST mode, the game will automatically submit a random answer (Enter or Space) every 5 seconds.
  - Useful for stress-testing, demo, or automated play scenarios.
  - Disable the checkbox to return to manual play.

### 4. Statistics and History
- **Score and Total Games:**
  - The UI displays your current score, total games played, and score percentage.
- **Game History:**
  - The backend tracks a history of each round, including:
    - Displayed color
    - Spoken color
    - User input
    - Result (correct/wrong)
    - Score and percentage at that round
- **Reset Game:**
  - Use the reset option to clear your score and history (total games played may also reset, depending on implementation).

### 5. Audio Feedback
- **Color Sounds:**
  - Each color has a corresponding spoken name audio file (e.g., "modra.mp3" for blue).
  - After each round, the correct color's audio can be played for feedback.
- **Result Sounds:**
  - "You were right.mp3" for correct answers.
  - "Wrong.mp3" for incorrect answers.

---

## Game Logic Details
- **Color Pool:**
  - The game uses 5 colors: red, magenta (pink), blue, green, yellow.
  - Each color is mapped to both a display color and a spoken name (in Slovenian).
- **Randomization:**
  - Each round, the displayed color is chosen randomly.
  - The spoken color is either the same (for a correct round) or a different random color (for an incorrect round).
- **Answer Checking:**
  - The backend checks if the user's input matches the correct response for the round.
  - Score and statistics are updated accordingly.

---

## Technical Notes
- **Settings Persistence:**
  - Delay settings are stored in cookies and loaded on page refresh.
- **Audio Files:**
  - All audio files are served from the `/static` directory.
- **Javascript Functions:**
  - `/start_game`: Starts a new round.
  - `/check_answer`: Submits the user's answer and returns result/score.
  - `/play_sound`: Returns the filename for result audio.
  - `/play_random_color_sound`: Returns the filename for the spoken color audio.
  - `/set_settings` and `/settings`: Manage delay settings.
  - `/reset_game`: Resets the game state.
  - `/game_history`: Returns the full game history.
  - `/total_games`: Returns total games played and score percentage.

---

## Example Playthrough
1. User selects a 10-second delay and starts the game.
2. The screen shows a blue color, and the audio says "modra" (blue).
3. User presses `Enter` (correct), score increases, "You were right" audio plays.
4. Next round: screen shows green, audio says "rdeča" (red).
5. User presses `Space` (correct), score increases, "You were right" audio plays.
6. User enables TEST mode; the game now submits random answers every 5 seconds.
7. User disables TEST mode to resume manual play.
8. User checks statistics and resets the game as desired.

---

## Troubleshooting
- If audio does not play, ensure your browser allows autoplay and the audio files exist in the `static` directory.
- If settings do not persist, check your browser's cookie settings.


