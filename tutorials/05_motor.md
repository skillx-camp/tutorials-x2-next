# Motor

## Einführung @unplugged

Schaltplan Motor:

![Schaltplan Buzzer](https://philipphgerber.github.io/tutorials-x2-next/docs/static/tutorials/05_motor.png)


## Variabe für den Motor

Erstelle eine Variabeln **motor**.

Schalte beim Start den internen Lautsprecher aus und
setzte die Variablen **buzzer** auf **523**.

``[pins.digitalWritePin(DigitalPin.P0, 1)]``

``[pins.setPull(DigitalPin.P1, PinPullMode.PullUp)]``

``[motor = false]``

```blocks
// Motor auf Pin0
pins.digitalWritePin(DigitalPin.P0, 1)
// Schalter auf Pin1
pins.setPull(DigitalPin.P1, PinPullMode.PullUp)
let motor = false
motor = false
```

## Motor anschalten

 dauerhaft
``[basic.forever()]``

``[if (motor) {} else {}]``

``[pins.digitalWritePin(DigitalPin.P0, 0)]``

``[pins.digitalWritePin(DigitalPin.P0, 1)]``


```blocks
basic.forever(function () {
    if (motor) {
        pins.digitalWritePin(DigitalPin.P0, 1)
    } else {
        pins.digitalWritePin(DigitalPin.P0, 0)
    }
})
```

## Schalter auslesen

 dauerhaft 

``[basic.forever()]``

``[if (motor) {} else {}]``

``[pins.digitalReadPin(DigitalPin.P1) == 0]``

``[motor = true]``
``[motor = false]``

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

Teste ein Programm zuerstim im Simulator und dann mit einem Mico:bit.


<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
