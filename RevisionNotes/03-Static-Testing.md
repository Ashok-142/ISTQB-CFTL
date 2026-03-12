# Chapter 3 — Static Testing
#ISTQB #CTFL #Chapter3

> ⏱ 80 minutes | [[00-INDEX|← Back to Index]]

---

## Keywords (must know K1)
`anomaly` `dynamic testing` `formal review` `informal review` `inspection` `review` `static analysis` `static testing` `technical review` `walkthrough`

---

## 3.1 Static Testing Basics

**Static testing** = examining work products **without executing the software**.

Methods:
- **Manual examination** — reviews
- **Tool-assisted** — static analysis (e.g., linters, code analysers)

Can be used for both **verification** AND **validation**.

---

## 3.1.1 Work Products Examinable by Static Testing (K1 — recognise)

**Can be reviewed:**
Almost any work product that can be read and understood, including:
- Requirements specification documents
- Source code
- Test plans and test cases
- Product backlog items / test charters
- Project documentation
- Contracts
- Models (state diagrams, business process models)

**Can be statically analysed (needs formal structure):**
- Models, code, or text with formal syntax

**NOT appropriate for static testing:**
- Work products difficult to interpret by humans
- 3rd party executable code (legal reasons)

---

## 3.1.2 Value of Static Testing (K2 — explain)

- **Early defect detection** — fulfils principle of early testing
- **Finds defects dynamic testing cannot** — unreachable code, design pattern errors, defects in non-executable work products
- **Builds confidence in work products**
- **Verifies documented requirements** match actual stakeholder needs
- **Creates shared understanding** among stakeholders (involves wide variety)
- **Improves communication** between stakeholders
- **Cost effective** — reviews cost less than fixing defects found later

**Static analysis specifically:**
- Identifies code defects before dynamic testing with less effort (no test cases needed)
- Often incorporated into CI frameworks
- Useful for maintainability and security evaluation
- Examples: spelling checkers, readability tools, linters

---

## 3.1.3 Static Testing vs Dynamic Testing (K2 — compare and contrast)

| Dimension                        | Static Testing                                           | Dynamic Testing                                      |
| -------------------------------- | -------------------------------------------------------- | ---------------------------------------------------- |
| **Execution**                    | No execution required                                    | Code must be executed                                |
| **What is examined**             | Any work product                                         | Executable software only                             |
| **How defects found**            | **Directly** identifies defects                          | Causes **failures** → defects determined by analysis |
| **Hard-to-reach paths**          | Easily examines all paths                                | Hard-to-reach paths may not be triggered             |
| **Non-executable work products** | ✅ Can test (requirements, plans)                         | ❌ Cannot test                                        |
| **Quality characteristics**      | Those NOT dependent on execution (e.g., maintainability) | Those dependent on execution (e.g., performance)     |

### Defect types easier/cheaper to find via static testing:
- **Requirements defects** — inconsistencies, ambiguities, contradictions, omissions, inaccuracies, duplications
- **Design defects** — inefficient DB structures, poor modularisation
- **Coding defects** — undefined variable values, unreachable/duplicated code, excessive complexity
- **Standards violations** — naming conventions, coding standards
- **Incorrect interface specs** — mismatched parameter number/type/order
- **Security vulnerabilities** — buffer overflows
- **Test coverage gaps** — missing tests for an acceptance criterion

---

## 3.2 Feedback and Review Process

### 3.2.1 Benefits of Early Stakeholder Feedback (K1 — identify)

- Prevents misunderstandings about requirements
- Changes understood and implemented earlier
- Helps dev team focus on **highest-value features**
- Focuses on features with **most positive impact on risks**
- Avoids costly rework, missed deadlines, project failure
- Prevents delivering something stakeholders don't actually want

---

### 3.2.2 Review Process Activities (K2 — summarise)

*(Based on ISO/IEC 20246)*

| Activity | What happens |
|----------|-------------|
| **Planning** | Define scope, purpose, work product, quality characteristics, areas of focus, exit criteria, effort, timeframes |
| **Review Initiation** | Ensure everyone is prepared — access to work product, roles understood, materials distributed |
| **Individual Review** | Each reviewer independently assesses quality, identifies anomalies, recommendations, questions using review techniques |
| **Communication & Analysis** | Anomalies discussed and analysed — decide status, ownership, actions (typically in review meeting) |
| **Fixing & Reporting** | Defect reports created → corrective actions → exit criteria checked → work product accepted → results reported |

> ⚠️ Anomalies identified ≠ always defects — they require analysis and discussion.

---

### 3.2.3 Roles and Responsibilities in Reviews (K1 — recall)

| Role | Responsibility |
|------|---------------|
| **Manager** | Decides what to review; provides resources (staff, time) |
| **Author** | Creates and **fixes** the work product under review |
| **Moderator** (facilitator) | Ensures effective review meetings; mediation, time management, safe environment |
| **Scribe** (recorder) | Records anomalies, decisions, new findings during the review meeting |
| **Reviewer** | Performs the review (project member, SME, or other stakeholder) |
| **Review Leader** | Takes overall responsibility; decides who is involved, when/where review occurs |

> 🔑 In an **inspection**, the author **cannot** act as review leader or scribe.

---

### 3.2.4 Review Types (K2 — compare and contrast)

| Type | Formality | Led by | Key Objectives |
|------|-----------|--------|---------------|
| **Informal Review** | Lowest | Anyone | Detect anomalies; no formal process or documented output |
| **Walkthrough** | Low-Medium | **Author** | Educate reviewers, build confidence, generate ideas, gain consensus, detect anomalies |
| **Technical Review** | Medium | **Moderator** (technically qualified reviewers) | Gain consensus on technical problems, make decisions, detect anomalies, evaluate quality |
| **Inspection** | Highest | **Review Leader** (not author) | Find **maximum** anomalies; collect metrics; improve SDLC; author ≠ leader or scribe |

**Increasing formality:** Informal → Walkthrough → Technical Review → Inspection

---

### 3.2.5 Success Factors for Reviews (K1 — recall)

- Clear objectives and **measurable exit criteria** (evaluation of participants should never be an objective)
- Appropriate review type for the objectives and work product
- Reviews on **small chunks** to maintain concentration
- Feedback provided to stakeholders and authors
- Adequate preparation time for participants
- **Management support** for the review process
- Reviews as part of **organisational culture** (learning/improvement)
- Adequate training for all participants
- Facilitated meetings

---

## 📝 Exam Quick-Check

- What is the difference between **static testing and dynamic testing**? (at least 4 differences)
- List **5 work products** that can be examined by static testing.
- What types of defects are **easier to find via static testing**?
- What are the **5 review process activities** (in order)?
- What are the **6 review roles** and what does each do?
- What are the **4 review types** ordered from least to most formal?
- What makes an **inspection** different from other review types?
- List **5 success factors** for reviews.
