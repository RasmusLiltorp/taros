# Taros.ai

An AI-powered chatbot platform that helps businesses deploy intelligent support assistants with document understanding, semantic search, and embeddable widgets.

Built to make AI support accessible – configure your bot, connect your knowledge base, and embed it anywhere in minutes.

---

## 💡 What is Taros?

- **Smart Document Search**: Upload PDFs or crawl websites – Taros automatically indexes content and retrieves relevant information when users ask questions.

- **Embeddable Anywhere**: Drop a chat widget on your website (bubble or inline mode) with just a few lines of code.

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

## ✨ Features

**Document & Knowledge Management**
- Crawl entire websites or upload documents (PDF, Markdown, etc.)
- Automatic indexing with semantic search
- Link multiple knowledge sources to each bot
- Track ingestion jobs with real-time status updates

**Customizable Bots**
- Configure personality with custom system prompts
- Fine-tune response style (temperature, length, etc.)
- Enable citations and follow-up question suggestions
- Multi-tenant with organization-based access control

**Image Processing**
- OCR text extraction from screenshots
- Optional vision model analysis for visual context
- Async processing for performance

**Developer Experience**
- TypeScript SDK with full type safety
- REST API with streaming support
- Session management built-in
- Comprehensive error handling

**Security & Reliability**
- Bot-specific API keys with granular permissions
- Rate limiting and abuse prevention
- CAPTCHA protection for public-facing widgets
- Session-based conversation persistence

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
