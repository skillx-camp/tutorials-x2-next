# Dreifarbige LED. 

## Einführung @unplugged

Schaltplan Dreifarbige LED:

![Schaltplan Dreifarbige LED](https://philipphgerber.github.io/tutorials-x2-next/docs/static/tutorials/02_led_rgb_board.png)


## Variabeln für die LEDs

Erstelle drei Variabeln **rot**, **grün** und **blau**.

Setzte alle drei Variablen beim Start auf ``||logic:wahr||``.

``[let rot = true ]``

``[let grün = true ]``

``[let blau = true ]``


```blocks
let rot = true
let grün = true
let blau = true
```

## LED rot ein- und ausschalten

Wenn **Knopf A** gedrückt wird, dann soll die LED **rot** leuchten.

``[rot = !(rot)]``


```blocks
input.onButtonPressed(Button.A, function () {
    rot = !(rot)
})
```

## LED rot ein- und ausschalten leuchten lassen

Überprüfe **dauerhaft** die Variable ``||variables:rot||``.
Wenn **rot** leuchten soll, dann schalte die LED auf Pin 2 ein, ansonsten schalte sie aus.

``[basic.forever()]``

``[if (rot) {} else {}]``

``[pins.digitalWritePin(DigitalPin.P2, 1)]``

```blocks
basic.forever(function () {
    if (rot) {
        pins.digitalWritePin(DigitalPin.P2, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P2, 0)
    }
})
```

## LED grün ein- und ausschalten

Wenn **Knopf B** gedrückt wird, dann soll die LED **grüne** leuchten.

``[grün = !(grün)]``


```blocks
input.onButtonPressed(Button.B, function () {
    grün = !(grün)
})
```

## LED grün leuchten lassen

Überprüfe **dauerhaft** die Variable ``||variables:grün||``.
Wenn **grün** leuchten soll, dann schalte die LED auf Pin 1 ein, ansonsten schalte sie aus.

``[basic.forever()]``

``[if (grün) {} else {}]``

``[pins.digitalWritePin(DigitalPin.P1, 1)]``

```blocks
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

## LED blau ein- und ausschalten

Wenn **Knopf A und B zusammen** gedrückt werden, dann soll die LED **blaue** leuchten.

``[blau = !(blau)]``


```blocks
input.onButtonPressed(Button.AB, function () {
    blau = !(blau)
})
```

## LED blau leuchten lassen

Überprüfe **dauerhaft** die Variable ``||variables:blau||``.
Wenn **blau** leuchten soll, dann schalte die LED auf Pin 0 ein, ansonsten schalte sie aus.

``[basic.forever()]``

``[if (blau) {} else {}]``

``[pins.digitalWritePin(DigitalPin.P0, 1)]``

```blocks
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

Teste ein Programm zuerstim im Simulator und dann mit einem Mico:bit.


<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
