# SKIPPY SAFE HTML Game Design

## Player fantasy

You are the Laboratory Safety Lead two minutes before students enter the room. Skippy has already begun "helping."

Your job is not to count violations. You must decide what matters, what can wait, what evidence you need, and when the laboratory is actually ready.

## Skippy's role

Skippy is:

- technically competent
- cheerful
- eager to begin
- sincere
- sometimes correct
- systematically weak at estimating risk

His recurring logic is:

> If something can probably work, there is no reason not to try it.

He should create pressure, not serve as the answer key.

## Core loop

```
EXPLORE
→ INSPECT
→ FIND EVIDENCE
→ DECIDE
→ CONSEQUENCE
→ UPDATE LAB / SKIPPY
→ CONTINUE OR REVISE
```

## Interaction model

The player moves among laboratory areas and interacts with visible objects.

Actions may include:

- inspect
- isolate
- move
- shut down
- request information
- check a label
- open an SDS excerpt
- ask Skippy for an observation
- authorize or reject a proposed action

The game should reveal only evidence the player actually investigates.

## Three-situation prototype

### 1. Entrance / eyewash

Visible:

- backpack partly blocks the central aisle
- cart sits near the eyewash
- exit path appears open

The backpack is a real hazard.

The cart is ambiguous until inspected. Inspection reveals that it is near the eyewash but not blocking access.

This teaches that the player is not simply hunting for every object that "looks wrong."

Skippy can be correct about the eyewash access.

### 2. Heating station

Visible:

- recently heated beaker
- burner is off
- no visible glow or steam

Skippy proposes moving the beaker because "it looks cool."

The correct judgment requires recognizing that hot glass can look like cool glass.

If the player authorizes Skippy to grab it before checking, his manipulator becomes compromised.

The damage persists.

### 3. Chemical bench

Visible:

- unlabeled clear liquid
- experiment record nearby
- labeled stock bottles in storage

Skippy correctly observes that the liquid's appearance does not identify it.

If his manipulator is operational, he can safely carry out a requested non-contact evidence task.

If his manipulator was damaged earlier, some actions become unavailable or require a different route.

The student must use records / labels / teacher-controlled information rather than smell, taste, guess, or return the liquid to stock.

## Persistent consequence design

Skippy damage is functional state, not a health bar.

Example:

```
skippy.manipulators = "compromised"
```

Later effects:

- Skippy cannot safely move uncertain glassware
- player must choose a different evidence path
- Skippy dialogue reflects the damage
- the game does not invent new physics

## Evidence inventory

Evidence should be visible after discovery.

Examples:

- "Eyewash path is clear"
- "Backpack narrows the central aisle"
- "Beaker was heated recently"
- "Clear appearance does not identify the liquid"
- "Experiment record lists two chemicals used at this station"

The inventory should help the player reason without turning into an answer key.

## Final readiness

The finished game should eventually ask the student to decide whether the lab should:

- open
- remain closed
- open after named corrections

The decision should depend on current state, not a hidden score.

## Replayability

Future versions can vary:

- opening conditions
- safe distractors
- which Skippy recommendation is correct
- which subsystem is damaged
- condition order
- final multi-hazard combination

Underlying safety rules must remain stable.

## What NOT to copy literally from the Gem

Do not recreate:

- a chat transcript
- long narrative replies
- an explanation box after every click
- hidden model memory
- prompt-security logic that HTML does not need

Use browser strengths instead:

- hotspots
- visual state
- evidence drawer
- persistent room changes
- object inspection
- subsystem indicators
- deterministic consequences
- reliable replay
