# SymconHP

SymconHP ist eine Erweiterung für die Heimautomatisierung IP Symcon. Diese Erweiterung stellt eine Anbindung an den Homepiloten 1 oder 2 dar. Dabei ist zu beachtet, dass dieses Modul einige Konfiguration vornimmt, welche sich nicht ändern bzw. überschreiben lassen. Damit möchte ich sicher stellen, dass die Aktoren und Sensoren direkt Out-Off-The-Box funktionieren ohne weitere Einrichtungen vornehmen zu müssen.

## Einrichtung

Die Einrichtung erfolgt über die Modulverwaltung von Symcon. Nach der Installation des Moduls sollte der Dienst neugestartet werden. Jetzt kann eine neue Instanz vom Typ "_Homepilot Bridge_" angelegt und konfiguriert werden. Nach dem Starten des "Gräte abgleichs", wird für jeden Aktor (Knoten) oder Sensor eine Instanz in der angegebenen Kategorie bzw. jede Gruppe in der angegebenen Gruppenkategorie angelegt. Ihr müsst somit **nicht** selber für jeden Knoten eine Instanz anlegen.

## Einstellungen

* **Host**  _Der Hostname bzw. die IP-Adresse des Homepiloten_
* **Homepilot Version**  _Firmware Basisversion des Hompiloten 3&4 / 5_
* **Interval**  _In welchem Abstand soll der Status abgeglichen werden_
* **Homepilot-Knoten**  _In der ausgewählten Kategorie werden die Knoteninstanzen bereit gestellt_
* **Homepilot-Sensoren**  _In der ausgewählten Kategorie werden die Sensorinstanzen bereit gestellt_

**Schalter**

* **Geräte abgleichen** _Es werden für jeden, im Hompiloten angemeldeten Knoten (Aktor) oder Sensor, eine Instanz in der jeweiligen Kategorie angelegt._
* **Status abgleichen** _Manueller Abgleich des Status aller Knoten/Sensoren_

**Linearisierung der Positionen**

Da die prozentualen Positionen der RolloTron Gurtwickler in der Regel nicht mit den realen Positionen der Rollade übereinstimmen gibt es die Möglichkeit die Position durch 3 Stützpunkte zu liniarisieren. Hierzu fährt man die realen Rollladenpositionen 25%, 50% und 75% an und notiert sich die angezeigten Prozentwerte. Dannach werden die notierten Werte in die Konfiguration der einzelnen Knoten eingetragen. Nach der Übernahme der Konfiguration werden die Werte bei der Anzeige und Ansteuerung entsprechend liniarisiert. D.h. möchte man die Rollade zu 50% schließen muss man den Wert nun auch 50% vorgeben.

## Voraussetzung

* Rademacher Homepilot 1 oder 2.
* Firmwaregrundversion 3, 4, oder 5
* ab Symcon Version 5

## Änderungen

### Version 3.18 ###
*  Name und Parent ID von Knoten und Sensoren nur dann ändern wenn sie nicht bereits gesetzt worden sind
 
### Version 3.17 ###
*  IPS_ApplyChanges wird nur noch aufgerufen wenn IPS_HasChanges true zurück liefert - dadurch müssten die häufigen Logmeldungen entfallen

### Version 3.16 ###
*  Anpassungen für IP Symcon Version 7

### Version 3.15 ###
*  Ab einem Batterie Level kleiner gleich 5% wird der Batterie Low Status gesetzt, falls er noch nicht gesetzt war

### Version 3.14 ###
*  Interner Typ 15 Rauchmelder sollte nun anzeigen ob Rauch erkannt wurde, Batterie Status und Level sollten nun auch bei HP Firmwareversion angezeigt werden

### Version 3.13 ###
*  Interner Typ 14 Heizkörperstellantrieb wird nun auch korrekt im Device Formular angezeigt
 
