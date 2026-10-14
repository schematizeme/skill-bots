# Changelog — schematize-bots

Todas as mudanças relevantes deste pacote, no formato [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/),
com versionamento [SemVer](https://semver.org/lang/pt-BR/).

## [0.1.0] — 2026-10-14
Primeira versão. Bot é um processo com credencial de longa vida, entrada pública e efeito externo em
massa (mensagem em canal real, menção a todos): token commitado, webhook sem assinatura, `@everyone`
ecoado de entrada de usuário e loop de envio sem tratamento de 429 são incidentes recorrentes e não
tinham dono nem gate no catálogo.

### Adicionado
- `SKILL.md` com 14 pisos e fronteiras com api, ai, iam, payments, infra/docker, observability, git, incident.
- `references/`: `credenciais-e-token`, `transporte-e-assinatura`, `prazo-fila-rate-limit`, `comandos-intents-permissoes`, `moderacao-entrada-privacidade`, `ambientes-e-efeito-externo`, `stack-versoes` (anexo volátil com fonte e data).
- `scripts/check-bot.sh` + `check-bot.test.sh`: 6 regras estáticas (token literal, webhook sem assinatura, eco sem allowed_mentions, envio em loop sem 429, intent privilegiada sem justificativa, setWebhook sem secret_token), waiver `bot-ok:`.
- Comandos: `bot-help`, `bot-load`, `bot-new`, `bot-review`, `bot-webhook`, `bot-commands`, `bot-moderation`, `bot-claude`, `bot-handoff`, `bot-cc`.
