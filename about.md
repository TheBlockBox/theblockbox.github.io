---
title: About
---
We are a small team of coders, modellers and texturers who are interested in Minecraft modding.

## Staff
{% for member in site.data.staff %}
* [{{ member.name }}](https://github.com/{{ member.name }}){:target="_blank"} - {{ member.role }}{% endfor %}