---
#
# By default, content added below the "---" mark will appear in the home page
# between the top bar and the list of recent posts.
# To change the home page layout, edit the _layouts/home.html file.
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
#
layout: page
---

<form class="example" action="/cari.html">
  <input type="text" placeholder="Cari..." name="query">
  <button type="submit"><i class="fa fa-search"></i></button>
</form>

<p>&nbsp;</p>

{% assign sorted_tag = site.tags | sort: tag[0]  %}

{% for tag in sorted_tag %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li class="spasi"><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
