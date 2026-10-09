# The Ambiguity Canon Is Wrong

*Work in progress. This report documents an ongoing project; findings,
numbers, and conclusions will be revised as labeling continues and new
annotators contribute. Last updated 2026-10-07.*

A report on four rounds of computational experiments, one round of human
labeling, and what the combination reveals about how linguistics and machine
learning handle sentence meaning.

## Summary

A Hopfield-network model of sentence reading was built and tested across four
rounds to ask whether iterating to convergence reveals ambiguity. All four
rounds returned negative results, reported honestly. A subsequent labeling
exercise then showed the deeper problem: 17 of the 19 sentences the field
treats as canonical examples of ambiguity read as clear to an annotator.
The project's ambiguity measurements had been tracking the labeler's
expectations, not reading difficulty. On the annotator's labels, the tested
models agree with the human reading at chance levels, and systematically
prefer word-for-word readings of idioms. The findings suggest the field's
treatment of ambiguity, as a property of sentence form with meaning factored
out, is both empirically unsupported and practically costly.

## 1. The question

A transformer's attention layer can be read as one step of a modern Hopfield
network (Ramsauer et al., 2020): a memory storing patterns, pulling a query
toward the patterns it resembles. A transformer takes one such step per layer
and moves on. This project asked what happens if the network keeps stepping
until the state stops moving. The hypothesis: the number of steps to settle
would carry information a single attention step cannot, with clear sentences
settling fast and ambiguous ones wandering before converging.

## 2. Methodology

**Corpus.** 52 English sentences, each paired with 2 to 4 candidate readings.
The original 18 were drawn from the linguistics literature's standard
ambiguity examples; 34 were added in round 4 (12 high-ambiguity, 10 low,
12 figurative by draft). Every sentence carries an ambiguity label (high,
low, or figurative/open), a dominant reading where one is obvious, and, for
figurative texts, the reading the text carries for the annotator. Labels were
used only for evaluation; nothing was fitted to them. All scoring choices in
rounds 3 and 4 were fixed before results were examined.

**Models.** Texts and readings were encoded with the sentence encoder
all-MiniLM-L6-v2 (bi-encoder channel). A second channel scored
text-reading pairs with an NLI cross-encoder (entailment). Readings were
stored as patterns; the text was the initial state. One update weights each
reading by softmax(beta * similarity to the state) and moves the state to the
weighted mixture. Iteration continued until movement fell below 1e-6. The
sharpness parameter beta was set by a label-free rule (twice the largest
critical beta, computed from the stored readings alone). Two baselines
required no iteration: (A) the margin between the text's similarity to its
two closest readings, and (B) the cosine similarity of those two readings,
which never examines the text.

**Evaluation.** Ambiguity labels were evaluated by AUC: whether a score ranks
high-ambiguity texts above low-ambiguity ones (0.5 is chance, 1.0 is
perfect). Reader agreement was evaluated by whether each model selected the
annotator's dominant reading on the 35 low-ambiguity texts.

**Verification.** The codebase carries 205 automated tests, all passing.
Every reported number was independently rechecked against the results files,
and three corrections were issued during the project and recorded in the
documentation.

## 3. Results: four rounds

**Round 1 (18 texts).** The identity between one Hopfield step and one
attention step verified to 1e-17. Step count separated high from low
ambiguity at AUC 0.75, but baselines A and B both scored 0.76, and the step
count correlated +0.91 with baseline B. Structural cause: after the first
step the state is a mixture of stored readings and the text never re-enters
the computation, so all later steps are functions of the first step's
weights and the readings' mutual similarity.

**Round 2.** A persistent query bias (the query re-voting at every step)
changed zero winners at any strength. Re-voting contributes no new
information.

**Round 3.** Cross-encoder (NLI) scoring raised the step-count AUC to 0.88,
but the NLI margin alone, a single lookup with no iteration, reached 0.98.
The signal resided in the scorer, not the dynamics. Clause-level structure
as additional fixed voters produced a clean negative: zero winner changes at
every strength, with controls confirming the pieces merely re-cast the
text's own vote.

**Round 4.** Neutral clause fragments were made to abstain from voting
(the earlier fragment-driven flips disappeared; the clean negative stood).
The corpus grew to 52 texts, on which the NLI margin weakened from 0.98 to
0.78 and the new high-ambiguity items repeated the earlier paraphrase
confound (the text-blind baseline scored 0.85 on them). Lateral inhibition
between competing readings, with a proven per-text energy bound, produced
zero flips on real text at any strength; the negative came with a structural
explanation, as flips are impossible with two readings and similar readings
occurred only in two-reading texts.

## 4. The labeling and the canon

All labels had been drafted by the builder and none confirmed. An annotator
labeled all 52 texts with no model output shown. Of the 19 sentences drafted
as highly ambiguous, the annotator kept one ("I saw her duck"). Seventeen
were relabeled low ambiguity, each with a clear dominant reading. Final
distribution: 2 high, 35 low, 15 figurative.

These sentences are the field's canonical examples. "Flying planes can be
dangerous" and "Visiting relatives can be boring" are taught as deep-structure
ambiguity (Fromkin and Rodman, 1983). "I saw the man with the telescope,"
"The chicken is ready to eat," and the same pair appear together in standard
structural-ambiguity teaching sets. Stanford's introductory linguistics
materials list "I saw the astronomer with a telescope," "visiting relatives,"
"flying planes," and "I saw her duck" as the exemplary ambiguous sentences
(Stanford Linguistics 1 course slides). With only 2 ambiguous texts in 52,
the project's founding question cannot be tested on this corpus, and the
round 1-4 ambiguity results must be read as measuring agreement with drafted
labels rather than with a reader.

