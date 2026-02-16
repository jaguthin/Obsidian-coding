---
Date Read: 2025-02-08
Author: Ray Bradbury
Read or Listened: Read
Image: "[[Something Wicked this way Comes - Ray Bradbury.jpg]]"
coverUrl: "[[Something Wicked this way Comes - Ray Bradbury.jpg]]"
tags:
  - 📚Book
description: Two boys' lives are changed forever when a sinister travelling carnival stops at their Illinois town.
---
```dataview
TABLE WITHOUT ID
	rows.description as Description
FROM  #📚Book
WHERE !contains(file.path, "Templates")
GROUP BY status
SORT status
```