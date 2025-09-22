<%* 
const personName = await tp.system.prompt("Enter person's name");
const imageName = await tp.system.prompt("Enter image filename (e.g., watson.png)");
%>---
tags:
  - People
created: <% tp.file.creation_date("YYYY-MM-DD") %>
image: <% imageName %>
---

---

## <% personName %>

---

![[<% imageName %>]]

---

## Notes

---

<%* 
await tp.file.rename(personName);
await tp.file.move("/2 Assets/People/" + personName);
%>