---
layout: single
classes: wide
author_profile: true
header:
  teaser: /assets/images/pfp.png
---
<style>
  .teaser-container {
    display: flex;
    flex-wrap: nowrap;
    justify-content: flex-start;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    -ms-overflow-style: none;
    scrollbar-width: none;
    scroll-behavior: smooth;
  }

  .teaser-item {
    flex: 0 0 200px;
    margin-right: 0px;
    justify-content: center;
    text-align: center;
    scroll-snap-align: start;
    text-decoration: none;
  }

  .teaser-container a {
    color: white;
  }

  .teaser-container::-webkit-scrollbar {
    width: 0;
    height: 0;
  }

  .teaser-item h2 {
    font-size: 16px;
    line-height: 1.2;
    margin: 5px 0;
    overflow: hidden;
    max-height: 100%;
    max-width: 100%;
    border: none;
  }

  .teaser-item img {
    width: 150px;
    height: 75px;
    object-fit: auto;
  }
</style>

## Posts
<div class="teaser-container">
  {% for post in site.posts limit:25 %}
    <a href="{{ post.url }}" class="teaser-item">
      <img src="{{ post.header.teaser }}" alt="{{ post.title }}">
      <h2>{{ post.title }}</h2>
    </a>
  {% endfor %}
</div>

## Projects
<div class="teaser-container">
  {% assign filteredPosts = site.posts | where: "categories", "projects" %}
  {% for post in filteredPosts limit:25 %}
    <a href="{{ post.url }}" class="teaser-item">
      <img src="{{ post.header.teaser }}" alt="{{ post.title }}">
      <h2>{{ post.title }}</h2>
    </a>
  {% endfor %}
</div>

## Cybersecurity
<div class="teaser-container">
  {% assign filteredPosts = site.posts | where: "categories", "cybersecurity" %}
  {% for post in filteredPosts limit:25 %}
    <a href="{{ post.url }}" class="teaser-item">
      <img src="{{ post.header.teaser }}" alt="{{ post.title }}">
      <h2>{{ post.title }}</h2>
    </a>
  {% endfor %}
</div>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    const teaserContainer = document.querySelector('.teaser-container');
    let isScrolling = false;
    
    teaserContainer.addEventListener('wheel', function(event) {
      event.preventDefault();

      if (!isScrolling) {
        isScrolling = true;
        const scrollAmount = event.deltaY;

        // Smooth scroll using requestAnimationFrame
        const startTime = performance.now();
        const duration = 100; // Adjust the duration as desired

        function scroll(timestamp) {
          const elapsed = timestamp - startTime;
          const progress = Math.min(elapsed / duration, 1);
          const easeValue = 0.8; // Adjust the ease value for smoother scrolling

          teaserContainer.scrollLeft += scrollAmount * easeValue * progress;

          if (elapsed < duration) {
            requestAnimationFrame(scroll);
          } else {
            isScrolling = false;
          }
        }

        requestAnimationFrame(scroll);
      }
    });
  });
</script>
