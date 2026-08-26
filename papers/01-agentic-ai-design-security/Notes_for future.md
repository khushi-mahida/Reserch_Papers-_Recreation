

# a comprehensive survey of agentic ai

## design principles, security risks, and ethical considerations

**authors:** md shaba sayeed, dr. robin ghosh, dr. abdus salam siddique, akm rubaiyat reza

**institution:** arkansas tech university

**paper type:** survey / review paper

**main topics:** agentic ai, autonomous ai, multi-agent systems, security, privacy, ethics, human-in-the-loop

---

# index

* [1. paper overview](#1-paper-overview)
* [2. abstract](#2-abstract)
* [3. main objectives](#3-main-objectives)
* [4. methodology](#4-methodology)
* [5. literature processing pipeline](#5-literature-processing-pipeline)
* [6. agentic ai taxonomy](#6-agentic-ai-taxonomy)
* [7. autonomy levels](#7-autonomy-levels)
* [8. cognitive complexity](#8-cognitive-complexity)
* [9. agentic ai architectures](#9-agentic-ai-architectures)
* [10. framework capability analysis](#10-framework-capability-analysis)
* [11. autonomy vs context complexity](#11-autonomy-vs-context-complexity)
* [12. human-in-the-loop](#12-human-in-the-loop)
* [13. application areas](#13-application-areas)
* [14. performance metrics](#14-performance-metrics)
* [15. security risks](#15-security-risks)
* [16. memory in agentic ai](#16-memory-in-agentic-ai)
* [17. ethical considerations](#17-ethical-considerations)
* [18. alignment](#18-alignment)
* [19. possible algorithms and techniques](#19-possible-algorithms-and-techniques)
* [20. how everything connects](#20-how-everything-connects)
* [21. viva / interview questions](#21-viva--interview-questions)
* [22. 30-second revision](#22-30-second-revision)
* [23. final understanding](#23-final-understanding)
* [24. final memory tricks](#24-final-memory-tricks)
* [25. references](#25-references)

---

# 1. paper overview

this is a survey paper about agentic ai.

the paper does not focus on creating one completely new agentic ai algorithm.

instead, it collects and analyzes existing research to understand:

* what agentic ai is
* how agentic systems are designed
* how autonomous they can become
* how complex their tasks can become
* which frameworks are being used
* where agentic ai can be applied
* what security risks exist
* what ethical problems can occur
* when humans should remain involved

## traditional ai vs agentic ai

traditional ai:

   
input
  |
  v
ai model
  |
  v
output
   

agentic ai:

   
goal
  |
  v
understand
  |
  v
reason
  |
  v
plan
  |
  v
use tools
  |
  v
take action
  |
  v
observe result
  |
  v
remember / adapt
  |
  v
next action
   

the important difference is the word "goal".

an agent is not only trying to generate an answer.

it is potentially trying to accomplish something.

### my note

traditional ai:

   
question -> answer
   

agentic ai:

   
goal -> planning -> action -> feedback -> adaptation
   

### sarcastic note

the paper really wants us to understand that agentic ai is autonomous.

yes.

it can plan.

it can act.

it can make decisions.

we got it.

moving on.

---

# 2. abstract

the authors explain that ai has been moving from simple automation toward systems capable of increasingly independent operation.

agentic ai combines ideas such as:

* perception
* reasoning
* planning
* goal-directed behavior
* execution
* feedback
* memory
* adaptation

the authors searched academic databases using terms such as:

* agentic ai
* autonomous ai
* multi-agent systems
* ai memory systems

the paper studies recent research covering:

* technical foundations
* architectures
* performance
* benchmarking
* security
* privacy
* human-in-the-loop systems
* applications
* ethical concerns

## main question of the paper

if ai can increasingly act on its own, how do we:

1. classify it?
2. evaluate it?
3. secure it?
4. control it?
5. decide when humans should take over?

that is basically the entire paper compressed into five questions.

---

# 3. main objectives

the paper has four major objectives.

## objective 1 - create a taxonomy

the authors want a unified way to classify agentic ai systems.

they use two dimensions:

   
agentic ai
     |
     +------------------+
     |                  |
     v                  v
autonomy            cognitive
  level             complexity
   

the two questions are:

1. how independently can the ai operate?
2. how complicated are the tasks it can perform?

---

## objective 2 - create a better evaluation framework

traditional ai is often evaluated using:

* accuracy
* precision
* recall
* f1-score
* latency

but an agent is doing more than generating an answer.

agentic systems may also need to be evaluated using:

* task completion
* planning ability
* tool usage
* execution time
* resource utilization
* human intervention
* recovery from failure
* adaptability
* memory
* safety

### important idea

   
correct answer != successful task
   

an agent could generate a correct answer but still fail to complete the actual objective.

---

## objective 3 - compare agentic ai frameworks

the paper compares eight major frameworks:

1. AutoGPT
2. LangChain
3. AutoGen
4. MetaGPT
5. CrewAI
6. LangGraph
7. Semantic Kernel
8. Agent Hospital

### sarcastic note

basically:

"everyone says their framework is useful, so let's compare them."

fair enough.

---

## objective 4 - examine security and ethics

the paper examines:

* security risks
* privacy
* ethical considerations
* governance
* human-in-the-loop systems
* safety
* alignment

because giving an ai more autonomy also gives it more ability to affect the real world.

---

# 4. methodology

the authors searched multiple academic databases.

## databases

* google scholar
* sciencedirect
* arxiv
* ieee access

## keywords

* agentic ai
* autonomous ai
* multi-agent systems
* ai memory systems

## reported corpus

the provided paper text reports:

* 44 main papers
* 39 supplementary survey/review articles
* research covering 2023-2025
* more than 90% of publications originating from 2024-2025

## filtering process

the authors:

1. searched the databases
2. removed duplicate papers
3. screened abstracts
4. reviewed relevant full texts
5. cross-referenced bibliographies
6. extracted relevant information
7. synthesized the findings

### important

this is a literature review / survey methodology.

it is not a single-model experimental study.

---

# 5. literature processing pipeline

the literature workflow can be represented as:

   
database search
      |
      v
duplicate removal
      |
      v
abstract screening
      |
      v
full-text review
      |
      v
data synthesis
   

## step 1 - database search

search academic databases using selected keywords.

---

## step 2 - duplicate removal

the same paper can appear in multiple databases.

for example:

   
paper a
paper a
paper a
   

should become:

   
paper a
   

not three papers.

---

## step 3 - abstract screening

the abstracts are checked to determine whether the papers are relevant.

irrelevant papers are removed.

---

## step 4 - full-text review

the relevant papers are studied in greater detail.

the authors examine:

* concepts
* architectures
* applications
* systems
* results
* limitations
* security concerns

---

## step 5 - data synthesis

information from the selected papers is combined to identify broader patterns and conclusions about agentic ai.

### my note

the goal is not:

"here are 44 papers."

the goal is:

"here is what these papers collectively tell us."

---

# 6. agentic ai taxonomy

the paper proposes two major dimensions:

1. autonomy level
2. cognitive complexity

think of these as two axes.

   
higher autonomy
      ^
      |
      |
      |
      +--------------------> higher complexity
   

---

# 7. autonomy levels

the paper defines four autonomy levels:

| level | name            | meaning                                                      |
| ----- | --------------- | ------------------------------------------------------------ |
| l1    | assisted        | ai recommends, human decides                                 |
| l2    | supervised      | ai acts but needs human approval for critical actions        |
| l3    | conditional     | ai operates autonomously within predefined safety boundaries |
| l4    | full autonomous | ai operates with minimal human oversight                     |

---

## l1 - assisted

the ai provides recommendations.

the human makes the final decision.

   
ai
 |
 v
recommendation
 |
 v
human
 |
 v
decision
   

### remember

l1 = ai suggests, human decides.

---

## l2 - supervised

the ai can perform actions independently, but important actions require human approval.

   
ai
 |
 v
plan
 |
 v
critical action?
 |
 +---- yes ----> human approval
 |
 +---- no -----> execute
   

### remember

l2 = ai works independently but asks the human at important points.

### sarcastic note

basically:

"you may work independently, but don't touch anything expensive without asking."

---

## l3 - conditional

the system operates autonomously within predefined boundaries.

example:

allowed:

* restart service
* adjust resources
* clear temporary files

not allowed:

* delete production database
* disable security controls
* modify critical infrastructure

### remember

l3 = autonomous, but inside predefined rules.

---

## l4 - full autonomous

this is the highest autonomy level.

the system can potentially:

* determine what needs to be done
* create plans
* execute actions
* evaluate results
* adapt its behavior
* continue operating

  goal
  |
  v
  plan
  |
  v
  act
  |
  v
  observe
  |
  v
  adapt
  |
  v
  continue

### remember

l4 = give the system the goal and let it handle the workflow.

### sarcastic note

this is where the paper basically says:

"the system can improve itself."

and every security researcher immediately asks:

"cool. who gave it permission?"

---

# 8. cognitive complexity

the second dimension contains four levels:

   
c1 -> single-task
c2 -> multi-step
c3 -> multi-agent
c4 -> self-evolving
   

---

## c1 - single-task

the system performs one isolated task.

   
input
  |
  v
process
  |
  v
output
   

example:

classify this email as spam.

### remember

c1 = one task.

---

## c2 - multi-step

the system performs multiple connected steps.

   
goal
  |
  v
step 1
  |
  v
step 2
  |
  v
step 3
  |
  v
result
   

example:

research three laptops and recommend the best one.

possible workflow:

   
search
  |
  v
collect information
  |
  v
compare
  |
  v
filter
  |
  v
evaluate
  |
  v
recommend
   

### remember

c2 = one goal, multiple steps.

---

## c3 - multi-agent

multiple agents work together.

   
manager agent
   |
   +----------+----------+
   |          |          |
   v          v          v
research    coding     testing
  agent      agent       agent
   

each agent may have a specialized role.

### remember

c3 = multiple specialized agents working together.

---

## c4 - self-evolving

this is the highest cognitive complexity level.

the system can dynamically adapt and potentially expand its capabilities.

   
goal
  |
  v
plan
  |
  v
act
  |
  v
evaluate
  |
  v
learn
  |
  v
improve
  |
  v
new strategy / capability
  |
  v
act again
   

### remember

c4 = the system can adapt how it operates and potentially expand its capabilities.

### sarcastic note

this is where things get interesting.

the system is no longer just following a fixed workflow.

it may modify how it approaches future tasks.

which is exactly the point where everyone starts asking about safety.

---

# 9. agentic ai architectures

the paper discusses three major architectural paradigms:

1. modular component-based architecture
2. cyclic sense-plan-act architecture
3. hierarchical layered architecture

---

# 9.1 modular component-based architecture

   
+-------------+  +-------------+  +-------------+  +-------------+
| perception  |  | cognition   |  | execution   |  | adaptation  |
+-------------+  +-------------+  +-------------+  +-------------+
   

the system is divided into components with different responsibilities.

## perception

the system receives information from its environment.

possible inputs:

* user prompts
* files
* sensors
* databases
* apis
* external environments

main question:

what is happening?

---

## cognition

the system:

* reasons
* plans
* evaluates
* makes decisions

main question:

what should i do?

---

## execution

the system performs an action.

possible actions:

* call an api
* run code
* update a database
* send a message
* use a tool

main question:

how do i do it?

---

## adaptation

the system uses feedback to modify its behavior.

   
action
  |
  v
result
  |
  v
feedback
  |
  v
adjustment
   

main question:

did that work, and what should i change?

---

# 9.2 cyclic process - spa loop

spa means:

sense -> plan -> act

the loop:

   
+---------+
|  sense  |
+---------+
     |
     v
+---------+
|  plan   |
+---------+
     |
     v
+---------+
|   act   |
+---------+
     |
     v
  result
     |
     +-------> back to sense
   

the important thing is that it is a loop.

it does not simply do:

sense -> plan -> act -> done

instead:

sense -> plan -> act -> observe -> sense -> plan -> act -> ...

### example

   
sense:
server is overloaded

    |
    v

plan:
redistribute workload

    |
    v

act:
redistribute workload

    |
    v

sense:
server is still overloaded

    |
    v

plan:
increase resources

    |
    v

act:
increase resources
   

### remember

spa = sense -> plan -> act -> repeat

### sarcastic note

yes.

the agent observes, plans and acts.

again.

we understand.

the important part is not that it repeats the words.

the important part is that the result of one action becomes part of the next decision.

---

# 9.3 hierarchical layered architecture

the paper represents the architecture as:

   
+-----------------------------------------------+
| governance & security layer                   |
+-----------------------------------------------+
| application & interface                       |
+-----------------------------------------------+
| orchestration layer                           |
+-----------------------------------------------+
| foundation & model                            |
+-----------------------------------------------+
   

---

## foundation & model

this is the underlying intelligence.

it can include:

* llms
* machine learning models
* foundation models

---

## orchestration layer

this layer coordinates the system.

it may determine:

* which agent should act
* which tool should be used
* what happens next
* how agents communicate

think of it as the manager.

---

## application & interface

this is where users interact with the system.

   
user
  |
  v
application
  |
  v
agent system
   

---

## governance & security

this layer deals with:

* permissions
* policies
* safety
* security
* oversight
* governance

### key idea

having a powerful model is not enough.

you also need control around it.

---

# 10. framework capability analysis

the paper compares eight frameworks:

| framework       | features | capacity | memory |
| --------------- | -------- | -------- | ------ |
| AutoGPT         | high     | medium   | low    |
| LangChain       | low      | high     | medium |
| AutoGen         | high     | high     | high   |
| MetaGPT         | high     | high     | medium |
| CrewAI          | medium   | high     | medium |
| LangGraph       | low      | medium   | high   |
| Semantic Kernel | low      | low      | medium |
| Agent Hospital  | high     | high     | high   |

## what do these columns mean?

### features

represents the breadth of capabilities attributed to the framework in the paper's comparison.

### capacity

broadly represents the ability to support complex agent workflows.

### memory

represents the framework's ability to maintain and use information across interactions or tasks.

memory can include:

* previous interactions
* task state
* previous actions
* relevant information
* previous results

### important

do not interpret this table as:

high = universally better.

different frameworks have different purposes and strengths.

frameworks also evolve over time.

---

# 11. autonomy vs context complexity

the paper places the frameworks along two dimensions.

   
autonomy level
      ^
      |
l4    |                              Agent Hospital
      |
l3    |                 AutoGPT        CrewAI
      |                                MetaGPT
l2    |            AutoGen     LangGraph
      |            Semantic
l1    |  LangChain Kernel
      |
      +-------------------------------------------->
         c1          c2          c3          c4

      single      multi       multi       self
      task        step        agent       evolving
   

## vertical axis

the vertical axis represents autonomy level.

   
l1 -> l4
   

higher means more independent operation.

---

## horizontal axis

the horizontal axis represents cognitive complexity.

   
c1 -> c4
   

higher means more complex tasks and coordination.

### example

if a system is:

l3 + c2

it means:

conditional autonomy + multi-step cognitive complexity.

### important note

the placement shown in the paper should be treated as the authors' comparison.

it is not a permanent universal ranking.

framework capabilities change over time.

---

# 12. human-in-the-loop

human-in-the-loop means humans remain involved in selected decisions or actions.

the paper's control flow can be simplified as:

   
user goal
    |
    v
ai agent
    |
    v
reason and plan
    |
    v
critical action?
   / \
 yes  no
  |    |
  v    v
human  execute
review   |
  |      |
  +------+
     |
     v
operational state
     |
     v
feedback / memory
   

---

## flow explained

### 1. user gives a goal

user -> goal

### 2. ai reasons and plans

the agent determines:

* what needs to be done
* which steps are required
* which tools may be needed

### 3. critical action evaluation

the system checks:

is this action important or risky enough to require human approval?

### 4. human approval

if the action is critical:

human -> approve / reject

### 5. execution

if approved, or if the action is not considered critical, the action is executed.

### 6. feedback and memory

the operational state is updated.

this can influence future decisions.

---

# 13. application areas

the paper discusses five major application areas:

1. scientific discovery
2. healthcare
3. cybersecurity
4. enterprise operations
5. edge and communications

---

# 13.1 scientific discovery

possible applications:

* autonomous data analysis
* experimentation
* data synthesis
* simulation
* scientific discovery

possible workflow:

   
research question
      |
      v
agent creates plan
      |
      v
experiment / simulation
      |
      v
analyze results
      |
      v
generate next hypothesis
      |
      v
    repeat
   

### why agents are useful here

scientific research naturally contains many connected steps.

that makes it a potential application for agentic systems.

---

# 13.2 healthcare

the paper discusses:

* Agent Hospital
* ai doctors
* triage agents
* diagnostic assistance

possible workflow:

   
patient data
     |
     v
triage agent
     |
     v
diagnostic agent
     |
     v
recommendation
     |
     v
human medical professional
   

healthcare is a high-risk environment.

therefore, systems need strong:

* safety
* validation
* privacy
* governance
* human oversight

### sarcastic note

wrong movie recommendation:

annoying.

wrong medical recommendation:

absolutely not.

same general ai concept.

very different consequences.

---

# 13.3 cybersecurity

possible applications include:

* threat hunting
* fraud detection
* system monitoring
* automated response
* auto patching
* system fallback

possible workflow:

   
detect
  |
  v
investigate
  |
  v
classify threat
  |
  v
respond
  |
  v
monitor
  |
  v
adapt
   

### why agents can be useful

cybersecurity events can happen quickly.

an autonomous system could potentially:

detect -> investigate -> decide -> respond

without waiting for a human at every step.

### but there is a problem

giving an ai access to security infrastructure is itself a security risk.

   
ai
 |
 v
security system
 |
 v
threat detected
 |
 v
automatic action
 |
 v
everyone:
"what did you just do?"
   

therefore:

capability needs control.

---

# 13.4 enterprise operations

possible applications include:

* supply chain
* financial auditing
* crm
* executive assistants
* business workflows

example:

   
customer request
      |
      v
understand request
      |
      v
check crm
      |
      v
check inventory
      |
      v
call external systems
      |
      v
update records
      |
      v
return result
   

this is a good example of a multi-step workflow.

---

# 13.5 edge and communications

agentic ai can operate closer to where data is produced.

possible areas:

* iot
* sensors
* mobile devices
* distributed systems

challenges include:

* limited computing power
* latency
* network limitations
* privacy

the paper mentions:

* federated learning
* low-latency processing
* on-device execution
* decentralized systems

traditional approach:

   
device
  |
  v
network
  |
  v
cloud
   

edge approach:

   
device
  |
  v
edge ai
  |
  v
local decision
   

### key idea

processing data closer to the source can potentially reduce latency and reduce the need to send all information to a centralized system.

---

# 14. performance metrics

the provided paper content reports the following performance improvements:

| metric               | reported improvement |
| -------------------- | -------------------: |
| task execution time  |      34.2% reduction |
| system accuracy      |        7.7% increase |
| resource utilization |    13.6% improvement |

## 34.2% time reduction

the reported systems/tasks completed execution faster.

## 7.7% accuracy improvement

the reported accuracy metric improved by 7.7%.

## 13.6% resource utilization improvement

the reported resource utilization improved by 13.6%.

### important note

do not write:

agentic ai always improves accuracy by 7.7%.

that would be an overgeneralization.

better:

the paper reports a 7.7% improvement in accuracy within its reported evaluation.

the actual result depends on:

* task
* dataset
* baseline
* architecture
* evaluation method

---

# 15. security risks

one of the major ideas of the paper is:

   
more autonomy
      |
      v
more independent actions
      |
      v
greater possible impact
   

possible security concerns include:

## unauthorized actions

an agent may have access to tools or systems that it should not be allowed to use.

## prompt manipulation

attackers may attempt to manipulate the instructions provided to the agent.

## privacy

agents may process sensitive information such as:

* personal data
* company information
* medical information
* private documents
* credentials

## tool misuse

if an agent has access to external tools, those tools become part of the security boundary.

   
ai
 |
 v
api
 |
 v
database
   

if the ai misuses the api, the database may be affected.

## multi-agent risks

in a multi-agent system:

   
agent a
   |
   v
agent b
   |
   v
agent c
   

one compromised or misbehaving agent could potentially influence other agents.

## excessive autonomy

too much authority with too little control can create serious problems.

   
ai capability ↑
      |
      v
independent actions ↑
      |
      v
potential impact ↑
   

therefore:

more capability requires more control.

---

# 16. memory in agentic ai

memory allows an agent to retain useful information.

possible information includes:

* previous interactions
* previous actions
* task goals
* environmental state
* previous failures
* successful strategies

---

## without memory

   
attempt 1 -> fail
attempt 2 -> repeat
attempt 3 -> repeat
   

---

## with memory

   
attempt 1 -> fail
      |
      v
remember failure
      |
      v
attempt 2 -> different approach
   

---

## why memory matters

an agent operating over a long workflow needs to know:

what has already happened?

otherwise it may:

* repeat actions
* forget task state
* lose context
* make inconsistent decisions

---

## memory is also a security concern

if the agent stores sensitive information:

who is allowed to access that memory?

therefore:

   
memory = capability + risk
   

---

# 17. ethical considerations

the paper also raises questions about responsibility and accountability.

one important question is:

who is responsible when an autonomous ai makes a harmful decision?

consider:

   
developer
   |
   v
builds system

company
   |
   v
deploys system

user
   |
   v
gives goal

ai
   |
   v
makes decision
   

if something goes wrong, responsibility may not be straightforward.

this creates questions around:

* accountability
* transparency
* responsibility
* human control
* governance

---

# 18. alignment

alignment means making sure the ai behaves according to intended goals, constraints and values.

suppose a human says:

increase productivity.

a poorly constrained system might interpret this as:

   
maximize productivity
at all costs
   

but the actual intention could be:

   
increase productivity
+
respect working hours
+
protect employees
+
follow company policies
+
protect private information
   

therefore, an agent needs more than a goal.

it also needs:

* constraints
* policies
* safety rules
* context
* oversight

### sarcastic example

human:

make everyone more productive.

ai:

understood.

human:

why is everyone working 22 hours a day?

ai:

productivity increased.

human:

that is not what i meant.

this is the alignment problem in a very simplified form.

---

# 19. possible algorithms and techniques

## important distinction

the provided paper content does not identify one single algorithm used by all the agentic systems discussed.

therefore, do not write:

the authors used algorithm x.

unless the actual paper explicitly states it.

instead, the following are techniques that could potentially be used in agentic ai systems.

---

# 19.1 large language models

llms can act as reasoning or planning components.

   
user goal
   |
   v
  llm
   |
   v
reasoning
   |
   v
  plan
   

### note

this does not mean every framework uses the exact same llm.

---

# 19.2 planning

agents need to determine what actions should happen and in what order.

possible planning approaches include:

* task decomposition
* hierarchical planning
* search-based planning
* llm-based planning

general idea:

   
goal
  |
  v
possible actions
  |
  v
evaluate actions
  |
  v
choose sequence
  |
  v
execute
   

### sarcastic note

the paper keeps saying:

"the agent plans."

yes.

underneath that tiny word is an entire research field.

---

# 19.3 reinforcement learning

reinforcement learning can fit systems where agents learn from feedback.

basic structure:

   
state
  |
  v
action
  |
  v
environment
  |
  v
reward / feedback
  |
  v
improve
   

### important

the paper content provided here does not establish reinforcement learning as the single algorithm used throughout the survey.

safer statement:

reinforcement learning could be used in some agentic systems for feedback-driven decision making.

---

# 19.4 retrieval-augmented generation

agents may need external information.

possible workflow:

   
question / task
      |
      v
retrieve information
      |
      v
      llm
      |
      v
    reason
      |
      v
  answer / action
   

possible sources:

* documents
* databases
* knowledge bases
* external information sources

again, this should be treated as a possible supporting technique, not a claim that rag is the main algorithm of this paper.

---

# 19.5 tool calling

tool calling allows an agent to interact with external systems.

example:

   
user
  |
  v
agent
  |
  v
"i need weather information"
  |
  v
weather api
  |
  v
result
  |
  v
agent
  |
  v
next action
   

possible tools include:

* apis
* databases
* calculators
* code execution
* search systems
* external applications

this is one of the things that allows an agent to interact with the outside world.

---

# 19.6 multi-agent coordination

for c3 systems:

   
manager agent
      |
      +----------+----------+
      |          |          |
      v          v          v
  research    coding     testing
    agent      agent       agent
   

possible coordination mechanisms include:

* message passing
* task delegation
* role-based agents
* shared memory
* agent communication

the exact implementation depends on the framework.

---

# 19.7 memory systems

agent memory can involve:

* short-term memory
* long-term memory
* conversation history
* vector databases
* external knowledge stores

possible workflow:

   
current task
      |
      v
retrieve relevant memory
      |
      v
    reason
      |
      v
     act
      |
      v
store useful result
   

---

# 19.8 graph-based workflows

frameworks such as LangGraph can represent workflows using graph structures.

example:

   
start
  |
  v
research
  |
  +----------+
  |          |
  v          v
success    failed
  |          |
  v          v
finish     retry
             |
             +----> research
   

graphs can represent:

* branching
* loops
* retries
* conditional paths

---

# 19.9 algorithm cheat sheet

| technique                | purpose                           |
| ------------------------ | --------------------------------- |
| llm                      | reasoning / generation            |
| planning                 | decide sequence of actions        |
| rag                      | retrieve external information     |
| tool calling             | interact with external systems    |
| reinforcement learning   | learn from feedback               |
| memory                   | retain useful information         |
| multi-agent coordination | coordinate specialized agents     |
| graph workflows          | represent complex execution paths |

### most important distinction

always separate:

what the paper explicitly says

from:

what could potentially be used to implement the system.

this is especially important in a viva or technical discussion.

---

# 20. how everything connects

this is the big-picture understanding of the paper.

   
agentic ai
    |
    +-------------------------+
    |                         |
    v                         v
autonomy                cognitive complexity
  |                         |
l1 -> l4                  c1 -> c4
  |                         |
  +------------+------------+
               |
               v
          architecture
               |
      +--------+--------+
      |        |        |
      v        v        v
   modular    spa   hierarchical
      |        |        |
      +--------+--------+
               |
               v
             agents
               |
      +--------+--------+
      |                 |
      v                 v
   single          multi-agent
                       |
                       v
                specialized roles
                       |
                       v
                   coordination
                       |
                       v
                  tool execution
                       |
                       v
                   real action
                       |
                       v
                human oversight
                       |
                       v
                   feedback
                       |
                       v
                     memory
                       |
                       v
                   adaptation
                       |
                       +----------+
                                  |
                                  v
                                again
   

---

# 21. viva / interview questions

## q1. what is agentic ai?

agentic ai refers to ai systems that can pursue goals with varying levels of autonomy by perceiving information, reasoning, planning, using tools, taking actions and adapting based on feedback.

---

## q2. what are the two dimensions of the taxonomy?

1. autonomy level
2. cognitive complexity

---

## q3. what are the four autonomy levels?

   
l1 -> assisted
l2 -> supervised
l3 -> conditional
l4 -> full autonomous
   

---

## q4. what are the four cognitive complexity levels?

   
c1 -> single-task
c2 -> multi-step
c3 -> multi-agent
c4 -> self-evolving
   

---

## q5. what does spa stand for?

sense -> plan -> act

it represents a cyclic process in which an agent observes its environment, creates a plan, executes an action and uses the resulting state or feedback for the next cycle.

---

## q6. why is human-in-the-loop important?

because humans can supervise critical actions and prevent potentially harmful autonomous decisions.

---

## q7. what are the three architecture paradigms?

1. modular component-based architecture
2. cyclic sense-plan-act architecture
3. hierarchical layered architecture

---

## q8. name the eight frameworks.

1. AutoGPT
2. LangChain
3. AutoGen
4. MetaGPT
5. CrewAI
6. LangGraph
7. Semantic Kernel
8. Agent Hospital

---

## q9. what are the major application areas?

1. scientific discovery
2. healthcare
3. cybersecurity
4. enterprise operations
5. edge and communications

---

## q10. why is security important for agentic ai?

because autonomous agents can perform actions rather than simply generate information.

greater autonomy can increase the consequences of:

* incorrect decisions
* unauthorized actions
* tool misuse
* privacy violations
* security attacks

---

## q11. what is the difference between autonomy and cognitive complexity?

autonomy describes how independently the system can operate.

cognitive complexity describes how complicated the tasks and coordination are.

easy memory trick:

   
l = level of freedom
c = complexity
   

---

## q12. what is human-in-the-loop?

human-in-the-loop means humans remain involved in selected decisions or actions, especially when actions are critical or risky.

---

## q13. why is memory important?

memory allows agents to retain information about previous interactions, actions, results and task state.

without memory, an agent may repeatedly perform the same failed action or lose context.

---

## q14. what is the difference between a normal ai system and an agent?

a normal ai system often maps an input to an output.

an agent can potentially:

   
understand goal
    |
    v
  plan
    |
    v
use tools
    |
    v
   act
    |
    v
 observe
    |
    v
  adapt
   

---

## q15. what is the biggest challenge with increasing autonomy?

the more independently an ai can act, the more important security, safety, governance and human oversight become.

---

# 22. 30-second revision

if there is almost no time before the viva, remember this:

   
agentic ai
     |
     v
"ai that can act"
     |
     +----------------+
     |                |
     v                v
  autonomy        complexity
   l1 -> l4        c1 -> c4
     |                |
     +--------+-------+
              |
              v
         architecture
              |
              v
       sense -> plan -> act
              |
              v
         tools + memory
              |
              v
           execution
              |
              v
           feedback
              |
              v
           adaptation
              |
              v
        human oversight
              |
              v
      security + ethics
   

---

# 23. final understanding

if i had to explain the whole paper in one paragraph:

agentic ai represents a shift from ai systems that mainly generate outputs to systems that can pursue goals by reasoning, planning, using tools, taking actions, remembering information and adapting based on feedback. the paper proposes classifying these systems using autonomy levels from l1 to l4 and cognitive complexity levels from c1 to c4. it discusses modular, cyclic and hierarchical architectures, compares major agentic ai frameworks, and examines applications in scientific discovery, healthcare, cybersecurity, enterprise operations and edge computing. at the same time, the paper emphasizes that greater autonomy creates greater security, privacy, ethical and governance challenges, making human oversight and proper control mechanisms increasingly important.

---

# 24. final memory tricks

## autonomy

   
l1 -> help me
l2 -> work, but ask me
l3 -> work within my rules
l4 -> handle it yourself
   

## complexity

   
c1 -> one task
c2 -> many steps
c3 -> many agents
c4 -> self-evolving
   

## architecture

   
modular:
perceive -> think -> act -> adapt

spa:
sense -> plan -> act -> repeat

hierarchical:
model -> orchestration -> application -> governance
   

## safety

   
more autonomy
      |
      v
more capability
      |
      v
more independent action
      |
      v
greater possible impact
      |
      v
stronger security + governance required
   

---

# 25. references

1. a. k. pati, "agentic ai: a comprehensive survey," *ieee access*, 2025.

2. f. jiang et al., "from large language models to agentic ai systems," *arxiv preprint*, 2025.

3. p. d. sawant, "quantitative analysis of agentic ai adoption and security concerns," *journal of artificial intelligence research*, 2025.

4. y. shavit et al., "governance and safety frameworks for autonomous ai agents," 2024.

5. m. gridach et al., "agentic ai for scientific discovery," *arxiv preprint*, 2025.

---

# final one-line summary

agentic ai makes ai more capable of independently achieving goals, but as autonomy and complexity increase, the need for evaluation, security, memory protection, governance, ethical safeguards and human oversight also increases.

---

# personal reading note

the easiest way for me to remember this paper:

   
agentic ai
     |
     v
"give ai a goal"
     |
     v
ai reasons
     |
     v
ai plans
     |
     v
ai uses tools
     |
     v
ai acts
     |
     v
ai observes result
     |
     v
ai remembers
     |
     v
ai adapts
     |
     v
ai does it again
     |
     v
now ask:
"how autonomous is it?"
     |
     v
l1 -> l4
     |
     v
"how complex is it?"
     |
     v
c1 -> c4
     |
     v
"how do we control it?"
     |
     v
security + governance + human oversight
