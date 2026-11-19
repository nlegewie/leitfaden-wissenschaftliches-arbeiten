# Quantitative Arbeiten

## Beginne mit der Zielgröße, nicht mit dem Modell

> [!IMPORTANT]
> Bevor du ein Modell rechnest, formuliere die **Zielgröße deiner Analyse in Worten, ohne jede Modellnotation**: über welche Einheiten, in welcher Population, welcher Vergleich, zu welchem Zeitpunkt? Zum Beispiel:
>
> „Der Unterschied im Vertrauen in Institutionen zwischen ostdeutschen Befragten mit und ohne Vereinsmitgliedschaft, im Jahr 2023."
>
> Erst danach überlegst du, welches statistische Verfahren diese Größe unter welchen Annahmen schätzen kann. Wer diesen Satz nicht formulieren kann, hat meist noch keine Forschungsfrage, sondern eine Variablenliste.

<details>
<summary><b>Vertiefung:</b> Warum der Umweg über die Zielgröße lohnt</summary>

<br>

Der Umweg trennt die theoretische Frage von der statistischen Technik und macht sichtbar, welche Annahmen dazwischen liegen — zwischen der Größe, die dich eigentlich interessiert, und dem Koeffizienten, den dein Modell ausgibt. Oft zeigt sich dabei, dass ein Regressionskoeffizient gar nicht die Größe schätzt, nach der die Frage fragt. Der Gedanke stammt aus Lundberg, Johnson und Stewart (2021), *What Is Your Estimand?* (siehe [Weiterführende Literatur](../04-nachschlagen/04-weiterfuehrende-literatur.md)).

</details>

## Dokumentation

Lege offen und reproduzierbar vor:

- ein **gründlich kommentiertes Analyseskript** (separate Datei);
- eine **Beschreibung der verwendeten Variablen** im Text **und** kompakt als **Codebook** (Anhang oder separate Datei);
- klare Beschreibungen der **Analyseverfahren** sowie des **Datensatzes** bzw. der **Erhebung**.

## Passt das Verfahren zu deinen Daten?

> [!WARNING]
> Prüfe, ob ein statistisches Verfahren tatsächlich das misst, was du wissen willst. Beispiel: **Cramérs V** behandelt Variablen als **nominal** und ignoriert die Abstände zwischen ordinalen Kategorien — der Unterschied zwischen 1 und 5 zählt dann genauso wie der zwischen 4 und 5. Auf ordinalen Skalen kann das die Befunde verzerren. Wähle Verfahren passend zum **Skalenniveau** und zur Fragestellung.

