# Servo

## Einführung @unplugged

Schaltplan Servo:

![Schaltplan Servo](https://philipphgerber.github.io/tutorials-x2-next/docs/static/tutorials/03_servo.png)


## Variabe für den Servomotor

Erstelle eine Variabeln **servo**.

Setzte die Variablen **servo** beim Start auf **0**.


``[let servo = 0 ]``

```blocks
let servo = 0
```

## Servo auf Pin 1

Setze dauerhaft den **Pin 1** auf den Wert von **servo**.

``[basic.forever()]``

``[pins.servoWritePin(AnalogPin.P1, servo)]``


```blocks
basic.forever(function () {
    pins.servoWritePin(AnalogPin.P1, servo)
})
```

## Auf und zu

Wenn **Knopf A und B zusammen** gedrückt wird, dann soll zu oder auf gehen.
Wenn der Servomotor offen ist ist (**servo > 0**), dann setze  **servo** auf **0**.
Ansonsten setze **servo** auf **180**.

``[if (servo > 0) {} else {}]``

``[let servo = 0 ]``

``[let servo = 180 ]``


```blocks
input.onButtonPressed(Button.AB, function () {
    if (servo > 0) {
        servo = 0
    } else {
        servo = 180
    }
})
```

## Schrittweise öffnen

Jedesmal wenn **Knopf B** gedrückt wird, soll der Servo um 10 Schritte geöffnet werden.
Der Wert darf dabei nicht grösser als **180** werden.

``[servo = Math.min(180, servo + 10))]``

```blocks
input.onButtonPressed(Button.B, function () {
    servo = Math.min(180, servo + 10)
})
```

## Schrittweise schliessen

Jedesmal wenn **Knopf A** gedrückt wird, soll der Servo um 10 Schritte geschlossen werden.
Der Wert darf dabei nicht kleiner als **0** werden.

``[servo = Math.max(0, servo - 10)]``

```blocks
input.onButtonPressed(Button.A, function () {
    servo = Math.max(0, servo - 10)
})
```

## Fertiges Projekt testen

Teste ein Programm zuerst im im Simulator und dann mit einem Mico:bit.


<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
