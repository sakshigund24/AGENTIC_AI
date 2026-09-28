# Day 01 — Agentic AI Overview

## 1. What is Agentic AI?

Agentic AI refers to AI systems that can work toward a given goal by deciding what actions to take, using available tools, observing the results, and continuing the process until the goal is completed.

A basic agent can be viewed as:

```text
Goal
 ↓
Observe
 ↓
Decide
 ↓
Act
 ↓
Observe
 ↓
Decide
 ↓
...
 ↓
Finish
```

The important idea is that an agent can operate through a loop instead of simply producing one response.

---

## 2. LLM

LLM stands for **Large Language Model**.

An LLM is a model that can understand and generate natural language.

Examples of tasks performed by an LLM:

* Answering questions
* Summarizing text
* Generating content
* Extracting information
* Explaining concepts
* Generating code

A simple LLM interaction is:

```text
User Prompt
     ↓
    LLM
     ↓
Response
```

### Key idea

An LLM primarily generates a response based on the input and context provided to it.

---

## 3. Workflow

A workflow is a predefined sequence of steps used to complete a task.

For example:

```text
Input
 ↓
Extract Information
 ↓
Process Information
 ↓
Generate Result
 ↓
Output
```

The sequence is defined by the developer.

### Example

A resume-processing workflow could be:

```text
Resume
 ↓
Extract Text
 ↓
Extract Skills
 ↓
Compare With Job Description
 ↓
Generate Report
```

The system follows the defined sequence.

### Key idea

> A workflow follows predefined steps.

---

## 4. Agent

An agent is an AI system that can work toward a goal by deciding what actions to take and interacting with tools or an environment.

A simplified agent looks like:

```text
              Goal
                ↓
             Agent
              / LLM
                ↓
          Decide Action
                ↓
              Tool
                ↓
             Result
                ↓
          Observation
                ↓
             Agent
                ↓
       Continue / Finish
```

Unlike a fixed workflow, an agent can determine the next action based on its current information and the result of previous actions.

### Key idea

> An agent is goal-oriented and can dynamically choose actions.

---

# 5. LLM vs Workflow vs Agent

| Concept  | Description                                     | Flow                             |
| -------- | ----------------------------------------------- | -------------------------------- |
| LLM      | Generates or understands information            | Prompt → Response                |
| Workflow | Executes predefined steps                       | Step 1 → Step 2 → Step 3         |
| Agent    | Works toward a goal using decisions and actions | Observe → Decide → Act → Observe |

### Simple way to remember

```text
LLM      → Answer this.

Workflow → Follow these steps.

Agent    → Achieve this goal and decide what to do next.
```

---

# 6. Components of an Agent

A basic agent architecture contains several important components.

## 6.1 Goal

The goal describes what the agent needs to accomplish.

Example:

```text
Find information about a particular topic
and prepare a summary.
```

---

## 6.2 State

State represents the information currently available to the agent.

It can include:

* User request
* Previous actions
* Tool results
* Conversation information
* Intermediate results

Example:

```text
Goal: Research a topic

State:
- Search performed
- 3 sources found
- Information partially collected
- Summary not yet generated
```

---

## 6.3 Observation

An observation is information received by the agent after interacting with its environment or a tool.

Example:

```text
Agent → Search Tool

Search Tool → Results

Agent receives the results as an observation.
```

---

## 6.4 Action

An action is something the agent decides to perform.

Examples:

```text
Search the web
Call an API
Query a database
Use a calculator
Retrieve a document
```

---

## 6.5 Tools

Tools allow an agent to interact with external systems or perform specific operations.

Examples include:

* APIs
* Databases
* Web search
* Calculators
* Python programs
* File systems

A tool generally receives arguments from the agent and returns a result.

```text
Agent
 ↓
Tool + Arguments
 ↓
Tool Execution
 ↓
Result
 ↓
Agent
```

---

## 6.6 LLM

The LLM acts as the reasoning/decision component of the agent.

It can help determine:

* What the user wants
* What information is available
* What action should be taken
* Which tool may be useful
* Whether the goal has been completed

---

## 6.7 Termination

An agent needs a condition that determines when it should stop.

For example:

```text
Goal completed
     ↓
   STOP
```

Without an appropriate termination condition, an agent could continue performing unnecessary actions.

---

# 7. The Agent Loop

The agent loop is one of the fundamental concepts in Agentic AI.

A simplified loop is:

