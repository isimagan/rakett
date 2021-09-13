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
Nedtellingen starter, og vi teller ned fra 5. Sett inn blokker så vi først viser tallet ``||basic:5||``, også tar vi ``||basic:pause (ms)||`` i ``1 sekund (1000 millisekunder)``.
``` blocks
input.onButtonPressed(Button.A, function(){
    basic.clearScreen()
    basic.showString("T-")
    basic.showNumber(5)
    basic.pause(1000)
})
```

## Steg 6
Gjør det samme igjen fem ganger. Men husk at dette er en nedtelling, så du må endre tallet til en mindre helt til ``0``.
``` blocks
input.onButtonPressed(Button.A, function(){
    basic.clearScreen()
    basic.showString("T-")
    basic.showNumber(5)
    basic.pause(1000)
    basic.showNumber(4)
    basic.pause(1000)
    basic.showNumber(3)
    basic.pause(1000)
    basic.showNumber(2)
    basic.pause(1000)
    basic.showNumber(1)
    basic.pause(1000)
    basic.showNumber(0)
    basic.pause(1000)
})
```

## Steg 7
Raketten skal skytes opp. Du må lage en animasjon av at raketten skytes opp ved å sette inn flere ``||basic:vis skjerm||``-blokker.

Sett inn dette under den nederste ``||basic:pause (ms) ||``. Avslutt med ``||basic:tøm skjerm||``.

``` blocks
input.onButtonPressed(Button.A, function(){
    basic.pause(1000)
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

## Ferdig! @showdialog
Fungerte det? Ta med iPaden til Martin og spør hvordan du får dette over til micro:biten din.

Hent din micro:bit og overfør. Så har du to andre oppgaver i **Showbie**.