### Version 3.12 ###
*  23782076 / DuoFern RollTube S-Line Sun für HP Version 5 unterstützt

### Version 3.11 ###
*  36500572_A / Duofern Troll Comfort 5665 für HP Version 5 unterstützt

### Version 3.10 ###
*  Heizkörperstellantrieb Sollwerte müssen für den Homepiloten ab Version 5 mit Nachkommastellen geschickt werden

### Version 3.09 ###
*  Heizkörperstellantrieb wird nun unterstützt

### Version 3.08 ###
* DuoFern Raumthermostat Solltemperatur wurde in Homepilot Version 5 nicht unterstützt, Device 32501812_S und 32501812_A wurde für Homepilot 5 noch nicht unterstützt

### Version 3.07 ###
* hat ein Autor oder ein Sensor einen Batteriestatus wird der nun auch in IP Symcon angelegt

### Version 3.06 ###
* der Fensterkontakt hat beim Homepiloten Version 5 nun alle drei möglichen Zustände

### Version 3.05 ###
* der Fensterkontakt sollte nun auch für den Homepiloten Version 5 wieder funktionieren 
* Debuging für eine Instanz landet nun auch im Instanzfenster 

### Version 3.04 ###
* für Debug wird  un das Standard Debug Fenster der Instanzen genutzt 

### Version 3.03 ###
* BugFix im Instanz Dialog für die Knoten. Die Linearisierungswerte werden nun als Integerwerte verarbeitet und auf Min/Maxwerte geprüft 
 
### Version 3.02 ###
* Geräte mit did 1 sollten nun auch funktionieren

### Version 3.01 ###
* Debug Option hinzugefügt

### Version 3.00 ###
* Unterstützung des neuen Homepiloten Api ab Firmwareversion 5.0 Die genutzte Version muss in der Bridge als Parameter eingestellt werden.

### Version 2.01 ###
* Kommafehler behoben, die Modulkonfiguration konnte nicht mehr geladen werden

### Version 2.00 ###
* Korrekturen zur Unterstützung von IP Symcon 5. Damit ist das modul nicht mehr zu Version 4 kompatibel!!

### Version 1.13 ###
* Troll Basis und Troll Comfort wurden in einigen Funktionen nicht korrekt unterstützt

### Version 1.12 ###
* Troll Basis wird unterstützt
 
### Version 1.11 ###
* Troll Comfort wird unterstützt

### Version 1.10 ###
* Raumthermostat Relaisstatus wird ausgelesen

### Version 1.9 ###
* Raumthermostat Relais und Sollwert werden unterschieden

### Version 1.8 ###
* Raumthermostat wird als Aktor unterstützt

### Version 1.7 ###
* kleiner Fehlerkorrekturen

### Version 1.6 ###
* Universal-Aktor unterstützt
* Sensorwerte 'Rauch', 'Batterie-Status', 'Aktueller Sollwert', 'Schließer' und 'HomePilot-Zone' werden unterstützt

### Version 1.5 ###
* Connect-Aktor und RolloTube unterstützt

### Version 1.4 ###
* SX5 Garagentorantrieb unterstützt
 
### Version 1.3 ###
* Der Bewegungsmelder / Aktor 9484 wird nun voll unterstützt

