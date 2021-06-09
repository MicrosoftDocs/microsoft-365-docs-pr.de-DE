---
title: Untersuchen von Entitäten auf Geräten mithilfe von Liveantwort in Microsoft Defender für Endpunkt
description: Greifen Sie mithilfe einer sicheren Remoteshell-Verbindung auf ein Gerät zu, um Untersuchungsvorgänge auszuführen und sofortige Reaktionsaktionen auf einem Gerät in Echtzeit auszuführen.
keywords: remote, shell, connection, live, response, real-time, command, script, remediate, hunt, export, log, drop, download, file,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d5e48f1e4f6bc2cfaa836d90e24f2ce8ba3f2114
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845330"
---
# <a name="investigate-entities-on-devices-using-live-response"></a>Untersuchen von Entitäten auf Geräten mithilfe von Liveantwort

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Live Response bietet Sicherheitsteams sofortigen Zugriff auf ein Gerät (auch als Computer bezeichnet) über eine Remoteshell-Verbindung. Dadurch haben Sie die Möglichkeit, tiefgehende Untersuchungsarbeit zu leisten und sofortige Maßnahmen zu ergreifen, um erkannte Bedrohungen umgehend einzudämmen – in Echtzeit. 

Live Response wurde entwickelt, um Untersuchungen zu verbessern, indem es Ihrem Sicherheitsteam ermöglicht, forensische Daten zu sammeln, Skripts auszuführen, verdächtige Entitäten zur Analyse zu senden, Bedrohungen zu beheben und proaktiv nach neuen Bedrohungen zu suchen.<br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

Mit Live-Antworten können Analysten alle folgenden Aufgaben ausführen:
- Führen Sie einfache und erweiterte Befehle aus, um untersuchungsrelevante Aufgaben auf einem Gerät auszuführen.
- Laden Sie Dateien wie Schadsoftwarebeispiele und Ergebnisse von PowerShell-Skripts herunter.
- Dateien im Hintergrund herunterladen (neu!).
- Hochladen sie ein PowerShell-Skript oder eine ausführbare Datei in die Bibliothek ein, und führen Sie es auf einem Gerät auf Mandantenebene aus.
- Durchführen oder Rückgängigmachen von Korrekturmaßnahmen.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie eine Sitzung auf einem Gerät initiieren können, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

