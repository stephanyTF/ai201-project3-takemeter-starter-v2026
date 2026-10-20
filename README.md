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

**Definition:** The post inquires about a cat's health which may include topics like vet visits or medical symptoms (heart conditions, eyesight, broken bone, sickness)

**Example 1:**
> #### regular vet appt
     how often are you guys taking your cats to see a vet? my pookie just saw someone in August and nothing has changed im not worried at all just wondering when when should i take her again


**Example 2:**
> #### Cat has a broken paw, managed to slide off her cast twice now.
     I'm really at my wits end and don't know what to do going forward.

     At the beginning of the month, one of my family's cat's broke her paw. She had a botched landing from a jump. We took her to the emergency vet and got her patched up, but unfortunately she has managed twice now to pull her paw out of the cast.

     She's going back to the emergency vet to get another one put on, but at this point I don't know what to do if she's messed it up again, or if it won't heal.
    


### `training`
**Definition:** The poster wants to teach or change a specific, repeatable behavior through deliberate practice, rewards, or correction. The focus is the behavior, not the cat's comfort with a new situation. Some examples may include potty training, being harnassed on a leash for walks, or using a clicker. 

**Example 1:**
>#### Help with Kitten training

     I recently rescued a kitten that was outside in the AZ summer heat. I do not know how old he is (he looks really young)and I am currently working on getting him to trust me and my other dogs that I currently have, and how to use the litter box and was wondering if anyone had any tips or help that I could use. This is my first cat and I just wanna make sure I’m doing things right for him.



**Example 2:**
> #### Training Advice

     Hi everyone! I recently adopted a tabby kitten (2 months old right now, but will be 3.5-4months by the time I can actually bring him home) and I need beginner advice on how I should start training him the moment I bring him home.

     I’ve never had any sort of pets before, although I’ve cat sat for long amounts of time and I adore them so much. I want advice (or even just YouTube videos) to see how I should handle being a first time cat mom as I’m pretty anxious about it.

     I also want to eventually get him used to being outdoors, being around people, and maybe even taking him camping/travelling way down the line.

     Any advice on training (or general cat advice) would be greatly appreciated 😭😭


### `acclimation`
**Definition:**  Focus on owners introducing new cats to home, getting used to resident cats or other cats, or a new living location.


**Example 1:**
>#### Struggling acclimating two cats 
     Hey all. We have two cats as of now and we have had a long conversation which included many tears of my own about rehoming our recently adopted cat. 

     ...

     Any suggestions? I have 8 days to continue to work on this. It has been just shy of a month now. They both have been with other cats before, especially our female who we adopted from a cat room, so it doesn’t make sense to me why she is being so aggressive.


**Example 2:**
>#### Struggling acclimating two cats 
     I have 2 cats, each around 2 years old now. My family and I raised them in a really big three story house. Now I’m moving out and I have to take the cats with me. I’m worried they might not be comfortable moving into a cramped apartment. (1 main room, 1 bathroom, no balcony)




### The hardest boundary

     - When there's a mixture of different elements that could blur between two labels like  `training` and `acclimation`. There are many different scenarios where making a cat comfortable in its new environment could involve training it to adjust. 

**Example 1:**
> Advice on acclimating two cats 
     Me and my boyfriend are about to move in together and we both have cats. I have a 10 year old girl and he has a 2 year old boy. His cat got in a street fight before coming to live with him. We are worried that he is going to try to fight her because he likes to growl at cats outside. Any advice on how to make sure they can live peacefully together? Neither of us want to give up our babies

**Which two labels:** `training` vs `acclimation`

**The decision rule I used every time:**
If the cat is adjusting to a change (new home, new pet, new routine) and the poster wants it to feel comfortable → acclimation.
If the poster wants a specific behavior from the cat, even in a new setting → training.
If both apply, label by the poster's main question: "How do I make them comfortable?" vs. "How do I get them to do or stop X?"



---

## The Dataset

