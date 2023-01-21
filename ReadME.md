# AT-USE-CASE Klient Gerald Schlafzimmer
## Aufgabenstellung
Die Aufgabenstellung war es, verschiedene Funktionen für Gerald zu erstellen, damit es ihm 
aufgrund seiner Beeinträchtigungen dennoch möglich ist einige Dinge zu tun können.
Gerald ist körperlich stark eingeschränkt und hat eine Hörbeeinträchtigung. Er kann zwar Klänge
wahrnehmen, allerdings ist er auf Hilfe angewiesen. Er möchte dennoch in der Lage sein,
seine Umgebung zu steuern, im Internet surfen können und mit Freunden kommunizieren können.
Zusammenfassend möchte er folgende Sachen machen können:
- Umgebungssteuerung
  - Steuerung des Lichtes und der Temperatur
  - Spielzeug (Roboter)
- Computer
  - im Internet surfen
  - E-Mails schreiben
  - Visuals erzeugen
  - SMS schreiben
  - Telefonieren
  

Gerald hat noch folgende Fähigkeiten:
- rechter Arm kann leicht gehoben werden, allerdings keine Handfunktion
- große Zähe links
- Kopf und Augen 
- non-verbal
- Mund, Lippen, Saugen, Pusten

Als Anforderung soll das Betriebssystem accessible sein, zwei verschiedene Eingabegeräte
verwendet werden, eine realistische Montage und eine Durchführung eines FittsTask2D gemacht
werden.
## Teammitglieder
- Markus Dvornikovich
- Stefan Pabisch
- Sejla Zukic

## Verwendete Eingabegeräte
- Augensteuerung
- FABI
- IR Trans

## Durchführung
Um die Aufgabe durchführen zu können, werden vier Programme benötigt: OpenHAB, FABI
Configuration, Asterics Configuration Suite und ARE<br>
Diese Programme werden laut Anleitungen auf Moodle heruntergeladen. <br>
Mithilfe der Augensteuerung, welche mithilfe des ARE-Modells bedient wurde, kann Gerald
alle Funktionen des Laptops steuern oder auch das Grid steuern, wenn er möchte. Die Grid
Steuerung wird allerdings vorrangig mithilfe von FABI gesteuert. Er kann entweder die 
Augensteuerung oder FABI benutzen, allerdings nicht gleichzeitig. Um zwischen den Modi zu
wechseln, muss Gerald seine Assistenz rufen, wofür es am Asterics Grid einen eigenen Button
gibt. Die ganzen Einstellungen und Konfigurationen werden im Folgenden beschrieben:

**Aterics Grid:** <br>
Nach korrektem herunterladen der Programme haben wir uns darum gekümmert, ein Asterics GRID
zu erstellen. Wir haben zwei Seiten erstellt, eine Startseite und eine Seite zur Steuerung
des Roboters. Diese sehen wie folgt aus:<br>

<img alt="Startseite Grid" height="200" src="/bilder/startseite_astericsgrid.png" title="Startseite Grid" width="400"/>
<img alt="Roboterseite Grid" height="200" src="/bilder/roboterseite_astericsgrid.png" title="Roboterseite Grid" width="400"/>

Ein neues Feld im Grid kann mit einem Rechtsklick auf ein leeres Feld erstellt werden. Im
Einstellungsmenü kann dann Name, Farbe und Aktion eingestellt werden. Um zum Beispiel das Licht
steuern zu können, muss eine Asterics Aktion erstellt werden. Dafür wird das ARE Modell 
heruntergeladen (ARE Modell Beschreibung folgt) und der zuständige Parameter zugewiesen. Die
Liste der notwendigen Parameter sieht wie folgt aus:
- Licht
  - Schlafzimmer Licht (Switch): Schlafzimmer_KNX_Licht_Schalten
- Temperatur
  - Temperatur in der Wohnung (Number): SOLL_Wohnung_Temp
  - Nachtabsenkung (Switch): Sem_Nachtabsenkung

<img alt="Asterics Grid Einstellungen" height="200" src="/bilder/astericsgrid_einstellungen.PNG" title="Asterics Grid Einstellungen" width="400"/>

Um den Roboter zu steuern, wurden die Funktionen der Roboter Fernbedienung mithilfe des IR
Trans programmiert. Dafür wurde die Konfigurationsdatei des IR Trans heruntergeladen. Um die
Funktionen mithilfe des Asterics Grid steuern zu können, ist es zuerst notwendig die Taste
der Fernbedienung zu drücken und danach die Programmiertaste im IR Trans Programm.

