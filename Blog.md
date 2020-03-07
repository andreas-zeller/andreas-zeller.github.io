# Andreas Zeller's Blog

My blog has a mixture of various topics from academia and software development, often with a humorous touch.  Here is the collection of all posts:

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      (<span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>)
    </li>
  {% endfor %}
</ul>
