---
layout: page
lang: de
title: CartoHack
shortTitle: CartoHack
parent: Veranstaltungen
trans: true
---

### Scope
Bald mehr...

### Nächste Veranstaltungen
<ul class="eventlist">
{% assign event_count = 0 %}
{% assign today = "now" | date: "%Y-%m-%d" %}
{% assign events = site.data.cartohack | sort_natural: "date" | reverse %}
{% assign current_events = events | where_exp:"event", "event.date >= today" %}
{% for event in current_events %}
  <li>
    CartoHack #{{event.num}} - {{event.date | date: "%d.%m.%Y"}}<br />
    <strong>{{ event.topic }}</strong>
    {{ event.speaker }}
    {% if event.video_url %}<br />
    <a href="{{event.video_url}}" class="btn">Video-Link {% if event.video_pass %}(Passwort: {{ event.video_pass }}) {% endif %}&raquo;</a>
    {% endif %}
    {% if event.url %}<br />
    <a href="{{event.url}}" class="btn">Mehr erfahren &raquo;</a>
    {% endif %}
  </li>
  {% capture event_count %}{{ event_count | plus:1 }}{% endcapture %}
{% endfor %}
{% if event_count == 0 %}
  <li>Im Augenblick gibt es leider keine anstehenden Veranstaltungen.</li>
{% endif %}
</ul>

### Veranstaltungsarchiv
<ul class="eventlist">
{% assign today = "now" | date: "%Y-%m-%d" %}
{% assign past_events = events | where_exp:"event", "event.date < today" %}
{% for event in past_events %}
  <li>
    CartoHack #{{event.num}} - {{event.date | date: "%d.%m.%Y"}}<br />
    <strong>{{ event.topic }}</strong>
    {{ event.speaker }}
    {% if event.url %}<br />
    <a href="{{event.url}}" class="btn">Mehr erfahren &raquo;</a>
    {% endif %}
  </li>
{% endfor %}
</ul>