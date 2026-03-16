# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [ ] Describe the game's purpose.
- [ ] Detail which bugs you found.
- [ ] Explain what fixes you applied.

## 📸 Demo

- [ ] [Insert a screenshot of your fixed, winning game here]

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]

## 📝 Document Your Experience

This project investigates bugs in an AI-generated number guessing game built with Streamlit.

### Bugs Found
- Hint logic was reversed and gave incorrect guidance.
- The secret number comparison behaved inconsistently because it was sometimes converted into a string.
- Starting a new game did not fully reset the game state.
- The displayed guessing range did not always match the selected difficulty.

### Fixes Applied
- Refactored helper functions into `logic_utils.py`.
- Corrected the high/low hint logic.
- Removed the inconsistent secret-number type conversion.
- Fixed the new game reset logic to reset attempts, score, history, and status correctly.

## Purpose
This project is a Streamlit number guessing game designed to help students debug AI-generated code. The goal was to investigate broken behavior, identify reproducible bugs, fix the logic, and document how AI suggestions were evaluated.

## Reproducible Bugs Found
1. **Hint logic was reversed**
   - Expected: if the guess is too high, the game should tell the player to go lower.
   - Actual: the game returned "Too High" but displayed "Go HIGHER!".

2. **Secret number handling was inconsistent**
   - Expected: the secret number should always stay as an integer during comparison.
   - Actual: on some attempts, the code converted the secret number to a string, which could cause inconsistent comparison behavior.

3. **New game did not reset correctly**
   - Expected: starting a new game should reset attempts, score, history, and respect the selected difficulty range.
   - Actual: the new game logic only partially reset state and always used a 1–100 range.

4. **Displayed range text was incorrect**
   - Expected: the UI should display the current difficulty range.
   - Actual: it always said “Guess a number between 1 and 100” even when a different difficulty was selected.

## Fixes Applied
- Moved helper functions into `logic_utils.py`.
- Corrected hint logic in `check_guess()`.
- Removed inconsistent secret-number type conversion.
- Fixed new game reset logic to reset all game state values correctly.
- Updated the displayed range text to match the selected difficulty.

## Evidence of Debugging
I reviewed the app flow in `app.py` and the helper functions in `logic_utils.py` to trace how guesses were parsed, compared, and scored. I used this to identify where the incorrect hints, inconsistent secret handling, and reset issues were happening.

## Demo
[Insert screenshot of fixed winning game here]

## Pytest
[Insert screenshot of pytest results here if available]