+++
title = "Building Great Agent Skills: The Missing Manual"
date = 2026-07-03
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Software engineering--Artificial intelligence","Human-computer interaction","Software maintenance","Documentation"]
tags = ["Agent skills","Model-invoked skills","User-invoked skills","Context window","Token budget","Context pointer","skill.md","Markdown templates","Product requirements document (PRD)","Architectural decision records (ADR)","Domain modeling","Glossary (context.md)","Test seams","Human-in-the-loop","Leading words","Vertical slice","Plan mode","Clarifying questions","Deletion test","Single source of truth","Sediment","No-op instructions","Matt PCO skills","Superpowers","aihero.dev"]

[extra]
excerpt = "With 100 model-invocable skills, an agent carries 100 always-on descriptions in context—paying token cost every request and increasing decision noise about what to call. The playbook here is a concrete skill-quality checklist (trigger → structure → steering → pruning) that trades off agent context load vs user cognitive load, then shrinks skills via branching references, leading words, and deletion tests to eliminate “no-op” instructions."
video_url = "https://www.youtube.com/watch?v=UNzCG3lw6O0"
video_id = "UNzCG3lw6O0"
cover = "https://img.youtube.com/vi/UNzCG3lw6O0/maxresdefault.jpg"
+++

## Overview

With 100 model-invocable skills, an agent carries 100 always-on descriptions in context—paying token cost every request and increasing decision noise about what to call. The playbook here is a concrete skill-quality checklist (trigger → structure → steering → pruning) that trades off agent context load vs user cognitive load, then shrinks skills via branching references, leading words, and deletion tests to eliminate “no-op” instructions.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
A practitioner’s rubric for skill engineering that treats skills as token-budgeted, failure-mode-prone software artifacts: explicitly manage invocation mode (user vs model), design skills as “steps + reference,” steer behavior with compact “leading words” that the model will echo in its own reasoning, and aggressively prune via deletion tests to remove sediment and no-ops. The distinctive stance is preferring user-invoked skills to reduce unpredictability from model choice, even if it increases pilot skill requirements.

### The Core Problem
“Skill hell”: an ecosystem full of downloadable agent skills without a shared way to judge quality, integrate them coherently, or convert organizational operating procedures into reliable agent behaviors. Without a rubric, teams accumulate bloated, inconsistent skills that cost tokens, behave unpredictably, and fail to deliver promised automation.

### The Solution Approach
1) Trigger design: decide whether a skill is user-invoked (hidden from the model; user explicitly calls it) or model-invoked (a description acts as a context pointer the model can follow). Make the trade-off explicit: model-invoked increases agent context load and unpredictability; user-invoked increases user cognitive load but improves determinism.
2) Internal structure: build skills from two units—Steps (procedure) and Reference (supporting definitions/templates). Keep the main skill.md minimal; push branch-specific reference behind context pointers to separate markdown files.
3) Steering: use “leading words” (dense phrases like “vertical slice”) repeated consistently so the model mirrors them in reasoning/output, reinforcing the intended behavior. If the model under-invests effort in early steps, hide future goals by splitting phases into separate skills.
4) Pruning: shrink and harden skills by removing duplication (single source of truth), clearing “sediment” from collaborative accretion, and deleting “no-ops” (text that doesn’t change behavior) using deletion tests.

### Key Insights
- Invocation mode is a systems trade-off: model-invoked skills add token and attention overhead to every request (context load), while user-invoked skills shift burden to the operator (cognitive load) but reduce stochastic “will it call the skill?” behavior.
- A skill description functions as a context pointer: it sits in the agent’s context and points to skill.md, which is only pulled in if the model decides to follow the pointer—making model invocation inherently less predictable.
- Design skills as “Steps + Reference” to make them composable and auditable: steps are the algorithm; reference is the supporting data (definitions, templates) that steps depend on.
- Branch-aware minimization is the fastest path to small skills: if reference material is only needed in one branch, move it out of skill.md and place it behind an external reference/context pointer to a separate file.
- Leading words are a compression-and-control hack: choose a term with strong developer priors (e.g., “vertical slice”), repeat it, and verify success by watching it appear in reasoning traces and plans.
- When agents don’t do enough leg work, it’s often because they can see the end goal and rush; splitting phases into separate skills forces depth by hiding the next objective (e.g., separate “clarify” from “plan/PRD”).
- Deletion tests explain how small skills happen in practice: remove a paragraph and see if behavior changes; if not, it was a no-op and should stay deleted.
- “Sediment” is a collaborative documentation failure mode: people keep appending to shared markdown without restructuring or deleting, producing large, stale skills that need branch refactoring or outright removal.
- Human-in-the-loop checkpoints can be embedded as explicit steps (e.g., confirm test seams) to prevent the agent from making silent, risky assumptions.
- A practical quality rubric beats collecting more skills: the ‘just one more skill’ mindset increases complexity without improving reliability unless skills are evaluated and pruned.

