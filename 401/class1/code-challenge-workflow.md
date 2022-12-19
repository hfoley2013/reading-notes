# Python Data Structures & Algorithms Code Challenge Workflow

- Daily Setup:
  - Create a new folder under the `python` level, with the name of the code challenge
    - Each code challenge assignment identifies the branch name to use, for example 'find-maximum-value'
    - For clarity, create your folder with the same name, ensuring that it's `snake_cased`
    - i.e. For a challenge named 'find_maximum_value', create the folder:`code_challenges/find_maximum_value`
  - Code Challenge Implementation
    - Each code challenge requires a function be written, for example "find maximum value"
    - Name the actual challenge file with the name of the challenge, in `snake_case`
      - i.e. `find_maximum_value.py`
    - Reminder: Your challenge file will then need to require the data structure you're using to implement
      - i.e. `from linked_list.linked_list import LinkedList`
    - Your challenge function name is up to you, but name something sensible that communicates the function's purpose. Obvious is better than clever
      - i.e. `find_maximum_value(linked_list)`
  - Tests
    - Ensure there is a `tests` folder at the root of project.
      - i.e. a sibling of this document.
    - within it, a test file called `test_[challenge].py`
      - i.e. `tests/find_maximum_value.py`
      - Your test file would require the challenge file found in the directory above, which has your exported function
        - i.e. `from code_challenges.find_maximum_value import find_maximum_value`

## Whiteboarding

![Whiteboarding Image](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/assets/whiteboard-example.png)

* Process Example:
  * Step 1: You write down the problem domain as the interviewer reads the problem to you.
  * Step 2: You draw a picture of what that input will look like and write down what you think the output will be.
  * Step 1 Again: The interviewer corrects you: your proposed output is incorrect. You revisit the problem domain.
  * Step 2 Again: Now that you understand the problem better, you come up with a more representative visual.
  * Steps 2 And 3: You develop your algorithm. You show with arrows in your visual how you’ll transform the input into the output, and write down a bulleted list of steps as you go.
  * Step 4: You analyze the runtime and space complexity of the algorithm you just proposed, using big O notation.
  * Step 4.5: The interviewer asks you why you’ve chosen to use a particular data structure instead of some other choice, and how that impacts your runtime and space complexity. You reason through the use of that data structure vs. alternatives verbally with the interviewer, and decide your choice of data structure was good, and you’ll continue using it.
  * Step 5: You decide your algorithm has some ambiguity, so you start writing pseudocode that matches your algorithm.
  * Step “Oh No”: You realize which part of your algorithm was imprecise; there’s more going on in this problem than you realized. You go back to your visual and algorithm and try to work through how this new realization fits in.
  * Steps 2 And 3 And 4 Again: You figure out how you’ll work through this issue, and add that into your arrows and your bullet points. Since you’ve changed your approach, you also change your estimate of the runtime/space complexity.
  * Step 5 Again: You keep working through your pseudocode.
  * Step 6: You write out syntactically correct code that matches your pseudocode.
  * Step 7: You start stepping through your example input from Step 2, walking through your syntactically correct code line by line.
  Step “Oh No” Again: You realize as you step through that your code doesn’t actually generate the output that you expected.
  * Step 6 Again: You debug your code and get it working on your example input.
  * Step 4 Again: Since you changed your code while debugging, you re-analyze runtime/space complexity.
  * Step 6 Again: You finish your stepthrough on the example input, and it’s now generating the correct output.
  * Step 7, Continued: You list out test cases that you would want to test this program on.
  * Step 8: Whatever your interviewer says!
