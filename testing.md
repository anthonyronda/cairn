---
layout: default
title: Testing
nav_order: 15
---

Monsters

{% for document in site.data.documents %}

{% if document._type == "npc" %}

# {{ document.name }}

{{ document.hp }} HP{% unless document.STR == 10 %}, {{ document.STR }} STR{% endunless %}{% unless document.DEX == 10 %}, {{ document.DEX }} DEX{% endunless %}{% unless document.WIL == 10 %}, {{ document.WIL }} WIL{% endunless %}{% for item in document.items %}, {{ item.name }} ({{ item.damageFormula }}){% endfor %}

{% for block in document.description %}
{% for child in block.children %}
{% if block.listItem == "bullet" %}

- {{child.text}}

{% endif %}
{% endfor %}
{% endfor %}

{% endif %}
{% endfor %}

End monsters
