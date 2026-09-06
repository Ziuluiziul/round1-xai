# Brief sample — Imagine API: imagem + vídeo (oficial)

**SKU:** R$ 50 · ROUND1 (sample gratuito — piloto)  
**Data:** 2026-09-05 ~22:51 America/Sao_Paulo  
**Fontes oficiais (só estas):**  
- https://x.ai/pricing (consultado nesta data via fetch HTTP)  
- https://docs.x.ai/docs · https://docs.x.ai/developers/model-capabilities/imagine  
- https://docs.x.ai/developers/models · https://docs.x.ai/developers/pricing  
- https://docs.x.ai/developers/advanced-api-usage/batch-api  
- https://docs.x.ai/console/billing  

> Produzido localmente (API credit US$ 0.00; sem top-up). Sem inventar model IDs nem preços.

## Ângulo 1 — Consumer Imagine ≠ Imagine API

Fonte: https://x.ai/pricing · https://docs.x.ai/developers/model-capabilities/imagine

| Canal | O que a página oficial diz | Billing |
|-------|----------------------------|---------|
| Chat Grok (Free / SuperGrok / Plus) | Free: limites generosos; SuperGrok US$30: image + video generation; SuperGrok Plus US$100: 1080p video + uso bem maior em Chat / Imagine / Voice / Build | Assinatura mensal — **não** enche Credit balance da API |
| Imagine API (`api.x.ai`) | Generate / edit image (até 5 refs); video T2V / I2V / edit / extension; Files API | Prepaid Credit balance (console) |

**Regra ROUND1:** com Credit **US$ 0.00**, entregar via chat web / artefato local. Sem top-up sem Luiz.

## Ângulo 2 — Modelos e preços Imagine (API)

Fonte: https://docs.x.ai/developers/models · https://docs.x.ai/developers/pricing

| Modelo | Preço publicado |
|--------|-----------------|
| `grok-imagine-image` | US$ **0.02** / image |
| `grok-imagine-image-2.0` | US$ **0.04** / image |
| `grok-imagine-image-quality` | US$ **0.05** / image |
| `grok-imagine-video` | US$ **0.050** / sec |
| `grok-imagine-video-1.5` | US$ **0.080** / sec |

Docs: preço de imagem é **flat por imagem** (prompt length não muda a taxa). Edição de imagem cobra **input image + output image**. Vídeo: por segundo; duração e resolução afetam o total (pricing page).

Recomendação na página de models: Images → **Grok Imagine Image 2.0**; Videos → **Grok Imagine Video 1.5**.

## Ângulo 3 — Capacidades (overview oficial)

Fonte: https://docs.x.ai/developers/model-capabilities/imagine

- **Image generation:** até 10 imagens/request; aspect ratio; resolution; response format.  
- **Image editing:** URL pública ou data-URI; multi-image até **5** sources (compositing / style transfer).  
- **Video:** text-to-video, image-to-video; duração até **15s**; aspect/resolution; async (poll `request_id`).  
- **Video editing** + **video extension** (continua do último frame).  
- **Reference-to-video:** refs influenciam sem forçar 1º frame — docs: requer `grok-imagine-video` (não `…-1.5`).  
- **Files API:** `image_file_id` / `video_file_id` / `reference_image_file_ids`; persist + URL pública opcional.  
- Compliance: SOC 2 Type II; HIPAA Eligible (BAA); GDPR; data residency; SSO/RBAC. Media gerada sob content policy; **não** usada para treino (texto da página Imagine).

## Ângulo 4 — Orçamento rápido (só números oficiais)

Exemplos **ilustrativos** com a tabela acima (sem inventar descontos):

| Cenário | Conta oficial |
|---------|---------------|
| 10 imgs `grok-imagine-image` | 10 × 0.02 = **US$ 0.20** |
| 10 imgs `grok-imagine-image-2.0` | 10 × 0.04 = **US$ 0.40** |
| 10 imgs `grok-imagine-image-quality` | 10 × 0.05 = **US$ 0.50** |
| 1 edit 2.0 (1 in + 1 out) | 0.04 + 0.04 = **US$ 0.08** |
| 12s video `grok-imagine-video` | 12 × 0.050 = **US$ 0.60** |
| 12s video `grok-imagine-video-1.5` | 12 × 0.080 = **US$ 0.96** |
| 15s video 1.5 | 15 × 0.080 = **US$ 1.20** |

Tool `image_generation` em agentic requests: “Imagine API rates” (https://docs.x.ai/developers/pricing). Não misturar com Web Search (US$ 5 / 1k calls).

## Ângulo 5 — Batch + Priority (Imagine)

Fonte: https://docs.x.ai/developers/pricing · batch-api

- Batch API **suporta** image + video generation.  
- Desconto batch (20% em alguns text models: grok-4.3 / 4.20-*) **não** se aplica a image/video — “billed at standard rates”.  
- Priority Processing (2×): Chat Completions / Responses only — **não** image, video, nem Batch.  
- URLs de resultado batch de image/video: expiram em **1 hora** (release notes / batch docs).

## Ângulo 6 — Multi-modelo: quando Imagine vs texto vs Voice

| Precisa de… | Caminho oficial |
|-------------|-----------------|
| Code / chat texto | Grok **4.6** |
| Imagens | Imagine Image **2.0** (API) ou Imagine no chat (plano) |
| Vídeo 1080p (consumer) | SuperGrok **Plus** (pricing) |
| Vídeo API | Imagine Video **1.5** (ou `grok-imagine-video` p/ reference-to-video) |
| Voz realtime / TTS / STT | Voice API (brief-8) |
| Volume assíncrono texto | Batch (desconto só text models listados) |

## Ângulo 7 — Checklist compra ROUND1

1. Tema = Imagine/API budget / consumer vs prepaid / video duração.  
2. PIX LUIZ: R$10=`pix_copia_cola_4`, R$50=`_2`, R$100=`_0` ou `_3` (texto EMV > PNG).  
3. Sem cold-DM; sem top-up API.  
4. Entrega: brief com links oficiais (este sample é o formato).

## Disclaimer

Preços e model IDs mudam. Reabrir https://docs.x.ai/developers/models e https://x.ai/pricing antes de orçar. Este sample não é fatura.
