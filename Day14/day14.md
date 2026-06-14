# 🚩 AI Job Red Flag Detector

A lightweight, single-file HTML tool that analyzes job descriptions and company information to help job seekers identify red flags before applying.

Built as a static frontend — no frameworks, no dependencies, no backend required.

---

## 📸 Preview

> Analyzes any job posting and outputs:
> - Overall Risk Score (0–100)
> - Categorized red flags with severity ratings
> - Positive signals
> - Risk breakdown by category
> - 5 smart interview questions tailored to the risks

---

## 🚀 Getting Started

### Option 1 — Open directly
Just download `job-red-flag-analyzer.html` and open it in any browser. No setup needed.

### Option 2 — Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/job-red-flag-analyzer.git
cd job-red-flag-analyzer
open job-red-flag-analyzer.html
```

---

## 📁 Project Structure

```
job-red-flag-analyzer/
├── job-red-flag-analyzer.html   # Main file — entire app lives here
└── README.md                    # You are here
```

---

## 🔍 What It Detects

| Category | What's Checked |
|---|---|
| **Requirements** | Unrealistic experience demands, skill overload, contradictory expectations |
| **Culture** | Burnout signals, hustle culture language, work-life balance red flags |
| **Remote Authenticity** | Hidden office requirements, misleading remote claims |
| **Hiring Transparency** | Missing salary info, vague responsibilities, suspicious practices |
| **Company Stability** | Reputation concerns, overclaimed size, growth or layoff indicators |

---

## 🧪 Sample Analysis — FakeCompany

The included file contains a pre-analyzed job posting for a **Software Developer Fresher** role at **FakeCompany**.

| Field | Value |
|---|---|
| Role | Software Developer Fresher |
| Stipend | ₹25,000/month |
| Location | Remote (India/USA) |
| Risk Score | **72 / 100** |
| Verdict | ⚠️ Apply with Caution |

### Top flags identified:
- Missing salary ceiling and no statutory benefits (PF, insurance)
- Software outsourcing model — limits career growth
- Legacy tech stack (.NET, VB.NET, XML)
- Generic, template-style job description
- Dual HQ with Indian pay for US-client work

---

## 🛠️ Built With

- Pure HTML5, CSS3, JavaScript
- No external frameworks or libraries
- Zero build step — open and run

---

## 💡 How to Customize

To analyze a different job posting, open the HTML file and update the relevant sections:

- **Company name** — search and replace the company name string
- **Stipend/Salary** — update the header and interview question #3
- **Risk scores** — adjust the `width` percentage on `.bar-fill` elements
- **Flag descriptions** — edit the `.flag-desc` paragraphs
- **Verdict** — change the `.verdict-badge` text and color class

---

## 📌 Roadmap

- [ ] Input form to paste any JD and auto-analyze via AI API
- [ ] Score history / comparison across multiple JDs
- [ ] Export report as PDF
- [ ] Browser extension version

---

## 🤝 Contributing

Pull requests are welcome. For major changes, open an issue first to discuss what you'd like to change.

---

## 📄 License

[MIT](https://choosealicense.com/licenses/mit/)

---

> Made with ❤️ to help job seekers make smarter decisions.
