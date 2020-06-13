---
title: People
permalink: /people/
---

{% assign people_sorted = (site.people | sort: 'joined' %}
{% assign people_array = "pi|postdoc|labmanager|gradstudent|undergrad" | split: "|" %}

{% for item in people_array %}

<div class="pos_header">
{% if item == 'pi' %}
<h3>Principal Investigator</h3>
 {% elsif item == 'postdoc' %}
<h3>Postdoctoral Fellows</h3>
 {% elsif item == 'labmanager' %}
<h3>Lab Manager</h3>
 {% elsif item == 'gradstudent' %}
<h3>Graduate Students</h3>
 {% elsif item == 'undergrad' %}
<h3>Undergraduate Students</h3>
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


| Who are they | When were they were here | Where they went |
| :------------- |:-------------| :-----------|


