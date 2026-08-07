# Rechercheauftrag: On-Device-AI für mobile Apps

## Auftrag

Während der nächsten zwei bis drei Tagen recherchiert ihr verschiedene
Möglichkeiten für eine mobile App mit einem LLM.

Die App soll später grundsätzlich auf folgenden Plattformen umgesetzt werden
können:

- iOS mit Swift
- Android mit Java

Ihr müsst noch keine fertige Projektidee entwickeln und noch keine App
programmieren.

Zuerst sammelt ihr möglichst viele interessante Technologien, AI-Modelle, APIs
und mögliche Funktionen.

---

## Ziel

Am Ende der Recherche sollt ihr wissen:

- Welche AI-Modelle gibt es?
- Welche Modelle könnten auf einem Smartphone laufen?
- Welche Aufgaben können diese Modelle lösen?
- Welche APIs könnten für eine mobile App verwendet werden?
- Welche Technologien gibt es für iOS und Android?
- Welche Themen interessieren euch besonders?
- Welche Möglichkeiten wären für ein späteres Projekt realistisch?

---

## 1. AI-Modelle recherchieren

Sucht mindestens **15 verschiedene AI-Modelle**, die euch interessieren.

Ihr könnt unter anderem auf folgenden Plattformen suchen:

- Hugging Face Models
- Kaggle Models
- ModelScope
- TensorFlow Hub
- PyTorch Hub
- ONNX Model Zoo
- Apple Core ML Models
- Qualcomm AI Hub Models
- NVIDIA NGC Catalog
- Ollama Library

Ihr müsst nicht nur Sprachmodelle suchen.

Mögliche Arten von AI-Modellen:

- Textgenerierung
- Chatbots
- Übersetzung
- Zusammenfassung
- Spracherkennung
- Text-to-Speech
- Bilderkennung
- Objekterkennung
- Texterkennung aus Bildern
- Bildgenerierung
- Sentimentanalyse
- Rechtschreibkorrektur
- Klassifikation
- Frage-Antwort-Systeme
- Modelle für Dokumente

Zusätzlich könnt ihr Technologien untersuchen, mit denen AI-Modelle in Apps
integriert oder lokal ausgeführt werden können:

- Core ML
- MLX
- LiteRT
- MediaPipe
- ONNX Runtime
- llama.cpp
- TensorFlow
- PyTorch

### Fragen zu jedem Modell

Beantwortet zu jedem gefundenen Modell kurz folgende Fragen:

1. Wie heisst das Modell?
2. Wo wurde das Modell gefunden?
3. Wer hat das Modell entwickelt? (optional wäre nice zu wissen)
4. Was kann das Modell?
5. Warum interessiert euch das Modell?
6. Welche Eingaben verarbeitet es?
7. Welche Ergebnisse erstellt es?
8. Welche Sprachen unterstützt es?
9. Wie gross ist das Modell?
10. Kann es ohne Internet verwendet werden?
11. Könnte es auf einem Smartphone laufen?
12. Gibt es eine kleinere oder quantisierte Version?
13. Welche Lizenz besitzt das Modell?
14. Welche Einschränkungen hat das Modell?
15. Wofür könnte man es in einer App verwenden?

### Tabelle für die Modelle

| Nr. | Modell                     | Aufgabe                                  | Grösse                                   | Offline möglich | Smartphone geeignet   | Quelle                          |
| --: | -------------------------- | ---------------------------------------- | ---------------------------------------- | --------------- | --------------------- | ------------------------------- |
|   1 | Instella-MoE-16B-A3B-Think | Textgenerierung, Chatbot, Reasoning      | 16B Parameter (2,8B aktiv)               | Ja              | Eher nein             | Hugging Face (AMD)              |
|   2 | Fine-Tuned T5 Small        | Textezusammenfassung                     | ca. 242 MB                               | Ja              | Ja                    | Hugging Face (Falcons.ai)       |
|   3 | NLLB-200 Distilled 600M    | Textübersetzung                          | 600 Mio. Parameter (circa 2,5 GB)        | Ja              | Eher nein             | Hugging Face (Meta AI)          |
|   4 | VGGish                     | Audioanalyse und Geräuscherkennung       | ca. 275 MB                               | Ja              | Ja                    | Kaggle Models (Google)          |
|   5 | BGE                        | Text-Embeddings und Suche                | Je nach Version, z.B. 33,4 Mio Parameter | Ja              | Ja (kleine Versionen) | Kaggle Models (Keras)           |
|   6 | Diffusion Gemma            | Textgenerierung mit Diffusionsverfahren  | 25.2 Mrd. Parameter (3.8 Mrd aktiv)      | Ja              | Eher nein             | Kaggle Models (Google DeepMind) |
|   7 | segmentation-3.0           | Sprechererkennung und Audiosegmentierung | ca. 6 MB                                 | Ja              | Ja                    | Hugging Face (pyannote)         |
|   8 | Donut-Base                 | Dokumentanalyse                          | 200 Mio. Parameter, 800 MB               | Ja              | Ja                    | Hugging Face (naver-clova-ix)   |
|   9 | Blip-image-captioning-base | Bildbeschreibung                         | 247 Mio. Parameter, 990 MB               | Ja              | Ja                    | Hugging Face (Saleforce)        |
|  10 | SpeechT5_tts               | Text-zu-Sprache                          | 144 Mio. Parameter, 586 MB               | Ja              | Ja                    | Hugging Face (Microsoft)        |
|  11 |                            |                                          |                                          |                 |                       |                                 |
|  12 |                            |                                          |                                          |                 |                       |                                 |
|  13 |                            |                                          |                                          |                 |                       |                                 |
|  14 |                            |                                          |                                          |                 |                       |                                 |
|  15 |                            |                                          |                                          |                 |                       |                                 |

#### 1. Modell: Instella-MoE-16B-A3B-Think Fragen beantworten

| Frage                                                | Antwort                                                                                                                      |
| ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| 1. Wie heisst das Modell?                            | Instella-MoE-16B-A3B-Think                                                                                                   |
| 2. Wo wurde das Modell gefunden?                     | Hugging Face                                                                                                                 |
| 3. Wer hat das Modell entwickelt?                    | AMD                                                                                                                          |
| 4. Was kann das Modell?                              | Texte generieren, Fragen beantworten und Anweisungen befolgen.                                                               |
| 5. Warum interessiert euch das Modell?               | Es wurde von AMD entwickelt und ist als Open-Source-Modell verfügbar.                                                        |
| 6. Welche Eingaben verarbeitet es?                   | Texte und Chat-Nachrichten.                                                                                                  |
| 7. Welche Ergebnisse erstellt es?                    | Texte und Antworten.                                                                                                         |
| 8. Welche Sprachen unterstützt es?                   | Hauptsächlich Englisch.                                                                                                      |
| 9. Wie gross ist das Modell?                         | 16 Milliarden Parameter.                                                                                                     |
| 10. Kann es ohne Internet verwendet werden?          | Ja, nach dem Herunterladen.                                                                                                  |
| 11. Könnte es auf einem Smartphone laufen?           | Eher nein, da es zu gross ist.                                                                                               |
| 12. Gibt es eine kleinere oder quantisierte Version? | Nein. Es gibt verschiedene Trainingsstufen (Pretrain, Base, SFT, DPO, Think), aber keine kleinere oder quantisierte Version. |
| 13. Welche Lizenz besitzt das Modell?                | ResearchRAIL License                                                                                                         |
| 14. Welche Einschränkungen hat das Modell?           | Benötigt viel Speicher und Rechenleistung.                                                                                   |
| 15. Wofür könnte man es in einer App verwenden?      | Chatbot, Textgenerator oder KI-Assistent.                                                                                    |

