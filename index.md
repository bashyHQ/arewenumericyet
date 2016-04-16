---
layout: main
---

# Are we *numeric* yet?

**You can build stuff!**

<p>Rust has a mature <a href="{{site.baseurl}}/topics/stack/">HTTP stack</a>{% include level.html level=2%} and various <a href="{{site.baseurl}}/topics/frameworks/">frameworks</a>{% include level.html level=3 %} enable you to build APIs and backend services quickly. While increasingly more <a href="{{site.baseurl}}/topics/database/#drivers">databases drivers</a>{% include level.html level=2 %} become available, <a href="{{site.baseurl}}/topics/database/#orms">ORMs</a>{% include level.html level=5 %} and connections to <a href="{{site.baseurl}}/topics/services/">external services</a>{% include level.html level=5 %} (like search or worker queues) are still scarce. Looking farther, it doesn't necessarily get better. Though there is significant support for base needs (like <a href="{{site.baseurl}}/topics/compression/">data compression</a>{% include level.html level=2 %} or <a href="{{site.baseurl}}/topics/logging/">logging</a>{% include level.html level=2 %}), a lot more web-specific needs are still unmet and immature.</p>

<p>&nbsp;</p>

## Can I replace my Rails/Django/Flask already?

**Well, probably not yet**. While the basics are there, many of handy utility libs that make working with many popular frameworks so quick and easy are still missing. **If your service primarily provides an API** to be consumed by  other computers, requires little external services and you are happy with writing most SQL yourself, then **Yes, You Can!** Otherwise, we would not recommend it just yet.

### What should I replace it with?

The frameworks of choice of the community are <a href="{{site.baseurl}}/topics/frameworks/#pkg-iron">iron</a>, <a href="{{site.baseurl}}/topics/frameworks/#pkg-conduit">conduit</a> and <a href="{{site.baseurl}}/topics/frameworks/#pkg-nickel">nickel</a>, best run with a <a href="{{site.baseurl}}/topics/database/#pkg-postgres">postgres</a> or <a href="{{site.baseurl}}/topics/database/#pkg-mysql">mysql</a> backend accompanied by <a href="{{site.baseurl}}/topics/database/#pkg-redis">redis</a> – all these drivers seem to be fairly mature. If you want to wrap that into an ORM <a href="{{site.baseurl}}/topics/database/#pkg-rustorm">rustorm</a> and <a href="{{site.baseurl}}/topics/frameworks/#pkg-diesel">diesel</a> are at your disposal – both are still fairly young though.

If you need to (or want to) go lower in the stack, those frameworks all use the fairly stable and mature <a href="{{site.baseurl}}/topics/stack/#pkg-hyper">hyper http stack</a>, if you want it slimmer <a href="{{site.baseurl}}/topics/stack/#pkg-tiny_http">tiny_http</a> might be an option and for the async-fans <a href="{{site.baseurl}}/topics/stack/#pkg-rotor-http">rotor</a> has you covered. If you need HTTP2, you have to turn to <a href="{{site.baseurl}}/topics/stack/#pkg-solicit">solicit</a> as none of the other stacks supports it just yet.

### Getting started

After you've set up your rust and worked yourself [through "The Book"](https://doc.rust-lang.org/book/), we highly recommend taking a look at [fully annotated source code](https://clippy.bashy.io/docs/) of the [clippy-service](https://clippy.bashy.io), an iron-based microservice, which shows how to use many common features like redis database connections or JSON parsing. And take a look at [this blog post by auth0.com](https://auth0.com/blog/2015/11/30/build-an-api-in-rust-with-jwt-authentication-using-nickelrs/) especially if nickel and mongo are of more interest to you.

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