<!-- Where you collected from, how you labelled, your counts, and three hard
     cases. -->
     - Public Reddit Community: r/CatAdvice  [https://www.reddit.com/r/CatAdvice/]

**Where the posts came from:**
- Reddit Users part of the r/CatAdvice community

**How I labelled them:** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->

- Manually labeled them based on my label rules.

**Counts per label:**

| Label | Count | Share |
|---|---|---|
| training  | 50  | 32% |
| health | 50 | 32%  |
| acclimation | 55 |  35% |  
| **Total** | 155 | 100% |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**
> *The post:*So for past 4 years I have been feeding my two cats their bedtime snacks at exactly 12am and to keep myself reminded I set up an alarm for it.
It used to be the default iphone ringtone but soon after I realized they got conditioned to it and would get overly excited during the day when I get a phone call.
I then followed some guides to decondition them. I desensitized them to the ringtone by playing it a lot.
So like 1 year ago I changed the sound to play Michael Jackson’s smooth criminal thinking it’s fine because even if they get conditioned I don’t listen to it much.
However my neighbors recently moved in and this guy blasts smooth criminal a lot and quite loud. I already talked to him about the volume and he has since turned down the volume to the point I can’t hear it but my cats still can. So they would get randomly triggered and I would have no idea and after checking with my neighbors it’s definitely him.
Now I cannot really tell him to turn it down even lower because that would exceeds courtesy and that song is one of his favorites.
I tried to de-condition with the desensitization trick but somehow it doesn’t work with this song. If I play smooth criminal all day they are excited all day and constantly yelling for treats.
I am at a loss here. Please help
> 
> *Could have been:* `acclimation` 
>
> *I chose `training` because:* the cat owner is focused on changing their cat's behavior. Despite the trigger being an external factor (the neighbor), the part where the cats have to reassociate a different sound to their "bedtime snacks" would be considered training. 

**2.**
> *The post:* Me and my boyfriend are about to move in together and we both have cats. I have a 10 year old girl and he has a 2 year old boy. His cat got in a street fight before coming to live with him. We are worried that he is going to try to fight her because he likes to growl at cats outside. Any advice on how to make sure they can live peacefully together? Neither of us want to give up our babies
>
> *Could have been:* `training`
>
> *I chose, `acclimation` because:* these are the cats first time living together and that's still involved in creating a space on the owner ends where they're able to gradually set up a peaceful interaction between the cats

**3.**
> *The post:* Adult stray sick cat I have a neighborhood stray that I have been feeding on occasion. ... So to summarize what do i do to get this cat to be more comfortable with me (i intend to adopt or at the very least foster) how do I prevent my current two cats from getting sick cat litter training? what to do for sickness between now and monday need info on anything i might be not considering that is required.
>
> *Could have been:* "training"
>
> *I chose, "health" because:* eventhough the world training was mentioned, it's not the focus. The focus is on how to treat a sick cat while the "training" is a small afterthought.

---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Base model:** distilbert-base-uncased

**Settings:** <!-- epochs, learning rate, batch size, seed -->
EPOCHS = 3
LEARNING_RATE = 2e-5
BATCH_SIZE = 16


**Anything I changed from the defaults, and why:**
I changed nothing. Kept the defaults because the posts didn't had any unique features to accommodate for. 

**Split sizes:** <!-- train / val / test, and per-label counts in the test
split. If a label had fewer than about 8 in test, say so — it explains a lot
of next unit's variance. -->
train 88  ·  val 19  ·  test 20 (Note due to running out of time, data pool was very sall (only 127))



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

**Moment 2** Missing Training data from Train/Test split 

- *What I asked for:* I asked why does my 30 training labeled rows not end up at all in the train, val, nor test set.

- *What came back:* It thinks the table display is cut off and there may not be an exact match in label string which may have resulted in it getting dropped
- *What I changed:* I decided to let it be

**Pre-labelling disclosure:** N/A

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure | Seed 42 | Seed 7 | Seed 2024 | Spread |
|---|---|---|---|---|
| Overall accuracy | 0.375 | 0.417 | 0.417 | 0.042 |
| Macro F1 | 0.246 | 0.311 | 0.311 | 0.065 |
| F1 — `health` | 0.222 | 0.400 | 0.400 | 0.178 |
| F1 — `acclimation` | 0.516 | 0.533 | 0.533 | 0.017 |
| F1 — `training` | 0.000 | 0.000 | 0.000 | 0.000 |

**What I predicted before I looked:**
<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->
     I think my trained model will not beat it because despite less categories than before and the size of the data is now 150 rows, there's still variation in each post despite their labels so the model may not be able to pick up a strong pattern.


**What the gap actually means:**
<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->
The trained model seem to perform worse than the acclimation for all labels. This may mean that acclimation is poorly worded for the baseline. 


---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->


| Measure | Seed 42 | Seed 7 | Seed 2024 | Spread |
|---|---|---|---|---|
| Overall accuracy | 0.375 | 0.417 | 0.417 | 0.042 |
| Macro F1 | 0.246 | 0.311 | 0.311 | 0.065 |
| F1 — `health` | 0.222 | 0.400 | 0.400 | 0.178 |
| F1 — `acclimation` | 0.516 | 0.533 | 0.533 | 0.017 |
| F1 — `training` | 0.000 | 0.000 | 0.000 | 0.000 |


| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1. Overall Accuracy of Post Labeling |.6 |  .375 | .417 |.417  |  NOT MET
| 2.  No label performance may be less than rest of the other labels | -/+ .2 max | -/+ .042 max | -/+ .042 max | -/+ .042 max | MET
| 3. Balance in Label Representation  | 20-30% Rep for each label | 32 | 32 | 35 | MET 
| 4. Consistent Labeling | .7 | .3 | .2 | .25 | NOT MET 
| 5.  Confident Labeling  | AUC Score >= .7 | ~ | ~ | ~  | NOT MET (may need to revise)

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

| true \ predicted | health | acclimation | training |
|---|---|---|---|
| **health** | 1 | 7 | 0 |
| **acclimation** | 0 | 8 | 0 |
| **training** | 0 | 8 | 0 |

**My biggest off-diagonal number, and what it means:**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->
     7 real `health` and 8 real training posts were misclassifed as  `acclimation`

---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 | Overall Accuracy of Post Labeling | .6 | NOT MET | Based it off the accuracy from the Run Log |
| 2 |  No label performance may be less than rest of the other labels | -/+ 30% max | MET | Based from Run Log |
| 3 | Balance in Label Representation |20-30% Rep for each label  | ~ | Not able to assess from run log nor results |
| 4 | Consistent Labeling | .7 | NOT MET  | Based on accuracy scores (may need revision to differentiate from Accuracy Criteria)  |
| 5 | Confident Labeling | AUC score of at least .7 | NOT MET |  Immeasurable since no AUC is given in the tables or output   |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->

1. Overall Accuracy of Post Labeling: Not clearly defined labels and possibly not enough data (127/200)
3. Balance in Label Representation: Critierion was measured based from Unit 5 in examining data structure.-
4. Consistent Labeling: Critierion couldn't be measured based from run log and results
5. Confident Labeling: Critierion couldn't be measured based from run log and results


---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate:** 26 / 30 = 87%

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
> *The post:* "Pulled the splits from the last five editions. The winning time has moved by 40 seconds total in ten years, but the 100th-place time is four minutes faster. The depth changed, the front didn't."
>
> *Staff said `analysis` / I said: `hot_take`*
>
> *My call, and why:*
The confident ending made me think it was a hot-take and the numbers were just being used to flash it off as analysis. However I agree it's analysis and I was applying the rule loosely. 
>
> *Which pile:* a)  the rule covered it

