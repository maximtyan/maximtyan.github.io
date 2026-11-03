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
  .publication-numbered ol.bibliography {
    list-style: decimal;
    padding-left: 2rem;
  }

  .publication-numbered ol.bibliography > li {
    padding-left: 0.35rem;
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

<script>
  document.addEventListener('DOMContentLoaded', function () {
    const fallbackAbstracts = {{ site.data.publication_abstracts | jsonify }};

    Object.entries(fallbackAbstracts).forEach(function ([key, abstractText]) {
      const entry = document.getElementById(key);
      if (!entry || entry.querySelector('.abstract.hidden')) return;

      const links = entry.querySelector('.links');
      if (!links) return;

      const button = document.createElement('a');
      button.className = 'abstract btn btn-sm z-depth-0';
      button.setAttribute('role', 'button');
      button.textContent = 'Abs';
      links.prepend(button);

      const abstract = document.createElement('div');
      abstract.className = 'abstract hidden';
      const paragraph = document.createElement('p');
      paragraph.textContent = abstractText;
      abstract.appendChild(paragraph);
      entry.appendChild(abstract);

      button.addEventListener('click', function () {
        abstract.classList.toggle('open');
        entry.querySelectorAll('.award.hidden.open, .bibtex.hidden.open').forEach(function (el) {
          el.classList.remove('open');
        });
      });
    });
  });
</script>
