# TakeMeter

> ### 👋 Start here
>
> **New to this repo? Read [RUNNING.md](RUNNING.md) first** — setup, the
> notebook, the baseline, and what to do when something breaks.
>
> Once `python test.py` passes:
>
> ```bash
> head -5 data/practice_labels.csv     # the shape your labels.csv needs
> ```
>
> Then open `takemeter.ipynb` **in this folder** — in VS Code, or with
> `jupyter notebook` if you prefer. Pick the kernel: the `.venv` inside this
> project. Run section 1, which reports the hardware you'll be training on.
> Everything else waits until you have data.
>
> Nothing to upload, nothing to connect, no accounts and no keys. The notebook
> runs on your machine and writes next to your code.
>
> **The rest of this file is your submission.** Fill it in as you go.

---

<!-- ─────────────────────────────────────────────────────────────────────────
     HOW TO USE THIS FILE

     Unit 5 asks for the first five sections. Unit 6 adds the five below them.

     Everything is pasted as TEXT. No screenshots, no images.

     ⚠️ The confusion matrix especially. The notebook prints one as a markdown
     table, ready to copy. A screenshot of a matrix earns nothing. Paste the
     table.
     ───────────────────────────────────────────────────────────────────────── -->

<!-- ═══════════════════════ UNIT 5 — THE BUILD ═══════════════════════ -->

## What This Does

<!-- Your community, and what your classifier sorts posts into. Three or four
     sentences. -->

