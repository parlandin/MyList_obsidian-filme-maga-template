---
cssclasses:
  - cards
  - cards-cover
  - full-width
  - table-wide
  - table-100
  - cards-2-3
---
```ad-note
title: Manga
icon: book-open
color: 111, 111, 111

```dataview
table without id 
	choice(length(file.outlinks) > 0, file.outlinks[0], "![](" + image + ")") as Poster,
	("<span class='file-link'><a href='" + file.path + "'>" + file.link + "</a></span>") as Title,
	string(year) as Year, 
	"by <span class='authors'>" + authors + "</span>" as Authors,
	"⭐ " + ("<span class='" + 
		(choice(onlineRating <= 2, "red", 
		choice(onlineRating <= 4, "orange", 
		choice(onlineRating <= 6, "yellow", 
		choice(onlineRating <= 8, "light-green", "green"))))) + "'>" + onlineRating + "</span>") as "⭐ rating",
		"Leitura: " + 
"<span class='" + 
choice(read = "finished", "green", 
  choice(read = "reading", "yellow", 
    choice(read = "not_started", "red", "gray"))) + 
"'>" + 
choice(read = "finished", "Finalizada", 
  choice(read = "reading", "Em andamento", 
    choice(read = "not_started", "Não iniciada", "Status desconhecido"))) + 
"</span>" as Read,
	"<span class='chapter'>Capitulo: " + chapter + "</span>" as Chapter,
	"<span class='page'>Página: " + page + "</span>" as Page
from #mangas 
where id != null
```


```ad-note
title: Animes / Series
icon: tv
color: 127, 172, 207

```dataview
table without id 
	choice(length(file.outlinks) > 0, file.outlinks[0], "![](" + image + ")") as Poster,
	"<span class='file-link'><a href='" + file.path + "'>" + file.link + "</a></span>" as Title,
	string(year) as Year, 
	"by <span class='studio'>" + studio + "</span>" as Studio,
	"⭐ <span class='" + 
		(choice(onlineRating <= 2, "red", 
		choice(onlineRating <= 4, "orange", 
		choice(onlineRating <= 6, "yellow", 
		choice(onlineRating <= 8, "light-green", "green"))))) + "'>" + onlineRating + "</span>" as "⭐ rating",
	"Status: <span class='" + 
		choice(watched = "finished", "green", 
		choice(watched = "watching", "yellow", 
		choice(watched = "not_started", "red", "gray"))) + 
	"'>" + 
		choice(watched = "finished", "Finalizado", 
		choice(watched = "watching", "Assistindo", 
		choice(watched = "not_started", "Não iniciado", "Desconhecido"))) + 
	"</span>" as Status,
	"<span class='season'>Temporada: " + season + "</span>" as Season,
	"<span class='episode'>Episódio: " + episode + "</span>" as Episode
from #series 
where id != null

```



```ad-note
title: Filmes
icon: film
color: 96, 253, 60

```dataview
table without id 
	choice(length(file.outlinks) > 0, file.outlinks[0], "![](" + image + ")") as Poster,
	"<span class='file-link'><a href='" + file.path + "'>" + file.link + "</a></span>" as Title,
	string(year) as Year, 
	"by <span class='director'>" + director + "</span>" as director,
	"⭐ <span class='" + 
		(choice(onlineRating <= 2, "red", 
		choice(onlineRating <= 4, "orange", 
		choice(onlineRating <= 6, "yellow", 
		choice(onlineRating <= 8, "light-green", "green"))))) + "'>" + onlineRating + "</span>" as "⭐ rating",
	"Status: <span class='" + 
		choice(watched = "finished", "green", 
		choice(watched = "watching", "yellow", 
		choice(watched = "not_started", "red", "gray"))) + 
	"'>" + 
		choice(watched = "finished", "Finalizado", 
		choice(watched = "watching", "Assistindo", 
		choice(watched = "not_started", "Não iniciado", "Desconhecido"))) + 
	"</span>" as Status
from #movies 
where id != null
```


```ad-note
title: Books
icon: book
color: 255, 164, 28

```dataview
table without id 
	choice(length(file.outlinks) > 0, file.outlinks[0], "![](" + image + ")") as Poster,
	("<span class='file-link'><a href='" + file.path + "'>" + file.link + "</a></span>") as Title,
	string(year) as Year, 
	"by <span class='authors'>" + author + "</span>" as author,
	"⭐ " + ("<span class='" + 
		(choice(onlineRating <= 2, "red", 
		choice(onlineRating <= 4, "orange", 
		choice(onlineRating <= 6, "yellow", 
		choice(onlineRating <= 8, "light-green", "green"))))) + "'>" + onlineRating + "</span>") as "⭐ rating",
	"Leitura: " + 
"<span class='" + 
choice(read = "finished", "green", 
  choice(read = "reading", "yellow", 
    choice(read = "not_started", "red", "gray"))) + 
"'>" + 
choice(read = "finished", "Finalizada", 
  choice(read = "reading", "Em andamento", 
    choice(read = "not_started", "Não iniciada", "Status desconhecido"))) + 
"</span>" as Read,
	"<span class='chapter'>Capitulo: " + chapter + "</span>" as Chapter,
	"<span class='page'>Página: " + page + "</span>" as Page
from #books  
where id != null
```
