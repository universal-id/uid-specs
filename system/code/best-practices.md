# 📋 Best practices

## ✅ Automated testing

Automated testing plays an important role as part of the overall implementation of system and components. It has the potential to add significant value to the implementation process and beyond, when done in a thoughtful and systematic manner.

### Goals

* Prevent breaks to integrity of the software system as a result of inevitably frequent changes.
  * Automate the verification of the system at all levels and end-to-end: Components, sub-components and integrated components
  * Enable diagnosis and fixing of issues locally (in the inner loop) before propagating to the builds (outer loop).
    * Logging and local debugging support
* Minimize maintenance by limiting the set of maintainable tests to the ones adding significant value.
  * Rule of thumb: If test breaks, it is likely that a relatively valuable scenario is broken
* Secondary goals:
  * Act as programmatic documentation of functionality at various levels
  * Add to developers' understanding of functionality as function of changes
    * Documented by test results
    * Documented test logs

### Requirements:

* Automated tests implemented for high value user and developer scenarios when possible.
* Logging of important test information.
  * In turn requires TestContext objects in tests.
* Implementation of test features inside product, forced only when required by high value scenario tests.

## 📐 Architecture and design

### Goals

* Lowered cost of discovering, understanding, communicating and manipulating functionality
  * For everyone (product, engineering)
  * At all levels (high level system, layers, components, sub-components
* Simple and familiar organization of functionality into system, layers and components
* Clear, concise and agreed-upon (consensus) language used to describe components and their inner workings (Functions, variables, etc).

### Requirements

* Use existing architecture and design frameworks when it makes sense.
* If something doesn't fit raise the issue early and drive arriving at consensus.
  * Efficiency achieved with help of those tasked with end-to-end understanding the curation of architecture, design and product vision.
