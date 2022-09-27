# X2 Next - Tutorial 01 LEDs

## It's time to code! @showhint

![Micro:bit](/static/01/board_01_leds.png)


## Micro:bit Programmierung

Starte mit dem ``||basic:forever||`` Block.

```blocks
basic.forever(function() {})
```

## LED an Pin 0 einschalten.

Verwende zum einstachalten der ersten LED den Block ``||pins:digitalWritePin(P0, 1)||`` 

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
})
```

## LED an Pin 0 ausschalten.

Verwende den Block ``||basic:pause(1000)||`` um eine Sekunde zu warten.
Schalte die LED dann wieder aus ``||pins:digitalWritePin(P0, 0)||`` 
Und warte wieder eine Sekunde.

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(1000)
    pins.digitalWritePin(DigitalPin.P0, 0)
    basic.pause(1000)
})
```

## LED an Pin 1

Lass die zweite LED (pin P1) abwechseld zur ersten LED blinken.

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    pins.digitalWritePin(DigitalPin.P1, 0)
    basic.pause(1000)
    pins.digitalWritePin(DigitalPin.P0, 0)
    pins.digitalWritePin(DigitalPin.P1, 1)
    basic.pause(1000)
})
```







```template

```

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
