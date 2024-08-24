# "Super God Mode" für Windows

Dieses PowerShell\-Skript <b>erstellt Verknüpfungen zu allen speziellen Shell\-Ordnern, benannten Ordnern, Aufgabenverknüpfungen, Systemeinstellungen, Deep Links und URL\-Protokollen in Windows<b> und ermöglicht so den einfachen Zugriff auf eine Vielzahl von Systemeinstellungen und Funktionen.

Er wurde von dem berühmt\-berüchtigten "God Mode"\-Ordner inspiriert und schafft noch viel mehr Abkürzungen als dieser.

## Screenshots

<p align="center">
<img width="700" alt="WindowNew" src="https://github.com/user-attachments/assets/35f8f858-dcf5-4670-866f-2b86de4569d9"/>
</p><p align="center">
<img width="290" alt="Ergebnisse" src="https://github.com/user-attachments/assets/4d01fbad-b597-4433-bd67-2638ded8a6ed"/> <img width="392" alt="Ausgabeordner" src="https://github.com/user-attachments/assets/898efc48-ddc6-4875-b906-b89963d5778e"/>
</p>



## Eigenschaften

- Erzeugt Verknüpfungen für verschiedene Windows\-Komponenten:
  - CLSID\-basierte Shell\-Ordner
  - Benannte Spezialordner
  - Aufgabenverknüpfungen (Unterseiten in Shell\-Ordnern und Menüs der Systemsteuerung)
  - Systemeinstellungen (ms\-settings: Links)
  - Deep Links (direkte Links zu verschiedenen Einstellungsmenüs in Windows)
  - URL\-Protokolle
  - Versteckte App\-Links (Intern verwendete und undokumentierte URL\-Links, die von Apps verwendet werden)
- Erzeugt CSV\-Dateien mit detaillierten Informationen über die Verknüpfungen
- Speichert XML\-Inhalte, die von shell32\.dll und anderen Quellen abgerufen werden, als Referenz
- Grafische Benutzeroberfläche (GUI) für einfache Konfiguration

## Wie man läuft:

