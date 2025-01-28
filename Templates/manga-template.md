---
read: <%* let reading = await tp.system.suggester(["✅ Finalizado", "📖 Lendo", "🛑 Não iniciado"], ["finished", "reading", "not_started"], false, "Qual o status da leitura?"); tR += reading %>
priority: <%* let priority = await tp.system.suggester(["🔴 Alta", "🟡 Média", "🟢 Baixa"], ["high", "medium", "low"], false, "Selecione a prioridade"); tR += priority %>
chapter: <% await tp.system.prompt("Em qual capitulo parou?", 0, true, true)%>
page: <% await tp.system.prompt("Em  qual página parou?", 1, true, true)%>
tags:
  - mangas
  - read
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

