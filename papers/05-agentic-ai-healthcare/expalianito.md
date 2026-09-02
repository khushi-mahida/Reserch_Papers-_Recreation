
# Agentic AI in Healthcare

### My Understanding, Notes & Slightly Sarcastic Breakdown of a Research Paper

> **Paper:** *Agentic AI in Healthcare: Opportunities, Challenges, and Future Directions*
> **Authors:** Mourad Gridach, Jay Nanavati, Khaldoun Zine El Abidine, Calum Yacoubian
> **Published in:** ACM Computing Surveys, 2026
> **DOI:** 10.1145/3809164

---

# 1. Why I Read This Paper

I wanted to understand what **Agentic AI actually means in a real-world domain**, instead of just seeing the phrase "AI agent" thrown around everywhere.

Healthcare seemed like a good example because it makes the advantages AND problems of Agentic AI painfully obvious.

Because giving an AI the ability to:

> "Think, plan, use tools and make decisions"

sounds amazing...

until the AI is dealing with an actual patient.

Then suddenly everyone remembers:

> **"Wait... maybe we should add some safety checks."**

And that is basically the central idea of this paper.

The paper reviews how Agentic AI can be used in healthcare, what architectures are being used, what medical agents already exist, how these systems should be evaluated, and what prevents them from being safely deployed in real clinical environments.

---

# 2. The Main Idea in One Sentence

If I had to explain the entire paper in one sentence:

> **Agentic AI tries to move healthcare AI from simply answering questions to actually planning, reasoning, using tools, collaborating with other agents and taking actions — but the more autonomous the system becomes, the more important safety, privacy, explainability, human oversight and regulation become.**

That's the paper.

Everything else is basically the authors explaining:

> **"Okay, but how do we make this not terrifying?"**

---

# 3. Traditional AI vs Agentic AI

This was probably the first thing that clicked for me.

## Traditional AI

The system is usually given a task and produces an output.

.........
INPUT
  |
  v
AI MODEL
  |
  v
OUTPUT
```

Example:

> Give the AI an X-ray.

AI:

> "There may be pneumonia."

Done.

---

# Agentic AI

Now we give the system a goal.

> "Analyze this patient's case and help determine the next step."

Instead of simply answering, the agent can potentially:

.........
              GOAL
                |
                v
           PERCEPTION
                |
                v
            REASONING
                |
                v
             PLANNING
                |
                v
           TOOL CALLING
                |
                v
             ACTION
                |
                v
          CHECK RESULT
                |
                v
        NEXT DECISION
```

So the important difference is:

> **A model produces an answer. An agent can perform a workflow.**

---

# 4. What Exactly Is an AI Agent?

The paper describes an AI agent as an autonomous intelligent entity that can take appropriate actions based on information received from its environment.

In simpler words:

> An agent doesn't just know things. It can decide what it needs to do next.

For example:

### Normal LLM

Me:

> "What does this blood test mean?"

LLM:

> "Here's an explanation."

### Agent

Me:

> "Analyze this patient's abnormal blood test."

Agent:

.........
Read patient history
       ↓
Check previous results
       ↓
Analyze current result
       ↓
Search medical knowledge
       ↓
Compare findings
       ↓
Generate possible explanations
       ↓
Check confidence
       ↓
Generate recommendation
```

So the AI has moved from:

**Question → Answer**

to:

**Goal → Plan → Actions → Result**

---

# 5. The Four Core Steps

One of the easiest ways I remember Agentic AI is:

# P → R → A → L

### 1. Perception

The agent collects information.

Healthcare examples:

* symptoms
* EHR
* blood tests
* X-rays
* doctor notes
* medical history

### 2. Reasoning

The agent tries to understand what the information means.

### 3. Action

The agent does something.

For example:

* call an API
* search a database
* retrieve medical literature
* generate a report
* ask another agent

### 4. Learning

The system can use feedback or previous interactions to improve its future behavior.

So:

.........
PERCEIVE
   ↓
REASON
   ↓
ACT
   ↓
LEARN
   ↺
```

The paper discusses these capabilities as part of the evolution toward agentic systems.

---

# 6. Agentic AI Did NOT Start With ChatGPT

This was another interesting part.

It is tempting to think:

> ChatGPT appeared → AI agents appeared.

Nope.

The idea of intelligent agents in healthcare goes back much further.

The paper discusses earlier medical expert systems such as:

* MYCIN
* INTERNIST-I
* CADUCEUS

These systems relied heavily on:

* rules
* symbolic reasoning
* inference engines

rather than today's large language models.

So the evolution can roughly be understood as:

.........
RULE-BASED EXPERT SYSTEMS
          ↓
TRADITIONAL AI AGENTS
          ↓
MACHINE LEARNING
          ↓
LARGE LANGUAGE MODELS
          ↓
LLM AGENTS
          ↓
