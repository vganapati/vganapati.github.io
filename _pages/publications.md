---
title: "Ganapati Lab - Publications"
layout: gridlay
excerpt: "Ganapati Lab -- Publications."
sitemap: false
permalink: /publications/
---


# Publications

## Highlights

(For a longer list of papers and patents see [below](#patents))

{% assign number_printed = 0 %}
{% for publi in site.data.publist %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="well">
  <pubtit>{{ publi.title }}</pubtit>
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="33%" style="float: left" />
  <p>{{ publi.description }}</p>
  <p><em>{{ publi.authors }}</em></p>
  <p><strong>{{ publi.link.display }}</strong></p>
  <p>| <a href="{{ publi.link.url }}">Link</a> |
  <a href="{{ site.url }}{{ site.baseurl }}/paperpdfs/{{ publi.pdf }}">PDF</a> | {% if publi.code == 0 %}{% else %}<a href="{{ publi.code }}">Code</a> | {% endif %}{% if publi.data == 0 %}{% else %}<a href="{{ publi.data}}">Data</a> |{% endif %}
   </p>
  <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
  <p>{{ publi.news2 }}</p>
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

<p> &nbsp; </p>


## Patents

{% for publi in site.data.patentlist %}

  {{ publi.title }} <br />
  <em>{{ publi.authors }} </em><br /><strong>{{ publi.link.display (publi.year) }}</strong><br />| <a href="{{ publi.link.url }}">Link</a> |
  <a href="{{ site.url }}{{ site.baseurl }}/paperpdfs/{{ publi.pdf }}">PDF</a> |<br />

{% endfor %}


## Papers

{% for publi in site.data.publist %}

  {{ publi.title }} <br />
  <em>{{ publi.authors }} </em><br /><strong>{{ publi.link.display }}</strong><br />| <a href="{{ publi.link.url }}">Link</a> |
  <a href="{{ site.url }}{{ site.baseurl }}/paperpdfs/{{ publi.pdf }}">PDF</a> | {% if publi.code == 0 %}{% else %}<a href="{{ publi.code }}">Code</a> | {% endif %}{% if publi.data == 0 %}{% else %}<a href="{{ publi.data}}">Data</a> |{% endif %}

{% endfor %}
