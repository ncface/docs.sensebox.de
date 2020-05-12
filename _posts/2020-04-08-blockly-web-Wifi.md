---
date: 2020-04-07
title: Web - WiFi
title_order: 5
categories: Blockly
description: Erste Schritte Web
type: Document
set: blockly-erste-schritte
set_order: 5
resources:
  - name: "Blockly.senseBox.de"
    link: https://blockly.sensebox.de
image1: /images/2020-04-08-blockly-web/blockly-Web-Wifi-1.svg
image2: /images/2020-04-08-blockly-web/blockly-Web-Wifi-2.svg


---

## Allgemeines
In Blockly hast du die verschieden Möglichkeiten Projekte umzusetzen, die mit dem Internet arbeiten. Für alle musst du deine senseBox zuerst mit den Internet verbinden.

## WiFi
Mit dem `Verbinde mit WLAN`-Block kannst du deine senseBox im Setup() mit einem WLAN-Netzwerk verbinden. Unter SSID muss der Netzwerkname und unter Passwort das WLAN-Zugangspasswort eingegeben werden.

{% include image.html image=page.image1 %}
<br>
Mit dem `Initialisiere WLAN Access Point`-Block kann deine senseBox ein WLAN-Netzwerk erstellen, in welches du mit anderen Geräten beitreten kannst. Im Textfeld SSID kannst du den Names deines Netzwerks festlegen.

{% include image.html image=page.image2 %}