---
title: Team
nav:
  order: 3
  tooltip: About our team
---

# {% include icon.html icon="fa-solid fa-users" %}Team

Meet our lab!

{% include section.html %}

{% comment %}
Define the order of groups here. Make sure these match the 'group' field in your member files.
{% endcomment %}
{% assign group_order = "PI,Postdoctoral Researcher,PhD Student,Undergraduate Student, Alumni" | split: "," %}

{% for group_name in group_order %}
  {% assign members_in_group = site.members | where: "group", group_name %}
  {% if members_in_group.size > 0 %}
    {% assign plural_group = group_name | append: "s" %}

    <!-- Group heading -->
    <h2 class="team-group-title">{{ plural_group }}</h2>

    <!-- Optional section spacing/background -->
    {% include section.html %}

    <!-- Portrait cards for this group -->
    {% assign filter_string = "group: " | append: group_name %}
    {% include list.html data="members" component="portrait" filters=filter_string %}

  {% endif %}
{% endfor %}

{% include section.html background="images/Screen Shot 2024-09-13 at 9.34.05 AM.png" dark=false %}

{% include section.html %}

{% capture content %}

{% include figure.html image="images/birthday_1.jpg" %}
{% include figure.html image="images/birthday_2.jpg" %}
{% include figure.html image="images/birthday_4.jpg" %}

{% endcapture %}

{% include grid.html style="square" content=content %}
