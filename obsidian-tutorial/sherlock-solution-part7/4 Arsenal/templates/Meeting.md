<%*
const projectNames = [... new Set(app.vault.getMarkdownFiles().map(f => f.path).filter(path => path.startsWith("1 Delivery/Active")).map(path => path.split("/")[2]))].filter(name => !name.endsWith(".md"));
const projectName = (await tp.system.suggester((item) => item, projectNames, true, "Select Case"));
const chosenDate = await tp.system.prompt("Meeting date:", tp.date.now("YYYY-MM-DD"));
const meetingType = await tp.system.prompt("Meeting type (e.g., Client Interview, Evidence Review, Team Briefing)");
%>---
case: '[[<% projectName %>]]'
date: '[[<% chosenDate %>]]'
attendees:
  - "[[Sherlock Holmes]]"
  - "[[Dr. John H. Watson]]"
type: <% meetingType %>
tags:
  - Meeting
---
---

## Agenda & Objectives

- 
---
## Key Observations

- 
--- 
## Deductions & Next Steps
- [ ]

<%* 
await tp.file.rename(chosenDate + " " + meetingType);
await tp.file.move("/1 Delivery/Active/" + projectName + "/Meetings/" + chosenDate + " " + meetingType);
%>
