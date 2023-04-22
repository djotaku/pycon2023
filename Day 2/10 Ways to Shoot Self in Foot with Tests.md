# 10 Ways to Shoot Yourself in the Foot with Tests

## The 10 foot-guns

- It's better to have some tests than no tests.
- If it doesn't fail, it doesn't pass. For each test you write, make sure that if it's not working correctly (modify your code for a second) it actually fails
- Testing too many things - test one fact about a function or bit of code at a time (see talk's example of test_user_can_edit_their_own_book vs test_edit_book)
- unclear language - use decisive and explicit lanaguage
- the devil is in the details
- the tests are not isolated - you don't want the order in which the tests are run to affect the outcome
- improper test scope - see behavior test vs implementation test in the talk
- test doubles everywhere - eg mocks. What's bad is that test doubles == implementation. They aren't exactly the same as the real thing. The test double might not stay in sync with the thing it's mocking. Use with caution. Try to design the code so that a lot of it can be tested w/o the need of doubles. Use a fake - so that it behaves like what you're replacing. Test the fake by ocassionally testing against the real thing and making sure you get the same answer. Or let's say that you can't test everything against the database. So you do as much as you can with the fake, but pick the two most important tests and also run against the database.
- slow tests 
    - the bottleneck - this causes PRs to end up stacking up because we can't merge them until they pass the tests. This means we're either going to go too slow when it's critical time or the team will start skipping tests. 
    - the time bomb - be prepared to optimize. (Don't have to pre-optimize, but make sure it's not too hard to optimize) Tests need to be able to run in parallel - so make sure the tests are isolated.
    - the speaker is running the tests in watch mode - every time they make a change, they're running a subset of the tests that can finish in 3 seconds. This means they can quickly see if they have caused an issue and what caused it.
    - Instead of asking yourself how long does it take the test to run - ask how long does it take to catch a bug. See talk about the bug funnel - so that you're finding most of the bugs before you get to the CI
- wrong priorities 
    - speaker suggests priorities should be in this order:
        - maintainable
        - performance
        - strong

Tools
- pytest-watch
- pytest-testmon
- see others on the slides
