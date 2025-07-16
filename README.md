# Taros.ai

Taros is a modular AI-powered support platform designed to make intelligent assistants easy to configure, secure to operate, and powerful enough to integrate vision, documents, and real-time chat. 

It lets your users get smart, context-aware answers from their own documents, images, and data – in real time.

Whether you're a startup, dev team, or hobbyist, Taros helps you spin up your own AI support bot in minutes – using either a few lines of code with an API key, or our plug-and-play tools.

---

## 💡 What can Taros do?

- 💬 Route any incoming question through a configurable AI backend. Taros currently uses GPT-4o by default, but is designed to support any LLM (e.g. Claude, Mistral, or your own model) through a pluggable architecture.

- 🧠 Upload and sync documents (PDF, Markdown, etc.), and Taros will embed and index them for semantic search. When a user asks a question, relevant snippets are automatically injected into the AI prompt.

- 🖼 When a user sends a screenshot or photo, Taros extracts the text using OCR, and can optionally pass both the text and the raw image to the AI model for visual understanding.

- 🔄 Some operations (like vision processing or large document searches) take time. Taros supports async processing with callback URLs, so your client can continue without blocking and receive results once ready.

- 🔐 Taros uses layered authentication: API keys for infrastructure-level security, and JWTs for bot-specific identity. This makes it safe to use in both server-side code and browser-based apps.

---

## 🧠 How it works

When your app or bot sends a request, Taros orchestrates the flow:

1. Retrieves the bot's configuration
2. (Optional) Searches relevant documents
3. (Optional) Processes any attached images
4. Sends the compiled context to the AI model
5. Returns or pushes the response via callback
   
---

## ⚙️ Architecture

Taros is built as a microservice system, orchestrated via a central controller that coordinates chat requests across modular services:

- **Orchestrator**: Core logic and routing
- **AI Service**: Handles model interactions, fallback, and OCR/vision integration *(currently only GPT)*
- **Training Service**: Embeds and searches for documents
- **OCR Service**: Extracts text from uploaded images
- **Account Service**: Stores bot configs and billing data
- **Configuration Layer**: Caches bot settings for ultra-fast access, even at scale
- **Callback Support**: Lets long-running operations finish in the background


Services communicate via HTTPS with API key authentication and support both synchronous and async patterns via callbacks.

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
- [**taros-public-api**](https://github.com/RasmusLiltorp/taros-public-api) – Lightweight API gateway that connects clients to the orchestrator service.

The rest of the system is private but modular. You can self-host parts or connect via the public API.

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
