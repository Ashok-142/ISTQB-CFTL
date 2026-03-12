# Chapter 4 — Test Analysis and Design
#ISTQB #CTFL #Chapter4

> ⏱ 390 minutes (largest chapter!) | [[00-INDEX|← Back to Index]]

---

## Keywords (must know K1)
`acceptance criteria` `acceptance test-driven development` `black-box test technique` `boundary value analysis` `branch coverage` `checklist-based testing` `collaboration-based test approach` `coverage` `coverage item` `decision table testing` `equivalence partitioning` `error guessing` `experience-based test technique` `exploratory testing` `state transition testing` `statement coverage` `test technique` `white-box test technique`

---

## 4.1 Test Techniques Overview (K2 — distinguish)

Test techniques help with:
- **Test analysis** — what to test
- **Test design** — how to test
- Developing a small but sufficient set of test cases systematically

| Category | Also known as | Based on |
|----------|--------------|---------|
| **Black-box** | Specification-based | Specified behaviour — no knowledge of internals |
| **White-box** | Structure-based | Internal structure — code, architecture, data flows |
| **Experience-based** | — | Tester's knowledge and experience |

> 💡 Experience-based techniques complement black-box and white-box — they can find defects missed by both.

---

## 4.2 Black-Box Test Techniques

### 4.2.1 Equivalence Partitioning (EP) — K3 Apply

**Concept:** Divide data into **partitions** where all elements are expected to be processed the **same way**. One test per partition is sufficient.

| Partition type | Description |
|---------------|-------------|
| **Valid partition** | Values that should be processed / accepted |
| **Invalid partition** | Values that should be rejected/ignored |

**Coverage:**
- Coverage items = the **equivalence partitions**
- 100% EP coverage = all partitions (including invalid) exercised at least once
- Coverage % = partitions exercised / total identified partitions × 100

**Multiple inputs:**
- Use **Each Choice coverage** = at least one value from each partition for each input parameter

> 🔑 Partitions must be: **non-overlapping, non-empty**, and cover all possible values.

---

### 4.2.2 Boundary Value Analysis (BVA) — K3 Apply

**Concept:** Exercise the **boundaries of equivalence partitions**. Only applicable to **ordered** partitions.

Developers make more errors at boundary values → most defects found here.

**Typical defects:** Boundaries placed above or below intended positions, or omitted.

| Version | Coverage items per boundary | To achieve 100% |
|---------|---------------------------|-----------------|
| **2-value BVA** | 2: the boundary + its nearest neighbour in adjacent partition | All boundary values exercised |
| **3-value BVA** | 3: the boundary + both neighbours | All boundary values AND their neighbours |

> 🔑 3-value BVA is **more rigorous** — can detect defects 2-value misses.  
> Example: `if (x ≤ 10)` incorrectly coded as `if (x = 10)` — only caught by 3-value BVA (x=9).

---

### 4.2.3 Decision Table Testing — K3 Apply

**When to use:** Testing combinations of conditions that produce different outcomes (business rules, complex logic).

**Structure:**
- **Rows** = conditions + actions
- **Columns** = decision rules (unique combination of conditions)
- **Limited-entry:** Boolean values (T/F)
- **Extended-entry:** Multiple values per condition/action