- **Stellen Sie sicher, dass Sie eine unterstützte Version von Windows ausführen.** <br/>
Auf Geräten muss eine der folgenden Versionen von Windows

  - **Windows 10**
    - [Version 1909](/windows/whats-new/whats-new-windows-10-version-1909) oder höher  
    - [Version 1903](/windows/whats-new/whats-new-windows-10-version-1903) mit [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)
    - [Version 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809) [mit KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    - [Version 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803) mit [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)
    - [Version 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) mit [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)
  
  - **Windows Server 2019 – Gilt nur für öffentliche Vorschau**
    - Version 1903 oder (mit [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) später 
    - Version 1809 (mit [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))

- **Aktivieren Sie die Liveantwort von der Seite "Erweiterte Einstellungen".**<br>
Sie müssen die Liveantwortfunktion auf der Seite ["Erweiterte Features"](advanced-features.md) aktivieren.

    >[!NOTE]
    >Nur Benutzer mit Sicherheits- oder globalen Administratorrollen können diese Einstellungen bearbeiten.

- Aktivieren Sie die **Liveantwort für Server über die Seite "Erweiterte Einstellungen"** (empfohlen).<br>

    >[!NOTE]
    >Nur Benutzer mit Sicherheits- oder globalen Administratorrollen können diese Einstellungen bearbeiten.
    
- **Stellen Sie sicher, dass dem Gerät eine Automatisierungsbereinigungsstufe zugewiesen ist.**<br>
Sie müssen mindestens die mindeste Korrekturstufe für eine bestimmte Gerätegruppe aktivieren. Andernfalls können Sie keine Live-Antwortsitzung für ein Mitglied dieser Gruppe einrichten.

    Sie erhalten den folgenden Fehler:

    ![Abbildung der Fehlermeldung](images/live-response-error.png)

- **Aktivieren Sie die Ausführung nicht signierter Skripts für Liveantworten** (optional). <br>

    >[!WARNING]
    >Wenn Sie die Verwendung von nicht signierten Skripts zulassen, können Sie Bedrohungen mehr ausgesetzt sein.
 
  Das Ausführen von nicht signierten Skripts wird nicht empfohlen, da dadurch Bedrohungen erhöht werden können. Wenn Sie sie jedoch verwenden müssen, müssen Sie die Einstellung auf der Seite ["Erweiterte Features"](advanced-features.md) aktivieren.
    
- **Stellen Sie sicher, dass Sie über die entsprechenden Berechtigungen verfügen.**<br>
    Nur Benutzer, die über die entsprechenden Berechtigungen verfügen, können eine Sitzung initiieren. Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md) 

    > [!IMPORTANT]
    > Die Option zum Hochladen einer Datei in die Bibliothek ist nur für Personen mit den entsprechenden RBAC-Berechtigungen verfügbar. Die Schaltfläche ist für Benutzer mit nur delegierten Berechtigungen abgeblendet.

    Je nachdem, welche Rolle Ihnen zugewiesen wurde, können Sie einfache oder erweiterte Liveantwortbefehle ausführen. Benutzerberechtigungen werden von der benutzerdefinierten RBAC-Rolle gesteuert. 

## <a name="live-response-dashboard-overview"></a>Übersicht über das Live-Antwortdashboard
Wenn Sie eine Liveantwortsitzung auf einem Gerät initiieren, wird ein Dashboard geöffnet. Das Dashboard enthält Informationen über die Sitzung, z. B. die folgenden: 

- Wer die Sitzung erstellt
- Zeitpunkt, zu dem die Sitzung gestartet wurde
- Die Dauer der Sitzung

Das Dashboard bietet Ihnen außerdem Zugriff auf:
- Trennen einer Sitzung
- Hochladen von Dateien in die Bibliothek 
- Befehlskonsole
- Befehlsprotokoll


## <a name="initiate-a-live-response-session-on-a-device"></a>Initiieren einer Liveantwortsitzung auf einem Gerät 

1. Melden Sie sich bei Microsoft Defender Security Center an.

2. Navigieren Sie zur Gerätelistenseite, und wählen Sie ein Gerät aus, das untersucht werden soll. Die Geräteseite wird geöffnet.

3. Starten Sie die Liveantwortsitzung, indem Sie **"Liveantwortsitzung initiieren"** auswählen. Eine Befehlskonsole wird angezeigt. Warten Sie, während die Sitzung eine Verbindung mit dem Gerät herstellt.

4. Verwenden Sie die integrierten Befehle, um Ermittlungsarbeit zu leisten. Weitere Informationen finden Sie unter [Live-Antwortbefehle.](#live-response-commands)

5. Wählen Sie nach Abschluss Der Untersuchung die **Sitzung trennen aus,** und wählen Sie dann **Bestätigen** aus.

## <a name="live-response-commands"></a>Live-Antwortbefehle

Je nachdem, welche Rolle Ihnen zugewiesen wurde, können Sie einfache oder erweiterte Liveantwortbefehle ausführen. Benutzerberechtigungen werden von benutzerdefinierten RBAC-Rollen gesteuert. Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md) 


>[!NOTE]
>Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.

### <a name="basic-commands"></a>Grundlegende Befehle

Die folgenden Befehle sind für Benutzerrollen verfügbar, denen die Möglichkeit gewährt wird, **grundlegende** Liveantwortbefehle auszuführen. Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md) 

| Befehl | Beschreibung |
|---|---|--- |
|`cd` | Ändert das aktuelle Verzeichnis. | 
|`cls` | Löscht den Konsolenbildschirm.  |
|`connect` | Initiiert eine Liveantwortsitzung auf dem Gerät. |
|`connections` | Zeigt alle aktiven Verbindungen an. |
|`dir` | Zeigt eine Liste von Dateien und Unterverzeichnissen in einem Verzeichnis an. |
|`drivers` |  Zeigt alle auf dem Gerät installierten Treiber an. |
|`fg <command ID>` | Platzieren Sie den angegebenen Auftrag im Vordergrund im Vordergrund, sodass er der aktuelle Auftrag ist. <br> HINWEIS: fg verwendet eine "Befehls-ID", die in Aufträgen verfügbar ist, nicht eine PID. |
|`fileinfo` | Abrufen von Informationen zu einer Datei. |
|`findfile` | Sucht Dateien anhand eines bestimmten Namens auf dem Gerät. |
|`getfile <file_path>` | Lädt eine Datei herunter. |
|`help` | Enthält Hilfeinformationen für Liveantwortbefehle. |
|`jobs` | Zeigt derzeit ausgeführte Aufträge, deren ID und Status an. |
|`persistence` | Zeigt alle bekannten Persistenzmethoden auf dem Gerät an. |
|`processes` | Zeigt alle auf dem Gerät ausgeführten Prozesse an. |
|`registry` | Zeigt Registrierungswerte an. |
|`scheduledtasks` | Zeigt alle geplanten Aufgaben auf dem Gerät an. |
|`services` | Zeigt alle Dienste auf dem Gerät an. |
|`trace` | Legt den Protokollierungsmodus des Terminal für das Debuggen fest. |

