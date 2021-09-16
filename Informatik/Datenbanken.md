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

SELECT P.Name, P.Datum, L.Name, avg(N.Note) AS Notendurchschnitt
FROM Person P, Noten N, Lehrer L
WHERE P.Lehrer = L.ID
GROUP BY P.Name, P.Datum, L.Name
HAVING avg(N.Note) > 3
ORDER BY avg(N.Note)