### Concepts & Definitions
- Skill hell: a developer trap where many available skills exist but there’s no shared rubric to evaluate them, so integration becomes trial-and-error and results underdeliver.
- User-invoked skill: a skill that the user explicitly calls; the model does not see the invocation description (often via a flag like disable_model_invocation=true), reducing agent context load and increasing determinism.
- Model-invoked (model-invocable) skill: a skill whose description is visible to the model and can be chosen automatically; the description acts as a context pointer to skill.md.
- Context pointer: a short description in context that points the model to another file for more detail; useful for modularity but introduces the risk the model won’t follow it.
- Context load vs cognitive load: context load is token/attention burden on the agent from always-present skill descriptions; cognitive load is the burden on the user to remember and choose skills.
- Steps: the procedural, step-by-step instructions a skill executes.
- Reference: supporting material (definitions, templates) that enables steps without bloating the procedure.
- External reference: reference material moved out of skill.md into separate files, pulled in only when needed for a branch.
- Leading words: compact, meaning-dense phrases repeated in a skill to steer model behavior because the model echoes them in reasoning/output.
- Sediment: accumulated, unstructured additions to a shared skill file that bloat it and introduce stale/irrelevant content.
- No-ops: instructions that look meaningful but don’t actually change model behavior; identified via deletion tests.
- Vertical slice: a development approach that builds a thin end-to-end feature slice (not layer-by-layer), used here as a leading word to trigger strong implementation priors.

### Technical Details & Implementation
- Model invocation control via metadata/flags: a pattern like disable_model_invocation=true hides the skill description from the model so only the user can invoke it.
- Skill packaging model: description (optional, for model invocation) + skill.md (main procedure) + auxiliary markdown reference files reachable via context pointers.
- Branching refactor technique: identify branches (different outcomes/actions) and move branch-only templates (e.g., ADR template, context.md template) into separate files referenced conditionally from skill.md.
- Steering verification loop: introduce a leading word, repeat it across steps, then inspect reasoning traces to see whether the model adopts the phrase (a proxy for behavioral uptake).
- Leg-work forcing architecture: split a multi-step ‘mode’ into sequential skills so the model cannot shortcut early steps (e.g., separate ‘grill with docs’ from ‘two PRD’).
- Deletion testing workflow: iteratively remove paragraphs/sections from a skill and re-run; if outputs remain effectively unchanged, the removed text was a no-op and should stay out.
- Single-source-of-truth discipline across steps and reference: keep templates/definitions in one place to avoid drift and duplication.

### Tools & Technologies
- Matt PCO skills / Matt’s skills repository (a public engineering skills repo; includes a ‘writing great skills’ skill encoding the checklist).
- Superpowers (another popular engineering skills set used as a contrast case for model-invoked skills).
- aihero.dev (newsletter site mentioned for follow-up content).
- Markdown skill files (skill.md plus referenced .md templates such as PRD templates, ADR templates, context.md/glossary).