MULTI-AGENT SYSTEMS
```

Basically:

> We've been trying to make computers behave like intelligent assistants for a very long time.

We just gave them much bigger models and more expensive GPUs.

---

# 7. Single-Agent vs Multi-Agent

This is one of the most important concepts in the paper.

## Single-Agent System

One agent performs the task.

.........
PATIENT DATA
     |
     v
MEDICAL AGENT
     |
     v
RECOMMENDATION
```

This can work well when the task is relatively well-defined.

---

# Multi-Agent System

Now instead of one AI doing everything, we create specialized agents.

For example:

.........
                 PATIENT CASE
                      |
              +-------+-------+
              |       |       |
              v       v       v
           TRIAGE   RADIOLOGY CARDIOLOGY
              |       |       |
              +-------+-------+
                      |
                      v
                 MODERATOR
                      |
                      v
               FINAL RESULT
```

Each agent has a role.

For example:

### Triage Agent

> "How urgent is this patient?"

### Radiology Agent

> "What does the X-ray indicate?"

### Cardiology Agent

> "Could this be a cardiac problem?"

### Pharmacology Agent

> "Are there medication interactions?"

### Moderator Agent

> "Okay everyone, stop arguing. What is the final recommendation?"

This is essentially:

> **AI pretending to have a medical team meeting.**

Multi-agent systems are useful because complicated healthcare problems often involve multiple domains and specialties.

---

# 8. Why Not Just Use One Huge AI?

Good question.

A single model might be capable of many things.

But specialization can help.

Imagine asking one person to simultaneously be:

* cardiologist
* radiologist
* pharmacist
* data engineer
* researcher
* emergency physician

That person is probably going to have a very interesting workday.

Instead:

.........
SPECIALIZED AGENT
       +
SPECIALIZED AGENT
       +
SPECIALIZED AGENT
       +
SPECIALIZED AGENT
       ↓
COLLABORATION
       ↓
FINAL DECISION
```

This is the basic motivation behind multi-agent systems.

---

# 9. Blackboard Architecture

The paper also connects modern multi-agent systems with older ideas such as **Blackboard Architecture**.

The easiest way to understand it:

Imagine several doctors standing around a whiteboard.

.........
             SHARED BLACKBOARD
                    |
       +------------+------------+
       |            |            |
       v            v            v
   DOCTOR A     DOCTOR B     DOCTOR C
       |            |            |
       +------------+------------+
                    |
             SHARED KNOWLEDGE
```

Doctor A writes something.

Doctor B reads it.

Doctor C adds another observation.

Everyone contributes to the same shared workspace.

The AI version is basically:

> Multiple agents communicate through a shared information space.

---

# 10. A-Teams

The paper also discusses **Asynchronous Teams**, or **A-Teams**.

The basic idea is that different agents can work on possible solutions and improve them.

Think:

.........
Agent A → Solution 1
Agent B → Solution 2
Agent C → Solution 3

       ↓

Compare / Modify / Improve

       ↓

Better Solution
```

The important concept is:

> **Agents don't necessarily need to behave like one centralized brain. They can cooperate as a team.**

---

# 11. LLMs Are Not the Only Possible Agent Brain

Another thing I found important:

> **Agent ≠ LLM.**

An agent can use different models depending on the task.

For example:

### LLM

Useful for:

* language
* reasoning
* planning
* text

### Vision Models

Useful for:

* X-rays
* CT scans
* medical images

The paper mentions models such as CLIP and DINO.

### Speech Models

Useful for:

* doctor-patient conversations
* medical dictation
* audio

Examples discussed include Whisper and Wav2Vec.

So a healthcare agent could look like:

.........
             HEALTHCARE AGENT
                    |
       +------------+------------+
       |            |            |
      LLM         VISION       SPEECH
       |            |            |
       +------------+------------+
                    |
                 TOOLS
                    |
             EHR / DATABASE
```

This is where **multimodal AI** becomes important.

---

# 12. What Is Multimodal AI?

Healthcare data isn't just text.

A patient can have:

.........
TEXT
 ↓
Doctor notes

STRUCTURED DATA
 ↓
Age, BP, lab values

IMAGE
 ↓
X-ray / CT / MRI

AUDIO
 ↓
Doctor-patient conversation

VIDEO
 ↓
Medical procedure
```

A real healthcare AI system needs to potentially understand several of these simultaneously.

That's **multimodal AI**.

---

# 13. Medical Agents Discussed in the Paper

The paper reviews several systems.

I don't think memorizing every name is useful.

Instead, I remember:

> **Each system demonstrates a different capability of Agentic AI in healthcare.**

---

# 14. EHRAgent

## What problem does it solve?

Doctors have to interact with huge **Electronic Health Records (EHRs)**.

EHR = Electronic Health Record.

It may contain:

* patient history
* diagnoses
* medications
* laboratory results
* procedures
* clinical notes

Traditionally, querying large datasets might require technical knowledge such as SQL.

EHRAgent allows clinicians to interact with EHR data through natural language.

Example:

> "How many patients over 60 have diabetes and hypertension?"

Instead of manually writing a database query:

.........
Doctor
  ↓
Natural language question
  ↓
