# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

When I first examined the game, several parts of the logic were behaving incorrectly. The hints were misleading because when a guess was too high the game sometimes told the player to go higher instead of lower. Another issue was that the secret number comparison behaved inconsistently because the code sometimes converted the secret number into a string instead of keeping it as an integer. I also noticed that starting a new game did not fully reset the game state and ignored the selected difficulty range. These issues made the game confusing and sometimes impossible to win.
---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

I used ChatGPT as my AI assistant while working on this project. One correct suggestion from the AI was identifying that the hint logic in the check_guess function was reversed. I verified this by reviewing the code and confirming that the message shown to the user did not match the outcome of the guess. One misleading suggestion from AI was that the score logic might be the main cause of the game breaking. After inspecting the code manually, I realized that the real problem was the secret number sometimes being converted to a string, which affected the comparison logic.
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

I verified that bugs were fixed by carefully reviewing the logic and tracing how values moved through the program. For example, I checked that the hint messages correctly matched the comparison between the guess and the secret number. I also reviewed how the new game button reset the session state variables to ensure that attempts, score, and history were cleared properly. AI helped me understand how the functions interacted, but I confirmed the fixes by reading the code and checking that the logic matched the expected behavior.
---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

Streamlit reruns the entire script every time the user interacts with the app, such as clicking a button. Because of this behavior, normal variables reset unless they are stored in st.session_state. Session state acts like memory for the app, allowing values such as the secret number, attempts, and score to persist between interactions. Without session state, the game would regenerate values every time the page updates.
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

One habit I want to reuse is carefully reviewing AI generated code instead of assuming it is correct. AI can help explain code and suggest fixes, but it still requires human judgment to verify whether those fixes actually solve the problem. Next time I work with AI on a coding task, I would test each suggestion step by step instead of trying to change many things at once. This project helped me realize that AI generated code should be treated as a starting point rather than a finished solution.