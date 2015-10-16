Coding Challenge came from DevDraft.

Turn-based 2 player game.
There are 3 positive integers in the start.
Each player on their turn chooses one number and replaces it with the average of the other two numbers,
rounding down if it is not an integer.
Players are not allowed to change the number if the average of the other two numbers would yield the same result.
A player loses if there are no valid moves available on their turn.

You are playing against an AI, which already has all of the moves predicted.
The only hope you have is to choose whether or not you go first or second.

Given the values of the 3 integers, determine whether or not you will be going first or second in order to win.

The user will input:
1) How many rounds of games we are analyzing (Between 1 and 50)
2) Groups of 3 integers separated by spaces (and lines) representing each of those rounds.

Output should be First or Second corresponding to each of the rounds.
