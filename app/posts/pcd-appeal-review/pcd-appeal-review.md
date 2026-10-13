---
override:tags: []
layout: product
title: PCD appeal review tasks
description: Managing green and red PCD appeals reviews from the task list
pagination:
  data: collections.pcd-appeal-review
  reverse: true
  size: 50
permalink: "pcd-appeal-review/{% if pagination.pageNumber > 0 %}page/{{ pagination.pageNumber + 1 }}{% endif %}/"
eleventyComputed:
  eleventyNavigation:
    title: PCD appeal review tasks
    key: pcd-appeal-review
    excerpt: "{{ description }}"
    parent: Home
---
