# Compatibility

## Interfaces / Clients

Legende:

- ✅ Kompatibel
- ➖ Mit Einschränkungen kompatibel
- ❌ Nicht kompatibel

| Client | Compatibility | Note
|--------|---------------|------
DBeaver  | ➖ | Erstellen einer Datenbank möglich allerdings konnte diese nach dem Erstellen "nicht gefunden" werden. Im Container gab es trotzdem einen zugehörigen Ordner bzw. Dolt Repo
HeidiSQL | ➖ | Verbindung zur Datenbank und einsehen der Daten funktioniert, beim Erstellen von Tabellen wird aber ein Fehler wegen der Enkodierung geworden. Egal welche Kollation man wählt, der Befehl schlägt fehl.
dbForge  | ✅ | Verbindung und Erstellen und Lesen von Tabellen funktioniert. Tabellen werden mit einem Zeichensatz erstellt, der bei HeidiSQL nicht funktioniert hat
||
phpMyAdmin | ❌ | Verbindung war nicht möglich, da phpMyAdmin die Datenbankversion nicht auslesen konnte. Auch bei abgewandelter Form nicht.
Adminer  | ➖ | Wie bei phpMyAdmin, aber manipulierte Version von Dolt hat funktioniert.
||
MySQL (Jun Han) | ✅ |
MySQL (Weijan Chen)| ✅ |
SQLTools MySQL/MariaDB (Matheus Teixeira)| ✅ |
JetBrains IDE Plugin| ✅ |

## Contao

