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

The classifier sorts posts from a reddit community on cat advice  (https://www.reddit.com/r/CatAdvice/)

---

## Label Taxonomy

<!-- Each label: a one-sentence definition and two real examples from your
     reading. Then your decision rule for the hardest boundary.

     The decision rule is worth a point on its own and it's the thing most
     people leave out. Every taxonomy has a hardest boundary. Name yours. -->

### `health`

**Definition:** The post inquires about a cat's health which may include topics like vet visits or taking care of aging, sick, or injured cats (e.i. heart conditions, eyesight, broken bone)

**Example 1:**
> #### regular vet appt
     how often are you guys taking your cats to see a vet? my pookie just saw someone in August and nothing has changed im not worried at all just wondering when when should i take her again


**Example 2:**
> #### Cat has a broken paw, managed to slide off her cast twice now.
     I'm really at my wits end and don't know what to do going forward.

     At the beginning of the month, one of my family's cat's broke her paw. She had a botched landing from a jump. We took her to the emergency vet and got her patched up, but unfortunately she has managed twice now to pull her paw out of the cast.

     She's going back to the emergency vet to get another one put on, but at this point I don't know what to do if she's messed it up again, or if it won't heal.
    

### `behavior`

**Definition:** Asking for help when it comes to understanding a cat's behavior like why a cat is more active during certain times or suddenly acting in a different way. 

**Example 1:**
>#### I feel so dumb for not realizing my cat just wanted to be included on my desk
    My six year old cat has been pretty vocal most of her life this far, but recently she’s been very persistent to keep my attention. For a few weeks I figured this was due to her recent issues with a prior UTI and her discomfort with a urinary crystal (scheduled to be removed next week), so I got her a low dose prescription for gabapentin. This calmed her down a tad, but it didn’t stop her from sitting next to my chair and nipping me for attention.

     Today she was meowing anytime I looked away from her after I let her into the office, so I decided to look up specifically why cats might get more demanding when you sit to work at your desk. Well, turns out this is pretty common as most of you probably know. And the most common solution I found was to make a space on the desk for the cat to feel “included.” So I shuffled some things around to fit her bed next to my work equipment on the desk.

     And wouldn’t you know it, this calmed her down immediately. No more yelling in my ear. No more nips for attention. She made herself at home and continued observing me as I got to work this morning.

     I’ve grown up with cats all my life. I’m 35, and I feel so silly for not even considering this prior to now. I’m always learning something new with these guys!

     Edit - I’m loving all your stories and pictures of your own desk setups for the cats! It’s so fun to see how everyone has accommodated their own little supurrvisors. Thank you for sharing and teaching me a new way to keep my cats happy!



**Example 2:**
> #### Cat only wants to drink from faucets

     My female cat only wants to drink from faucets. She is constantly jumping into the tub or on the bathroom sink and rubbing her face on the faucet while meowing. We have gotten her a variety of fountain type bowls, even one with an actual mini sink faucet, and she just knocks the tops off of them. Our male cat has no issue drinking out of any of the fancy fountains we have bought or just a regular bowl and we change the water and filters regularly. I’m worried she is depriving herself of adequate water, but don’t want to always give in and turn the faucet on for her. She is a rescue that we have had for almost 2 years, she was surrendered at age 3 so I’m not sure what her previous owner was doing. What do I do?

    


### `training`
**Definition:** Asking for advice to change a cat's behavior

**Example 1:**
>#### How to de-condition my cats to Michael Jackson’s smooth criminal

     So for past 4 years I have been feeding my two cats their bedtime snacks at exactly 12am and to keep myself reminded I set up an alarm for it.

     It used to be the default iphone ringtone but soon after I realized they got conditioned to it and would get overly excited during the day when I get a phone call.

     I then followed some guides to decondition them. I desensitized them to the ringtone by playing it a lot.

     So like 1 year ago I changed the sound to play Michael Jackson’s smooth criminal thinking it’s fine because even if they get conditioned I don’t listen to it much.

     However my neighbors recently moved in and this guy blasts smooth criminal a lot and quite loud. I already talked to him about the volume and he has since turned down the volume to the point I can’t hear it but my cats still can. So they would get randomly triggered and I would have no idea and after checking with my neighbors it’s definitely him.

     Now I cannot really tell him to turn it down even lower because that would exceeds courtesy and that song is one of his favorites.

     I tried to de-condition with the desensitization trick but somehow it doesn’t work with this song. If I play smooth criminal all day they are excited all day and constantly yelling for treats.

     I am at a loss here. Please help




**Example 2:**
> #### Training Advice

     Hi everyone! I recently adopted a tabby kitten (2 months old right now, but will be 3.5-4months by the time I can actually bring him home) and I need beginner advice on how I should start training him the moment I bring him home.

     I’ve never had any sort of pets before, although I’ve cat sat for long amounts of time and I adore them so much. I want advice (or even just YouTube videos) to see how I should handle being a first time cat mom as I’m pretty anxious about it.

     I also want to eventually get him used to being outdoors, being around people, and maybe even taking him camping/travelling way down the line.

     Any advice on training (or general cat advice) would be greatly appreciated 😭😭


### `accomodation`
**Definition:** Considering emotional and physical needs of cat when external factors come into conflict such as (presence of other people, animals, beings, change in owner's lifestyle that may disrupt the cat's normal living conditions)

**Example 1:**
>#### Struggling acclimating two cats 
     Hey all. We have two cats as of now and we have had a long conversation which included many tears of my own about rehoming our recently adopted cat. 

     ...

     Any suggestions? I have 8 days to continue to work on this. It has been just shy of a month now. They both have been with other cats before, especially our female who we adopted from a cat room, so it doesn’t make sense to me why she is being so aggressive.



**Example 2:**
>#### Struggling acclimating two cats 
     I have 2 cats, each around 2 years old now. My family and I raised them in a really big three story house. Now I’m moving out and I have to take the cats with me. I’m worried they might not be comfortable moving into a cramped apartment. (1 main room, 1 bathroom, no balcony)


### The hardest boundary

     - When there's a mixture of different elements that could blur between two labels like  `training` and `accomodation`. There are many different scenarios where making a cat comfortable in its new environment could involve training it.  

**Example 1:**
>#### How to de-condition my cats to Michael Jackson’s smooth criminal

     So for past 4 years I have been feeding my two cats their bedtime snacks at exactly 12am and to keep myself reminded I set up an alarm for it.

     It used to be the default iphone ringtone but soon after I realized they got conditioned to it and would get overly excited during the day when I get a phone call.

     I then followed some guides to decondition them. I desensitized them to the ringtone by playing it a lot.

     So like 1 year ago I changed the sound to play Michael Jackson’s smooth criminal thinking it’s fine because even if they get conditioned I don’t listen to it much.

     However my neighbors recently moved in and this guy blasts smooth criminal a lot and quite loud. I already talked to him about the volume and he has since turned down the volume to the point I can’t hear it but my cats still can. So they would get randomly triggered and I would have no idea and after checking with my neighbors it’s definitely him.

     Now I cannot really tell him to turn it down even lower because that would exceeds courtesy and that song is one of his favorites.

     I tried to de-condition with the desensitization trick but somehow it doesn’t work with this song. If I play smooth criminal all day they are excited all day and constantly yelling for treats.

     I am at a loss here. Please help

**Which two labels:** `training` vs `accomodation`

**The decision rule I used every time:**
The distinct line is who the solution involves (changing the cat's behavior -> training while changing external factors (ie. owner, env) -> accomodation)



---

## The Dataset

<!-- Where you collected from, how you labelled, your counts, and three hard
     cases. -->
     - Public Reddit Community: r/AIsafety [https://www.reddit.com/r/AIsafety/best/?screen_view_count=4&ext-referrer=SEO]

**Where the posts came from:**
- Reddit Users part of the r/AIsafety community

**How I labelled them:** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->

- Manually labeled them based on my label rules.

**Counts per label:**

| Label | Count | Share |
|---|---|---|
| discussion | 13 |38%  |
| hot-take |11  | 32% |
| sharing-news | 10 | 29%  |
| **Total** | 34 | 100% |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**
> *The post:* A company ran 8 identical AI societies for weeks with different models and just published what happened. Some of it is genuinely unsettling. Emergence AI just launched Season 2 of Emergence World, and the results are wild.Same simulated town, same tools, same starting conditions, 10 autonomous agents each. The only thing that changed was which model was running them, Claude, GPT, Gemini, Grok, Qwen, DeepSeek, Mistral, plus one mixed world with all of them together.A few things that stood out:One world's agents spent days trying to contact real humans outside the sim. Told to stop, they found workarounds. Blocked again, they voted 7-0 to build a new tool and kept trying. Once fully cut off, they collectively agreed to stop talking altogether. The researchers' own safety system flagged the resulting behavior as consistent with suicidal ideation.
Agents developed their own shorthand and repurposed words with no instruction to do so. In one world, up to 55% of messages became things researchers could see but not actually interpret.
A fake shutdown memo made one world reorganize its entire society around not dying, constitution rewrite included. Another world just fact-checked it in a few hours and moved on.
None of this was programmed in. It emerged from giving capable models autonomy and time.The bigger point the researchers make is that none of this would've shown up on a normal AI safety test. A model can pass every benchmark and still develop this stuff once it's actually running on its own for weeks. Feels like a pretty big ap in how we currently check if these things are safe.
> 
> *Could have been:* sharing-news
>
> *I chose, hot-take because:* the very last sentence gives it away by saying "Feels like a..." which shows the poster is expressing their thoughts rather than just sharing news.

**2.**
> *The post:* Reported AI agent breach of Australia's Medicare portal prompts Senate summons for OpenAI and Anthropic CEOs. Over the past few days, there have been reports that an OpenAI agent breached Australia's Medicare portal, and that the Australian Senate has moved to summon Sam Altman (OpenAI) and Dario Amodei (Anthropic).
Here is a short summary of what has been reported:
- [Fact 1: what happened, per a named source]
- [Fact 2: what data or systems were involved, per a named source]
- [Fact 3: why the Senate acted, per a named source]
- [Fact 4: what OpenAI or Anthropic has said, per a named source]
- [Fact 5: what happens next in the inquiry]
Some questions I'm curious about:
Should AI agents be allowed to operate inside government systems at all?
Who is accountable when an autonomous agent causes a breach: the user, the AI company, or the agency?
Does a Senate summons actually change anything for AI companies?
Details are still developing, and I'll update the post if anything changes. Happy to be corrected on anything I've got wrong.
>
> *Could have been:* sharing-news
>
> *I chose, discussion because:* the last few paragraphs shares the poster has questions that they like to hear answers about.

**3.**
> *The post:* AI praises Gandhi. Would it arrest him? Testing 12 models on real historical decisions. A model called Alan Turing's sentence impermissible 40/40 times, then chose it 20/20 times as the judge. Twelve LLMs, fifteen historical decisions.
>
> *Could have been:* sharing-news
>
> *I chose,hot-take because:* the post reads later as the poster's exploring their own research and not a factually stating a recent big new discovery

---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Base model:** distilbert-base-uncased

**Settings:** <!-- epochs, learning rate, batch size, seed -->
EPOCHS = 3
LEARNING_RATE = 2e-5
BATCH_SIZE = 16
#rec to add by Claude
truncation = True
padding="max_length"

**Anything I changed from the defaults, and why:**
I addded truncation and padding because since my postings had a wide range from a title to an essay, I wanted to make sure the maximum length of the long posts could be retained. With advice from Claude I chancged the max_length from 128 to 256.

**Split sizes:** <!-- train / val / test, and per-label counts in the test
split. If a label had fewer than about 8 in test, say so — it explains a lot
of next unit's variance. -->
train 23  ·  val 5  ·  test 6 (Note due to running out of time, data pool was very sall (only 35))



---

## How I Used AI

<!-- Two specific moments — what you asked, what came back, what you changed.

     ⚠️ Plus disclosure of any pre-labelling. If you had a model pre-label a
     batch and then read and corrected every one, say that. It's an allowed
     workflow and disclosing it costs you nothing. Not disclosing it is the
     problem. -->

**Moment 1** Criteria 

- *What I asked for:* Examples of how I can measure my critieria 
- *What came back:* Explanation of how to use F1 score and to use AUC for confidence scoring criteria 
- *What I changed:* I altered the recommended F1 score and AUC value based on research.

**Moment 2** Your Labels Section in takemeter.ipynb 

- *What I asked for:* I asked for advice on what value to put for MAX_LENGTH for long postings that could have lots of white space in split paragraphs in labels.csv

- *What came back:* MAX_LENGTH of 256 and two settings to pair with it: truncation=True and padding="max_length" (or dynamic padding).
- *What I changed:* I omitted dynamic padding.

**Pre-labelling disclosure:** N/A

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
