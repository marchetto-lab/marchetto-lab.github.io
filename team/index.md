---
title: Team
nav:
  order: 3
  tooltip: About our team
---

# {% include icon.html icon="fa-solid fa-users" %}Team

Meet our lab!

{% include section.html %}

{% assign group_order = "Principal Investigator,Postdoc,Student,Collaborator" | split: "," %}

{% for group_name in group_order %}
  {% assign members_in_group = site.members | where: "group", group_name %}
  {% if members_in_group.size > 0 %}
    {% assign plural_group = group_name | append: "s" %}

    <!-- Group heading -->
    <h2 class="team-group-title">{{ plural_group }}</h2>
    {% include section.html %}

    <!-- Render each member manually -->
    <div class="member-grid">
      {% for member in members_in_group %}
        {% include portrait.html member=member %}
      {% endfor %}
    </div>

  {% endif %}
{% endfor %}
