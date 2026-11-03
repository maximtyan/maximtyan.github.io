---
layout: page
permalink: /projects/
title: Projects
description:
nav: true
nav_order: 2
---

<div class="projects-page">

{% assign sorted_projects = site.projects | sort: "importance" %}

{% for project in sorted_projects %}
<div class="project-card">
  <div class="project-card__title">
    <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
  </div>

  {% if project.funding_source %}
  <div class="project-card__meta">Funding: {{ project.funding_source }}</div>
  {% elsif project.description %}
  <div class="project-card__meta">{{ project.description }}</div>
  {% endif %}

  {% if project.period %}
  <div class="project-card__period">Period: {{ project.period }}</div>
  {% endif %}
</div>
{% endfor %}

</div>

<style>
.projects-page {
  margin-top: 1.25rem;
}

.project-card {
  margin: 0 0 0.85rem;
  padding: 0.95rem 1.05rem;
  border: 1px solid var(--global-divider-color);
  border-radius: 0.45rem;
  background: var(--global-card-bg-color);
}

.project-card__title {
  margin-bottom: 0.2rem;
  font-size: 1.05rem;
  font-weight: 600;
  line-height: 1.35;
}

.project-card__title a {
  color: var(--global-text-color);
  text-decoration: none;
}

.project-card__title a:hover {
  color: var(--global-theme-color);
  text-decoration: none;
}

.project-card__meta,
.project-card__period {
  font-size: 0.92rem;
  line-height: 1.5;
}

.project-card__meta {
  color: var(--global-theme-color);
  font-weight: 500;
}

.project-card__period {
  color: var(--global-text-color-light);
}

@media (max-width: 576px) {
  .project-card {
    padding: 0.85rem 0.9rem;
  }
}
</style>
