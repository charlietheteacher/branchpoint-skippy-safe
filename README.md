# SKIPPY SAFE: Best Lab Day Ever

SKIPPY SAFE is a BranchPoint Simulations laboratory-safety judgment game for roughly grades 7–9, adaptable for grades 6–10.

The student is the Laboratory Safety Lead. Skippy is a cheerful, technically competent robot assistant whose recurring blind spot is risk estimation. The learning goal is not to memorize a checklist. Students investigate evidence, make consequential safety decisions, experience realistic consequences, revise when needed, and decide when the laboratory is genuinely ready.

## Repository status

Current source baseline: SKIPPY SAFE Gemini Gem package v1.1.

The HTML game in this repository is exploratory. It is not yet a finished commercial or classroom release.

The first development question is:

> Can the open, stateful BranchPoint judgment engine in the Gem become an excellent static HTML game without turning into a linear quiz or a chatbot imitation?

## BranchPoint design principles

The core loop is:

```
problem
→ observation
→ evidence
→ student judgment
→ consequence
→ new evidence
→ revision or defense
```

The browser should provide the environment, evidence, state, character behavior, and consequences. The student should retain the important intellectual work: hazard identification, prioritization, evidence interpretation, causal reasoning, and final authorization.

Important constraints:

- reality and laboratory safety rules determine consequences
- Skippy is competent and is sometimes correct
- Skippy must never become the answer key
- earlier decisions and Skippy damage can affect later play
- safe, unsafe, and ambiguous conditions should all exist
- routine safe corrections should not become constant quiz questions
- major or ambiguous decisions should expose student reasoning
- the game should remain usable on ordinary school Chromebooks
- the static game should not collect student names or require accounts

## Repository structure

```
source/       Current v1.1 Gem source package
docs/         HTML translation and game-design documentation
game/         Static HTML prototype
tests/        Functional and adversarial test plans
```

## Run the prototype

The prototype uses plain HTML, CSS, and JavaScript with no build step.

For the current vertical slice, open:

```
game/index.html
```

A simple local web server is preferred during development because the game uses ES modules. For example:

```bash
python3 -m http.server 8000
```

Then open:

```
http://localhost:8000/game/
```

## Privacy

The prototype is designed to run entirely in the browser.

- no accounts
- no student-name collection
- no API keys
- no server-side database
- optional progress stored only in browser localStorage

## Deployment direction

If the static architecture proves successful, the game can later be deployed to a static host such as Cloudflare Pages or GitHub Pages.

## Source of truth

The files in `source/` preserve the current v1.1 Gemini simulation design. The HTML implementation may redesign interaction mechanics where a browser can do better than chat, but it should preserve the underlying BranchPoint instructional architecture.

## Licensing

This repository is public for development visibility. No open-source license has been granted. Unless explicitly stated otherwise, all rights are reserved by the repository owner.
