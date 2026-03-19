This is the index page of meeting notes.

## Table of Contents
```dataviewjs
```
```dataviewjs
const pages = dv.pages()
    .where(p => p.type === "meeting-notes" && !p.file.path.includes("Templates"))
    // Sorts by file name (YYYY-MM-DD) from newest to oldest
    .sort(p => p.file.name, 'desc');

const data = pages.map(p => {
    const cache = app.metadataCache.getFileCache(app.vault.getAbstractFileByPath(p.file.path));
    const firstH1 = cache?.headings?.find(h => h.level === 1);
    const meetingName = firstH1 ? firstH1.heading : "⚠️ No H1 found";
    
    return [p.file.link, meetingName];
});

dv.table(["Date (File Name)", "Meeting Name"], data);
```