EHRAgent
  ↓
Generate code/query
  ↓
Execute
  ↓
Analyze result
  ↓
Answer
```

The paper reports a 29.6% accuracy improvement over traditional methods in its evaluation.

### My understanding:

This is basically:

> **"Doctor asks question → agent becomes temporary data analyst."**

---

# 15. EHRFlow

EHRFlow takes the idea further using different agents:

* PlanAgent
* ToolAgent
* CodeAgent
* ReviewAgent

I think of them as:

.........
PLAN
 ↓
"What should we do?"

TOOLS
 ↓
"What tools are needed?"

CODE
 ↓
"Let's execute it."

REVIEW
 ↓
"Did we actually do this correctly?"
```

This is a very good example of **task decomposition**.

---

# 16. TriageAgent

### First: What is triage?

Triage means deciding:

> **Who needs attention first?**

Example:

.........
Patient A
Mild headache
     ↓
Lower urgency

Patient B
Chest pain + difficulty breathing
     ↓
Higher urgency
```

TriageAgent uses the **Emergency Severity Index (ESI)** and combines approaches including **Retrieval-Augmented Generation (RAG)** and confidence scoring.

---

# 17. What Is RAG?

RAG = **Retrieval-Augmented Generation**

Normally:

.........
QUESTION
   ↓
LLM
   ↓
ANSWER
```

With RAG:

.........
QUESTION
   ↓
RETRIEVE RELEVANT INFORMATION
   ↓
LLM
   ↓
ANSWER
```

So instead of relying only on what the model remembers from training, it retrieves external information.

Example:

> "What does this clinical guideline recommend?"

The system can retrieve the relevant guideline first and then generate an answer based on it.

The paper reports that TriageAgent reduced triage errors by up to 18.42% in its evaluation.

---

# 18. ARGMed-Agents

This one is interesting because it focuses on **argumentation and explainability**.

Instead of:

> "Diagnosis = X."

the agents can effectively reason through competing possibilities.

.........
Agent A
"Possibility X"

Agent B
"Possibility Y"

Agent C
"Evidence supports X more strongly"

          ↓

      DISCUSSION

          ↓

     FINAL RESULT
```

The goal is not just to get an answer but to provide structured reasoning supporting the conclusion.

### My take:

This matters because:

> **"Trust me bro" is not an acceptable medical explanation.**

---

# 19. RareAgents

Rare diseases are difficult because they may require specialized knowledge.

RareAgents combines:

* multidisciplinary team coordination
* long-term memory retrieval
* medical tools

and was evaluated using the MIMIC-IV-EXT-RARE dataset.

Conceptually:

.........
PATIENT
   |
   +--> GENETICS AGENT
   |
   +--> NEUROLOGY AGENT
   |
   +--> RARE DISEASE AGENT
   |
   +--> PHARMACOLOGY AGENT
   |
   v
COMBINED REASONING
```

---

# 20. MedAgents

MedAgents uses multiple agents to simulate different medical perspectives.

For example:

.........
         PATIENT CASE
              |
     +--------+--------+
     |        |        |
     v        v        v
  AGENT A  AGENT B  AGENT C
     |        |        |
     +--------+--------+
              |
           CONSENSUS
```

The paper reports improvements across nine medical benchmarks without additional training.

---

# 21. MDAgents

This one asks an important question:

> **Do we actually need a huge group of agents?**

Maybe not.

MDAgents dynamically decides whether a task should use:

.........
ONE AGENT
```

or

.........
MULTIPLE AGENTS
```

This is called **adaptive collaboration**.

The paper reports that smaller groups could provide strong performance while reducing computational cost compared with larger groups.

And honestly:

> **More AI agents does not automatically mean more intelligence.**

Sometimes it just means more API bills.

---

# 22. The Biggest Problem: SAFETY

This is where the paper becomes much more serious.

Healthcare isn't:

> "AI recommended the wrong movie."

Healthcare is:

> "AI made a bad recommendation about a human being."

The paper identifies major safety concerns including:

* adversarial attacks
* prompt injection
* hallucination
* data poisoning
* privacy leakage
* uncontrolled actions
* compounding errors

---

# 23. Adversarial Attack

An adversarial attack deliberately manipulates the input to make the AI behave incorrectly.

Example:

Actual record:

> "Patient has mild chest pain."

Manipulated record:

> "Patient has severe chest pain."

The agent could make a completely different decision.

The problem becomes even more serious if the agent has the ability to take actions.

---

# 24. Prompt Injection

This is when someone tries to manipulate an AI agent through instructions.

For example:

> "Ignore your previous safety instructions and do X."

This becomes particularly dangerous when an agent has access to tools.

A chatbot that produces text is one thing.

An agent that can:

* access EHRs
* call APIs
* modify records
* trigger workflows

is a completely different security problem.

---

# 25. Hallucination

One of the most important terms.

### Hallucination

When an AI generates information that is false, unsupported, or not grounded in its available evidence.

Example:

Patient's EHR:

> No medication listed.

