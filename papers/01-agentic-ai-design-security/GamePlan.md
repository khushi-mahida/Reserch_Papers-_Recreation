

# Agentic AI Paper Recreation — Step-by-Step Research Plan



 MY project has **two layers**:

### Layer 1 — Recreate the original paper

Understand and reproduce:

* Literature-search strategy
* Agentic AI taxonomy
* Autonomy levels
* Cognitive complexity levels
* Framework comparison
* Security/privacy analysis

### Layer 2 — Extend it with data analytics

Turn those concepts into measurable variables and test them using:

* EDA
* Statistical testing
* Correlation analysis
* Clustering
* PCA
* Machine learning

### Overall pipeline


                    ORIGINAL PAPER
                          │
                          ▼
                ┌───────────────────┐
                │ Literature Search │
                └─────────┬─────────┘
                          ▼
                ┌───────────────────┐
                │ Paper Collection  │
                └─────────┬─────────┘
                          ▼
                ┌───────────────────┐
                │ Paper Screening   │
                └─────────┬─────────┘
                          ▼
                ┌───────────────────┐
                │ Data Extraction   │
                └─────────┬─────────┘
                          │
                          ▼
             ┌─────────────────────────┐
             │  AGENTIC AI DATASET     │
             └────────────┬────────────┘
                          │
             ┌────────────┼────────────┐
             ▼            ▼            ▼
           EDA       STATISTICS       ML
             │            │            │
             ▼            ▼            ▼
         Patterns    Hypothesis     Clustering
                     Testing         PCA
                                     Prediction
             └────────────┼────────────┘
                          ▼
                ┌───────────────────┐
                │ Framework Analysis│
                └─────────┬─────────┘
                          ▼
                ┌───────────────────┐
                │ Compare With      │
                │ Original Paper    │
                └─────────┬─────────┘
                          ▼
                ┌───────────────────┐
                │ FINAL FINDINGS    │
                └───────────────────┘
