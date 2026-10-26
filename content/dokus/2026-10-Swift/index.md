+++
title = "Swift Grundlagen"
date = 2026-10-26
description = "Die Grundlagen der Programmiersprache Swift: Syntax, Datentypen und Kontrollstrukturen kennenlernen."

[extra]
tags = ["Swift", "Programmiersprache", "Syntax"]
+++

## Ausgangslage

Wir haben bereits mit dem Lehrlingsprojekt begonnen, bei dem wir hauptsächlich
mit Swift programmieren. Deshalb halte ich es für eine gute Idee, die Grundlagen
von Swift gründlich kennenzulernen und festzuhalten. So kann ich effizienter mit
Swift arbeiten.

<!-- more -->

## Vorgehen

Ich habe die Beispiele in einer Swift-Datei mit dem `#Playground`-Makro
ausprobiert. Der Code innerhalb von `#Playground { }` wird direkt ausgeführt,
und Xcode zeigt die Ergebnisse im Canvas an.

### Konstanten und Variablen

Mit `let` deklariert man eine Konstante, mit `var` eine Variable. Einer
Konstanten kann man nach der ersten Zuweisung keinen neuen Wert mehr geben.

```swift
let name = "Tim"
var alter = 17
alter = 18      // funktioniert
// name = "Theo" // Das gibt einen Fehler aus: name ist eine Konstante
```

In Swift verwendet man standardmässig `let` und nur dann `var`, wenn sich der
Wert wirklich ändert. Xcode gibt sogar eine Warnung aus, wenn eine Variable nie
verändert wird.

### Datentypen

Die wichtigsten Grundtypen:

| Typ      | Beschreibung  | Beispiel  |
| -------- | ------------- | --------- |
| `Int`    | Ganze Zahl    | `42`      |
| `Double` | Kommazahl     | `3.14`    |
| `String` | Text          | `"Hallo"` |
| `Bool`   | Wahrheitswert | `true`    |

Den Datentyp muss man meistens nicht angeben, da Swift ihn aus dem Wert ableitet
(Typinferenz). Man kann ihn aber auch explizit hinschreiben:

```swift
let zahl = 42             // Swift erkennt Int
let preis: Double = 9.90  // Typ explizit angegeben
```

Mit `\()` lassen sich Werte direkt in einen String einfügen. Beispiel:

```swift
let alter = 50
let name = "Tim"

print("Sein Name ist \(name) und er ist \(alter) Jahre alt.")
```

### Arrays und Dictionaries

Ein Array ist eine geordnete Liste, ein Dictionary speichert
Schlüssel-Wert-Paare. Mit `let` deklariert sind beide unveränderlich.

```swift
var sprachen = ["Swift", "Java", "Python"]
sprachen.append("Kotlin")

var noten = ["Mathe": 5.5, "Deutsch": 5.0]
noten["Englisch"] = 4.5
```

### Optionals

Ein Optional (`?` nach dem Typ) kann auch keinen Wert haben, also `nil` sein.
Bevor man es verwendet, muss man es auspacken:

```swift
var spitzname: String? = nil

if let spitzname {
    print("Spitzname: \(spitzname)")
}

let anzeige = spitzname ?? "Kein Spitzname"  // Ersatzwert, falls nil
```

### Kontrollstrukturen

Kontrollstrukturen werden verwendet, um zu bestimmen, ob und wie oft Code
ausgeführt wird. Bedingungen brauchen keine Klammern. Bei `switch` ist kein
`break` nötig, dafür müssen aber alle möglichen Werte abgedeckt sein.

Beispiel:

```swift
if alter >= 18 {
    print("Volljährig")
} else {
    print("Minderjährig")
}

switch alter {
case 0..<16:  print("Kind")
case 16...17: print("Jugendlich")
default:      print("Erwachsen")
}

for sprache in sprachen {
    print(sprache)
}

var countdown = 3
while countdown > 0 {
    countdown -= 1
}
```

`guard` bricht früh ab, wenn eine Bedingung nicht erfüllt ist, und hält den
restlichen Code so übersichtlich:

```swift
func begruessen(name: String?) {
    guard let name else { return }
    print("Hallo, \(name)")
}
```

### Funktionen

Funktionen werden mit `func` deklariert, der Rückgabetyp steht nach dem Pfeil
`->`. Bei einem Aufruf schreibt man den Parameternamen mit, ausser man setzt `_`
davor. Bei nur einem Ausdruck kann `return` ausgelassen werden.

```swift
func addieren(a: Int, b: Int) -> Int {
    a + b
}

func quadrat(_ zahl: Int) -> Int {
    zahl * zahl
}

addieren(a: 2, b: 3)
quadrat(4)
```

## Reflexion

Durch das Ausprobieren kenne ich die wichtigsten Grundlagen von Swift und kann
diese jederzeit schnell nachschlagen. Vieles war mir aus Java vertraut, neu war
vor allem `guard`. Schwierig war am Anfang der Playground: Erst nachdem ich den
Code in `#Playground { }` gesetzt hatte, wurde er ausgeführt.
