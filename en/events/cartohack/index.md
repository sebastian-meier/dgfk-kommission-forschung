---
layout: page
lang: en
title: CartoHack
shortTitle: CartoHack
parent: Events
trans: true
---

### Scope
Soon more...

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