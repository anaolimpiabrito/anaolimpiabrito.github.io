---
layout: page
permalink: /teaching/
title: teaching
description: work in progress
nav: true
display_categories: [Present Courses, Previous Courses]
nav_order: 6
---

For now, this page is assumed to be a static description of your courses. You can convert it to a collection similar to `_projects/` so that you can have a dedicated page for each course.

Organize your courses by years, topics, or universities, however you like!

{% if site.enable_project_categories and page.display_categories %} {% for category in page.display_categories %}
{{ category }}
{% assign categorized_projects = site.projects | where: "category", category %} {% assign sorted_projects = categorized_projects | sort: "importance" %} {% if page.horizontal %}
{% for project in sorted_projects %} {% include projects_horizontal.liquid %} {% endfor %}
{% else %}
{% for project in sorted_projects %} {% include projects.liquid %} {% endfor %}
{% endif %} {% endfor %}

{% else %}

{% assign sorted_projects = site.projects | sort: "importance" %}

{% if page.horizontal %}
{% for project in sorted_projects %} {% include projects_horizontal.liquid %} {% endfor %}
{% else %}
{% for project in sorted_projects %} {% include projects.liquid %} {% endfor %}
{% endif %} {% endif %} 
