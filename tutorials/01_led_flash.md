# LED blinken lassen. 

```template
basic.forever()
```

## Einführung @showdialog

Schaltplan LED:

![Schaltplan LED](https://philipphgerber.github.io/tutorials-x2-next/docs/static/tutorials/01_leds_board.png)


## Variabeln für die LEDs @unplugged

Erstelle drei Variabeln ``||variables:LED0||``, ``||variables:LED1||`` und ``||variables:blinken||``.

``||variables:Setzte||`` alle drei Variablen ``||basic:beim Start||`` auf ``||logic:falsch||``.

```blocks
```
```block
LED0 = false
```
```block
LED1 = false 
```
```block
blinken = false
```

## Variabeln für die LEDs

Erstelle drei Variabeln ``||variables:LED0||``, ``||variables:LED1||`` und ``||variables:blinken||``.

``||variables:Setzte||`` alle drei Variablen ``||basic:beim Start||`` auf ``||logic:falsch||``.

```blocks
blinken = false
LED1 = false
LED0 = false
```


## LED0 ein- und ausschalten @unplugged

Wenn ``||input:Knopf A||`` geklickt wird, dann soll ``||variables:LED0||`` eingeschaltet werden. 
Wenn der Knopf noch mal geklickt wird, soll sie wieder ausgeschaltet werden.

```block
input.onButtonPressed(Button.A, function () {})
```
```block
LED0 = !(LED0)
```

## LED0 ein- und ausschalten

Wenn ``||input:Knopf A||`` geklickt wird, dann soll ``||variables:LED0||`` eingeschaltet werden. 
Wenn der Knopf noch mal geklickt wird, soll sie wieder ausgeschaltet werden.

```blocks
input.onButtonPressed(Button.A, function () {
    LED0 = !(LED0)
})
```

## LED1 ein- und ausschalten @unplugged

Wenn ``||input:Knopf B||`` geklickt wird, dann soll ``||variables:LED1||`` eingeschaltet werden. 
Wenn der Knopf noch mal geklickt wird, soll sie wieder ausgeschaltet werden.

```block
input.onButtonPressed(Button.B, function () {})
```
```block
LED1 = !(LED1)
```

## LED1 ein- und ausschalten

Wenn ``||input:Knopf B||`` geklickt wird, dann soll ``||variables:LED1||`` eingeschaltet werden. 
Wenn der Knopf noch mal geklickt wird, soll sie wieder ausgeschaltet werden.

```blocks
input.onButtonPressed(Button.B, function () {
    LED1 = !(LED1)
})
```


## LEDs blinken lassen @unplugged

Wenn ``||input:Knopf A+B||`` **zusammen** geklickt werden, dann sollen beide LEDs ``||variables:blinken||``.
Wenn die Knöpfe noch mal geklickt wird, soll das blinken wieder aufhören.

```block
input.onButtonPressed(Button.AB, function () {})
```
```block
blinken = !(blinken)
```

## LEDs blinken lassen

Wenn ``||input:Knopf A+B||`` **zusammen** geklickt werden, dann sollen beide LEDs ``||variables:blinken||``.
Wenn die Knöpfe noch mal geklickt wird, soll das blinken wieder aufhören.

```blocks
input.onButtonPressed(Button.AB, function () {
    blinken = !(blinken)
})
```


## Sollen die LEDs blinken? @unplugged

Überprüfe ``||basic:dauerhaft||`` die Variable ``||variables:blinken||``:

```block
basic.forever()
```
```block
if (blinken) {} else {}
```

## Sollen die LEDs blinken?

Überprüfe ``||basic:dauerhaft||`` die Variable ``||variables:blinken||``:

```blocks
basic.forever(function () {
    if (blinken) {
    } else {
    }
})
```

## LEDs abwechselnd blinken lassen @unplugged

Wenn die LEDs blinken sollen (``||variables:blinken||``), dann schalte die LEDs für ``||basic:200ms||`` ein und danach für ``||basic:200ms||`` aus.

```block
pins.digitalWritePin(DigitalPin.P0, 1)
```

```block
pins.digitalWritePin(DigitalPin.P1, 1)
```
```block
basic.pause(200)
```
```block
pins.digitalWritePin(DigitalPin.P0, 0)
```
```block
pins.digitalWritePin(DigitalPin.P1, 0)
```
```block
basic.pause(200)
```


## LEDs abwechselnd blinken lassen

Wenn die LEDs blinken sollen (``||variables:blinken||``), dann schalte die LEDs für ``||basic:200ms||`` ein und danach für ``||basic:200ms||`` aus.

```diffblocks
basic.forever(function () {
    if (blinken) {
    } else {
    }
})
----------
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

## LED0 ein- und ausschalten @unplugged

Wenn die LEDs nicht blinken, dann prüfe, ob ``||variables:LED0||`` eingeschaltet werden soll.

```block
if (LED0) {} else {}
```
```block
pins.digitalWritePin(DigitalPin.P0, 1)
```
```block
pins.digitalWritePin(DigitalPin.P0, 0)
```

## LED0 ein- und ausschalten

Wenn die LEDs nicht blinken, dann prüfe, ob ``||variables:LED0||`` eingeschaltet werden soll.

```diffblocks
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
----------
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

## LED1 ein- und ausschalten @unplugged

Wenn die LEDs nicht blinken, dann prüfe, ob ``||variables:LED1||`` eingeschaltet werden soll.

```block
if (LED1) {} else {}
```
```block
pins.digitalWritePin(DigitalPin.P1, 1)
```
```block
pins.digitalWritePin(DigitalPin.P1, 0)
```

## LED1 ein- und ausschalten 

Wenn die LEDs nicht blinken, dann prüfe, ob ``||variables:LED1||`` eingeschaltet werden soll.

```diffblocks
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
----------
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

Teste dein Programm zuerst im Simulator und dann mit einem Mico:bit.


<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