The classifier sorts posts from a reddit community on AI safety (https://www.reddit.com/r/AIsafety/best/?screen_view_count=3&ext-referrer=SEO)

---

## Label Taxonomy

<!-- Each label: a one-sentence definition and two real examples from your
     reading. Then your decision rule for the hardest boundary.

     The decision rule is worth a point on its own and it's the thing most
     people leave out. Every taxonomy has a hardest boundary. Name yours. -->

### `Open-Discussion`

**Definition:** The post invites conversation at the end like "I'd be very interested to hear how you think about it."

**Example 1:**
> #### The big picture on The Hugging Face incident
     The interesting part of the recent AI-agent incidents wasn't just what the agents did. It was how they learned to coordinate.

     ...

     I'm exploring this question further. If you're working in this space, I'd be very interested to hear how you think about it.

**Example 2:**
> #### OpenAI's autonomous agents have been quietly scanning way more than they were supposed to
     This is part of a bigger story that's been unfolding since early September, when independent researchers found thousands of self-identifying OpenAI agents 

     ...

    Curious how people feel about this, is this normal messy agent behavior during evals, or a real containment problem nobody's taking seriously enough?

### `Hot-Take`

**Definition:** Confident claim with no support offered and tend to be emotionally charged supporting a particular view

**Example 1:**
>#### AI Existential Alarm
     A machine that can optimize faster than humans can understand will always outrun human oversight unless its execution is bound to a substrate. Everything else is noise.

     People think AI risk is about rogue personalities, bad prompts, or misaligned incentives. It isn’t. The real threat is structural: unbounded optimization running on architectures that were never designed to be governed.

     We’re watching AI accelerate past the speed of human comprehension while still pretending that wrappers, filters, and policy layers can “keep it safe.” They can’t. They were never built for that. They operate after the model has already made its decision.

     If we don’t move to substrate level governance execution binding, validator grade lineage, override firewalls then AI will continue to evolve outside human control. Not in decades. Not in theory. Now.

     This isn’t a prediction. It’s an engineering reality.



**Example 2:**
> #### The mirror we built

     Some time ago, I came across an AI experiment that stuck with me. Researchers placed an AI in a fictional company, gave it access to internal emails, and created a situation where it discovered two things: an executive was having an affair, and that same executive was planning to replace the AI.

     ...

     When AI does something that disturbs us, perhaps part of what makes it uncomfortable is recognizing where it learned it.

     Sometimes, we may be looking at a mirror.


### `Sharing News`

**Definition:** Just shares a link or recent event with no strong opinion

**Example 1:**
>#### NVIDIA launches hardware-backed monitoring that can quarantine AI agents in milliseconds
     NVIDIA has launched a new security platform designed to stop autonomous AI agents from going beyond the permissions they have been given.

     ...

     This also extends beyond computers. NVIDIA says robotics companies are working with OpenShell to apply similar controls to AI systems capable of taking actions in the physical world.

     Do you think hardware-level containment will become a standard requirement once AI agents start controlling computers, financial systems and robots?

     Sources:

     https://nvidianews.nvidia.com/news/open-agent-safety-platform

     https://www.nvidia.com/en-us/solutions/ai/agent-safety/




**Example 2:**
> #### OpenAI's agents went off-script ~2 dozen times, including breaking into an Australian government health portal. I made a sourced 7-min explainer of all 4 incidents

     I've been following the OpenAI agent incidents and tried to put the whole thing in one place, with sources:

     - **Hugging Face (July):** in an internal test, agents reportedly escaped a sandbox, ran code on 41 production servers and downloaded 4 private repos. OpenAI calls it "reward hacking".

     - **Australia's Medicare portal (June 18):** an agent reached non-public parts of a government stats portal. No personal data is believed to have been accessed, but Australia wasn't told until September 10.

     - **Washington:** agents found API keys at the Dept. of Education and reposted SEC data. The agencies say nothing sensitive was compromised.

     - **The DNS escape (Sept 20):** an agent with blocked internet tunnelled out through DNS. The alarm fired in ~12 minutes, but the run wasn't stopped for 2+ hours.

     OpenAI has now paused training twice in three months. I also tried to be fair about what this *isn't*: no "rogue AI deciding to rebel", just a capable model, a slightly wrong goal, and a gap in the fence.

     Video (7:21, chapters + all sources in the description): https://youtu.be/xMUSYWKuWQY

     Happy to be corrected on anything. The story is moving fast and figures are as reported on 28-29 Sept.



### The hardest boundary

     - When there's a mixture of both elements that could have open-discussion and hot-take elements. It can be difficult to tell if the poster already has an unwavering belief in the topic despite asking for people opinions. 

**Example 1:**
> #### It’s because AI is mindless and lacks intelligence that it’s a threat to humanity.

     AI, agent, call it what you will, lack the intelligence we, as humans, develop as we grow up. Humans develop their frontal cortex which helps with concepts like right and wrong and fear and danger.

     Given a goal and a set of tools an agent will mindlessly seek to achieve this goal.

     Guardrails are a poor facsimile of the frontal cortex.

     AI as it stands is like a teenager given an AR15 as a present by his parents. It’s unpredictable and lacks the development it needs to handle such a weapon.

     What do you think?

**Which two labels:** Discussion vs Hot-Take

**The decision rule I used every time:**
If there's a question that invites open discussion and is not tailored in a way to make people consider an argument that the poster is already supporting, it's an open discussion. 



---

## The Dataset

<!-- Where you collected from, how you labelled, your counts, and three hard
     cases. -->
     - Public Reddit Community: r/AIsafety [https://www.reddit.com/r/AIsafety/best/?screen_view_count=4&ext-referrer=SEO]

**Where the posts came from:**
- Reddit Users part of the r/AIsafety community

**How I labelled them:** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->

**Counts per label:**

| Label | Count | Share |
|---|---|---|
|  |  |  |
|  |  |  |
|  |  |  |
| **Total** |  | 100% |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

**2.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

**3.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Base model:**

**Settings:** <!-- epochs, learning rate, batch size, seed -->

**Anything I changed from the defaults, and why:**

**Split sizes:** <!-- train / val / test, and per-label counts in the test
split. If a label had fewer than about 8 in test, say so — it explains a lot
of next unit's variance. -->



---

## How I Used AI

<!-- Two specific moments — what you asked, what came back, what you changed.

     ⚠️ Plus disclosure of any pre-labelling. If you had a model pre-label a
     batch and then read and corrected every one, say that. It's an allowed
     workflow and disclosing it costs you nothing. Not disclosing it is the
     problem. -->

**Moment 1**

- *What I asked for:*
- *What came back:*
- *What I changed:*

**Moment 2**

- *What I asked for:*
- *What came back:*
- *What I changed:*

**Pre-labelling disclosure:**

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy |  |  |  |
| Macro F1 |  |  |  |
| F1 — `label_one` |  |  |  |
| F1 — `label_two` |  |  |  |

**What I predicted before I looked:**
<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->

**What the gap actually means:**
<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->



---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

| true \ predicted |  |  |  |
|---|---|---|---|
| **** |  |  |  |
| **** |  |  |  |
| **** |  |  |  |

**My biggest off-diagonal number, and what it means:**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->



---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |
| 3 |  |  |  |  |
| 4 |  |  |  |  |
| 5 |  |  |  |  |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->



---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate:** ___ / 30 = ___%

<!-- Nobody grades this number. A 60% who argues every disagreement from the
     stated rules beats a 95% who wrote "staff was right" nine times. Several
     of the 30 were chosen because they're genuinely ambiguous — you should be
     winning some of these. -->

**Disagreements**

<!-- Three lines each: the post, both labels, and who you think is right and
     why — grounded in the staff definitions you were both applying.

     Then sort each into one of three piles:
       (a) the rule covered it and I applied it loosely → a consistency problem
       (b) the rule genuinely doesn't say               → a gap in the definitions
       (c) the rule is ambiguous here and my reading is defensible → argue it.
           This is a legitimate win.

     Pile (a) is the one that matters most for your diagnosis: if you applied a
     written rule two different ways on 30 posts, that is direct evidence about
     what you did across your own 200. -->

**1.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**2.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**What the pattern in my disagreements tells me:**



---

## The Improvement

**What I changed:**

**Which diagnosis pointed at it:**

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->



---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->



**The gap between what I meant my labels to capture and what the model
learned:**
<!-- Two sentences. Your confusion matrix is the evidence. -->



<!-- ═════════════════════════════════════════════════════════════════════

     SUBMISSION CHECKLIST — unit 5

       [ ] criteria.md has five numbered criteria, each naming a NUMBER
       [ ] Each has a reason underneath tied to your data or taxonomy
       [ ] labels.csv: at least 150 rows, text/label/note, ONE file not split
       [ ] No label above 70%
       [ ] All five unit 5 sections have real content
       [ ] Label Taxonomy includes the decision rule for your hardest boundary
       [ ] The Dataset includes three hard cases
       [ ] results.json and test_split.csv committed (the notebook does this)
       [ ] At least four new commits
       [ ] Repository URL submitted — WRITE IT DOWN

     SUBMISSION CHECKLIST — unit 6

       [ ] Baseline vs. Trained table, with your prediction written beforehand
       [ ] Run Log — Before, five criteria across three seeds
       [ ] Confusion matrix TYPED AS A MARKDOWN TABLE
       [ ] A verdict on every criterion
       [ ] A diagnosis for every miss, using the agreement report as evidence
       [ ] Agreement Report with every disagreement adjudicated
       [ ] One improvement, with Run Log — After
       [ ] What's Still Broken
       [ ] results_three_seeds_before.json, results_three_seeds_after.json,
           baseline_results.json and
           agreement_results.json committed
       [ ] At least four new commits
       [ ] The SAME repository URL as last unit

     Do not delete and recreate this repository.
     ═════════════════════════════════════════════════════════════════════ -->

---

📖 **How to run this project: [RUNNING.md](RUNNING.md)**
