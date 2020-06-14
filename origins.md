---
title: ORIGINS
permalink: /ORIGINS/
---

{% assign people_sorted = (site.origins | sort: 'joined' %}
{% assign people_array = "MSU|UNC|CCG|CS|MPI|others" | split: "|" %}

{% for item in people_array %}

<div class="pos_header">
{% if item == 'MSU' %}
<h3>Michigan State University</h3>
 {% elsif item == 'CCG' %}
<h3>Charité Centrum für Human- und Gesundheitswissenschaften</h3>
 {% elsif item == 'UNC' %}
<h3>University of North Carolina at Chapel Hill</h3>
 {% elsif item == 'CS' %}
<h3>Cedars Sinai</h3>
 {% elsif item == 'MPI' %}
<h3>Max Planck Institute</h3>
{% endif %}
</div>

<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains item %}
    <div class="list-item-people">
      <p class="list-post-title">
        {% if profile.avatar %}
        <a href="{{ site.baseurl }}{{ profile.url }}"><img width="200" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
        {% else %}
        <a href="{{ site.baseurl }}{{ profile.url }}"><img width="200" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
        {% endif %}
        <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
      </p>
    </div>    
    {% endif %}
  {% endfor %}
</div>
<hr>
{% endfor %}


