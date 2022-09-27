# LED blinken lassen. 

## Einführung @unplugged
Der Dialog wird im Fenster angezeigt und übersprungen,
sobald ``|ok|`` gedrückt wird.
Dient deshalb gut als Einführungstext des Tutorials.

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

Wenn Knopf A gedrückt wird, soll LED0 ein- und wieder ausgeschaltet werden.

``[LED0 = !(LED0)]``


```blocks
input.onButtonPressed(Button.A, function () {
    LED0 = !(LED0)
})
```

## LED1 ein- und ausschalten

Wenn Knopf B gedrückt wird, soll LED1 ein- und wieder ausgeschaltet werden.

``[LED1 = !(LED1)]``


```blocks
input.onButtonPressed(Button.B, function () {
    LED1 = !(LED1)
})
```

## LEDs blinken lassen

Wenn Knopf A und B zusammen gedrückt werden, dann sollen beide LEDs blinken.

``[blinken = !(blinken)]``


```blocks
input.onButtonPressed(Button.AB, function () {
    blinken = !(blinken)
})
```

## Sollen die LEDs blinken?

Überprüfe dauerhaft die Variable ``||variables:blinken||``:

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

LED0 einschalten:

``[pins.digitalWritePin(DigitalPin.P0, 1)]``

LED1 einschalten:

``[pins.digitalWritePin(DigitalPin.P1, 1)]``

und ausschalten:

``[pins.digitalWritePin(DigitalPin.P0, 0)]``
``[pins.digitalWritePin(DigitalPin.P1, 0)]``

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

## LED0 ein- und ausschalten

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
