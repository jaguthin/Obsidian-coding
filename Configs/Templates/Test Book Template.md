---
tags:
  - 📚Book
title: '"{{title}}"'
subtitle: '"{{subtitle}}"'
Author: "[{{author}}]"
category: "[{{category}}]"
publisher: "{{publisher}}"
publishDate: "{{publishDate}}"
totalPage: "{{totalPage}}"
isbn:
  - "{{isbn10}} {{isbn13}}"
cover: "{{coverUrl}}"
localCover: "{{localCoverImage}}"
status:
created: "{{DATE:YYYY-MM-DD HH:mm:ss}}"
updated: "{{DATE:YYYY-MM-DD HH:mm:ss}}"
DateRead:
Read or Listened:
---

# 📚 My Bookshelf

```dataview
TABLE WITHOUT ID
	status as Status,
	rows.file.link as Book
FROM  #📚Book
WHERE !contains(file.path, "Templates")
GROUP BY status
SORT status
```

## List of all books

```dataview
TABLE WITHOUT ID
	status as Status,
	"![|60](" + cover + ")" as Cover,
	link(file.link, title) as Title,
	author as Author,
	join(list(publisher, publish)) as Publisher
FROM #📚Book
WHERE !contains(file.path, "Templates")
SORT status DESC, file.ctime ASC
```