title: foo
name: bar

class: center, middle, inverse

**Hi :-)**

---

class: center, middle

# Towards a Theory of Test-Driven Design
Jonathan Berger, 2015

Mobile Central Europe Conf, Warsaw

---

class: center, middle, inverse

.small[
**or**]
***A Proposed program for Automated Testing in Design***

---


**Who Am I?**

- @jonathanpberger
- ~30 agile projects since 2008
- design, code, pm
- interested in agile practice for design

---

# What it says on the tin

.small[
> Years ago, Developers had problems and devised Agile techniques to address them. Today, Desingers face similar problems. Can we adopt similar techniques? In this talk, we’ll explore what automated testing might look like for design. What would it look like to have a more defined definition of “done” for design? What if designers could refactor with impunity? We’ll explore testing possibilities for Visual design, User Experience design, and front-end engineering, and try to build a testing pyramid for design.
]

---

# Designers have Problems

---

- Who's had to refactor a mess of CSS?
- Who's had unintended design changes (especially in responsive designs) lead to regressions?
- Who's had trouble defining "done" for a design problem?

---

## Developers had similar problems

---

**and so devised**
***automated testing techniques***
**to protect their work.**

---

class: center, middle, inverse


## What might automated testing look like for design?


---

**What would it look like to have a more defined definition of "done" for design?**

**What if designers could refactor with impunity?**


---

In this talk we'll explore testing possibilities for

- Visual design,
- User Experience design, and
- front-end engineering,

---

and
**try to build a testing pyramid for design.**

---
class: center, middle, inverse


***20 yrs ago***

---

## Software development had problems

- Sclerosis around processes and tools,
- Compulsive (CYA) documentation,
- Endless negotiation about targets and deliverables,
- A fixation on following an old plan in a new situation.

---

## What is design?

(people ask "did you design that shirt?")

---

## What is Test-Driven Development?
- benefits
- technique

---

### Benefits

