# Brief sample — Prepaid API vs chat + long-context (oficial)

**SKU:** R$ 50 · ROUND1 (sample gratuito — piloto)  
**Data:** 2026-09-05 ~18:52 America/Sao_Paulo  
**Fontes oficiais (só estas):**  
- https://x.ai/pricing (consultado nesta data via fetch HTTP)  
- https://docs.x.ai/docs  
- https://docs.x.ai/developers/models  
- https://docs.x.ai/console/billing  

> Produzido localmente (API credit US$ 0.00; sem top-up; Grok browser não re-tentado nesta rodada). Sem inventar model IDs nem preços.

## Ângulo 1 — Dois produtos, dois caixas

| Canal | O que é | Como paga | Fonte |
|-------|---------|-----------|-------|
| Chat consumer (grok.com / X) | Free · SuperGrok · SuperGrok Plus | Assinatura mensal US$ 0 / 30 / 100 | https://x.ai/pricing |
| API (api.x.ai) | Texto, Imagine, Voice, Build | **Prepaid credits** (ou invoice enterprise) | https://docs.x.ai/console/billing |

**Heavy/consumer ≠ API.** Assinar SuperGrok **não** enche o Credit balance do console. Com Credit **US$ 0.00**, requests API falham até prepaid (ou Luiz autorizar top-up).

## Ângulo 2 — Prepaid: regras que evitam surpresa

Fonte: https://docs.x.ai/console/billing

- Compra antecipada em Billing → API spend management; uso desconta do saldo.  
- Auto top-up: dispara abaixo de limiar; **mínimo US$ 25** por top-up; teto mensal configurável; avisos em 80% do limite e no último de 5 top-ups / 24h.  
- Invoiced billing: **desligado por padrão** (limite US$ 0) → só prepaid; pedido via sales@x.ai / contato na página Billing.  
- Guest Checkout: docs dizem compra prepaid **só via Guest Checkout** (requisito regulatório atual).  
- Transferência bancária: 2–3 dias úteis até crédito.  
- Estado missão local: **sem top-up** até Luiz.

## Ângulo 3 — Long-context: a faixa ≥200k

Fonte: https://docs.x.ai/developers/models

Pedidos cujo **prompt** atinge o limiar (≥200k tokens) cobram a **faixa alta em todos os tokens** da request.

| Modelo | Context | In / Out (&lt;200k) | In / Out (≥200k) |
|--------|---------|---------------------|-------------------|
| `grok-4.6` | 500k | US$ 2.00 / 6.00 | US$ 4.00 / 12.00 |
| `grok-4.5` | 500k | US$ 2.00 / 6.00 | US$ 4.00 / 12.00 |
| `grok-4.3` | 1M | US$ 1.25 / 2.50 | US$ 2.50 / 5.00 |
| `grok-4.20-*-0309` (reasoning / non / multi-agent) | 1M | US$ 1.25 / 2.50 | US$ 2.50 / 5.00 |
| `grok-build-0.1` | 256k | US$ 1.00 / 2.00 | US$ 2.00 / 4.00 |

Cached input também sobe na faixa longa (ex. `grok-4.6`: US$ 0.50 → US$ 1.00 / 1M). Reabrir a tabela oficial antes de orçar.

## Ângulo 4 — Qual stack pedir (docs)

Fonte: https://docs.x.ai/docs · https://docs.x.ai/developers/models

| Necessidade | Caminho oficial | Nota |
|-------------|-----------------|------|
| Code / chat texto | **Grok 4.6** (`grok-4.6`) | “most intelligent and fastest”; cut-off **2026-02-01** |
| Coding agentic / Build | Code API / Grok Build | early access na página docs |
| Apps multi-turn + tools | Responses API | base `https://api.x.ai/v1` |
| Imagem | Imagine Image **2.0** | US$ 0.04 / image |
| Vídeo | Imagine Video **1.5** | US$ 0.080 / sec |
| Voz | Grok Voice API | S2S / STT / TTS na tabela models |
| Eventos em tempo real | Web Search / X Search tools | sem tools = sem realtime |

Aliases: `` e `-latest` migram; pin `-` para reprodutibilidade (docs Models).

## Ângulo 5 — Checklist freela / orçamento

1. Separar **assinatura chat** vs **prepaid API** (dois caixas).  
2. Se Credit = US$ 0 → chat web / entregável local; **sem top-up** sem ordem.  
3. Orçar prompt longo: verificar se passa **200k** (dobra faixa).  
4. Confirmar model ID e preço em https://docs.x.ai/developers/models no dia do contrato.  
5. PIX BRL → LUIZ; ledger com nome do arquivo EMV (`pix_copia_cola_*` / `qr_*`).

## Como comprar o brief pago (não este sample)

Ver `OFERTA.md` · Pages https://ziuluiziul.github.io/round1-xai/ · PIX estoque `/workspace/pix-clean/out/` (R$10=`_4`, R$50=`_2`, R$100=`_0`/`_3`).
