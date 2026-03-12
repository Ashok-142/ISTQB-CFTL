# Chapter 5 — Managing the Test Activities
#ISTQB #CTFL #Chapter5

> ⏱ 335 minutes | [[00-INDEX|← Back to Index]]

---

## Keywords (must know K1)
`defect management` `defect report` `entry criteria` `exit criteria` `product risk` `project risk` `risk` `risk analysis` `risk assessment` `risk control` `risk identification` `risk level` `risk management` `risk mitigation` `risk monitoring` `risk-based testing` `test approach` `test completion report` `test control` `test monitoring` `test plan` `test planning` `test progress report` `test pyramid` `test strategy` `testing quadrants`

---

## 5.1 Test Planning

### 5.1.1 Purpose and Content of a Test Plan (K2 — exemplify)

**A test plan:**
- Documents means and schedule for achieving test objectives
- Ensures test activities meet established criteria
- Serves as communication with team/stakeholders
- Demonstrates adherence to test policy/strategy (or explains deviations)

**Typical content:**
- Context of testing (scope, objectives, test basis)
- Assumptions and constraints
- Stakeholders (roles, responsibilities, training needs)
- Communication (forms, frequency, templates)
- Risk register (product and project risks)
- Test approach (levels, types, techniques, deliverables, entry/exit criteria, independence, metrics, data/environment requirements)
- Budget and schedule

---

### 5.1.2 Tester's Contribution to Planning (K1 — recognise)

**Release planning** (big picture):
- Writing testable user stories and acceptance criteria
- Project and quality risk analyses
- Estimating test effort for user stories
- Determining test approach
- Planning testing for the release

**Iteration planning** (sprint level):
- Detailed risk analysis of user stories
- Determining testability of user stories
- Breaking user stories into testing tasks
- Estimating effort for all testing tasks
- Identifying and refining functional and non-functional aspects

---

### 5.1.3 Entry Criteria and Exit Criteria (K2 — compare and contrast)