Paul Wilson [says](http://www.neo.com/2014/03/20/the-many-faces-of-test-driven-development):

> For me, TDD's benefits are:

> - It gives me **confidence** that my code does what I think it does

> - It confers the **ability to refactor** code without the fear that I have broken something

> - It encourages a testable, and hence modular, **design**

> - The **tests describe the behaviour** of the code

---

### Technique
- Red
- Green
- Refactor

---

## What is Test-Driven Design?
- benefits
- technique

---

# Dev Testing Pyramid
- 1 ("Functional") Acceptance test
- 10 Integration tests
- 100 Unit tests

or

UI
Service
Unit

---

# Design Testing Pyramid

- Assert Design Decisions (cactus)
- Control Regressions (green_onion)
- Safely refactor bloated CSS (CSS Racionator)
- Enforce Code Conventions (CSS Lint)
- Enforce personas (persona_dot_yml)
- Enforce Styleguide-Driven Development (style_cop)


---

<!-- not sure where this goes -->
# I.N.V.E.S.T.

Independent: maybe?
Negotiable: yes!
Valuable: yes!
Estimatable: in theory, yes
Small: maybe?
Testable: working on that now

---

# 99 (Hypo)theses
not sure if this is part of the talk, a new version of the talk, or what. But I shuold go with it for a little while.

---

> "We believe [TYPE OF USER] has a problem [DOING THING]. We can help them with [OUR SOLUTION]. We'll know we're right if [CHANGE IN METRIC]."

---

We believe designers have a problem 

*refactoring the messes of CSS that metastasize once a project gets past the early phases.*

We can help them with 

*a tool that provides for refactoring CSS with impunity.*

We'll know we're right 

*if Latter-Day Stylesheets become less of a problem (we can test this on our own codebases).*

---

We believe designers suffer from unintended design regressions (especially in responsive designs) when changes in one part of the codebase unexpectedly affect another. We can help them with a tool that craws the whole app and announces if anything's changed.

---


We believe designers suffer from the *fear* of unintended design regressions, never being 100% certain that new changes haven't broken old styling.

---


*We believe*

designers have trouble defining "done", which makes it hard to set expectations, to communicate with teams, and to manage their own work. 

*We can fix this *

with a practice of Test-Driven Design, where "done" can be INVESTED up-front. 

*We'll know we're right*

if there're fewer client disapprovals, because expectations were better set up-front. We'll know we're right if life gets better for designers.

---


We believe developers lacked confidence that their code would continue to work in the face of a changing codebase. They fixed it by testing their code and running Continuous Integration tests. We know they're right because this is a growing practice among businesses and developers.

---


We believe developers suffered from an inability to safely refactor code for fear of breaking something. They fixed this with tests, and we know they're right because techniques like Red-Green-Refactor can become cornerstones of their practice.

<!-- 2 more: testable and hence modular, and "tests describe behavior" -->

---


We believe designers have a problem with the imprecision of the word "design". We can fix this by spreading a vocabulary with more subtle distinctions. We'll know we're right if expectations are better set because client and designer share a ubiquitous language.


---

# Pyramid of types of design

what is it?, what do we usually call it?, how do we usually deliver it?, how could we test it?
concept / visual language / metaphor (IA?)
UX / wires

CSS
expression: final app

---
# Notes

## Ideal Workflow

### VxD
- designer designs new user_profile/show page
- creates a "test": screenshot
- developer implements feature
- run tests
  - screenshoot each page
  - image diff each screenshot against last version or design_tests

- (if PASS then NOTHING HAPPENS)
- if FAIL then
  - stop the line (e.g. break the CI build)
  -

### FE
- refactor some CSS
- run tests: screenshots are image-diff'd
- FAIL! user_profile/show looks different
- Was this a desired difference?
  - if YES: bless this new screenshot. Does this imply a Design Changelog?
  - if NO: fix it

- stop the line (e.g. break the CI build)
- look at what broke, fix the CSS



### UX
- design something new
- run tests
- if PASS then NOTHING HAPPENS
- if FAIL then
  - stop the line (e.g. break the CI build)
  -





---

# Thanks!

- <http://jonathanpberger.com/talks>
- Say hi on twitter at `@jonathanpberger`
- or `jonathanpberger` on github, gmail, forrst, etc...

---

---
# Hi!

- I'm @jonathanpberger
- I use Git every day to make stuff at @pivotallabs
- My background is in philosophy and then design and now development


---
## Who are you?
Show of hands:

- Who's used any version control before?
- Who's used git before?
- Who uses the terminal regularly?



---
# The Plan
- 40m to Speed through a *ton* of material.
- Try to show actual use and common workflows. No time to be exhaustive
- This will be a live-coded technical talk.


---

- Act 1 - Solo Git & Heroku
- Act 2 - Team Git
- Act 3 - Setting-up, links to more

---


# What

# Why

# Experience so far


---

# Notes from UX Sketch Camp

- Talk -> never given

- how do I practice?

- New Idea...I dho'nt have practice

- Q: content tricky or stories?

- A: How do we know when design phase is done?

## Testing Pyramid
- 1 Acceptance test for every
- 10 Intergration tests, for every
- 100 Unit tests

Test driven engineering

What's the design version of the testing pyramid?
Sketching?
Common language of done
holy grail
looking at design as a series of experiments
more than just pretty pictures

75% spot-on
10% crazy
15% eh

---

# ways forward
- CI for design
- Design Testing Pyramid
- Gherkin-driven mockups

---

## The Pain
- Conversation started w/ numerical formatting: neg numbers red w/ parens, positive numbers w/ green, etc (cactus would fix this)
- layout broke w/ an experimental class leaking out to another DOM element, absolute positioning broke a page (GO would fix this)

## The Plan
- spike on a screenshotting tool wraith / GO (try graham's branch) / huxley and choose one
- put a screenshotting tool into a new Design build
- put the Design Build onto the CI board
- put Acknowledger page under screenshotting test
- report back to Automated Design Test Working Group

# Goals / Benefits

Automated design testing can address a number of design pains, e.g.:

- Enforce code conventions using linting tools: [idiomatic.js][], [idiomatic-css][]
- documenting the design of an app at a state in time
- help make cucumber / feature tests more focused, help devs write them more like a real person and go through the actual workflows. "Cuke it like a human (GH)"
- safely refactoring horrible CSS: [css-ratiocinator][]
- help enforce the (live) style guide
- keep the DOM clean and semantic
- enforce good stylesheet structure / best practices
- ensure modules are implemented w/ proper DOM
- explicitly assert design decisions

# Risks
- adding overhead to team flow

## Errata
- How to connect to (live?) styleguide?
- Changing data will break tests. We'll need fixtures. Create a separate "design test" build?
- How to run separately? How often? Separate rake task?
- what about interactions? we're mostly talking about testing static design
- user testing: [ethn.io][]
- what are the outside-in patterns in design testing?
- Are we talking about TDDing? What does TDDing look like for design?
- how can we assert / protect the grid system? the type system?
- how to deal w/ dynamic, js-driving DOM? what about ember, angular, etc.?
- "Catastrophic cactus test": assert against total failure, e.g. cards collapsing to 0 width.
- TDD w/ GO: create a mock in the browser w/ firebug, use it as the reference for GO to run against

## TODO
- send Github image diffing to Interesting

# Resources
[capybara-accessible]: https://github.com/Casecommons/capybara-accessible
[css-ratiocinator]: https://github.com/begriffs/css-ratiocinator
[csste.st]: http://csste.st/tools/
[ethn.io]: http://ethn.io
[green_onion]: http://intridea.github.io/green_onion/
[GrabThemAll]: https://addons.mozilla.org/en-US/firefox/addon/grab-them-all/
[huxley]: https://github.com/facebook/huxley
[idiomatic-css]:https://github.com/necolas/idiomatic-css
[idiomatic.js]: https://github.com/rwaldron/idiomatic.js
[persona_dot_yml]: https://github.com/jonathanpberger/persona_dot_yml
[symilaa]: http://rubygems.org/gems/symilaa
[wraith]: https://github.com/BBC-News/wraith