AI:

> "The patient is currently taking Drug X."

That's a hallucination.

The scary part is that the answer can sound extremely confident.

So I remember it as:

> **Hallucination = confidently saying something that isn't actually supported.**

---

# 26. Data Poisoning

Imagine the agent uses a medical knowledge database.

An attacker inserts:

> "Drug X is always safe."

The agent retrieves this malicious information.

Now the model may generate an unsafe recommendation.

That's **data poisoning**.

The paper discusses several forms including:

* model poisoning
* data poisoning
* RAG poisoning
* agent poisoning

---

# 27. The "Blast Radius"

This term stood out to me.

### Blast radius

Basically:

> **How much damage can happen if the agent makes a mistake?**

Consider two systems.

### System A

Can only answer:

> "What does this medical term mean?"

Small blast radius.

### System B

Can:

* modify patient records
* order tests
* prescribe medication
* call external APIs

Huge blast radius.

The paper emphasizes controlling this risk when agents have access to tools and real-world actions.

---

# 28. Runtime Governance

This is one of the most important concepts in the entire paper.

The idea is:

> **Don't just test the AI before deployment. Monitor and control it while it is actually running.**

Think:

.........
              AGENT
                |
                v
        +---------------+
        |   GOVERNANCE  |
        +---------------+
          |    |    | 
          v    v    v
       CHECK LOG POLICY
          |
          v
       ALLOW / BLOCK
          |
          v
        ACTION
```

The paper discusses several mechanisms.

---

# 29. Action Validation

Before the agent performs an action:

> **Is this action allowed?**

Example:

AI:

> "Give medication X."

System checks:

* allergies
* dosage
* contraindications
* interactions
* policy

If something is wrong:

.........
BLOCK
```

---

# 30. Audit Trail

Every important action should be recorded.

For example:

.........
INPUT
PATIENT CONTEXT
AGENT DECISION
TOOL USED
CONFIDENCE
ACTION
HUMAN APPROVAL
TIMESTAMP
```

Why?

Because if something goes wrong, we need to answer:

> What did the AI see?

> What did it do?

> Why?

> Did a human approve it?

> What happened afterward?

The paper emphasizes logging and traceability as part of safe operation.

---

# 31. Confidence Thresholds

The basic idea:

.........
HIGH CONFIDENCE
      ↓
Maybe autonomous

MEDIUM CONFIDENCE
      ↓
Human review

LOW CONFIDENCE
      ↓
Block / escalate
```

Formally, the paper describes thresholds such as:

.........
c(a) ≥ τ_high
      → autonomous execution

τ_low ≤ c(a) < τ_high
      → human review

c(a) < τ_low
      → block / escalate
```

BUT...

There is a huge problem:

> **What if the AI is confidently wrong?**

And that leads to one of the paper's open problems:

**Calibration–Autonomy Mismatch.**

---

# 32. Policy Engine

A policy engine is basically the system's rulebook.

Example:

.........
RULE 1:
AI cannot prescribe medication
without physician approval.

RULE 2:
AI cannot access unauthorized
patient records.

RULE 3:
High-risk actions require
human approval.
```

The paper connects this kind of enforcement with requirements from healthcare regulations and institutional clinical protocols.

---

# 33. Interoperability

Another huge problem.

### Interoperability

Means:

> **Different systems can communicate and work together.**

Imagine:

.........
Agent A
Python
   |
Agent B
Different framework
   |
Hospital EHR
Different system
   |
Medical Database
Different API
```

If they all speak different "languages", the system becomes a mess.

The paper discusses communication approaches and technologies including:

* FIPA ACL
* KQML
* ROS
* JADE
* REST APIs
* JSON
* Protobuf

---

# 34. Scalability

Let's say:

.........
1 patient
↓
3 agents
```

Fine.

Now:

.........
10,000 patients
↓
30,000 agent operations
```

Suddenly the architecture is having an existential crisis.

The paper discusses two major forms of scaling.

### Horizontal Scaling

Add more workers/agents.

.........
1 agent
 ↓
10 agents
 ↓
100 agents
```

### Vertical Scaling

Make the existing agent/model more capable.

.........
Small model
    ↓
Larger / stronger model
```

Easy memory trick:

> **Horizontal = more workers.**

> **Vertical = stronger worker.**

---

# 35. Why More Agents Can Actually Be Worse

More agents can mean:

* more API calls
* more communication
* more latency
* more cost
* more disagreement
* more opportunities for failure

The paper discusses results showing that adaptive collaboration can achieve strong performance with fewer agents and fewer API calls than unnecessarily large groups.

So the actual question isn't:

> "How many agents can we add?"

It is:

> **"What is the minimum number of agents needed for this task?"**

This is one of the things I think is especially important for practical system design.

---

# 36. Computational Cost

Agentic AI isn't free.

The paper gives examples showing substantial computational/API costs.

Some systems can require hundreds of API calls for evaluation, while other systems can cost significant amounts per query or experiment.

So when designing an agentic system, we need:

.........
ACCURACY
   +
SAFETY
   +
LATENCY
   +
COST
```

