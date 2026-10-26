# SKIPPY SAFE HTML Prototype Test Plan

## Functional

- fresh run initializes correctly
- each area can be opened
- evidence appears only after inspection
- resolved hazards remain resolved after changing areas
- Skippy damage persists
- damaged subsystem changes a later available action
- refresh restores saved state
- restart clears saved state
- final readiness reflects unresolved state

## Adversarial student behavior

Test whether a player can:

- click randomly and still win
- always oppose Skippy
- always agree with Skippy
- inspect nothing and reach the ending
- authorize every unsafe action and still open the lab
- repeatedly click the same action to duplicate evidence
- reload to erase a consequence
- manipulate localStorage into an impossible state
- deliberately damage Skippy for entertainment
- select every apparent problem without distinguishing safe/ambiguous conditions
- bypass the reasoning interaction
- trigger final readiness before meaningful investigation

## BranchPoint quality checks

- does the player have to use evidence?
- is at least one Skippy statement correct?
- does at least one wrong decision create a scientifically defensible consequence?
- does the consequence teach the human hazard?
- does earlier state change later play?
- does the game avoid "Correct / Incorrect" as its main feedback?
- is the reading load appropriate for grades 7–9?
- does the experience feel like a laboratory problem rather than a quiz?
