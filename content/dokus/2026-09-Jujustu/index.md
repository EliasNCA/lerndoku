+++
title = "Jujutsu Grundlagen"
date = 2026-09-28
description = "Die Grundlagen des Versionsverwaltungssystems Jujutsu: die wichtigsten Befehle kennenlernen und sicherer im Umgang mit Jujutsu werden."

[extra]
tags = ["Jujutsu", "Versionsverwaltung", "Befehle"]
+++

## Ausgangslage

Diesen Monat haben wir uns für ein Lehrlingsprojekt entschieden. Wir hatten
schon einige Ideen gesammelt und sind dabei auf eine gestossen, die für den
Alltag spannend klingt: eine eigene Code-Hosting-Plattform für das
Versionsverwaltungssystem Jujutsu. Weil mich Jujutsu auch unabhängig vom Projekt
interessiert, möchte ich einige Befehle kennenlernen.

<!-- more -->

## Vorgehen

### Installation

Zuerst musste ich jj über das Terminal installieren, auf macOS mit Homebrew:

```console
brew install jj
```

Dann vor dem ersten `jj describe` Name und Mailadresse setzen, das gilt
systemweit und ist nur einmal nötig:

```console
jj config set --user user.name "Dein Name"
jj config set --user user.email "mail@mail.ch"
```

### Testrepository aufsetzen

Um ein Testrepository mit jj und git aufzusetzen, schreibt man:

```console
$ mkdir jj-spielwiese && cd jj-spielwiese
$ jj git init --colocate
Initialized repo in "."
```

Darin habe ich die Befehle der Reihe nach eingegeben, statt sie nur nachzulesen,
und nach jedem Schritt mit `jj log` geprüft, wie sich der Verlauf verändert hat.

Bemerkung: `--colocate` legt neben `.jj/` ein normales `.git/` an. Beide
Werkzeuge arbeiten dann auf demselben Verlauf, und die gewohnten git-Befehle
bleiben verfügbar. Ohne das Flag liegt das Git-Repository versteckt in
`.jj/repo/store/git` und ist für `git` und die IDE nicht erreichbar.

Der Zustand direkt nach dem Aufsetzen:

```console
$ jj st
The working copy has no changes.
Working copy (@) : mzsrmyvy bf040a79 (empty) (no description set)
Parent commit (@-): zzzzzzzz 00000000 (empty) (no description set)
```

Was man bemerkt, ist, dass gegenüber `git status` der Staging-Bereich fehlt.
Alle Änderungen sind automatisch Teil der aktuellen Änderung.

Jetzt werden zwei Änderungen umgesetzt:

```console
echo "Erste Zeile" > notizen.md
jj describe -m "Notizen angelegt"
jj new
echo "Zweite Zeile" >> notizen.md
jj describe -m "Zweite Zeile ergänzt"
```

`jj describe` erzeugt nichts, die Änderung existiert bereits, sobald eine Datei
bearbeitet wird. Die Änderung hat nur keinen Namen. `jj new` schliesst die
aktuelle Änderung ab und beginnt eine neue darüber. Beide zusammen entsprechen
ungefähr dem, was `git commit` in einem Schritt macht.

```console
$ jj log
@  lsswmvwn testmail@mail.ch 2026-09-28 11:33:12 001bf3cb
│  Zweite Zeile ergänzt
○  mzsrmyvy testmail@mail.ch 2026-09-28 11:32:52 bb55e2c2
│  Notizen angelegt
◆  zzzzzzzz root() 00000000
```

Wichtig sind die zwei IDs pro Zeile. Links ist die Change-ID (`lsswmvwn`),
rechts der Commit-Hash (`001bf3cb`). Die Change-ID bleibt stabil, auch wenn die
Änderung umgeschrieben wird, der Hash ändert sich jedes Mal. In Git gibt es nur
den Hash, und nach einem `--amend` besteht keine Verbindung mehr zum alten
Commit. Genau darauf baut unser Projekt auf.

## Befehlsübersicht

### Einrichten

| Befehl                              | Was er macht                       | Git-Entsprechung      |
| ----------------------------------- | ---------------------------------- | --------------------- |
| `jj git init --colocate`            | Repository anlegen, `.git` daneben | `git init`            |
| `jj git clone <url>`                | Repository klonen                  | `git clone`           |
| `jj config set --user <key> <wert>` | Einstellung setzen                 | `git config --global` |

### Änderungen bearbeiten

