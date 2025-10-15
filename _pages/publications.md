---
layout: page
permalink: /publications/
title: Publications
description: My journal publications, patents and conference presentations
nav: true
nav_order: 2
---

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

## Journal Publications

{% bibliography --file journal %}

---

## Conference Publications

{% bibliography --file conference %}

</div>