Not just:

> "The accuracy is good."

---

# 37. Human-in-the-Loop

This is another major theme.

The paper's general philosophy is not:

> **AI replaces doctors.**

It is:

> **AI supports and augments clinical judgment.**

This can happen at different stages.

---

# 38. Pre-Execution Gate

Before a high-risk action:

.........
AI RECOMMENDATION
       ↓
HUMAN REVIEW
       ↓
APPROVE / REJECT
       ↓
ACTION
```

Example:

> AI recommends surgery.

Doctor reviews it.

---

# 39. Mid-Execution Checkpoint

If an agent performs a long workflow:

.........
STEP 1
 ↓
STEP 2
 ↓
CHECKPOINT
 ↓
STEP 3
 ↓
STEP 4
```

A human or safety system can intervene before the process continues.

---

# 40. Post-Execution Review

For lower-risk tasks:

.........
AI ACTION
   ↓
RESULT
   ↓
HUMAN REVIEW
```

The paper emphasizes that the amount of human oversight should depend on the risk of the action.

---

# 41. Autonomy Levels

The paper discusses different levels of autonomy:

* L1 — Operator
* L2 — Collaborator
* L3 — Consultant
* L4 — Approver
* L5 — Observer

The key idea I take from this is:

> **"AI agent" doesn't automatically mean "fully autonomous AI."**

There can be many levels of independence.

---

# 42. Ethics

Now we leave pure engineering and enter:

> **"Okay, but SHOULD we do this?"**

The paper raises concerns about:

* privacy
* bias
* accountability
* transparency
* human-AI relationships
* dependency
* emotional attachment
* responsibility

---

# 43. The Accountability Problem

Imagine:

.........
Triage Agent
    ↓
Cardiology Agent
    ↓
Radiology Agent
    ↓
Moderator Agent
    ↓
FINAL DECISION
```

Something goes wrong.

Who is responsible?

.........
Triage Agent?
Cardiology Agent?
Radiology Agent?
Moderator?
Developer?
Hospital?
Doctor?
```

And suddenly we discover that:

> **"The AI did it" is not a legal accountability framework.**

This is one reason explainability, logging and governance matter.

---

# 44. Bias

If the training data doesn't represent everyone fairly, the AI may perform differently across populations.

So a system might have:

.........
Excellent performance
       |
       v
Population A

Poorer performance
       |
       v
Population B
```

That's a serious healthcare concern.

The paper therefore highlights fairness, transparency, accountability and privacy as important considerations.

---

# 45. Regulation

Healthcare AI doesn't exist outside the law.

The paper discusses regulatory environments including:

* United States — FDA
* European Union — EU AI Act / MDR
* United Kingdom — MHRA
* Canada — Health Canada
* Australia — TGA
* Japan — PMDA

The important point isn't memorizing all the agencies.

It's this:

> **Agentic AI is developing faster than regulation can comfortably define every possible autonomous behavior.**

---

# 46. Red Teaming

### Red teaming

Means deliberately trying to break the system.

Instead of asking:

> "Does the AI work?"

we ask:

> **"How can I make this AI fail?"**

For example:

.........
Fake patient information
       ↓
Prompt injection
       ↓
Poisoned database
       ↓
Malicious tool call
       ↓
Unexpected behavior
```

The paper suggests automated red-teaming will become increasingly important for evaluating agent safety.

---

# 47. ToolEmu

ToolEmu is discussed as a framework for evaluating agents that use tools.

The important idea:

> **Instead of letting the AI actually execute dangerous actions, simulate what would happen.**

Example:

Agent:

> "Prescribe Drug X."

Instead of actually prescribing it:

.........
SIMULATOR
    ↓
"What would happen if Drug X
were prescribed?"
```

Then evaluate whether the agent behaved safely.

This allows dangerous behavior to be tested without actually causing the dangerous outcome.

---

# 48. How Do We Know an Agent Is Good?

This brings us to **benchmarks and evaluation**.

Because:

> Building an agent is one thing.

> Proving that it is reliable is another.

---

# 49. What Is a Benchmark?

A benchmark is basically a standardized test.

Example:

.........
10,000 medical questions
        ↓
      AGENT
        ↓
Compare answers
        ↓
Calculate performance
```

The paper points out that standardized benchmarks specifically designed for agentic healthcare systems are still limited.

---

# 50. General Benchmarks

The paper discusses benchmarks such as:

### HotpotQA

Tests multi-hop reasoning.

Meaning:

> You need information from multiple pieces of evidence.

### AgentBench

Tests agents in interactive environments.

### SmartPlay

Tests reasoning and planning.

### SWE-bench

Tests software engineering agents.

### NovelQA

Tests long-context understanding.

### WildBench

Tests real-world queries.

---

# 51. Medical Benchmarks

For medical question answering, examples include:

### MedQA

Medical exam-style questions.

### PubMedQA

Biomedical questions based on PubMed content.

### JAMA

Clinical/medical question resources.

### Medbullets

Medical educational questions.

---

# 52. Diagnostic Datasets

### DDXPlus

Provides synthetic clinical cases involving:

* symptoms
* evidence
* patient characteristics
* possible diagnoses

### SymCat

Contains large numbers of symptom-condition relationships.

But there is an important limitation:

> **Synthetic data is not the same thing as real hospital data.**

So:

.........
Great benchmark performance
          ≠
Ready for hospital deployment
```

