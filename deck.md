class: center middle

# Hi :-)

---

# Towards a Theory of Test-Driven Design
Jonathan Berger, 2015

Mobile Central Europe, Warsaw

---

## Who Am I?

- @jonathanpberger
- ~30 agile projects since 2008
- design, code, pm
- interested in agile practice for design

---
name: who-are-you

## Who are you?
Show of hands:

--
- Designer?

--
- Developer?

-- 
- What else?

---

## What it says on the tin

> Years ago, Developers had problems and devised Agile techniques to address them. Today, Desingers face similar problems. Can we adopt similar techniques? In this talk, we’ll explore what automated testing might look like for design. What would it look like to have a more defined definition of “done” for design? What if designers could refactor with impunity? We’ll explore testing possibilities for Visual design, User Experience design, and front-end engineering, and try to build a testing pyramid for design.

---

# The Plan
- foo
- bar
- baz

---
class: center, middle, inverse
# Problems

---

## Designers have Problems

--

- Who's had to refactor a mess of CSS?
- Who's had unintended design changes (especially in responsive designs) lead to regressions?
- Who's had trouble defining "done" for a design problem?

---

## Developers had similar problems

--

and so devised
.em[automated testing techniques]
to protect their work.

---

## What might automated testing look like for design?


--

- What would it look like to have a more defined definition of "done" for design?
- What if designers could refactor with impunity?

---

# The Solution: TDD for Design

--

In this talk we'll explore

## possible testing-based solutions

for

- Visual design,
- User Experience design, and
- front-end engineering,

--

and
## try to build a testing pyramid for design.

---
class: interlude

# Interlude: Why Do I Care?

---

class: interlude
## origin story

---

class: interlude
## background on this talk: tried to give it before, but wasn't ready

---

class: interlude
## What is design?

(people ask "did you design that shirt?")

---

class: interlude
# </EndInterlude>

---

So...

# What is TDD?

---

## TDD: History

<!-- TODO: EXPAND THIS -->

- "rediscovered" by Kent Beck
-  mainframe era
- XP Explained - modern history

<http://www.quora.com/Why-does-Kent-Beck-refer-to-the-rediscovery-of-test-driven-development>
<http://derekbarber.ca/blog/2012/03/27/why-test-driven-development/>

---

# TDD: Benefits

> Kent Beck, who is credited with having developed or 'rediscovered'[1] the technique, stated in 2003 that TDD encourages simple designs and inspires confidence.[2] -<http://en.wikipedia.org/wiki/Test-driven_development>


---

## Benefits of TDD

> - It gives me **confidence** that my code does what I think it does

> - It confers the **ability to refactor** code without the fear that I have broken something

> - It encourages a testable, and hence **modular, design**

> - The **tests describe the behaviour** of the code

[Paul Wilson](http://www.neo.com/2014/03/20/the-many-faces-of-test-driven-development)

---

## TDD Technique
- Red
- Green
- Refactor

---

# A TDD example: Hamazon.com

---

!["images/hamazon_item_page.png"]

---

**Let's say we're Pair Programming...**

---

Our story is

**`User should be able to add Item to Shopping Cart`**

---

## Gherkin

looks a lot like regular English, but with a few magic words:

- **"Given",** 
- **"When",** 
- **"And",** 
- **"Then".**

---

### The Test

    Given I'm a logged-in User
    
    When I go to the Item Page
    
    And I tap the "Add Item to Cart" button
    
    Then I should see the Cart Inventory increment
    
    And I should see the Cart Sub-Total increment
    
    And I should see the Warehouse Inventory decrement

---

- readable by the computer
- each line will fail or pass individually.

---

### run the test. Red! What happens?
.right-column[
.green[`Given I'm a logged-in User`]


.green[`When I go to the Item Page`]


.red[`And I tap the "Add Item to Cart" button`]
]

???

- (Let's say by this point we've already written the User login system, so that line goes green.) 
- (...And let's say we've already written the Item Page, so that line goes green.) 
- (there is no "Add Item to Cart" button, so that should fail.) 

---
# make it green
- go into the part of the codebase which has front-end HTML views, 
- find the Item Page, and 
- add `<button>Add Item to Cart</button>`. 

---

*That's it.* 

???
No mucking with the database. The button isn't hooked up to anything. All we're trying to do is make the test pass, line by line.

---

run the test again:
`Given I'm a logged-in User`...GREEN!
`When I go to the Item Page`...GREEN!
`And I tap the "Add Item to Cart" button`...now that'll be green too!
`Then I should see the Cart Inventory increment` will fail. 

---

wire the `<button>` you just made in the front-end view up to the database, so that the Cart Inventory increments. 
  
---
  
Then we'll run the test again, the `Cart Inventory` line will pass, then next line (`Cart Sub-Total`) will fail, you'll make it pass, etc. etc. 

---

In this manner, the whole feature will be written according to a plain-Engish User Story that anyone can read—including a non-technical Product Manager or client stakeholder—without any over-engineering or extra work.

---

### Running Suite


???
Now here's the fun part. Remember how we said we already built the User Login system and the Item Page? Those features will have tests too. In fact, close to 100% of the codebase is under test. So now that we've TDD'd a new feature and it's test is green, we'll run the entire Test Suite—every test that's been written to date. We already know that our feature works on its own, but now we'll get to see whether it integrates with the rest of the software.


---



We'll kick off the full test run, and it'll take a few minutes to run all the tests. Now's a great time to get up, stretch our legs, grab a drink, maybe play a game of ping pong. When we return, the test suite is red! It turns out that when we decremented Warehouse Inventory, we broke part of the warehouse management system that had already been written. Now we'll go fix our code (writing additional tests as necessary) and repeat the process until the test suite is green. Once suite is green, we can push our code to production with confidence that the software will act as expected. In this manner, we mitigate technical risks and let deployment be a purely business decision.


---
class: interlude
# <Interlude>: TDD & Pairing

---

class: interlude
## Ping Pong Pairing
- How does it work?
- how would TDD help Design Pairing?

---

class: interlude
# </End Interlude>

---

# What is Test-Driven Design?
- benefits
- technique

---

# Pyramid Scheming

---

## Dev Testing Pyramid
- 1 ("Functional") Acceptance test
- 10 Integration tests
- 100 Unit tests

or

UI
Service
Unit

---

## Design Testing Pyramid

- Assert Design Decisions (cactus)
- Control Regressions (green_onion)
- Safely refactor bloated CSS (CSS Racionator)
- Enforce Code Conventions (CSS Lint)
- Enforce personas (persona_dot_yml)
- Enforce Styleguide-Driven Development (style_cop)


---


## Pyramid of types of design

what is it?, what do we usually call it?, how do we usually deliver it?, how could we test it?
concept / visual language / metaphor (IA?)
UX / wires

CSS
expression: final app

---

# recap
- foo 
- bar
- baz

---

# ways forward
- CI for design
- Design Testing Pyramid
- Gherkin-driven mockups
- style-guide driven design


---

# Thanks!

- <http://jonathanpberger.com/talks>
- Say hi on twitter at `@jonathanpberger`
- or `jonathanpberger` on github, gmail, forrst, etc...

---

