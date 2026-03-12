# Exam Tips & Final Revision Guide
#ISTQB #CTFL #ExamTips

> [[00-INDEX|← Back to Index]]

---

## 🎯 Exam Format

- **40 questions** (multiple choice)
- **60 minutes**
- **Pass mark: 65%** = 26 correct answers minimum
- All chapters 1–6 are examinable
- Some questions draw on content from multiple chapters

---

## ⚡ The Most Commonly Tested Concepts

### 🔁 Things that get confused — learn these pairs carefully

| Confused pair | How to tell them apart |
|--------------|----------------------|
| **Error vs Defect vs Failure** | Error = human mistake → creates Defect → when executed may cause Failure |
| **Testing vs Debugging** | Testing = finds failures/defects. Debugging = diagnoses & fixes defects |
| **Testing vs QA** | Testing = product-oriented, corrective. QA = process-oriented, preventive |
| **Verification vs Validation** | Verification = "built it right?" (vs requirements). Validation = "built the right thing?" (vs user needs) |
| **Static vs Dynamic testing** | Static = no execution. Dynamic = requires execution |
| **Confirmation vs Regression** | Confirmation = retest the fix. Regression = check nothing else broke |
| **Entry vs Exit criteria** | Entry = must be true to START. Exit = must be true to FINISH |
| **Project risk vs Product risk** | Project = schedule/budget/scope. Product = quality characteristics |
| **Statement vs Branch coverage** | Branch subsumes statement — 100% branch always gives 100% statement, not vice versa |
| **Walkthrough vs Inspection** | Walkthrough = author leads, informal-medium. Inspection = most formal, author ≠ leader/scribe |

---

## 📊 Tables to Memorise

### 7 Testing Principles
1. Testing shows presence, not absence of defects
2. Exhaustive testing is impossible
3. Early testing saves time and money
4. Defects cluster together (Pareto)
5. Tests wear out
6. Testing is context dependent
7. Absence-of-defects fallacy

### 5 Test Levels (weakest to highest scope)
1. Component (unit) — isolated, by developers
2. Component integration — interfaces between components
3. System — full system, functional + non-functional
4. System integration — interfaces with other systems
5. Acceptance — validation, business readiness

### 4 Review Types (least to most formal)
1. Informal
2. Walkthrough (author leads)
3. Technical Review (moderator leads, technical reviewers)
4. Inspection (most formal, author ≠ leader/scribe, metrics collected)

### State Transition Coverage (weakest to strongest)
1. All states coverage
2. Valid transitions coverage (0-switch) ← most commonly used
3. All transitions coverage ← minimum for safety-critical

### 4 Estimation Techniques
1. Estimation based on ratios (metrics-based, historical data)
2. Extrapolation (metrics-based, current project data)
3. Wideband Delphi / Planning Poker (expert-based, consensus)
4. Three-point estimation: E = (a + 4m + b) / 6

---

## 🚩 Common Exam Traps

1. **"Testing proves software is defect-free"** → ❌ NEVER true — principle 1
2. **"The author should lead the inspection"** → ❌ In inspections, author CANNOT be leader or scribe
3. **"100% statement coverage means all branches tested"** → ❌ Branch subsumes statement, not the other way
4. **"Regression testing = retesting the fix"** → ❌ That's confirmation testing. Regression = checking nothing else broke
5. **"QA is the same as testing"** → ❌ QA is process-oriented and everyone's responsibility; testing is product-oriented
6. **"White-box testing can detect omitted requirements"** → ❌ It only tests what IS implemented
7. **"More independence is always better"** → ❌ Has drawbacks: isolation, communication problems, adversarial relationships
8. **"Exhaustive testing is possible with enough time"** → ❌ Principle 2: it's impossible except in trivial cases

---

## 💡 Memory Aids

### INVEST (User Story criteria)
**I**ndependent **N**egotiable **V**aluable **E**stimable **S**mall **T**estable

### 3 C's of User Stories
**C**ard — **C**onversation — **C**onfirmation

### BVA: 2-value vs 3-value
- 2-value: boundary + 1 neighbour
- 3-value: boundary + 2 neighbours (one each side) → MORE RIGOROUS

### EP Coverage Formula
`Coverage % = (partitions exercised / total partitions) × 100`

### Three-point Estimation Formula
`E = (a + 4m + b) / 6`  
`SD = (b − a) / 6`

### Testing Quadrants Shortcut
- Q1: Tech + Support = component/unit tests (automated, CI)
- Q2: Business + Support = functional, acceptance criteria (manual or automated)
- Q3: Business + Critique = exploratory, usability, UAT (manual)
- Q4: Tech + Critique = smoke tests, non-functional (automated)

---

## 📅 Final Week Revision Plan

| Day | Focus |
|-----|-------|
| Day 1 | Ch1: 7 principles + error/defect/failure chain + test objectives |
| Day 2 | Ch2: 5 test levels + 4 test types + shift left + TDD/ATDD/BDD |
| Day 3 | Ch3: static vs dynamic + 4 review types + 6 roles + success factors |
| Day 4 | Ch4: EP + BVA (2-value vs 3-value) + decision table + state transition |
| Day 5 | Ch4 continued: white-box (statement vs branch) + ATDD + INVEST |
| Day 6 | Ch5: risk types + estimation formulas + entry/exit criteria + defect report |
| Day 7 | Ch6 + full mock exam + review weak areas |

---

## 🧪 Self-Test: Recall Without Notes

Try answering each of these before checking your notes:

**Chapter 1:**
- [ ] Name all 7 testing principles
- [ ] Explain error → defect → failure with an example
- [ ] Distinguish testing from debugging in 2 sentences
- [ ] What's the difference between QA and testing?

**Chapter 2:**
- [ ] Name the 5 test levels and who performs each
- [ ] What does shift left mean? Give 3 examples
- [ ] Distinguish confirmation from regression testing

**Chapter 3:**
- [ ] List 4 differences between static and dynamic testing
- [ ] Name the 5 review process activities in order
- [ ] Name the 4 review types ordered by formality
- [ ] What makes an inspection unique?

**Chapter 4:**
- [ ] What are the 3 test technique categories?
- [ ] For BVA: what values does 3-value cover that 2-value doesn't?
- [ ] In decision tables: what does `-` mean? What does `N/A` mean?
- [ ] State transition: which coverage is minimum for safety-critical?
- [ ] Branch vs statement: which subsumes which?

**Chapter 5:**
- [ ] Three-point estimation: write the formula
- [ ] Name all 3 test case prioritisation strategies
- [ ] Name 4 project risks and 4 product risks
- [ ] List 6 key fields in a defect report
- [ ] What are the 4 testing quadrants?

**Chapter 6:**
- [ ] Name 4 benefits of test automation
- [ ] Name 4 risks of test automation
