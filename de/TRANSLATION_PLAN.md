# Produktionsplan für die deutsche Übersetzung

## Ziel

Das vollständige englische Markdown-Korpus wird in zeitgenössisches,
genaues und gut lesbares Deutsch unter dem parallelen Verzeichnis `de/`
übersetzt. Struktur, Metadaten, Links, Absatzanker und inhaltliche
Unterscheidungen der Quellen bleiben erhalten. Die englischen Quelldateien
werden nicht verändert.

## Arbeitsweise

Die Übersetzung wird ab jetzt ausschließlich in der Hauptsitzung fortgeführt.
Es werden keine parallelen Übersetzungsagenten eingesetzt. Bereits von ihnen
fertiggestellte Dateien bleiben erhalten, werden jedoch vor der Freigabe durch
die Hauptsitzung geprüft. Unvollständige Bücher werden anhand des tatsächlichen
Dateibestands übernommen und in der Hauptsitzung abgeschlossen.

## Abschlussstand

| Arbeitsstrang | Umfang | Stand |
|---|---|---|
| Hauptsitzung (`/root`) | Gesamtes Markdown-Korpus | Übersetzung und korpusweite Schlussprüfung abgeschlossen |

Alle Buchverzeichnisse sowie `README.md`, `index.md` und `GLOSSARY.md` liegen
unter `de/` vollständig auf Deutsch vor.

## Koordinationsprotokoll

1. Die Hauptsitzung bearbeitet jeweils ein Buchverzeichnis unter `de/` bis zum
   Abschluss und prüft es anschließend als Ganzes.
2. Korpusweite Suchen und das Lesen anderer Übersetzungen sind für wichtige
   Begriffe verpflichtend.
3. Terminologiefragen werden anhand der englischen Wendung, ihres Kontextes
   und weiterer Fundstellen im Korpus entschieden und bei Bedarf im Leitfaden
   festgehalten.
4. Nach jedem abgeschlossenen Buch aktualisiert die Hauptsitzung Leitfaden,
   Status und die laufende Zuteilung und beginnt unmittelbar das nächste Buch.
5. Nach Abschluss aller Bücher folgt eine korpusweite Schlussprüfung auf
   Terminologie, Metadaten, Struktur und verbliebene englische Prosa.

## Verbindliche Vorbereitung jedes Buches

Vor Beginn eines Buches muss die Hauptsitzung:

1. `TRANSLATION_GUIDE.md` vollständig lesen.
2. Die englischen Dateien und den Dateiumfang des zugewiesenen Buches
   erfassen.
3. Wichtige, mehrdeutige oder als Lehrbegriffe verwendete Ausdrücke im
   gesamten englischen Korpus und in bestehenden deutschen Übersetzungen
   nachschlagen.
4. Bereits festgelegte Begriffe unverändert übernehmen, sofern der konkrete
   Zusammenhang keine nachweisbare Abweichung verlangt.

## Übersetzungsstandard

- Genauigkeit hat Vorrang vor stilistischer Ausschmückung.
- Das Deutsch soll zeitgenössisch, würdevoll und leicht lesbar sein.
- Englische Syntax wird nicht mechanisch nachgebildet, wenn dadurch
  unnatürliches oder schwer verständliches Deutsch entsteht.
- Lehrbegriffe, Sprecherstimme, Anredeformen und Großschreibung folgen
  `TRANSLATION_GUIDE.md`.
- Absatzanker, Markdown-Struktur, URLs, Zahlen, Hervorhebungen und
  Quellenverweise bleiben erhalten.
- Jede deutsche Inhaltsdatei erhält `language: de` und einen korrekten
  relativen `translation_of`-Verweis.

## Übergabe und Prüfung

Ein Buch gilt erst als fertig, wenn die Hauptsitzung mindestens Folgendes
geprüft hat:

- gleicher Dateibestand in Quelle und Übersetzung;
- gleiche geordnete Absatzanker;
- gleiche externen URLs und passende Überschriftenstruktur;
- gültige YAML-Metadaten und auflösbare `translation_of`-Verweise;
- keine unbeabsichtigten englischen Textreste;
- keine Änderungen an den englischen Quelldateien;
- keine Fehler aus `git diff --check`.

Erst danach wird das Buch als abgeschlossen in `TRANSLATION_STATUS.md`
eingetragen.

## Bearbeitungsstrategie

- Die Hauptsitzung schließt begonnene Bücher ab, bevor sie zum nächsten
  unvollständigen Buch wechselt.
- Bereits von früheren Arbeitsagenten erstellte Dateien werden übernommen,
  aber vor der Buchfreigabe von der Hauptsitzung geprüft.
- Die Arbeit läuft bis zur vollständigen Übersetzung und abschließenden
  Korpusprüfung weiter, nicht nur bis zum nächsten Buch oder Teilbestand.
