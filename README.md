# WRO-Auto-BackyardBuilders
Einleitung:
---

Zunächst haben wir das Auto aufgebaut auf Basis von Fischertechnik. Ausgestattet mit einem Fischertechnik Servomotor für den Antrieb und zur Lenkung einem rotem Encoder-Motor und einem Differentialantrieb an der Hinterachse. Zur Steuerung haben wir einen Fischertechnik TXT Controller mit einem I2C Leveschifter und einem I2C Servoadapter eingesetzt. Der Servoadapter bekommt per I2c die Werte 63-125 und steuert dementsprechend den Servo von 63-125 an. Es ist somit nicht möglich z.B. die Position 30 zu erreichen. Der TXT-Controller lässt sich mit dem Programm Fischertechnik Robopro programmieren.

Der Fischertechnik Servomotor war schon nach kurzer Zeit defekt. Daher sind wir auf baugleichen Micro Servomotor SG90 (https://www.roboter-bausatz.de/p/sg90-9g-micro-servomotor) umgestiegen. Den roten Encoder-Motor haben wir durch einen stärkeren und etwas schnelleren schwarzen Encoder-Motor von Fischertechnik ersetzt.

Aufgabe 1:
    stand: 02.07.2022
     Wird das Auto nah an der inneren Begrenzung gestartet orientiert es sich mithilfe des linken oder rechten           Ultrschallsensors  (je nach Fahrtrichtung) an der inneren Begrenzung. Wird es aber aussen gestartet orientiert es sich auch aussen. Somit ist das Problem mit dem anfänglichen Ausrichten gelöst.

    Bei der Fahrt im Uhrzeigersinn dreht sich der Motor dauerhaft vorwärts. Dabei misst der rechte Ultraschallsensor dem Abstand zur inneren Wand. Ist dieser =15 steuert der Servo die Position 91 an. Eigentlich währe zwar 94 die Mitte aber der Servo ist nicht genau mittig mit der Radachse verbunden. Ist der Wert des Ultraschallsensors <15 steuert der Servo die Position 81 (leichte Linkskurve) an. Wenn der Wert >15 ist steuert der Servo die Position 99 (leichte Rechtskurve) an. So fährt das Auto mit leichten Kurven an der Wand entlang. Ist der linke Ultraschallsensor dann aber >60 steuert der Servo die Position 123 (starke Rechtskurve) an, wartet dann bis der Wert wieder <= 15 ist und beginnt von vorne.

    Bei der Fahrt gegen den Uhrzeigersinn dreht sich der Motor ebenfalls dauerhaft vorwärts. Dabei misst der linke Ultraschallsensor dem Abstand zur inneren Wand. Ist dieser =15 steuert der Servo die Position 91 an. Ist der Wert des Ultraschallsensors <15 steuert der Servo die Position 100 (leichte Rechtskurve) an. Wenn der Wert >15 ist, steuert der Servo die Position 82 (leichte Linkskurve) an. So fährt das Auto mit leichten Kurven an der Wand entlang. Ist der rechte Ultraschallsensor dann aber >60 steuert der Servo die Position  63 (starke Linkskurve) an, wartet dann bis der Wert wieder <= 15 ist und beginnt von vorne.

Aufgabe 2:
    Wir hatten Servo-und Kamerausfall. Daher konten wir die Aufgabe leider nicht lösen.