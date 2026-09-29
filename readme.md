# Jev — System 1 Decision Model

> This README is derived from the ideas, definitions, examples, questions, and notes contained in `workflow.excalidraw` in this repository.
>
> The Jev definitions below are kept from the original project notes rather than replaced with external definitions.

---

## 1. What is Jev?

The project notes describe Jev as:

> "it is a Ai models"

> "but it's not a LLM"

> "jev does'nt generate text"

> "Jev is the ai models build to make fast and structured decision that software can used directly"

> "it's a decisions models and classefier."

The central idea recorded in the workflow is that Jev is focused on **decision-making and classification** rather than text generation.

---

## 2. Why Jev?

The workflow asks:

> "LLM also do the decision and classefier then why we choose Jev??"

The answers recorded in the notes are:

* Speed
* Cost

The notes state:

> "Jev - (i) speed"

> "(ii) cost -> token cost is very low"

Another distinction in the notes is:

> "In LLM you can generally ask one question in one query"

> "but in Jev you can ask many question in one query"

---

## 3. Core Decision Model

The workflow states:

> "when Jev select any options then they can also tell ---> confidence score of every options"

The notes define the following confidence flow:

> "confidence >= 0.90 --> option will 90% correct"

> "confidence 0.60 - 0.90 --> then you can asked some follow up question"

> "confidence below 0.60 --> take a help of humman review"

### Decision Flow

```text
Input
  |
  v
Jev Decision / Classification
  |
  +--> Confidence >= 0.90
  |       |
  |       +--> Use the selected option
  |
  +--> Confidence 0.60 - 0.90
  |       |
  |       +--> Ask follow-up question
  |
  +--> Confidence < 0.60
          |
          +--> Human review
```

The thresholds above are taken directly from the project notes.

---

## 4. Confidence and Reliability

The workflow states:

> "LLM can fake there confidence but in jev you can always they can give accurate"

It also states:

> "Jev can't fake and can't hallucinate the answer"

These statements represent the intended design goal recorded in the project notes: Jev should provide structured decisions with explicit confidence information so software can use the result directly.

---

## 5. Five Good Features

The workflow contains a section titled:

> "5 good Features...."

The five features listed are:

1. **Low cost**
2. **High speed**
3. **Asked multiple question in single time**
4. **All options have there own confidence score**
5. **They not fake and hallucinate the answer**

---

## 6. System 1 vs System 2

The project notes describe two modes:

> "brain are working on 2 modes"

### System 1

> "(a) fast modes -> system 1 (quick decision/thinking)"

### System 2

> "(b) slow modes -> system 2 (slow thinking plane based thinking)"

The notes then state:

> "software need system1 thinking, but we keep building system2 thinking."

The workflow also states:

> "LLM are system2 models because the are very good in reasoning"

And the project direction is written as:

> "Jev founder said in many place we don't need system2 thinking we need system1 thinking that's why Jev are come"

### Project Concept

```text
System 1
Fast Decision / Thinking
        |
        v
       Jev


System 2
Slow Thinking / Reasoning
```

---

## 7. Jev as a Software Primitive

The workflow asks:

> "Impact ??"

and records:

> "Ai move from a feature to a Primitive"

The example in the notes is:

```javascript
if(jev("is this customer angry") > 0.9 ):
```

The workflow further says:

> "In feature may be this types of code will be writen they act like a if else condition"

This represents the intended direction of making AI decision capability usable directly inside software logic.

### Concept

```text
Application
     |
     v
   Jev
     |
     +--> Decision
     |
     +--> Classification
     |
     +--> Confidence
     |
     v
Application Logic
```

---

## 8. AI Agents

The workflow asks:

> "where we can see the impact??"

The recorded answer is:

> "-> AI agents"

The notes state:

> "In Ai agent we need good decision making"

> "jev can actually good in decision making"

> "which tools? which models? which steps safe?"

This gives Jev a decision-making role inside AI-agent workflows.

### Agent Decision Flow

```text
AI Agent
    |
    v
   Jev
    |
    +--> Which Tool?
    |
    +--> Which Model?
    |
    +--> Which Step?
    |
    +--> Is the Step Safe?
    |
    v
Selected Path
```

