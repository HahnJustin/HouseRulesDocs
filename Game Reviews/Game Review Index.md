## Table of Contents
```dataviewjs
```
```dataview
TABLE date, complete, review
FROM "game-review" OR #game-review
WHERE type = "game-review" 
  AND file.name != "Game Review Template"
SORT date DESC
```
