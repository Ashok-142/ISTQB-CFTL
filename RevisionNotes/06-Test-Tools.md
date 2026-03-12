# Chapter 6 — Test Tools
#ISTQB #CTFL #Chapter6

> ⏱ 20 minutes | [[00-INDEX|← Back to Index]]

---

## Keywords (must know K1)
`test automation`

---

## 6.1 Tool Support for Testing (K2 — explain)

Test tools support and facilitate many test activities:

| Tool Category | What it supports |
|--------------|-----------------|
| **Test management tools** | Management of SDLC, requirements, tests, defects, configuration |
| **Static testing tools** | Reviews and static analysis |
| **Test design & implementation tools** | Generation of test cases, test data, test procedures |
| **Test execution & coverage tools** | Automated test execution and coverage measurement |
| **Non-functional testing tools** | Performance, security, usability testing (often impossible to do manually) |
| **DevOps tools** | Delivery pipeline, workflow tracking, automated builds, CI/CD |
| **Collaboration tools** | Communication |
| **Deployment/scaling tools** | Virtual machines, containerisation |

> 💡 Even a spreadsheet is a test tool in the context of testing.

---

## 6.2 Benefits and Risks of Test Automation (K1 — recall)

> ⚠️ Simply acquiring a tool does NOT guarantee success. Effort is needed for introduction, maintenance, and training.

### ✅ Benefits of Test Automation:

- **Time saved** — reduces repetitive manual work (regression tests, test data entry, results comparison, coding standards checks)
- **Consistency and repeatability** — prevents simple human errors; tests derived and executed the same way every time
- **Objective assessment** — coverage measures, complex calculations humans can't easily do
- **Better information access** — statistics, graphs, aggregated data about progress, failure rates, execution duration
- **Earlier defect detection** — reduced execution times → faster feedback → faster time to market
- **More time for testers** — design new, deeper, more effective tests

### ❌ Risks of Test Automation:

- **Unrealistic expectations** about functionality, ease of use, and benefits
- **Inaccurate estimations** of time/cost/effort for tool introduction, script maintenance, process change
- **Using automation when manual is more appropriate**
- **Over-reliance on tools** — ignoring human critical thinking
- **Vendor dependency** — company goes out of business, tool retired, sold, or poor support
- **Open-source risks** — project abandoned, no further updates, frequent component updates required
- **Incompatibility** — automation tool not compatible with development platform
- **Unsuitable tool** — doesn't comply with regulatory requirements or safety standards

---

## 📝 Exam Quick-Check

- List **6 categories of test tools** and what each supports.
- List **4 benefits** of test automation.
- List **4 risks** of test automation.
- What is the key message about simply **acquiring a tool**?
