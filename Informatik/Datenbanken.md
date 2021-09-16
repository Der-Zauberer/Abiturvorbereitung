# Datenbanken
André Sommer am 14.09.2021

## Datenbanktypen

- Relationale Datenbank
- Herarchische Datenbank
- Objektorientierte Datenbank
- Objektrelationale Datenbank

## Grundlegende Begriffe

Eine Datenbank ist eine Verknüpfung von Tabellen (Entitätstypen) welche wiederum Daten enthalten. Datenbanbanken werden verwendet um Daten zentral verwalten zu können. Eine Datenbank besteht aus der Speicherung und einem Datenbankmanagementsystenm (DBMS), welches die Speicherung verwaltet.

### Tabelle (Entitätstyp)

Eine Tabelle besteht aus mehreren Einträten (Entitäten) die alle nach dem geichen Muster aufgebaut sind, sie Definieren die Atributetypen und Atributnamen. Die Anzahl dieser Entitäten nennt man Entitätsmenge.

### Entität

Eine Entität hat einen eindeutigen Primärshlüssel und ein oder mehrere Atributwerte, welche im Entitätstyp definiert sind.

### Primärschlüssel

Der Primärschlüssel ist eine Identifikationsnummer. Anhand dieser kann die Entität identifiziert werden.

### Fremdschlüssel

Der Fremdschlüssel ist ein Verweis auf einen anderen Primärschlüssel, mit ihm lassen sich Joins erstellen.

### Join

Ein Join ist eine Verknüpfung zweier Tabellen. Dabei verweißt ein Fremdschlüssel auf einen Primärschlüssel einer anderen Tabelle.

## Beziehungen

Es gibt verschiedene Arten von Beziehungen zwischen Tabellen. Die 1:1 Beziehung ist eine direkte Verknüpfung zweier Entitäten. Somit währe es auch möglich die Entitäten zusammen zu fassen. Bei der 1:n Beziehung verweisen mehrere Entitäten auf eine Entität. Zum Beispiel könnten mehrere Söhne zu einem Vater gehören. Bei einer n:n Beziehung können verschiedene Tabellen auf verschiedene Tabellen verweisen. Da sich dies in Relationalen Datenbanken nicht umsetzen lässt ist über eine Zwischentabelle die n:n Beziehung in zwei 1:n beziehungen aufzulösen. Zum Beispiel können verschiedene Fahrgäste verschieden Züge benutzen. Somit wird in einer Übergangstabele jeweils ein Fahrgast einem Zug zugeordnet. Beziehungen werden ach Joins genannt.

## Normalisierung

Hierbei geht es darum Rendundanzen (Datendopplungen) zu vermeiden und einheitliche Atributwerte festzulegen.

1. Normalenform: Atribute müssen eindeutige Werte haben und dürfen jeweils nur aus einem Wert bestehen. 
2. Normalenform: Es werden Zwischentabellen angelegt um n:n Beziehungen in 1:n Beziehungen aufzulösen.
3. Normalenform: Es werden zusammengehörige Daten in eindeutigen Tabellen zusammengefasst. Nicht zusammengehörige Atribute werden in verschiedene Tabellen getrennt.

## ER-Model und Relationsschreibweise

Wird hier nicht aufgeführt!

## SQL

Die Reihenfolge bei SQL-Abfragen ist immer `SELECT` `FROM` `WHERE` `GROUP BY` `HAVING` `ORDER BY`. Hier ein Beispiel für eine SQL Abfrage:

```sql
SELECT P.Name, P.Datum, L.Name, avg(N.Note) AS Notendurchschnitt
FROM Person P, Noten N, Lehrer L
WHERE P.Lehrer = L.ID
GROUP BY P.Name, P.Datum, L.Name
HAVING avg(N.Note) > 3
ORDER BY avg(N.Note) ASC
```

### SELECT

Select wählt die Spalten aus, bei funktionen ist es oft Notwendig einen Namen zu hinterlegen. Dies geschied mit dem Schlüsselwort `AS`, dahinter kommt der Name. Sollte dieser Lehgrzeichen und Sonderzeichen enthalten ist der Name mit eckigen Klammern einzuschließen: `avg(N.Note) AS [Der Notendurchschnitt]`. Es gibt verschiedene Aggregatfunktionen:

|Schlüsselbefehle||
|---|---|
|`avg()`|Durchschnitt|
|`sum()`|Summe|
|`count()`|Menge|
|`min()`|Minimaler Wert|
|`max()`|Maximaler Wert|

### FROM

From gibt an welche Tabellen benötigt werden. Diese können für Spaltenaufrufe mit einem Buchstaben abgekürzt werden.

### WHERE

Where kann eine Verbindung (Join) zwischen Tabellen herstellen und weitere Bedingungen festlegen, die nicht von Aggregatfunktionen abhängig sind. Eine Verbindung erfolgt zuwischen dem Primärschlüssel der einen Tabelle und dem Fremdschlüssel der anderen Tabelle: `WHERE A.Primärschlüssel = B.Fremdschlüssel`.

|Schlüsselbefehle||
|---|---|
|`=`|Vergleichsoperator|
|`LIKE`|Vergleich für Strings|
|`BETWEEN`|Daten innerhalb eines Wertebereiches|
|`AND`|Und|
|`OR`|Oder|

### WHERE und Strings

### WHERE und Daten

### GROUP BY

### HAVING

### ORDER BY

Die Entitäten der Abfrage werden nach dem Atribut aufsteigend sortiert. Dies kann mit den Befehlen `DESC` absteigend und `ASC`aufsteigend konkretisiert werden.
