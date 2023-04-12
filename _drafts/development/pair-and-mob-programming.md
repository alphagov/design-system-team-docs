# Pair and mob programming

## Suggested principles for pairing

> Based on: https://gds.blog.gov.uk/2018/02/06/how-to-pair-program-effectively-in-6-steps/ and https://gist.github.com/jordanpoulton/607a8854673d9f22c696


- Book time in the calendar for the session (where this is possible - sometimes you just want to pick someone else's brain regarding a problem immediately).
- Make sure both parties are aware at the beginning of the session of what the problem you're trying to solve is. If one party has already started to work on the problem, they should talk their partner through the existing code first (or send it to them beforehand to look through).
- Make a plan at the beginning of the session of what you want to achieve.
- The driver:
   - Writes the code according to the navigator's instructions.
   - Asks questions wherever there is a lack of clarity.
   - Offers alternative solutions if they disagree with the navigator. Where there is disagreement, the navigator should be deferred to.
- The navigator:
   - Is responsible for what code should be written. This ensures that you are both communicating together as the navigator cannot write code without first explaining it to the driver.
   - Explains 'why' they have chosen the particular solution to this problem.
   - Looks out for mistakes.
   - Calls a halt if necessary to rethink where you are, where you want to get to and how to get there.
   - Outlines and notes down high level tasks / issues.
- Try to do all the work on just the one machine if possible. It can also be appropriate to go and do research on your own machine while the other person does something else on theirs but there's sometimes the risk that the pairing becomes less collaborative when done that way. But you should do what works!
- Use a timer and swap over every 30 or so mins - at this point, the driver pushes the code to the remote branch. Just "WIP" as commit message can be enough at this point as a [proper commit message](https://github.com/alphagov/design-system-team-docs/blob/master/development/commit-messages.md) is written when the commit is wrapped up.
- Remember to take breaks - pairing can feel more intense than working on your own.
- Give the person you're pairing with
  - Permission to make mistakes
  - Encouragement to experiment
  - Constructive feedback

## Tools for pairing remotely

We're going to try out Slack's tools as they are code editor agnostic.

## Draft: Suggested principles for mobbing

Mobbing can be particularly useful when you are:
- Starting on a large piece of work so the outline of the solution can be discussed and/or coded.
- Stuck on a particularly difficult problem that needs multiple pairs of eyes.

An example of successful mobbing:

_The whole thing felt super collaborative because everyone was engaged in solving the same problem. Every 5-8 minutes, we swapped roles, being careful not to shove someone into a role they weren’t keen to take on._

_We weren’t planning to mob forever, but by starting to rewrite the test code as a group, individual developers returning to the project later would be aware of its history and understand its design._

From https://gds.blog.gov.uk/2016/09/01/using-mob-programming-to-solve-a-problem/
