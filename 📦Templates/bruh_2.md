<%*
let qcFileName = await tp.system.prompt("Note Title")
titleName = qcFileName + " " + tp.date.now("YYYY-MM-DD")
await tp.file.rename(titleName)
await tp.file.move("/🛒Temporal Lobe/" + titleName);
-%>
---
title: <% qcFileName %>
date: <% tp.file.creation_date("YYYY-MM-DD HH:mm:ss") %>
tags: quick_note
topic: 
---


<% tp.file.cursor() %>