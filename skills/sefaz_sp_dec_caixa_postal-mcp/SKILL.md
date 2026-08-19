---
name: sefaz_sp_dec_caixa_postal-mcp
description: Skill da REST API do SEFAZ SP DEC: Caixa Postal na MCP.AI: 1 endpoint em /api/sefaz_sp_dec_caixa_postal. SEFAZ SP DEC: Caixa Postal, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# SEFAZ SP DEC: Caixa Postal — REST API skill

Você tem acesso à **SEFAZ SP DEC: Caixa Postal** REST API na MCP.AI.

> SEFAZ SP DEC: Caixa Postal, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/sefaz_sp_dec_caixa_postal
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/sefaz_sp_dec_caixa_postal/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"pkcs12_cert":"...","pkcs12_pass":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/sefaz_sp_dec_caixa_postal/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `sefaz_sp_dec_caixa_postal_consultar`

SEFAZ SP DEC: Caixa Postal, consulta em fonte oficial. _(POST /api/sefaz_sp_dec_caixa_postal/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `pkcs12_cert` | string | Sim | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Sim | Parâmetro de consulta "pkcs12_pass". |
| `ignora_nao_lidas` | string | Não | Parâmetro de consulta "ignora_nao_lidas". |
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_sefaz_sp_dec_caixa_postal` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
