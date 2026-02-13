<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-12LPWFYSG2"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-12LPWFYSG2');
</script>

---
title: DeepSeek V4 Tutorial
description: How to use DeepSeek V4 via API and local deployment
---

# DeepSeek V4 Tutorial

## Method 1: API

```python
import openai
client = openai.OpenAI(
    api_key="your-key",
    base_url="https://api.deepseek.com/v1"
)
```

## Method 2: Local

```bash
ollama run deepseek-v4
```

## Hardware Requirements

| Setup | VRAM |
|-------|------|
| 8x A100 80G | Smooth |
| 4x H100 80G | Recommended |

---

*Usage guide based on V3 patterns.*