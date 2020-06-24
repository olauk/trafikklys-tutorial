# Trafikklys 
### @activities true

## Oppkobling

### Introduksjon @unplugged

Nå skal vi lage et program som styrer led-dioder som er koblet til micro:bit slik at vi får et trafikklys som lyser i riktig rekkefølge.
![Trafikklys](https://github.com/olauk/static/blob/master/tutorial/trafikklys/trafikklys1.png?raw=true)

### Step 1

Koble rød ledning fra P0 (raud) på trafikklyset til koblingsbrettet. 
![Rødt lys](https://github.com/olauk/static/blob/master/tutorial/trafikklys/r%C3%B8d.png?raw=true)
### Step 2

Koble ledning videre fra koblingsbrettet og over til pin 0 på micro:bit.
![Til micro:bit](https://github.com/olauk/static/blob/master/tutorial/trafikklys/r%C3%B8d_mb.png?raw=true)
### Step 3

Gjenta dette med ledninger fra P1 (gul) og P2 (grøn) fra trafikklyset via koblingsbrettet og til micro:bit.
![Gult og grønt lys](https://github.com/olauk/static/blob/master/tutorial/trafikklys/r%C3%B8d_gul_gr%C3%B8nn.png?raw=true)
### Step 4

Koble ledning fra GND på trafikklyset til koblingsbrettet.
![GND](https://github.com/olauk/static/blob/master/tutorial/trafikklys/r%C3%B8d_gul_gr%C3%B8nn_gnd.png?raw=true)

### Step 5

Koble ledning fra koblingsbrettet over til GND (0V) på micro:bit.
![GND micro:bit](https://github.com/olauk/static/blob/master/tutorial/trafikklys/rgb_gnd_mb.png?raw=true)
## Programmere lysene

### Step 1

 Rødt lys: For å skru på den røde led-dioden må vi skru på strømmen i pin 0. Dette gjør vi med blokken ``||pins:skriv digital||`` Denne blokken finner du i kategorien ``||pins:Tilkoblinger||``. Plasser blokken i ``||basic:gjenta for alltid||`` Vi velger P0 for pin 0 og gir blokken verdi 1 som betyr strøm på. 

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
	
})
```


### Step 1
Gult lys: Vi henter inn en ny ``||pins:skriv digital||`` blokk som vi endrer til P1 og gir verdien 1. Dette skrur på det gule lyset.

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    pins.digitalWritePin(DigitalPin.P1, 1)
	
})
```
### Step 2
Grønt lys: Vi henter en ny ``||pins:skriv digital||`` blokk og endrer til P2 og verdi 1. Dette skrur på det grønne lyset.
Hvis du overfører programmet til micro:bit etter dette steget vil du få lys i alle led-diodene i trafikklyset.

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    pins.digitalWritePin(DigitalPin.P1, 1)
    pins.digitalWritePin(DigitalPin.P2, 1)	
})

```

## Lyssekvens

### Step 1

På et trafikklys vil ikke alle lysene være på samtidig. Vi må skru av og på de ulike lysene i riktig rekkefølge i programmet vårt.
Vi bruker blokken ``||basic:pause||`` for å la ett lys være på eller av i en bestemt periode. ``||basic:Pause||`` gjør at programmet venter i det antall millisekunder du angir i blokken før det går videre til neste blokk.
Legg inn en pause mellom første og andre ``||pins:skriv digital||`` blokk.

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P1, 1)
    pins.digitalWritePin(DigitalPin.P2, 1)	
})

```
### Step 2 @fullscreen

Hvis vi har satt ``||pins:skriv digital||`` til verdi 1 vil micro:bit sende strøm ut denne pin helt til vi i programmet bruker en ny ``||pins:skriv digital||`` og setter verdien til 0.
Bruk ``||basic:pause||`` og ``||pins:skriv digital||`` blokker til å lage et program som skrur lysene i trafikklyset av og på i riktig sekvens. Gå til neste steg hvis du trenger litt ekstra hjelp.
![sekvens](https://github.com/olauk/static/blob/master/tutorial/trafikklys/sekvens.png?raw=true)

### Step 3
I hintet finner du et forslag til hvordan man kan lage programmet.

Hvilke forandringer vil du gjøre i ditt trafikklys? Hvordan kan du videreutvikle dette? Er det mulig å legge inn varsel for fotgjengeroverang?
```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P1, 1)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P0, 0)
    pins.digitalWritePin(DigitalPin.P1, 0)
    pins.digitalWritePin(DigitalPin.P2, 1)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P1, 1)
    pins.digitalWritePin(DigitalPin.P2, 0)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P1, 0)	
})

```
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