---

## 9. Business Operations

The workflow identifies:

> "-> Buisness Operations"

Examples recorded in the notes:

> "support triage, Claims, Invoice, lead scoring"

### Business Use Cases

* Support triage
* Claims
* Invoice
* Lead scoring

---

## 10. Trust and Safety

The workflow identifies:

> "-> trust and safty"

Examples recorded in the notes:

> "Moderation, fraud, Spam, jailbreak detections"

### Trust and Safety Use Cases

* Moderation
* Fraud
* Spam
* Jailbreak detection

---

## 11. Unstructured Data → Structured Data

The workflow explicitly records:

> "-> unstructured data --> structured data"

### Conceptual Flow

```text
Unstructured Data
        |
        v
       Jev
        |
        v
Structured Data
        |
        v
Application
```

---

## 12. Real-Time Systems

The notes also identify:

> "-> Real time system --> like game"

This connects the project's speed requirement with real-time decision workloads.

---

# Product Requirements Document

## 13. Product Vision

The workflow describes a direction for an AI model focused on **fast and structured decision-making** instead of text generation.

The model should be usable directly by software and should expose decision information such as confidence so application logic can determine what to do next.

---

## 14. Problem Statement

The workflow states:

> "software need system1 thinking, but we keep building system2 thinking."

The proposed direction recorded in the notes is therefore a system focused on fast decisions that can be directly integrated into software.

---

## 15. Product Goals

### Goal 1 — Fast Decisions

The notes identify:

> "high speed"

### Goal 2 — Low Cost

The notes identify:

> "low cost"

and:

> "token cost is very low"

### Goal 3 — Multiple Decisions in One Query

The notes identify:

> "asked multiple question in single time"

### Goal 4 — Confidence for Options

The notes identify:

> "all options have there own confidence score"

### Goal 5 — Software-Consumable Decisions

The Jev definition states:

> "structured decision that software can used directly"

---

## 16. Functional Requirements

### FR-01 — Decision Input

The system must accept an input representing a decision or classification requirement.

### FR-02 — Structured Decision

The system should return a decision in a form that software can use directly.

### FR-03 — Multiple Questions

The system should support multiple questions in a single query, according to the project notes.

### FR-04 — Options

The system should support multiple possible options for a decision.

### FR-05 — Confidence Score

Each option should have its own confidence score.

### FR-06 — Confidence-Based Workflow

The project notes define:

| Confidence    | Intended Action             |
| ------------- | --------------------------- |
| `>= 0.90`     | Option will be 90% correct  |
| `0.60 - 0.90` | Ask some follow-up question |
| `< 0.60`      | Take help of human review   |

### FR-07 — Software Integration

The workflow provides the example:

```javascript
if(jev("is this customer angry") > 0.9 ):
```

---

## 17. Non-Goals

The workflow explicitly distinguishes Jev from an LLM:

> "but it's not a LLM"

and:

> "jev does'nt generate text"

Therefore, **text generation is not the primary purpose** described by the current project notes.

---

## 18. Primary Use Cases

### AI Agents

* Tool selection
* Model selection
* Step selection
* Safety decisions

The original workflow describes these as:

> "which tools? which models? which steps safe?"

### Business Operations

* Support triage
* Claims
* Invoice
* Lead scoring

### Trust and Safety

* Moderation
* Fraud
* Spam
* Jailbreak detection

### Data Processing

* Unstructured data → structured data

### Real-Time Systems

* Real-time decision systems
* Game-like real-time applications

---

## 19. Example Decision

The workflow provides:

```javascript
if(jev("is this customer angry") > 0.9 ):
```

The intended pattern is:

```text
Customer Input
      |
      v
Jev Decision
      |
      v
Option + Confidence
      |
      +---- >= 0.90 ----> Application Action
      |
      +---- 0.60-0.90 --> Follow-up Question
      |
      +---- < 0.60 ----> Human Review
```

---

## 20. High-Level Product Flow