**Notation:**
- `T` = condition satisfied
- `F` = condition not satisfied
- `–` = irrelevant (don't care)
- `N/A` = infeasible
- `X` = action should occur
- blank = action should not occur

**Coverage:**
- Coverage items = **feasible columns**
- 100% = all feasible condition combinations exercised

**Strength:** Systematic — ensures all combinations identified, including gaps or contradictions in requirements.

> ⚠️ Many conditions → exponential rule growth → use minimised table or risk-based approach.

---

### 4.2.4 State Transition Testing — K3 Apply

**Concept:** Model system as states + transitions triggered by events.

| Model | Description |
|-------|-------------|
| **State diagram** | Visual — shows states and valid transitions |
| **State table** | Grid — rows=states, columns=events; explicitly shows **invalid transitions** (empty cells) |

**Transition syntax:** `event [guard condition] / action`

**Coverage criteria (weakest to strongest):**

| Coverage | Items | Strength |
|----------|-------|---------|
| **All states coverage** | States | Weakest |
| **Valid transitions coverage** (0-switch) | Valid transitions | Most widely used |
| **All transitions coverage** | Valid + invalid transitions | Strongest — minimum for safety-critical |

> 🔑 Full **valid transitions** coverage guarantees **all states** coverage.  
> Full **all transitions** coverage guarantees both of the above.  
> For **safety-critical** systems, all transitions coverage should be a minimum.

---

## 4.3 White-Box Test Techniques

### 4.3.1 Statement Testing and Coverage (K2 — explain)

**Coverage items:** Executable statements  
**Goal:** Design tests that exercise statements until acceptable coverage achieved.

`Coverage % = statements exercised / total executable statements × 100`

**100% statement coverage ensures:**
- All executable statements exercised at least once
- Statements with defects will be executed

**Limitations of 100% statement coverage:**
- Does NOT detect data-dependent defects (e.g., division by zero only if denominator = 0)
- Does NOT ensure all decision logic tested (doesn't cover all branches)

---

### 4.3.2 Branch Testing and Coverage (K2 — explain)

**A branch** = a transfer of control between two nodes in the control flow graph
- **Unconditional** branch = straight-line code
- **Conditional** branch = `if/then`, `switch/case`, loop decisions

`Coverage % = branches exercised / total branches × 100`

**100% branch coverage:**
- All unconditional and conditional branches exercised

> 🔑 **Branch coverage SUBSUMES statement coverage**  
> 100% branch coverage → always achieves 100% statement coverage  
> BUT 100% statement coverage → does NOT guarantee 100% branch coverage

---

### 4.3.3 Value of White-Box Testing (K2 — explain)

**Strengths:**
- Entire software implementation considered — even if spec is vague, outdated, or incomplete
- Used in static testing too (dry runs, pseudocode, control flow graph reviews)
- Provides objective, measurable coverage
- Identifies paths to add tests for

**Weakness:**
- Cannot detect **defects of omission** — if a requirement isn't implemented, white-box tests won't find what isn't there

---

## 4.4 Experience-based Test Techniques

### 4.4.1 Error Guessing (K2 — explain)

**Based on:** Tester's knowledge of:
- How the application worked in the past
- Types of errors developers tend to make
- Types of failures in similar applications

**Common areas:** Input, output, logic, computation, interfaces, data

**Fault attacks:** Create a list of possible errors/defects/failures → design tests to detect them.

---

### 4.4.2 Exploratory Testing (K2 — explain)

**Definition:** Tests are **simultaneously designed, executed, and evaluated** while the tester learns about the test object.

**Session-based testing:**
- Defined **time box**
- **Test charter** with objectives to guide testing
- Followed by **debriefing** with stakeholders
- **Test session sheets** document steps and discoveries

**Best when:**
- Few or inadequate specifications
- Significant time pressure
- Complementing formal techniques

**Most effective when** tester has: experience, domain knowledge, analytical skills, curiosity, creativity.

---

### 4.4.3 Checklist-Based Testing (K2 — explain)

**Definition:** Design, implement, and execute tests to cover items on a checklist.

**Good checklists:**
- Based on experience, user importance, or failure modes
- Items phrased as questions
- Each item checked separately and directly
- Should NOT contain: auto-checkable items, entry/exit criteria items, overly general items
- Regularly updated based on defect analysis

**Benefit:** Provides guidelines and consistency when detailed test cases are absent.

**Limitation:** High-level checklists → variability in testing → greater coverage but less repeatability.

---

## 4.5 Collaboration-based Test Approaches

### 4.5.1 Collaborative User Story Writing (K2 — explain)

**3 C's of User Stories (Jeffries 2000):**
- **Card** — the medium (index card, electronic board entry)
- **Conversation** — explains how the software will be used
- **Confirmation** — the acceptance criteria

**Format:** `"As a [role], I want [goal], so that I can [business value]"` + acceptance criteria

**INVEST criteria** for good user stories:
- **I**ndependent
- **N**egotiable
- **V**aluable
- **E**stimable
- **S**mall
- **T**estable

---

### 4.5.2 Acceptance Criteria (K2 — classify)

**Definition:** Conditions an implementation must meet to be **accepted by stakeholders**.

**Used to:**
- Define the scope of the user story
- Reach consensus among stakeholders
- Describe positive AND negative scenarios
- Serve as basis for acceptance testing
- Enable accurate planning and estimation

**Two common formats:**

| Format | Description |
|--------|-------------|
| **Scenario-oriented** | Given/When/Then (BDD format) |
| **Rule-oriented** | Bullet point verification list or input-output mapping table |

---

### 4.5.3 ATDD — Acceptance Test-Driven Development (K3 — use)

**Process:**
1. **Specification workshop** — user story + acceptance criteria analysed, discussed, written by team (developers, testers, customers)
2. **Test cases created** — based on acceptance criteria (examples of how software works)
3. **Tests automate** — when using automation framework, tests become **executable requirements**

**Order of test design:**
1. Positive test cases first (correct behaviour, no errors)
2. Negative testing (error conditions, exceptions)
3. Non-functional characteristics (performance, usability)

**Rules:**
- Test cases must cover **all characteristics** of the user story
- Test cases must **NOT exceed** the story scope
- No two test cases describe the same characteristic

---

## 📝 Exam Quick-Check

- What are the **3 categories of test techniques**? How do they differ?
- For **EP**: what is a valid vs invalid partition? What is Each Choice coverage?
- For **BVA**: what's the difference between 2-value and 3-value? When would you choose each?
- For **decision tables**: what do `T`, `F`, `-`, and `N/A` mean?
- For **state transition**: put the 3 coverage criteria in order from weakest to strongest.
- What is the relationship between **branch coverage and statement coverage**?
- What is the **weakness** of white-box testing?
- What does **INVEST** stand for in user stories?
- What are the **3 C's** of a user story?
- What is the difference between **error guessing** and **exploratory testing**?
