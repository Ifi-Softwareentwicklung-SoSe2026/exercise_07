# Exercise07 Agent-Workflow

Diese Datei dient der Middleware als strukturierte Grundlage fuer die automatisch erzeugten Issues von Maria und Juergen. Die fachliche User Story und die Akzeptanzkriterien stehen in `README.md`.

## 1. Initiale Aufgabe von Maria an die Studierenden

- Der LiaScript Link im `README.md` muss auf dem Repository der Studenten geändert werden.
- Ein Badge für den Status der Tests muss in die `README.md` eingebunden werden. (Hilfen in der `README.md`)
- Das Testprojekt soll unter `csharp/tests/TruthTableTests` angelegt werden.
- Eine Solution muss angelegt werden und sowohl mit dem Produktionsprojekt als auch mit dem Testprojekt verknüpft werden.
- Das Testprojekt muss mit dem Produktionsprojekt verknüpft werden.
- Schreibe die CI Aktion in `.github/workflows/ci.yml` so, dass sie die Tests beim push auf jeden branch ausführt.

## 2. Tests Aufgabe von Maria an die Studierenden

Schreibe folgende Tests:

1. Integrationstest Wahrheitstabelle End-to-End
Eingabe eines Terms wie A AND (B OR NOT C) über den normalen Ablauf (Input -> Parse -> Matrix -> Writer). Bonus: Prüfung, dass Anzahl Zeilen, Spaltenreihenfolge und Ergebnisse konsistent sind.
Diesen Test als Commandline Integrationstest implementieren, der den gesamten Ablauf prüft.

2. Unit-Test AND korrekt
Mehrere Belegungen für A AND B prüfen, insbesondere dass nur 1 AND 1 zu 1 wird.

3. Unit-Test OR korrekt
Belegungen für A OR B prüfen, insbesondere dass nur 0 OR 0 zu 0 wird.

4. Unit-Test NOT korrekt
Prüfen, dass NOT A den Wert zuverlässig invertiert (0 -> 1, 1 -> 0).

5. Unit-Test Klammern/Priorität korrekt
Vergleich von A AND (B OR C) mit A AND B OR C, um sicherzustellen, dass Klammern die Auswertungsreihenfolge wirklich verändern.

6. Leere Eingaben im Wahrheitstabellenmodul müssen einen Fehler verursachen
Falls der Nutzer nichts eingibt, muss der Parser mit einer klaren Fehlermeldung fehlschlagen.

7. Parser-Fehlertest fehlende schließende Klammer
Eingabe wie A AND (B OR C muss mit klarer Fehlermeldung fehlschlagen.

8. Parser-Fehlertest unerwartetes Token/ungültiges Zeichen
Eingaben mit verbotenen Zeichen oder Token (z. B. A & B) müssen sauber abgewiesen werden.

9. Nicht-implementierte Operatoren
Für XOR, NAND, NOR jeweils prüfen, dass gezielt NotImplementedException geworfen wird.

10. Variablenextraktion und Matrixgröße
Für einen Term mit n unterschiedlichen Variablen prüfen, dass exakt 2^n Zeilen erzeugt werden und jede Variablenbelegung genau einmal vorkommt.

## 3. Maria möchte die Codequalität im Projekt verbessern.

Die Studenten sollen einen statischen Code-Analyzer in das Projekt einbinden und die Codequalität verbessern. Siehe Section 2 in der `README.md` für weitere Details.

## 4. Jürgen möchte eine Dokumentation immer verfügbar haben

Die Studenten sollen eine Dokumentation mit Doxygen erstellen und diese als Artefakt in der CI Pipeline generieren. Siehe Section 3 in der `README.md` für weitere Details.

## 5. Bonusaufgabe: Maria möchte, ein Issue und ein PR-Template für das Projekt haben

Issue-Template erstellen
====================

Erstelle ein Issue-Template für dein Projekt, das folgende Punkte abdeckt:

- Titel
- Beschreibung
- Akzeptanzkriterien
- Labels
- Priorität

Erstelle ein PR-Template, das folgende Punkte enthält:

- Titel
- Beschreibung
- Verknüpfte Issues
- Änderungen
- Tests
- Checkliste

Teste die Templates, indem du ein neues Issue und einen neuen Pull Request erstellst.
