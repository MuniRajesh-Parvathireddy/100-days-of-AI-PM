# 📅 Day 6 – Prompt Engineering Basics for Product Managers  
Part of the #30DaysOfAIProductManagement Series by [Rajesh Munirajesh](https://www.linkedin.com/posts/pmrajesh_prompt-pm-basic-activity-7344940228962328576-uiU0)

---

## 📌 Overview

On Day 6, I explored how **Prompt Engineering** can enhance the productivity and creativity of Product Managers (PMs) using large language models (LLMs) like **GPT-4** and **Gemini 1.5**.

This day focused on building **prompting intuition** and learning how to **communicate effectively with LLMs** to:
- Speed up product discovery
- Simulate customer personas
- Rapidly generate ideas, features, and roadmaps
- Conduct market research using AI

---

## 🔍 Key Concepts Covered

### 🧠 Types of Prompting
- **Zero-shot prompting** – No example needed. Just the instruction.
- **Few-shot prompting** – Giving a few examples to guide the model.
- **Chain-of-thought (CoT)** – Asking the model to explain reasoning step-by-step.
- **Role-based prompting** – Instructing the model to take on a specific role, like “Act as a Product Manager…”

### 🎯 Prompt Engineering for PMs
| Use Case                          | Example Prompt |
|----------------------------------|----------------|
| Feature Ideation                 | “Suggest 3 new features for a budgeting app targeting Gen Z” |
| Persona Simulation               | “Act as a 28-year-old working mom using a mental wellness app” |
| Competitor Analysis              | “Compare Swiggy vs. Zomato in terms of user experience” |
| Empathy Mapping                  | “What would frustrate a user with disabilities when using a shopping app?” |
| Market Research                  | “List pros and cons of launching a sustainable fashion app in Tier 2 cities in India” |

---

## 💡 Prompt Templates (see `prompt_templates.txt`)
- Designed templates that I can reuse across multiple PM tasks
- Fine-tuned prompts using few-shot learning to make outputs more accurate and reliable

---

## 📂 Files in This Folder

---

## 🔬 Sample Prompt Output (from `llm_outputs.json`)
```json
{
  "prompt": "Act as a PM. Suggest 3 new features for a budgeting app for Gen Z.",
  "output": [
    "1. Social Savings Challenges with friends",
    "2. AI-based Spending Personality Quiz",
    "3. Daily Finance Streaks & Rewards Gamification"
  ]
}