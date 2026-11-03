---
layout: page
permalink: /publications/
title: Publications
description:
nav: true
nav_order: 3
---

<!-- _pages/publications.md -->

1. [**Journals**](#journals)
2. [**Conferences**](#conferences)
3. [**Patents**](#patents)

---

<style>
  .publication-numbered {
    counter-reset: publication-item;
  }

  .publication-numbered ol.bibliography {
    list-style: none;
    padding-left: 0;
  }

  .publication-numbered ol.bibliography > li {
    counter-increment: publication-item;
    position: relative;
    padding-left: 2.25rem;
  }

  .publication-numbered ol.bibliography > li::before {
    content: counter(publication-item) ".";
    position: absolute;
    left: 0;
    top: 0;
    min-width: 1.75rem;
    text-align: right;
    color: var(--global-text-color);
  }

  .publications a.abstract,
  .publications div.abstract.hidden {
    display: none !important;
  }
</style>

<div class="publications">

<h2 id="journals">Journal Articles</h2>

<div class="publication-numbered">
{% bibliography --file journal %}
</div>

---

<h2 id="conferences">Conference Papers</h2>

<div class="publication-numbered">
{% bibliography --file conference %}
</div>

---

<h2 id="patents">Patents</h2>

<div class="publication-numbered">
{% bibliography --file patent %}
</div>

</div>
