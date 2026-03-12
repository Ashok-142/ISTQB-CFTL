# Chapter 1 — Fundamentals of Testing
#ISTQB #CTFL #Chapter1

> ⏱ 180 minutes | [[00-INDEX|← Back to Index]]

---

## Keywords (must know K1)
`coverage` `debugging` `defect` `error` `failure` `quality` `quality assurance` `root cause` `test analysis` `test basis` `test case` `test completion` `test condition` `test control` `test data` `test design` `test execution` `test implementation` `test monitoring` `test object` `test objective` `test planning` `test procedure` `test process` `test result` `testing` `testware` `traceability` `validation` `verification`

---

## 1.1 What is Testing?

**Definition:** Software testing is a set of activities to **discover defects** and **evaluate the quality** of software work products.

> 🔑 Testing is NOT just running the software — it includes planning, analysis, design, and reporting.

### Two misconceptions to remember:
1. ❌ "Testing only = executing tests" → ✅ Testing includes many activities across the SDLC
2. ❌ "Testing only = verification" → ✅ Testing includes both **verification** AND **validation**

| Term | Definition |
|------|-----------|
| **Verification** | Checking whether the system meets **specified requirements** |
| **Validation** | Checking whether the system meets **users' actual needs** in operation |

### Types of Testing:
- **Dynamic testing** — requires code execution
- **Static testing** — does NOT require code execution (reviews, static analysis)

---

## 1.1.1 Test Objectives (K1 — identify)

- Evaluating work products (requirements, designs, code)
- Causing failures and finding defects
- Ensuring required coverage of a test object
- Reducing risk of inadequate software quality
- Verifying whether specified requirements are fulfilled
- Verifying compliance with contractual, legal, regulatory requirements
- Providing information to stakeholders for informed decisions
- Building confidence in the quality of the test object
- Validating the test object is complete and works as expected

> 💡 Test objectives **vary by context** — test level, SDLC, business context, risks

---

## 1.1.2 Testing vs Debugging (K2 — differentiate)

| | Testing | Debugging |
|--|---------|-----------|
| **What it does** | Finds failures / defects | Diagnoses and fixes defects |
| **Who does it** | Testers | Developers |
| **Dynamic context** | Triggers failures → reports them | Reproduces → diagnoses → fixes |
| **Static context** | Finds defects directly | Removes the defect |

**Debugging process (dynamic):**
1. Reproduction of a failure
2. Diagnosis (finding the defect)
3. Fixing the defect

After fixing → **Confirmation testing** (retest the fix) → **Regression testing** (check no new failures)

---

## 1.2 Why is Testing Necessary?

### 1.2.1 Contributions to Success
- Provides cost-effective defect detection
- Evaluates quality at various SDLC phases
- Represents users' interests in development
- May be required for contractual / legal / regulatory compliance

### 1.2.2 Testing vs QA (K1 — recall relation)

| | Testing | Quality Assurance (QA) |
|--|---------|----------------------|
| **Focus** | Product-oriented, corrective | Process-oriented, preventive |
| **Goal** | Achieve appropriate quality levels | Implement and improve processes |
| **Scope** | A form of quality control | Responsibility of **everyone** on project |

> 🔑 QA: "Good process → good product." Test results used in QA for process feedback; used in testing to fix defects.

### 1.2.3 Errors → Defects → Failures (K2 — distinguish)

```
Human Error (mistake)  
    ↓  
Defect (fault/bug) — in code, docs, requirements  
    ↓ (if executed)  
Failure (incorrect behaviour)
```

**Root cause:** The fundamental reason for the occurrence of a problem (leads to an error).

> ⚠️ Not all defects cause failures (some require specific circumstances). Not all failures are from code defects — environmental conditions (radiation, EMF) can also cause failures.

---

## 1.3 Testing Principles (K2 — explain all 7)

| # | Principle | Key Point |
|---|-----------|-----------|
| 1 | **Testing shows presence, not absence of defects** | Can't prove zero defects exist |
| 2 | **Exhaustive testing is impossible** | Use risk-based, prioritised approaches |
| 3 | **Early testing saves time and money** | Shift left — start static + dynamic testing ASAP |
| 4 | **Defects cluster together** | Pareto principle — small % of components cause most defects |
| 5 | **Tests wear out** | Same tests become ineffective — vary and add new tests |
| 6 | **Testing is context dependent** | No universal approach — adapt to context |
| 7 | **Absence-of-defects fallacy** | Meeting all requirements ≠ user satisfaction — also validate! |

