# 🎯 vibe-coding-prompts

> **Copy-paste prompt templates for vibe coding with Claude Code, Cursor, Lovable & Bolt.**
> 60+ scenario-based templates, each with a "why it works" explainer — so the AI does what you meant, instead of over-refactoring, guessing, and going rogue.

[![Stars](https://img.shields.io/github/stars/shao-yung-85/vibe-coding-prompts?style=flat-square)](https://github.com/shao-yung-85/vibe-coding-prompts/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](./LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](./CONTRIBUTING.md)
[![Prompts](https://img.shields.io/badge/prompts-60+-orange.svg?style=flat-square)](#-table-of-contents)
[![Last Commit](https://img.shields.io/github/last-commit/shao-yung-85/vibe-coding-prompts?style=flat-square)](https://github.com/shao-yung-85/vibe-coding-prompts/commits/main)

🇬🇧 English (this file) ・ 🇹🇼 [中文](./README.md) ・ 💡 [Examples](./examples/)

**👇 Jump to:** [⚡ Cheat Sheet](#-cheat-sheet-one-liner-prompts) ・ [🛡️ Stop AI from going rogue](#️-guardrail-prompts-keep-the-ai-from-going-off-script) ・ [🆚 Bad vs good prompts](#-bad-prompt-vs-good-prompt)

> ⭐ **Useful? Drop a Star** — every star helps the next dev who's losing their mind to a rogue AI find this list.

---

## 🤔 What problem does this solve?

When you code with AI (vibe coding), three things go wrong constantly:

1. **You don't know how to ask** — you stare at the input box, write a vague prompt, and the AI hands back something unusable.
2. **The AI goes rogue** — you ask for one button, and it refactors half the project, deletes your tests, and touches unrelated files.
3. **Results are unpredictable** — same request, sometimes one shot, sometimes ten rounds of going in circles.

This repo collects prompts that *reliably* produce good results, as copy-paste-ready templates — **and every one explains why it works**, because once you understand the principle, you can adapt it to your own needs.

---

## ⚡ How to use (30 seconds)

1. **Find your scenario** — hit `Ctrl/⌘ + F` and search (e.g. "debug", "refactor", "guardrail"), or jump from the [table of contents](#-table-of-contents).
2. **Copy the prompt** — every prompt is in a code block; click the copy button.
3. **Fill in the blanks** — replace the `[brackets]` with your actual content.
4. **Paste into your tool** — works with Claude Code / Cursor / Lovable / Bolt. Paste and send.

> 💡 Want to see how multiple prompts chain together? See the [examples](./examples/).
> Want to set up project guardrails once instead of re-pasting? Use the [CLAUDE.md template](./CLAUDE-md-template.md).

---

## ⚡ Cheat Sheet (one-liner prompts)

Don't want to scroll? These 12 one-liners are copy-paste-and-fill ready. Full versions (with "why it works") are in the categories below.

| 🎯 What you want | 💬 Paste this (`[ ]` = fill in) |
|------------------|----------------------------------|
| New project | Don't write code yet — restate the requirements, list the folder structure, flag any concerns. I'll confirm before you start. |
| Add a feature | Don't write yet — list which files you'll change and your plan. I'll say OK, then you build. |
| Fix a bug | Don't change anything yet — explain the error, list the 2-3 most likely causes, and how to confirm which. |
| Refactor | Behavior must stay identical, no new features, structure only. Explain how to confirm behavior is unchanged. |
| Write tests | Cover edge cases (null/0/huge) and bad input; name each test for what it verifies. |
| Tweak styling | Only change `className`/`style` — don't touch any logic, state, or event handlers. |
| 🛡️ Stop it changing things | Use the minimal change, don't refactor/reformat/touch unrelated code; ask me before changing anything else. |
| 🛡️ Stay in scope | You may only edit these files: `[list]`. Stop and ask before touching anything else. |
| 🛡️ Don't guess | If anything is uncertain, stop and ask me — don't assume an answer and keep going. |
| Explain this code | Walk through line by line what it actually does; flag side effects and edge-case failures. |
| Write a commit | Use Conventional Commits; explain "why" in the body, not just "what" changed. |
| Deploy failed | Find the line that actually caused the failure (not the cascade), explain it, give fix steps. |

> 🛡️ = guardrails, the most effective at stopping the AI from going rogue — and what sets this repo apart from a generic prompt list.

---

## 📑 Table of Contents

- [🆚 Bad prompt vs good prompt](#-bad-prompt-vs-good-prompt)
- [🚀 Project Initialization](#-project-initialization)
- [✨ Adding Features](#-adding-features)
- [🐛 Debugging](#-debugging)
- [♻️ Refactoring](#️-refactoring)
- [🧪 Writing Tests](#-writing-tests)
- [🎨 UI / Styling](#-ui--styling)
- [🗄️ Database / SQL](#️-database--sql)
- [🚢 Deployment / DevOps](#-deployment--devops)
- [📝 Writing Docs](#-writing-docs)
- [🧠 General Prompting Principles](#-general-prompting-principles)
- [🛡️ Guardrail Prompts (keep the AI from going off-script)](#️-guardrail-prompts-keep-the-ai-from-going-off-script)
- [📋 CLAUDE.md Templates](#-claudemd-templates)
- [🔧 Tool Comparison](#-tool-comparison)
- [🤝 Contributing](#-contributing)

---

## 🆚 Bad prompt vs good prompt

Same request, different phrasing, very different results. Once you get these pairs, you've got the principle behind every template here.

**Case 1: New project**

❌ Bad:
```
build me a todo app
```
✅ Good:
```
I want to build a todo app, stack React + TypeScript.
Don't write code yet — restate the requirements, list the folder structure, and flag anything you're unsure about. I'll confirm before you start.
```
**The difference:** The bad one forces the AI to guess a pile of assumptions; the good one aligns on requirements before any code, catching misunderstandings early.

---

**Case 2: Fix a bug**

❌ Bad:
```
fix this error [paste error]
```
✅ Good:
```
I'm hitting this error [paste error]. Don't change any code yet — explain what it means,
list the 2-3 most likely causes (most to least likely), and tell me how to confirm which one.
```
**The difference:** The bad one makes the AI change things at random — treating symptoms, adding new bugs; the good one forces it to find the root cause.

---

**Case 3: Add a feature**

❌ Bad:
```
add user login
```
✅ Good:
```
I want to add login. Don't write yet — list which files you'll add/change, your plan, and whether it affects existing features.
I'll say OK, then build only the "enter credentials → logged in" main path first.
```
**The difference:** The bad one produces a pile of untested code that may touch unrelated things; the good one narrows scope and shows you the plan first.

---

**Case 4: Refactor (where the AI most easily overreaches)**

❌ Bad:
```
optimize this code
```
✅ Good:
```
Refactor this code: external behavior must stay exactly the same, no new features, don't change anything on the side,
only structure and naming. When done, explain what you did and how to confirm behavior is unchanged.
```
**The difference:** "Optimize" is too vague — the AI changes features, formatting, and a dozen things you didn't ask for; the good one nails down "behavior unchanged" as the iron rule.

---

**Case 5: Stop the AI from going rogue**

❌ Bad:
```
while you're at it, clean up the related stuff too
```
✅ Good:
```
Solve this with the minimal change — only the lines truly necessary. Don't refactor, don't reformat,
don't touch unrelated code. If you really want to change something else, list it and ask me first.
```
**The difference:** "While you're at it" is where disasters start — a small fix becomes a 100-line diff; the good one locks the scope so the diff stays small and reviewable.

> 📌 The shared principle: **plan before executing ｜ narrow the scope ｜ spell out the boundaries ｜ keep your veto**. Every template below is a variation on these four.

---

## 🚀 Project Initialization

The first prompt of a new project sets the foundation for every conversation that follows. A crooked foundation makes everything else crooked.

### 1. Talk it through before writing a single line

```
I want to build [one-sentence description of the project].
Stack: [language / framework / database].
Target users: [who will use it].

Don't write any code yet. Please:
1. Restate the requirements as you understand them, as bullet points
2. List your suggested folder structure
3. Point out anything you're unsure about or that needs my decision

Wait for my confirmation before you start.
```

**Why it works:** It forces the AI into "planning mode" instead of "generate immediately" mode. Having it restate requirements catches misunderstandings in round one; asking for its concerns surfaces the hidden assumptions it would otherwise make silently.

### 2. Walking skeleton first

```
Please create the minimal skeleton that gets this project running:
- Just enough to start successfully and show a "Hello" screen
- Include the necessary config files (package.json / requirements.txt, etc.)
- No business logic, no features yet

When done, tell me how to start it. I'll run it and confirm before we continue.
```

**Why it works:** Generating an entire project at once almost never runs, and it's hard to debug. Asking for a minimal "it runs" version first establishes a known-good baseline, so every feature you add stands on stable ground.

### 3. Lock versions and conventions

```
Before we start, set up the project under these constraints:
- [Language] version: [x.x]
- Package manager: [npm / pnpm / pip / poetry]
- Style: [ESLint + Prettier / Black / ...]
- Don't use deprecated APIs

If you plan to use a major package I haven't mentioned, ask me before installing.
```

**Why it works:** AI training data spans many versions, so it may mix old and new syntax by default. Pinning versions and tools explicitly avoids producing a Frankenstein project that won't run on your machine.

### 4. Decide the folder structure once

```
Propose 2 folder-structure options for this project:
- Option A: optimized for fast development, few files
- Option B: optimized for long-term maintenance, clear modules

List pros, cons, and the ideal use case for each, then recommend one. Once I pick, create the empty folders and placeholder files.
```

**Why it works:** Changing structure mid-project is the most painful refactor (every import path moves). Having the AI present options with tradeoffs lets you make this high-leverage decision when it costs nothing.

### 5. Generate the README and dev commands

```
Generate a README.md for this project, including:
- A one-line description
- Requirements
- Install steps (copy-paste-able commands)
- How to run / how to test
- Folder structure explanation

Write actual runnable commands, not vague descriptions like "install dependencies".
```

**Why it works:** Forcing the AI to write down exactly how to run the project is a sanity check — if it can't produce runnable commands, the project setup itself has a problem.

---

## ✨ Adding Features

Adding features is where the AI most easily loses control, because it "helpfully" touches whatever it thinks is related. The key is to narrow the scope and define the boundaries.

### 1. Plan first, implement second

```
I want to add this feature: [description].

Don't write code yet. Please:
1. List which files you'll add / modify
2. Describe roughly what each file needs to change
3. Point out anything that might affect existing functionality

After I review the plan and say OK, then start writing.
```

**Why it works:** It splits "planning" from "execution." You catch wrong directions at the cheap stage (before any code), and you see which files it intends to touch, preventing it from sprawling beyond scope.

### 2. Vertical slice (one complete path at a time)

```
Implement only the minimal vertical slice of this feature:
- One complete path from [user action] to [seeing the result]
- Skip edge cases, error handling, and styling for now
- Just get the main flow working

When done, I'll test it. If it's good, we'll add the details.
```

**Why it works:** "Building the whole feature at once" produces a pile of untested code. Wiring up the thinnest end-to-end path first quickly validates the design works, then you reinforce it in batches, each step verifiable.

### 3. Follow the existing pattern

```
Look at how an existing similar feature is built (e.g. src/features/login),
and implement [new feature] using the same structure and style.

Keep the naming, folder location, and error-handling consistent with the existing code.
```

**Why it works:** The AI defaults to whatever style it "thinks is best," which fragments a codebase. Giving it a concrete example as an anchor makes the output blend naturally into the project instead of sticking out.

### 4. Spell out acceptance criteria

```
Add this feature: [description].

Definition of done (must satisfy all):
- [ ] [criterion 1, e.g. show a hint when the email format is invalid]
- [ ] [criterion 2, e.g. redirect to home on success]
- [ ] [criterion 3, e.g. show a loading state]

Implement each one, then report the status of every item against the checklist.
```

**Why it works:** Vague requirements buy vague results. Breaking "done" into checkable, concrete criteria gives the AI a clear target and gives you an objective basis for acceptance — no more "it thinks it's done but half is missing."

### 5. Integrate into an existing flow

```
I want to wire [new feature] into the existing [flow, e.g. checkout].

First read the relevant existing files, then tell me:
1. Where the integration point is (which function / component)
2. What data needs to be passed
3. Whether it might break existing behavior

After I confirm, make the change, and try not to alter the public interface of existing functions.
```

**Why it works:** The biggest risk of a new feature is breaking an old one. Requiring the AI to "understand" before "integrating," and to protect existing interfaces, drastically reduces the chain damage of fixing A and breaking B.

---

## 🐛 Debugging

The cardinal sin in debugging is letting the AI guess and change things randomly. A good prompt forces it to find the root cause before touching anything.

### 1. Diagnose first, don't rush to fix

```
I'm hitting this error:
[full error message / stack trace]

Steps to reproduce:
[1. ... 2. ... 3. ...]

Don't change any code yet. Please:
1. Explain what this error actually means
2. List the 2-3 most likely causes, most to least likely
3. Tell me how to confirm which one it is

We'll confirm the root cause before fixing.
```

**Why it works:** The AI's instinct on seeing an error is "change something and see." That treats symptoms, not causes, and often introduces new bugs. Forcing it to analyze, hypothesize, and give verification methods lands on the real root cause.

### 2. Provide full context

```
This code doesn't behave as expected.

I expected: [expected behavior]
What actually happens: [actual behavior]

Relevant code:
[paste code]

Relevant input / data:
[paste actual data]

Find why the expected and actual don't match.
```

**Why it works:** "Expected vs actual" is the golden format for debugging. A clear description of the gap plus real data means the AI doesn't have to guess what you want — it focuses directly on the discrepancy.

### 3. Add logs to narrow it down

```
I'm not sure which part is failing. Add console.log / print statements at the
key points in this flow so I can see the variable values at each step.

Don't change the logic yet — only add observability output. I'll run it and paste the results, then we'll judge together.
```

**Why it works:** When the root cause is unclear, adding observability beats letting the AI guess-and-edit. Narrowing it down with real execution data is more accurate than any speculation and avoids cutting in the wrong place.

### 4. Bisect to locate it

```
This feature worked yesterday and broke today. I'm not sure which change caused it.

Help me locate it with a bisection approach:
- Tell me which part to check / temporarily disable first
- Based on the result, narrow it down further

Give me one clear action at a time.
```

**Why it works:** It turns a needle-in-a-haystack into a systematic binary search. One action at a time avoids confounding variables and pins down the offending change in the fewest steps.

### 5. Explain this code I don't understand

```
I don't understand why this code behaves this way (or why it errors):
[paste code]

Explain line by line what it actually does, especially flagging:
- Anything with side effects
- Anything that could fail in an edge case

Explain at a level a [beginner / intermediate] like me can follow.
```

**Why it works:** Many bugs come from "you think this does A, but it does B." Letting the AI act as a translator, reconstructing the real behavior line by line and flagging side effects and edge risks — you often spot the problem yourself halfway through the explanation.

---

## ♻️ Refactoring

Refactoring is where the AI most easily "helps too much" — it quietly changes behavior. The rule: **change structure, not behavior.**

### 1. Behavior-preserving refactor

```
Refactor this code:
[paste code]

Absolute rules:
- External behavior must stay exactly the same (same inputs → same outputs)
- Don't add features, don't change the API
- Only improve readability / structure / naming

When done, explain what you changed, why, and how to confirm behavior is unchanged.
```

**Why it works:** "Behavior unchanged" is the iron law of refactoring. Writing it in as an absolute rule blocks the AI's urge to "optimize features while it's in there," so you can safely review structural changes only.

### 2. Tests before refactoring

```
I want to refactor [some code], but I'm worried about breaking it.

Step 1: Write tests for its current behavior (main cases + edge cases) and make sure they're green.
Step 2: Once I confirm the tests pass, do the refactor and keep the tests passing.

Do only step 1 for now.
```

**Why it works:** Refactoring without tests is surgery with your eyes closed. Locking in "the current correct behavior" with tests first means a green suite after refactoring proves behavior is unchanged — the safest refactoring workflow there is.

### 3. One kind of refactor at a time

```
This code has several things worth improving. Do only one kind of refactor at a time, in batches.

This round: only [e.g. extract duplicated code into a function]. Leave everything else.

When done, I'll review, then we do the next kind.
```

**Why it works:** Mixing refactors (rename + extract + restructure) makes the diff impossible to review and hard to bisect when something breaks. Batching keeps each diff small and focused.

### 4. Eliminate duplication (DRY)

```
I think these spots have duplicated logic:
[paste a few similar snippets]

Decide whether they can genuinely be merged. If yes, extract a shared function / module;
if they merely look alike but are fundamentally different, tell me directly that they shouldn't be merged, and why.
```

**Why it works:** Giving the AI the option to "say no" prevents it from force-merging fundamentally different logic just to remove duplication (which creates painful over-abstraction). Let it judge, rather than blindly apply a rule.

### 5. Split an oversized function / component

```
This [function / component] is too big and does too much:
[paste code]

Split it into small, single-responsibility units:
- Each unit does one thing
- Names should reveal what each is responsible for
- Keep the external behavior unchanged

Give me the split plan first (which pieces), and after I agree, implement it.
```

**Why it works:** "Plan first" lets you evaluate the split before implementation. Requiring "single responsibility + clear naming" gives concrete criteria, avoiding both fragmentation and meaningless splits.

---

## 🧪 Writing Tests

The AI's common failing with tests is "only testing the happy path" or "green for green's sake." A good prompt makes it test the right things.

### 1. Cover edge and error cases

```
Write tests for this function:
[paste code]

Beyond the normal case, make sure to cover:
- Boundary values (null, 0, negatives, huge values, empty string / empty array)
- Invalid input (wrong type, wrong format)
- Whether exceptions are handled as expected

Name each test clearly to describe what it verifies.
```

**Why it works:** Bugs almost always hide in boundaries and error paths, not the normal flow. Explicitly listing what to cover stops the AI from writing three happy-path tests and calling it done.

### 2. Test behavior, not implementation details

```
Write tests for [feature].

Principle: test the externally observable behavior and results, not internal implementation details. That way, refactoring internals later shouldn't break the tests.

Use [test framework].
```

**Why it works:** Tests bound to implementation details are brittle — refactoring turns them red, and people end up deleting the tests. Behavior-focused tests have lasting value and protect you during refactors.

### 3. Start with a list of test cases

```
I want to write tests for [feature].

Don't write code yet. First list the test cases you plan to write (one sentence each describing what it verifies), grouped into "normal / edge / error".

After I review and add or remove cases, write the actual test code.
```

**Why it works:** Reviewing the list catches "missing cases" or "redundant tests" at zero cost. Getting the list right before writing code is far more efficient than writing a pile of tests only to find the direction was wrong.

### 4. Regression test that reproduces the bug

```
We just fixed a bug: [describe the bug].

Write a regression test that:
- Would fail before the fix (reproduces the bug)
- Passes after the fix

That way if someone accidentally reverts it later, the test catches it immediately.
```

**Why it works:** Every fixed bug deserves a "guard." This kind of test turns a one-time fix into permanent protection, preventing the same problem from sneaking back.

### 5. Add tests to existing code (build a safety net)

```
This code has no tests yet, and I'm not planning to change its behavior:
[paste code]

Write characterization tests for its current behavior — faithfully record what it actually outputs now, even if some behavior looks odd, write it down as-is, and flag anything suspicious for me to review.
```

**Why it works:** Facing untested legacy code, the first step isn't fixing but "pinning down the status quo." Locking the existing behavior with tests builds a safety net so you can later refactor or fix bugs with confidence.

---

## 🎨 UI / Styling

UI is the most "needs-specifics" scenario. The vaguer you are ("make it look nicer"), the less controllable the result.

### 1. Give references and constraints

```
Build a UI for [component, e.g. a pricing card].

Style reference: [e.g. clean modern like Stripe / paste a screenshot description]
Constraints:
- Use our existing [CSS framework / design system]
- Color scheme: [primary / secondary]
- Must be responsive (mobile + desktop)

Give me one version first, then I'll suggest adjustments.
```

**Why it works:** "Looks good" means something different to everyone. Concrete style references and hard constraints (framework, colors, responsive) turn abstract taste into an executable spec the AI can actually hit.

### 2. Style only, don't touch logic

```
Adjust only the visual styling of this component:
[paste code]

Need: [e.g. more spacing, rounded buttons, adjusted font sizes]

Do NOT touch any logic, state, event handlers, or data flow — only change className / style.
```

**Why it works:** When tweaking styles, the AI often "helpfully" optimizes logic and breaks things. Drawing a clear "styles only" red line keeps the change in the visual layer, making the diff safe and easy to review.

### 3. Use design tokens, not magic numbers

```
Apply styling to this interface, but don't hardcode magic numbers for colors and sizes.

Use variables / design tokens (e.g. CSS variables, Tailwind's spacing scale) so future global adjustments only need to change one place. If the project has no token system yet, propose one first.
```

**Why it works:** Hardcoded `#3b82f6` and `margin: 13px` scattered everywhere make later adjustments hell. Tokens make styling systematic and maintainable — something the AI won't do by default but matters long-term.

### 4. Accessibility (a11y) first

```
Build [component], accessible from the start:
- Correct semantic HTML tags
- Keyboard operable (Tab / Enter / Esc)
- Appropriate aria attributes and labels
- Sufficient color contrast

When done, list the accessibility measures you applied.
```

**Why it works:** Retrofitting accessibility is painful; doing it from the start is nearly free. Listing the requirements in the prompt makes a11y the default behavior and nudges the AI toward more correct semantic structure.

### 5. Incremental adjustment (small steps)

```
I want to fine-tune this screen, but one step at a time.

This round, change only: [one specific small tweak, e.g. center and enlarge the title]

Don't change anything else along the way. After I see the effect and I'm happy, I'll tell you the next tweak.
```

**Why it works:** UI tweaking is subjective; big rounds often "fix here, break there." Small steps verify one change at a time, giving you precise control over the final look and easy rollback of changes you don't like.

---

## 🗄️ Database / SQL

Database changes carry the highest risk — one wrong migration can destroy real data. These prompts emphasize safety and reversibility.

### 1. Safe migration (rollback-able)

```
I want to make this database change: [e.g. add a phone column to the users table].

Generate a migration, and make sure to:
- Write both the up (change) and down (rollback) directions
- Make the new column nullable or give it a default, so existing rows don't get stuck
- Don't drop or rename any existing column unless I explicitly ask

Show me the migration first; I'll confirm before you run it.
```

**Why it works:** Enforcing "rollback-able" and "don't break existing data" is the baseline for database safety. Requiring review before execution catches errors before an irreversible operation lands — destroyed data usually can't be recovered.

### 2. Explain and optimize this query

```
This SQL query is slow:
[paste SQL]

Please:
1. Explain what it's actually doing now and why it might be slow (e.g. full table scan, missing index)
2. Propose an optimized version
3. Say whether an index is needed, on which column, and why

Don't touch production data — just give me the analysis and suggestions.
```

**Why it works:** Asking for "why it's slow" first forces the AI to actually analyze the execution plan instead of blindly applying optimizations. Separating "analysis" from "execution" lets you evaluate the suggestion before applying it to production.

### 3. Prevent SQL injection

```
Review / write this database access code:
[paste code]

Rules:
- Always use parameterized queries (prepared statements)
- Never build SQL via string concatenation
- Treat all user input as untrusted before it reaches the query

If existing code concatenates SQL, flag it and convert to parameterized.
```

**Why it works:** SQL injection is one of the most common and most lethal vulnerabilities. Explicitly banning concatenation and requiring parameterization makes this safety rule the AI's default, closing off injection at the source.

### 4. Design the table schema

```
I need to store [describe data, e.g. orders and order line items].

Don't write SQL yet. First propose a table design:
- Which tables, and each one's columns and types
- How to set primary keys, foreign keys, indexes
- How to handle one-to-many / many-to-many relationships

Explain with text + a simple relationship diagram. After I confirm, generate the DDL.
```

**Why it works:** Table schemas are hard to change once they hold data. Discussing relationships and indexes at the "design stage" moves a high-leverage decision to when it costs nothing, avoiding painful migrations after launch.

### 5. Write a data-fix script safely

```
I need to correct a batch of data in production: [describe what to change].

Write a data-fix script, and:
- First write a "SELECT-only, no modification" query so I can confirm which rows are affected and how many
- The UPDATE statement must have an explicit WHERE clause, never omitted
- Wrap it in a transaction and tell me how to verify before committing

Give me that SELECT confirmation query first.
```

**Why it works:** "SELECT to confirm before UPDATE" is muscle memory for senior engineers. Seeing exactly which rows are affected, protecting with a transaction, and forcing a WHERE clause avoids the disaster of "forgot the WHERE and updated the whole table."

---

## 🚢 Deployment / DevOps

Deployment prompts focus on "reproducibility" and "don't leak secrets."

### 1. Write a Dockerfile

```
Write a Dockerfile for this project.

Requirements:
- Base image [e.g. node:20-alpine], as small as possible
- Use a multi-stage build to separate build from runtime
- Don't bundle dev dependencies, secrets, or .env
- Run as a non-root user

When done, explain each step line by line.
```

**Why it works:** Spelling out best practices (multi-stage, minimal image, non-root, no secrets) avoids the bloated, insecure default Dockerfile the AI might produce. Requiring line-by-line explanation keeps it understandable and editable.

### 2. Set up a CI pipeline

```
Set up a [GitHub Actions / GitLab CI] pipeline that, on every push:
1. Installs dependencies
2. Runs lint
3. Runs tests
4. (PRs only) runs a build check

Use caching to speed up dependency installs, and make any failed step abort the rest. Show me the config first; I'll review before enabling.
```

**Why it works:** Listing each CI stage explicitly stops the AI from missing key steps or getting the order wrong. "Fail-fast" and "caching" are CI basics — writing them out ensures the pipeline actually works and doesn't waste time.

### 3. Environment variables and secret management

```
This project has some config values hardcoded:
[paste relevant code]

Move them to environment variables:
- Create .env.example (keys only, no real values)
- Add .env to .gitignore
- Error clearly at startup if a required env var is missing

Never write any real secret value into the example file or the code.
```

**Why it works:** Hardcoded config and leaked secrets are the two big deployment landmines. This externalizes config, uses `.env.example` as documentation, and errors on missing values — solving portability and security at once, with an explicit no-leak rule.

### 4. Pre-deploy checklist

```
I'm about to deploy [project] to [platform, e.g. Vercel / AWS].

Don't do anything yet. Give me a pre-launch checklist covering:
- Are all environment variables set
- Do database migrations need to run first
- Any hardcoded localhost URLs / ports
- Is error monitoring / logging ready

Ask me about my current status item by item, and confirm all is OK before proceeding.
```

**Why it works:** Most deployment incidents come from "forgot one setting." A checklist systematically walks the easily-missed items, turning tacit deployment knowledge into explicit steps and drastically reducing launch failures.

### 5. Understand a deployment error

```
My deployment failed. Here's the log:
[paste the full deploy / build log]

Please:
1. Find the line that actually caused the failure (not the downstream cascade errors)
2. Explain the cause
3. Give me concrete fix steps

If there's not enough info to judge, tell me which other log to check.
```

**Why it works:** Deploy logs are long and noisy, and beginners get scared by walls of red text. Having the AI locate "the real line" and filter the cascade noise converges on the root cause far faster than searching blindly.

---

## 📝 Writing Docs

Docs are the most-skipped, most-regretted part of vibe coding. A good prompt makes the AI reverse-engineer accurate docs from the code.

### 1. Generate a README from the code

```
Based on this project's actual code, generate a README.md including:
- A one-line description
- A feature list (based on real code — don't invent features that don't exist)
- Install and start steps (copy-paste-able commands)
- A basic usage example

Describe only what actually exists in the code, and flag anything you're unsure about for me.
```

**Why it works:** Emphasizing "based on real code, don't invent" blocks the AI from hallucinating nonexistent features. Asking it to "flag uncertainties" lets you fill in context it can't read, producing genuinely accurate docs.

### 2. Write function / API doc comments

```
Add doc comments ([JSDoc / docstring / ...]) to this code:
[paste code]

For each function, describe:
- What it does (one line)
- The meaning and type of each parameter
- The return value
- What exceptions / errors it throws

Only add comments, don't change any logic.
```

**Why it works:** Explicitly listing what comments should cover (purpose, params, return, exceptions) avoids "// this is a function" garbage comments. The "comments only, no logic" constraint makes this a risk-free action.

### 3. Write usage examples

```
Write usage examples for [this function / API / package].

Requirements:
- Start with the simplest "minimal working example"
- Then give 2-3 examples for common scenarios
- Each example is complete and directly runnable — don't omit imports
- Annotate the expected output next to each example

The examples must actually run — no fictional usage.
```

**Why it works:** "Complete, runnable, imports included, expected output annotated" turns examples from "looks about right" into "actually runs." Progressing from minimal to common scenarios matches the reader's learning path.

### 4. Write a commit message

```
Here's my change:
[paste git diff or describe what changed]

Write a commit message in Conventional Commits format:
- Subject: type(scope): short description (imperative, under 50 chars)
- Body: explain "why" the change, not just "what"

Use one of feat / fix / refactor / docs / test / chore for type.
```

**Why it works:** Given a clear format (Conventional Commits) and the "explain why, not what" principle, commit messages become useful history. The length and type constraints keep messages tidy and consistent, easing later lookups and auto-generated changelogs.

### 5. Write an architecture doc

```
Write an architecture doc (ARCHITECTURE.md) to help new joiners understand the project quickly.

First read the main code, then explain:
- The overall architecture and data flow (from request in to response out)
- Each major module's responsibility
- Key design decisions and why they were made this way

Explain with text + a simple diagram (mermaid or ASCII). Lock onto the "big picture", don't explain line by line.
```

**Why it works:** Requiring the AI to "read the code first, then describe data flow and responsibilities" produces an architecture diagram that reflects reality, not a generic template. Focusing on the "big picture and design decisions" is exactly what new joiners need most but can least piece together from code alone.

---

## 🧠 General Prompting Principles

These aren't scenario-specific templates — they're general techniques that make *any* prompt more effective, stackable on top of all the categories above.

### 1. Assign a role and a standard

```
You are now a senior [domain, e.g. backend engineer / security expert]
with 10 years of hands-on experience, who values [maintainability / security / performance].

Handle my upcoming request with that identity and standard: [request].
```

**Why it works:** Specifying a professional role and value orientation anchors the AI's answers to the matching expertise and concerns. A "senior security expert" proactively thinks about boundaries and exploits; an engineer "who values maintainability" avoids clever-but-fragile code — the role directly shapes output quality.

### 2. Make it ask questions first

```
Before you start [task], ask me 3-5 clarifying questions whose answers
would affect how you do it.

Wait for my answers, then begin.
```

**Why it works:** Proactively asking the AI to ask spreads out its "silent assumptions" for you to confirm. Most rework comes from an early misunderstanding; a few upfront questions calibrate the direction and save endless back-and-forth later.

### 3. Make it explain its reasoning

```
Handle this request: [request].

Before giving the final answer, walk through your reasoning step by step and why you chose it.
If there are multiple approaches, list them with tradeoffs, then tell me which you recommend.
```

**Why it works:** Requiring "reason first, answer second" measurably improves accuracy on complex problems and shows you the basis for its judgment. When it lays out tradeoffs, you can intervene before it commits, rather than passively accepting the result.

### 4. Give examples (few-shot)

```
I want [output type, e.g. API response format / commit messages / naming].

Here are examples of the style I like:
[example 1]
[example 2]

Produce [count] more / handle my next input in the same style.
```

**Why it works:** Rather than describing the style you want in words (easy to misconvey), give examples directly. The AI is very good at extracting patterns from concrete samples — 2-3 examples often convey your expectation more precisely than a paragraph of adjectives.

### 5. Iterate instead of one-shotting

```
Let's do [task] iteratively.

Give me a rough first version (doesn't need to be perfect). I'll give feedback, and
we'll improve it round by round. Each round, only adjust based on my feedback — don't change other parts.
```

**Why it works:** Explaining a complex requirement perfectly in one go is nearly impossible. Declaring "iteration mode" and requiring "only change what I gave feedback on" stops the AI from rebuilding from scratch each time, letting the result converge steadily toward what you want instead of bouncing around.

---

## 🛡️ Guardrail Prompts (keep the AI from going off-script)

This category is for "locking things down" — preventing the AI from acting on its own and overstepping. Use them standalone or drop them into CLAUDE.md.

### 1. Plan-confirmation gate

```
From now on, before any action that modifies code, you must:
1. First explain what you intend to do and which files you'll touch
2. Wait for my explicit "go" or "OK" before acting

Until I agree, only discuss — don't modify.
```

**Why it works:** It inserts a human confirmation gate between "idea" and "action." This is the most effective guardrail — it gives you veto power before any change lands, completely eliminating "it finished changing things before I finished talking."

### 2. Freeze the file scope

```
For this task, you may only modify these files:
[list of files]

Don't touch any other file. If you think you need to change a file outside the list,
stop and tell me why, and let me decide — don't do it yourself.
```

**Why it works:** An explicit whitelist hard-locks the AI's blast radius. Its most dangerous behavior is "helpfully editing related files," and a file-level hard boundary directly cuts off that scope creep.

### 3. Minimal-change principle

```
Solve this problem with the "minimal change":
- Change only the few lines truly necessary
- Don't refactor, don't reformat, don't rename, don't touch unrelated code
- Don't "helpfully" optimize anything

If you really want to change something else, list it and ask me — don't just do it.
```

**Why it works:** The AI naturally loves to "optimize while it's in there," turning a small fix into a hundred-line diff that's hard to review and prone to new bugs. Emphasizing minimal change keeps the diff lean, focused, and trustworthy.

### 4. No deleting, no breaking

```
Rules:
- Don't delete any existing tests, comments, or features unless I explicitly ask
- Don't change the public interface (parameters, return values) of existing functions
- If your change might break existing behavior, warn me first

Proceed under these rules.
```

**Why it works:** Explicitly listing the "assets that must not be broken" (tests, interfaces, existing features) protects the things the AI tends to sacrifice to reach its goal. Naming what to protect beats discovering after the fact that it deleted your tests.

### 5. Ask, don't assume

```
For this task, if you hit anything uncertain
(unclear requirement, multiple approaches, missing info, an important technical choice),
stop and ask me — don't assume an answer and keep going.

I'd rather answer a few questions than have you guess wrong and build a pile of the wrong thing.
```

**Why it works:** The AI defaults to "filling the gap" — guessing an answer and barreling ahead, which means massive rework when the direction is wrong. Explicitly authorizing it to "stop and ask" blocks errors before they happen, far cheaper than redoing after the fact.

---

## 📋 CLAUDE.md Templates

`CLAUDE.md` (or Cursor's `.cursorrules`) is a "standing instruction" file in your project root that the AI reads on every conversation. Put the guardrails above in it, and you won't have to re-paste them every time.

> 💡 For a complete, ready-to-use template, see **[CLAUDE-md-template.md](./CLAUDE-md-template.md)**. Below are a few blocks you can grab individually.

### 1. Project overview block

```markdown
## Project Overview
- What this is: [one line]
- Stack: [language / framework / database]
- Entry point: [main file, e.g. src/main.ts]
- How to run: `[command]`
- How to test: `[command]`
```

**Why it works:** It gives the AI the full picture upfront, so it doesn't have to guess or rummage through files. Clear run/test commands also let it self-verify after making changes.

### 2. Code conventions block

```markdown
## Code Conventions
- Language version: [x.x], don't use deprecated syntax
- Style: follow the [ESLint / Prettier / Black] config
- Naming: [camelCase / snake_case ...]
- New code should follow the project's existing patterns and structure
```

**Why it works:** It turns style constraints into standing rules, avoiding every new file looking different. "Follow existing patterns" especially makes output blend into the existing codebase.

### 3. Guardrails block (most important)

```markdown
## Working Rules (follow strictly)
- Before modifying code, explain the plan and wait for my confirmation
- Apply the minimal-change principle; don't refactor or optimize on the side
- Don't delete existing tests / comments / features
- When uncertain, stop and ask me — don't assume
- Don't change the public interface of existing functions
```

**Why it works:** It makes the most effective guardrails standing rules, auto-locking every conversation without re-pasting each round. This is the most valuable part of a CLAUDE.md.

### 4. Don'ts block

```markdown
## Don'ts
- Don't install new packages I haven't approved
- Don't modify [config files / migrations / CI config] unless I explicitly ask
- Don't write secrets / API keys into code
- Don't generate a pile of unrelated "drive-by improvements"
```

**Why it works:** A blacklist explicitly marks high-risk actions. In practice, "don't do X" often constrains the AI's overreach more effectively than positive instructions.

### 5. Context hints block

```markdown
## Hints for the AI
- Important business logic lives in: [path]
- These files are sensitive, think twice before changing: [list]
- Common gotchas: [project-specific traps, e.g. always store time in UTC]
- Related docs: [links]
```

**Why it works:** Writing down the "things only veterans know" is like giving the AI an onboarding doc, drastically reducing its chances of stepping on project-specific landmines.

---

## 🔧 Tool Comparison

Different tools have different strengths. Match the scenario and you'll do twice the work in half the time.

| Tool | Best for | Strengths | Watch out |
|------|----------|-----------|-----------|
| **Lovable** | Building a Web app with UI from scratch, MVPs, quick prototypes for non-engineers | Full-stack generation (frontend + backend + DB), WYSIWYG, easy deploy | Limited customization depth; complex logic still needs manual work |
| **Bolt** | Turning an idea into a runnable full-stack prototype fast, live in-browser preview | In-browser live environment, fast generation, great for demos | Weaker maintainability for large projects; better for short cycles |
| **Cursor** | Working on an existing codebase, needing precise control over changes in an IDE | In-editor AI, reads the whole project context, `.cursorrules` guardrails, great for daily dev | Requires you to know how to code; depends on your prompting skill |
| **Claude Code** | Agentic dev in the terminal, multi-file refactors, automating run + test + debug flows | Reads/writes files, runs commands, `CLAUDE.md` standing rules, great for complex multi-step tasks | CLI-based, slightly steeper learning curve |

**How to choose:**

- 🆕 **No code yet, want to see results fast** → Lovable / Bolt
- 🛠️ **Existing project, making changes inside it** → Cursor / Claude Code
- 🧩 **Multi-file, multi-step, running tests and commands** → Claude Code
- 👀 **Want to tweak while watching the screen** → Lovable / Bolt / Cursor

---

## 🤝 Contributing

PRs welcome! New prompts, better explanations, even typo fixes — all appreciated.

1. Fork this repo
2. Add your template following the prompt format in **[CONTRIBUTING.md](./CONTRIBUTING.md)**
3. Make sure every prompt is **copy-paste ready** and **explains why it works**
4. Open a Pull Request

> One rule: quality over quantity. We take prompts that are *genuinely useful and clearly explained*, not filler.

See **[CONTRIBUTING.md](./CONTRIBUTING.md)** for the full format spec.

---

## ⭐ Found this useful?

If this prompt library saved you from a few pitfalls:

- Drop a **Star** ⭐ — it helps others find it (and it's the best encouragement for maintenance)
- **Share** it with friends who code with AI
- Got a better prompt? [Contribute it](./CONTRIBUTING.md) and help grow the list

> Your one star saves the next person — stuck on a prompt — half an hour.

---

<p align="center">The right prompt makes AI actually help 🚀<br><sub>Made for the vibe coding community.</sub></p>
