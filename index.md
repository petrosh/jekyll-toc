---
permalink: /
---

{% assign collection = site.collections | where: "label", "tests" | first %}
{% for p in collection.docs %}- [{{ p.title }}]({{ p.url }})
{% endfor %}
