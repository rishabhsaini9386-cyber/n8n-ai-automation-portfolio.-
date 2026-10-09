# n8n AI Automation Portfolio

A collection of AI automation workflows built with n8n, covering lead qualification, content automation, and customer support.

---

## 🎯 Lead Qualifier Bot

**Problem it solves:** Businesses receive many leads, but not all are worth equal sales effort. This bot chats with incoming leads, asks about their company size and budget, and classifies them as Hot, Warm, or Cold, so sales teams can prioritize high-value prospects first.

**How it works:** An AI agent collects lead details conversationally, then calls a scoring sub-workflow that applies business rules (employee count, budget) to classify the lead. An error-handling fallback keeps the conversation going even if a step fails.

**Skills demonstrated:** Conditional routing (Switch), AI Agent with tool-calling, sub-workflow architecture, error handling.

---

## 📝 Content Automation Bot

**Problem it solves:** Consistent posting drives audience growth, but business owners are often too busy to write daily. This bot generates a ready-to-publish post every day, independent of the owner's availability.

**How it works:** A scheduled trigger runs daily, picks topics from a content list, and uses AI to generate a post for each one. If generation fails for one topic, the rest continue unaffected.

**Skills demonstrated:** Scheduled automation, batch/list processing (Split Out), AI content generation, fault-tolerant design.

---

## 💬 Support Bot (RAG-powered)

**Problem it solves:** Slow support replies can cost a sale, since customers may change their mind while waiting. This bot gives instant, accurate answers from company documents and escalates to a human only when it doesn't know the answer.

**How it works:** Company FAQs are converted into vector embeddings (numeric representations of meaning), so the AI finds the most relevant answer even when documents cover similar topics. If no good match is found, it escalates instead of guessing.

**Skills demonstrated:** RAG (Retrieval-Augmented Generation), vector embeddings, multi-tool agents, escalation handling.

---

## 🤖 Universal Business Assistant

**Problem it solves:** Customers often switch between support questions and buying interest in the same conversation. This assistant handles both in one chat: it answers policy questions from the knowledge base and qualifies leads, while remembering the earlier conversation.

**How it works:** A single AI agent with conversation memory chooses between three tools (lead scoring, knowledge base search, human escalation) depending on what the customer asks.

**Skills demonstrated:** Multi-tool AI agent orchestration, conversation memory, clear tool descriptions, sub-workflow integration.

---

## Tools

n8n (self-hosted)
