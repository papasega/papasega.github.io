{% for post in site.categories.deep-learning %}
  <!-- Insérez ici le code pour afficher l'article (voir étape 3) -->
  <article class="post-preview">
  <a href="{{ post.url | relative_url }}">
    <h2 class="post-title">{{ post.title }}</h2>
    {% if post.subtitle %}
    <h3 class="post-subtitle">{{ post.subtitle }}</h3>
    {% endif %}
  </a>

  <p class="post-meta">
    Publiée le {{ post.date | date: "%-d %B %Y" }}
  </p>

  <div class="post-entry-container">
    {% if post.image %}
    <div class="post-image">
      <a href="{{ post.url | relative_url }}">
        <img src="{{ post.image | relative_url }}">
      </a>
    </div>
    {% endif %}
    <div class="post-entry">
      {{ post.excerpt | strip_html | xml_escape | truncatewords: site.excerpt_length }}
      {% assign excerpt_word_count = post.excerpt | number_of_words %}
      {% if post.content != post.excerpt or excerpt_word_count > site.excerpt_length %}
        <a href="{{ post.url | relative_url }}" class="post-read-more">[Lire&nbsp;plus]</a>
      {% endif %}
    </div>
  </div>
</article>

{% endfor %}
