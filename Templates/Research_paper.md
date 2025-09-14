---
aliases:
  - "{{title}}"
authors: "{{authors}}"
year: {{ date.year() }}
type: paper
tags:
  - academic
page(s): "{{pages}}"
---
{% if abstractNote %}
> [!abstract]
> {{abstractNote}}
{% endif %}
# Annotations
({{importDate.format("M/D/YYYY, h:mm:ss A")}})
{% for annotation in annotations %}
{% if annotation.annotatedText %}"{{annotation.annotatedText}}" ([{{citationKey | capitalize}}](zotero://select/items/@{{citekey}})) ([pdf, p. {{annotation.pageLabel}}]({{annotation.desktopURI}})){% endif %}{% if annotation.imageRelativePath %}![[{{annotation.imageRelativePath}}]]{% endif %}{% if annotation.comment %}([{{citationKey | capitalize}}]({{annotation.desktopURI}})) {{annotation.comment}}{% endif %}
{% endfor %}
## References
1. [{{citekey}}]({{select}})