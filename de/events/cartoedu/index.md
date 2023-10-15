---
layout: page
lang: de
title: CartoEdu
shortTitle: CartoEdu
parent: Veranstaltungen
trans: true
---

CartoEdu ist ein virtuelles Format, welches im Wechsel zum CartoCafé der DGfK organisiert wird. Mit dem Format CartoHack versuchen wir den Fokus auf praktische Tutorials, Demos und Anwendungsbeispiele zu legen. Wir freuen uns jeder Zeit über Einreichungen von Vortragsvorschlägen (<a href="mailto:sebastian.meier@fh-potsdam.de">sebastian.meier@fh-potsdam.de</a>).

### Newsletter
Immer auf dem Laufenden über aktuelle, öffentliche Veranstaltungen der DGfK: <a href="https://newsletter.dgfk.net">Hier zum Newsletter anmelden.</a>

### Nächste Veranstaltungen
<ul class="eventlist">
{% assign event_count = 0 %}
{% assign today = "now" | date: "%Y-%m-%d" %}
{% assign events = site.data.cartoedu | sort: "date" %}
{% assign current_events = events | where_exp:"event", "event.date >= today" %}
{% for event in current_events %}
  <li>
    CartoEdu #{{event.num}} - {{event.date | date: "%d.%m.%Y"}} / {{ event.time }}<br />
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
    CartoEdu #{{event.num}} - {{event.date | date: "%d.%m.%Y"}}<br />
    <strong>{{ event.topic }}</strong>
    {{ event.speaker }}
    {% if event.url %}<br />
    <a href="{{event.url}}" class="btn">Mehr erfahren &raquo;</a>
    {% endif %}
  </li>
{% endfor %}
</ul>

### Ansprechpartner

- __Jochen Schiewe__<br />HafenCity Universität Hamburg