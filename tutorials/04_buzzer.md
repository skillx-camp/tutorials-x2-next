# Buzzer

## Einführung @showdialog

Schaltplan Buzzer:

![Schaltplan Buzzer](https://skillx-camp.github.io/tutorials-x2-next/docs/static/tutorials/04_buzzer.png)


## Variabe für den Buzzer @unplugged

Erstelle eine Variabeln ``||variables:buzzer||``.

Schalte ``||basic:beim Start||`` den ``||music:internen Lautsprecher||`` aus und
``||variables:setze||`` die Variable ``||variables:buzzer||`` beim Start auf ``||variables:0||``.

```blocks
```
```block
music.setBuiltInSpeakerEnabled(false)
```
```block
buzzer = 0
```

## Variabe für den Buzzer 

Erstelle eine Variabeln ``||variables:buzzer||``.

Schalte ``||basic:beim Start||`` den ``||music:internen Lautsprecher||`` aus und
``||variables:setze||`` die Variable ``||variables:buzzer||`` beim Start auf ``||variables:0||``.

```blocks
music.setBuiltInSpeakerEnabled(false)
buzzer = 0
```

## Ton ausgeben @unplugged

Spiele ``||basic:dauerhaft||`` die ``||music:Note||``, die in der Variable ``||variables:buzzer||`` gespeichert ist.

```block
basic.forever()
```
```block
music.ringTone(buzzer)
```

## Ton ausgeben

Spiele ``||basic:dauerhaft||`` die ``||music:Note||``, die in der Variable ``||variables:buzzer||`` gespeichert ist.

```blocks
basic.forever(function () {
    music.ringTone(buzzer)
})
```

## Kein Ton ausgeben  @unplugged

Wenn ``||input:das Logo gedrückt||`` wird, dann soll kein Ton mehr ausgegeben werden
(``||variables:buzzer||`` = 0).

```block
input.onLogoEvent(TouchButtonEvent.Pressed, function () {})
```
```block
buzzer = 0
```

## Kein Ton ausgeben

Wenn ``||input:das Logo gedrückt||`` wird, dann soll kein Ton mehr ausgegeben werden
(``||variables:buzzer||`` = 0).

```blocks
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    buzzer = 0
})
```

## Tonhöhe verändern - Knopf A @unplugged

Wenn ``||input:Knopf A||`` geklickt wird, dann soll der Ton tiefer werden, jedoch nicht tiefer als 130.

```block
input.onButtonPressed(Button.A, function () {}
```
```block
buzzer = Math.max(130, buzzer - 10)
```

## Tonhöhe verändern - Knopf A

Wenn ``||input:Knopf A||`` geklickt wird, dann soll der Ton tiefer werden, jedoch nicht tiefer als 130.

```blocks
input.onButtonPressed(Button.A, function () {
    buzzer = Math.max(130, buzzer - 10)
})
```

## Tonhöhe verändern - Knopf B @unplugged

Wenn ``||input:Knopf B||`` geklickt wird, dann soll der Ton höher werden, jedoch nicht tiefer als 990.

```block
input.onButtonPressed(Button.B, function () {}
```
```block
buzzer = Math.max(990, buzzer + 10)
```

## Tonhöhe verändern - Knopf B

Wenn ``||input:Knopf B||`` geklickt wird, dann soll der Ton höher werden, jedoch nicht tiefer als 990.

```blocks
input.onButtonPressed(Button.B, function () {
    buzzer = Math.min(990, buzzer + 10)
})
```

## Melodie abspielen @unplugged

Wenn ``||input:Knopf A+B||`` **zusammen** geklickt werden, dann soll eine Melodie gespielt werden.
Mit ``buzzer = 0`` wird der Buzzer ausgeschaltet.

```block
input.onButtonPressed(Button.AB, function () {}
```
```block
for (let index = 0; index < 5; index++) {}
```
```block
buzzer = 523
```
```block
basic.pause(500)
```
```block
buzzer = 659
```
```block
buzzer = 0
```

## Melodie abspielen

Wenn ``||input:Knopf A+B||`` **zusammen** geklickt werden, dann soll eine Melodie gespielt werden.
Mit ``buzzer = 0`` wird der Buzzer ausgeschaltet.

```blocks
input.onButtonPressed(Button.AB, function () {
    for (let index = 0; index < 5; index++) {
        buzzer = 523
        basic.pause(500)
        buzzer = 659
        basic.pause(500)
    }
    buzzer = 0
})
```


## Fertiges Projekt testen

Teste dein Programm zuerst im Simulator und dann mit einem Mico:bit.


<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
