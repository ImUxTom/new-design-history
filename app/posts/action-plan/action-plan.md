---
override:tags: []
layout: product
title: Action plan
description: Seeing and managing the action points related to a case
pagination:
  data: collections.action-plan
  reverse: true
  size: 50
permalink: "action-plan/{% if pagination.pageNumber > 0 %}page/{{ pagination.pageNumber + 1 }}{% endif %}/"
eleventyComputed:
  eleventyNavigation:
    title: Action plan
    key: action-plan
    excerpt: "{{ description }}"
    parent: Home
---
