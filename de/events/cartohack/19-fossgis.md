---
layout: page
lang: de
title: "CartoHack #19 – OSM-basierte Karten mit QGIS und PostGIS erstellen"
shortTitle: "CartoHack #19"
parent: CartoHack
trans: true
redirect_from:
  - "/en/events/cartohack/19-fossgis"
---

Mathias Gröbe<br />

<a href="https://streaming.media.ccc.de/">streaming.media.ccc.de, live von der FOSSGIS 2024</a>

Die Arbeitsschritte für die Herstellung einer typischen OSM-basierte Karte im Maßstab 1:10.000 bis 1:100.000 gleichen sich im Wesentlichen: Es müssen Daten von OpenStreetMap aufbereitet, generalisiert und signaturiert werden. Die typischen benötigten Ebenen wie Gewässer, Straßen, Gebäude und Verwaltungsgrenzen bleiben dabei Konstanten. Das Projekt "Graubrot" bietet hierfür eine Ausgangsbasis mit einer Konfiguration für osm2pgsql für den Datenimport, einem Datenschema in PostgreSQL/PostGIS und einer ersten Visualisierung in QGIS. Beispiele für Generalisierungen der Ebenen liegen bei und können bei Bedarf angepasst werden. Ebenfalls wird die Möglichkeit von Aktualisierungen und gleichzeitiger Anpassung von Objekte thematisiert.