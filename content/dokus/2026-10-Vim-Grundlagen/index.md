+++
title = "vim Grundlagen"
date = 2026-10-28
description = "Die Grundlagen des Texteditors vim: Modi verstehen, Text bearbeiten und vim im Terminal sicher bedienen."

[extra]
tags = ["vim", "Texteditor", "Terminal"]
+++

## Ausgangslage

Wenn ich mit jj oder Git eine Beschreibung ohne `-m` schreibe, öffnet sich ein
Editor im Terminal, meistens ist das vim. Damit ich mich dort bei Navigation und
Bedienung besser zurechtfinde, notiere ich die wichtigsten Grundlagen.

<!-- more -->

## Vorgehen

Zuerst habe ich viele Aufgaben im `vimtutor` durchgearbeitet, das bei vim
mitgeliefert wird. Danach habe ich die Befehle in einer eigenen Testdatei
ausprobiert.

```console
vimtutor
vim test.txt
```

### Die Modi

vim hat verschiedene Modi. Das ist der grösste Unterschied zu anderen Editoren.

| Modus   | Wechseln mit       | Wofür                        |
| ------- | ------------------ | ---------------------------- |
| Normal  | `Esc`              | Bewegen und Befehle          |
| Insert  | `i`, `a`, `o`, `O` | Text schreiben               |
| Visual  | `v`, `V`           | Text markieren               |
| Command | `:`                | Speichern, Beenden, Ersetzen |

In den Insert-Modus kommt man mit verschiedenen Tasten. Sie unterscheiden sich
darin, wo man anfängt zu schreiben:

| Taste | Wo man anfängt zu schreiben   |
| ----- | ----------------------------- |
| `i`   | vor dem Cursor                |
| `a`   | nach dem Cursor               |
| `o`   | in einer neuen Zeile darunter |
| `O`   | in einer neuen Zeile darüber  |

Wenn man nicht weiss, in welchem Modus man ist: `Esc` drücken, dann ist man im
Normal-Modus.

### Speichern und Beenden

| Befehl | Wirkung                   |
| ------ | ------------------------- |
| `:w`   | Speichern                 |
| `:q`   | Beenden                   |
| `:wq`  | Speichern und beenden     |
| `:q!`  | Beenden ohne zu speichern |

### Bewegen

| Taste      | Wirkung                     |
| ---------- | --------------------------- |
| `h j k l`  | links, runter, hoch, rechts |
| `w` / `b`  | Wort vor / zurück           |
| `0` / `$`  | Zeilenanfang / Zeilenende   |
| `gg` / `G` | Dateianfang / Dateiende     |

### Bearbeiten

| Taste    | Wirkung                      |
| -------- | ---------------------------- |
| `x`      | Zeichen löschen              |
| `dd`     | Zeile löschen (ausschneiden) |
| `yy`     | Zeile kopieren               |
| `p`      | Einfügen                     |
| `u`      | Rückgängig                   |
| `Ctrl+R` | Wiederherstellen             |

Befehle lassen sich mit einer Zahl kombinieren, zum Beispiel `3dd` löscht gleich
drei Zeilen.

### Suchen und Ersetzen

```text
/Suchbegriff        vorwärts suchen, n für nächsten Treffer
:%s/alt/neu/g       in der ganzen Datei ersetzen
```

### vim als Editor für jj und Git einstellen

Ohne Einstellung öffnet jj nano und Git vi (auf macOS vim). Damit beide vim
verwenden, setze ich die Umgebungsvariable `EDITOR`, die jj und Git beide
berücksichtigen:

```console
$ echo 'export EDITOR=vim' >> ~/.zshrc
$ source ~/.zshrc
$ jj config get ui.editor
vim
```

Ich verwende zsh, die Standard-Shell auf macOS. Bei bash heisst die Datei
`~/.bashrc`.

Danach öffnet `jj describe` ohne `-m` die Beschreibung direkt in vim.

## Reflexion

Am Anfang war vim ungewohnt, weil man nicht einfach losschreiben kann. Je mehr
ich die Befehle ausprobiert habe, desto besser kam ich mit vim zurecht.

Der `vimtutor` hat mir beim Einstieg geholfen, weil man die Befehle direkt
ausprobiert. Durch die Einstellung von `EDITOR` öffnet sich vim auch bei jj, so
kann ich das Gelernte im Alltag weiter üben.