---

## 1.4 Test Activities, Testware and Test Roles

### 1.4.1 Test Activities and Tasks (K2)

| Activity | Key question | Key outputs |
|----------|-------------|-------------|
| **Test Planning** | Why/what/how/when? | Test plan, risk register |
| **Test Monitoring & Control** | Are we on track? | Progress reports, control directives |
| **Test Analysis** | **What to test?** | Test conditions, defect reports on test basis |
| **Test Design** | **How to test?** | Test cases, test charters, coverage items |
| **Test Implementation** | Ready to run? | Test procedures, scripts, test suites, test data |
| **Test Execution** | Run and record | Test logs, defect reports |
| **Test Completion** | Lessons learned? | Test completion report, archived testware |

### 1.4.2 Context Factors (K2)

Testing is influenced by:
- Stakeholders · Team members · Business domain · Technical factors
- Project constraints · Organizational factors · SDLC · Tools

### 1.4.3 Testware by Activity (K2 — differentiate)

| Activity | Testware produced |
|----------|------------------|
| Planning | Test plan, schedule, risk register, entry/exit criteria |
| Monitoring/Control | Test progress reports, control directives |
| Analysis | Test conditions, defect reports on test basis |
| Design | Test cases, coverage items, test data requirements |
| Implementation | Test procedures, scripts, test suites, test data, execution schedule |
| Execution | Test logs, defect reports |
| Completion | Completion report, lessons learned, change requests |

### 1.4.4 Traceability (K2 — explain value)

**Traceability** = links between test basis elements ↔ testware ↔ test results ↔ defects

Benefits:
- Coverage evaluation — verify all requirements tested
- Residual risk assessment
- Impact analysis for changes
- Facilitates audits and IT governance
- Communicates technical aspects to stakeholders

### 1.4.5 Roles in Testing (K2 — compare)

| Role | Focus | Responsible for |
|------|-------|----------------|
| **Test Management** | Process & leadership | Planning, monitoring, control, completion |
| **Testing** | Engineering/technical | Analysis, design, implementation, execution |

> 💡 One person can hold both roles. In Agile, test management tasks may be distributed across the team.

---

## 1.5 Essential Skills and Good Practices

### 1.5.1 Generic Skills (K2 — give examples)

- Testing knowledge — techniques and methods
- Thoroughness, carefulness, curiosity, attention to detail
- Good communication, active listening, team player
- Analytical thinking, critical thinking, creativity
- Technical knowledge (tools)
- Domain knowledge (understand end users)

> 💡 Testers are "bearers of bad news" — communication skills are critical. Defect info must be communicated **constructively**.

### 1.5.2 Whole Team Approach (K1 — recall advantages)

- From **Extreme Programming (XP)**
- **Anyone** with the skills can do any task
- **Everyone** is responsible for quality
- Shared workspace (physical or virtual) → better collaboration
- Improves team dynamics, communication, synergy

> ⚠️ Not always appropriate — safety-critical contexts may need high independence

### 1.5.3 Independence of Testing (K2 — benefits/drawbacks)

**Levels of independence:**
- No independence: author tests own work
- Some independence: peers from same team
- High independence: testers from outside author's team
- Very high independence: testers from outside the organization

**Benefits of independence:**
- Recognises different failures/defects
- Different backgrounds → different biases
- Can verify/challenge/disprove assumptions

**Drawbacks of independence:**
- Isolation from dev team → communication problems
- Developers may lose sense of responsibility for quality
- Can be seen as bottleneck or blamed for delays

---

## 📝 Exam Quick-Check

> Try answering before revealing — test yourself!

- What are the **7 testing principles**? (list them)
- What is the difference between **error, defect, failure, root cause**?
- What is the difference between **testing and debugging**?
- What is the difference between **testing and QA**?
- What is the difference between **verification and validation**?
- What are the **6 main test activities**?
- What are the **two roles in testing** and what does each cover?