## Funktionen

	// Abgleich aller Knoten
	HP_SyncDevices(int $bridgeId);

	// Abgleich des Status aller Knoten
	HP_SyncStates(int $bridgeId);

	// Liefert zu einer UniqueID die passende Lampeninstanz
	HP_GetDeviceByUniqueId(int $bridgeId, int $uniqueId);


	// Aktualisierung der Daten eines Knotens (Aktors)
	// Parameter ist ein JSON string der alle Daten des Aktors beinhaltet
	HP_ApplyJsonData( int $instanzId, string $jsonString )
	
	// Aktualisierung der Daten eines Sensors
	// Parameter ist ein JSON string der alle Daten des Sensors beinhaltet
	HPSensor_ApplyJsonData( int $instanzId, string $jsonString )
	

	// Liefert zu einer UniqueID die passende Sensorinstanz
	HPSensor_GetDeviceByUniqueId(int $bridgeId, int $uniqueId);

	// Abgleich des Status eines Knoten (HP_SyncStates sollte bevorzugewerden,
	// da direkt alle Aktoren abgeglichen werden mit nur 1 Request zur Homepiloten)
	HP_RequestData(int $lightId);
	HPSensor_RequestData(int $lightId);

	// Mögliche Keys (ja nach Typ unterschiedlich):
	// _______________ Schaltaktor _________________
	// SWITCH         -> true oder false für an/aus
	//
	// _______________ RolloTron / Rohraktor _______
	// SHUTTER        -> true oder false für geschlossen/offens
	// SHUTTERPOS     -> Werte für eine Rollladenposition zwichen 0 und 100%
	// SHUTTERCMD     -> Werte für eine Rollladenposition zwichen 0 und 100% in 25% Schritten
	// AUTOMATIC      -> true oder false für Automatik an/aus
	//
	// _______________ Dimmer ______________________
	// DIMMERSTATE    -> true oder false für an/aus
	// DIMMERPOS      -> Werte für eine Helligkeit zwichen 0 und 100%
	// DIMMERCMD      -> Werte für eine Dimmerposition zwichen 0 und 100% in 25% Schritten
	//
	// _______________ Raumthermostat ______________
	// DESTTEMP      -> Werte für die Raumthermostat Solltemperatur zwichen 4°C und 40°C
	// RELAISSTATE   -> Relaisstatus des Schaltrelais true oder false für an/aus
	//

	// Liefert einen Knotenparameter je nach Parameter (s.o.)
	HP_GetValue(int $lightId, string $key);
			
	// Mögliche Keys (ja nach Typ unterschiedlich):
	// _______________ Für Sensoren ________________
	// SUN            -> Sonne erkannt / nicht erkannt
	// RAIN           -> Regen erkannt / nicht erkannt
	// SMOKE          -> Rauch erkannt / nicht erkannt
	// MOTION         -> Bewegung erkannt / nicht erkannt
	// BATTERIE       -> Batteriestatus von 0-100%
	// TEMPERATUR_NOM -> aktuelle Solltemperatur in °C
	// HP_ZONE        -> HompilotZone abwesend / anwesend
	// SHUTTER        -> Schliesser offen / geschlossen
	// LUX            -> Lichtwert in Lux
	// WIND           -> Windgweschwindigkeit in m/s
	// TEMPERATURE    -> Temperatur in Grad C
	// SUNHEIGHT      -> Sonnehöhe in Grad
	// SUNDIRECTION   -> Sonnenrichtung in Grad
	// ACTTIME        -> Aktualisierungszeit als string
	
	// Liefert einen Sensorparameter je nach Parameter (s.o.)
	HPSensor_GetValue(int $lightId, string $key);
	
	// Staus setzen: Ein/Aus geschlossen/offen
	HP_SetState(int $lightId, bool $value)
	HP_GetState(int $lightId)
	
	// Position setzen (Werte zwichen 0 - 100%)
	// Solltemperatur vorgeben (4-40°C)
	HP_SetPosition(int $lightId, float $value)
	HP_GetPosition(int $lightId)
	
	// Automatik Ein/Ausschalten
	HP_SetAutomatic(int $lightId, bool $value)
	HP_GetAutomatic(int $lightId)

	// Lampe einschalten (Richtung 100%), Rollladen runterfahren (Richtung 0%)
	HP_DirectionUp(int $lightId)
	// Dimmvorgang stoppen, Rollladen stoppen
	HP_DirectionStop(int $lightId)
	// Lampe ausschalten (Richtung 0%), Rollladen runterfahren (Richtung 100%)
	HP_DirectionDown(int $lightId)