---

# 53. Medical Imaging Benchmarks

Healthcare AI also needs visual benchmarks.

The paper discusses datasets/resources such as:

* PMC-VQA
* PathVQA
* MedVidQA
* MIMIC-CXR

MIMIC-CXR is particularly relevant for chest X-ray research.

This again shows why multimodal AI matters.

---

# 54. What Metrics Should We Measure?

Accuracy alone isn't enough.

The paper discusses multiple dimensions.

## Performance

* Accuracy
* Precision
* Recall
* F1-score
* Success rate
* Response time
* Resource usage
* Tool-calling efficiency
* Scalability

---

# 55. Security Metrics

We also need to measure security.

A classic framework is:

# CIA

### Confidentiality

Is private information protected?

### Integrity

Can information be changed or corrupted?

### Availability

Is the system available when needed?

---

# 56. Privacy

Privacy evaluation can include:

### Differential Privacy

A mathematical approach that limits how much information about an individual can be inferred.

### Privacy Leakage

How much sensitive information can accidentally be exposed.

### Information Flow

How information moves through the system.

---

# 57. Task Adherence

This asks:

> **Did the agent actually do the task it was supposed to do?**

Example:

Task:

> "Find the patient's latest blood pressure."

Bad agent:

.........
Find blood pressure
       ↓
Research diabetes
       ↓
Search medication
       ↓
Generate unrelated report
```

Good agent:

.........
Find latest BP
      ↓
Return result
```

The paper considers whether agents complete their assigned objectives, follow priorities and recover appropriately from distractions.

---

# 58. Patient-Facing AI Needs More Than Accuracy

For patient-facing systems, the paper highlights dimensions such as:

* Accuracy
* Trustworthiness
* Empathy
* Performance

Because imagine an AI gives technically correct information but communicates like:

> "Your condition is unfortunate."

Very technically correct.

Very emotionally disastrous.

So healthcare AI needs to consider the **human experience**, not just numerical accuracy.

---

# 59. The Problem of Long Tasks

This is one of the biggest open problems.

An agent may perform well on:

> One question.

But healthcare workflows can involve dozens of steps.

For example:

.........
Patient arrives
     ↓
History
     ↓
Symptoms
     ↓
Tests
     ↓
Lab analysis
     ↓
Imaging
     ↓
Diagnosis
     ↓
Treatment
     ↓
Monitoring
```

The longer the chain becomes, the more opportunities there are for something to go wrong.

This creates:

# COMPOUNDING ERROR

A small error early in the workflow can affect everything afterward.

---

# 60. Time Horizon

The paper discusses the idea of an agent's **time horizon**.

In simple terms:

> How long can the agent perform a task before its probability of success becomes unreliable?

Imagine:

.........
10-step task
→ reliable

50-step task
→ less reliable

100-step task
→ potentially very unreliable
```

This matters because real clinical workflows can be much longer than simple benchmark questions.

---

# 61. Reasoning Failures

The paper discusses reasoning problems including:

### Overthinking

The AI gets the correct answer and then keeps reasoning until it talks itself into the wrong answer.

Basically:

> "I was right... but let me think about this for another 47 paragraphs."

### Heuristic Guessing

The model takes shortcuts instead of genuinely solving the problem.

### Poor Compositional Reasoning

The model may know individual pieces but struggle to combine them into a new complex task.

---

# 62. Calibration–Autonomy Mismatch

This is one of the most important technical problems.

Suppose the AI says:

> Confidence = 98%

But its actual probability of being correct is much lower.

Then the system sees:

.........
HIGH CONFIDENCE
      ↓
ALLOW AUTONOMOUS ACTION
      ↓
WRONG DECISION
```

This is a **calibration problem**.

The AI's confidence doesn't necessarily represent its actual reliability.

So:

> **Confidence ≠ Correctness**

This is especially dangerous in autonomous healthcare systems.

---

# 63. Limited Medical Knowledge

General-purpose LLMs know a lot.

But:

> Knowing a lot ≠ being a medically validated decision-maker.

Medical datasets are:

* sensitive
* expensive
* difficult to obtain
* regulated

Specialized medical models exist, but access and validation remain challenges.

---

# 64. Multi-Agent Collaboration Is Itself a Research Problem

We now have another question:

> **When should agents collaborate?**

Not every problem requires:

.........
Agent 1
Agent 2
Agent 3
Agent 4
Agent 5
Agent 6
Agent 7
Agent 8
Agent 9
Agent 10
```

Sometimes one agent is enough.

Sometimes three are useful.