**2.**
> *The post:* "The club championship scoring changed in 2019 from top-6 to top-10. Since then our B team has finished above the A team twice. That's not depth improving, it's the scoring rewarding turnout."
>
> *Staff said `analysis` / I said: `hot_take`*
>
> *My call, and why:* The confident ending and the statistical info in the post doesn't seem the correlate well with the claim made (I'm not clear with what the claim even is, is it to show that Team B peforms better than A?). Even if the top pool changed from 2019, I'm not sure what the current date the poster is in and how many times both Team A and B has competeted to see if winning two times is significant. Example if Team B finished above 2 out 5 times, it's not that impressive. Hence that's why I believe it's hot-take because the evidence doesn't seem strong and the confident ending to make it lean that way.
>
>
> *Which pile:* c) the rule is ambiguous here and my reading is defensible.



**3.**
> *The post:* "Carbon plates aren't the whole story. My times dropped 2% in the shoes and another 2% the following year in the same pair, when the only thing that changed was going from 35 to 50 miles a week."
>
> *Staff said `analysis` / I said: `hot_take`*
>
> *My call, and why:* I may have been judging the quality of the analysis since there's not another comparable example in another pair of shoes to show that carbon plates are not a huge factor. However the first sentence doesn't argue out right that carbon plates doesn't affect their running, only admits it's not the whole story so I would relabel this as `analysis`.
>
> *Which pile:* a) the rule covered it