```text
        ┌──────────────┐
        │     Goal     │
        └──────┬───────┘
               ↓
        ┌──────────────┐
        │   Observe    │
        └──────┬───────┘
               ↓
        ┌──────────────┐
        │    Decide    │
        └──────┬───────┘
               ↓
        ┌──────────────┐
        │     Act      │
        └──────┬───────┘
               ↓
        ┌──────────────┐
        │   Observe    │
        └──────┬───────┘
               ↓
         Goal complete?
           /       \
         No         Yes
         ↓           ↓
      Decide        STOP
```

The basic pattern is:

```text
Observe → Decide → Act → Observe → Decide → Act → Finish
```

---

# 8. Example of an Agent Loop

Consider an agent whose goal is:

```text
Research a topic and create a summary.
```

### Step 1 — Goal

```text
Research the topic.
```

### Step 2 — Observe

The agent determines what information it currently has.

```text
No external information collected yet.
```

### Step 3 — Decide

The agent decides that it needs external information.

```text
Action: Search for information
```

### Step 4 — Act

The agent uses a search tool.

```text
Search Tool
```

### Step 5 — Observe

The tool returns search results.

```text
Search results received.
```

### Step 6 — Decide

The agent determines whether it has enough information.

If not, it can perform another action.

### Step 7 — Continue

```text
Observe → Decide → Act
```

The process continues until the agent determines that the goal has been completed.

### Step 8 — Finish

```text
Generate final summary
        ↓
       STOP
```

---

# 9. Agent vs Traditional Chatbot

A basic chatbot interaction can look like:

```text
User
 ↓
LLM
 ↓
Response
```

An agent can involve multiple interactions with tools:

```text
User Goal
    ↓
  Agent
    ↓
  Decide
    ↓
  Tool
    ↓
 Result
    ↓
  Observe
    ↓
  Decide
    ↓
  Tool
    ↓
 Result
    ↓
 Final Response
```

Therefore, an agent can perform multiple actions as part of completing a goal.

---

# 10. Basic Agent Architecture

The architecture created for Day 1 represents:

```text
                    USER GOAL
                        │
                        ↓
                ┌───────────────┐
                │     AGENT     │
                │      LLM      │
                └───────┬───────┘
                        │
                  Decide Action
                        │
                        ↓
                ┌───────────────┐
                │     TOOLS     │
                │ API / DB / Web│
                └───────┬───────┘
                        │
                      Result
                        │
                        ↓
                ┌───────────────┐
                │  OBSERVATION  │
                └───────┬───────┘
                        │
                        ↓
                     AGENT
                    /     \
                   /       \
             Continue     Finish
                │           │
                ↓           ↓
               LOOP        STOP
```

The architecture diagram is stored separately as:

```text
Day-01/architecture.png
```

---

# 11. Key Concepts to Remember

### LLM

A model that understands and generates language.

### Workflow

A predefined sequence of steps.

### Agent

A goal-oriented system that can decide actions and interact with tools.

### State

The information currently available to the agent.

### Observation

Information received after an action or interaction.

### Action

An operation selected by the agent.

### Tool

An external capability that the agent can use.

### Termination

The condition that tells the agent to stop.

### Agent Loop

```text
Observe → Decide → Act → Observe → ...
```

---

# 12. Interview Questions

### Q1. What is Agentic AI?

Agentic AI refers to AI systems that work toward goals by making decisions, taking actions, using tools, observing results, and continuing until the task is completed.

### Q2. What is the difference between an LLM and an agent?

An LLM primarily generates or understands information, while an agent uses an LLM as part of a larger system that can decide actions, use tools, observe results, and work toward a goal.

### Q3. What is the difference between a workflow and an agent?

A workflow follows a predefined sequence of steps. An agent can dynamically determine its next action based on the current state and observations.

### Q4. What is an agent loop?

An agent loop is the repeated process of observing the current situation, deciding an action, performing the action, observing the result, and continuing until a termination condition is reached.

### Q5. What are tools in an AI agent?

Tools are external capabilities that an agent can use to perform actions, such as APIs, databases, web search, calculators, or programs.

### Q6. Why does an agent need a termination condition?

A termination condition determines when the agent should stop because the goal has been completed or another stopping condition has been reached.

---

# 13. Day 1 Practical Work

### Completed

* Studied LLMs
* Studied workflows
* Studied AI agents
* Compared LLMs, workflows, and agents
* Studied agent components
* Studied the agent loop
* Created a basic agent architecture diagram

### Files

```text
Day-01/
├── notes.md
└── architecture.png
```

---

# 14. What I Should Be Able to Explain After Day 1

After completing Day 1, I should be able to explain:

1. What an LLM is.
2. What a workflow is.
3. What an AI agent is.
4. How an agent differs from a workflow.
5. The components of an agent.
6. What state means in an agent.
7. What observations and actions are.
8. What tools are.
9. How the agent loop works.
10. Why an agent needs a termination condition.

