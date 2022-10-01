# Motor

```template
basic.forever()
```

## Einführung @showdialog

Schaltplan Motor:

![Schaltplan Buzzer](https://philipphgerber.github.io/tutorials-x2-next/docs/static/tutorials/05_motor.png)


## Variabe für den Motor @unplugged

Erstelle eine Variabeln ``||variables:motor||``.

``||variables:Setze||`` die Variable ``||variables:motor||`` ``||basic:beim Start||`` auf ``||logic:falsch||``.

```blocks
```
```block
motor = false
```

## Variabe für den Motor

Erstelle eine Variabeln ``||variables:motor||``.

``||variables:Setze||`` die Variable ``||variables:motor||`` ``||basic:beim Start||`` auf ``||logic:falsch||``.

```blocks
motor = false
```

## Pins für den Motor @unplugged

Setze ``||basic:beim Start||`` den ``||pins:digitalen Wert von Pin P0||`` für den Motor auf ``||variables:0||``

und ziehe dann ``||pins: Pin P1||`` für den Schalter auf ``||pins: nach oben||``.

```block
pins.digitalWritePin(DigitalPin.P0, 0)
```
```block
pins.setPull(DigitalPin.P1, PinPullMode.PullUp)
```

## Pins für den Motor

Setze ``||basic:beim Start||`` den ``||pins:digitalen Wert von Pin P0||`` für den Motor auf ``||variables:0||``

und ziehe dann ``||pins: Pin P1||`` für den Schalter auf ``||pins: nach oben||``.

```diffblocks
motor = false
----------
motor = false
// Motor auf Pin0
pins.digitalWritePin(DigitalPin.P0, 0)
// Schalter auf Pin1
pins.setPull(DigitalPin.P1, PinPullMode.PullUp)

```


## Motor an- oder anschalten @unplugged

Überprüfe ``||basic:dauerhaft||`` die Variable ``||variables:motor||``.

Setze zum anschalten den ``||pins:digitalen Wert von Pin P0||`` auf ``||variables:1||``.

Setze zum ausschalten den ``||pins:digitalen Wert von Pin P0||`` auf ``||variables:0||``.

```block
basic.forever()
```
```block
if (motor) {} else {}
```
```block
pins.digitalWritePin(DigitalPin.P0, 1)
```
```block
pins.digitalWritePin(DigitalPin.P0, 0)
```

## Motor an- oder anschalten

Überprüfe ``||basic:dauerhaft||`` die Variable ``||variables:motor||``.

Setze zum anschalten den ``||pins:digitalen Wert von Pin P0||`` auf ``||variables:1||``.

Setze zum ausschalten den ``||pins:digitalen Wert von Pin P0||`` auf ``||variables:0||``.

```blocks
basic.forever(function () {
    if (motor) {
        pins.digitalWritePin(DigitalPin.P0, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P0, 0)
    }
})
```

## Schalter auslesen @unplugged

Überprüfe ``||basic:dauerhaft||`` ``||pins: Pin P1||``.

Wenn der Wert von ``||pins: Pin P1||`` 0 ist, dann ``||variables:setze||`` die Variable ``||variables:motor||`` auf ``||logic:wahr||``.

Wenn der Wert von ``||pins: Pin P1||`` nicht 0 ist, dann ``||variables:setze||`` die Variable ``||variables:motor||`` auf ``||logic:falsch||``.

```block
basic.forever()
```
```block
if (pins.digitalReadPin(DigitalPin.P1) == 0) {} else {}
```
```block
motor = true
```
```block
motor = false
```

## Schalter auslesen

Überprüfe ``||basic:dauerhaft||`` ``||pins: Pin P1||``.

Wenn der Wert von ``||pins: Pin P1||`` 0 ist, dann ``||variables:setze||`` die Variable ``||variables:motor||`` auf ``||logic:wahr||``.

Wenn der Wert von ``||pins: Pin P1||`` nicht 0 ist, dann ``||variables:setze||`` die Variable ``||variables:motor||`` auf ``||logic:falsch||``.

```blocks
basic.forever(function () {
    if (pins.digitalReadPin(DigitalPin.P1) == 0) {
        motor = true
    } else {
        motor = false
    }
})
```

## Fertiges Projekt testen

Teste dein Programm zuerst im Simulator und dann mit einem Mico:bit.


<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
