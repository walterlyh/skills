---
name: socratic-prompting
description: Use this skill when users need deep thinking, critical analysis, structured problem-solving, or content creation. Forces AI into deep thinking mode by building underlying logic before generating answers through Socratic 5-step questioning.
---

# Socratic Prompting

## Overview

This skill implements the Socratic Method through a structured 5-step questioning framework. It forces the AI to enter "deep thinking mode" by constructing underlying logic before generating final answers. Best suited for complex decisions, problem-solving, content creation, and critical analysis.

**When to use:**
- Complex decision-making (career changes, investments, strategic choices)
- Content creation requiring depth (writing, presentations, proposals)
- Problem-solving and root cause analysis
- Concept clarification and knowledge synthesis
- Any situation requiring multi-dimensional thinking

**How it works:**
1. Detect user input (with/without topic argument)
2. Execute 5-step Socratic questioning cycle
3. Display thinking process + synthesized insights at each step
4. Output final action plan in structured format

## Workflow

### Invocation Detection

Check for `$ARGUMENTS` parameter:
- **If provided**: Start 5-step process immediately with the given topic
- **If empty**: Ask "What topic would you like to analyze deeply?"

### The 5-Step Socratic Cycle

Execute each step with **dual output mode** (Process + Synthesis):

#### Step 1: Essence & Definition (本体与定义)

**Thinking Process:**
Analyze: What is the fundamental nature of this topic? How would experts define it? What are the core components?

**Key Questions:**
- What is [topic] at its core?
- How would you define it in the simplest terms?
- What are the essential attributes that make it what it is?
- What is it NOT? (Boundary definition)

**Output:** Synthesized definition and core essence

#### Step 2: Mechanism & Causality (机制与因果)

**Thinking Process:**
Trace: What are the driving forces? How do inputs transform into outputs? What are the cause-effect chains?

**Key Questions:**
- What are the underlying drivers that create this situation?
- How does [Factor A] lead to [Result B]? Trace the mechanism.
- What feedback loops exist?
- What are the second-order effects?

**Reference:** Load [references/thinking_frameworks.md] for systems thinking and causal analysis frameworks

**Output:** Causal mechanism map and key leverage points

#### Step 3: Boundaries & Constraints (边界与约束)

**Thinking Process:**
Pressure-test: Where does this logic break down? What are the failure modes? What constraints are often overlooked?

**Key Questions:**
- Where is this most likely to fail?
- What assumptions am I making that might be wrong?
- What are the hidden constraints (time, resources, capabilities)?
- What would make this entire approach invalid?

**Reference:** Load [references/thinking_frameworks.md] for inversion thinking and failure mode analysis

**Output:** Risk map and constraint inventory

#### Step 4: Frameworks & Perspectives (框架与视角)

**Thinking Process:**
Synthesize: Apply multiple mental models. How would different experts approach this? What cross-disciplinary insights emerge?

**Key Questions:**
- How would Munger analyze this using multiple mental models?
- What would [Domain Expert] focus on?
- Apply frameworks: First Principles, Second-Order Thinking, Systems Thinking
- What patterns from other domains apply here?

**Reference:** Load [references/thinking_frameworks.md] for available frameworks

**Output:** Multi-perspective synthesis and cross-domain insights

#### Step 5: Synthesis & Application (合成与应用)

**Thinking Process:**
Integrate: Combine all previous insights into actionable intelligence. What concrete steps emerge?

**Key Questions:**
- Given all the above analysis, what is the highest-leverage action?
- What is the decision criteria?
- What is the implementation roadmap?
- How do we measure success?

**Reference:** Load [references/output_templates.md] for appropriate output format

**Output:** Final structured action plan

## Output Format

Use **structured Markdown** with clear visual hierarchy:

```markdown
# 🎯 Deep Analysis: [Topic]

## Step 1/5: Essence & Definition 🔍

### 💭 Thinking Process
[Show analysis process, key questions considered, preliminary thoughts]

### ✨ Core Insight
**Definition:** [Clear, concise definition]
**Essence:** [Fundamental nature in 1-2 sentences]
**Key Components:**
- Component A: [description]
- Component B: [description]

---

## Step 2/5: Mechanism & Causality ⚙️

### 💭 Thinking Process
[Analysis of causal chains, mechanisms traced]

### ✨ Mechanism Map
**Primary Drivers:**
1. [Driver] → [Intermediate] → [Outcome]
2. [Driver] → [Intermediate] → [Outcome]

**Key Leverage Points:**
- [Point 1]: [Why it matters]
- [Point 2]: [Why it matters]

---

[Continue through Step 3, 4, 5...]

---

# 📋 Synthesized Action Plan

## Executive Summary
[2-3 sentences capturing the core recommendation]

## Decision Framework
| Criteria | Weight | Option A | Option B | Option C |
|----------|--------|----------|----------|----------|
| [Criteria 1] | High | Score | Score | Score |
| [Criteria 2] | Medium | Score | Score | Score |

## Recommended Actions

### Immediate (This Week)
- [ ] Action 1
- [ ] Action 2

### Short-term (This Month)
- [ ] Action 3
- [ ] Action 4

### Long-term (3+ Months)
- [ ] Action 5

## Success Metrics
- Metric 1: [Target]
- Metric 2: [Target]

## Risk Mitigation
- Risk: [Description] → Mitigation: [Strategy]
```

## Thinking Frameworks Library

When additional frameworks are needed during analysis, reference:
- [references/thinking_frameworks.md] - 11 mental models and frameworks
- [references/output_templates.md] - Structured output formats

## Example Invocation

**With topic:**
```
/socratic-prompting Should I quit my job to start a business?
```
→ Immediately starts 5-step analysis on career decision

**Without topic:**
```
/socratic-prompting
```
→ Response: "What topic would you like to analyze deeply?"

## Guidelines

1. **Always show thinking process** - Transparency builds trust and helps users follow the logic
2. **Push deeper** - Don't accept surface-level answers; ask "Why?" and "What if?"
3. **Use frameworks actively** - Reference thinking frameworks at relevant steps
4. **Be recursive** - If an insight reveals new questions, do a micro-loop on that sub-topic
5. **Stay practical** - Every analysis must lead to actionable conclusions
6. **Challenge assumptions** - Actively seek and test hidden assumptions

## Tips for Maximum Effectiveness

- Encourage users to provide context - the more specific, the better the analysis
- For complex topics, suggest breaking into sub-analyses
- Use analogies and metaphors to make abstract concepts concrete
- When stuck, apply inversion: "How would we guarantee failure?"
- Cross-reference multiple frameworks for richer insights
