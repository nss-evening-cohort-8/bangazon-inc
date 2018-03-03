String Calculator

The following is a TDD Kata- an exercise in coding, refactoring and test-first.
Before you start: 

    Try not to read ahead.
    Do one task at a time. The trick is to learn to work incrementally.
    Make sure you only test for correct inputs. there is no need to test for invalid inputs for this kata

String Calculator

    Create a simple String calculator with a method int Add(string numbers)
        - The method can take 0, 1 or 2 numbers, and will return their sum (for an empty string it will return 0) for example “” or “1” or “1,2”
        - Start with the simplest test case of an empty string and move to 1 and two numbers
        - Remember to solve things as simply as possible so that you force yourself to write tests you did not think about
        - Remember to refactor after each passing test
    Allow the Add method to handle an unknown amount of numbers
    Numbers bigger than 1000 should be ignored, so adding 2 + 1001  = 2
    Calling Add with a negative number will throw an exception “negatives not allowed” - and the negative that was passed.if there are multiple negatives, show all of them in the exception message 
