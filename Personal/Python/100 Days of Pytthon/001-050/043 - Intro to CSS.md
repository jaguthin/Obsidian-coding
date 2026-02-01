---
tags:
  - Education
  - Programming
  - CSS
---

---

Three ways of adding css

inline:
Added to a tag. style=color:blue  

internal:
Put between the head tags:
```css

<style>
h1 {
color: red;
}
</style>
```
external: 
Link to another page that is separate but has the styling information. 
Also between the head tags.
<link rel="stylesheet" href="style.css">

class has .name <-- No spaces and before the brackets. <-- In css. In the actual tag: in tag class=name

id="name" in css. In html before tag. 

Difference is id should only be applied to one element in an html file. 
can put attributes of tags in brackets in css file. [draggable] for example. Is only applied if html tag has that attribute. Can also use value of attribute. value is in quotes.  for example li[value="value"]{}