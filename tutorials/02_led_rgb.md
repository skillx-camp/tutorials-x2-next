# Dreifarbige LED. 

```template
basic.forever()
```

## Einführung @showdialog

Schaltplan Dreifarbige LED:

![Schaltplan Dreifarbige LED](https://philipphgerber.github.io/tutorials-x2-next/docs/static/tutorials/02_led_rgb_board.png)


## Variabeln für die LEDs @unplugged

Erstelle drei Variabeln ``||variables:rot||``, ``||variables:grün||`` und ``||variables:blau||``.

``||variables:Setze||`` alle drei Variablen ``||basic:beim Start||`` auf ``||logic:falsch||``.

```blocks
```
```block
rot = false 
```
```block
grün = false 
```
```block
blau = false 
```


## Variabeln für die LEDs 

Erstelle drei Variabeln ``||variables:rot||``, ``||variables:grün||`` und ``||variables:blau||``.

``||variables:Setze||`` alle drei Variablen ``||basic:beim Start||`` auf ``||logic:falsch||``.


```blocks
rot = false
grün = false
blau = false
```

## LED rot ein- und ausschalten @unplugged

Wenn ``||input:Knopf A||`` geklickt wird, dann soll ``||variables:rot||`` eingeschaltet werden. 
Wenn der Knopf noch mal geklickt wird, soll sie wieder ausgeschaltet werden.
```block
input.onButtonPressed(Button.A, function () {})
```
```block
rot = !(rot)
```

## LED rot ein- und ausschalten 

Wenn ``||input:Knopf A||`` geklickt wird, dann soll ``||variables:rot||`` eingeschaltet werden. 
Wenn der Knopf noch mal geklickt wird, soll sie wieder ausgeschaltet werden.

```blocks
input.onButtonPressed(Button.A, function () {
    rot = !(rot)
})
```

## LED rot leuchten lassen @unplugged

Überprüfe ``||basic:dauerhaft||`` die Variable ``||variables:rot||``:
Wenn ``||variables:rot||`` leuchten soll, dann schalte die LED auf ``||pins:Pin P2||`` ein, ansonsten schalte sie aus.

```block
basic.forever()
```
```block
if (rot) {} else {}
```
```block
pins.digitalWritePin(DigitalPin.P2, 1)
```
```block
pins.digitalWritePin(DigitalPin.P2, 0)
```


## LED rot leuchten lassen

Überprüfe ``||basic:dauerhaft||`` die Variable ``||variables:rot||``:
Wenn ``||variables:rot||`` leuchten soll, dann schalte die LED auf ``||pins:Pin P2||`` ein, ansonsten schalte sie aus.

```blocks
basic.forever(function () {
    if (rot) {
        pins.digitalWritePin(DigitalPin.P2, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P2, 0)
    }
})
```

## LED grün ein- und ausschalten @unplugged

Wenn ``||input:Knopf B||`` geklickt wird, dann soll ``||variables:grün||`` eingeschaltet werden. 
Wenn der Knopf noch mal geklickt wird, soll sie wieder ausgeschaltet werden.
```block
input.onButtonPressed(Button.B, function () {})
```
```block
grün = !(grün)
```

## LED grün ein- und ausschalten

Wenn ``||input:Knopf B||`` geklickt wird, dann soll ``||variables:grün||`` eingeschaltet werden. 
Wenn der Knopf noch mal geklickt wird, soll sie wieder ausgeschaltet werden.

```blocks
input.onButtonPressed(Button.B, function () {
    grün = !(grün)
})
```

## LED grün leuchten lassen @unplugged

Überprüfe ``||basic:dauerhaft||`` die Variable ``||variables:grün||``:
Wenn ``||variables:grün||`` leuchten soll, dann schalte die LED auf ``||pins:Pin P1||`` ein, ansonsten schalte sie aus.

```block
if (grün) {} else {}
```
```block
pins.digitalWritePin(DigitalPin.P1, 1)
```
```block
pins.digitalWritePin(DigitalPin.P1, 0)
```

## LED grün leuchten lassen 

Überprüfe ``||basic:dauerhaft||`` die Variable ``||variables:grün||``:
Wenn ``||variables:grün||`` leuchten soll, dann schalte die LED auf ``||pins:Pin P1||`` ein, ansonsten schalte sie aus.

```diffblocks
basic.forever(function () {
    if (rot) {
        pins.digitalWritePin(DigitalPin.P2, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P2, 0)
    }
})
----------
basic.forever(function () {
    if (rot) {
        pins.digitalWritePin(DigitalPin.P2, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P2, 0)
    }
    if (grün) {
        pins.digitalWritePin(DigitalPin.P1, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P1, 0)
    }
})
```

## LED blau ein- und ausschalten @unplugged

Wenn ``||input:Knopf A+B||`` **zusammen** geklickt werden, dann soll ``||variables:blau||`` eingeschaltet werden. 
Wenn die Knöpfe noch mal geklickt werden, dann soll sie wieder ausgeschaltet werden.
```block
input.onButtonPressed(Button.AB, function () {})
```
```block
blau = !(blau)
```

## LED blau ein- und ausschalten

Wenn ``||input:Knopf A+B||`` **zusammen** geklickt werden, dann soll ``||variables:blau||`` eingeschaltet werden. 
Wenn die Knöpfe noch mal geklickt werden, dann soll sie wieder ausgeschaltet werden.

```blocks
input.onButtonPressed(Button.AB, function () {
    blau = !(blau)
})
```


## LED blau leuchten lassen @unplugged

Überprüfe ``||basic:dauerhaft||`` die Variable ``||variables:blau||``:
Wenn ``||variables:blau||`` leuchten soll, dann schalte die LED auf ``||pins:Pin P0||`` ein, ansonsten schalte sie aus.

```block
if (blau) {} else {}
```
```block
pins.digitalWritePin(DigitalPin.P0, 1)
```
```block
pins.digitalWritePin(DigitalPin.P0, 0)
```

## LED blau leuchten lassen

Überprüfe ``||basic:dauerhaft||`` die Variable ``||variables:blau||``:
Wenn ``||variables:blau||`` leuchten soll, dann schalte die LED auf ``||pins:Pin P0||`` ein, ansonsten schalte sie aus.

```diffblocks
basic.forever(function () {
    if (rot) {
        pins.digitalWritePin(DigitalPin.P2, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P2, 0)
    }
    if (grün) {
        pins.digitalWritePin(DigitalPin.P1, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P1, 0)
    }
})
----------
basic.forever(function () {
    if (rot) {
        pins.digitalWritePin(DigitalPin.P2, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P2, 0)
    }
    if (grün) {
        pins.digitalWritePin(DigitalPin.P1, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P1, 0)
    }
    if (blau) {
        pins.digitalWritePin(DigitalPin.P0, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P0, 0)
    }
})
```

## Fertiges Projekt testen

Teste dein Programm zuerst im Simulator und dann mit einem Mico:bit.


<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
