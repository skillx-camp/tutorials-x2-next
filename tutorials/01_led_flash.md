# LED blinken lassen. 

## Einführung @unplugged

Schaltplan LED:

![Schaltplan LED](https://philipphgerber.github.io/tutorials-x2-next/docs/static/tutorials/01_leds_board.png)


## Variabeln für die LEDs

Erstelle drei Variabeln und setzte alle drei Variablen beim Start auf ``||logic:wahr||``.

``[let LED0 = true ]``

``[let LED1 = true ]``

``[let blinken = true ]``


```blocks
let blinken = true
let LED1 = true
let LED0 = true
```

## LED0 ein- und ausschalten

Wenn **Knopf A** gedrückt wird, dann soll **LED0** ein- und wieder ausgeschaltet werden.

``[LED0 = !(LED0)]``


```blocks
input.onButtonPressed(Button.A, function () {
    LED0 = !(LED0)
})
```

## LED1 ein- und ausschalten

Wenn **Knopf B** gedrückt wird, dann soll **LED1** ein- und wieder ausgeschaltet werden.

``[LED1 = !(LED1)]``


```blocks
input.onButtonPressed(Button.B, function () {
    LED1 = !(LED1)
})
```

## LEDs blinken lassen

Wenn **Knopf A und B zusammen** gedrückt werden, dann sollen beide LEDs blinken.

``[blinken = !(blinken)]``


```blocks
input.onButtonPressed(Button.AB, function () {
    blinken = !(blinken)
})
```

## Sollen die LEDs blinken?

Überprüfe **dauerhaft** die Variable ``||variables:blinken||``:

``[basic.forever()]``

``[if (blinken) {} else {}]``

```blocks
basic.forever(function () {
    if (blinken) {
    } else {
    }
})
```

## LEDs abwechselnd blinken lassen

Wenn die LEDs blinken sollen (``||variables:blinken||``), dann schalte die LEDs für 200ms ein und danach für 200ms aus.

LEDs  einschalten:
``[pins.digitalWritePin(DigitalPin.P0, 1)]``
``[pins.digitalWritePin(DigitalPin.P1, 1)]``

LEDs ausschalten:
``[pins.digitalWritePin(DigitalPin.P0, 0)]``
``[pins.digitalWritePin(DigitalPin.P1, 0)]``

Warten:
``[basic.pause(200)]``

```blocks
basic.forever(function () {
    if (blinken) {
        pins.digitalWritePin(DigitalPin.P0, 0)
        pins.digitalWritePin(DigitalPin.P1, 1)
        basic.pause(200)
        pins.digitalWritePin(DigitalPin.P0, 1)
        pins.digitalWritePin(DigitalPin.P1, 0)
        basic.pause(200)
    } else {
    }
})
```

## LED0 ein- und ausschalten

Wenn die LEDs nicht blinken, dann prüfe, ob LED0 eingeschaltet werden soll.

``[if (LED0) {} else {}]``

``[pins.digitalWritePin(DigitalPin.P0, 1)]``
``[pins.digitalWritePin(DigitalPin.P0, 0)]``

```blocks
basic.forever(function () {
    if (blinken) {
        pins.digitalWritePin(DigitalPin.P0, 0)
        pins.digitalWritePin(DigitalPin.P1, 1)
        basic.pause(200)
        pins.digitalWritePin(DigitalPin.P0, 1)
        pins.digitalWritePin(DigitalPin.P1, 0)
        basic.pause(200)
    } else {
        if (LED0) {
            pins.digitalWritePin(DigitalPin.P0, 1)
        } else {
            pins.digitalWritePin(DigitalPin.P0, 0)
        }
    }
})
```

## LED1 ein- und ausschalten

Wenn die LEDs nicht blinken, dann prüfe, ob LED1 eingeschaltet werden soll.

``[if (LED1) {} else {}]``

``[pins.digitalWritePin(DigitalPin.P1, 1)]``
``[pins.digitalWritePin(DigitalPin.P1, 0)]``

```blocks
basic.forever(function () {
    if (blinken) {
        pins.digitalWritePin(DigitalPin.P0, 0)
        pins.digitalWritePin(DigitalPin.P1, 1)
        basic.pause(200)
        pins.digitalWritePin(DigitalPin.P0, 1)
        pins.digitalWritePin(DigitalPin.P1, 0)
        basic.pause(200)
    } else {
        if (LED0) {
            pins.digitalWritePin(DigitalPin.P0, 1)
        } else {
            pins.digitalWritePin(DigitalPin.P0, 0)
        }
        if (LED1) {
            pins.digitalWritePin(DigitalPin.P1, 1)
        } else {
            pins.digitalWritePin(DigitalPin.P1, 0)
        }
    }
})
```

## Fertiges Projekt testen

Teste ein Programm zuerstim im Simulator und dann mit einem Mico:bit.


<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
