# Trafikklys lyssekvens

## Step 1

Nå skal vi lage et program som styrer led-dioder som er koblet til micro:bit. Vi vil koble rød LED til pin 0. For å skru på den røde led-dioden må vi da skru på strømmen i pin 0. Dette gjør vi med blokken ``||pins:skriv digital til||`` Denne blokken finner du i kategorien Tilkoblinger. Plasser blokken i ``||basic:gjenta for alltid||`` Vi velger P0 for pin 0 og gir blokken verdi 1 som betyr strøm på. 

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
	
})
```

## Step 2
Det neste vi vil gjøre er å koble til den gule led-dioden. Denne kobler vi til pin 1 (P1). Deretter henter vi inn en ny ``||pins:skriv digital til||`` blokk som vi endrer til P1 og gir verdien 1.

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    pins.digitalWritePin(DigitalPin.P1, 1)
	
})
```
## Step 3
Så skal vi koble til den grønne led-dioden. Denne kobles til pin 2 (P2). Vi henter en ny ``||pins:skriv digital til||`` blokk og endrer til P2 og verdi 1.
Når du er ferdig med dette steget lyser alle led-diodene.

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    pins.digitalWritePin(DigitalPin.P1, 1)
    pins.digitalWritePin(DigitalPin.P2, 1)	
})

```
* for PXT/microbit
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
