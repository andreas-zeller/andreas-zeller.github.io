# Samuel Ferino's Blog

My blog includes a variety of topics, from academia and software development to my tourism experience reports.  Here is the list of all posts:

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      (<span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>)
    </li>
  {% endfor %}
</ul>
