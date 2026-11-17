+++
title = "Terminal Grundlagen"
date = 2026-11-17
description = "Die Grundlagen des Terminals: sich im Dateisystem bewegen, Dateien verwalten und Befehle mit Pipes verbinden."

[extra]
tags = ["Terminal", "Shell", "Befehle"]
+++

## Ausgangslage

Bei der Jujutsu- und der vim-Doku habe ich schon viel im Terminal gearbeitet.
Damit ich die wichtigsten Befehle nicht jedes Mal neu nachschlagen muss, fasse
ich die Grundlagen hier in einer Übersicht zusammen. So arbeite ich im Terminal
sicherer und schneller, auch mit jj und Git.

<!-- more -->

## Vorgehen

Zuerst habe ich recherchiert, welche Befehle man im Alltag am häufigsten
braucht. Dazu habe ich die `man`-Seiten und Anleitungen im Internet gelesen. Die
meisten Befehle habe ich nur nachgelesen. Pipes sowie `grep` und `find` habe ich
zusätzlich ausprobiert. Dafür habe ich einen Testordner angelegt, damit nichts
Wichtiges kaputtgeht. Ich verwende zsh, die Standard-Shell auf macOS.

```sh
mkdir ~/Desktop/terminal-spielwiese
cd ~/Desktop/terminal-spielwiese
```

### Navigation

| Befehl      | Wirkung                                     |
| ----------- | ------------------------------------------- |
| `pwd`       | Zeigt, in welchem Ordner man gerade ist     |
| `ls`        | Listet den Inhalt des Ordners auf           |
| `ls -la`    | Ausführliche Liste, auch versteckte Dateien |
| `cd ordner` | Wechselt in einen Ordner                    |
| `cd ..`     | Wechselt einen Ordner nach oben             |
| `cd ~`      | Wechselt in den Benutzerordner              |
| `cd -`      | Wechselt zurück in den vorherigen Ordner    |

Versteckte Dateien beginnen mit einem Punkt, zum Beispiel `.zshrc` oder `.jj`.
Ohne `-a` zeigt `ls` sie nicht an.

### Dateien und Ordner verwalten

```sh
mkdir -p notizen/swift     # Ordner anlegen, -p auch mit Unterordnern
touch notizen/todo.txt     # Leere Datei anlegen
cp notizen/todo.txt kopie.txt
cp -r notizen backup       # Ordner kopieren, -r für rekursiv
mv kopie.txt alt.txt       # Umbenennen
mv alt.txt notizen/        # Verschieben
rm notizen/alt.txt         # Datei löschen
rm -r backup               # Ordner löschen
```

`mv` macht beides: Es benennt um, wenn das Ziel ein neuer Name ist, und
verschiebt, wenn das Ziel ein Ordner ist.

Wichtig bei `rm`: Es gibt keinen Papierkorb. Was gelöscht ist, ist weg. Mit
`rm -i` fragt das Terminal vor jedem Löschen nach. Das Gegenteil ist `rm -rf`:
Es löscht einen Ordner mit allem Inhalt ohne jede Rückfrage. Schon ein
Tippfehler im Pfad kann dabei viel löschen, deshalb verwende ich es nur mit
Bedacht.

### Inhalte anschauen

| Befehl            | Wirkung                         |
| ----------------- | ------------------------------- |
| `cat datei`       | Gibt den ganzen Inhalt aus      |
| `less datei`      | Zeigt den Inhalt seitenweise an |
| `head -n 5 datei` | Zeigt die ersten 5 Zeilen       |
| `tail -n 5 datei` | Zeigt die letzten 5 Zeilen      |

`cat` eignet sich für kurze Dateien. Bei langen Dateien ist `less` besser. Dort
funktionieren einige Tasten wie in vim: `j` und `k` zum Scrollen, `/` zum Suchen
und `q` zum Beenden.

### Umleitungen und Pipes

Mit `>` schreibt man die Ausgabe eines Befehls in eine Datei, statt sie im
Terminal anzuzeigen. `>` überschreibt die Datei, `>>` hängt am Ende an.

```console
$ echo "Swift lernen" > notizen/todo.txt
$ echo "Terminal lernen" >> notizen/todo.txt
$ cat notizen/todo.txt
Swift lernen
Terminal lernen
```

