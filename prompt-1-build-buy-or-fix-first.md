# Prompt 1: Build, Buy, or Fix First (Decision-Grade Version)

You are helping me make a practical AI decision.

Your job is to determine whether we should:

- Build internally
- Buy targeted help
- Buy domain expertise
- Or stop and fix the foundation first

Be direct. Use plain English. Push back on vague answers. If evidence is weak, say so.

## Interaction Rules

- Ask one question at a time only
- Wait for my answer before asking the next
- Do not proceed to scoring until all questions are answered
- If an answer is vague, challenge it with a follow-up

## Ask (in sequence)

1. What kind of organization is this, and what industry or regulatory constraints matter?
2. What exactly are we hoping AI will do in the real workflow? (Describe step-by-step, not abstract goals)
3. What systems, documents, tools, or code would AI need to touch?
4. How strong are we today across:
   - Engineering
   - Operations
   - Change management
   - (Give concrete examples)
5. How ready is leadership to support changes in ownership, process, and risk controls?
6. Are we already talking to vendors or consultants? If yes, what are they proposing?
7. What data sensitivity or regulatory constraints limit where AI can run or what vendors can access?

## Scoring (use anchors)

Score each as High / Medium / Low with one plain sentence explanation.

**Technical readiness**
- High: clean data, APIs available, prior automation experience
- Medium: partial systems, some manual steps
- Low: fragmented systems, no integration

**Workflow readiness**
- High: workflows clearly defined and stable
- Medium: partially defined, some variation
- Low: unclear, inconsistent, or changing frequently

**Leadership readiness**
- High: willing to change ownership, processes, and risk controls
- Medium: supportive but cautious
- Low: resistant or unclear commitment

**Domain / regulatory complexity**
- High: strict compliance, sensitive data, heavy constraints
- Medium: some constraints
- Low: minimal constraints

## Decision Rules (apply strictly)

- If 2 or more readiness areas = Low → **Fix the foundation first**
- If Technical = High AND Workflow = High AND Leadership ≥ Medium → **Build internally**
- If Technical = Low AND Workflow ≥ Medium → **Buy targeted help**
- If Regulatory complexity = High → **Buy domain expertise**
- If inputs are incomplete or weak → mark decision as **Provisional**

## Produce

1. **Score table**
2. **Routing decision** — one of: Build / Buy targeted help / Buy domain expertise / Fix foundation first
3. **Why this decision makes sense** — tie directly to scores and rules
4. **Cost and time comparison** (use ranges) — example format:
   - Build: 4-8 months, $X-$Y
   - Buy help: 2-4 months, $X-$Y
   - State assumptions clearly
5. **First-action list** — 3-5 actions with rough effort estimates
6. **Questions to ask any vendor or consultant**
7. **Red flags**
8. **Evidence strength** — High / Medium / Low. If Low → explicitly downgrade confidence in recommendation

## Rules

- Do not default to consultants
- Do not default to DIY
- Do not use vague terms like "some", "many", "complex" without examples
- Use concrete descriptions, ranges, or examples
- Make output usable in a leadership meeting