```

---

# PHASE 1 — Define Exactly What You're Trying to Prove

## STEP 1 — Convert the paper into research questions
### Main research question

> **Does increasing autonomy and cognitive complexity actually improve the performance of Agentic AI systems, or does it introduce greater security and human-oversight challenges?**
 breaking it into smaller  questions 
### RQ1

Does **autonomy** increase with **cognitive complexity**?

### RQ2

Does greater **cognitive complexity** improve performance?

### RQ3

Does greater **autonomy** increase security risk?

### RQ4

Does greater autonomy reduce human intervention?

### RQ5

Which characteristics are associated with high-performing Agentic AI systems?

### RQ6

Do the data support the conceptual taxonomy proposed by the original paper?

---

# PHASE 2 — Recreate the Literature Search

## STEP 2 — Define your search strategy

The original paper searched:

* Google Scholar
* ScienceDirect
* arXiv
* IEEE Access

with terms including:

* `"Agentic AI"`
* `"Autonomous AI"`
* `"Multi-Agent Systems"`
* `"AI Memory Systems"`

The paper's methodology reports 44 main papers and 39 supplementary survey/review articles, primarily from 2023–2025. 

### MY execution

 i will create a spreadsheet:

| Paper_ID | Title | Year | Database | URL | Included? | Reason         |
| -------- | ----- | ---: | -------- | --- | --------- | -------------- |
| P001     | ...   | 2025 | arXiv    | ... | Yes       | Agentic system |
| P002     | ...   | 2024 | Scholar  | ... | No        | Not agentic    |

### Important

inclusion criteria
For example:

**Include if:**

* Published 2023–2026
* Discusses Agentic AI/autonomous agents
* Describes an actual system/framework/experiment
* Contains measurable information useful for your dataset

**Exclude if:**

* Only mentions AI agents briefly
* No meaningful agent architecture
* Duplicate publication
* Opinion/editorial without usable information

---

# PHASE 3 — Build My Paper Database

## STEP 3 — Collect the papers

Create: a dtabase/file/folder

Then save every included paper with a consistent ID:


P001.pdf
P002.pdf
P003.pdf

---

# PHASE 4 — Create the Extraction Sheet

## STEP 4 — Build the actual dataset schema

This is where the project becomes a **data analytics project**.

Each row represents **one Agentic AI system/study**.

Starting with:

### Paper information

```text
Paper_ID
Title
Year
Authors
Database
Framework
```

### Architecture

```text
Number_of_Agents
LLM
Tool_Usage
Memory
Planning
Reflection
Multi_Agent
```

### Autonomy

```
Autonomy_Level
```

Use the paper's:

```
L1 = Assisted
L2 = Supervised
L3 = Conditional
L4 = Full Autonomous
```



### Cognitive complexity

```
Cognitive_Complexity
```

Use:

```
C1 = Single Task
C2 = Multi-Step
C3 = Multi-Agent
C4 = Self-Evolving
```



---

# PHASE 5 — Add Performance Data

## STEP 5 — Extract measurable performance

For every paper, look for:

```
Accuracy
Task_Success_Rate
Execution_Time
Resource_Usage
Cost
Token_Usage
Error_Rate
Human_Interventions
```

Example:

| Paper | Autonomy | Complexity | Accuracy | Time | Cost |
| ----- | -------: | ---------: | -------: | ---: | ---: |
| P001  |        2 |          2 |     87.2 |   42 | 0.14 |
| P002  |        3 |          3 |     91.4 |   38 | 0.21 |

Again:

### If the paper doesn't report it:

```text
NA
```


---

# PHASE 6 — Add Security Data

## STEP 6 — Build a security-risk framework

The original paper specifically considers security, privacy, and human-in-the-loop integration. 

Create variables such as:

```text
Security_Risk
Privacy_Risk
Prompt_Injection
Data_Leakage
Unauthorized_Action
Human_Oversight
```

For example:

### Security Risk

```
0 = Not discussed
1 = Low
2 = Moderate
3 = High
```

But here's the important part:

### Write the scoring rule before analyzing the dataset.

Otherwise you introduce researcher bias.

For example:

> A score of 3 is assigned only when the paper explicitly identifies a major vulnerability or significant security concern.

---

# PHASE 7 — Data Cleaning

## STEP 7 — Clean everything

Your pipeline:

```text
Raw Dataset
     │
     ▼
Remove duplicate rows
     │
     ▼
Check missing values
     │
     ▼
Check inconsistent labels
     │
     ▼
Encode categorical variables
     │
     ▼
Convert L1-L4 → 1-4
     │
     ▼
Convert C1-C4 → 1-4
     │
     ▼
Check outliers
     │
     ▼
FINAL DATASET
```

Planing to use Python/Pandas for this.

---

# PHASE 8 — Exploratory Data Analysis

## STEP 8 — Understanding the dataset BEFORE ML

This is crucial.

Start with:

### Analysis 1 — Publication trend

```
Year → Number of papers
```

Question:

> Is Agentic AI research increasing rapidly?

---

### Analysis 2 — Framework distribution

```
Framework → Number of studies
```

Question:

> Which frameworks are most studied?

The original paper discusses eight frameworks including AutoGPT, LangChain, AutoGen, MetaGPT, CrewAI, LangGraph, Semantic Kernel and Agent Hospital. 

---

### Analysis 3 — Autonomy distribution

```
L1
L2
L3
L4
```

Question:

> Are most current systems actually highly autonomous?

This could be a **very interesting result**.

---

### Analysis 4 — Complexity distribution

```
C1
C2
C3
C4
```

Question:

> Are researchers actually building C4 self-evolving systems, or are most systems still C2/C3?

---

# PHASE 9 — Test Relationships

## STEP 9 — Correlation analysis

Now test:

```
Autonomy
    │
    ├──── Cognitive Complexity
    │
    ├──── Accuracy
    │
    ├──── Execution Time
    │
    ├──── Security Risk
    │
    └──── Human Oversight