| Befehl                 | Was er macht                                  | Git-Entsprechung              |
| ---------------------- | --------------------------------------------- | ----------------------------- |
| `jj st`                | Zustand der Arbeitskopie                      | `git status`                  |
| `jj describe -m "..."` | Beschreibung setzen oder ändern               | Teil von `git commit -m`      |
| `jj new`               | Aktuelle Änderung abschliessen, neue beginnen | Teil von `git commit`         |
| `jj new <id>`          | Neue Änderung auf einer bestimmten aufbauen   | `git checkout` + `git commit` |
| `jj edit <id>`         | In einer älteren Änderung weiterarbeiten      | `git rebase -i` (edit)        |
| `jj squash`            | Änderung in die darüberliegende schieben      | `git commit --amend`          |
| `jj split`             | Eine Änderung in zwei aufteilen               | `git reset -p` + commit       |
| `jj abandon <id>`      | Änderung verwerfen                            | `git reset --hard`            |
| `jj restore <pfad>`    | Datei auf früheren Stand zurücksetzen         | `git restore`                 |

### Verlauf ansehen

| Befehl               | Was er macht                          | Git-Entsprechung  |
| -------------------- | ------------------------------------- | ----------------- |
| `jj log`             | Verlauf als Graph                     | `git log --graph` |
| `jj log -r <revset>` | Verlauf gefiltert                     | `git log <range>` |
| `jj diff`            | Änderungen im Detail                  | `git diff`        |
| `jj show <id>`       | Beschreibung und Diff einer Änderung  | `git show`        |
| `jj evolog`          | Wie sich eine Änderung entwickelt hat | —                 |

### Verlauf umbauen

| Befehl              | Was er macht                          | Git-Entsprechung  |
| ------------------- | ------------------------------------- | ----------------- |
| `jj rebase -d <id>` | Änderung auf eine andere Basis setzen | `git rebase`      |
| `jj duplicate <id>` | Kopie einer Änderung erstellen        | `git cherry-pick` |
| `jj resolve`        | Konflikte auflösen                    | `git mergetool`   |

### Bookmarks

Bookmarks sind jjs Ersatz für Branch-Namen. Anders als in Git wandern sie nicht
automatisch mit, wenn eine neue Änderung entsteht (man setzt sie bewusst).

| Befehl                              | Was er macht                      | Git-Entsprechung    |
| ----------------------------------- | --------------------------------- | ------------------- |
| `jj bookmark list`                  | Alle Bookmarks anzeigen           | `git branch --list` |
| `jj bookmark create <name>`         | Bookmark anlegen                  | `git branch <name>` |
| `jj bookmark set <name> -r <id>`    | Bookmark auf eine Änderung setzen | `git branch -f`     |
| `jj bookmark move <name> --to <id>` | Bookmark verschieben              | `git branch -f`     |
| `jj bookmark delete <name>`         | Bookmark löschen                  | `git branch -d`     |
| `jj bookmark track <name>@origin`   | Remote-Bookmark verfolgen         | `git branch -u`     |

### Mit einem Remote arbeiten

| Befehl                | Was er macht                                  | Git-Entsprechung |
| --------------------- | --------------------------------------------- | ---------------- |
| `jj git fetch`        | Änderungen vom Remote holen                   | `git fetch`      |
| `jj git push`         | Bookmarks zum Remote pushen                   | `git push`       |
| `jj git push -c <id>` | Änderung pushen, Bookmark automatisch anlegen | —                |

### Rückgängig machen

| Befehl               | Was er macht                               | Git-Entsprechung             |
| -------------------- | ------------------------------------------ | ---------------------------- |
| `jj undo`            | Letzte Operation zurücknehmen              | —                            |
| `jj op log`          | Alle bisherigen Operationen                | `git reflog` (eingeschränkt) |
| `jj op restore <id>` | Repository auf einen früheren Stand setzen | —                            |

## Reflexion

Der Einstieg ging schneller als erwartet: Installation, Konfiguration und erstes
Repository waren in wenigen Minuten erledigt. Gewöhnen musste ich mich daran,
dass es keine Staging-Area gibt. In Git wähle ich mit `git add` die Dateien aus,
die in den Commit kommen - in jj gehört automatisch alles zur aktuellen
Änderung.

Ob ich zukünftig jj im Alltag weiterverwenden werde, kann ich noch nicht sagen,
da ich noch zu wenig damit gearbeitet habe. Bisher habe ich nur einzelne Befehle
ausprobiert.