### Option 1 (Einfacher): .Bat Launcher verwenden
1. Lade die neueste Version des Skripts herunter. (Direkter Link [hier](https://github.com/ThioJoe/Windows-Super-God-Mode/releases/download/v1.0.0/Super_God_Mode.ps1))
2. Lade die Launcher\-Batch\-Datei an denselben Ort herunter. (Direkter Link [hier](https://github.com/ThioJoe/Windows-Super-God-Mode/releases/download/v1.0.0/SuperGodMode-EasyLauncher.bat))
3. Führe die Batch\-Datei aus.

### Option 2: Manuell ausführen

1. Lade die neueste Version des Skripts herunter. (Direkter Link [hier](https://github.com/ThioJoe/Windows-Super-God-Mode/releases/download/v1.0.0/Super_God_Mode.ps1))
2. Öffne die PowerShell in dem Verzeichnis mit dem Skript. (Tipp: Gib im Datei\-Explorer einfach "PowerShell.exe" in die Adressleiste ein, um sie in diesem Pfad zu öffnen).
3. Führe den folgenden Befehl aus, um die Skriptausführung für die aktuelle Sitzung zu erlauben:
   ```
   Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope Process
   ```
4. Führe das Skript aus:
   ```
   .\Super_God_Mode.ps1
   ```
   - Wenn du keine Parameter angibst, wird eine grafische Benutzeroberfläche zur einfachen Konfiguration angezeigt.
   - Du kannst das Skript auch mit optionalen Parametern ausführen (siehe unten).

## CLI\-Parameter

Hinweis: Außer für `-Debuggen` und `-Ausführlich` musst du `-NoGUI` verwenden, damit die Argumente wirksam werden.

#### Alternative Optionen Argumente

- `-DontGroupTasks`: Gruppierung von Aufgabenkurzbefehlen nach Anwendungsname verhindern
- `-UseAlternativeCategoryNames`: Verwende alternative Kategorienamen für Aufgabenlinks
- `-AllURLProtocols`: URL\-Protokolle von Drittanbietern aus installierter Software einbeziehen
- `-CollectExtraURLProtocolInfo`: Sammle zusätzliche Informationen über URL\-Protokolle

#### Kontrolle Ausgang

- `-Ausgabe`: Einen benutzerdefinierten Ausgabeordnerpfad angeben
- `-KeepPreviousOutputFolders`: Vorhandene Ausgabeordner vor der Ausführung nicht automatisch löschen

#### Argumente zur Begrenzung der Erstellung von Verknüpfungen

- `-NoStatistics`: Keine Statistikordner und \-dateien erstellen
- `-NoReadMe`: Keine Tipps Textdatei erstellen
- `-SkipCLSID`: Überspringe die Erstellung von Verknüpfungen für CLSID\-basierte Shell\-Ordner
- `-SkipNamedFolders`: Überspringe das Erstellen von Verknüpfungen für benannte Sonderordner
- `-SkipTaskLinks`: Abkürzungen für Aufgabenverknüpfungen nicht erstellen
- `-SkipMSSettings`: Überspringe das Erstellen von Verknüpfungen für ms\-settings: links
- `-SkipDeepLinks`: Überspringe die Erstellung von Shortcuts für Deep Links
- `-SkipURLProtocols`: Überspringe die Erstellung von Abkürzungen für URL\-Protokolle
- `-SkipHiddenAppLinks`: Verknüpfungen zu versteckten App\-Links nicht erstellen

#### Fehlersuche

- `-Ausführlich`: Aktiviere die ausführliche Ausgabe. Kann mit oder ohne `-NoGUI` verwendet werden.
- `-Debuggen`: Aktiviere die Debug\-Ausgabe (aktiviert auch die ausführliche Ausgabe). Kann mit oder ohne `-NoGUI` verwendet werden.

#### Fortgeschrittene Argumente

- `-NoGUI`: Überspringe den GUI\-Dialog und führe mit Standard\- oder vorgegebenen Parametern aus
- `-CustomDLLPath`: Gib einen benutzerdefinierten DLL\-Dateipfad für shell32\.dll an
- `-CustomLanguageFolderPath`: Gib einen Pfad zu einem Ordner an, der sprachspezifische MUI\-Dateien enthält
- `-CustomSystemSettingsDLLPath`: Gib einen benutzerdefinierten Pfad zur Datei SystemSettings.dll an
- `-CustomAllSystemSettingsXMLPath`: Gib einen benutzerdefinierten Pfad zu der XML\-Datei "AllSystemSettings\_" an

### Beispiel

```powershell
.\Super_God_Mode.ps1 -Output "C:\SuperGodMode" -AllURLProtocols -Verbose
```

## Ausgabe

Das Skript erstellt einen Ordner (Standardname: "Super God Mode") enthalten:

- Verknüpfungen zu CLSID\-basierten Shell\-Ordnern
- Verknüpfungen zu benannten speziellen Ordnern
- Shortcuts zu Aufgabenlinks
- Verknüpfungen zu Systemeinstellungen (ms\-settings: Links)
- Abkürzungen zu Deep Links
- Abkürzungen zu URL\-Protokollen
- Shortcuts zu versteckten App\-Links
- Ein Statistik\-Ordner (mit CSV\- und XML\-Dateien)
- Eine Textdatei mit einigen Tipps und anderen Infos

## Anmerkungen

- Einige Tastenkombinationen funktionieren möglicherweise nicht auf allen Windows\-Versionen, da es Unterschiede bei den verfügbaren Funktionen gibt.
- Das Skript ändert keine Systemeinstellungen, sondern erstellt nur Verknüpfungen zu bestehenden Windows\-Funktionen.
- Alle Parameter und GUI\-Einstellungen sind optional. Das Skript wird mit den Standardeinstellungen ausgeführt, wenn der Benutzer nichts ändert.

___

# Extra Tools

Der Ordner "Extra Tools" enthält zusätzliche Skripte, die die Hauptfunktionen des Windows Super God Mode ergänzen:

### Get\_DLL\_String\_Reference.ps1

Mit diesem Skript kannst du ganz einfach die lokalisierte Zeichenkette einer bestimmten String\-Referenz abrufen.

Merkmale:
- Fragt interaktiv nach String\-Referenzen
- Löst die lokalisierten String\-Werte auf und zeigt sie an
- Unterstützt das `@dllpath,-resourceID` Format

Verwendung:
1. Führe das Skript in der PowerShell aus
2. Gib die String\-Referenz ein, wenn du dazu aufgefordert wirst (z. B. `@%SystemRoot%\system32\shell32.dll,-9227`)
3. Das Skript wird den aufgelösten String\-Wert anzeigen

### Windows\_XML\_String\_Resolver.ps1

Dieses Skript verarbeitet ganze XML\-Dateien, die Windows String\-Referenzen enthalten, und löst sie in ihre tatsächlichen String\-Werte auf. Sie ist hauptsächlich für die XML\-Datei aus shell32\.dll.mun gedacht, die alle Windows\-Task\-Links enthält.

Merkmale:
- Verarbeitet ganze XML\-Dateien und ersetzt String\-Referenzen durch ihre aufgelösten Werte
- Unterstützt benutzerdefinierte DLL\-Pfade für die Auflösung von Strings
- Erzeugt eine neue XML\-Datei mit aufgelösten Strings

Verwendung:
```powershell
.\Windows_XML_String_Resolver.ps1 -XmlFilePath "path\to\your\file.xml" [-CustomResourcePaths "shell32=C:\custom\path\shell32.dll", "user32=C:\another\path\user32.mui"] [-Debug]
```

### Get\-MS\-Settings\-Strings.ps1

Dieses Skript findet die Zeichenketten "ms\-settings:" in einer DLL\-Datei und gibt sie in eine Textdatei aus. Es ist eine eigenständige Version der Funktion, die in das Hauptskript eingebaut ist. Vor allem für: "C:\\Windows\\ImmersiveControlPanel\\SystemSettings.dll".

Verwendung:
```
`.\Get-MS-Settings-Strings.ps1 -DllPath "C:\Windows\ImmersiveControlPanel\SystemSettings.dll" -OutputFilePath "SystemSettings-MS-Settings.txt"
```
- Wenn keine Argumente angegeben werden, fragt das Skript den Benutzer nach dem DLL\-Pfad und gibt ihn im selben Verzeichnis wie das Skript aus.

### Find\_URLs\_From\_AppxPackage\_Files.ps1

Dieses Skript holt sich die URI\-Protokolle für jedes installierte AppxPackage über die Datei AppxManifest.xml und sucht dann mit roher Gewalt nach diesen URIs in allen Dateien im Installationsverzeichnis der App. Es ist eine eigenständige Version der Funktion, die in das Hauptskript eingebaut ist.

Verwendung:
- Keine Argumente nötig:  `.\Find_URLs_From_AppxPackage_Files.ps1`
