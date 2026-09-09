---
layout: post
title: "The AI Paradigm Shift: More Ambition in the Same Time"
excerpt: "Notes on how AI is changing my development workflow, project scope, and the problems I want to tackle next."
categories: [Tech💡]
comments: true
image:
  feature: feature/poly.jpg
---

<!-- Writing outline: expand each one-line note with personal examples and evidence; verify claims marked TODO before publishing. -->

## The Way We Build Has Changed

Write about raising project ambition within the same time budget, using a six-month development plan becoming three months or less as an example to substantiate from my own work.

## Predicting AI: The Bet I Remembered

Use Melanie Mitchell’s [Artificial Intelligence: A Guide for Thinking Humans](https://melaniemitchell.me/aibook/) to introduce uncertainty in AI predictions, then explain the [2002 Kurzweil–Kapor wager](https://longbets.org/1/): Kurzweil expected a computer to pass their agreed Turing test by 2029 and Kapor disagreed; distinguish this test from an agreed definition of AGI and locate the book passage before quoting it.

## The Indie Developer’s Advantage

Explain how years spent learning 3D modelling, graphics, VFX and programming help me direct agents, judge their output and connect work across disciplines.

### Integrating MCP into Everyday Work

Describe a concrete example of MCP tools automating tedious work in an existing project, shortening the path from an idea to a prototype and helping me discard weak ideas sooner.

### A Visual Project Map Beside the GDD

Explain why a growing game design document needs a visual overview of systems, dependencies and progress so I can understand the whole project as its scope expands.

## From Scrum Teams to a Different Balance

Reflect on my experience with DevOps and Scrum at four to six engineers per PM, then explore my prediction of a possible 1:1 balance with PMs more involved in testing and validating delivery pace.

## From a Kanban Issue to a Tested Change

Describe giving an agent access to my live Kanban board, asking it to execute an issue by ID, and reviewing the change after it moves the issue into testing with suggested test cases.

### The Issue Description Is the Prompt

Show an example task containing the same details I would give a developer: the existing class to reference, what to change or add, constraints to consider and acceptance criteria.

### Short Context and Clear References

Explain why a task exceeding roughly 15,000 tokens makes me review my own instructions and project references, treating that as a personal diagnostic rather than a universal limit, and question whether my specialised subagents still help.

### Test Harnesses That Understand the Project

Outline how a harness could expose project state, repeatable scenarios and pass/fail criteria to agents while keeping human review focused on behaviour and experience.

## Local Inference and the Fear of Being Priced Out

Recount my concern about access to “superintelligence” while using Claude in March 2026 and how, by June, well-scoped natural-language prompts let me complete tasks almost as quickly as I could formulate them.

### What Makes Sense for a Hobby Project?

Explain my personal comfort with 40 a month versus 200, adding the currency and relevant subscriptions before publication and considering local hardware and running costs alongside recurring fees.

### What Can My Local GPU Actually Do?

TODO: verify the model name remembered as “Qwen 3.7” and the roughly 100 tokens/second claim on an RTX 5080, recording model size, quantisation, runtime, context length and whether this measures output generation before drawing comparisons with hosted agents.

## The Problems I Want to Be More Ambitious About

Introduce the game-development and scientific problems I want to revisit now that faster iteration makes previously impractical experiments more approachable.

### A GUI for Managing Agent Work

Sketch a visual interface that brings sprint progress, tasks, missing requirements and project dependencies into one view so I can keep pace with agent-driven development.

### Agents That Can Validate Gameplay

Explore combining direct access to game state and automated checks with visual UI selection, on-screen text reading and gameplay, reducing reliance on repeated screenshots while retaining visual tests where needed.

### Playing Against My Own Skill Level

Describe the idea of learning from my movement and actions to build an adaptive opponent for a Rust-style 1v1, distinguishing training from inference and starting with a turn-based prototype to measure latency before attempting real-time play or a hybrid with procedural behaviour.

### Frameless Rendering for VR

Outline the experiment I want to run in a game engine to explore frameless rendering and measure whether it can reduce jitter associated with missed frames in VR.

### Improving Field of View in VR

Define the field-of-view limitation I want to investigate and identify which parts could be addressed through rendering, interface design or hardware before proposing an experiment.

## What I Will Build Next

Choose one of these ideas for a first prototype and define its time budget, success criteria and the evidence that would justify expanding or abandoning it.

## References to Revisit

- [Melanie Mitchell’s book page](https://melaniemitchell.me/aibook/) — background on the book and its treatment of AI’s capabilities and limitations.
- [Goodreads book entry](https://www.goodreads.com/book/show/43565360-artificial-intelligence) — the edition reference from my original notes.
- [Kurzweil–Kapor wager, Long Bets](https://longbets.org/1/) — primary source for the participants, 2029 deadline and their opposing arguments.
