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
**Definition:** Asking for advice to change a cat's behavior towards a certain goal. This may involve repeated training and posts usually have the word "train/ training" in them. 

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
**Definition:**  Focus on owners introducing new cats to home, getting used to resident cats, or a new living location.


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
     - Public Reddit Community: r/CatAdvice  [https://www.reddit.com/r/CatAdvice/]

**Where the posts came from:**
- Reddit Users part of the r/CatAdvice community

**How I labelled them:** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->

- Manually labeled them based on my label rules.

**Counts per label:**

| Label | Count | Share |
|---|---|---|
| behavior | 30 |24%  |
| training  | 30  | 24% |
| health | 25 | 20%  |
| accommodation | 31 |  24% | 
|other | 11 | 9% | 
| **Total** | 127 | 100% |

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
> *Could have been:* `accommodation` 
>
> *I chose `training` because:* the cat owner is focused on changing their cat's behavior. Despite the trigger being an external factor (the neighbor), the part where the cats have to reassociate a different sound to their "bedtime snacks" would be considered training. 

**2.**
> *The post:* My soul cat has heart failure and I feel nothing. Exactly as title says, we noticed her breathing was off and that she had been eating less in June- took her in and her blood tests were all normal so everything seemed fine, chalked it up to old cat things and possibly arthritis. After lots of back and fourthing (over 3 months) to the vet and knowing something was off when her breathing became so much worse, they told us we could either take her to the ER or wait another day to clear her lungs. She went from “slightly worried about her health” to “she’s most likely going to die in 5 months” over the span of 3 days.
She is my childhood cat, I picked her out at 7 years old and named her. She saved me so many times when my mental and physical health was in the shitter. It’s killing me to force meds down her throat and watch her deteriorate but ultimately we’re just doing at home ‘hospice’ care if you can call it that. We just lost our other cat last year to end stage cancer at a similar time and I wasn’t even able to say goodbye to her (college).
Maybe it’s the meds I’m on, the fact that I’m going into veterinary medicine, or maybe it’s because I heard the possibility of heart failure and I’ve been pre-mourning her and expecting bad news. But it hasn’t hit me yet she might not even make it till Christmas.
I’ve been trying to spend every day with her but I just had hip surgery and the place she goes to (my room) is upstairs. I’m so sad but at the same time I’m not. Does it get any better?
>
> *Could have been:* `health`
>
> *I chose, `other` because:* there's no seeking for advice to aid the cat's health. The cat's health is talked about but it's more of the owner explaining their situation and seeking emotional support. 

**3.**
> *The post:* How do I stop my cat from parkouring off my face at 4am? Clarice is turning 1 next week, so I think that means she's still in the "teen" stage. She is pure chaos. She chews on the plants (sprayed with Bitter Apple, so she stopped chewing the leaves and started pulling bits of mulch out of the pots), throws litter everywhere, chases her sister, climbs on top of the cabinets and the wash tower, scales the window screens, and screams just to hear the sound of her own voice. She makes silly little gremlin noises as she bounces around - the best is when I hear a huge crash as she careens into something, followed by an uncertain little "brrrr?" noise after the dust settles. I love her.
She has a new unpleasant habit of wanting to involve me in her zoomies, especially at night. It's like she gets so excited by running around top speed and decides she wants to share her excitement with Mom. Which means targeting the part of me she can see - my vulnerable, unsuspecting head and shoulders poking out of the blankets.
It's a spacious studio apartment with one little storage room, so I can't really close her out of my "bedroom." I do throw her in there after this happens to get some peace, but there's no litter box in there and it wouldn't be cool to cram her in there all night. Last night she scratched my face and I'm at my wits' end. Any ideas how I can stop this behavior or should I just start wearing a motorcycle helmet to bed?
>
> *Could have been:* behavior
>
> *I chose, training because:* the cat owner already understand about behavior and is more intent on looking for tips to train or correct their cat's behavior. Behavior is reserved when the owner is asking for the community support in suggesting the root cause of a strange behavior. 

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

| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy | 0.500 | 0.300 | -0.200 |
| Macro F1 | 0.389 | 0.210 | -0.179 |
| F1 — `accomodation` | 0.526 | 0.333 | -0.193 |
| F1 — `behavior` | 0.000 | 0.353 | +0.353 |
| F1 — `health` | 0.667 | 0.000 | -0.667 |
| F1 — `other` | 0.000 | 0.000 | +0.000 |
| F1 — `training` | 0.750 | 0.364 | -0.386 |

**What I predicted before I looked:**
<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->
     I think my trained model will not beat it because there’s too many categories and the size of the data is only 127 rows (still a little far from the 200 expected labels)


**What the gap actually means:**
<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->
The trained model seem to perform worse than the baseline for all labels except behavior (excluding `other` label because was 0 for both.)


---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Measure | Seed 42 | Seed 7 | Seed 2024 | Spread |
|---|---|---|---|---|
| Overall accuracy | 0.300 | 0.200 | 0.250 | 0.100 |
| Macro F1 | 0.210 | 0.117 | 0.080 | 0.130 |
| F1 — `behavior` | 0.353 | 0.300 | 0.000 | 0.353 |
| F1 — `health` | 0.000 | 0.000 | 0.000 | 0.000 |
| F1 — `accomodation` | 0.333 | 0.286 | 0.400 | 0.114 |
| F1 — `training` | 0.364 | 0.000 | 0.000 | 0.364 |
| F1 — `other` | 0.000 | 0.000 | 0.000 | 0.000 |


| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1. Overall Accuracy of Post Labeling | .6 | .3 |.2  | .25 | NOT MET
| 2. `other` label performance may be less than rest of the other labels  | -/+ 30% max | -36% max | -33% max | -40% max | MET
| 3. Balance in Label Representation  | 20-30% Rep for each label | ~ | ~ | ~ | NOT MET (may need to revise)
| 4. Consistent Labeling | .7 | .3 | .2 | .25 | NOT MET 
| 5.  Confident Labeling  | AUC Score >= .7 | ~ | ~ | ~  | NOT MET (may need to revise)

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

 true \ predicted | behavior | health | accomodation | training | other |
|---|---|---|---|---|---|
| **behavior** | 3 | 0 | 0 | 2 | 0 |
| **health** | 3 | 0 | 0 | 1 | 0 |
| **accomodation** | 3 | 0 | 1 | 1 | 0 |
| **training** | 2 | 0 | 0 | 2 | 0 |
| **other** | 1 | 0 | 0 | 1 | 0 |

**My biggest off-diagonal number, and what it means:**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->
     3 real `health` posts called `behavior` but 0 `behavior` posts called `health`


---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 | Overall Accuracy of Post Labeling | .6 | NOT MET | Based it off the accuracy from the Run Log |
| 2 | `other` label performance may be less than rest of the other labels | -/+ 30% max | MET | Based from Run Log |
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
3. Balance in Label Representation: Critierion couldn't be measured based from run log and results
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

**What I changed:** Relabeled posts focusing on having more accurate `behavioral` label

**Which diagnosis pointed at it:** " Biggest confusion: 3 real `health` posts called `behavior`.
The other direction: 0 real `behavior` posts called `health`. That's lopsided — the model leans toward `behavior` on this pair.A direction like that usually points at your labelling rather than the
model. "

### Run Log — After

| Measure | Seed 42 | Seed 7 | Seed 2024 | Spread |
|---|---|---|---|---|
| Overall accuracy | 0.300 | 0.200 | 0.250 | 0.100 |
| Macro F1 | 0.210 | 0.117 | 0.080 | 0.130 |
| F1 — `behavior` | 0.353 | 0.300 | 0.000 | 0.353 |
| F1 — `health` | 0.000 | 0.000 | 0.000 | 0.000 |
| F1 — `accomodation` | 0.333 | 0.286 | 0.400 | 0.114 |
| F1 — `training` | 0.364 | 0.000 | 0.000 | 0.364 |
| F1 — `other` | 0.000 | 0.000 | 0.000 | 0.000 |

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1. Overall Accuracy of Post Labeling | .6 | .3 |.2  | .25 | NOT MET
| 2. `other` label performance may be less than rest of the other labels  | -/+ 30% max | -36% max | -33% max | -40% max | MET
| 3. Balance in Label Representation  | 20-30% Rep for each label | ~ | ~ | ~ | NOT MET (may need to revise)
| 4. Consistent Labeling | .7 | .3 | .2 | .25 | NOT MET 
| 5.  Confident Labeling  | AUC Score >= .7 | ~ | ~ | ~  | NOT MET (may need to revise)

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->
Relabelling didn't help since the results in the 2nd run has no difference than the first run. It may not have helped since the only about 7 rows out of 127 were relabeled so perhaps the change was too small to make a signficant change. 


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
