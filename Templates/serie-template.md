---
watched: <%* let watched = await tp.system.suggester(["✅ Finalizado", "🍿 Assistindo", "🛑 Não iniciado"], ["finished", "watching", "not_started"], false, "Qual o status da série/anime?"); tR += watched %>
priority: <%* let priority = await tp.system.suggester(["🔴 Alta", "🟡 Média", "🟢 Baixa"], ["high", "medium", "low"], false, "Selecione a prioridade"); tR += priority %>
episode: <% await tp.system.prompt("Em qual episodio parou?", 0, true, true)%>
season: <% await tp.system.prompt("Em  qual temporada parou?", 1, true, true)%>
tags:
  - series
  - animes
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