### <a name="advanced-commands"></a>Erweiterte Befehle
Die folgenden Befehle sind für Benutzerrollen verfügbar, denen die Möglichkeit gewährt wird, **erweiterte** Liveantwortbefehle auszuführen. Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md) 

| Befehl | Beschreibung |
|---|---|
| `analyze` | Analysiert die Entität mit verschiedenen Inkriminierungs-Engines, um eine Bewertung zu erzielen. |
| `run` | Führt ein PowerShell-Skript aus der Bibliothek auf dem Gerät aus. |
| `library` | Listet Dateien auf, die in die Liveantwortbibliothek hochgeladen wurden. |
| `putfile` | Platziert eine Datei aus der Bibliothek auf dem Gerät. Dateien werden in einem Arbeitsordner gespeichert und gelöscht, wenn das Gerät standardmäßig neu gestartet wird. |
| `remediate` | Behebt eine Entität auf dem Gerät. Die Korrekturaktion variiert je nach Entitätstyp:<br>- Datei: löschen<br>- Prozess: beenden, Bilddatei löschen<br>- Dienst: beenden, Bilddatei löschen<br>- Registrierungseintrag: löschen<br>– Geplante Aufgabe: entfernen<br>- Startordnerelement: Datei löschen <br> HINWEIS: Dieser Befehl verfügt über einen erforderlichen Befehl. Sie können den `-auto` Befehl zusammen `remediate` verwenden, um den erforderlichen Befehl automatisch auszuführen. 
|`undo` | Stellt eine Entität wieder her, die korrigiert wurde. |


## <a name="use-live-response-commands"></a>Verwenden von Liveantwortbefehlen

