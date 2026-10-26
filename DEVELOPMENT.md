# SKIPPY SAFE HTML Development Notes

## Objective

Translate the current SKIPPY SAFE Gemini Gem into a static browser game without flattening it into a quiz or recreating a chat window.

The Gem currently relies on a conversational model to maintain state, reveal evidence, judge student reasoning, play Skippy, and generate consequences. The HTML version must make those responsibilities explicit in code and data.

## Gem concept → HTML equivalent

| Gem architecture | HTML architecture |
| --- | --- |
| Open conversation | Explorable laboratory interface |
| Conversational state | Explicit JavaScript state object |
| Gem Knowledge files | Structured scenario/reference data |
| Skippy runtime behavior | Character + consequence engine |
| Evidence release | Clickable inspections and evidence inventory |
| Explanation Gate | Reasoning interaction at consequential decisions |
| Persistent damage | Skippy subsystem state |
| Re-anchor behavior | State serialization + deterministic rendering |
| Replay variation | Scenario configuration and condition selection |
| Final synthesis | Laboratory readiness decision |
| Gem memory | localStorage save/resume |

## State model

The first prototype uses a compact state object:

```js
{
  version: 1,
  currentArea: "entrance",
  areasVisited: [],
  evidence: [],
  hazardsResolved: [],
  hazardsUnresolved: [],
  decisions: [],
  skippy: {
    chassis: "operational",
    optics: "operational",
    manipulators: "operational",
    mobility: "operational",
    chemicalSensor: "operational",
    temperatureSensor: "operational",
    voice: "operational"
  },
  flags: {},
  finished: false
}
```

Future versions should separate immutable scenario definition from mutable runtime state.

## What translates directly

- open exploration
- safe / unsafe / ambiguous conditions
- Skippy's stable worldview and risk blind spot
- evidence-before-conclusion
- persistent robotic damage
- consequences constrained by physics and lab safety
- final readiness decision
- replay variation
- adaptive difficulty through evidence and choice structure

## What should be redesigned for HTML

The Gem can accept arbitrary natural-language actions. A static game cannot genuinely understand every student sentence without an AI model.

Do not fake open-ended understanding.

Instead, preserve agency through:

- explorable areas
- inspectable objects
- evidence requests
- multiple reasonable actions
- contextual reason/evidence selections
- optional short free-response at major synthesis points
- multiple valid safe routes where practical
- stateful consequences that change later choices

## What HTML can do better than chat

- stable visible state
- visual laboratory map
- persistent Skippy damage
- environmental changes
- evidence inventory
- disabled or altered actions after damage
- direct inspection of labels and SDS excerpts
- replayable deterministic QA
- fast loading and no model latency
- no model drift during long sessions
- no prompt injection / answer extraction vulnerabilities

## What may be lost without an LLM

- arbitrary natural-language investigation
- nuanced interpretation of unusual student proposals
- flexible follow-up questions
- rich improvisational Skippy dialogue
- open-ended explanation grading

The goal is not to replace those capabilities with fake NLP. The goal is to build interaction structures that still require judgment.

## Reasoning design

Do not ask "Why?" after every correct action.

Require explicit reasoning mainly when the player:

- claims a condition is safe
- chooses among competing priorities
- proposes a risky action
- handles an emergency
- makes a consequential decision
- authorizes the final lab opening

For routine corrections, let the action occur and show the consequence.

## Source-of-truth rule

The files in `source/` remain the instructional source of truth. HTML code should not silently introduce new safety rules, chemical facts, or emergency procedures.

If the game needs a fact not established in the source package, document the gap before adding it.

## Prototype goal

The first vertical slice proves:

1. laboratory exploration
2. an ambiguous condition
3. a genuine hazard
4. one case where Skippy is right
5. one case where Skippy underestimates risk
6. evidence discovery
7. one consequential choice
8. persistent Skippy damage
9. a later choice changed by earlier damage
10. save/resume through localStorage

This is an architecture test, not a finished game.
