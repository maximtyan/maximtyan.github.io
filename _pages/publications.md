---
layout: page
permalink: /publications/
title: Publications
description: My journal publications, patents and conference presentations
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

## SCI/SCIE Journals

{% bibliography --file journal.bib%}

## Conferences

{% bibliography --file conference.bib%}

</div>
