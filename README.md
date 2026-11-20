# VEDA – Verkehrsdatenanalyse

Die Applikation ***VEDA** dient der statistischen Auswertung von Verkehrszähldaten sowie deren Darstellung als Diagramm und Tabelle. Resultate können direkt im Browser betrachtet, als PNG-Grafik oder CSV-Tabelle heruntergeladen oder als PDF gedruckt werden.
Der Fokus von VEDA liegt in der Bereitstellung von Grundlagendaten für Zwecke der Verkehrsplanung und richtet sich an Fachpersonen in der Verwaltung und Ingenieurbüros.

## Datenquellen
Das System kann unterschiedliche Datenquellen verarbeiten. Die in VEDA dargestellten Verkehrszähldaten werden aus offenen Datenquellen (Open Government Data) bezogen. Für die Richtigkeit, Genauigkeit und Aktualität der Daten sind die jeweiligen Dateneigentümer verantwortlich. Hinsichtlich Weiterbearbeitung und kommerzieller Nutzung gelten die Lizenzbedingungen der jeweiligen Dateneigentümer.

Bisher wurden Schnittstellen zu folgenden Datenquellen umgesetzt:

* **Open Data Zürich (OD2031):** Stundenwerte zum motorisierten Individualverkehr (MIV) aus dem Open-Data-Katalog der Stadt Zürich seit 2012 (https://data.stadt-zuerich.ch/dataset/sid_dav_verkehrszaehlung_miv_od2031)
* **DAV 3-Minuten-Messwerte:** Daten der LSA-Detektoren der Dienstabteilung Verkehr (Verkehrsstärke und Belegung) die für bereits abgeschlossene Jahre (seit 2018) als 3-Minutenmesswerte vorliegen.
* **KTZH VDP (vdpzh):** Kontinuierlicher Live-Stream resp. 5-Minuten-Intervall aller Messstellen des Kantons Zürich  (https://vdp.zh.ch/pws)

Die Integration weiterer Schnittstellen wie bspw. DATEX II ist in Bearbeitung.

### Systemkomponenten
VEDA besteht aus dem Statistik-Modul **vedastat** und dem Web-Frontend **vedaweb** und ist für den Betrieb auf einem LINUX-Server konzipiert.
**vedastat** Datenimport, Archivierung, Statistikberechnung und Export (python, shell/bash, sqlite3).
**vedaweb**  Webclient für Abfragen, Tabellen, Diagramme und Karten (HTML, CSS, PHP, JavaScript, MariaDB) .
***vedastat*** und ***vedaweb*** können auf separaten Servern eingerichtet werden.

### Darstellung der importierten Messwerte
Die Messwerte aus den Quellsystemen können über den Webclient ***vedaweb*** dargestellt und für die Weiterbearbeitung exportiert werden.

### Berechnete Jahresauswertungen
Aus den Messwerten der Quellsysteme berechnet **vedastat**  verschiedene statistische Auswertungen , die neben den Originammesswerten mit **vedaweb** dargestellt werden können.
* Tagesganglinien der Stundenwerte (aggregiert nach Wochentagen Mo, Di, Mi... und Tagesgruppen Mo--Fr, Di-Do, Mo-So)
* Dauerlinien der Stundenwerte (1.–300. Stunde)
* DTV und DWV nach im Jahresmittel sowie nach Monaten, Kalenderwochen und Wochentagen
* Entwicklung von DTV, DWV, MSP Mo-Fr, ASP Mo-Fr sowie der absoluten Spitzenstunde übere mehrere Jahre

VEDA ist so konzipiert, dass weitere Auswertungen ergänzt werden können.

