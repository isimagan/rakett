# Rakettoppskytning

## Steg 1
Vi starter med å tegne et bilde av en rakett innenfor ``||basic:ved start||``.
``` blocks
basic.showLeds(`
    . . # . .
    . # # # .
    . # # # .
    # # # # #
    . # # # .
    `)
```

## Steg 2
For å fyre av raketten vår må vi trykke på ``knapp A``, så sett inn ``||input:når knapp A trykkes||``.
``` blocks
input.onButtonPressed(Button.A, function(){})
```

## Steg 3
Første som må skje er at alt på skjermen fjernes, så sett inn ``||basic:tøm skjerm||``.
``` blocks
input.onButtonPressed(Button.A, function(){
    basic.clearScreen()
})
```

## Steg 4
I NASA sier de alltid "T-", og deretter begynner nedtellingen. Vis teksten ``T-``.
``` blocks
input.onButtonPressed(Button.A, function(){
    basic.clearScreen()
    basic.showString("T-")
})
```

## Steg 5
Vi skal nå bruke en ny blokk: ``||loops:gjenta for indeks fra 0 til 4||``. Denne blokken gjentar blokkene på innsiden fem ganger (0.gang, 1.gang, 2.gang, 3.gang, 4.gang).

Men hvorfor ikke bare bruke ``||loops:gjenta 4 ganger||``? Jo, for her kan vi bruke variabelen ``||variables:indeks||`` som ``||loops:gjenta||``-blokken lager til kodingen innenfor.
``` blocks
input.onButtonPressed(Button.A, function(){
    basic.clearScreen()
    basic.showString("T-")
    for (let indeks = 0; indeks <= 4; indeks++) {}
})
```

## Steg 6
I ``||loops:gjenta||``-blokken bytter du ut ``4`` med ``5``.
``` blocks
input.onButtonPressed(Button.A, function(){
    basic.clearScreen()
    basic.showString("T-")
    for (let indeks = 0; indeks <= 5; indeks++) {}
})
```

## Steg 7
Blokken teller oppover fra 0 til 5. Men vi vil telle nedover, og vise tallet. Derfor må vi sette inn ``||basic:vis tall||`` og vise tallet ``5 - `` ``||variables:indeks||``.
``` blocks
input.onButtonPressed(Button.A, function(){
    basic.clearScreen()
    basic.showString("T-")
    for (let indeks = 0; indeks <= 5; indeks++) {}
})
```

### Steg 7a
Sett inn ``||basic:vis tall||``.
``` blocks
input.onButtonPressed(Button.A, function(){
    basic.clearScreen()
    basic.showString("T-")
    for (let indeks = 0; indeks <= 5; indeks++) {
        basic.showNumber(0)
    }
})
```

### Steg 7b
I stedet for ``0`` setter vi inn fra matematikk ``||math:0 - 0||``.
``` blocks
input.onButtonPressed(Button.A, function(){
    basic.clearScreen()
    basic.showString("T-")
    for (let indeks = 0; indeks <= 5; indeks++) {
        basic.showNumber(0 - 0)
    }
})
```

### Steg 7c
Bytt ut første ``0`` med ``5``, og den andre med ``||variables:indeks||``. Dra variabelen fra ``||loops:gjenta||``-blokken ned til den siste ``0``.
``` blocks
input.onButtonPressed(Button.A, function(){
    basic.clearScreen()
    basic.showString("T-")
    for (let indeks = 0; indeks <= 5; indeks++) {
        basic.showNumber(5 - indeks)
    }
})
```

## Steg 8
Nå skal raketten skytes opp. Vis raketten fra ``||basic:ved start||``. Den må animeres ut av micro:biten, og da trenger du å sette inn flere ``||basic:vis skjerm||``-blokker.

Den settes inn etter ``||loops:gjenta||``-blokken. Avslutt med å tømme skjermen.
``` blocks
input.onButtonPressed(Button.A, function(){
    basic.showLeds(`
        . . # . .
        . # # # .
        . # # # .
        # # # # #
        . # # # .
        `)
    basic.showLeds(`
        . # # # .
        . # # # .
        # # # # #
        . # # # .
        . . . . .
        `)
    basic.showLeds(`
        . # # # .
        # # # # #
        . # # # .
        . . . . .
        . . . . .
        `)
    basic.showLeds(`
        # # # # #
        . # # # .
        . . . . .
        . . . . .
        . . . . .
        `)
    basic.showLeds(`
        . # # # .
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        `)
    basic.clearScreen()
})
```
