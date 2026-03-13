# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

A: There were many problems that were easily noticeable with the game after running it the first time. As soon as you were going to make your first guess on normal difficulty I had chosen a number within the correct range of possible values, but it first did not decrease my attempt limit from 7 to 6. It had stayed at 7. After guessing more times, the attempt limit began to go down, however, it had constantly kept saying that the value was lower than that. I had put 1 as one of the values, and it still said that it was lower which is impossible because 1 should be the lowest value you are able to input. I was even able to plug in a number that is out of the range from 1-100.

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

A: The AI tool that I had used for this project was Claude Code. The first error of the program that I have decided to test out was to fix the New Game button of the game. The problem was that the new game button wasn't working at all. I had asked the AI tool to see if it was able to identify the problem/solutions for this problem. It had suggested that the underlying cause was that even though it may seem like the attempt counter was being reset, it does not set the player to be considered "playing". This would lead to the game being frozen. We would also have to change the secret number because we are trying to start a fresh game. After testing out the game by playing the game through the streamlit itself, the game would successfully reset with a new secret number being changed. 

Another error of the game was that the game was providing incorrect messages where you were trying to input a value for the game. The first thing I wanted to make sure the AI tool can fix was to be sure that the number you are trying to input in the game was in the correct range of values whether it be from 1-100 (default). Asking the AI tool, the first change that it first wants to change is to use proper variables instead of fixed values. Instead of just using 1 as a number, it changed to "low" as it is a cleaner variable to use. It had also added an elif statement for that you were only able to input a number that is between the (low, high) interval. This was a successful fix because I had tested through the streamlit, and I had tested inputting a number like 1000, and it delivers a message saying that it is not in the correct range of values. There was only one thing that the AI tool did not consider. When I had tested for when the ranges are 1-100, I inputted 100 into the game and it had provided me with a "GO HIGHER" which is not supposed to happen. 

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
