---
layout: page
lang: en
title: CartoHack
shortTitle: CartoHack
parent: Events
trans: true
---

CartoHack is a virtual format, which runs alternating to the DGfK's CartoCafé. The format CartoHack focusses on hands-on tutorials, demos and real world use cases. We are excited to hear what you would like to present. Proposals for talks can be submitted at any time (<a href="mailto:sebastian.meier@hcu-hamburg.de">sebastian.meier@hcu-hamburg.de</a>).

### Upcoming Events
<ul class="eventlist">
{% assign event_count = 0 %}
{% assign today = "now" | date: "%Y-%m-%d" %}
{% assign events = site.data.cartohack | sort: "date" %}
{% assign current_events = events | where_exp:"event", "event.date >= today" %}
{% for event in current_events %}
  <li>
    CartoHack #{{event.num}} - {{event.date | date: "%d.%m.%Y"}} / {{ event.time }}<br />
    <strong>{{ event.topic }}</strong>
    {{ event.speaker }}
    {% if event.video_url %}<br />
    <a href="{{event.video_url}}" class="btn">Video-link {% if event.video_pass %}(Password: {{ event.video_pass }}) {% endif %}&raquo;</a>
    {% endif %}
    {% if event.url %}<br />
    <a href="{{event.url}}" class="btn">Read more &raquo;</a>
    {% endif %}
  </li>
  {% capture event_count %}{{ event_count | plus:1 }}{% endcapture %}
{% endfor %}
{% if event_count == 0 %}
  <li>No upcoming events at the moment.</li>
{% endif %}
</ul>

{% assign events = events | reverse %}

### Event Archive
<ul class="eventlist">
{% assign today = "now" | date: "%Y-%m-%d" %}
{% assign past_events = events | where_exp:"event", "event.date < today" %}
{% for event in past_events %}
  <li>
    CartoHack #{{event.num}} - {{event.date | date: "%d.%m.%Y"}}<br />
    <strong>{{ event.topic }}</strong>
    {{ event.speaker }}
    {% if event.url %}<br />
    <a href="{{event.url}}" class="btn">Read more &raquo;</a>
    {% endif %}
  </li>
{% endfor %}
</ul>

### Organizers

- __<a href="https://tu-dresden.de/bu/umwelt/geo/ifk/das-institut/beschaeftigte/dirk-burghardt">Dirk Burghardt</a>__<br />Technical University Dresden
- __<a href="https://tu-dresden.de/bu/umwelt/geo/ifk/das-institut/beschaeftigte/mathias-groebe">Mathias Gröbe</a>__<br />Technical University Dresden
- __<a href="">Johannes Kröger</a>__<br />
- __<a href="">Franziska Martin</a>__<br />
- __<a href="https://www.sebastianmeier.eu">Sebastian Meier</a>__<br />HafenCity University Hamburg