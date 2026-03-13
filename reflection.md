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

A: Whenever it comes to deciding whether a bug is really fixed, I would try to manually input as many numbers as I can to see if there aren't any problems. As said before in Part 2, I had believed that the problem of inputting a number between a range was fixed, however, I had found 1 bug when I had inputted the highest number of a range. This shows that even if it may seem like the program is correct, there may be always a tiny error somewhere that it hard to notice. 

A test that I was trying to fix was the scoring system of the guessing game. After altering the codes slightly such as a wrong answer would actually accumulate the score, I had managed to pass the pytests after the AI had explained the errors. 

Additionally, there was a bug that I had managed to notice. First of all, the attempt counter was able to decrement in number whenever there wasn't anything inputted at all. After making some edits to the with assistance from Claude, I retested it through the streamlit, and it was successfully not able to become a negative number of attempts. Here is where it still becomes interesting. After testing the code more after fixing 1 mistake in the game, it immediately led to another mistake that I noticed within the game. The game incorrectly displays the number of attempts because when you start playing the game at 'Normal' difficulty, when you put in your first number, the attempt number doesn't decrease at all. The game still works, but the number of attempts aren't displayed correctly. This allowed my to help better find out fixes that allows the game to look cleaner with the use of AI. 

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

A: I believe that the reason why the secret number kept changing was due to the number changing types several times. Based on the attempt count, the secret number would change from an int into a string, and you are essentially trying to compare an int with a string which would cause major problems, due the types not matching. Allowing the secret number to stay as it is throughout the entire game would keep the game consistent. 

If I was trying to explain Streamlit reruns and session states, I would say that with the guessing game provided as an example, each time you are inputting a random number to try to see what the correct number is, the program reruns itself yet keeps the saved data of what the secret number is for example. The session state stays the same after each rerun in order to make the game playable. The secret number would stay the same, and the attempt count would also be saved (why we are able to decrement by 1 each time we guess). 

The change that I had made was to fully keep the secret number as an int or to put it simply, prevent it from changing types each time. It would allow the guesses to be properly compared with the secret number in order to provide whether or not you are guessing too high or low.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

Whenever it comes to projects, I would try to always look through the code and see whether or not I believe where errors can be possibly be happening. While you consistently document your possible errors, this is where AI can be helpful in identifying them. With some great context to ask the AI tool, the AI is able to consistently identify a solution to your problem and quickly speed up the debugging process. I didn't know how strong utilizing Claude AI would be during this project because it was able to quickly identify where the errors in your program was, and once I see some of the recommended changes, it allowed me to realize in great detail why or why not this is a needed change. It allowed me to think more logically on bugs in coding. While there may be some instances where the AI tool can sometimes provide code that doesn't do what you hoped it would, it allows to think more strategically in a way on how you are able to provide good enough context on the issue.
