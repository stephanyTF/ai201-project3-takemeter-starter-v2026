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

**Definition:** Asking for help when it comes to understanding or finding the reason for a cat's behavior like why a cat is more active during certain times or suddenly acting in a different way. Most post usually have the word 'behavior' in them. 

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



### `other`
**Definition:** Any other posts that doesn't fit the other labels

**Example 1:**
>#### do basic research before asking reddit for advice
>     most of you are grown adults. yet a lot of the times, i notice two things:
>     basic, extremely google-able questions.
>     people improvising key aspects of cat care, especially with socialization & first-time cat owner things, then asking redditors for
>     tips on fixing their mistakes when they could've... googled it first and gotten their answers much more quickly and potentially not
>             make the mistake in the 1st place.
>     
>     doesn't necessarily make someone a bad person, but maybe a more helpless one... and potentially chronically irresponsible by consequence  because of a lack of basic research skills and lack of proactivity.
>     
>     please. for the sake of yourself and your pet, google things first to see if you can get your answer in seconds. you could get your
>     answer a lot faster, and even if you still ask clarifying questions on reddit, you'll have enough context to know when someone's saying
>     something absolutely batsh*t. 🫶🏻

**Example 2:**
>#### does my cat know im drunk
>     very important right now i think




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
train 23  ·  val 5  ·  test 6 (Note due to running out of time, data pool was very sall (only 127))



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
