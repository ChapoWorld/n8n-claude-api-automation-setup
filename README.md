# 🤖 N8N & Make Automations: Reduce Claude API Costs

Running high-volume workflows (like processing emails, summarizing articles, or generating SEO content) using Anthropic's official API can become prohibitively expensive.

This repository explains how to bypass Anthropic's Tier 1 rate limits and lower your token costs using a Custom Drop-in Endpoint.

## 🔗 The Drop-in Replacement
You don't need to change your workflow logic. You simply change the API URL.

👉 **[Get your Custom Base URL and API Token here](https://claude.sell.app/product/claude-api-tokens)**

## ⚙️ How to use in N8N (HTTP Request Node)

Instead of using the native Anthropic node (which restricts base URLs), use the standard **HTTP Request Node**:

* **Method:** `POST`
* **URL:** `YOUR_CUSTOM_BASE_URL/messages`
* **Headers:**
  * `x-api-key`: `YOUR_PURCHASED_KEY`
  * `anthropic-version`: `2023-06-01`
  * `content-type`: `application/json`
* **Body (JSON):**
```json
  {
    "model": "claude-3-5-sonnet-20241022",
    "max_tokens": 1024,
    "messages": [
      {"role": "user", "content": "={{ $json.inputText }}"}
    ]
  }

This setup provides Enterprise-level stability, zero multi-layer routing, and massive cost savings for high-volume automated tasks.