This finding replicates a documented phenomenon rather than announcing a
new one. Readers have long been observed to experience a single reading
where grammatical theory counts dozens: Altmann (1998) notes that "Time
flies like an arrow" admits nearly a hundred permissible readings, none of
which readers notice. Piantadosi, Tily, and Gibson (2012) argue the pattern
is structural to efficient communication itself: ambiguity lets a language
reuse short, easy forms because context does the disambiguating work in
use, which is why sentences examined in isolation look more ambiguous than
they ever are in practice. Wasow similarly observes that sentences taken in
isolation are ambiguous "although hearers have no difficulty in
understanding what meaning was intended," attributing this to speakers
leaving out whatever hearers can infer. The canon's contribution is the
model-side half of the picture: the tested models are torn exactly where
the textbook is torn (Section 5), so embedding-space closeness tracks the
theory's ambiguity, not the reader's. The round 1-4 null results are
therefore better read as honest measurements of the wrong quantity than as
failures to find anything.

## 5. Model-reader agreement

On the 35 low-ambiguity texts with annotator-chosen dominant readings, the
bi-encoder selected the annotator's reading 18 times (51%; chance on
two-reading texts). The NLI cross-encoder selected it 23 times (66%), with
all gains on straightforward word-sense items. Eighteen texts defeated both
models, including the structural classics (telescope, relatives, planes,
leaders): the annotator reads each one way while the models sit near a coin
flip or confidently select the other reading. On idioms, the bi-encoder
selected the word-for-word reading on 11 of 12 texts. Model confidence
barely predicted agreement (AUC 0.59 bi-encoder, 0.66 NLI against chance
0.5).

The mechanism is word overlap, not meaning. "The walls have ears" shares
vocabulary with "the walls of the room have ears growing on them" and shares
nothing with "someone may be secretly listening." Where meaning diverges
from the words, the failure is systematic.

## 6. Implications

The field's standard treatment strips meaning out of the text and calls the
remainder ambiguity: a sentence is ambiguous when its form admits multiple
parses. This move has two costs.

First, it removes the account of why language works. The pleasure and force
of a sentence, the way "still waters run deep" lands whole, is the meaning
arriving in the reader. A theory whose object of study is the meaning-stripped
form cannot explain what makes language effective, because it has defined the
effective part out of scope.

Second, it leaves the theory blind to the contemporary failure mode: fluent
sentences carrying no meaning. Formulaic, performative, and machine-generated
prose can be grammatically well-formed while semantically hollow. A framework
that defines ambiguity as "too many readings" has no entry for "no reading,"
and therefore cannot diagnose language whose problem is emptiness rather
than multiplicity.

The likely downstream effect concerns literacy itself. When curricula and
benchmarks define reading as structural analysis, the meaning-making
capacity, building the scene a sentence describes and tracking what someone
means by it, is neither exercised nor measured, and its decline goes
undetected. Models trained and evaluated on the same terms then reproduce the
husk at scale, and the resulting flood of fluent, empty text further trains
readers on meaninglessness. The theory cannot see the cycle because it
removed the term that would name it.

## 7. Limitations

This work has significant limits, stated plainly. The labels come from a
single annotator; they measure one reader, and inter-annotator agreement has
not been established. With only 2 high-ambiguity texts, the founding question
about ambiguity detection remains untested rather than answered. The corpus is
small (52 texts) and English-only. The cross-encoder weights (approximately
870 MB) sit outside version control, which constrains exact reproducibility.
No claim is made about large language models as readers; only the tested
bi-encoder and cross-encoder were evaluated.

## 8. What needs continuing

- **More annotators.** The same labeling procedure with annotators unfamiliar
  with the project, measuring agreement. This determines whether the canon
  fails to generalize or the single annotator is the outlier.
- **A corpus of genuine ambiguity.** Sentences selected from reader
  uncertainty rather than textbook tradition, which would finally allow the
  founding question to be tested.
- **LLM-as-reader benchmarking.** The 52 texts with annotator readings now
  form a benchmark: prompt a large language model to select the reading for
  each text and compare. This tests whether scale overcomes the failure or
  reproduces it.

## References

- Altmann, G. (1998). Ambiguity in sentence processing. *Trends in Cognitive
  Sciences.*
- Piantadosi, S. T., Tily, H., and Gibson, E. (2012). The communicative
  function of ambiguity in language. *Cognition*, 122, 280-291.
- Wasow, T. (manuscript). Ambiguity. Stanford University.
- Fromkin, V. and Rodman, R. (1983). *An Introduction to Language.* (Cited
  via teaching materials for the deep-structure ambiguity examples.)
- Ramsauer, H. et al. (2020). Hopfield Networks is All You Need.
- Stanford Linguistics 1 course slides: "Some Ambiguities" (I saw the
  astronomer with a telescope; Visiting relatives can be boring; Flying
  planes can be dangerous; I saw her duck).
- Crystal, D. (2008). *A Dictionary of Linguistics and Phonetics* (ambiguity
  as "more than one meaning").