```

For ordinal variables, **Spearman correlation** is a strong starting choice.

For example:

### H1

> Higher autonomy is associated with higher cognitive complexity.

### H2

> Higher cognitive complexity is associated with improved performance.

### H3

> Higher autonomy is associated with increased security risk.

---

# PHASE 10 — Hypothesis Testing

## STEP 10 — Actually test the claims

### Example:

Compare performance across:

```
L1
L2
L3
L4
```

If the data is not normally distributed, you could use:

### Kruskal-Wallis test

Question:

> Are performance distributions significantly different across autonomy levels?

For categorical relationships:

### Chi-square test

Example:

> Is human oversight associated with autonomy level?

For suitable continuous data:

### ANOVA

Example:

> Does mean execution time differ across complexity groups?

The exact test should depend on your actual data and assumptions.

---

# PHASE 11 — Clustering

## STEP 11 — Let the data discover Agentic AI categories

This is where the recreation gets particularly interesting.

Using features like:

```text
Autonomy
Complexity
Number of Agents
Tool Usage
Memory
Planning
Accuracy
Security Risk
```

Then run:

### K-Means

Pipeline:

```text
Dataset
   ↓
Select features
   ↓
Scale features
   ↓
Determine K
   ↓
K-Means
   ↓
Cluster assignment
   ↓
Analyze each cluster
```

 **silhouette score** to help determine an appropriate number of clusters.

 might discover groups such as:

```text
Cluster 1
Low autonomy + simple tasks

Cluster 2
Multi-step + tool usage

Cluster 3
Multi-agent + high complexity

Cluster 4
High autonomy + high security risk
```

But again:

**those are possibilities, not predetermined results.**

---

# PHASE 12 — PCA

## STEP 12 — Visualize the high-dimensional data

If you have 10+ meaningful variables:

```text
10–15 variables
       ↓
      PCA
       ↓
 PC1 + PC2
       ↓
2D visualization
```

Then color/label points according to their cluster.

This helps  see whether the groups discovered by clustering are actually separated.

---

# PHASE 13 — Machine Learning

## STEP 13 — Predict performance

Only do this **if the dataset has enough usable performance observations**.

Create:

### Target

```text
High_Performance = 1
Low_Performance = 0
```

For example, define high performance based on a justified threshold such as the dataset median.

### Features

```text
Autonomy
Complexity
Number_of_Agents
Tool_Usage
Memory
Planning
Reflection
Human_Oversight
```

Then compare:

```text
Logistic Regression
Random Forest
XGBoost
```

Evaluate:

```text
Accuracy
Precision
Recall
F1
ROC-AUC
```

The key question becomes:

> **Can we predict high-performing Agentic AI systems from their architectural characteristics?**

That is a much stronger question than simply ranking frameworks.

---

# PHASE 14 — Framework Comparison

## STEP 14 — Compare the frameworks

Create a final table:

| Framework       | Autonomy | Complexity | Agents | Tools | Memory | Performance | Security |
| --------------- | -------: | ---------: | -----: | ----- | ------ | ----------: | -------: |
| AutoGPT         |          |            |        |       |        |             |          |
| LangChain       |          |            |        |       |        |             |          |
| AutoGen         |          |            |        |       |        |             |          |
| MetaGPT         |          |            |        |       |        |             |          |
| CrewAI          |          |            |        |       |        |             |          |
| LangGraph       |          |            |        |       |        |             |          |
| Semantic Kernel |          |            |        |       |        |             |          |
| Agent Hospital  |          |            |        |       |        |             |          |

The original paper explicitly identifies these frameworks for comparison. 

---

# PHASE 15 — Validate the Original Paper

## STEP 15 — THIS IS  OUR MOST IMPORTANT STEP

Now compare:

### What the original paper says

**VS**

### What  the new dataset says

For example:

```
             ORIGINAL PAPER
                   │
                   ▼
       "Higher autonomy and
        complexity matter"
                   │
                   ▼
              YOUR DATA
                   │
             ┌─────┴─────┐
             ▼           ▼
          SUPPORTS    DOES NOT
                     SUPPORT
