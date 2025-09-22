<%*
const projectNames = [... new Set(app.vault.getMarkdownFiles().map(f => f.path).filter(path => path.startsWith("1 Delivery")).map(path => path.split("/")[1]))].filter(name => !name.endsWith(".md"));
const projectName = (await tp.system.suggester((item) => item, projectNames, true, "Select Project Name"));
const chosenDate = await tp.system.prompt("Day of Meeting:", tp.date.now("YYYY-MM-DD"));
const meetingKind = await tp.system.prompt("Meeting type (e.g., Daily, Sprint Planning, Review)");
%>---
project: '[[<% projectName %>]]'
date: '[[<% chosenDate %>]]'
people:
  - "[[Sherlock Holmes]]"
kind: <% meetingKind %>
tags:
  - Meeting
aliases:
---
---

## What I bring

- 
---
## Discussion

- 
--- 
## Next actions
- [ ]

<%* 
await tp.file.rename(chosenDate + " " + meetingKind);
await tp.file.move("/1 Delivery/" + projectName + "/Meetings/" + chosenDate + " " + meetingKind);
%>