#### 2. Modell Fine-Tuned T5 Small Fragen beantworten

| Frage                                                | Antwort                                                                                             |
| ---------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| 1. Wie heisst das Modell?                            | Fine-Tuned T5 Small                                                                                 |
| 2. Wo wurde das Modell gefunden?                     | Hugging Face                                                                                        |
| 3. Wer hat das Modell entwickelt?                    | Falcons.ai                                                                                          |
| 4. Was kann das Modell?                              | Es fasst lange Texte zu kurzen Zusammenfassungen zusammen.                                          |
| 5. Warum interessiert euch das Modell?               | Es eignet sich gut zum Zusammenfassen von Texten und Dokumenten.                                    |
| 6. Welche Eingaben verarbeitet es?                   | Texte.                                                                                              |
| 7. Welche Ergebnisse erstellt es?                    | Kurze Zusammenfassungen von Texten.                                                                 |
| 8. Welche Sprachen unterstützt es?                   | Englisch.                                                                                           |
| 9. Wie gross ist das Modell?                         | Ca. 242 MB.                                                                                         |
| 10. Kann es ohne Internet verwendet werden?          | Ja, nach dem Herunterladen.                                                                         |
| 11. Könnte es auf einem Smartphone laufen?           | Ja, da es ein relativ kleines Modell ist.                                                           |
| 12. Gibt es eine kleinere oder quantisierte Version? | Keine kleinere Version auf der Modellseite. Es werden jedoch ONNX- und Core ML-Versionen angeboten. |
| 13. Welche Lizenz besitzt das Modell?                | Apache 2.0                                                                                          |
| 14. Welche Einschränkungen hat das Modell?           | Hauptsächlich für englische Texte geeignet.                                                         |
| 15. Wofür könnte man es in einer App verwenden?      | Zum Zusammenfassen von Dokumenten, Artikeln oder Notizen.                                           |

#### 3. Modell: NLLB-200 Distilled 600M Fragen beantworten

| Frage                                                | Antwort                                                                   |
| ---------------------------------------------------- | ------------------------------------------------------------------------- |
| 1. Wie heisst das Modell?                            | NLLB-200 Distilled 600M                                                   |
| 2. Wo wurde das Modell gefunden?                     | Hugging Face                                                              |
| 3. Wer hat das Modell entwickelt?                    | Meta AI (Facebook)                                                        |
| 4. Was kann das Modell?                              | Es übersetzt Texte zwischen vielen verschiedenen Sprachen.                |
| 5. Warum interessiert euch das Modell?               | Es unterstützt sehr viele Sprachen und eignet sich für Übersetzungen.     |
| 6. Welche Eingaben verarbeitet es?                   | Texte.                                                                    |
| 7. Welche Ergebnisse erstellt es?                    | Übersetzte Texte.                                                         |
| 8. Welche Sprachen unterstützt es?                   | Rund 200 Sprachen.                                                        |
| 9. Wie gross ist das Modell?                         | 600 Millionen Parameter (ca. 2,5 GB).                                     |
| 10. Kann es ohne Internet verwendet werden?          | Ja, nach dem Herunterladen.                                               |
| 11. Könnte es auf einem Smartphone laufen?           | Eher nein, da es relativ gross ist.                                       |
| 12. Gibt es eine kleinere oder quantisierte Version? | Ja, es gibt kleinere NLLB-Modelle, z. B. eine 350M-Version.               |
| 13. Welche Lizenz besitzt das Modell?                | CC-BY-NC 4.0                                                              |
| 14. Welche Einschränkungen hat das Modell?           | Nicht für kommerzielle Nutzung gedacht und für Smartphones eher zu gross. |
| 15. Wofür könnte man es in einer App verwenden?      | Übersetzungs-App, Chat-Übersetzer oder Übersetzung von Dokumenten.        |

#### 4. Modell: VGGish Fragen beantworten

| Frage                                                | Antwort                                             |
| ---------------------------------------------------- | --------------------------------------------------- |
| 1. Wie heisst das Modell?                            | VGGish                                              |
| 2. Wo wurde das Modell gefunden?                     | Kaggie Models                                       |
| 3. Wer hat das Modell entwickelt?                    | Google                                              |
| 4. Was kann das Modell?                              | Es analysiert Audiodaten und erkennt Audio-Merkmale |
| 5. Warum interessiert euch das Modell?               | Es eignet sich für Audio- und Geräuscherkennung     |
| 6. Welche Eingaben verarbeitet es?                   | Audiodaten und Audiosignale                         |
| 7. Welche Ergebnisse erstellt es?                    | Audio-Merkmale                                      |
| 8. Welche Sprachen unterstützt es?                   | Keine, da es Audio verarbeitet                      |
| 9. Wie gross ist das Modell?                         | ca. 275 MB                                          |
| 10. Kann es ohne Internet verwendet werden?          | Ja                                                  |
| 11. Könnte es auf einem Smartphone laufen?           | Ja                                                  |
| 12. Gibt es eine kleinere oder quantisierte Version? | Ja, es gibt mobile Versionen                        |
| 13. Welche Lizenz besitzt das Modell?                | Apache 2.0                                          |
| 14. Welche Einschränkungen hat das Modell?           | Erkennt keine Sprache oder Texte                    |
| 15. Wofür könnte man es in einer App verwenden?      | Geräuscherkennung und Audioanalyse                  |

#### 5. Modell: BGE (BAAI General Embedding) Fragen beantworten

