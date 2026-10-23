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

Für eine quantitative Arbeit musst du in aller Regel **keine eigenen Daten erheben**. Es gibt eine riesige Zahl hochwertiger, frei oder nach Registrierung zugänglicher Datensätze — für fast jede sozialwissenschaftliche Frage ist irgendwo schon etwas erhoben worden. Eine kleine Auswahl:

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
- **Replikationsdaten**: Viele Fachartikel veröffentlichen ihre Daten. Wenn du einen Artikel liest, der mit passenden Daten arbeitet, schau nach, ob sie zugänglich sind.

**Worauf du achten solltest**

- **Zugang braucht Zeit.** Für manche Datensätze (z. B. das SOEP) musst du einen Nutzungsvertrag abschließen; das kann Wochen dauern. Kläre den Zugang deshalb früh — spätestens beim Exposé bzw. in der Planungsphase.
- **Lies die Dokumentation.** Fragebogen und Codebook sagen dir, wie eine Variable genau erhoben wurde, welche Werte fehlende Angaben bedeuten und ob du **Gewichte** verwenden musst.
- **Prüfe aufbereitete Daten an der Quelle.** Our World in Data und ähnliche Angebote fassen Daten aus vielen Quellen zusammen. Nenne in deiner Arbeit die ursprüngliche Quelle und prüfe, wie die Werte zustande kommen.
- **Länderdaten erlauben Aussagen über Länder, nicht über Personen.** Wenn Länder mit höherem Durchschnittseinkommen mehr Vertrauen haben, heißt das nicht, dass reichere Menschen mehr vertrauen (ökologischer Fehlschluss).
- **Zitiere Datensätze** wie Literatur, mit Version und DOI, falls vorhanden.

---
<!-- nav -->

← [Forschungsethik und Datenschutz](03-forschungsethik-und-datenschutz.md) · [Kapitelübersicht](README.md) · [Startseite](../README.md) · [Qualitative Arbeiten](05-qualitative-arbeiten.md) →
