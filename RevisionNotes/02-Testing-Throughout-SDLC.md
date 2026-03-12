# Chapter 2 — Testing Throughout the SDLC
#ISTQB #CTFL #Chapter2

> ⏱ 130 minutes | [[00-INDEX|← Back to Index]]

---

## Keywords (must know K1)
`acceptance testing` `black-box testing` `component integration testing` `component testing` `confirmation testing` `functional testing` `integration testing` `maintenance testing` `non-functional testing` `regression testing` `shift left` `system integration testing` `system testing` `test level` `test object` `test type` `white-box testing`

---

## 2.1 Testing in the Context of a SDLC

### SDLC Model Types:
- **Sequential:** Waterfall, V-model → limited early dynamic testing
- **Iterative:** Spiral, Prototyping → static + dynamic testing each iteration
- **Incremental:** Unified Process → working increment each cycle
- **Agile methods:** Scrum, Kanban, XP → lightweight docs, extensive automation

### 2.1.1 SDLC Impact on Testing (K2 — explain)

SDLC choice affects:
- Scope and timing of test activities
- Level of detail of test documentation
- Choice of test techniques and approach
- Extent of test automation
- Tester's role and responsibilities

### 2.1.2 Good Testing Practices (K1 — recall)

Regardless of SDLC model:
- Every development activity has a **corresponding test activity**
- Different test levels have **specific, different** test objectives (no redundancy)
- Test analysis/design begins **during the corresponding development phase**
- Testers are **involved in reviewing work products as soon as drafts are available**

---

## 2.1.3 Test-First Approaches (K1 — recall examples)

| Approach | Description |
|----------|-------------|
| **TDD** (Test-Driven Development) | Write test → write code to pass → refactor |
| **ATDD** (Acceptance Test-Driven Dev.) | Derive tests from acceptance criteria before building |
| **BDD** (Behaviour-Driven Development) | Tests in natural language (Given/When/Then); auto-translatable |

All three: early testing + shift left + iterative development. Tests persist as **automated regression tests**.

---

## 2.1.4 DevOps and Testing (K2 — summarise)

**DevOps** = development (incl. testing) + operations working together with shared goals.

**Benefits for testing:**
- Fast feedback on code quality
- CI promotes shift left (devs submit code + component tests + static analysis)
- Stable test environments via automated pipelines
- Increased visibility of non-functional quality
- Less repetitive manual testing via automation
- Minimised regression risk through automated regression tests

**Challenges/risks:**
- DevOps pipeline must be defined and established
- CI/CD tools need introduction and maintenance
- Test automation requires resources and effort

> ⚠️ Manual testing — especially from the user's perspective — is **still needed** in DevOps.

---

## 2.1.5 Shift Left (K2 — explain)

**Shift left** = perform testing **earlier** in the SDLC (not just at the end).

**Practices that achieve shift left:**
- Review specifications from a testing perspective — find ambiguities/incompleteness early
- Write test cases before code is written
- Use CI/CD with fast feedback and automated component tests
- Complete static analysis before dynamic testing
- Perform non-functional testing from component level upwards

> 💡 Shift left may mean **extra effort/cost early** but **saves more later**. Stakeholder buy-in is essential.

---

## 2.1.6 Retrospectives (K2 — explain)

**When:** End of project/iteration, release milestone, or when needed.

**Discussed:**
- What was successful and should be retained?
- What was not successful and could be improved?
- How to incorporate improvements in future?

**Benefits for testing:**
- Increased test effectiveness/efficiency
- Better quality testware
- Team bonding and learning
- Improved quality of test basis (requirements deficiencies addressed)
- Better cooperation between dev and testing

> 📌 Results are recorded in the test completion report. Improvements must be followed up.

---

## 2.2 Test Levels and Test Types

### 2.2.1 Five Test Levels (K2 — distinguish)

| Level | Focus | Who |
|-------|-------|-----|
| **Component** (unit) testing | Individual components in isolation; uses test harnesses/frameworks | Developers |
| **Component Integration** (unit integration) | Interfaces/interactions between components; depends on integration strategy (bottom-up, top-down, big-bang) | Developers |
| **System testing** | Overall behaviour of the entire system; functional + non-functional; end-to-end | Independent test team |
| **System Integration testing** | Interfaces with other systems and external services; needs realistic test environment | Test team |
| **Acceptance testing** | Validation; readiness for deployment; meets business needs | Intended users (ideally) |

**Acceptance testing forms:**
- UAT (User Acceptance Testing)
- Operational acceptance testing
- Contractual/regulatory acceptance testing
- Alpha testing (internal users)
- Beta testing (external users)

**Test levels are distinguished by:**
Test object · Test objectives · Test basis · Defects and failures · Approach and responsibilities

---

### 2.2.2 Four Test Types (K2 — distinguish)

| Type | What it tests | Basis |
|------|--------------|-------|
| **Functional** | *What* the system does; functional completeness, correctness, appropriateness | Specifications |
| **Non-functional** | *How well* it behaves; quality characteristics (ISO 25010) | Quality models |
| **Black-box** | Behaviour vs specification; no knowledge of internals | Specs/docs |
| **White-box** | Internal structure (code, architecture, data flows) | Code/design |

**ISO 25010 Non-functional quality characteristics:**
Performance efficiency · Compatibility · Usability · Reliability · Security · Maintainability · Portability · Safety

> 💡 All 4 test types can be applied at all test levels — focus differs.

---

### 2.2.3 Confirmation Testing vs Regression Testing (K2 — distinguish)

| | Confirmation Testing | Regression Testing |
|--|---------------------|-------------------|
| **Purpose** | Confirms a specific defect has been **fixed** | Confirms no **new failures** were introduced by a change |
| **Trigger** | After a defect fix | After any change (fix, enhancement, environment change) |
| **Scope** | Test steps that reproduced the original failure | Broader — can be the whole system |
| **Automation** | Less common | Strong candidate for automation (grows with each iteration) |

> 💡 Regression testing is a strong candidate for automation due to repetition. In DevOps/CI, automated regression tests are best practice.

---

## 2.3 Maintenance Testing (K2 — summarise)

**Maintenance testing** = testing changes to an **operational system**.

**Categories of maintenance:**
- Corrective (fix bugs)
- Adaptive (environment changes)
- Improve performance/maintainability

**Scope depends on:**
- Degree of risk of the change
- Size of the existing system
- Size of the change

### Triggers for maintenance testing:

| Trigger | Examples |
|---------|---------|
| **Modifications** | Planned enhancements, corrective changes, hot fixes |
| **Upgrades/Migrations** | New platform, data migration |
| **Retirement** | Data archiving, restore/retrieval testing |

> 💡 **Impact analysis** helps decide if change should be made, and scope of regression testing needed.

---

## 📝 Exam Quick-Check

- What are the **5 test levels**? Who performs each?
- What are the **4 test types**? How do they differ?
- What is the difference between **confirmation** and **regression testing**?
- What is **shift left**? Give 3 practices that achieve it.
- What is the difference between **TDD, ATDD, and BDD**?
- What does DevOps mean for testing? (benefits and risks)
- What are the triggers for **maintenance testing**?
