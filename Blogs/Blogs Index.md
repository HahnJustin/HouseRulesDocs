This is the index page of blogs.

## Table of Contents
```dataviewjs
```
```dataviewjs
```
```dataview
TABLE date, title, draft
FROM "Blogs" OR #blog
WHERE type = "blog" 
  AND file.name != "Blog Template"
SORT date DESC
```

