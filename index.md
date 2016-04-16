---
layout: main
---

# Are we *numeric* yet?

*You can build stuff!*

<p>Rust has a mature <a href="{{site.baseurl}}/topics/compiler/">compiler</a>{% include level.html level=1%}.</p>

<p>&nbsp;</p>

### Getting started

First set up your rust and work yourself through ["The Book"](https://doc.rust-lang.org/book/).

Either way you choose, if you find yourself stuck and looking for help, the [official Rust-Lang user forum](https://users.rust-lang.org/) has a [help section](https://users.rust-lang.org/c/help), where you are welcome to post your questions and soon will find help.


## In detail

learn more about the state of numerical algorithm development in rust by topic:

<ul class="topic-list">
  {% for page in site.pages %}
    {% if page.layout == 'topic' %}
      <li><a href="{{page.url}}">{{page.title}}</a>  {% include level.html level=page.level%}</li>
    {% endif %}
  {% endfor %}
</ul>

<h3> Latest News <a href="{{site.baseurl}}/atom.xml" title="subscribe"><i class="fa fa-rss-square"></i></a></h3>

<ul class="related-news">
  {% for post in site.posts | limit:5 %}
    {% include news_item.html post=post %}
  {% endfor %}
  <li><a href='/news/'>show all</a></li>
</ul>