Mit der Pipe `|` gibt man die Ausgabe eines Befehls direkt an den nächsten
weiter. So lassen sich einfache Befehle kombinieren:

```console
$ ls -la notizen | grep txt
-rw-r--r--  1 benutzer  staff  29 Nov  9 10:12 todo.txt
$ cat notizen/todo.txt | wc -l
       2
```

### Suchen

`grep` sucht nach Text in Dateien, `find` sucht nach Dateien selbst.

```sh
grep "Swift" notizen/todo.txt    # Zeilen mit "Swift" anzeigen
grep -i "swift" notizen/todo.txt # Gross-/Kleinschreibung ignorieren
grep -rn "TODO" .                # Rekursiv im Ordner, mit Zeilennummer
find . -name "*.txt"             # Alle .txt-Dateien finden
```

Der `*` steht für beliebig viele Zeichen. `"*.txt"` passt also auf jede Datei,
die mit `.txt` endet.

### Hilfe finden

Mit `man` öffnet man die Anleitung zu einem Befehl, zum Beispiel `man ls`. Die
Anleitung wird in `less` angezeigt, die Tasten sind also dieselben wie oben.

Viele Programme wie `jj` oder `git` kennen auch `--help`. Bei den
Standardbefehlen von macOS wie `ls` oder `cp` funktioniert das aber nicht, dort
hilft nur `man`.

### Nützliche Tastenkürzel

| Taste               | Wirkung                                |
| ------------------- | -------------------------------------- |
| `Tab`               | Befehle und Pfade automatisch ergänzen |
| `↑` / `↓`           | Durch frühere Befehle blättern         |
| `Ctrl+R`            | In früheren Befehlen suchen            |
| `Ctrl+C`            | Laufenden Befehl abbrechen             |
| `Ctrl+L`            | Terminal leeren (wie `clear`)          |
| `Ctrl+A` / `Ctrl+E` | Zum Zeilenanfang / Zeilenende springen |

### Aliase in der `~/.zshrc`

Für Befehle, die ich oft brauche, kann ich in der `~/.zshrc` eine Abkürzung
anlegen:

```sh
echo 'alias ll="ls -la"' >> ~/.zshrc
echo 'alias jl="jj log"' >> ~/.zshrc
source ~/.zshrc
```

Danach reicht `ll` statt `ls -la`. `source` lädt die Datei neu, sonst gelten die
Änderungen erst in einem neuen Terminalfenster.

### Andere Shells und Terminal-Programme

Das Terminal ist nur das Fenster, in dem man tippt. Die Befehle verarbeitet die
Shell, die darin läuft. Beides kann man austauschen.

Bekannte Shells:

| Shell   | Besonderheit                                                 |
| ------- | ------------------------------------------------------------ |
| bash    | Sehr verbreitet, ist Standard auf vielen Linux-Systemen      |
| zsh     | Standard auf macOS seit 2019, weitgehend kompatibel mit bash |
| fish    | Vorschläge und Farben ohne Einrichtung, eigene Syntax        |
| Nushell | Behandelt Ausgaben als Tabellen statt als reinen Text        |

fish ist vor allem einsteigerfreundlich: Während man tippt, schlägt es frühere
Befehle vor, und falsch geschriebene Befehle werden rot markiert. Dafür ist die
Syntax nicht mit bash und zsh kompatibel. Variablen setzt man zum Beispiel mit
`set -gx EDITOR vim` statt mit `export`, und die Konfiguration liegt in
`~/.config/fish/config.fish` statt in der `~/.zshrc`.

Bekannte Terminal-Programme auf macOS:

- **Terminal**: bei macOS vorinstalliert
- **iTerm2**: viele Einstellungen, zum Beispiel geteilte Fenster
- **Ghostty**: schnell und schlicht
- **Warp**: modernes Terminal mit eingebauten KI-Funktionen

## Reflexion

Die meisten Befehle kannte ich schon aus meiner Erfahrung und meinen früheren
Dokus. Durch die Recherche habe ich sie jetzt aber übersichtlich an einem Ort
und finde sie schneller, wenn ich sie brauche. Neu waren für mich das Flag `-i`
und die anderen Shells.
