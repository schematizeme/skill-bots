---
description: schematize-bots — scaffold de bot novo: plataforma, transporte, token, comandos, ambientes e gate antes do primeiro handler
argument-hint: "<plataforma: discord|telegram|slack|whatsapp|matrix> <propósito>"
---

# /bot-new — nasce com o piso, não ganha depois

Alvo: `${ARGUMENTS}`. Leia `references/transporte-e-assinatura.md`, `credenciais-e-token.md` e `ambientes-e-efeito-externo.md`.

1. **Linguagem** do rol por fit + ADR (`schematize-engineering → references/linguagens.md`).
2. **Transporte** por critério (webhook x gateway x polling) e registre em ADR.
3. **Ambientes**: bot e servidor/workspace de teste separados do de prd; `APP_ENV` fail-closed; um token por ambiente, lido do cofre.
4. **Intents/permissões mínimas** declaradas em um arquivo versionado, com justificativa das privilegiadas.
5. **Receptor** com assinatura verificada, ack imediato, fila, dedupe e cliente de saída com tratamento de 429.
6. **Registro de comandos** como script idempotente (`/bot-commands`).
7. **Privacidade**: o que guarda, retenção, opt-out (`/bot-moderation`).
8. **Gate no CI**: `bash .claude/skills/schematize-bots/scripts/check-bot.sh .`; `/bot-claude` para o piso sempre-on.
Mídia (avatar, banner) segue a regra de mídia da casa: nunca por modelo Claude.