**4.**
> *The post:*  "Three of us ran the same session on the same day, different shoes, within 10 seconds of each other over 5 miles. I'm not saying shoes do nothing, but whatever they do was smaller than the noise between three people."
>
> *Staff said `analysis` / I said: `hot_take`*
>
> *My call, and why:* I'm not sure what the poster mean by "the noise" between three people. Since it's part of their claim and there was no checkable evidence at all for this, I would still consider this a `hot_take`
>
> *Which pile:* a)  the rule covered it

**What the pattern in my disagreements tells me:**
Some of the analysis labeled posts can be mistaken for hot-takes because of the way the post is written, it can make it sound that the fact inserted are used loosely. 


---

## The Improvement

**What I changed:** 

**Which diagnosis pointed at it:** Biggest confusion: 8 real `training` posts called `acclimation`.
The other direction: 0 real `acclimation` posts called `training`.

That's lopsided — the model leans toward `acclimation` on this pair.
A direction like that usually points at your labelling rather than the
model. Your agreement report is the thing that can tell you which.

### Run Log — After

| Measure | Seed 42 | Seed 7 | Seed 2024 | Spread |
|---|---|---|---|---|
| Overall accuracy | 0.704 | 0.593 | 0.630 | 0.111 |
| Macro F1 | 0.703 | 0.588 | 0.586 | 0.117 |
| F1 — `health` | 0.714 | 0.615 | 0.667 | 0.099 |
| F1 — `acclimation` | 0.667 | 0.615 | 0.727 | 0.112 |
| F1 — `training` | 0.727 | 0.533 | 0.364 | 0.364 |

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1. Overall Accuracy of Post Labeling | .6 | .7 |.6  | .6 | MET
| 2. No label performance may be less than rest of the other labels | .2-.3 MAX | .06 max | .082 max | .363 max  | NOT MET
| 3. Balance in Label Representation  | 20-30% Rep for each label | .3 | .3 | .3 | MET
| 4. Consistent Labeling | .7 | .7 | .6 | .7 | NOT MET 
| 5.  Confident Labeling  | AUC Score >= .7 | ~ | ~ | ~  | NOT MET (may need to revise)

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->
Refining definitions, relabeling, and adding more postings helped since the results in the 2nd run had a major differenc than the first run. Despite the small change (4) rows were relabelled and the total number of postings from 155 were increased to 174 were relabeled so perhaps the change was significant enough to make a distinctive change. 


---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->
For below the reason for all of them of why I was unable to implement what I missed was due to time constraint.

1. Overall Accuracy of Post Labeling: Add more rows to the total expected number of postings- 200
3. Balance in Label Representation: Add more rows to the total expected number of postings- 200
4. Consistent Labeling: Create a new criterion that's tracked in the results (ie: F1, precision, recall)
5. Confident Labeling: Create a new criterion that's tracked in the results (ie: F1, precision, recall)


**The gap between what I meant my labels to capture and what the model
learned:**
<!-- Two sentences. Your confusion matrix is the evidence. -->
I meant my labels to capture distinct posts but the model learned there's can be ambiguity in the diverse aposts so improvement to data quantity and labeling can be improved.


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
