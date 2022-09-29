# Buzzer

## Einführung @unplugged

Schaltplan Buzzer:

![Schaltplan Buzzer](https://philipphgerber.github.io/tutorials-x2-next/docs/static/tutorials/04_buzzer.png)


## Variabe für den Buzzer

Erstelle eine Variabeln **buzzer**.

Schalte beim Start den internen Lautsprecher aus und
setzte die Variablen **buzzer** auf **523**.

``[music.setBuiltInSpeakerEnabled(false)]``

``[let buzzer = 523]``

```blocks
music.setBuiltInSpeakerEnabled(false)
let buzzer = 523
```

## Ton ausgeben

Setze dauerhaft die Note, die in der Variable **buzzer** gespeichert ist.

``[basic.forever()]``

``[music.ringTone(buzzer)]``


```blocks
basic.forever(function () {
    music.ringTone(buzzer)
})
```

## Tonhöhe verändern - Knopf A

Wenn **Knopf A** gedrückt wird, dann soll der Ton tiefer werden, jedoch nicht tiefer als 130.

``[input.onButtonPressed(Button.A, function () {}]``

``[buzzer = Math.max(130, buzzer - 9)]``

```blocks
input.onButtonPressed(Button.A, function () {
    buzzer = Math.max(131, buzzer - 9)
})
```

## Tonhöhe verändern - Knopf B

Wenn **Knopf B** gedrückt wird, dann soll der Ton höher werden, jedoch nicht höher als 988.

``[input.onButtonPressed(Button.B, function () {}]``

``[buzzer = Math.min(988, buzzer + 9)]``

```blocks
input.onButtonPressed(Button.B, function () {
    buzzer = Math.min(988, buzzer + 9)
})
```


## Melodie abspielen

Wenn **Knopf A und B zusammen** gedrückt wird, dann soll eine Melodie gespielt werden.
Mit ``buzzer = 0`` wird der Buzzer ausgeschaltet.

``[input.onButtonPressed(Button.AB, function () {}]``

``[for (let index = 0; index < 5; index++) {}]``

``[buzzer = 523 ]``
``[basic.pause(500) ]``
``[buzzer = 659 ]``


``[buzzer = 0 ]``


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

Teste ein Programm zuerst im im Simulator und dann mit einem Mico:bit.


<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
