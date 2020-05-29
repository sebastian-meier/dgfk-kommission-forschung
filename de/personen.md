---
layout: page
title: Personen
parent: "Über uns"
---

### Steuerungsgruppe:
<div class="columns" id="persons">
{% for person in site.data.chairs %}
<div class="column col-6 col-md-6 col-sm-12">
  <a class="card" href="{{person.url}}">
    <div class="card-image">
      <img src="/images/people/{{person.image}}" class="img-responsive">
    </div>
    <div class="card-header">
      <div class="card-title h5">{{person.title}} {{person.firstname}} {{person.lastname}}</div>
      <div class="card-subtitle text-gray">{{person.institution}}</div>
    </div>
    {% if person.lead != "false" %}
    <div class="card-body">
      {{person.lead}}
    </div>
    {% endif %}
  </a>
</div>
{% endfor %}
</div>
### Mitglieder:
<ul>
{% for person in site.data.members %}
  <li>{{ person.title }} {{ person.firstname }} {{ person.lastname }} ({{ person.institution }})</li>
{% endfor %}
</ul>