# TDD for Design Scratchpad

# ******************* Shower Notes

Where does TDD fit into Think -> Make -> Check

---

- "I code and design" => describe TDD workflow in dev, set up "I want this for design. What might that look like?"

- subj/obj => design pyramid

- ghost story benefit: declaritive testing benefit: ontological design story is told in code. This is probably the top of the pyramid

- think about how dev test Pyramid involves rendered results vs declarative statements. how much is a priori? in dev, unit tests are declarative, closest to math, closest to a priori. In Design, it may be inverted.

- use a geo font w/ lots of triangles

---

# ******************* From main file



---

# Software development had problems

- Sclerosis around processes and tools,
- Compulsive (CYA) documentation,
- Endless negotiation about targets and deliverables,
- A fixation on following an old plan in a new situation.

---


## Continuous Integration

the insight that great cost is not to write code; rather, the majority of technical cost lays in *maintaining* a codebase.


----

# 99 (Hypo)theses about Design Fears
not sure if this is part of the talk, a new version of the talk, or what. But I shuold go with it for a little while.
// maybe the dev part goes up in the bg on TDD, and the design parts can set up moving from TDD -> TDDesign

---

> "We believe [TYPE OF USER] has a problem [DOING THING]. We can help them with [OUR SOLUTION]. We'll know we're right if [CHANGE IN METRIC]."

---

We believe designers have a problem

*refactoring the messes of CSS that metastasize once a project gets past the early phases.*

We can help them with

## a tool that provides for refactoring CSS with impunity.

We'll know we're right

*if Latter-Day Stylesheets become less of a problem (we can test this on our own codebases).*

---

We believe designers suffer from

## unintended design regressions

(especially in responsive designs) when changes in one part of the codebase unexpectedly affect another.

We can help them with a tool that craws the whole app and announces if anything's changed.

---


We believe designers suffer from the

## *fear* of unintended design regressions,

never being 100% certain that new changes haven't broken old styling.

---


*We believe*

## designers have trouble defining "done", which makes it hard to set expectations, to communicate with teams, and to manage their own work.

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

# Ideal Workflow

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


# From TDD Lunch Talk

## The Pain
- Conversation started w/ numerical formatting: neg numbers red w/ parens, positive numbers w/ green, etc (cactus would fix this)
- layout broke w/ an experimental class leaking out to another DOM element, absolute positioning broke a page (GO would fix this)

---

## The Plan
- spike on a screenshotting tool wraith / GO (try graham's branch) / huxley and choose one
- put a screenshotting tool into a new Design build
- put the Design Build onto the CI board
- put Acknowledger page under screenshotting test
- report back to Automated Design Test Working Group

---

## Goals / Benefits

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

---

## Risks
- adding overhead to team flow

---

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

---

## TODO
- send Github image diffing to Interesting



---

---

<!-- not sure where this goes ; do we need to talk about storywriting? maybe storymapping?-->
# I.N.V.E.S.T.

- Independent: maybe?
- Negotiable: yes!
- Valuable: yes!
- Estimatable: in theory, yes
- Small: maybe?
- Testable: working on that now

---

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