<img alt="Roboter" height="400" src="/bilder/roboter.jpg" title="Roboter" width="200"/>
<img alt="Fernbedienung Roboter" height="400" src="/bilder/fernbedienung_roboter.jpg" title="Fernbedienung Roboter" width="200"/>
<img alt="IR Trans" height="400" src="/bilder/irtrans.jpg" title="IR Trans" width="200"/>
<br>

**ARE und ACS:** <br>
Um alle Komponenten wie IR Trans, Asterics Grid, OpenHAB zu verbinden erstellten wir ein
ARE Modell. Dieses wurde in der Asterics Configuration Suite erstellt. Das ARE Modell wurde
von Moodle heruntergeladen. Die notwendigen Komponenten wurde, wie im nachfolgenden Bild
gezeigt, miteinander verbunden. Anschließend verbindet man sich mit der ARE und drückt den
Button "Start Model". Die Kameramaus wurde in der ARE gestartet, wie ebenfalls folgend im
Bild zu sehen ist.
<br>

<img alt="ACS Modell" height="400" src="/bilder/acs_model.png" title="ACS Modell" width="200"/>
<img alt="Arbeiten mit ACS" height="400" src="/bilder/acs_working.jpg" title="Arbeiten mit ACS" width="200"/>
<img alt="ARE Kameramaus" height="400" src="/bilder/are_cameramouse.png" title="ARE Kameramaus" width="200"/>
<br>

**FABI:** <br>
Den FABI kann man auf folgender [Seite](https://fabi.asterics.eu/index_fabi.htm) 
konfigurieren. Wir haben zwei Button Aktionen programmiert. Kurz Drücken und lang
gedrückt halten. Dies haben wir getan, um mithilfe des FABIs das Asterics Grid per Scanning
steuern zu können. Zudem haben wir den Schwellenwert für langes Drücken auf 500ms gestellt,
da das lange Drücken nicht zu lange dauern sollte, da es sonst für Gerald anstrengend werden
könnte. Die Konfigurationen sahen wie folgt aus:<br>
<img alt="FABI Konfiguration Slots" height="200" src="/bilder/fabiconf_slots.png" title="FABI Konfiguration Slots" width="400"/>
<img alt="FABI Konfiguration Timing" height="200" src="/bilder/fabiconf_timing.png" title="FABI Konfiguration Timing" width="400"/>
<br><br>

Abschließend wurde ein FittsTask2D Test durchgeführt. Dieser wurde nach Anleitung von Moodle
durchgeführt. Das Programm wurde installiert und anschließend wurde der Test gemacht. Es
wurde eine Zusammenfassung erstellt. Der Test bestand aus 9 Übungen, welche per Augensteuerung
durchgeführt wurden. Am Ende wurde ebenfalls das Beste und schlechteste Ergebnis ausgewählt.
Diese sehen wie folgt aus:<br>

<img alt="FittsTask Zusammenfassung" height="200" src="/bilder/fittstask_summary.png" title="FittsTask Zusammenfassung" width="400"/>
<img alt="FittsTask bestes Ergebnis" height="200" src="/bilder/fittstask_bestresult.png" title="FittsTask bestes Ergebnis" width="400"/>
<img alt="FittsTask schlechtestes Ergebnis" height="200" src="/bilder/fittstask_worstresult.png" title="FittsTask schlechtestes Ergebnis" width="400"/>
<br>

**Aufbau:**
<br>
Der Fabi Button wurde mithilfe einer Halterung am rechten Bettrand (aus der Sicht von Gerald)
montiert. Der Laptop befindet sich auf Bauchhöhe ebenfalls mit einer Halterung, welche
links und rechts am Bett befestigt ist. <br>

<img alt="FABI Halterung" height="400" src="/bilder/fabi_halterung.jpg" title="FABI Halterung" width="200"/>
<img alt="FABI Halterung Bett" height="400" src="/bilder/halterung_bett_fabi.jpg" title="FABI Halterung Bett" width="200"/>
<img alt="Laptop Montage 1" height="200" src="/bilder/laptop_montage.jpg" title="Laptop Montage 1" width="400"/>
<img alt="Laptop Montage 2" height="400" src="/bilder/laptop_montage2.jpg" title="Laptop Montage 2" width="200"/>
<br>

Die Heizsteuerung sieht wie folgt aus:<br>

<img alt="Heizsteuerung" height="400" src="/bilder/heizsteuerung.jpg" title="Heizsteuerung" width="200"/>
