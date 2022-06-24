# HOG
Game involving two players and some die
In Hog, two players alternate turns trying to be the first to end a turn with at least 100 total points. On each turn, the current player chooses some number of dice to roll, up to 10. That player's score for the turn is the sum of the dice outcomes. See detailed rules below

## To play  
Run in terminal:
```
python3 hog_gui.py
```

To play against computer automated strategy, run in terminal:
```
python3 hog_gui.py -f
```

## Rules  
To spice up the game, we will play with some special rules:

Pig Out. If any of the dice outcomes is a 1, the current player's score for the turn is 1.

Example 1: The current player rolls 7 dice, 5 of which are 1's. They score 1 point for the turn.
Example 2: The current player rolls 4 dice, all of which are 3's. Since Pig Out did not occur, they score 12 points for the turn.
Free Bacon. A player who chooses to roll zero dice scores one more than the minimum of of the ones and tens digit of the opponent's score

Example 1: The opponent has 10 points, and the current player chooses to roll zero dice. The minimum of 0 and 1 is 0, so the current player gains 1 point
Example 2: The opponent has 39 points, and the current player chooses to roll zero dice. The minimum of 3 and 9 is 3, so the current player gains 4 points
Swine Swap. After points for the turn are added to the current player's score, if the current and other player's scores share any digits in the same place value, the scores are swapped.

Note: a 0 at the beginning of a number does not count. This includes the 0 in the tens place of 5, the hundreds place of 23, and the ones place of 0. However, a 0 at the end of a number does count, so 20 and 30 are a swap.

Example 1: The current player has a total score of 41 and the opponent has 83. The current player rolls one dice with value 2. The player's new score is 43, and the opponent's score is 83. The players' scores both have a 3 in the one's place, so the scores are swapped.
Example 2: The current player has a total score of 41 and the opponent has 52. The current player rolls two dice with total value 10. The player's new score is 51, and the opponent's score is 52. The players' scores both have a 5 in the ten's place, so the scores are swapped.
Example 3 The current player has a total score of 1 and the opponent has 2. The current player rolls one dice with value 6. The player's new score is 8, and the opponent's score is 2. The players' scores have no digits in common, as leading 0s do not count as digits, so the scores are not swapped.
Example 4 The current player has a total score of 99 and the opponent has 14. The current player rolls three dice that total 18. The player's new score is 117, and the opponent's score is 14. The players' scores have 1 in common in the ten's place, so the scores are swapped.
Example 5 The current player has a total score of 0 and the opponent has 0. The current player rolls three dice that total 20. The player's new score is 20, and the opponent's score is 0. The players' scores have no digits in common (as we assume 0 has no digits), so the scores are not swapped
