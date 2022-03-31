---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

Welcome to the Climate Compatible Growth Curation Guidelines.

On this site, you can browse guidelines on "good enough" [Practices](#good-enough-practices) that
implement the goals of Open Science.

We also provide a description of how the practices can be applied to a range of [Research Outputs](#research-outputs).

## Good Enough Practices

{%- if site.posts.size > 0 -%}
{% assign mydocs = site.posts | group_by: 'category' %}
{% for cat in mydocs %}
  {%- if cat.size > 0 and cat.name == "practice" -%}
  <ul>
    {% assign items = cat.items | sort_natural: "title" %}
    {% for item in items %}
      <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a>
      {{ item.excerpt }}</li>
    {% endfor %}
  </ul>
  {%- endif -%}
{% endfor %}
{%- endif -%}

## Research Outputs

{%- if site.posts.size > 0 -%}
{% assign mydocs = site.posts | group_by: 'category' %}
{% for cat in mydocs %}
  {%- if cat.size > 0 and cat.name == "output" -%}
  <ul>
    {% assign items = cat.items | sort_natural: "title" %}
    {% for item in items %}
      <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a>
      {{ item.excerpt }}</li>
    {% endfor %}
  </ul>
  {%- endif -%}
{% endfor %}
{%- endif -%}

## U4RIA

[U4RIA]({% post_url 2021-12-16-u4ria %})
provides a set of high-level goals relating to conducting
open and accessible energy system analyses in countries.

{% for tag in site.tags %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

<h3>{{ t | downcase }}</h3>
<ul>
{% for post in posts %}
  {% if post.tags contains t %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </li>
  {% endif %}
{% endfor %}
</ul>
{% endfor %}

# Categories

Alternatively, you can browse our guidelines by category:

{%- if site.posts.size > 0 -%}
{% assign mydocs = site.posts | group_by: 'category' %}
{% for cat in mydocs %}
  {%- if cat.size > 0 -%}
  <h3>{{ cat.name | capitalize }}</h3>
  <ul>
    {% assign items = cat.items | sort: 'order' %}
    {% for item in items %}
      <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a></li>
    {% endfor %}
  </ul>
  {%- endif -%}
{% endfor %}
{%- endif -%}
