# ðŸ•³ï¸ Projeto Caverna

> Disciplina, forÃ§a, fÃ© e progresso num sÃ³ lugar.

Painel pessoal de acompanhamento de rotina com sistema de XP, sequÃªncia de dias, recompensas e diÃ¡rio rÃ¡pido â€” tudo rodando 100% no navegador, sem backend e sem dependÃªncias externas.

---

## âœ¨ Funcionalidades

| Ãrea | O que rastreia |
|---|---|
| ðŸ’» ProgramaÃ§Ã£o | Cursos, prÃ¡tica diÃ¡ria e commits no GitHub |
| ðŸŒ™ JeovÃ¡ | BÃ­blia, oraÃ§Ã£o e reflexÃµes |
| ðŸ“š Estudo escolar | LiÃ§Ãµes, revisÃµes e exercÃ­cios |
| ðŸ’ª Treino | ForÃ§a, postura e mobilidade |
| ðŸ¤Ÿ Libras | Alfabeto, sinais e vocabulÃ¡rio |

**Sistema de jogo:**
- **XP** acumulado por Ã¡rea concluÃ­da, hÃ¡bitos e humor do dia
- **NÃ­veis** a cada 150 XP
- **SequÃªncia** de dias completos seguidos
- **Recompensas** desbloqueadas conforme o progresso diÃ¡rio (10â€“30 min de Instagram + lazer extra)
- **DiÃ¡rio** com registro de vitÃ³rias e planos

---

## ðŸš€ Como usar

1. Abra o arquivo `index.html` direto no navegador â€” nÃ£o precisa de servidor.
2. Preencha seu perfil (nome, idade, altura, peso e lema).
3. Marque as Ã¡reas e hÃ¡bitos do dia.
4. Acompanhe seu XP, nÃ­vel e sequÃªncia no painel.
5. Tudo Ã© salvo automaticamente no `localStorage` do navegador.

> **AtenÃ§Ã£o:** limpar os dados do navegador apaga o histÃ³rico. Use o botÃ£o **Resetar painel** com cuidado.

---

## ðŸ—ï¸ Estrutura do cÃ³digo

```
index.html          â€” arquivo Ãºnico (HTML + CSS + JS)
â”‚
â”œâ”€â”€ CORE_AREAS      â€” 5 Ã¡reas principais com pontos e dicas de inÃ­cio
â”œâ”€â”€ HABITS          â€” 4 hÃ¡bitos de suporte (+5 XP cada)
â”œâ”€â”€ REWARDS         â€” recompensas por faixa de progresso
â”œâ”€â”€ TRAINING        â€” lista de exercÃ­cios com sÃ©ries e dicas
â”‚
â”œâ”€â”€ state           â€” objeto global com perfil, dias e diÃ¡rio
â”œâ”€â”€ scoreDay()      â€” calcula XP de um dia (Ã¡reas + hÃ¡bitos + bÃ´nus de humor)
â”œâ”€â”€ streak()        â€” conta dias completos consecutivos atÃ© hoje
â”œâ”€â”€ getLevel()      â€” converte XP total em nÃ­vel e progresso
â”œâ”€â”€ rewardFor()     â€” retorna a recompensa mais alta desbloqueada
â”œâ”€â”€ weekData()      â€” gera os dados dos Ãºltimos 7 dias
â”œâ”€â”€ trajectoryText()â€” texto de anÃ¡lise de trajetÃ³ria semanal
â”œâ”€â”€ bodyTrend()     â€” anÃ¡lise de IMC baseada em peso/altura do perfil
â”‚
â”œâ”€â”€ render()        â€” re-renderiza todo o painel a partir do estado
â”œâ”€â”€ loadState()     â€” lÃª o localStorage na inicializaÃ§Ã£o
â””â”€â”€ saveState()     â€” persiste o estado a cada mudanÃ§a
```

---

## ðŸ§® CÃ¡lculo de XP

```
XP do dia = Î£ pontos das Ã¡reas concluÃ­das
           + (nÂº de hÃ¡bitos marcados Ã— 5)
           + ((humor - 1) Ã— 2)

Ãrea       Pontos
â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€
ProgramaÃ§Ã£o  25
JeovÃ¡        20
Estudo       20
Treino       20
Libras       15
â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€
MÃ¡x. Ã¡reas  100
MÃ¡x. hÃ¡bitos 20
MÃ¡x. humor    8
â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€
MÃ¡x. total  128 XP/dia
```

**Meta diÃ¡ria padrÃ£o:** 80 XP (`dailyTarget`).

---

## ðŸŽ Recompensas

| Progresso do dia | Recompensa liberada |
|---|---|
| â‰¥ 70% | 10 min de Instagram |
| â‰¥ 85% | 20 min de Instagram |
| â‰¥ 100% | 30 min de Instagram |
| â‰¥ 125% | SessÃ£o extra de lazer |

---

## ðŸ› ï¸ Tecnologias

- **HTML5 / CSS3 / JavaScript** â€” sem frameworks
- **localStorage** â€” persistÃªncia local no navegador
- **CSS Grid + Flexbox** â€” layout responsivo
- **`crypto.randomUUID()`** â€” IDs dos registros do diÃ¡rio

---

## ðŸ“± Responsividade

| Largura | Layout |
|---|---|
| > 1100 px | 2 colunas (hero e painel principal) |
| 701â€“1100 px | 1 coluna, stats em 2Ã—2 |
| â‰¤ 700 px | Tudo em coluna Ãºnica |

---

## ðŸ”’ Privacidade

Nenhum dado sai do seu dispositivo. NÃ£o hÃ¡ servidor, nÃ£o hÃ¡ analytics, nÃ£o hÃ¡ cookies de terceiros.

---

## ðŸ“„ LicenÃ§a

Uso pessoal. Projeto criado para acompanhar evoluÃ§Ã£o pessoal diÃ¡ria.

---

*ConsistÃªncia hoje, forÃ§a amanhÃ£.*
