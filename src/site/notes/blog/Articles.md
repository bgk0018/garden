---
{"dg-publish":true,"dg-path":"Articles.md","permalink":"/articles/","pinned":true,"tags":["🥕"],"created":"2025-01-05T08:44:56.312-06:00","updated":"2025-01-05T10:16:15.240-06:00"}
---


# Articles

```dataview
TABLE WITHOUT ID
  link(file.link, default(aliases[0], file.name)) as "Title",
  dateformat(date(create-date), "yyyy-MM-dd") as Published
FROM "blog/articles"
SORT date(create-date) DESC
