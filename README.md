# Taros.ai

An AI-powered chatbot platform that helps businesses deploy intelligent support assistants with document understanding, semantic search, and embeddable widgets.

Built to make AI support accessible – configure your bot, connect your knowledge base, and embed it anywhere in minutes.

---

## 💡 What is Taros?

- **Smart Document Search**: Upload PDFs or crawl websites – Taros automatically indexes content and retrieves relevant information when users ask questions.

- **Embeddable Anywhere**: Drop a chat widget on your website (bubble or inline mode) with just a single line of code.

- **Multi-Bot Management**: Create multiple chatbots with different personalities, knowledge bases, and configurations – all from one dashboard.

- **Image Understanding**: Users can share screenshots or photos, and Taros extracts text and context to provide better answers.

- **Developer-Friendly**: Simple TypeScript SDK and REST API for seamless integration into your existing stack.

---

## 🚀 Getting Started

### TypeScript SDK

```bash
npm install @taros-ai/sdk
```

```typescript
import { createTarosClient } from '@taros-ai/sdk'

const client = await createTarosClient({
  apiKey: 'your-bot-api-key',
  botId: 'your-bot-id'
})

const response = await client.ask("What's your refund policy?")
console.log(response.message)

// Streaming support
for await (const chunk of client.askStream('How do I get started?')) {
  process.stdout.write(chunk.value)
}
```

### Embed the Widget

```html
<script src="https://widgets.taros.ai/loader.js"></script>
<script>
  window.TarosChat?.('init', {
    botId: 'your-bot-id',
    mode: 'bubble',
    position: 'bottom-right',
    theme: {
      brandColor: '#2563eb',
      mode: 'light'
    }
  })
</script>
```

### REST API

```bash
curl -X POST https://api.taros.ai/bots/{botId}/chat \
  -H "Authorization: Bearer YOUR_BOT_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"message": "Hello!"}'
```

---

## 👥 Who is Taros for?

- **SaaS Companies**: Add AI support to your product without building from scratch
- **Startups**: Get production-ready chatbots in minutes, not months
- **Support Teams**: Reduce ticket volume with intelligent self-service
- **Developers**: Clean APIs that integrate seamlessly with existing tools

---

## 📫 Get Started

Visit [**taros.ai**](https://taros.ai) to create your first bot.

Questions? Reach out at [contact@taros.ai](mailto:contact@taros.ai)

---

© 2025 Taros.ai
