# WRO-Auto-BackyardBuilders
Content
---
...

Einleitung:
---

Zunächst haben wir das Auto aufgebaut auf Basis von Fischertechnik. Ausgestattet mit einem Fischertechnik Servo zur Lenkung ,einem rotem Encoder Motor und einem  Differential Antrieb an der Hinterachse.
Zur Steuerung haben wir einen Fischertechnik TXT Controller mit einem I2C Leveschifter und einem I2C Servoadapter eingesetzt. Der Servoadapter bekommt per I2c die Werte 63-125 und steiert dementsprechend den Servo von 63-125 an. Es ist somit nicht möglich zb. die Position 30 zu ereichen. Der TXT-Controller lässt sich in Fischertechnik Robopro programmieren.

Der Fischertechnik Servo ging sehr schnell kaputt. Daher sind wir auf baugleichen Micro Servo SG90 (https://www.roboter-bausatz.de/p/sg90-9g-micro-servomotor) umgestiegen. Den roten encoder Motor haben wir durch einen stärkeren und etwas schnelleren schwarzen Encoder Motor von Fischertechnik ersetzt. Um die erste Aufgabe zu lösen orientiren wir uns an der inneren Begrenzung.

Bei der Fahrt im Uhrzeigersinn Treht sich der Motor dauerhaft vorwärts. Dabei misst der Rechte Ultraschallsensor dem Abstannd zur inneren Wand. Ist dieser =15 steuert der Servo die Position 91 an. Eigentlich währe zwar 94 die Mitte aber der Servo ist nicht genau mittig mit der Radachse verbunden. Ist der Wert des Ultraschallsensors <15 steuert der Servo die Position 81 (leichte linkskurve) an. Wenn der Wert >15 ist, steuert der Servo die Position 99 (leichte Rechtskurve) an. So fährt das Auto mit leichten kurven an der Wand entlang. Ist der Linke Ultraschallsensor dann aber >60 steuert der Servo die Position 123 (starke Rechtskurve) an, wartet dan biss der Wert wieder <= 15 ist und beginnt von vorne.

Bei der Fahrt gegen den Uhrzeigersinn Treht sich der Motor ebenfalls dauerhaft vorwärts. Dabei misst der Linke Ultraschallsensor dem Abstannd zur inneren Wand. Ist dieser =15 steuert der Servo die Position 91 an. Ist der Wert des Ultraschallsensors <15 steuert der Servo die Position 100 (leichte Rechtskurve) an. Wenn der Wert >15 ist, steuert der Servo die Position 82 (leichte Linkskurve) an. So fährt das Auto mit leichten kurven an der Wand entlang. Ist der Rechte Ultraschallsensor dann aber >60 steuert der Servo die Position 63 (starke Linkskurve) an, wartet dan biss der Wert wieder <= 15 ist und beginnt von vorne.


Um die zweite Aufgabe zu lösen...