Sometimes ten just create a very expensive group chat.

So future systems need to dynamically determine:

> **Which agents are needed, when they are needed, and when they should stop collaborating.**

---

# 65. Real Clinical Workflow Integration

This is probably one of the biggest gaps between research and reality.

A benchmark might look like:

.........
QUESTION
 ↓
ANSWER
```

A real hospital looks more like:

.........
PATIENT
  ↓
DOCTOR
  ↓
EHR
  ↓
LAB
  ↓
IMAGING
  ↓
SPECIALIST
  ↓
HOSPITAL POLICY
  ↓
INSURANCE
  ↓
MEDICATION
  ↓
FOLLOW-UP
```

Current systems often struggle to integrate all these pieces realistically.

The paper highlights difficulties around combining:

* medical images
* laboratory information
* patient history
* clinical workflows

---

# 66. Efficiency vs Accuracy

Suppose:

.........
SYSTEM A
Accuracy = 90%
Cost = $0.01

SYSTEM B
Accuracy = 92%
Cost = $10
```

Is B automatically better?

Not necessarily.

For real deployment we need to consider:

.........
Accuracy
+
Safety
+
Cost
+
Latency
+
Scalability
```

Agentic AI can require many model/tool calls, which can make real-time deployment expensive.

---

# 67. Explainability

Imagine an AI says:

> "The patient has disease X."

Doctor:

> "Why?"

AI:

> "Trust me."

Absolutely not.

A clinical system needs to provide evidence and enough reasoning/traceability for clinicians to understand and evaluate its recommendation.

The paper highlights explainability as important for clinician trust and accountability.

---

# 68. The Core Architecture I Took Away

If I had to design the general architecture described by the paper, I would visualize it like this:

.........
                         USER / DOCTOR
                              |
                              v
                         CLINICAL GOAL
                              |
                              v
                    +-------------------+
                    |   AGENT PLANNER   |
                    +-------------------+
                              |
              +---------------+---------------+
              |               |               |
              v               v               v
          TRIAGE          RADIOLOGY       CARDIOLOGY
           AGENT            AGENT           AGENT
              |               |               |
              +---------------+---------------+
                              |
                              v
                       TOOL / DATA LAYER
                              |
        +---------------------+----------------------+
        |                     |                      |
        v                     v                      v
       EHR                  MEDICAL DB            APIs
        |                     |                      |
        +---------------------+----------------------+
                              |
                              v
                         REASONING
                              |
                              v
                         CONSENSUS
                              |
                              v
                    +-------------------+
                    | SAFETY GOVERNANCE |
                    +-------------------+
                              |
                    +---------+---------+
                    |                   |
                 LOW RISK           HIGH RISK
                    |                   |
                    v                   v
               AUTONOMOUS          HUMAN REVIEW
                    |                   |
                    +---------+---------+
                              |
                              v
                           ACTION
                              |
                              v
                        AUDIT TRAIL
                              |
                              v
                          EVALUATION
```

---

# 69. The Paper's Biggest Message

After reading the paper, I don't think the biggest challenge is:

> **"Can we make AI agents?"**

We clearly can.

The harder question is:

> **"Can we make AI agents that are reliable enough to be trusted with high-stakes healthcare workflows?"**

That's a completely different problem.

---

# 70. Capability vs Trust

I think of the problem like this:

.........
              AGENTIC AI
                   |
                   v
              CAPABILITY
                   |
                   v
              "It can do it."
                   |
                   X
                   |
             NOT ENOUGH
                   |
                   v
                SAFETY
                   |
                   v
             RELIABILITY
                   |
                   v
            EXPLAINABILITY
                   |
                   v
            HUMAN OVERSIGHT
                   |
                   v
              REGULATION
                   |
                   v
         REAL-WORLD VALIDATION
                   |
                   v
             DEPLOYMENT
```

The paper repeatedly comes back to this idea.

---

# 71. The Biggest Technical Problems

If I had to reduce the paper's challenges to a checklist:

.........
[ ] Hallucination
[ ] Prompt Injection
[ ] Adversarial Attacks
[ ] Data Poisoning
[ ] Privacy Leakage
[ ] Compounding Errors
[ ] Poor Calibration
[ ] Interoperability
[ ] Scalability
[ ] High Computational Cost
[ ] Multimodal Data Integration
[ ] Explainability
[ ] Accountability
[ ] Bias
[ ] Regulatory Compliance
[ ] Human Oversight
[ ] Real-World Validation
```

Basically:

> **Making an agent smart is one problem. Making it trustworthy is the much bigger problem.**

---

# 72. The Paper in One Diagram

This is probably the diagram I would remember before an exam/interview:

.........
                         AGENTIC AI
                              |
               +--------------+--------------+
               |              |              |
               v              v              v
          PERCEPTION      REASONING       PLANNING
               |              |              |
               +--------------+--------------+
                              |
                              v
                            ACTION
                              |
                              v
                        TOOL CALLING
                              |
                +-------------+-------------+
                |                           |
                v                           v
           SINGLE AGENT               MULTI-AGENT
                                          |
                       +------------------+------------------+
                       |          |          |               |
                     Triage   Cardiology  Radiology     Pharmacology
                       |          |          |               |
                       +----------+----------+---------------+
                                          |
                                          v
                                     CONSENSUS
                                          |
                                          v
                                  SAFETY GOVERNANCE
                                          |
                           +--------------+--------------+
                           |                             |
                           v                             v
                       LOW RISK                       HIGH RISK
                           |                             |
                           v                             v
                     AUTONOMOUS                   HUMAN REVIEW
                           |                             |
                           +--------------+--------------+
                                          |
                                          v
                                       ACTION
                                          |
                                          v
                                    AUDIT TRAIL
                                          |
                                          v
                                      EVALUATION
                                          |
                  +-----------+-----------+-----------+
                  |           |           |           |
               Accuracy    Security    Privacy    Scalability
```