```text
                 +----------------------+
                 |      Application     |
                 +----------+-----------+
                            |
                            v
                 +----------------------+
                 |         Jev          |
                 |                      |
                 | Fast Decision Model  |
                 | Classification       |
                 | Structured Output    |
                 +----------+-----------+
                            |
                +-----------+-----------+
                |           |           |
                v           v           v
             Option A    Option B    Option C
                |           |           |
                +-----------+-----------+
                            |
                            v
                    Confidence Scores
                            |
              +-------------+-------------+
              |             |             |
              v             v             v
            >=0.90       0.60-0.90      <0.60
              |             |             |
              v             v             v
          Use Result    Follow-up       Human
                         Question        Review
```

---

## 21. Product Positioning From the Workflow

| Area               | Direction Recorded in Project       |
| ------------------ | ----------------------------------- |
| Model type         | AI model                            |
| LLM                | Not an LLM                          |
| Primary output     | Structured decision                 |
| Text generation    | Not the purpose                     |
| Main capability    | Decision and classification         |
| Thinking direction | System 1                            |
| Speed              | High                                |
| Cost               | Low                                 |
| Query behavior     | Multiple questions in one query     |
| Confidence         | Confidence score for options        |
| Software usage     | Directly usable by software         |
| Agent usage        | Decision-making                     |
| Business usage     | Business operations                 |
| Safety usage       | Trust and safety                    |
| Data usage         | Unstructured data → structured data |
| Real-time usage    | Real-time systems                   |

---

## 22. Core Design Principles

The workflow points toward these principles:

### 1. Decision First

Jev is described as a decision and classification model.

### 2. Fast Execution

Speed is repeatedly identified as a core reason for Jev.

### 3. Low Cost

The notes identify low token cost as a reason to choose Jev.

### 4. Structured Output

The result should be usable directly by software.

### 5. Confidence-Aware Decisions

Options should carry confidence information.

### 6. Human Review When Confidence Is Low

The notes explicitly include human review below the defined threshold.

### 7. AI as a Primitive

The workflow states:

> "Ai move from a feature to a Primitive"

---

## 23. Open Questions in the Project

The workflow itself contains questions that can become future product and engineering work.

### Why Jev if LLMs can also classify?

The notes ask:

> "LLM also do the decision and classefier then why we choose Jev??"

The current answers recorded in the notes are:

* Speed
* Cost
* Multiple questions in one query

### How Should Confidence Be Guaranteed?

The notes state:

> "LLM can fake there confidence but in jev you can always they can give accurate"

This should become an engineering and evaluation requirement during implementation.

### How Should Jev Integrate With AI Agents?

The notes ask:

> "which tools? which models? which steps safe?"

This can become a core agent-integration requirement.

### How Does Jev Become a Software Primitive?

The notes provide:

```javascript
if(jev("is this customer angry") > 0.9 ):
```

The implementation will eventually need to define the actual API, SDK, runtime, model interface, and response schema.

---

## 24. Future Implementation Areas

The current repository is a concept and product-definition repository.

The workflow suggests these future implementation areas:

1. Jev model
2. Classification engine
3. Decision API
4. Confidence scoring
5. Multiple-question query handling
6. Structured response schema
7. Application integration
8. AI-agent integration
9. Business-operation integrations
10. Trust-and-safety integrations
11. Human-review workflow
12. Real-time decision support
13. Evaluation and accuracy testing
14. Performance and latency testing
15. Cost measurement

These are implementation areas derived from the requirements and use cases recorded in the workflow. They are **not currently implemented** in this repository.

---

## 25. Current Repository Status

### Status

**Concept / Product Definition**

Current repository artifact:

```text
Jev-systemOne-model/
└── workflow.excalidraw
```

The workflow is the current source of the Jev product-thinking notes, definitions, feature ideas, examples, use cases, and decision-flow concepts.

### Next Stage

```text
Product Requirements
        |
        v
   Model Design
        |
        v
 API / Interface
        |
        v
    Prototype
        |
        v
    Evaluation
        |
        v
Application Integration
        |
        v
 Agent Integration
```

---

## 26. Source of Truth

For the current Jev project definition:

**Source:** `workflow.excalidraw`

This README organizes the content from that workflow into a structured product and engineering document.

**No external technical definition is used as the source for the Jev definition in this README.**
