<%* 
const deliveryName = await tp.system.prompt("Enter delivery name (e.g., Venture Capital)");
const priority = await tp.system.prompt("Enter priority (High/Medium/Low)", "Medium");
%>---
tags:
  - Delivery
  - <% deliveryName.replace(/\s+/g, '-') %>
created: <% tp.file.creation_date("YYYY-MM-DD") %>
status: In Progress
priority: <% priority %>
delivery_name: <% deliveryName %>
---

---

# <% deliveryName %>

## Overview

Brief description of the <% deliveryName %> delivery.

## Objectives

- [ ] Primary objective
- [ ] Secondary objective
- [ ] Additional goals

## Resources

### Team Members
- 

### Documents
- 

### Related Deliveries
- 

## Progress Notes

### <% tp.date.now("YYYY-MM-DD") %>
- Initial delivery setup

## Issues & Risks

| Issue | Impact | Mitigation | Status |
|-------|--------|------------|--------|
| | | | |

---

## Next Steps

- [ ] Define detailed requirements
- [ ] Assign team members
- [ ] Set milestone dates

---

<%* 
await tp.file.rename(deliveryName);
await tp.file.move("1 Delivery/" + deliveryName + "/" + deliveryName);
%>