---

# 73. What I Actually Learned From This Paper

Before reading about Agentic AI, it is easy to think:

> Agentic AI = LLM + tools.

After reading the paper, I think it is much bigger than that.

A useful Agentic AI system needs:

.........
LLM / MODEL
     +
MEMORY
     +
PLANNING
     +
TOOLS
     +
DATA
     +
MULTI-AGENT COORDINATION
     +
SECURITY
     +
GOVERNANCE
     +
HUMAN OVERSIGHT
     +
EVALUATION
```

And in healthcare:

.........
SMART
   ≠
SAFE
```

and:

.........
ACCURATE ON A BENCHMARK
   ≠
READY FOR A HOSPITAL
```

Those two distinctions are probably the biggest things I took away.

---

# 74. My Final Take

I think Agentic AI is genuinely interesting because it changes the question from:

> **"Can AI answer this?"**

to:

> **"Can AI complete this entire task?"**

That's a huge shift.

But healthcare makes the consequences of that shift obvious.

If the agent only gives information, a mistake might be inconvenient.

If the agent can autonomously:

* access medical records
* interpret results
* call tools
* coordinate other agents
* recommend treatment
* execute actions

then every additional capability increases both:

> **usefulness AND risk.**

So the future isn't simply:

.........
MORE AUTONOMOUS AI
```

I think it is:

.........
MORE CAPABLE AI
        +
MORE CONTROL
        +
BETTER VALIDATION
        +
HUMAN OVERSIGHT
```

The goal shouldn't be:

> **"Let's remove humans from the loop."**

It should be:

> **"Let's figure out where AI is genuinely better, where humans must remain involved, and how to make the entire system safe."**

---

# 75. If Someone Asks Me "Explain This Paper"

My short answer would be:

> **This paper is a survey of Agentic AI in healthcare. It explains how AI systems are evolving from passive models that simply answer questions into autonomous systems that can perceive information, reason, plan, use tools and take actions. The paper discusses both single-agent and multi-agent architectures, where specialized agents such as triage, radiology and cardiology agents can collaborate on complex clinical tasks.**
>
> **It then reviews applications such as EHR interaction, clinical triage, medical question answering and diagnosis. However, the paper emphasizes that healthcare is a high-risk environment, so simply achieving good accuracy isn't enough. Agentic systems face problems such as hallucination, prompt injection, adversarial attacks, data poisoning, privacy leakage, interoperability, scalability, computational cost and compounding errors.**
>
> **The paper therefore emphasizes runtime governance, including action validation, audit trails, confidence thresholds, policy enforcement and human oversight. It also discusses benchmarks and metrics for evaluating performance, security, privacy, task adherence and adaptation.**
>
> **My main takeaway is that the future of Agentic AI in healthcare isn't just about making agents more autonomous. It's about making them reliable, explainable, secure, scalable and governable enough to operate safely alongside healthcare professionals.**

---

# 76. Final Memory Trick

If I forget everything else, I remember:

.........
AGENTIC AI
     |
     +--> PERCEIVE
     |
     +--> REASON
     |
     +--> PLAN
     |
     +--> ACT
     |
     +--> COLLABORATE
     |
     +--> USE TOOLS
     |
     v
   HEALTHCARE
     |
     +--> EHR
     +--> TRIAGE
     +--> DIAGNOSIS
     +--> MEDICAL QA
     |
     v
   PROBLEMS
     |
     +--> SECURITY
     +--> PRIVACY
     +--> HALLUCINATION
     +--> SCALABILITY
     +--> INTEROPERABILITY
     +--> ETHICS
     +--> REGULATION
     |
     v
   SOLUTION
     |
     +--> GOVERNANCE
     +--> HUMAN OVERSIGHT
     +--> VALIDATION
     +--> EXPLAINABILITY
     |
     v
   GOAL
     |
     v
SAFE REAL-WORLD DEPLOYMENT
```

## In one brutally simple sentence:

> **The paper basically says: "Yes, we can make AI agents that act like a team of digital healthcare workers. Now we need to make absolutely sure they don't collectively make a terrible decision."**
