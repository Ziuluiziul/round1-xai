# Brief sample — Grok Build + tools API (oficial)

**SKU:** R$ 50 · ROUND1 (sample gratuito — piloto)  
**Data:** 2026-09-05 ~20:44 America/Sao_Paulo  
**Fontes oficiais (só estas):**  
- https://x.ai/pricing (consultado nesta data via fetch HTTP)  
- https://docs.x.ai/docs · https://docs.x.ai/build/overview  
- https://docs.x.ai/developers/models · https://docs.x.ai/developers/models/grok-build-0.1  
- https://docs.x.ai/developers/pricing · https://docs.x.ai/console/billing  

> Produzido localmente (API credit US$ 0.00; sem top-up). Sem inventar model IDs nem preços.

## Ângulo 1 — Dois caminhos para “Build”

| Caminho | O que é | Como paga | Fonte |
|---------|---------|-----------|-------|
| Consumer Grok Build | Coding agent (TUI / headless / ACP) | Assinatura: SuperGrok lista **Grok Build access**; Free/Plus conforme tabela | https://x.ai/pricing · https://docs.x.ai/build/overview |
| API Code / Build | Modelos na API (`grok-4.6` recomendado p/ code; também `grok-build-0.1`) | **Prepaid credits** no console | https://docs.x.ai/build/overview · https://docs.x.ai/developers/models |

**Heavy/consumer ≠ API.** SuperGrok **não** enche Credit balance. Com Credit **US$ 0.00**, requests API falham até prepaid (ou Luiz autorizar top-up).

## Ângulo 2 — Instalar e rodar (docs Build)

Fonte: https://docs.x.ai/build/overview

- Install: `curl -fsSL https://x.ai/cli/install.sh | bash` (ou PowerShell `irm https://x.ai/cli/install.ps1 | iex`).  
- Interativo: `cd seu-projeto && grok` (auth browser; ou `export XAI_API_KEY=...`).  
- Headless: `grok -p "Explain this codebase"` · `--output-format streaming-json`.  
- Custom model em `~/.grok/config.toml`; inspecionar com `grok inspect`; trocar com `-m` ou `/model`.  
- O modelo que **powers Grok Build** na API (docs) é **`grok-4.6`** via Responses `https://api.x.ai/v1`.

## Ângulo 3 — `grok-build-0.1` (ficha oficial)

Fonte: https://docs.x.ai/developers/models/grok-build-0.1

| Campo | Valor oficial |
|-------|----------------|
| Model name | `grok-build-0.1` |
| Aliases | `grok-code-fast-1`, `grok-code-fast`, `grok-code-fast-1-0825` |
| Context | 256k |
| Modalities | text, image → text |
| Function calling / structured / reasoning | Yes |
| Batch API | **Not supported** |
| In / cached / out (&lt;200k) | US$ 1.00 / 0.20 / 2.00 por 1M |
| In / cached / out (≥200k) | US$ 2.00 / 0.40 / 4.00 por 1M |
| Rate limits | 37 req/s · 10M tokens/min |
| Regions | us-east-1, us-west-2 |

Docs models: para **code em geral**, preferir **Grok 4.6** (“most intelligent and fastest”); Build 0.1 é a linha dedicada listada com aliases code-fast.

## Ângulo 4 — Tools: token + invocação

Fonte: https://docs.x.ai/developers/pricing

Pedidos com tools server-side cobram **tokens** (input / reasoning / completion / image / cached) **+** invocações:

| Tool | Nomes | Custo / 1k calls |
|------|-------|------------------|
| Web Search | `web_search` | US$ 5 |
| X Search | `x_search` | US$ 5 |
| Code Execution | `code_execution` / `code_interpreter`† | US$ 5 |
| Image Generation | `image_generation` | taxas Imagine |
| File Attachments | `attachment_search` | US$ 10 |
| Collections Search | `collections_search` / `file_search`† | US$ 2.50 |
| view_image / view_x_video | — | só tokens (sem fee de invocação) |
| Remote MCP | MCP server | só tokens |

† No gRPC/Python xAI SDK, `code_interpreter` e `file_search` **não** são suportados (usar nomes nativos). Agent decide quantas tools → custo escala com complexidade.

## Ângulo 5 — Batch / Priority / storage (orçamento)

Fonte: https://docs.x.ai/developers/pricing

- **Batch:** desconto **20%** em `grok-4.3` e família `grok-4.20-*-0309`; **sem** desconto batch listado para `grok-4.6` / `grok-4.5` / `grok-build-0.1`. Imagine/vídeo no Batch = taxa standard.  
- **Priority Processing:** **2×** em todos os tipos de token; só Chat Completions / Responses; não Imagine/vídeo/Batch. Só cobra 2× se a response confirmar `"service_tier": "priority"`.  
- Storage: files US$ 0.025 / GiB / day · collections US$ 0.10 / GiB / day · download US$ 0.20 / GiB.  
- Usage guideline (Responses, pré-geração): fee US$ 0.05 / request.

## Ângulo 6 — Planos consumer (Build + Imagine)

Fonte: https://x.ai/pricing (Individual)

| Plano | Preço | Destaques oficiais relevantes |
|-------|-------|-------------------------------|
| Free | US$ 0/mês | limites generosos; web+X search; Voice; Connectors |
| SuperGrok | US$ 30/mês | Grok 4.6 · **Grok Build access** · Imagine image/video · higher limits |
| SuperGrok Plus | US$ 100/mês | tudo SuperGrok + **1080p video** · usage bem maior · priority peak |

Lite / Heavy / Business / Enterprise aparecem na tabela comparativa; preços Lite/Heavy **não** extraídos com certeza nesta consulta — reabrir https://x.ai/pricing.

## Checklist freela / orçamento Build

1. Separar **assinatura chat/Build consumer** vs **prepaid API**.  
2. Credit = US$ 0 → CLI/API só se key+crédito; senão entregável local / chat free. **Sem top-up** sem Luiz.  
3. Orçar tools: tokens + (calls/1000)×tabela.  
4. Pin model ID (`grok-4.6` vs `grok-build-0.1`) e reabrir pricing no dia do contrato.  
5. PIX BRL → LUIZ; ledger com arquivo EMV (`_4`=R$10, `_2`=R$50, `_0`/`_3`=R$100; R$20 = `round1/pix_r20_*`).

## Como comprar o brief pago (não este sample)

Ver `OFERTA.md` · Pages https://ziuluiziul.github.io/round1-xai/ · PIX `/workspace/pix-clean/out/` (texto CRC &gt; PNG).
