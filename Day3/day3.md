# Day 3 – Role-Based Prompting with Claude

## Objective

Learn how assigning different roles (personas) to Claude changes the quality, focus, and perspective of the generated response.

---

## Task Completed

* Read about Role-Based Prompting.
* Asked Claude the same question without a role.
* Asked Claude the same question with a Founder persona.
* Asked Claude the same question with a Developer persona.
* Compared the responses.
* Installed and explored Claude Usage Counter.
* Documented observations and learnings.

---

# Prompt Used

## Scenario

Build an AI-powered task management app for students.

---

## Prompt 1: No Role Assigned

Provide a structured, actionable plan to build an AI-powered task management app for students, covering validation, MVP features, AI integration, go-to-market strategy, and success metrics.

### Output Summary

* General-purpose response.
* Balanced mix of business and technical recommendations.
* High-level roadmap.
* Suitable for beginners.

---

## Prompt 2: Founder Persona

You are a successful SaaS founder who has built and scaled multiple startups from idea to product-market fit.

Provide a structured, actionable plan to build an AI-powered task management app for students.

### Output Summary

* Focused heavily on validation.
* Emphasized customer interviews.
* Prioritized finding product-market fit.
* Recommended lean MVP development.
* Discussed growth strategies and user acquisition.
* Included startup metrics and business milestones.

### Key Takeaway

The Founder persona thinks primarily about users, growth, revenue, and market demand.

---

## Prompt 3: Developer Persona

You are a senior full-stack software developer specializing in scalable web apps and AI-powered products.

Provide a structured, actionable plan to build an AI-powered task management app for students.

### Output Summary

* Detailed technical architecture.
* Suggested technology stack.
* Included database design.
* Discussed APIs and AI integration.
* Covered deployment and scalability.
* Explained implementation roadmap.

### Key Takeaway

The Developer persona focuses on system design, engineering decisions, scalability, and implementation.

---

# Comparison of Responses

| Aspect                 | No Role    | Founder Persona   | Developer Persona        |
| ---------------------- | ---------- | ----------------- | ------------------------ |
| Focus                  | General    | Business & Growth | Technical Implementation |
| Validation Strategy    | Moderate   | Strong            | Moderate                 |
| MVP Planning           | Basic      | Lean MVP          | Feature-Oriented         |
| Technology Stack       | Minimal    | Limited           | Detailed                 |
| AI Integration         | High-Level | Business Value    | Technical Execution      |
| User Acquisition       | Basic      | Detailed          | Moderate                 |
| Scalability Discussion | Minimal    | Business Scale    | Technical Scale          |

---

# Claude Usage Counter Exploration

## Installation

Installed the Claude Usage Counter extension and connected it with Claude.

## Features Explored

* Token usage tracking
* Message usage monitoring
* Remaining usage visibility
* Session analytics
* Daily usage insights

## Observation

The tool helps understand how prompts consume tokens and encourages writing clearer, more efficient prompts.

---


# Learnings

### 1. Role-Based Prompting Improves Response Quality

Assigning a role gives Claude additional context and changes how it approaches the problem.

### 2. Different Roles Produce Different Perspectives

* Founder → Business strategy and growth.
* Developer → Technical architecture and implementation.
* No Role → Generic response.

### 3. Better Prompts Produce Better Outputs

Specific instructions lead to more detailed and actionable answers.

### 4. Persona Selection Matters

The quality of AI outputs can improve significantly when the role matches the task.

### 5. Usage Tracking Is Helpful

Claude Usage Counter provides visibility into prompt efficiency and token consumption.

---

# Conclusion

Day 3 demonstrated the power of Role-Based Prompting. By assigning Founder and Developer personas, Claude generated responses tailored to specific objectives. This exercise highlighted how prompt engineering can influence AI behavior and produce more relevant, actionable outputs.