Die Befehle, die Sie in der Konsole verwenden können, folgen ähnlichen Prinzipien wie [Windows Befehle.](/windows-server/administration/windows-commands/windows-commands#BKMK_c)

Die erweiterten Befehle bieten einen stabileren Satz von Aktionen, mit denen Sie leistungsstärkere Aktionen ausführen können, z. B. eine Datei herunterladen und hochladen, Skripts auf dem Gerät ausführen und Korrekturmaßnahmen für eine Entität ausführen können.

### <a name="get-a-file-from-the-device"></a>Abrufen einer Datei vom Gerät

Für Szenarien, in dem Sie eine Datei von einem Gerät abrufen möchten, das Sie untersuchen, können Sie den `getfile` Befehl verwenden. Auf diese Weise können Sie die Datei zur weiteren Untersuchung vom Gerät speichern.

>[!NOTE]
>Es gelten die folgenden Dateigrößenbeschränkungen:
>- `getfile` Grenzwert: 3 GB
>- `fileinfo` Grenzwert: 10 GB
>- `library` Grenzwert: 250 MB

### <a name="download-a-file-in-the-background"></a>Herunterladen einer Datei im Hintergrund

Damit Ihr Sicherheitsteam die Untersuchung eines betroffenen Geräts fortsetzen kann, können Dateien jetzt im Hintergrund heruntergeladen werden.

- Um eine Datei im Hintergrund herunterzuladen, geben Sie in der Befehlskonsole für Liveantworten `download <file_path> &` .
- Wenn Sie warten, bis eine Datei heruntergeladen wird, können Sie sie mit STRG +Z in den Hintergrund verschieben.
- Um einen Dateidownload in den Vordergrund zu bringen, geben Sie in der Befehlskonsole der Liveantwort `fg <command_id>` .

Im Folgenden finden Sie einige Beispiele:


|Befehl  |Funktion der Einstellung  |
|---------|---------|
|`getfile "C:\windows\some_file.exe" &`     |Startet das Herunterladen einer Datei mit dem Namen *some_file.exe* im Hintergrund.         |
|`fg 1234`     |Gibt einen Download mit der Befehls-ID *1234* im Vordergrund zurück.         |


### <a name="put-a-file-in-the-library"></a>Einfügen einer Datei in die Bibliothek

Live response has a library where you can put files into. Die Bibliothek speichert Dateien (z. B. Skripts), die in einer Liveantwortsitzung auf Mandantenebene ausgeführt werden können.

Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them. 

Sie können über eine Sammlung von PowerShell-Skripts verfügen, die auf Geräten ausgeführt werden können, mit denen Sie Liveantwortsitzungen initiieren. 

#### <a name="to-upload-a-file-in-the-library"></a>So laden Sie eine Datei in die Bibliothek hoch

1. Klicken Sie auf **Hochladen Datei, um die Bibliothek zu öffnen.** 

2. Klicken Sie auf **"Durchsuchen",** und wählen Sie die Datei aus.

3. Geben Sie eine kurze Beschreibung an.

4. Geben Sie an, ob Sie eine Datei mit demselben Namen überschreiben möchten.

5. Wenn Sie möchten, wissen Sie, welche Parameter für das Skript erforderlich sind, aktivieren Sie das Kontrollkästchen "Skriptparameter". Geben Sie in das Textfeld ein Beispiel und eine Beschreibung ein.

6. Klicken Sie auf **"Bestätigen".** 

7. (Optional) Führen Sie den Befehl aus, um zu überprüfen, ob die Datei in die Bibliothek hochgeladen `library` wurde.


### <a name="cancel-a-command"></a>Abbrechen eines Befehls
Sie können einen Befehl jederzeit während einer Sitzung abbrechen, indem Sie STRG +C drücken.  

>[!WARNING]
>Wenn Sie diese Verknüpfung verwenden, wird der Befehl auf agentseitiger Seite nicht beendet. Es wird nur der Befehl im Portal abgebrochen. Das Ändern von Vorgängen wie "Korrigieren" kann also fortgesetzt werden, während der Befehl abgebrochen wird. 

## <a name="run-a-powershell-script"></a>Ausführen eines PowerShell-Skripts 

Bevor Sie ein PowerShell-Skript ausführen können, müssen Sie es zuerst in die Bibliothek hochladen. 

Verwenden Sie nach dem Hochladen des Skripts in die Bibliothek den `run` Befehl, um das Skript auszuführen.

Wenn Sie beabsichtigen, in der Sitzung ein nicht signiertes Skript zu verwenden, müssen Sie die Einstellung auf der Seite ["Erweiterte Features"](advanced-features.md) aktivieren.

>[!WARNING]
>Wenn Sie die Verwendung von nicht signierten Skripts zulassen, können Sie Bedrohungen mehr ausgesetzt sein.

## <a name="apply-command-parameters"></a>Anwenden von Befehlsparametern

- Sehen Sie sich die Konsolenhilfe an, um mehr über Befehlsparameter zu erfahren. Um mehr über einen einzelnen Befehl zu erfahren, führen Sie Folgendes aus:
 
    `help <command name>`

- Beachten Sie beim Anwenden von Parametern auf Befehle, dass Parameter basierend auf einer festen Reihenfolge behandelt werden:
 
    `<command name> param1 param2` 

- Geben Sie beim Angeben von Parametern außerhalb der festen Reihenfolge den Namen des Parameters mit einem Bindestrich an, bevor Sie den Wert angeben:
 
    `<command name> -param2_name param2`

- Wenn Sie Befehle verwenden, die über erforderliche Befehle verfügen, können Sie Flags verwenden:

    `<command name> -type file -id <file path> - auto` oder `remediate file <file path> - auto`.

## <a name="supported-output-types"></a>Unterstützte Ausgabetypen

Live response supports table and JSON format output types. Für jeden Befehl gibt es ein Standardausgabeverhalten. Mit den folgenden Befehlen können Sie die Ausgabe im bevorzugten Ausgabeformat ändern:

- `-output json`
- `-output table`

>[!NOTE]
>Aufgrund des begrenzten Platzes werden weniger Felder im Tabellenformat angezeigt. Um weitere Details in der Ausgabe anzuzeigen, können Sie den JSON-Ausgabebefehl verwenden, damit weitere Details angezeigt werden.

## <a name="supported-output-pipes"></a>Unterstützte Ausgabepipes

Live response supports output pipeing to CLI and file. CLI ist das Standardausgabeverhalten. Mit dem folgenden Befehl können Sie die Ausgabe an eine Datei weiterleitung: [Befehl] > [Dateiname].txt.  

Beispiel:

```console
processes > output.txt
```

## <a name="view-the-command-log"></a>Anzeigen des Befehlsprotokolls

Wählen Sie die Registerkarte **"Befehlsprotokoll"** aus, um die Befehle anzuzeigen, die während einer Sitzung auf dem Gerät verwendet werden. Jeder Befehl wird mit vollständigen Details nachverfolgt, z. B.:
- ID
- Befehlszeile
- Dauer
- Status- und Eingabe- oder Ausgabe-Seitenleiste

## <a name="limitations"></a>Einschränkungen

- Live-Antwortsitzungen sind jeweils auf 25 Liveantwortsitzungen beschränkt.
- Das inaktive Timeout der Live-Antwortsitzung beträgt 30 Minuten. 
- Ein Benutzer kann bis zu 10 gleichzeitige Sitzungen initiieren.
- Ein Gerät kann sich jeweils nur in einer Sitzung enthalten.
- Es gelten die folgenden Dateigrößenbeschränkungen:
   - `getfile` Grenzwert: 3 GB
   - `fileinfo` Grenzwert: 10 GB
   - `library` Grenzwert: 250 MB

## <a name="related-article"></a>Verwandter Artikel
- [Kommandobeispiele für Liveantworten](live-response-command-examples.md)
