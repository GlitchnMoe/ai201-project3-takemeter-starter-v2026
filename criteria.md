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

## 1. Overall Accuracy

The classifier should achieve an overall accuracy of **at least 65% on the held-out test set**.

**Why:** My classifier has three `r/truegaming` labels — `player_experience`, `game_design`, and `gaming_culture` — and some posts can reasonably sit near the boundary between them. I chose 65% because correctly classifying about two out of every three unseen `r/truegaming` posts would be meaningfully better than roughly 33% random guessing while still accounting for the overlap in my taxonomy.

## 2. Per-Label F1

Each of the three labels — `player_experience`, `game_design`, and `gaming_culture` — should achieve an **F1 score of at least 0.55** on the held-out test set.

**Why:** Overall accuracy could hide a label that the model performs poorly on. I chose 0.55 because `player_experience` and `gaming_culture` have a particularly difficult boundary in my taxonomy: posts about player behavior can either focus on an individual's experience or use that behavior to make a broader point about gaming culture.

## 3. Dataset Balance

No single label should make up more than **60% of the examples in `labels.csv`**.

**Why:** From my initial reading of `r/truegaming`, a large number of posts analyze mechanics and design choices, so `game_design` could easily become much larger than the other two labels. I chose a 60% maximum so the model would still see enough `player_experience` and `gaming_culture` examples instead of learning to rely heavily on the most common type of discussion in the subreddit.

## 4. Labeling Consistency

My labels should agree with the comparison or staff labels on **at least 70% of the posts that are labeled by both sides**.

**Why:** `r/truegaming` posts are often long and argumentative, and one post can discuss a player's experience, game mechanics, and broader gaming culture at the same time. I do not expect perfect agreement, but at least 70% agreement would show that my definitions and decision rules are clear enough for another person to apply them similarly.

## 5. High-Confidence Predictions

For predictions where the model reports a confidence of **80% or higher**, at least **80% of those predictions should be correct**.

**Why:** Many `r/truegaming` posts are long and can mix multiple parts of my taxonomy, especially `player_experience` with `gaming_culture`. If the model still assigns at least 80% confidence to one of my three labels despite that ambiguity, I expect that prediction to be correct at least 80% of the time. Otherwise, the model's confidence would not be very useful for distinguishing clear posts from borderline ones.

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
