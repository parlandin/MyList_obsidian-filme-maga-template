---
watched: <%* let watched = await tp.system.suggester(["✅ Finalizado", "🍿 Assistindo", "🛑 Não iniciado"], ["finished", "watching", "not_started"], false, "Qual o status do filme?"); tR += watched %>
priority: <%* let priority = await tp.system.suggester(["🔴 Alta", "🟡 Média", "🟢 Baixa"], ["high", "medium", "low"], false, "Selecione a prioridade"); tR += priority %>
tags:
  - movies
  - watched
cssclasses:
  - image-center
---
# {{title}}

![Image|360]({{image}})
## Sinopse

{{plot}}

## Descrição
(Adicione sua descrição aqui)

## Notas
(Adicione notas pessoais aqui)