| Frage                                                | Antwort                                                                           |
| ---------------------------------------------------- | --------------------------------------------------------------------------------- |
| 1. Wie heisst das Modell?                            | BGE                                                                               |
| 2. Wo wurde das Modell gefunden?                     | Kaggle Models                                                                     |
| 3. Wer hat das Modell entwickelt?                    | BAAI (Beijing Academy of Artificial Intelligence)                                 |
| 4. Was kann das Modell?                              | Es erstellt Embeddings für Texte, um sie zu vergleichen und durchsuchen zu können |
| 5. Warum interessiert euch das Modell?               | Es eignet sich für intelligente Suchfunktionen                                    |
| 6. Welche Eingaben verarbeitet es?                   | Texte                                                                             |
| 7. Welche Ergebnisse erstellt es?                    | Text-Embeddings                                                                   |
| 8. Welche Sprachen unterstützt es?                   | Mehrere Sprachen (je nach Modellversion)                                          |
| 9. Wie gross ist das Modell?                         | Unterschiedlich, je nach Version (z.B. 33,4 Mio Parameter                         |
| 10. Kann es ohne Internet verwendet werden?          | Ja                                                                                |
| 11. Könnte es auf einem Smartphone laufen?           | Ja, kleinere Versionen sind dafür geeignet                                        |
| 12. Gibt es eine kleinere oder quantisierte Version? | Ja, es gibt verschiedene Modellgrössen                                            |
| 13. Welche Lizenz besitzt das Modell?                | MIT                                                                               |
| 14. Welche Einschränkungen hat das Modell?           | Es erzeugt keine Texte oder Antworten                                             |
| 15. Wofür könnte man es in einer App verwenden?      | Intelligente Suche, Dokumentensuche oder Empfehlungssysteme                       |

#### 6. Modell Diffusion Gemma Fragen beantworten

| Frage                                                | Antwort                                                              |
| ---------------------------------------------------- | -------------------------------------------------------------------- |
| 1. Wie heisst das Modell?                            | Diffusion Gemma                                                      |
| 2. Wo wurde das Modell gefunden?                     | Kaggle Models                                                        |
| 3. Wer hat das Modell entwickelt?                    | Google DeepMind                                                      |
| 4. Was kann das Modell?                              | Es generiert Texte mit einem Diffusionsverfahren                     |
| 5. Warum interessiert euch das Modell?               | Es zeigt eine andere Methode zur Textgenerierung als klassische LLMs |
| 6. Welche Eingaben verarbeitet es?                   | Text, Bilder und Videos                                              |
| 7. Welche Ergebnisse erstellt es?                    | Texte                                                                |
| 8. Welche Sprachen unterstützt es?                   | Mehrere Sprachen                                                     |
| 9. Wie gross ist das Modell?                         | 25.2 Mrd. Parameter                                                  |
| 10. Kann es ohne Internet verwendet werden?          | Ja                                                                   |
| 11. Könnte es auf einem Smartphone laufen?           | Eher nein                                                            |
| 12. Gibt es eine kleinere oder quantisierte Version? | Ja, es gibt quantisierte Versionen                                   |
| 13. Welche Lizenz besitzt das Modell?                | Apache 2.0                                                           |
| 14. Welche Einschränkungen hat das Modell?           | Benötigt leistungsstarke Hardware                                    |
| 15. Wofür könnte man es in einer App verwenden?      | Chatbot, Textgenerator oder Schreibassistent                         |

#### 7. Modell segmentation-3.0 Fragen beantworten

| Frage                                                | Antwort                                                           |
| ---------------------------------------------------- | ----------------------------------------------------------------- |
| 1. Wie heisst das Modell?                            | segmentation-3.0                                                  |
| 2. Wo wurde das Modell gefunden?                     | Hugging Face                                                      |
| 3. Wer hat das Modell entwickelt?                    | pyannote                                                          |
| 4. Was kann das Modell?                              | Es erkennt, wann gesprochen wird und trennt verschiedene Sprachen |
| 5. Warum interessiert euch das Modell?               | Es eignet sich für Sprach- und Audioanwendungen                   |
| 6. Welche Eingaben verarbeitet es?                   | Audiodateien                                                      |
| 7. Welche Ergebnisse erstellt es?                    | Sprachsegmente und Sprecherinformationen                          |
| 8. Welche Sprachen unterstützt es?                   | Mehrere Sprachen                                                  |
| 9. Wie gross ist das Modell?                         | Ca. 6 MB                                                          |
| 10. Kann es ohne Internet verwendet werden?          | Ja                                                                |
| 11. Könnte es auf einem Smartphone laufen?           | Ja                                                                |
| 12. Gibt es eine kleinere oder quantisierte Version? | Ja, es gibt quantisierte Versionen                                |
| 13. Welche Lizenz besitzt das Modell?                | MIT                                                               |
| 14. Welche Einschränkungen hat das Modell?           | Es verarbeitet nur Audio und erzeugt keine Texte                  |
| 15. Wofür könnte man es in einer App verwenden?      | Sprechererkennung, Sprachaufnahmen oder Meeting-Analyse           |

#### 8. Modell: donut-base Fragen beantworten

| Frage                                                | Antwort                                                               |
| ---------------------------------------------------- | --------------------------------------------------------------------- |
| 1. Wie heisst das Modell?                            | Donut-Base                                                            |
| 2. Wo wurde das Modell gefunden?                     | Hugging Face                                                          |
| 3. Wer hat das Modell entwickelt?                    | naver-clova-ix                                                        |
| 4. Was kann das Modell?                              | Es analysiert Dokumente und liest Informationen direkt aus Bildern    |
| 5. Warum interessiert euch das Modell?               | Es eignet sich für die Verarbeitung von Dokumenten                    |
| 6. Welche Eingaben verarbeitet es?                   | Dokumentbilder und Bilder                                             |
| 7. Welche Ergebnisse erstellt es?                    | Texte und Informationen aus Dokumenten                                |
| 8. Welche Sprachen unterstützt es?                   | Mehrere Sprachen (Englisch, Chinesisch, Japanisch und Koreanisch)     |
| 9. Wie gross ist das Modell?                         | 200 Millionen Parameter                                               |
| 10. Kann es ohne Internet verwendet werden?          | Ja                                                                    |
| 11. Könnte es auf einem Smartphone laufen?           | Ja                                                                    |
| 12. Gibt es eine kleinere oder quantisierte Version? | Es gibt verschiedene Donut-Modelle                                    |
| 13. Welche Lizenz besitzt das Modell?                | MIT                                                                   |
| 14. Welche Einschränkungen hat das Modell?           | Das Basismodell muss für eine konkrete Aufgabe weitertrainiert werden |
| 15. Wofür könnte man es in einer App verwenden?      | Rechnungen, Formulare oder Belege analysieren                         |

#### 9. Modell: blip-image-captioning-base Fragen beantworten

| Frage                                                | Antwort                                               |
| ---------------------------------------------------- | ----------------------------------------------------- |
| 1. Wie heisst das Modell?                            | blip-image-captioning-base                            |
| 2. Wo wurde das Modell gefunden?                     | Hugging Face                                          |
| 3. Wer hat das Modell entwickelt?                    | Salesforce                                            |
| 4. Was kann das Modell?                              | Es erstellt Beschreibungen für Bilder                 |
| 5. Warum interessiert euch das Modell?               | Es eignet sich für Bildanalyse und Bildbeschreibungen |
| 6. Welche Eingaben verarbeitet es?                   | Bilder                                                |
| 7. Welche Ergebnisse erstellt es?                    | Beschreibungen (Texte) von Bildern                    |
| 8. Welche Sprachen unterstützt es?                   | Englisch                                              |
| 9. Wie gross ist das Modell?                         | 247 Mio Parametern, ca. 990 MB                        |
| 10. Kann es ohne Internet verwendet werden?          | Ja, nach dem Herunterladen                            |
| 11. Könnte es auf einem Smartphone laufen?           | Ja                                                    |
| 12. Gibt es eine kleinere oder quantisierte Version? | Ja, es gibt quantisierte Versionen                    |
| 13. Welche Lizenz besitzt das Modell?                | bsd-3-clause                                          |
| 14. Welche Einschränkungen hat das Modell?           | Es ist hauptsächlich für Bildbeschreibungen geeignet  |
| 15. Wofür könnte man es in einer App verwenden?      | Bilder automatisch beschreiben oder Fotos analysieren |

#### 10. Modell: speech5_tts Fragen beantworten

| Frage                                                | Antwort                                              |
| ---------------------------------------------------- | ---------------------------------------------------- |
| 1. Wie heisst das Modell?                            | speechT5 (TTS task)                                  |
| 2. Wo wurde das Modell gefunden?                     | Hugging Face                                         |
| 3. Wer hat das Modell entwickelt?                    | Microsoft (Junyi Ao, Rui Wang etc.)                  |
| 4. Was kann das Modell?                              | Es wandelt Text in gesprochene Sprache um            |
| 5. Warum interessiert euch das Modell?               | Es eignet sich für Sprachausgabe in Apps             |
| 6. Welche Eingaben verarbeitet es?                   | Text                                                 |
| 7. Welche Ergebnisse erstellt es?                    | Gesprochene Sprache (Audio)                          |
| 8. Welche Sprachen unterstützt es?                   | Englisch                                             |
| 9. Wie gross ist das Modell?                         | 144 Mio. Parameter, 540 MB                           |
| 10. Kann es ohne Internet verwendet werden?          | Ja, nach dem Herunterladen                           |
| 11. Könnte es auf einem Smartphone laufen?           | Ja                                                   |
| 12. Gibt es eine kleinere oder quantisierte Version? | Es gibt weitere SpeechT5-Modelle für andere Aufgaben |
| 13. Welche Lizenz besitzt das Modell?                | MIT                                                  |
| 14. Welche Einschränkungen hat das Modell?           | Es unterstützt hauptsächlich Englisch                |
| 15. Wofür könnte man es in einer App verwenden?      | Vorlesen von Texten oder Sprachassistenten           |

---

## 2. APIs und Geräteschnittstellen recherchieren

Sucht APIs und Schnittstellen, die für eine mobile AI-App interessant sein
könnten.

Mögliche Beispiele:

- Kamera
- Mikrofon
- Dateisystem
- Bildergalerie
- lokale Datenbank
- Standort
- Kalender
- Kontakte
- Benachrichtigungen
- Spracherkennung
- Text-to-Speech
- Texterkennung
- Bluetooth
- Internetzugriff
- Zwischenablage
- Sensoren
- lokale AI-Schnittstelle

Sucht mindestens **10 verschiedene APIs oder Schnittstellen**.

### Fragen zu jeder API

1. Wie heisst die API oder Schnittstelle?
2. Was kann sie?
3. Für welche App-Funktion könnte sie verwendet werden?
4. Gibt es sie auf iOS?
5. Gibt es sie auf Android?
6. Benötigt sie Internet?
7. Welche Berechtigungen werden benötigt?
8. Welche Daten verarbeitet sie?
9. Verarbeitet sie persönliche oder sensible Daten?
10. Könnte sie mit einem lokalen AI-Modell kombiniert werden?

### Tabelle für die APIs

| Nr. | API oder Schnittstelle                 | Funktion                                           | iOS                    | Android                | Internet nötig | Verarbeitete Daten                              |
| --: | -------------------------------------- | -------------------------------------------------- | ---------------------- | ---------------------- | -------------- | ----------------------------------------------- |
|   1 | CameraX                                | Zugriff auf Kamera, Fotos, Videos und Bild analyse | Nein                   | Ja                     | Nein           | Bilder und Videos                               |
|   2 | Notification API (NotificationManager) | Erstellt und verwaltet Benachrichtigungen          | Ähnliche API vorhanden | Ja                     | Nein           | Nachrichtentexte und Benachrichtigungen         |
|   3 | MediaRecorder API                      | Audioaufnahme über das Mikrofon                    | Ähnliche API vorhanden | Ja                     | Nein           | Audiodateien und Sprachaufnahmen                |
|   4 | Room Database                          | Lokale Speicherung von App Daten                   | Ähnliche API vorhanden | Ja                     | Nein           | Lokale Daten wie Texte und Einstellungen        |
|   5 | Fused Location Provider API            | Ermittelt den Standort des Geräts                  | Ähnliche API vorhanden | Ja                     | Nein           | Standortdaten                                   |
|   6 | Calender Provider API                  | Liest und verwaltet Kalender und Termine           | Ähnliche API vorhanden | Ja                     | Nein           | Kalender- und Termindaten                       |
|   7 | Contacts Framework                     | Liest und verwaltet Kontakte                       | Ja                     | Ähnliche API vorhanden | Nein           | Kontaktdaten wie Name, Bild, Telefonnummer usw. |
|   8 | Photos Framework                       | Zugriff auf Fotos & Videos von der Galerie         | Ja                     | Ähnliche API vorhanden | Nein           | Fotos, Videos und Metadaten                     |
|   9 | FileManager                            | Verwaltet Dateien und Ordner                       | Ja                     | Ähnliche API vorhanden | Nein           | Dateien und Ordner der App                      |
|  10 | Core Motion Framework                  | Zugriff auf Bewegungs- und Lagesensoren            | Ja                     | Ähnliche API vorhanden | Nein           | Bewegungs- und Sensordaten                      |

#### 1. API: CameraX Fragen beantworten

| Frage                                                         | Antwort                                                           |
| ------------------------------------------------------------- | ----------------------------------------------------------------- |
| 1. Wie heisst die API oder Schnittstelle?                     | CameraX                                                           |
| 2. Was kann sie?                                              | Zugriff auf Kamera, Fotos, Videos und Bildanalyse                 |
| 3. Für welche App-Funktion könnte sie verwendet werden?       | Fotos aufnehmen, Dokumente scannen oder Bilder mit KI analysieren |
| 4. Gibt es sie auf iOS?                                       | Nein                                                              |
| 5. Gibt es sie auf Android?                                   | Ja                                                                |
| 6. Benötigt sie Internet?                                     | Nein                                                              |
| 7. Welche Berechtigungen werden benötigt?                     | Kamera- und Galeriezugriff                                        |
| 8. Welche Daten verarbeitet sie?                              | Bilder und Videodaten                                             |
| 9. Verarbeitet sie persönliche oder sensible Daten?           | Ja, Bilder können persönliche Daten enthalten.                    |
| 10. Könnte sie mit einem lokalen AI-Modell kombiniert werden? | Ja z.B. mit Modellen für Bilderkennung oder Dokumentanalyse       |

#### 2. API: Notification API (NotificationManager) Fragen beantworten

| Frage                                                         | Antwort                                                         |
| ------------------------------------------------------------- | --------------------------------------------------------------- |
| 1. Wie heisst die API oder Schnittstelle?                     | Notification API (NotificationManager)                          |
| 2. Was kann sie?                                              | Erstellt und verwaltet Benachrichtigungen (Android Geräte)      |
| 3. Für welche App-Funktion könnte sie verwendet werden?       | Erinnerungen, Warnungen oder KI-Ergebnisse anzeigen             |
| 4. Gibt es sie auf iOS?                                       | Nein, es gibt aber ähnliche API (z.B. UserNotifications)        |
| 5. Gibt es sie auf Android?                                   | Ja                                                              |
| 6. Benötigt sie Internet?                                     | Nein (es ist eine lokale Benachrichtigung)                      |
| 7. Welche Berechtigungen werden benötigt?                     | Die Berechtigung für Benachrichtigungen                         |
| 8. Welche Daten verarbeitet sie?                              | Nachrichtentexte, Titel und Informationen zur Benachrichtigung  |
| 9. Verarbeitet sie persönliche oder sensible Daten?           | Ja, wenn die Benachrichtigung persönliche Informationen enthält |
| 10. Könnte sie mit einem lokalen AI-Modell kombiniert werden? | Ja, z.B. um KI-Ergebnisse oder Erinnerungen anzuzeigen          |

#### 3. API: MediaRecorder API Fragen beantworten

| Frage                                                         | Antwort                                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------------------- |
| 1. Wie heisst die API oder Schnittstelle?                     | MediaRecorder API                                                         |
| 2. Was kann sie?                                              | Nimmt Audio über das Mikrofon des Geräts auf                              |
| 3. Für welche App-Funktion könnte sie verwendet werden?       | Sprachaufnahmen, Sprachsteuerung oder Audioanalyse                        |
| 4. Gibt es sie auf iOS?                                       | Nein, es gibt aber ähnliche API's (z.B. AVAudioRecorder)                  |
| 5. Gibt es sie auf Android?                                   | Ja                                                                        |
| 6. Benötigt sie Internet?                                     | Nein                                                                      |
| 7. Welche Berechtigungen werden benötigt?                     | Mikrofonzugriff                                                           |
| 8. Welche Daten verarbeitet sie?                              | Audiosignale und Sprachaufnahmen                                          |
| 9. Verarbeitet sie persönliche oder sensible Daten?           | Ja, Audioaufnahmen können persönliche Informationen enthalten             |
| 10. Könnte sie mit einem lokalen AI-Modell kombiniert werden? | Ja, z.B. mit Whisper für Speech-To-Text oder VGGish für Geräuscherkennung |

#### 4. API: Room Database API Fragen beantworten

| Frage                                                         | Antwort                                              |
| ------------------------------------------------------------- | ---------------------------------------------------- |
| 1. Wie heisst die API oder Schnittstelle?                     | Room Database                                        |
| 2. Was kann sie?                                              | Speichert und verwaltet Daten lokal auf dem Gerät    |
| 3. Für welche App-Funktion könnte sie verwendet werden?       | Speichern von Notizen und Benutzerdaten              |
| 4. Gibt es sie auf iOS?                                       | Nein, aber es gibt ähnliche APIs (z.B. Core Data)    |
| 5. Gibt es sie auf Android?                                   | Ja                                                   |
| 6. Benötigt sie Internet?                                     | Nein                                                 |
| 7. Welche Berechtigungen werden benötigt?                     | Keine                                                |
| 8. Welche Daten verarbeitet sie?                              | Lokale gespeicherte App Daten                        |
| 9. Verarbeitet sie persönliche oder sensible Daten?           | Ja, wenn persönliche Daten gespeichert werden        |
| 10. Könnte sie mit einem lokalen AI-Modell kombiniert werden? | Ja, z.B. um Dokumente oder Chatverlaufe zu speichern |

#### 5. API: Fused Location Provider API Fragen beantworten

| Frage                                                         | Antwort                                                                              |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| 1. Wie heisst die API oder Schnittstelle?                     | Fused Location Provider API                                                          |
| 2. Was kann sie?                                              | Ermittelt den aktuellen Standort des Geräts                                          |
| 3. Für welche App-Funktion könnte sie verwendet werden?       | Für Navigation, ortsbezogene Informationen oder Standortvorschläge                   |
| 4. Gibt es sie auf iOS?                                       | Nein, aber es gibt ähnliche API's (z.B. Core Location)                               |
| 5. Gibt es sie auf Android?                                   | Ja                                                                                   |
| 6. Benötigt sie Internet?                                     | Nein                                                                                 |
| 7. Welche Berechtigungen werden benötigt?                     | Standortberechtigung                                                                 |
| 8. Welche Daten verarbeitet sie?                              | Standortdaten                                                                        |
| 9. Verarbeitet sie persönliche oder sensible Daten?           | Ja, Standortdaten gelten als persönliche Daten                                       |
| 10. Könnte sie mit einem lokalen AI-Modell kombiniert werden? | Ja, z.B. damit man ortsbezogene Empfehlungen erhält oder für intelligente Navigation |

#### 6. API: Calender Provider API Fragen beantworten

| Frage                                                         | Antwort                                                         |
| ------------------------------------------------------------- | --------------------------------------------------------------- |
| 1. Wie heisst die API oder Schnittstelle?                     | Calender Provider API                                           |
| 2. Was kann sie?                                              | Liest und verwaltet Kalender und Termine                        |
| 3. Für welche App-Funktion könnte sie verwendet werden?       | Termine anzeigen, erstellen oder bearbeiten                     |
| 4. Gibt es sie auf iOS?                                       | Nein, es gibt jedoch eine ähnliche API (EventKit)               |
| 5. Gibt es sie auf Android?                                   | Ja                                                              |
| 6. Benötigt sie Internet?                                     | Nein                                                            |
| 7. Welche Berechtigungen werden benötigt?                     | Kalenderberechtigungen, evtl. Benachrichtigungen                |
| 8. Welche Daten verarbeitet sie?                              | Kalender und Termine                                            |
| 9. Verarbeitet sie persönliche oder sensible Daten?           | Ja, Kalendereinträge können persönliche Informationen enthalten |
| 10. Könnte sie mit einem lokalen AI-Modell kombiniert werden? | Ja, z.B. zum Erkennen oder Erstellen von Terminen aus Texten    |

#### 7. API: Contacts Framework API Fragen beantworten

| Frage                                                         | Antwort                                                              |
| ------------------------------------------------------------- | -------------------------------------------------------------------- |
| 1. Wie heisst die API oder Schnittstelle?                     | Contacts Framework                                                   |
| 2. Was kann sie?                                              | Kontaktdaten lesen und verwalten                                     |
| 3. Für welche App-Funktion könnte sie verwendet werden?       | Kontakte anzeigen, auswählen oder hinzufügen                         |
| 4. Gibt es sie auf iOS?                                       | Ja                                                                   |
| 5. Gibt es sie auf Android?                                   | Nein, aber es gibt eine ähnliche API (Contacts Provider)             |
| 6. Benötigt sie Internet?                                     | Nein                                                                 |
| 7. Welche Berechtigungen werden benötigt?                     | Zugriff auf die Kontakte                                             |
| 8. Welche Daten verarbeitet sie?                              | Kontaktdaten wie Name, Telefonnummer, Bild, und E-Mail Adressen      |
| 9. Verarbeitet sie persönliche oder sensible Daten?           | Ja, Kontaktdaten sind persönliche Daten                              |
| 10. Könnte sie mit einem lokalen AI-Modell kombiniert werden? | Ja, z.B. für eine intelligente Suche oder Organisieren von Kontakten |

#### 8. API: Photos Framework API Fragen beantworten

| Frage                                                         | Antwort                                                             |
| ------------------------------------------------------------- | ------------------------------------------------------------------- |
| 1. Wie heisst die API oder Schnittstelle?                     | Photos Framework API                                                |
| 2. Was kann sie?                                              | Greift auf Fotos & Videos in der Bildergalerie zu und verwaltet sie |
| 3. Für welche App-Funktion könnte sie verwendet werden?       | Bilder auswählen, speichern oder mit KI analysieren                 |
| 4. Gibt es sie auf iOS?                                       | Ja                                                                  |
| 5. Gibt es sie auf Android?                                   | Nein, aber es gibt ähnliche APIs (z.B. MediaStore)                  |
| 6. Benötigt sie Internet?                                     | Nein                                                                |
| 7. Welche Berechtigungen werden benötigt?                     | Zugriff auf die Galerie                                             |
| 8. Welche Daten verarbeitet sie?                              | Fotos, Videos und Metadaten in der Galerie                          |
| 9. Verarbeitet sie persönliche oder sensible Daten?           | Ja, Fotos & Videos können persönliche Informationen sein            |
| 10. Könnte sie mit einem lokalen AI-Modell kombiniert werden? | Ja, z.B. zur Bilderkennung, Bildbeschreibung oder Bildanalysierung  |

#### 9. API: FileManager Fragen beantworten

| Frage                                                         | Antwort                                                         |
| ------------------------------------------------------------- | --------------------------------------------------------------- |
| 1. Wie heisst die API oder Schnittstelle?                     | FileManager                                                     |
| 2. Was kann sie?                                              | Kann Ordner und Dateien auf dem Gerät verwalten                 |
| 3. Für welche App-Funktion könnte sie verwendet werden?       | Dateien speichern, lesen oder löschen                           |
| 4. Gibt es sie auf iOS?                                       | Ja                                                              |
| 5. Gibt es sie auf Android?                                   | Nein, aber es gibt ähnliche APIs (z.B. File API)                |
| 6. Benötigt sie Internet?                                     | Nein                                                            |
| 7. Welche Berechtigungen werden benötigt?                     | Keine besonderen Berechtigungen für den App-Speicher            |
| 8. Welche Daten verarbeitet sie?                              | Ordner und Dateien der App                                      |
| 9. Verarbeitet sie persönliche oder sensible Daten?           | Ja, wenn persönliche Dateien gespeichert werden                 |
| 10. Könnte sie mit einem lokalen AI-Modell kombiniert werden? | Ja, z.B. zum intelligenten Speichern oder Laden von KI-Modellen |

#### 10. API: Core Motion Framework Fragen beantworten

| Frage                                                         | Antwort                                                                                 |
| ------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| 1. Wie heisst die API oder Schnittstelle?                     | Core Motion Framework                                                                   |
| 2. Was kann sie?                                              | Greift auf Bewegungs- und Lagesensoren des Geräts zu                                    |
| 3. Für welche App-Funktion könnte sie verwendet werden?       | Fitnesstracking (z.B. Schritte tracken), Aktivitäten analysieren, Querformat            |
| 4. Gibt es sie auf iOS?                                       | Ja                                                                                      |
| 5. Gibt es sie auf Android?                                   | Nein, aber es gibt ähnliche Sensor-APIs                                                 |
| 6. Benötigt sie Internet?                                     | Nein                                                                                    |
| 7. Welche Berechtigungen werden benötigt?                     | Je nach Sensor können Berechtigungen erforderlich sein                                  |
| 8. Welche Daten verarbeitet sie?                              | Bewegungs- und Sensordaten, z.B. Rotation des Geräts für Querformat oder Beschleunigung |
| 9. Verarbeitet sie persönliche oder sensible Daten?           | Ja, Bewegungsdaten sind persönliche Daten                                               |
| 10. Könnte sie mit einem lokalen AI-Modell kombiniert werden? | Ja, z.B. zur Aktivitätserkennung                                                        |

---

## 3. Technologien für iOS recherchieren

Sucht Technologien, mit denen AI-Funktionen auf iOS umgesetzt werden können.

Mögliche Suchbegriffe:

- Swift AI
- Swift On-Device AI
- Core ML
- Apple Intelligence
- Foundation Models Framework
- MLX Swift
- Vision Framework
- Natural Language Framework
- Speech Framework
- Create ML

### Fragen zur iOS-Recherche

1. Welche AI-Technologien bietet Apple an?
2. Welche Technologien funktionieren direkt auf dem Gerät?
3. Welche Modellformate werden unterstützt?
4. Wie kann ein Modell in Swift verwendet werden?
5. Welche Technologien unterstützen Text?
6. Welche Technologien unterstützen Bilder?
7. Welche Technologien unterstützen Sprache?
8. Welche Geräte werden benötigt?
9. Welche iOS-Version wird benötigt?
10. Welche Einschränkungen gibt es?
11. Können Modelle von Hugging Face verwendet werden?
12. Müssen Modelle zuerst konvertiert werden?

### Tabelle für iOS-Technologien

| Technologie                | Aufgabe                                                                                                 | Lokal ausführbar | Programmiersprache | Einschränkungen                                                                          |
| -------------------------- | ------------------------------------------------------------------------------------------------------- | ---------------- | ------------------ | ---------------------------------------------------------------------------------------- |
| CoreML                     | Ausführen von Machine-Learning-Modellen direkt auf dem Gerät                                            | Ja               | Swift              | Modelle müssen meistens in das CoreML Format konvertiert werden                          |
| Vision Framework           | Bildanalyse, Bilderkennung, Texterkennung und Erkennung von Objekten oder Gesichtern                    | Ja               | Swift              | Unter nur bestimmte Bildverarbeitungsaufgaben (komplexere Modelle benötigen oft Core ML) |
| Apple Intelligence         | KI-Funktionen wie Textverständnis, Zusammenfassungen, Schreibunterstützung und Bildfunktionen ausführen | Teilweise        | Swift              | Benötigt unterstützte Geräte und aktuelle Betriebssysteme                                |
| Natural Language Framework | Textanalyse, Spracherkennung, Klassifikation und Analyse von Texten                                     | Ja               | Swift              | Bietet fertige Sprachfunktionen (komplexere Sprachmodelle benötigen oft Core ML)         |
| Create ML                  | Erstellen und Trainieren eigener Machine-Learning-Modelle für Apple Plattformen                         | Ja               | Swift              | Benötigt Trainingsdaten (Modelle sind meist für bestimmte Aufgaben spezialisiert)        |

### Fragen zur iOS-Recherche beantworten

| Frage                                                      | Antwort                                                                                                                                                                    |
| ---------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. Welche AI-Technologien bietet Apple an?                 | Apple bietet Technologien wie CoreML, Vision Framework, Swift On-Device AI, Apple Intelligence und viele mehr an.                                                          |
| 2. Welche Technologien funktionieren direkt auf dem Gerät? | CoreML, Vision, Natural Language und Speech können direkt auf dem Gerät verwendet werden.                                                                                  |
| 3. Welche Modellformate werden unterstützt?                | Vor allem das Core ML Format (.mlmodel, .mlpackage). Andere müssen oft konvertiert werden.                                                                                 |
| 4. Wie kann ein Modell in Swift verwendet werden?          | Modelle werden in Xcode eingebunden und über Swift-APIs der jeweilgen Technologie verwendet.                                                                               |
| 5. Welche Technologien unterstützen Text?                  | Natural Language Framework, Speech Framework und Core ML.                                                                                                                  |
| 6. Welche Technologien unterstützen Bilder?                | Vision Framework, Core ML und Create ML.                                                                                                                                   |
| 7. Welche Technologien unterstützen Sprache?               | Speech Framework, Natural Language Framework und Core ML.                                                                                                                  |
| 8. Welche Geräte werden benötigt?                          | Unterstütztes iPhone, iPad oder Mac mit aktueller Version des Betriebssystems.                                                                                             |
| 9. Welche iOS-Version wird benötigt?                       | Je nach Technologie unterschiedlich, viele Frameworks kann man ab iOS 11 verwenden.                                                                                        |
| 10. Welche Einschränkungen gibt es?                        | Nicht alle KI-Modelle können direkt verwendet werden. Manche Modelle müssen konvertiert werden. Andere sind grössere Modelle und die benötigen ein leistungsfähiges Gerät. |
| 11. Können Modelle von Hugging Face verwendet werden?      | Ja, viele Modelle können verwendet werden                                                                                                                                  |
| 12. Müssen Modelle zuerst konvertiert werden?              | Meistens ja, wenn sie nicht bereits als Core ML Modell (.mlmodel) vorhanden sind                                                                                           |

---

## 4. Technologien für Android recherchieren

Sucht Technologien, mit denen AI-Funktionen auf Android umgesetzt werden können.

Mögliche Suchbegriffe:

- Android On-Device AI
- Java AI Android
- LiteRT
- TensorFlow Lite
- MediaPipe
- ML Kit
- ONNX Runtime Mobile
- ExecuTorch
- llama.cpp Android
- Android Neural Networks API

### Fragen zur Android-Recherche

1. Welche AI-Technologien gibt es für Android?
2. Welche Technologien können mit Java verwendet werden?
3. Welche Modelle können lokal ausgeführt werden?
4. Welche Modellformate werden unterstützt?
5. Können GPU oder NPU verwendet werden?
6. Welche Android-Versionen werden unterstützt?
7. Welche Geräteanforderungen gibt es?
8. Welche Unterschiede gibt es zwischen Android-Geräten?
9. Können Hugging-Face-Modelle verwendet werden?
10. Müssen Modelle zuerst konvertiert werden?
11. Welche Technologien eignen sich für Text?
12. Welche Technologien eignen sich für Bilder und Sprache?

### Tabelle für Android-Technologien

| Technologie         | Aufgabe                                                                                 | Lokal ausführbar      | Mit Java verwendbar | Einschränkungen                                                   |
| ------------------- | --------------------------------------------------------------------------------------- | --------------------- | ------------------- | ----------------------------------------------------------------- |
| ML Kit              | Texterkennung, Barcode-Scanner, Gesichtserkennung usw.                                  | Ja (viele Funktionen) | Ja                  | Nicht alle Funktionen sind offline verfügbar                      |
| MediaPipe           | Verarbeitung von Bildern, Videos und Audio (z.B. für eine Hand- oder Gesichtserkennung) | Ja                    | Ja (eingeschränkt)  | Funktionsrate verschlechtert sich bei verschiedenen Verhältnissen |
| ExecuTorch          | Führt PyTorch-Modelle auf dem Gerät effizient aus                                       | Ja                    | Ja                  | Unterstützt hauptsächlich PyTorch Modelle                         |
| LiteRT              | Führt KI-Modelle auf dem Android Gerät aus                                              | Ja                    | Ja (eingeschränkt)  | Modelle müssen im LiteRT-/TensorFlow-Lite-Format vorliegen        |
| ONNX Runtime Mobile | Führt ONNX-KI-Modelle lokal auf Android Geräten aus                                     | Ja                    | Ja                  | Unterstützt nur Modelle im ONNX-Format                            |

### Fragen zur iOS-Recherche beantworten

### Fragen zur Android-Recherche beantworten

| Frage                                                       | Antwort                                                                                                          |
| ----------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| 1. Welche AI-Technologien gibt es für Android?              | ML Kit, LiteRT (TensorFlow Lite), MediaPipe, ONNX Runtime Mobile und ExecuTorch.                                 |
| 2. Welche Technologien können mit Java verwendet werden?    | LiteRT (über Java API), ML Kit und ONNX Runtime Mobile. MediaPipe unterstützt Java nur eingeschränkt.            |
| 3. Welche Modelle können lokal ausgeführt werden?           | TensorFlow-Lite-, ONNX- und PyTorch-Modelle sowie die in ML Kit integrierten Modelle.                            |
| 4. Welche Modellformate werden unterstützt?                 | ".tflite", ".onnx" und PyTorch-Modelle                                                                           |
| 5. Können GPU oder NPU verwendet werden?                    | Ja, viele Technologien unterstützen GPU oder NPU zur Beschleunigung der KI-Berechnungen                          |
| 6. Welche Android-Versionen werden unterstützt?             | Je nach Technologie unterschiedlich, viele unterstützen Android 5.0 oder neuer                                   |
| 7. Welche Geräteanforderungen gibt es?                      | Ein Android Gerät mit ausreichend Arbeitsspeicher (bzw. RAM) und Rechenleistung                                  |
| 8. Welche Unterschiede gibt es zwischen Android-Geräten?    | Prozessor, Arbeitsspeicher und Hardwarebeschleunigung (GPU/NPU) unterscheiden sich je nach Gerät                 |
| 9. Können Modelle von Hugging Face verwendet werden?        | Ja, viele Modelle können benutzt werden, aber einige müssen jedoch in ein unterstützes Format konvertiert werden |
| 10. Müssen Modelle zuerst konvertiert werden?               | Oft ja, z.B. in das TensorFlow-Lite- oder ONNX-Format                                                            |
| 11. Welche Technologien eignen sich für Text?               | LiteRT, ML Kit, ONNX Runtime Mobile und ExecuTorch                                                               |
| 12. Welche Technologien eignen sich für Bilder und Sprache? | LiteRT, ML Kit, MediaPipe und ExecuTorch                                                                         |

---

## 5. Interessante AI-Funktionen sammeln

Sammelt mindestens **15 Funktionen**, die eine AI-App besitzen könnte.

Beispiele:

- Texte zusammenfassen
- Texte übersetzen
- Fragen beantworten
- Texte vereinfachen
- Notizen sortieren
- Sprache in Text umwandeln
- Text vorlesen
- Objekte in Bildern erkennen
- Dokumente analysieren
- Lernfragen erstellen
- Texte korrigieren
- Ideen vorschlagen
- Termine aus Texten erkennen
- Bilder beschreiben
- lokale Dateien durchsuchen

### Fragen zu jeder Funktion

1. Was macht die Funktion?
2. Für wen wäre sie nützlich?
3. Welches Problem löst sie?
4. Welches AI-Modell könnte dafür verwendet werden?
5. Welche APIs werden benötigt?
6. Funktioniert sie offline?
7. Könnte sie auf iOS und Android umgesetzt werden?
8. Wie schwierig wäre die Umsetzung?
9. Welche Daten verarbeitet die Funktion?
10. Welche Datenschutzprobleme könnten entstehen?

### Tabelle für mögliche Funktionen

| Nr. | Funktion | Mögliches Modell | Benötigte APIs | Offline möglich | Interesse               |
| --: | -------- | ---------------- | -------------- | --------------- | ----------------------- |
|   1 |          |                  |                |                 | niedrig / mittel / hoch |
|   2 |          |                  |                |                 | niedrig / mittel / hoch |
|   3 |          |                  |                |                 | niedrig / mittel / hoch |
|   4 |          |                  |                |                 | niedrig / mittel / hoch |
|   5 |          |                  |                |                 | niedrig / mittel / hoch |
|   6 |          |                  |                |                 | niedrig / mittel / hoch |
|   7 |          |                  |                |                 | niedrig / mittel / hoch |
|   8 |          |                  |                |                 | niedrig / mittel / hoch |
|   9 |          |                  |                |                 | niedrig / mittel / hoch |
|  10 |          |                  |                |                 | niedrig / mittel / hoch |
|  11 |          |                  |                |                 | niedrig / mittel / hoch |
|  12 |          |                  |                |                 | niedrig / mittel / hoch |
|  13 |          |                  |                |                 | niedrig / mittel / hoch |
|  14 |          |                  |                |                 | niedrig / mittel / hoch |
|  15 |          |                  |                |                 | niedrig / mittel / hoch |

---

## 6. On-Device und Cloud vergleichen

Untersucht den Unterschied zwischen lokaler AI und AI aus der Cloud.

### Fragen

1. Was bedeutet On-Device-AI?
2. Was bedeutet Cloud-AI?
3. Welche Variante benötigt Internet?
4. Welche Variante schützt persönliche Daten besser?
5. Welche Variante ist schneller?
6. Welche Variante benötigt mehr Speicherplatz auf dem Gerät?
7. Welche Variante verursacht laufende Kosten?
8. Welche Variante funktioniert auf älteren Smartphones besser?
9. Welche Variante kann grössere Modelle verwenden?
10. Welche Variante wäre für ein Schulprojekt geeigneter?

### Vergleich

| Thema               | On-Device-AI | Cloud-AI |
| ------------------- | ------------ | -------- |
| Internetverbindung  |              |          |
| Datenschutz         |              |          |
| Geschwindigkeit     |              |          |
| Modellgrösse        |              |          |
| Kosten              |              |          |
| Geräteanforderungen |              |          |
| Offline-Nutzung     |              |          |
| Entwicklungsaufwand |              |          |

---

## 7. Auswahl der interessantesten Ergebnisse

Wählt nach der Recherche eure **fünf interessantesten Ergebnisse** aus.

Das können sein:

- AI-Modelle
- Technologien
- APIs
- Funktionen
- Frameworks
- Bibliotheken

Beantwortet zu jedem Ergebnis:

1. Was habt ihr gefunden?
2. Warum findet ihr es interessant?
3. Was könnte man damit entwickeln?
4. Könnte es auf iOS verwendet werden?
5. Könnte es auf Android verwendet werden?
6. Ist eine Offline-Nutzung möglich?
7. Welche Probleme könnten entstehen?
8. Möchtet ihr dieses Thema später genauer untersuchen?

---

## 8. Persönliches Fazit

Beantwortet am Schluss folgende Fragen:

1. Welche AI-Art interessiert euch am meisten?
2. Welches Modell fandet ihr am interessantesten?
3. Welche API würdet ihr gerne verwenden?
4. Welche iOS-Technologie fandet ihr interessant?
5. Welche Android-Technologie fandet ihr interessant?
6. Welche Funktionen wären für eine spätere App geeignet?
7. Was hat euch bei der Recherche überrascht?
8. Welche Themen möchtet ihr noch genauer untersuchen?
9. Welche drei möglichen Richtungen für ein Projekt erkennt ihr?
10. Welche Richtung würdet ihr aktuell empfehlen?

---

## Anforderungen

Die Dokumentation muss mindestens enthalten:

- [ ] 15 recherchierte AI-Modelle
- [ ] 10 recherchierte APIs oder Schnittstellen
- [ ] 5 iOS-Technologien
- [ ] 5 Android-Technologien
- [ ] 15 mögliche AI-Funktionen
- [ ] einen Vergleich zwischen On-Device-AI und Cloud-AI
- [ ] fünf besonders interessante Ergebnisse
- [ ] ein persönliches Fazit
- [ ] Quellen und Links zu den gefundenen Informationen

---

## Wichtig

- Es muss noch keine feste Projektidee ausgewählt werden.
- Es muss noch keine App programmiert werden.
- Ihr dürft verschiedene AI-Bereiche untersuchen.
- Die Recherche darf nicht nur auf Hugging Face stattfinden.
- Schreibt die Informationen in eigenen Worten.
- Gebt bei allen wichtigen Informationen die Quelle an.
- Achtet auf Modellgrösse, Lizenz, Datenschutz und Geräteanforderungen.
- Überlegt immer, ob eine Technologie auf iOS und Android verwendet werden
  könnte.

```text
```
