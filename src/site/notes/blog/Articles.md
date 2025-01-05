---
{"dg-publish":true,"dg-path":"Articles.md","permalink":"/articles/","hide":true,"hideInGraph":true,"tags":["🥕"],"created":"2025-01-05T08:44:56.312-06:00","updated":"2025-01-05T09:55:31.444-06:00"}
---


# Articles

```dataview
TABLE WITHOUT ID
  link(file.link, default(aliases[0], file.name)) as "Title"
FROM "blog/articles"
SORT date(create-date) DESC
