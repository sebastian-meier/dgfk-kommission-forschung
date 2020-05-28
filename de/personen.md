---
layout: page
title: Personen
parent: "Über uns"
---

### Steuerungsgruppe:
<div class="columns" id="persons">
{% for person in site.data.chairs %}
<div class="column col-6 col-md-6 col-xs-12">
  <div class="card">
    <div class="card-image">
      <img src="/images/person/{{person.image}}" class="img-responsive">
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
  </div>
</div>
{% endfor %}
</div>
### Mitglieder:
<ul>
{% for person in site.data.members %}
  <li>{{ person.title }} {{ person.firstname }} {{ person.lastname }} ({{ person.institution }})</li>
{% endfor %}
</ul>


### Nachlesen:
Kick-Off-Meeting der Kommission, am 9. März 2011, an der HafenCity Universität Hamburg
Aktivitäten der neuen Kommission. Die Ergebnisse sind unter den entsprechenden Rubriken dieser Website zusammengefasst worden und werden in Kürze auch in den Kartographischen Nachrichten publiziert.
<caption>Die Teilnehmer am KickOff-Meeting in Hamburg (Foto: Kinkeldey, HCU Hamburg)</caption>