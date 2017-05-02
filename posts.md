---
layout: page
title: Articles
permalink: /articles/
---


  <div class="post-list clearfix">
    {% for post in site.posts %}

      <div class="pr inline-block">
        <img src="/images/{{post.thumbnail}}" class="img thumbnail">
      </div>

      <div class="inline-block">
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
      </div>

      <p class="mb1"></p>

    {% endfor %}
  </div>

  <p>&nbsp;</p>

  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>