Reflektiere bei statistischen Befunden nicht nur Richtung und Signifikanz, sondern auch **Effektstärke und Erklärungskraft** (siehe [Aussagen im Rahmen der Evidenz](../01-anforderungen/05-analyse-und-evidenz.md#aussagen-im-rahmen-der-evidenz)).

## Datenquellen

Für eine quantitative Arbeit musst du in aller Regel **keine eigenen Daten erheben**. Es gibt eine riesige Zahl hochwertiger, frei oder nach Registrierung zugänglicher Datensätze. Für fast jede sozialwissenschaftliche Frage ist irgendwo schon etwas erhoben worden. Eine kleine Auswahl:

**Bevölkerungsumfragen**

| Datensatz | Was er bietet |
|---|---|
| **ALLBUS** (Allgemeine Bevölkerungsumfrage der Sozialwissenschaften) | Einstellungen und Verhalten der Bevölkerung in Deutschland, seit 1980 regelmäßig |
| **GLES** (German Longitudinal Election Study) | Wahlverhalten und politische Einstellungen in Deutschland |
| **SOEP** (Sozio-oekonomisches Panel) | Langzeitbefragung derselben Haushalte in Deutschland, seit 1984 |
| **ESS** (European Social Survey) | Einstellungen und Werte im europäischen Vergleich |
| **ISSP** (International Social Survey Programme) | Jährlich wechselnde Themen im internationalen Vergleich |
| **EVS / WVS** (European / World Values Survey) | Werte und Einstellungen weltweit, über Jahrzehnte |
| **Eurobarometer** | Regelmäßige Umfragen in den EU-Staaten |

**Länder- und Aggregatdaten**

| Quelle | Was sie bietet |
|---|---|
| **[Our World in Data](https://ourworldindata.org)** | Aufbereitete Länderdaten zu fast allen gesellschaftlichen Themen, mit Grafiken und Downloads |
| **V-Dem** (Varieties of Democracy) | Detaillierte Indikatoren zur Demokratiequalität weltweit |
| **Manifesto Project** | Inhaltsanalysen von Wahlprogrammen |
| **ParlGov** | Parteien, Wahlen und Regierungen in Demokratien |
| **Weltbank, OECD, Eurostat, Destatis** | Amtliche Statistik zu Wirtschaft, Bevölkerung, Sozialem |

**Wie du weitere Datensätze findest**

- **[GESIS Search](https://search.gesis.org)** und das GESIS-Datenarchiv — die zentrale Anlaufstelle für sozialwissenschaftliche Daten in Deutschland.
- **[Google Dataset Search](https://datasetsearch.research.google.com)** und **[re3data](https://www.re3data.org)** (Verzeichnis von Datenrepositorien).
- Internationale Archive wie **ICPSR** oder **Harvard Dataverse**.
- Für ausgefallenere Datensätze kannst du mal bei [Data is Plural](data-is-plural.com) vorbeischauen.
- **Replikationsdaten**: Viele Fachartikel veröffentlichen ihre Daten. Wenn du einen Artikel liest, der mit passenden Daten arbeitet, schau nach, ob sie zugänglich sind.

**Worauf du achten solltest**

- **Zugang braucht manchmal Zeit.** Für manche Datensätze (z. B. das SOEP) musst du einen Nutzungsvertrag abschließen; das kann Wochen dauern. Kläre den Zugang deshalb früh — spätestens beim Exposé bzw. in der Planungsphase.
- **Lies die Dokumentation.** Fragebogen und Codebook sagen dir, wie eine Variable genau erhoben wurde, welche Werte fehlende Angaben bedeuten und ob du **Gewichte** verwenden musst.
- **Prüfe aufbereitete Daten an der Quelle.** Our World in Data und ähnliche Angebote fassen Daten aus vielen Quellen zusammen. Nenne in deiner Arbeit die ursprüngliche Quelle und prüfe, wie die Werte zustande kommen.
- **Länderdaten erlauben Aussagen über Länder, nicht über Personen.** Wenn Länder mit höherem Durchschnittseinkommen mehr Vertrauen haben, heißt das nicht, dass reichere Menschen mehr vertrauen (ökologischer Fehlschluss).
- **Zitiere Datensätze** wie Literatur, mit Version und DOI, falls vorhanden.

## Signifikanztests mit einer Gelegenheitsstichprobe

Wenn du doch eigene Daten erhebst, etwa mit einer Online-Umfrage im erweiterten Freundeskreis, über Email-Verteiler oder über Social Media, hast du meist eine **Gelegenheitsstichprobe**. Auch damit kannst du t-Tests oder χ²-Tests rechnen. Du musst die Ergebnisse aber anders deuten als bei einer Zufallsstichprobe. (Zu Einwilligung und Datenschutz bei eigenen Erhebungen siehe [Forschungsethik und Datenschutz](03-forschungsethik-und-datenschutz.md).)

> [!IMPORTANT]
> Ein Signifikanztest beantwortet genau eine Frage: Könnte der gefundene Unterschied auch einfach durch Zufall entstanden sein, also durch die zufällige Auswahl der Befragten oder die zufällige Zuteilung zu Gruppen? Diese Frage ergibt nur Sinn, wenn es einen solchen Zufallsmechanismus tatsächlich gibt. Bei einer Gelegenheitsstichprobe gibt es ihn nicht. Der p-Wert erlaubt deshalb keinen direkten Schluss auf „die Studierenden in Deutschland“.

**Worauf du achten solltest**

- **Verzerrung verschwindet nicht durch mehr Fälle.** Wenn deine Stichprobe systematisch anders ist als die Grundgesamtheit, wird der Fehler mit größerem n nicht kleiner. Er wirkt dann nur genauer.
- **Gruppenunterschiede können durch die Rekrutierung entstehen.** Ein Beispiel: Die Männer stammen vor allem aus einem Sportverein, die Frauen aus einer Psychologie-Vorlesung. Dann ist ein „Geschlechterunterschied“ vielleicht nur ein Unterschied zwischen diesen beiden Orten.
- **Die Befragten sind oft nicht unabhängig.** Wer über Freunde von Freunden rekrutiert, erhält ähnliche Personen. Die Standardfehler fallen dann zu klein aus, und Ergebnisse wirken signifikanter, als sie sind.

**Was du konkret tun solltest**

- **Rekrutierung offenlegen.** Beschreibe genau, wie du die Teilnehmenden gewonnen hast. Formuliere deine Schlussfolgerungen entsprechend vorsichtig, z. B. „unter den befragten Studierenden …“.
- **Stichprobe vergleichen.** Vergleiche Merkmale wie Geschlecht, Studienfach und Semester mit amtlichen Daten, etwa der Hochschulstatistik des Statistischen Bundesamts oder deiner Universität. Wo gibt es Abweichungen, und was bedeuten sie für deine Ergebnisse?
- **Zuerst beschreiben, dann testen.** Berichte Mittelwerte, Prozentanteile und Effektstärken, etwa Cohens d oder Cramérs V. Diese Werte beschreiben deine Stichprobe, egal wie sie zustande kam. Ob sie auch über deine Stichprobe hinaus gelten, sagen sie allerdings nicht.
- **Tests vorsichtig deuten.** Schreib nicht „signifikant, also gibt es den Unterschied in der Bevölkerung“. Schreib stattdessen etwa: „Wenn man annimmt, dass sich die Stichprobe in dieser Hinsicht wie eine Zufallsstichprobe verhält, ist der Unterschied größer als durch Zufall zu erwarten.“
- **Nicht wahllos viele Tests rechnen.** Wer viele Vergleiche testet, findet allein durch Zufall einige „signifikante“ Ergebnisse: Bei 20 Tests auf dem 5-%-Niveau ist im Schnitt einer signifikant, auch wenn es nirgends einen echten Unterschied gibt. Lege vorher fest, welche Vergleiche dich interessieren, und berichte alle Tests, die du gerechnet hast.
- **Die Studie als explorativ verstehen.** Deine Ergebnisse können Hypothesen erzeugen, aber nicht bestätigen. Das ist völlig legitim, solange du es klar so benennst.

<details>
<summary><b>Vertiefung:</b> Technisch sauber rechnen</summary>

<br>

- **t-Test:** Verwende standardmäßig den **Welch-Test**. Er setzt keine gleichen Varianzen in den Gruppen voraus. In R ist er bei `t.test()` bereits voreingestellt.
- **χ²-Test:** Prüfe, ob die **erwarteten Zellhäufigkeiten** groß genug sind. Die übliche Faustregel: alle mindestens 5 (etwas großzügiger: höchstens 20 % der Zellen unter 5, keine unter 1). Bei kleinen Stichproben ist das oft nicht der Fall. In R zeigt `chisq.test(...)$expected` die erwarteten Häufigkeiten; R warnt außerdem mit „Chi-squared approximation may be incorrect“. Fasse dann inhaltlich sinnvolle Kategorien zusammen oder verwende den **exakten Test nach Fisher** (`fisher.test()`).
- **Cramérs V** behandelt beide Variablen als nominal. Bei ordinalen Variablen beachte den Hinweis oben unter [Passt das Verfahren zu deinen Daten?](#passt-das-verfahren-zu-deinen-daten).

</details>

---
<!-- nav -->

← [Forschungsethik und Datenschutz](03-forschungsethik-und-datenschutz.md) · [Kapitelübersicht](README.md) · [Startseite](../README.md) · [Qualitative Arbeiten](05-qualitative-arbeiten.md) →
