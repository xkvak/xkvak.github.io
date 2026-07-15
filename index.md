---
layout: default
title: Alex Kvak
description: Hello, world, I'm Alex, and this is my blog, where I talk about math, machine learning, and other things like cooking.
---

{% assign totalPosts = site.posts | size %}
{% assign totalWords = 0 %}

{% for post in site.posts %}
{% assign postWords = post.content | number_of_words %}
{% assign totalWords = totalWords | plus: postWords %}
{% endfor %}

# 안녕하세요, 저는 곽준호입니다.

이곳에 오신 것을 진심으로 환영합니다. 저는 넓디넓은 인터넷 속에서 조그마한 이곳을 관리하며 여러 가지 주제에 대한 제 생각을 글로 남기고 있습니다. 제가 글을 쓰는 몇 가지 이유에 대해서 [이곳](https://xkvak.github.io/2026/07/15/내가-글을-쓰는-이유.html)에 설명을 해두었으니, 저에 대해 궁금하시면 읽어보세요. 저는 2026년부터 지금까지 {{ totalPosts }}개의 글을 올렸고, 총 {{ totalWords }}자를 작성했습니다.

저는 이곳을 최대한 깔끔한 디자인으로 유지하려고 합니다. 외관보다는 내용물에 집중하고 있기 때문입니다. 어떤 사람은 너무 간결하다고 생각하실 수 있지만 어쩔 수 없습니다. 혹시 이곳의 소스 코드가 필요하시다면 제 [저장소](https://github.com/xkvak/xkvak.github.io/)에서 찾을 수 있습니다. 마음껏 사용해 주세요.

---

## Latest posts

{% assign postCount = 0 %}
{% for post in site.posts %}
{% if postCount < 5 %}

  <li>
    <span class="post-date">{{ post.date | date: "%b %d %Y" }}</span> · <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
  {% assign postCount = postCount | plus: 1 %}
{% endif %}
{% endfor %}

---

## Favourite posts

{% for post in site.posts %}
{% if post.favourite %}

  <li>
    <span class="post-date">{{ post.date | date: "%b %d %Y" }}</span> · <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
{% endif %}
{% endfor %}