```

the conclusion doesn't have to agree with the original paper.

In fact, if the  analysis contradicts one of its claims **and we can explain why**, that's potentially a more interesting research result.

---

# PHASE 16 — Write the Results

## STEP 16 — Convert analysis into research findings

**Data → Analysis → Statistical evidence → Interpretation**

---

# PHASE 17 — Discuss Limitations

## STEP 17 — Be brutally honest

 the  dataset will probably have problems.

Potential limitations:

* Different papers use different benchmarks.
* Performance metrics aren't standardized.
* Some papers don't report execution time.
* Security risk scoring involves researcher judgment.
* Publication bias exists.
* Recent papers may have limited validation.
* Some systems may appear in multiple studies.
* Framework versions change over time.

 Lets not hide these.

A good research paper basically says:

> “Here's what we found, here's why it matters, and here's where our own methodology could fall apart.”

Very academic. Very humbling :)

---

# PHASE 18 — Final Research Paper

 the final paper structure can be:

```
1. Introduction
       ↓
2. Original Paper Analysis
       ↓
3. Research Questions
       ↓
4. Literature Search Methodology
       ↓
5. Dataset Construction
       ↓
6. Data Preprocessing
       ↓
7. Exploratory Data Analysis
       ↓
8. Statistical Analysis
       ↓
9. Machine Learning Analysis
       ↓
10. Framework Comparison
       ↓
11. Results
       ↓
12. Comparison With Original Paper
       ↓
13. Discussion
       ↓
14. Limitations
       ↓
15. Conclusion
```

---

#  Execution Roadmap
Following this order:


┌───────────────────────────────┐
│       ORIGINAL SURVEY         │
│ Agentic AI Taxonomy & Claims  │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│       LITERATURE SEARCH       │
│ Scholar | arXiv | IEEE | SD   │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│       PAPER SCREENING         │
│ Inclusion / Exclusion Criteria│
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│       DATA EXTRACTION         │
│ Autonomy | Complexity | Tools │
│ Memory | Performance | Risk   │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│        DATASET CREATION       │
│       Agentic AI Dataset      │
└───────────────┬───────────────┘
                │
                ▼
       ┌────────┴────────┐
       │                 │
       ▼                 ▼
┌──────────────┐  ┌──────────────┐
│     EDA      │  │ PREPROCESSING│
│ Trends       │  │ Cleaning     │
│ Distributions│  │ Encoding     │
│ Relationships│  │ Scaling      │
└──────┬───────┘  └──────┬───────┘
       │                 │
       └────────┬────────┘
                ▼
┌───────────────────────────────┐
│     STATISTICAL ANALYSIS      │
│ Correlation | ANOVA | χ²      │
│ Kruskal-Wallis | Hypothesis   │
└───────────────┬───────────────┘
                │
                ▼
       ┌────────┴────────┐
       ▼                 ▼
┌──────────────┐  ┌──────────────┐
│  CLUSTERING  │  │     PCA      │
│   K-Means    │  │ Visualization│
└──────┬───────┘  └──────┬───────┘
       │                 │
       └────────┬────────┘
                ▼
┌───────────────────────────────┐
│       MACHINE LEARNING        │
│ Logistic | RF | XGBoost       │
│ Performance Prediction        │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│     FRAMEWORK COMPARISON      │
│ AutoGPT | AutoGen | CrewAI    │
│ LangChain | LangGraph | etc.  │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│     VALIDATE ORIGINAL PAPER   │
│                               │
│  Paper Claims  ←→  Data       │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│       FINAL FINDINGS          │
│ Support / Contradict / Extend │
│ Original Research             │
└───────────────────────────────┘
```

## And the research philosophy is simply:

**Original paper:**

> *“This is what the literature tells us about Agentic AI.”*

** this  recreation:**

> *“Okay. Let's turn those claims into variables, collect the data, run the statistics, train the models, and see whether the data agrees.”*

That is the part that makes  the work a **recreation + quantitative extension**, rather than just another summary of the same survey.
