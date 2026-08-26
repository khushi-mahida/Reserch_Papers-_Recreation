# a survey of ai reliance — paper notes

> personal github notes for remembering what the paper actually says, what the concepts mean, how the framework works, and what i think the authors are trying to prove.

---

# index

1. [paper overview](#1-paper-overview)
2. [the main idea](#2-the-main-idea)
3. [ai reliance vs ai trust](#3-ai-reliance-vs-ai-trust)
4. [appropriate reliance, overreliance and underreliance](#4-appropriate-reliance-overreliance-and-underreliance)
5. [sociotechnical system perspective](#5-sociotechnical-system-perspective)
6. [environment component](#6-environment-component)
7. [social component](#7-social-component)
8. [technical component](#8-technical-component)
9. [mutual interaction](#9-mutual-interaction)
10. [morphological box / categorization framework](#10-morphological-box--categorization-framework)
11. [task](#11-task)
12. [setting](#12-setting)
13. [use cases](#13-use-cases)
14. [decision approach](#14-decision-approach)
15. [reliance measures](#15-reliance-measures)
16. [user training](#16-user-training)
17. [performance feedback](#17-performance-feedback)
18. [implementation](#18-implementation)
19. [transparency and xai](#19-transparency-and-xai)
20. [single-stage vs two-stage experiments](#20-single-stage-vs-two-stage-experiments)
21. [decision outcome matrix](#21-decision-outcome-matrix)
22. [major problems in existing research](#22-major-problems-in-existing-research)
23. [external validity](#23-external-validity)
24. [measurement problems](#24-measurement-problems)
25. [explainability fixation](#25-explainability-fixation)
26. [temporal effects](#26-temporal-effects)
27. [future research agenda](#27-future-research-agenda)
28. [generative ai and agentic ai](#28-generative-ai-and-agentic-ai)
29. [overall paper in simple language](#29-overall-paper-in-simple-language)
30. [important concepts to remember](#30-important-concepts-to-remember)
31. [my interpretation / things to investigate](#31-my-interpretation--things-to-investigate)

---

# 1. paper overview

**paper:** *a survey of ai reliance*

**authors:** Eckhardt et al.

**year:** 2025

## what kind of paper is this?

this is a **survey paper**.

that means the authors are not mainly creating one new ai model and testing it.

instead, they look at a large collection of previous research about how humans use ai recommendations.

their question is basically:

> "when humans work with ai, when do they actually rely on it correctly, when do they rely on it too much, and when do they ignore it?"

and then they ask an even bigger question:

> "are researchers actually measuring ai reliance properly?"

this second question is arguably the more interesting part of the paper.

---

# 2. the main idea

the central argument can be simplified to:

```
humans + ai + task + environment
              |
              v
         final decision
              |
              v
        measure reliance
```

the authors argue that we cannot understand ai reliance simply by looking at:

```
"how accurate is the ai?"
```

or:

```
"does the human trust the ai?"
```

instead, we need to look at the entire system surrounding the human and ai.

for example:

```
same ai
   |
   +------------------+
   |                  |
   v                  v
```

doctor            random user
|                  |
v                  v
medical task      simple quiz
|                  |
v                  v
different reliance behaviour

the ai has not changed.

the **environment, user, task and interaction** have changed.

therefore, reliance can change.

> "apparently humans don't use ai inside a vacuum. shocking."

---

# 3. ai reliance vs ai trust

this is one of the most important distinctions in the paper.

## trust

trust is more of an **attitude or belief**.

a person might say:

> "i trust this ai."

that tells us what they feel or believe.

but it does not necessarily tell us what they actually do.

## reliance

reliance is **observable behaviour**.

for example:

```
ai says: "patient probably has disease x"

human decision:

accepts ai recommendation
        |
        v
   reliance
```

or:

```
ai says: "choose option b"

human chooses option a
        |
        v
   non-reliance
```

so:

```
trust = what i believe about the ai

reliance = what i actually do with the ai's advice
```

this distinction matters because:

```
"i trust the ai"
```

does not necessarily mean:

```
"i will follow the ai."
```

and the reverse can also happen.

a person might not particularly trust an ai but still use its recommendation because it is useful.

> "feelings are nice. behaviour is measurable."

---

# 4. appropriate reliance, overreliance and underreliance

the paper divides reliance into important categories.

## appropriate reliance

the human:

```
accepts correct ai advice
```

or:

```
rejects incorrect ai advice
```

basically:

```
correct advice  -> accept
incorrect advice -> reject
```

this is what we ideally want.

---

## overreliance

overreliance happens when:

```
ai gives incorrect advice
          |
          v
    human accepts it
```

this is also called **misuse**.

example:

```
ai: "patient has disease x"

actual answer: disease y

doctor: "okay, i'll go with x"

result:
wrong decision
```

this is dangerous because the human has allowed the ai to override their own judgment when the ai was wrong.

> "the ai said it confidently, therefore it must be right. famous last words."

---

## underreliance

underreliance is the opposite.

```
ai gives correct advice
          |
          v
    human rejects it
```

this is also called **disuse**.

example:

```
ai: "transaction is fraudulent"

actual answer: fraudulent

human: "nah, i'll ignore it."

result:
correct ai information was wasted.
```

---

# 5. sociotechnical system perspective

this is probably the most important framework in the paper.

the authors use a **sociotechnical system (sts)** perspective.

## what is a sociotechnical system?

"socio" = people and society

"technical" = technology

so a sociotechnical system means:

```
technology
    +
humans
    +
environment
    +
interaction
```

instead of asking:

```
"does the ai make good recommendations?"
```

the paper wants us to ask:

```
"what happens when this particular ai
 interacts with this particular human,
 doing this particular task,
 under this particular environment?"
```

the framework can be represented as:

```
+-------------------------------------------------------------+
|                         environment                          |
|                                                             |
|   task        setting        use case                       |
|     |            |              |                           |
+-----+------------+--------------+---------------------------+
      |
      v
+-------------------------------------------------------------+
|                           social                            |
|                                                             |
|       user training       performance feedback              |
|                                                             |
+-----------------------------+-------------------------------+
                              |
                              v
+-------------------------------------------------------------+
|                     mutual interaction                     |
|                                                             |
|                 decision approach                           |
|                                                             |
+-----------------------------+-------------------------------+
                              |
                              v
+-------------------------------------------------------------+
|                          technical                          |
|                                                             |
|             implementation      transparency                |
|                                                             |
+-------------------------------------------------------------+
```

the important point is that these components interact.

---

# 6. environment component

the environment describes the situation in which the human-ai interaction happens.

the paper identifies things such as:

* task
* setting
* use case

---

# 7. task

a task can be broadly divided into:

## objective task

there is a correct answer or ground truth.

example:

```
"is this transaction fraudulent?"
```

answer:

```
yes / no
```

we can compare the human and ai decisions against the actual answer.

---

## subjective task

there may not be one objectively correct answer.

example:

```
"which product design is more appealing?"
```

different people can legitimately disagree.

this creates a problem for measuring reliance because:

```
ai says A
human says B
```

does that mean the human underrelied?

not necessarily.

the human may simply have a different valid preference.

> "not agreeing with the ai does not automatically mean the human is wrong."

this is an important distinction.

---

# 8. setting

the setting refers to **who is participating and where the experiment happens**.

examples include:

* online crowdworkers
* students
* domain experts
* convenience samples

a common example is using platforms such as:

```
mturk
prolific
```

for experiments.

the problem is that a student or crowdworker answering a simplified experiment is not necessarily equivalent to:

```
doctor making a medical decision
```

or:

```
financial analyst making a high-stakes decision.
```

therefore:

```
laboratory result
       !=
real-world result
```

this is part of the paper's **external validity** concern.

> "if your experiment asks students to classify 50 imaginary cases, congratulations. you have studied students classifying 50 imaginary cases."

---

# 9. use cases

the paper discusses different application domains where ai reliance can be studied.

examples include:

* healthcare
* finance
* business
* recidivism prediction
* housing
* autonomous driving
* classification tasks

the domain matters because the consequences of a wrong decision are different.

for example:

```
wrong movie recommendation
        |
        v
    annoying

wrong medical recommendation
        |
        v
    potentially dangerous
```

therefore, reliance should not always be studied using the same experimental setup.

---

# 10. social component

the social component focuses on factors related to the human side.

two important factors highlighted are:

```
user training
      +
performance feedback
```

these can change how humans interact with ai.

---

# 11. user training

training can vary.

for example:

```
no training

training without ai

training with ai
```

why does this matter?

imagine two users.

user a:

```
never used ai before
```

user b:

```
trained for weeks with the same ai system
```

their behaviour is obviously not guaranteed to be the same.

training can affect:

* knowledge
* confidence
* understanding of the system
* ability to identify ai mistakes

therefore, training becomes part of the reliance equation.

---

# 12. performance feedback

another important factor is whether users receive feedback.

possible conditions:

```
no feedback

partial feedback

full feedback
```

example:

```
user makes decision
       |
       v
receives no information
```

versus:

```
user makes decision
       |
       v
"correct answer was b"
       |
       v
user learns
```

over repeated interactions, feedback could potentially change reliance behaviour.

this connects directly to the paper's argument about **long-term reliance**.

---

# 13. technical component

the technical component focuses on the ai system itself.

two major concepts are:

```
implementation
      +
transparency
```

---

# 14. implementation

implementation refers to how the ai is actually presented or generated during the experiment.

the paper discusses possibilities such as:

* wizard of oz
* static samples
* live ai models

## wizard of oz

this sounds more magical than it is.

a **wizard of oz experiment** means the participant thinks they are interacting with an automated system, but some part of the system is actually being controlled manually behind the scenes.

conceptually:

```
participant
     |
     v
"ai system"
     |
     v
hidden human researcher
     |
     v
generated response
```

the participant does not know the response is being manually produced.

this can be useful for testing systems before the real ai exists.

but it creates an external-validity problem.

---

# 15. transparency and xai

**transparency** concerns how much information the user receives about the ai.

the paper mentions different levels.

## no transparency

```
ai -> prediction
```

nothing else.

---

## performance / uncertainty information

```
ai -> prediction
      +
      confidence / uncertainty
```

example:

```
fraud probability = 92%
```

---

## explanations

the system may explain why it produced the result.

examples include:

* feature-based explanations
* example-based explanations
* counterfactual explanations

---

# 16. xai

**xai = explainable artificial intelligence**

the basic goal is:

```
black-box prediction
       |
       v
   explanation
       |
       v
human understands
possible reasoning
```

example:

```
prediction:
"loan rejected"
```

instead of just saying that, an explanation might say:

```
- high debt-to-income ratio
- low credit history
- insufficient income
```

the paper points out that research has focused heavily on these explainability features.

but the authors argue that explanations are only **one factor**.

human behaviour depends on many other things too.

> "apparently adding an explanation box does not magically solve human-ai interaction."

---

# 17. mutual interaction

this part deals with how the human and ai interact during decision-making.

one major factor is:

```
decision approach
```

the paper distinguishes between:

```
single-stage
```

and:

```
two-stage
```

---

# 18. single-stage vs two-stage experiments

## single-stage

the human sees the ai recommendation before making their decision.

```
+-------------+
|    task     |
+-------------+
       |
       v
+-------------+
|  ai advice  |
+-------------+
       |
       v
+-------------+
| human final |
|  decision   |
+-------------+
```

example:

```
question:
"is this transaction fraudulent?"

ai:
"yes"

human:
"yes"
```

the researcher may conclude:

```
human followed ai
```

but there is a problem.

maybe the human already thought the answer was yes.

therefore:

```
agreement
   !=
reliance
```

this can create **positive measurement error**.

---

# 19. two-stage approach

in a two-stage experiment:

```
task
  |
  v
human makes initial decision
  |
  v
ai recommendation appears
  |
  v
human makes final decision
```

diagram:

```
+-------------+
|    task     |
+-------------+
       |
       v
+------------------+
| initial human    |
| decision         |
+------------------+
       |
       v
+------------------+
| ai recommendation|
+------------------+
       |
       v
+------------------+
| final human      |
| decision         |
+------------------+
```

now researchers can see whether the human changed their mind after seeing the ai.

for example:

```
initial decision = A
ai recommendation = B
final decision = B
```

this provides stronger evidence that the ai influenced the decision.

but there is another problem.

the human may become attached to their first answer.

this can produce **anchoring** or **status quo effects**.

so:

```
single-stage
|
+--> positive measurement error

two-stage
|
+--> possible negative measurement error
```

> "we finally found a situation where both experimental designs have something to complain about."

---

# 20. reliance measures

the paper discusses several ways researchers measure reliance.

important examples include:

## agreement percentage

how often human and ai produce the same answer.

```
agreement =
same human + ai decisions
--------------------------
total decisions
```

but:

```
agreement != guaranteed reliance
```

because the human may independently reach the same answer.

---

## switch percentage

measures how often a human changes their decision after receiving ai advice.

example:

```
before ai = A
ai = B
after ai = B
```

human switched.

this can provide evidence that the ai influenced the person.

---

## weight of advice

**woa = weight of advice**

this measures how strongly the human's final decision moves toward the ai recommendation.

conceptually:

```
initial human decision
        |
        |      ai advice
        |         |
        v         v
A --------------------> B
           |
           v
    final decision
```

if the final answer moves significantly toward the ai's answer, the human gave more weight to the ai.

---

## delegation

another possibility is whether the human simply delegates the task to the ai.

example:

```
human:
"ai, you decide."
```

this is a different type of reliance from:

```
human:
"i'll make the decision,
 but i'll consider the ai recommendation."
```

---

# 21. decision outcome matrix

this is one of the easiest diagrams to remember.

```
+----------------------+----------------------+
|                      | ai correct           | ai incorrect         |
+----------------------+----------------------+----------------------+
| human accepts ai     | appropriate reliance | overreliance         |
+----------------------+----------------------+----------------------+
| human rejects ai     | underreliance        | appropriate rejection|
+----------------------+----------------------+----------------------+
```

## example 1

```
ai = correct
human = accepts

result:
appropriate reliance
```

---

## example 2

```
ai = wrong
human = accepts

result:
overreliance
```

---

## example 3

```
ai = correct
human = rejects

result:
underreliance
```

---

## example 4

```
ai = wrong
human = rejects

result:
appropriate rejection
```

this gives us an important insight:

**we cannot determine whether reliance was good simply by knowing whether the human followed the ai.**

we also need to know:

```
was the ai actually correct?
```

---

# 22. morphological box / categorization framework

the paper organizes previous ai reliance research using multiple dimensions.

the overall idea is:

```
+-------------------------------------------------------+
|                    ai reliance study                  |
+-------------------------------------------------------+
   |          |          |          |
   v          v          v          v
environment social   technical   interaction
   |          |          |          |
   v          v          v          v
  task      training implementation decision
  setting   feedback   transparency  approach
  use case                         measures
```

this is useful because it lets researchers compare studies systematically.

instead of saying:

```
"paper x studied ai reliance"
```

we can ask:

```
what task?
who were the users?
what ai?
what feedback?
what explanations?
what interaction design?
what measurement?
what environment?
```

---

# 23. the nine major subconcepts

the framework can be remembered as:

```
environment
   |
   +-- task
   +-- setting
   +-- use case

social
   |
   +-- user training
   +-- performance feedback

technical
   |
   +-- implementation
   +-- transparency

mutual interaction
   |
   +-- decision approach
   +-- reliance measures
```

this is essentially the paper's way of saying:

> "stop studying one variable and pretending it explains the entire human-ai relationship."

---

# 24. major problem 1 — external validity

this is one of the biggest criticisms.

many existing studies use:

```
online crowdworkers
       +
simplified tasks
       +
artificial environments
       +
static ai responses
```

instead of:

```
domain experts
       +
real tasks
       +
live ai
       +
realistic environments
```

the problem:

```
laboratory experiment
      |
      v
interesting result
      |
      ?
      |
      v
does this actually happen
in the real world?
```

that question is **external validity**.

---

# 25. external validity

## definition

external validity means:

> how well do the findings from a study apply outside the experiment?

example:

```
experiment:
500 students classify images

conclusion:
"humans rely on ai in image classification."
```

but maybe:

```
doctors
engineers
financial analysts
cybersecurity experts
```

behave completely differently.

therefore:

```
experimental result
        !=
universal human behaviour
```

unless the experimental setting actually represents the real-world situation.

---

# 26. major problem 2 — measurement problems

another problem is that researchers do not always measure reliance consistently.

different studies may use:

```
agreement %

switch %

weight of advice

delegation

accuracy

self-report
```

this makes comparisons difficult.

for example:

```
paper a:
reliance = 80%

paper b:
reliance = 65%
```

but what exactly does "reliance" mean in each study?

if they measured different things:

```
80% != 65%
```

cannot automatically be compared.

> "two papers using the word 'reliance' does not mean they are measuring the same thing."

---

# 27. positive measurement error

in a single-stage experiment:

```
ai answer = A
human answer = A
```

researcher:

```
"the human relied on ai."
```

but maybe:

```
human would have chosen A anyway.
```

therefore:

```
observed agreement
      |
      +--> actual reliance
      |
      +--> coincidence / independent agreement
```

this can make reliance look higher than it actually is.

---

# 28. negative measurement error

two-stage experiments solve one problem but may create another.

suppose:

```
human initially chooses A
```

then:

```
ai recommends B
```

the human sees the recommendation but sticks with A.

does that mean:

```
"human ignored ai"?
```

maybe.

but maybe the human simply became anchored to their original answer.

therefore:

```
observed non-switch
      |
      +--> genuine rejection of ai
      |
      +--> anchoring / status quo effect
```

this can make reliance look lower than it actually is.

---

# 29. major problem 3 — explainability fixation

the paper argues that researchers have placed a lot of attention on:

```
"does explaining the ai
 make humans trust it more?"
```

this is useful, but incomplete.

because human-ai interaction also depends on:

```
user expertise
confidence
task difficulty
time pressure
environment
feedback
training
ai accuracy
interaction design
```

so:

```
reliance
   |
   +-- ai explanation
   +-- user characteristics
   +-- task
   +-- environment
   +-- interaction
   +-- experience
   +-- feedback
```

the authors therefore argue for a more **multi-factorial** approach.

---

# 30. major problem 4 — temporal effects

another important criticism is that many experiments happen only once.

something like:

```
day 1
   |
   v
experiment
   |
   v
measure reliance
   |
   v
done
```

but real human-ai interaction may look like:

```
day 1 -> day 10 -> day 30 -> day 100
   |       |        |        |
   v       v        v        v
 reliance changes over time
```

humans may:

* learn the system
* become more confident
* become more skeptical
* become dependent
* notice recurring mistakes
* adapt their decision strategy

therefore:

```
reliance(t)
```

may be more meaningful than:

```
one average reliance score
```

---

# 31. longitudinal research

**longitudinal** means studying behaviour across time.

example:

```
week 1
|
v
human + ai
|
v
measure reliance

week 4
|
v
human + ai
|
v
measure reliance

week 12
|
v
human + ai
|
v
measure reliance
```

then we can ask:

```
does reliance increase?
decrease?
stabilize?
fluctuate?
```

this is much closer to real-world ai usage.

---

# 32. future research agenda

the paper proposes several directions.

## 1. improve external validity

move toward:

```
live ai systems
+
domain experts
+
real-world tasks
+
realistic environments
```

instead of relying mainly on:

```
crowdworkers
+
artificial experiments
+
static ai outputs
```

---

## 2. standardize measurements

researchers need clearer and more consistent ways to measure reliance.

possible measures include:

```
agreement
switching
weight of advice
delegation
accuracy
```

but researchers need to understand exactly what each metric measures.

---

## 3. study multiple factors together

instead of:

```
"does explanation affect reliance?"
```

study:

```
user expertise
      +
confidence
      +
task difficulty
      +
time pressure
      +
ai accuracy
      +
explanation
      |
      v
   reliance
```

this is a much more realistic model.

---

# 33. multi-user environments

the paper also argues that research should move beyond:

```
one human
    +
one ai
```

toward:

```
human 1
   |
   +------+
          |
          v
         ai
          |
   +------+
   |
human 2
```

or even:

```
doctor
   |
patient
   |
  ai
   |
hospital
   |
administrator
```

real systems often involve multiple stakeholders.

so studying only:

```
human <-> ai
```

may be too simplistic.

---

# 34. generative ai and agentic ai

this is especially important if you want to connect this paper to your agentic ai research.

traditional reliance experiments often look like:

```
task
  |
  v
ai prediction
  |
  v
human decision
```

but generative ai changes the interaction.

now it can be:

```
human
  |
  v
generative ai
  |
  v
generated content
  |
  v
human edits
  |
  v
final content
```

so instead of asking only:

```
"did the human accept the ai recommendation?"
```

we might measure:

```
how much did the human edit?

how much content was accepted?

how long did the human spend checking it?

how frequently did they override it?

did they delegate the task?
```

---

# 35. agentic ai makes this even more complicated

an agentic system may not simply recommend something.

it may:

```
receive goal
    |
    v
  plan
    |
    v
  use tools
    |
    v
execute actions
    |
    v
 observe result
    |
    v
  re-plan
    |
    +-------> repeat
```

so reliance becomes:

```
human
  |
  v
agent
  |
  +--> reasoning
  |
  +--> planning
  |
  +--> tool use
  |
  +--> execution
  |
  +--> feedback
  |
  v
final outcome
```

this raises new questions.

for example:

```
how much autonomy should humans give the agent?

when should the human intervene?

how do we measure overreliance when
the ai is performing multiple actions?

what happens when the agent makes
one correct decision followed by one
incorrect decision?
```

the paper's framework provides a useful starting point for these questions, but the pasted material does not provide a complete agentic-ai reliance metric.

---

# 36. important distinction: reliance is not the same as accuracy

this is VERY important.

suppose:

```
ai accuracy = 95%
```

human follows ai = 90%

you cannot simply say:

```
"great, reliance is 90%."
```

because reliance depends on the relationship between:

```
ai recommendation
human decision
actual ground truth
```

for example:

```
ai correct + human accepts
        =
appropriate reliance
```

but:

```
ai wrong + human accepts
        =
overreliance
```

therefore:

```
reliance quality
    depends on
ai correctness + human behaviour
```

---

# 37. important distinction: following ai is not automatically good

consider:

```
ai recommendation = wrong
human follows ai
```

this means:

```
high reliance
```

but:

```
poor reliance quality
```

now:

```
ai recommendation = correct
human rejects ai
```

this means:

```
low reliance
```

but:

```
also poor reliance quality
```

therefore the goal is not:

```
"maximize reliance"
```

the goal is:

```
"maximize appropriate reliance."
```

this is one of the most important concepts to remember.

---

# 38. the entire paper in one diagram

```
+----------------------------------------------------------+
|                     AI RELIANCE                          |
+----------------------------------------------------------+
                          |
          +---------------+---------------+
          |               |               |
          v               v               v
    ENVIRONMENT         SOCIAL        TECHNICAL
          |               |               |
      +---+---+       +---+---+       +---+---+
      |   |   |       |       |       |       |
    task setting use training feedback impl. transparency
    case
          \               |               /
           \              |              /
            +-------------+-------------+
                          |
                          v
                MUTUAL INTERACTION
                          |
                          v
                 decision approach
                          |
                          v
                  human + ai decision
                          |
                          v
             +------------+------------+
             |            |            |
             v            v            v
        appropriate   overreliance  underreliance
          reliance      misuse        disuse
```

---

# 39. what the authors are basically arguing

the paper can be reduced to this argument:

```
old approach:

"how much do humans trust the ai?"

                |
                v

better approach:

"how do humans actually behave
 when interacting with ai?"

                |
                v

even better:

"how does that behaviour change
 depending on the task, user,
 technology, interaction and
 environment?"

                |
                v

future:

"how does that behaviour change
 over time and in real-world
 multi-user environments?"
```

that is essentially the progression of the paper.

---

# 40. what you should remember for research

if you ever want to recreate or extend this paper experimentally, remember these variables.

## independent variables

things you can manipulate:

```
ai accuracy
explanation vs no explanation
user training
performance feedback
task difficulty
time pressure
decision approach
ai confidence information
```

## user variables

things about the human:

```
expertise
confidence
previous experience
familiarity with ai
```

## dependent variables

things you can measure:

```
agreement %
switch %
weight of advice
delegation
final accuracy
reliance
overreliance
underreliance
```

## environmental variables

```
task type
domain
stakes
user population
real-world vs laboratory environment
```

---

# 41. possible experimental setup

if i wanted to turn the ideas from this paper into a data analytics project, one possible structure would be:

```
+----------------------+
| participant          |
+----------+-----------+
           |
           v
+----------------------+
| task                 |
+----------+-----------+
           |
           v
+----------------------+
| initial decision     |
+----------+-----------+
           |
           v
+----------------------+
| ai recommendation    |
+----------+-----------+
           |
           v
+----------------------+
| final decision       |
+----------+-----------+
           |
           v
+----------------------+
| ground truth         |
+----------+-----------+
           |
           v
+----------------------+
| calculate reliance   |
+----------+-----------+
           |
   +-------+-------+
   |       |       |
   v       v       v
correct  over    under
reliance reliance reliance
```

then the resulting dataset could contain something like:

```
participant_id
expertise
task_difficulty
ai_accuracy
ai_confidence
explanation
initial_decision
ai_decision
final_decision
ground_truth
switched
decision_time
reliance_type
```

then you could analyze:

```
expertise vs overreliance

ai confidence vs switching

explanation vs reliance

task difficulty vs underreliance

experience vs appropriate reliance

time pressure vs decision quality
```

---

# 42. possible data analytics

the paper itself is a survey, so if recreating its ideas as a data project, you could potentially use:

```
descriptive statistics
        |
        v
correlation analysis
        |
        v
hypothesis testing
        |
        v
regression
        |
        v
classification
        |
        v
longitudinal analysis
```

for example:

```
target variable:

reliance_type

values:

appropriate
overreliance
underreliance
```

then potentially build a classification model:

```
expertise
ai_accuracy
explanation
task_difficulty
confidence
time_pressure
      |
      v
machine learning model
      |
      v
predicted reliance type
```

important:

> this is a possible research implementation derived from the paper's framework, not a method explicitly reported as being used by the authors in the supplied material.

---

# 43. the biggest takeaway

the paper is NOT simply saying:

```
"humans trust ai."
```

it is saying something much more complicated:

```
AI reliance is a behavioural phenomenon
that emerges from interactions between
humans, technology, tasks, environments
and decision processes.
```

and therefore:

```
+----------------+
|     HUMAN      |
+-------+--------+
        |
        |
+-------v--------+
|       AI       |
+-------+--------+
        |
        |
+-------v--------+
|      TASK      |
+-------+--------+
        |
        |
+-------v--------+
|  ENVIRONMENT   |
+-------+--------+
        |
        v
    DECISION
        |
        v
   RELIANCE TYPE
```

---

# 44. important concepts — quick revision

| concept               | simple meaning                                                  |
| --------------------- | --------------------------------------------------------------- |
| ai reliance           | what humans actually do with ai advice                          |
| ai trust              | what humans believe or feel about ai                            |
| appropriate reliance  | accept correct advice / reject incorrect advice                 |
| overreliance          | accept incorrect ai advice                                      |
| underreliance         | reject correct ai advice                                        |
| sociotechnical system | human + technology + environment + interaction                  |
| external validity     | whether findings apply to the real world                        |
| xai                   | explainable ai                                                  |
| wizard of oz          | system appears automated but part is manually controlled        |
| agreement             | human and ai give the same answer                               |
| switch                | human changes decision after seeing ai                          |
| weight of advice      | how strongly the final decision moves toward ai advice          |
| delegation            | human gives decision responsibility to ai                       |
| longitudinal study    | studying behaviour over time                                    |
| objective task        | task with a known correct answer                                |
| subjective task       | task without one objectively correct answer                     |
| anchoring             | relying heavily on an initial decision                          |
| measurement error     | measured behaviour does not perfectly represent actual reliance |

---

# 45. things i would investigate further

these are not claims from the paper; these are questions that naturally come out of reading it.

> "okay, but how do we actually quantify autonomy and reliance when the ai is an agent rather than a recommendation system?"

possible direction:

```
traditional ai

human ---> ai recommendation ---> human decision
```

versus:

```
agentic ai

human ---> agent ---> plan ---> tools ---> actions
                   ^                    |
                   |                    |
                   +---- feedback <-----+
```

then reliance could potentially involve more than just:

```
accept / reject
```

it might involve:

```
intervention frequency
override rate
delegation rate
action approval rate
correction rate
human verification time
agent task completion
agent error recovery
human intervention timing
```

this would be an interesting extension of the paper's framework.

> "the moment the ai starts doing things instead of merely recommending things, the definition of 'reliance' starts getting considerably more annoying."

---

# 46. final one-minute revision

if you have to explain this paper to someone quickly:

> *a survey of ai reliance* studies how humans actually behave when working with ai systems. the authors distinguish reliance from trust because trust is a belief while reliance is observable behaviour. they classify reliance into appropriate reliance, overreliance and underreliance depending on whether the ai was correct and whether the human accepted or rejected its advice. the paper uses a sociotechnical perspective, arguing that reliance depends not only on the ai but also on the task, user, environment, training, feedback and human-ai interaction. the authors identify problems in existing research, particularly excessive use of crowdworkers and artificial experiments, inconsistent reliance measurements, over-focus on explainability, and lack of long-term studies. they propose future research involving real-world ai systems, domain experts, standardized measurements, multi-factor analysis, longitudinal studies, multi-user environments, and eventually generative and agentic ai systems.*

---

# 47. the sentence to remember

> **the goal is not to make humans rely on ai more. the goal is to make humans rely on ai appropriately.**

that is probably the single most important idea to carry away from this paper.

