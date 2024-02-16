---
{"dg-publish":true,"permalink":"/permanent/tdd-where-did-it-all-go-wrong-ian-cooper-dev-ternity-conference-highlights/","title":"🚀  TDD, Where Did It All Go Wrong (Ian Cooper)","tags":["🎥"],"created":"2024-02-16T17:31:01.873-06:00","updated":"2024-02-16T17:31:02.365-06:00"}
---

# 🚀  TDD, Where Did It All Go Wrong (Ian Cooper)

![cover|150](https://i.ytimg.com/vi/EZ05e7EMOLM/maxresdefault.jpg)
## Metadata
- Document Note: 
   **The Problem**
   - Some good developers don't want to write tests
   - We often write more test code than implementation code
   - Sometimes 2-3 times as much
   - We were slower when we wrote tests to deliver
   - We ended up breaking a lot of tests when we attempted to make changes
   - Often times these were the tests with a lot of mocks involved
   - The tests became an obstacle to change when we changed implementation details
   - Surely [[permanent/Martin Fowler\|Martin Fowler]] and [[permanent/Kent Beck\|Kent Beck]] were expecting refactors to occur without breaking tests
   - [[Fred George\|Fred George]] "If [[Extreme Programming\|Extreme Programming]] is good then lets turn the dial up to 11" 
   - [[Programmer Anarchy\|Programmer Anarchy]] fire anyone who is not a developer, let developers talk to customers, and write very small pieces of code called [[Microservice\|Microservice]]s that only have about 100 lines of code without tests because you're bound to get it right, and if it breaks we'll just throw it away
   - [[Test Driven Development\|TDD]] is something you do when you're scaling
   - Why is the [[Duct Tape Programmer\|Duct Tape Programmer]] winning?
   - He get's solutions out the door very fast
   - His engineering is rubbish but he gets all the credit from product
   - It's hard to maintain his code
   - When we return to our tests - because they are broken it is often difficult to understand their intent
   - Default to 'the best thing to do is just delete the test' if it's broken and we don't know why
   - We have large ATDD suites written in Fit or Gherkin SpecFlow etc.
   - They spend much of their life red
   - Customer never looked at it because they don't know, Is it red because it hasn't been implemented yet or is it red because it's broken?
   - Our ATDD suites are slow to run and increase the cost of the check-in dance
   - Broke your code flow process because of how long it took to take
   - Developers start ignoring red results
   - Developers don't want to write them
   - Because they can't see the value return on their effort
   [[permanent/David Heinemeier Hansson\|David Heinemeier Hansson]] wrote [TDD is dead. Long live testing.](https://dhh.dk/2014/tdd-is-dead-long-live-testing.html)
   His complaint is that I'm being forced by people
   [[Active Record Pattern\|Active Record Pattern]] people tell me this is no good, because I can't cleanly separate their domain object models from their testing framework code. I used to write my unit tests and they'd talk to the database and I was told that was wrong as well.
   He used to like [[Test Driven Development\|TDD]] when it first came out but now I'm constantly being told I'm doing it wrong so I'm giving up on [[Test Driven Development\|TDD]].
   
- URL: https://www.youtube.com/watch?v=EZ05e7EMOLM

## Highlights
#📫
>[!QUOTE]  
>if you find yourselfimplementing an IOC registration in yourtest something has gone horribly wrong ([View Highlight](https://read.readwise.io/read/01gzpsbcgy1b8t08j8byya58ms)) #✂️ 
{ #ref-523057271}


---