| | Entry Criteria | Exit Criteria |
|--|---------------|--------------|
| **Definition** | Preconditions for **starting** an activity | What must be achieved to **declare an activity complete** |
| **Purpose** | Ensure testing is feasible to begin | Define when testing is done |
| **Agile equivalent** | **Definition of Ready** (user story) | **Definition of Done** (team's metrics for releasable item) |

**Typical entry criteria:**
- Resources available (people, tools, environments, test data, budget, time)
- Testware available (test basis, requirements, user stories, test cases)
- Initial quality of test object acceptable (e.g., smoke tests passed)

**Typical exit criteria:**
- Thoroughness measures (coverage achieved, unresolved defects, defect density, failed test cases)
- Binary criteria (planned tests executed, static testing done, all defects reported, regression tests automated)

> ⚠️ Running out of time/budget can be a valid exit criterion if stakeholders have reviewed and accepted the risk.

---

### 5.1.4 Estimation Techniques (K3 — use to calculate)

| Technique | Type | How it works |
|-----------|------|-------------|
| **Estimation based on ratios** | Metrics-based | Use historical data from similar projects to derive standard ratios (e.g., dev:test = 3:2) |
| **Extrapolation** | Metrics-based | Measure early iterations → extrapolate remaining effort using a mathematical model |
| **Wideband Delphi** | Expert-based | Experts estimate independently → compare → discuss deviations → re-estimate → repeat until consensus. Planning Poker is a variant. |
| **Three-point estimation** | Expert-based | E = (a + 4m + b) / 6; SD = (b - a) / 6 |

**Three-point formula:**
- `a` = most optimistic estimate
- `m` = most likely estimate
- `b` = most pessimistic estimate
- `E = (a + 4m + b) / 6`
- `SD = (b − a) / 6`

**Example:** a=6, m=9, b=18 → E = (6 + 36 + 18)/6 = **10** person-hours; SD = (18-6)/6 = **2** → estimate: **10 ± 2 person-hours**

---

### 5.1.5 Test Case Prioritisation (K3 — apply)

| Strategy | Order based on |
|----------|---------------|
| **Risk-based prioritisation** | Results of risk analysis — highest risk first |
| **Coverage-based prioritisation** | Highest coverage first (or additional coverage first) |
| **Requirements-based prioritisation** | Stakeholder-defined requirement priorities — most important first |

> ⚠️ Dependencies between test cases may override priority order — lower priority test case may need to run first.

---

### 5.1.6 Test Pyramid (K1 — recall)

Represents different levels of test granularity:

```
         /\
        /  \  ← UI / End-to-end tests (few, slow, high-level)
       /    \
      /------\  ← Service / Integration tests
     /        \
    /----------\  ← Unit / Component tests (many, fast, isolated)
```

- **Bottom layer:** Small, isolated, fast, check small functionality — need many
- **Top layer:** Complex, end-to-end, slow, check large functionality — need few
- Supports test automation planning and effort allocation

---

### 5.1.7 Testing Quadrants (K2 — summarise)

*(Brian Marick model)*

|  | **Support the team (guide development)** | **Critique the product (measure behaviour)** |
|--|------------------------------------------|---------------------------------------------|
| **Business facing** | **Q2:** Functional tests, examples, user story tests, UX prototypes, API testing, simulations → manual or automated | **Q3:** Exploratory testing, usability testing, UAT → user-oriented, often manual |
| **Technology facing** | **Q1:** Component tests, component integration tests → automated, in CI | **Q4:** Smoke tests, non-functional tests (except usability) → often automated |

---

## 5.2 Risk Management

### 5.2.1 Risk Definition and Attributes (K1 — identify)

**Risk** = potential event whose occurrence causes adverse effect.

**Two factors:**
- **Risk likelihood** — probability of occurrence (0 < p < 1)
- **Risk impact (harm)** — consequences of occurrence

**Risk level** = measure based on likelihood × impact → higher level = more important to treat.

**Risk-based testing** = test activities selected, prioritised, managed based on risk analysis and control.

---

### 5.2.2 Project Risks vs Product Risks (K2 — distinguish)

| | Project Risks | Product Risks |
|--|--------------|--------------|
| **Related to** | Management and control of the project | Product quality characteristics (ISO 25010) |
| **Examples** | Organizational issues (delays, poor estimates); People issues (insufficient skills, staff shortage); Technical issues (scope creep); Supplier issues (delivery failure) | Missing/wrong functionality, incorrect calculations, runtime errors, poor architecture, security vulnerabilities, poor UX |
| **Impact when occur** | Affects project schedule, budget, or scope | User dissatisfaction, revenue loss, damage, criminal penalties, physical harm |

---

### 5.2.3 Product Risk Analysis (K2 — explain influence)

**Goal:** Minimise residual product risk by focusing test effort appropriately.

**Two parts:**
1. **Risk identification** — brainstorming, workshops, interviews, cause-effect diagrams
2. **Risk assessment** — categorise risks, determine likelihood/impact/level, prioritise, propose mitigations

**Assessment approaches:**
- **Quantitative:** risk level = likelihood × impact
- **Qualitative:** use a risk matrix

**Influences on testing:**
- Determine test scope
- Select test levels and types
- Choose test techniques and coverage targets
- Estimate test effort per task
- Prioritise to find critical defects early
- Identify activities beyond testing to reduce risk

---

### 5.2.4 Product Risk Control (K2 — explain)

**Risk control** = risk mitigation + risk monitoring

**Response options after risk analysis:**
- Risk mitigation by testing
- Risk acceptance
- Risk transfer
- Contingency plan

**Actions to mitigate product risks via testing:**
- Select testers with appropriate experience for risk type
- Apply appropriate independence level
- Perform reviews and static analysis
- Apply appropriate test techniques and coverage levels
- Apply appropriate test types for affected quality characteristics
- Perform dynamic testing including regression testing

---

## 5.3 Test Monitoring, Control and Completion

### 5.3.1 Metrics used in Testing (K1 — recall)

| Category | Examples |
|----------|---------|
| **Project progress** | Task completion, resource usage, test effort |
| **Test progress** | Test cases run/not run, passed/failed, execution time, environment preparation |
| **Product quality** | Availability, response time, mean time to failure |
| **Defect** | Defects found/fixed, defect density, defect detection percentage |
| **Risk** | Residual risk level |
| **Coverage** | Requirements coverage, code coverage |
| **Cost** | Cost of testing, cost of quality |

---

### 5.3.2 Test Reports (K2 — summarise)

**Two types:**

| | Test Progress Report | Test Completion Report |
|--|---------------------|----------------------|
| **When** | During testing (regular: daily/weekly) | At end of project/test level/test type |
| **Purpose** | Support ongoing test control; inform stakeholders | Summarise entire test activity; inform future testing |
| **Audience** | Team members (frequent, informal) | Stakeholders (formal, once per milestone) |
| **Content** | Testing period, progress, impediments, metrics, new risks, next period plan | Test summary, quality evaluation vs plan, deviations, impediments, metrics, unmitigated risks, lessons learned |

---

### 5.3.3 Communicating Test Status (K2 — exemplify)

Options:
- Verbal communication (team/stakeholders)
- Dashboards (CI/CD, task boards, burn-down charts)
- Electronic communication (email, chat)
- Online documentation
- Formal test reports

> 💡 Distributed teams → more formal communication; different stakeholders → tailor content accordingly.

---

## 5.4 Configuration Management (K2 — summarise)

**CM provides discipline for:** identifying, controlling, and tracking work products (test plans, conditions, cases, scripts, results, logs, reports) as **configuration items**.

**A baseline** = approved configuration item that can only be changed via formal change control.

**CM ensures:**
- All configuration items uniquely identified, version controlled, tracked, related to others (supports traceability)
- All documentation and software items unambiguously referenced in testware

> 💡 Enables reverting to previous baselines to reproduce previous test results. Part of DevOps automated pipelines.

---

## 5.5 Defect Management (K3 — prepare a defect report)

**Process:** Discovery → logging → analysis/classification → decision → closure

> 🔑 Reported anomalies may be real defects, false positives, or change requests — resolved during process.

**Objectives of a defect report:**
- Provide sufficient info for resolution
- Track quality of work product
- Provide improvement ideas for development and test process

**Defect report content:**
| Field | Description |
|-------|-------------|
| Unique identifier | Auto-generated |
| Title / Summary | Short description of the anomaly |
| Date, organisation, author, role | When/who reported |
| Test object and test environment | What was being tested |
| Context | Test case, SDLC phase, technique, checklist, test data |
| Description of failure | Steps to reproduce, logs, screenshots, recordings |
| Expected vs actual results | What should happen vs what happened |
| Severity | Degree of impact on stakeholders/requirements |
| Priority | Urgency to fix |
| Status | open, deferred, duplicate, waiting to be fixed, awaiting confirmation, re-opened, closed, rejected |
| References | Related test cases |

---

## 📝 Exam Quick-Check

- What are the **4 estimation techniques**? How does each work?
- Calculate: a=4, m=8, b=18 → E = ? SD = ?
- What are the **3 test case prioritisation strategies**?
- What is the difference between **entry criteria and exit criteria**?
- What is the difference between **project risk and product risk**? Give 2 examples of each.
- What are the **4 quadrants** and what testing is in each?
- What does a **defect report** contain? (list key fields)
- What metrics categories does CM support?
- What are the **2 test report types** and when is each produced?
- What is **risk-based testing**?
