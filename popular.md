---
layout: page
title: Mike Schwarz
css: "/css/index.css"
subtitle: My Data Science Blog
---

<div class="list-filters">
  <a href="/" class="list-filter">All posts</a>
  <span class="list-filter filter-selected">Most Popular</span>
</div>


<div class="posts-list">
  {% for post in site.tags.popular %}
  <article>
    <a class="post-preview" href="{{ post.url | prepend: site.baseurl }}">
	    <h2 class="post-title">{{ post.title }}</h2>
	
	    {% if post.subtitle %}
	    <h3 class="post-subtitle">
	      {{ post.subtitle }}
	    </h3>
	    {% endif %}
	    </a> 
      <p class="post-meta">
        Posted on {{ post.date | date: "%B %-d, %Y" }}
      </p>
      
      <div class="post-entry">
        {{ post.excerpt | strip_html }}
         {% assign excerpt_word_count = post.excerpt | number_of_words %}
        {% if post.content != post.excerpt or excerpt_word_count > site.excerpt_length %}
          <a href="{{ post.url | prepend: site.baseurl }}" class="post-read-more">[Read&nbsp;More]</a>
        {% endif %}
      </div>
     
   </article>
  {% endfor %}
</div>