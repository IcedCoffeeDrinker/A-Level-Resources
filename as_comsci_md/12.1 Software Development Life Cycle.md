# 12.1 Software Development Life Cycle
=> Five Fundamental stages
=> Four common models combining those stages

## Stages
### Analysis
- Investigate issues and old systems (if existent)
- Define problem clearly and precisely
- Plan a solution
- Decide approach: bottom-up: start with small sub-problems
	- top-down: start broad (e.g. pseudocode) and refine down

### Design
- Plan data structures, algorithms and required variables
	- => use identifier tables

### Coding
- Decide on a suitable programming language
- Convert design (e.g. pseudocode) into code
- Debug until it works (compiles / doesn't crash)

### Testing
- write and perform tests
(Discussed later)

### Maintenance

## Program Development Life Cycle (PDLC)
=> Consists of many models that clearly define how the five steps of development are iterated over

most simple: (A circular flow) Analysis -> Design -> Coding -> Testing -> Maintenance -> (back to Analysis)

## Waterfall Model
(A linear flow with feedback loops: Analysis <-> Design <-> Coding <-> Testing <-> Maintenance)

### Principle:
- Starting with analysis, stages are completed one at a time
- Output from stage is input for the stage below
- more work might be required in the stage above, hence the loops

### Benefits:
- simple, clearly defined
- easy to manage, predictable outcomes for each stage
- works well for smaller projects
	- => requirements need to be well understood

### Drawbacks
- software not working until end
- not adaptable to changing requirements or new insights
- hard to measure progress, poor for long projects

## Iterative Model
### Principle
- start with a small subset of requirements
- after each full iteration add more requirements until system is completed

(Diagram showing progressive development: skateboard -> bicycle -> car)

### Benefits:
- early working project
	- => early risk identification
	- => Faster Feedback loop
- allows for parallel development
- testing for smaller program parts is easier

### Drawbacks
- only large projects really profit
	- => simple projects can't be subdivided
- Design issues, as requirements aren't clear from start
- Might need more resources

## Rapid Application Development (RAD) Model
(Diagram showing multiple versions and prototypes being developed in parallel and iteratively, e.g., v1.0, v2.9, v3.5, v1, v2)

### Principle
- uses minimal planning
- prototypes for modules are developed and integrated
- The stages of PDLC are iterated over fast and many times
- modules will be changed and refined during development

### Benefits:
- very adaptable to changing requirements
- Measurable progress
- Very productive when few people
- Reduces development time
	- => reusability of modules

### Drawbacks
- only works for systems that can be build in modules
- requires skillfull coders
- mainly suitable for scalable systems
- requires user involvement during development