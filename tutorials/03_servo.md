# Servo

## Einführung @showdialog

Schaltplan Servo:

![Schaltplan Servo](https://philipphgerber.github.io/tutorials-x2-next/docs/static/tutorials/03_servo.png)


## Variabe für den Servomotor @unplugged

Erstelle eine Variabele ``||variables:servo||``.

``||variables:Setze||`` die Variable ``||variables:servo||`` ``||basic:beim Start||`` auf ``||variables:0||``.


```blocks
```
```block
servo = 0
```

## Variabe für den Servomotor 

Erstelle eine Variabele ``||variables:servo||``.

``||variables:Setze||`` die Variable ``||variables:servo||`` ``||basic:beim Start||`` auf ``||variables:0||``.


```blocks
servo = 0
```


## Servo auf Pin 1 @unplugged

Setze ``||basic:dauerhaft||``  den ``||pins:Pin P1||`` auf den Wert von ``||variables:servo||``.

```block
basic.forever()
```
```block
pins.servoWritePin(AnalogPin.P1, servo)
```

## Servo auf Pin 1 

Setze ``||basic:dauerhaft||``  den ``||pins:Pin P1||`` auf den Wert von ``||variables:servo||``.

```blocks
basic.forever(function () {
    pins.servoWritePin(AnalogPin.P1, servo)
})
```


## Auf und zu @unplugged

Wenn ``||input:Knopf A+B||`` **zusammen** geklickt werden, dann soll der Servomotor auf oder zu gehen.
Wenn der Servomotor offen ist (``||logic:servo > 0||``), dann setze  ``||variables:servo||`` auf den Wert ``||variables:0||``.
Ansonsten setze ``||variables:servo||`` auf den Wert ``||variables:0||``.

```block
input.onButtonPressed(Button.AB, function () {})
```
```block
if (servo > 0) {} else {}
```
```block
servo = 0
```
```block
servo = 180
```

## Auf und zu

Wenn ``||input:Knopf A+B||`` **zusammen** geklickt werden, dann soll der Servomotor auf oder zu gehen.
Wenn der Servomotor offen ist (``||logic:servo > 0||``), dann setze  ``||variables:servo||`` auf den Wert ``||variables:0||``.
Ansonsten setze ``||variables:servo||`` auf den Wert ``||variables:0||``.

```blocks
input.onButtonPressed(Button.AB, function () {
    if (servo > 0) {
        servo = 0
    } else {
        servo = 180
    }
})
```

## Schrittweise öffnen @unplugged

Jedesmal wenn ``||input:Knopf B||`` geklickt wird, soll der Servo um ``||variables:10||`` Schritte geöffnet werden.
Der Wert darf dabei nicht grösser als ``||variables:180||`` werden.

```block
input.onButtonPressed(Button.B, function () {})
```
```block
servo = Math.min(180, servo + 10)
```

## Schrittweise öffne

Jedesmal wenn ``||input:Knopf B||`` geklickt wird, soll der Servo um ``||variables:10||`` Schritte geöffnet werden.
Der Wert darf dabei nicht grösser als ``||variables:180||`` werden.

```blocks
input.onButtonPressed(Button.B, function () {
    servo = Math.min(180, servo + 10)
})
``` 

## Schrittweise schliessen @unplugged

Jedesmal wenn ``||input:Knopf A||`` geklickt wird, soll der Servo um ``||variables:10||`` Schritte geschlossen werden.
Der Wert darf dabei nicht kleiner als ``||variables:0||`` werden.

```block
input.onButtonPressed(Button.A, function () {})
```
```block
servo = Math.max(0, servo - 10)
```

## Schrittweise schliessen

Jedesmal wenn ``||input:Knopf A||`` geklickt wird, soll der Servo um ``||variables:10||`` Schritte geschlossen werden.
Der Wert darf dabei nicht kleiner als ``||variables:0||`` werden.

```blocks
input.onButtonPressed(Button.A, function () {
    servo = Math.max(0, servo - 10)
})
```

## Fertiges Projekt testen

Teste dein Programm zuerst im Simulator und dann mit einem Mico:bit.


<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
