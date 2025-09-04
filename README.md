# Taros.ai

Taros is a modular AI-powered support platform designed to make intelligent assistants easy to configure, secure to operate, and powerful enough to integrate vision, documents, and real-time chat. 

It lets your users get smart, context-aware answers from their own documents, images, and data – in real time.

Whether you're a startup, dev team, or hobbyist, Taros helps you spin up your own AI support bot in minutes – using either a few lines of code with an API key, or our plug-and-play tools.

---

## 💡 What can Taros do?

- 💬 Route any incoming question through a configurable AI backend. Taros currently uses GPT-4o by default, but is designed to support any LLM (e.g. Claude, Mistral, or your own model) through a pluggable architecture.

- 🧠 Upload and sync documents (PDF, Markdown, etc.), and Taros will embed and index them for semantic search. When a user asks a question, relevant snippets are automatically injected into the AI prompt.

- 🖼 When a user sends a screenshot or photo, Taros extracts the text using OCR, and can optionally pass both the text and the raw image to the AI model for visual understanding.

---

## 🚀 Getting Started

The easiest way to get started is using our [TypeScript SDK](https://github.com/RasmusLiltorp/taros-sdk):

```bash
npm install @taros-ai/sdk
```


## 📦 Example Use Case

```ts
const sdk = await createTarosClient();

await sdk.initialize(); // handles login or headless env automatically

const response = await sdk.ask("What's the refund policy?", {
  botId: "customer-support",
});

console.log(response.message);
```

---

## 🛠️ Open Source Components

These components are public and MIT licensed:

- [**taros-sdk**](https://github.com/RasmusLiltorp/taros-sdk) – Official TypeScript SDK for authentication, chat requests, and configuration.

The rest of the system is private but modular. You can connect to our system via the public API.

---

## 👥 Who is Taros for?

- Companies who want a smart, secure AI support bot without hiring a dev team

- Startups building custom chatbots on top of modern AI models

- Product teams who want to integrate support into their webapp in minutes

- Developers looking for a modular, pluggable way to combine AI, documents, and images

- Non-coders who prefer visual tools and plug-and-play setup

---

## 📫 Questions?

Have a question, found a bug, or want to contribute? Open an issue and let's talk.

Explore features, use cases, and more at [**taros.ai**](https://taros.ai)

---

© 2025 Taros.ai – All rights reserved.
