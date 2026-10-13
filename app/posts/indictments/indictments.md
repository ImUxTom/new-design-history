---
override:tags: []
layout: product
title: Indictments
description: Designing the process for prosecutors to build indictments
pagination:
  data: collections.indictments
  reverse: true
  size: 50
permalink: "indictments/{% if pagination.pageNumber > 0 %}page/{{ pagination.pageNumber + 1 }}{% endif %}/"
eleventyComputed:
  eleventyNavigation:
    title: Indictments
    key: indictments
    excerpt: "{{ description }}"
    parent: Home
---
