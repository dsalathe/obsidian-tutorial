<%* 
const deliveryName = await tp.system.prompt("Enter case name");
const priority = await tp.system.suggester(
    ["High", "Medium", "Low"], 
    ["High", "Medium", "Low"],
    false,
    "Select priority"
);
%>---
tags:
  - Delivery
  - <% deliveryName.replace(/\s+/g, '-') %>
created: <% tp.file.creation_date("YYYY-MM-DD") %>
status: Under Investigation
priority: <% priority %>
case_name: <% deliveryName %>
---

---

# <% deliveryName %>

## Case Summary

Brief description of the <% deliveryName %> investigation.

## Objectives

- [ ] Identify primary suspects
- [ ] Gather physical evidence
- [ ] Establish timeline
- [ ] Determine motive

## Resources

### Personnel Assigned
- [[Sherlock Holmes]]
- [[Dr. John H. Watson]]

### Evidence Collected
- 

### Related Cases
- 

## Investigation Log

### <% tp.date.now("YYYY-MM-DD") %>
- Case opened

## Suspects & Persons of Interest

| Name | Motive | Alibi | Status |
|------|--------|-------|--------|
| | | | |

---

## Next Actions

- [ ] Interview primary witnesses
- [ ] Examine crime scene
- [ ] Research background information

---

<%* 
await tp.file.rename(deliveryName);
await tp.file.move("1 Delivery/Active/" + deliveryName + "/" + deliveryName);
%>