### Contrarian Takes & Different Approaches
- Model-invoked skills are not automatically superior; they can be worse in practice because they add unpredictability (the model may not follow the pointer) and impose a permanent context tax.
- Shifting burden to the user (user-invoked skills) can be the right engineering choice when reliability matters more than convenience.
- Big, comprehensive skills are usually a smell, not a feature; quality often comes from aggressive minimization and modular references, not from adding more instruction text.
- Generic ‘plan mode’ is structurally flawed: combining ‘clarify’ and ‘plan’ invites the model to rush; separating them is a more reliable control mechanism.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Audit every skill with the checklist: (1) trigger choice, (2) steps+reference structure, (3) steering via leading words and leg-work control, (4) pruning for duplication/sediment/no-ops.
- Choose invocation mode deliberately: default to user-invoked when determinism matters; use model-invoked sparingly when user cognitive load is the bottleneck and you can tolerate missed calls.
- Count context load: if you’re accumulating many model-invoked skills, treat each description as an always-on token tax and a new decision branch for the agent.
- Rewrite skills into ‘Steps’ and ‘Reference’ sections; move templates/definitions out of the procedure when they’re not universally needed.
- Identify branches explicitly (different possible actions/outcomes); for each branch, externalize branch-only reference behind a context pointer to keep skill.md small.
- Pick 1–3 leading words that encode your desired behavior (e.g., “vertical slice”), repeat them consistently, and confirm they appear in reasoning traces and plans.
- If clarifying questions are shallow, split the workflow: run a dedicated ‘clarify/grill’ skill first, then a separate ‘plan/PRD’ skill so the model can’t rush to the end.
- Run deletion tests weekly on high-use skills: remove one chunk at a time and keep it deleted unless behavior measurably worsens.
- Treat shared skill files like code: refactor and delete aggressively to prevent sediment; restructure contributions into branches and external references.

### What to Avoid
- Defaulting everything to model-invoked skills creates hidden costs: token overhead on every request and increased unpredictability when the model ignores a context pointer.
- Assuming ‘more flexible’ equals ‘better’: model invocation adds a new failure mode (non-invocation) that can force painful evaluation work to ensure skills are called appropriately.
- Monolithic skill.md files become un-auditable and expensive; bloat is usually a symptom of missing branching structure, duplication, or sediment.
- Plan modes commonly fail because the model sees the final goal (a plan) and under-invests in clarifying questions; bundling both steps encourages shortcutting.
- Duplicating templates/definitions across steps or reference causes drift and makes maintenance harder; it also inflates tokens without improving behavior.
- Sediment from collaborative edits leads to stale instructions that may conflict with current practice; without pruning, skills degrade over time.
- No-op instructions waste tokens and attention; if deleting a paragraph doesn’t change outputs, it was never steering the model.

### Best Practices
- Use a shared rubric for skill quality so teams can distinguish good skills from bad and iteratively improve them rather than endlessly collecting new ones.
- Prefer small, modular skills: keep skill.md minimal, externalize branch-only reference, and treat every word as both maintenance surface area and token cost.
- Enforce single source of truth for reference artifacts (templates/definitions) and link to them rather than repeating them.
- Steer with leading words: compress intent into reusable phrases that the model will echo, making behavior more consistent and easier to diagnose.
- Increase effort on critical phases by hiding future steps: split skills so the model focuses on the current objective without rushing.
- Add explicit human-in-the-loop checkpoints where risk is high (e.g., confirm test seams) to prevent silent misalignment.
- Continuously prune: remove duplication, refactor sediment, and run deletion tests to eliminate no-ops and keep skills sharp.

### Personal Stories & Experiences
- A personal preference for control shaped the design philosophy: user-invoked skills were chosen to reduce unpredictability from model choice, accepting higher operator cognitive load as the price of determinism.
- Repeated frustration with ‘plan mode’ across implementations led to an evolved workflow: split clarifying questions into a dedicated ‘grill with docs’ skill and follow with a separate PRD skill to force deeper inquiry.
- Maintaining a popular skills repository created a sense of responsibility to help users escape ‘skill hell’ by providing a concrete checklist and an encoded ‘writing great skills’ skill.

### Metrics & Examples
- Example scale used to illustrate context load: 100 model-invoked skills implies 100 skill descriptions in the agent’s context on every request (token and attention overhead).

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=UNzCG3lw6O0)

## Value Assessment

- **Practical Value:** conceptual framework
- **Uniqueness Factor:** fresh perspective
