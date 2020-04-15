---
date: 2020-03-11
title: Feinstaubsensor
categories: Sensoren
description: Feinstaubsensor SDS011
type: Document
resources:
  - name: Shop
    link: https://sensebox.kaufen/product/feinstaub-sds011
  - name: Datenblatt NOVA SDS011
    link: https://cdn-reichelt.de/documents/datenblatt/X200/SDS011-DATASHEET.pdf
---

Mit diesem Sensor SDS011 ist es möglich die Feinstaubkonzentration in der Luft zu bestimmen. Der Sensor gibt zwei Werte aus: Die Konzentration von PM2.5 (Partikel < 2.5 um) und PM10 (Partikel < 10 um). Dieser Sensor ist mit einem kleinen Ventilator ausgestattet, um Luft anzusaugen. In seinem Inneren befindet sich ein Laser, der zusammen mit einer Photodiode die Anzahl der Partikel misst. Die Ergebnisse der Messungen werden in µg/m³ (Mikrogramm pro Kubikmeter) angegeben.

![Feinstaubsensor für PM10 und PM2.5](https://github.com/sensebox/resources/raw/master/gitbook_pictures/feinstaub_top.png)

## Technische Details
* "Plug-in-and-Go" senseBox kompatibel
* Schnelle Reaktionszeit von weniger als 10 Sekunden
* Hohe Auflösung bis zu 0.3µg/m3
* Mehrfach wissenschaftliche Prüfung der Datengenauigkeit

## Programmierung (Arduino)

Ist dies erledigt können wir nun im Programmcode den Sensor initialisieren und uns die ersten Messwerte ausgeben lassen.

Als erstes muss eine Instanz des Sensors erstellt werden. Dazu erstellen wir noch 2 Variablen in denen wir unsere beiden Messwerte für PM10 und PM2.5 speichern.

```arduino
#include "SenseBoxMCU.h"
#include <SPI.h>
#include <Wire.h>

SDS011 my_sds(Serial1) // Serial1 gibt hier den Seriellen Port an, an dem du den Sensor angeschlossen hast
float p10,p25

```arduino
void setup(){
    // Normalen seriellen Port initialisieren 
    Serial.begin(9600);
    while(!Serial);
    // Seriellen Port an dem unsere Sensor angeschlossen ist initialisieren
    Serial1.begin(9600);
    delay(5000);
}

void loop(){
    // Variablen den gemessenen Feinstaubwerte zuweisen
    p10 = my_sds.getPm10();
    p25 = my_sds.getPm25();
    //Werte in der Konsole drucken
    Serial.println("P2.5: "+String(p25));
    Serial.println("P10:  "+String(p10));
    delay(1000);
}
```

## Programmierung (Blockly)
