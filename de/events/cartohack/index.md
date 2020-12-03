---
layout: page
lang: de
title: CartoHack
shortTitle: CartoHack
parent: Veranstaltungen
trans: true
---

CartoHack ist ein virtuelles Format, welches im Wechsel zum CartoCafé der DGfK organisiert wird. Mit dem Format CartoHack versuchen wir den Fokus auf praktische Tutorials, Demos und Anwendungsbeispiele zu legen. Wir freuen uns jeder Zeit über Einreichungen von Vortragsvorschlägen (<a href="mailto:sebastian.meier@hcu-hamburg.de">sebastian.meier@hcu-hamburg.de</a>).

### Nächste Veranstaltungen
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

{% assign events = events | reverse %}

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

### Organisator*innen

- __<a href="https://tu-dresden.de/bu/umwelt/geo/ifk/das-institut/beschaeftigte/dirk-burghardt">Dirk Burghardt</a>__<br />Technische Universität Dresden
- __<a href="https://tu-dresden.de/bu/umwelt/geo/ifk/das-institut/beschaeftigte/mathias-groebe">Mathias Gröbe</a>__<br />Technische Universität Dresden
- __<a href="">Johannes Kröger</a>__<br />
- __<a href="">Franziska Martin</a>__<br />
- __<a href="https://www.sebastianmeier.eu">Sebastian Meier</a>__<br />HafenCity Universität Hamburg