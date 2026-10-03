# Acceptance criteria — TakeMeter

Five criteria that say what "working" means for this classifier, written in
unit 5 **before** anything was trained.

**All five are yours this time.** None are given. You've had two projects of
practice.

An acceptance criterion names a number. *"The model is accurate"* is an
opinion. *"Every label has an F1 of at least 0.60 on the held-out set"* is a
criterion.

Under each, write a sentence or two on **why that number**. A reason that says
something about your data or your taxonomy earns credit — *"I picked 0.60 F1
for `reaction` because it's my smallest label and I only have about 50
examples of it"*. A reason that could be attached to any project does not.

> Missing your own targets next unit costs you nothing. Setting a target so
> easy you can't miss it does.

---

## Pick numbers you can defend

Not numbers that sound impressive. Three labels means a coin-flip guesser gets
about 33%, so a target of 0.40 is barely a target. Your number should sit
somewhere you'd honestly call useful.

**Cover at least three of these five areas.** They're here as prompts, not as a
form to fill in — a criterion that fits none of them is fine if it names a
number.

| Area | A question it could answer |
|---|---|
| Overall accuracy | How often does it need to be right to be worth using? |
| Per-label performance | Is one label allowed to be much worse than the others? |
| Balance | How lopsided can your label counts get before it's a problem? |
| Consistency | If someone else labelled the same posts, how often should you agree? |
| Confidence | Should a confident prediction be right more often than an unsure one? |

Two things worth knowing before you pick numbers, because both will affect
whether you hit them:

- **Your smallest label will have the jumpiest score.** If a label has 50
  examples, about 8 land in the test split. An F1 computed on 8 examples moves
  a lot between seeds. A target for that label should be looser than one for
  your biggest label, and saying so is a good reason.
- **Unit 6 tests across three seeds, and the target has to hold across all
  three.** A target of 0.65 against results of 0.71, 0.62, 0.68 is a **miss**.
  Pick with that in mind — it is stricter than it first sounds.

---

## 1. Overall Accuracy of Post Labeling 

<!-- Your criterion. It must name a number. -->

    Every label has an F1 of at least 0.60 on the held-out set


**Why this target:**
    The F1 score measures the harmonic mean of precision and recall which helps reflect the overall accuracy.


---

## 2. Sharing News label performance may be less than hot-takes label

<!-- Your criterion. -->
    The accuracy of sharing news label may be max 30% less accurate than other labels


**Why this target:**
  There's not a lot of non-partial posts on the reddit. Since it's a community there tends to be more opinionated posts that wants to spark discussion.


---

## 3. Balance in Label Representation

<!-- Your criterion. -->
Out of the 3 labels, there should be about 20-30% representation of each in the posts data


**Why this target:**
Ensures there's a fair representation for each label so the model is not biased toward a specific label.


---

## 4. Consistent Labeling

<!-- Your criterion. -->
  If someone else labeled the same 20 held-out posts, they should agree with my original label at least 80% of the time.


**Why this target:**
My labels (hot-takes, sharing news, open-discussion) rely on some judgment calls. For instance, a slightly charged discussion can read like a hot take when it actually opens up for mixed discussion. 80% raw agreement should allow for that ambiguity. 



---

## 5. Confident Labeling

<!-- Your criterion. -->
The model should be able to have at least a moderate accuracy in distinguishing between classes by having an AUC score of at least .7



**Why this target:**
AUC between .7 and .9 are considered to rank a model as good with moderate to strong predictive power.


---

<!-- ─────────────────────────────────────────────────────────────────────────
     UNIT 6 — read this before you change anything above.

     If a criterion turns out to be BROKEN rather than merely unmet, you can
     revise it, and that earns credit. But never delete or edit the original
     line. Add the revision underneath, like this:

         ## 2. Every label performs acceptably

         The model performs well on all labels.

         **Why this target:** ...

         > **Revised in unit 6:** Every label has an F1 of at least 0.60 on
         > the held-out set.
         >
         > **Why revised:** "performs well" gave me nothing to check. I
         > couldn't produce a verdict from it at all.

     That's a revision because the criterion couldn't be MEASURED.

     Lowering a target because you missed it is not a revision, and it costs
     you the point:

         ✗ "Overall accuracy of at least 0.65" → "at least 0.55", because
            0.65 turned out to be optimistic for 200 examples.

     A number you missed stays where it is, gets diagnosed, and gets a fix
     attempted. That's where the points are.
     ───────────────────────────────────────────────────────────────────────── -->
