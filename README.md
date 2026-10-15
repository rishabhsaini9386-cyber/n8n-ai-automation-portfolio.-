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
---

## 📰 Daily News Digest Bot

**Problem it solves:** Business owners need to stay updated with industry news but rarely have time to read multiple sites. This bot collects the top headlines every day, summarizes them in simple language, and delivers the digest straight to Telegram.

**How it works:** A scheduled trigger reads headlines from an RSS feed, combines the top 5 into a single list, and an AI model writes a short friendly digest which is sent as a Telegram message.

**Skills demonstrated:** RSS data fetching, data aggregation, AI summarization, real-world app integration (Telegram), handling output formatting between apps.

## 📊 Case Study: Inquiry Automation for a Coaching Center (Demo Project)

**The scenario:** A coaching center receives many inquiries from students and parents. With so many coming in, some get missed, and the owner spends a lot of time reading and sorting them by hand.

**What I built:** An automation in n8n that works like this:
1. Every inquiry arrives through a single web form.
2. An AI classifier sorts it as **Urgent**, **Normal**, or **Spam**.
3. The AI writes a polite draft reply for the owner.
4. Every inquiry, with its category and draft reply, is saved to Google Sheets.
5. Only **urgent** inquiries trigger an instant Telegram alert to the owner.
6. If the AI step fails, a fallback alert still notifies the owner, so no inquiry is silently lost.

**A problem I had to solve:** When connecting Google Sheets, sign-in kept failing with "Access blocked". I traced it to my Google Cloud app being in testing mode, where only approved test users can sign in. Adding my account as a test user fixed it. Later, Telegram rejected my messages because the AI's Markdown symbols broke its formatting; I fixed it by asking the AI for plain text and setting the message format to HTML.

**The outcome (tested with sample inquiries):** Urgent, normal, and spam messages were each routed correctly. In this setup no inquiry is missed, every one is recorded in a single place, and the owner is alerted instantly only when something needs attention, which saves time on sorting.

**Skills used:** Form Trigger, AI Text Classifier, conditional routing, Google Sheets (OAuth), Telegram integration, error-handling fallback, debugging.
