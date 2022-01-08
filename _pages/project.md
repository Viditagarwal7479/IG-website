---
title: "COPS IG - Projects"
layout: gridlay
excerpt: "COPS IG -- Projects."
sitemap: false
permalink: /project
---


# Projects

## Group highlights

{% assign number_printed = 0 %}
{% for publi in site.data.publist %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="well">
  <pubtit><strong><a href="{{ site.url }}{{ site.baseurl }}{{ publi.link.url }}">{{ publi.title }}</a></strong></pubtit>
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="33%" style="float: left" />
  <!-- <img src="{{ publi.image }}" class="img-responsive" width="33%" style="float: left" /> -->
  <p>{{ publi.description }}</p>
  <p><em>{{ publi.authors }}</em></p>
  <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

## Full List of publications

{% for publi in site.data.publist %}

  <a href="{{ publi.link.url }}">{{ publi.title }}</a><br>
  <em>{{ publi.authors }} </em><br />

{% endfor %}