---
title: Einrichten eines Connectors zum Importieren physischer Badges-Daten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Administratoren können einen Daten Konnektor einrichten, um Daten aus dem physischen Badges-System Ihrer Organisation nach Microsoft 365 zu importieren. Auf diese Weise können Sie diese Daten in Richtlinien für das Insider Risikomanagement verwenden, damit Sie den Zugriff auf ihre physischen Gebäude von bestimmten Benutzern erkennen können, die auf eine mögliche interne Bedrohung Ihrer Organisation hindeuten.
ms.openlocfilehash: 71f43d8e6abd53454b6c81d811d0dca2e8b08388
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816648"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>Einrichten eines Connectors zum Importieren physischer Badges-Daten (Vorschau)

Sie können einen Daten Konnektor im Microsoft 365 Compliance Center einrichten, um physische Badges-Daten wie unformatierte physische Zugriffsereignisse des Mitarbeiters oder alle vom Badges-System des Unternehmens generierten physischen Zugriffs Warnungen zu importieren. Beispiele für physikalische Zugriffspunkte sind ein Eintrag für ein Gebäude oder ein Eintrag in einen Serverraum oder ein Datencenter. Physische Badges-Daten können von der Microsoft 365 [Insider Risk Management-Lösung](insider-risk-management.md) verwendet werden, um Ihre Organisation vor böswilligen Aktivitäten oder Datendiebstahl in Ihrer Organisation zu schützen.

Das Einrichten eines physischen Badges-Connectors besteht aus den folgenden Aufgaben:

- Erstellen einer APP in Azure Active Directory (Azure AD) für den Zugriff auf einen API-Endpunkt, der eine JSON-Nutzlast akzeptiert, die physikalische Badges-Daten enthält.

- Erstellen der JSON-Nutzlast mit einem Schema, das durch physikalische Badges Data Connector definiert ist.

- Erstellen eines physischen Badges-Daten Konnektors im Microsoft 365 Compliance Center.

- Ausführen eines Skripts zum Pushen der physischen Badges-Daten an den API-Endpunkt.

- Optional wird das automatische Ausführen des Skripts zum Importieren von derzeit physischen Badges-Daten geplant.

## <a name="before-you-set-up-the-connector"></a>Vor dem Einrichten des Connectors

- Ihre Organisation muss einwilligen, dass der Office 365-Import Dienst auf Daten in Ihrer Organisation zugreifen kann. Um dieser Anforderung zuzustimmen, gehen Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), melden Sie sich mit den Anmeldeinformationen eines globalen Administrators von Microsoft 365 an, und nehmen Sie dann die Anforderung an. Sie müssen diesen Schritt ausführen, bevor Sie den physischen Badges-Connector in Schritt 3 erfolgreich erstellen können.

- Dem Benutzer, der den physischen Badges-Connector in Schritt 3 erstellt, muss in Exchange Online die Rolle "Post Fach Import Export" zugewiesen sein. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine neue Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Sie müssen bestimmen, wie Sie die Daten aus dem physischen Badges-System Ihrer Organisation (täglich) abrufen oder exportieren und eine JSON-Datei erstellen, die in Schritt 2 beschrieben wird. Durch das in Schritt 4 ausgeführte Skript werden die Daten in der JSON-Datei an den API-Endpunkt verschoben.

- Im Beispielskript, das Sie in Schritt 4 ausführen, werden die physikalischen Badges-Daten aus der JSON-Datei in die Connector-API verschoben, damit Sie von der Insider Risiko-Verwaltungslösung verwendet werden kann. Dieses Beispielskript wird unter keinem Microsoft Standard Support Programm oder-Dienst unterstützt. Das Beispielskript wird ohne jegliche Gewährleistung bereitgestellt. Microsoft schließt ferner alle konkludenten Gewährleistungen, einschließlich, aber nicht beschränkt auf konkludente Gewährleistungen der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Das gesamte Risiko, das aus der Verwendung oder der Leistung des Beispielskripts und der Dokumentation erwachsen, bleibt bei Ihnen. In keinem Fall sind Microsoft, seine Autoren oder an der Erstellung, Produktion oder Übermittlung der Skripts beteiligte Personen für Schäden jeglicher Art (einschließlich und ohne Einschränkung Schäden durch Verlust entgangener Gewinne, Geschäftsunterbrechungen, Verlust von Geschäftsinformationen oder andere geldliche Verluste) haftbar, die aus der Nutzung bzw. Unfähigkeit zur Nutzung der Beispielskripts oder Dokumentation entstehen, auch wenn Microsoft auf die Möglichkeit solcher Schäden hingewiesen wurde.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer APP in Azure Active Directory

Der erste Schritt besteht darin, eine neue app in Azure Active Directory (Azure AD) zu erstellen und zu registrieren. Die APP entspricht dem physischen Badges-Connector, den Sie in Schritt 3 erstellen. Durch das Erstellen dieser APP wird Azure Ad die Push-Anforderung für JSON-Nutzlast mit physischen Badges-Daten authentifizieren können. Achten Sie beim Erstellen dieser Azure AD-App darauf, die folgenden Informationen zu speichern. Diese Werte werden in späteren Schritten verwendet.

- Azure AD Anwendungs-ID (auch als *App-ID* oder *Client-ID* bezeichnet)

- Geheime Azure AD Anwendung (auch als *geheimer Client Schlüssel* bezeichnet)

- Mandanten-ID (auch als *Verzeichnis-ID* bezeichnet)

Eine Schritt-für-Schritt-Anleitung zum Erstellen einer APP in Azure AD finden Sie unter [Registrieren einer Anwendung mit der Microsoft Identity-Plattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>Schritt 2: Vorbereiten einer JSON-Datei mit physischen Badges-Daten

Der nächste Schritt besteht darin, eine JSON-Datei zu erstellen, die Informationen zu den physischen Zugriffsdaten von Mitarbeitern enthält. Wie im Abschnitt bevor Sie beginnen beschrieben, müssen Sie bestimmen, wie diese JSON-Datei aus dem physischen Badges-System Ihrer Organisation generiert werden soll.

Die JSON-Datei muss mit der Schema Definition übereinstimmen, die für den Connector erforderlich ist. Hier finden Sie eine Beschreibung der erforderlichen Schemaeigenschaften für die JSON-Datei:

| Eigenschaft | Beschreibung | Datentyp |
|:-----------|:--------------|:------------|
|UserId|Ein Mitarbeiter kann mehrere digitale Identitäten in allen Systemen haben. Für die Eingabe muss die Azure Ad-ID bereits vom Quellsystem aufgelöst werden. |UPN oder e-Mail-Adresse|
|Posten|Die Referenz-ID des physischen Objekts oder physischen Zugriffspunkts.| Alphanumerische Zeichenfolge|
|AssetName|Der Anzeigename des physischen Objekts oder des physischen Zugriffs Points.|Alphanumerische Zeichenfolge|
|EventTime|Der Zeitstempel des Zugriffs.|Datum und Uhrzeit im UTC-Format|
|AccessStatus|Wert von `Success` oder `Failed`| String|
|||

Im folgenden finden Sie ein Beispiel für eine JSON-Datei, die dem erforderlichen Schema entspricht:

```json
[
    {
        "UserId":"sarad@contoso.com"
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed",
    },
    {
        "UserId":"pilarp@contoso.com",        
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",        
        "AccessStatus":"Success",
    }
]
```
Sie können auch die folgende Schema Definition für die JSON-Datei aus dem Assistenten herunterladen, wenn Sie den physikalischen Badges-Connector in Schritt 3 erstellen.

```text
{
    "title" : "Physical Badging Signals",
    "description" : "Access signals from physical badging systems",
    "DataType" : {
        "description" : "Identify what is the data type for input signal",
        "type" : "string",
    },
    "type" : "object",
    "properties": {
        "UserId" : {
            "description" : "Unique identifier AAD Id resolved by the source system",
            "type" : "string",
        },
        "AssetId": {
            "description" : "Unique ID of the physical asset/access point",
            "type" : "string",
        },
        "AssetName": {
            "description" : "friendly name of the physical asset/access point",
            "type" : "string",
        },
        "EventTime" : {
            "description" : "timestamp of access",
            "type" : "string",
        },
        "AccessStatus" : {
            "description" : "what was the status of access attempt - Success/Failed",
            "type" : "string",
        },
    }
    "required" : ["UserId", "AssetId", "EventTime" "AccessStatus"]
}
```

## <a name="step-3-create-the-physical-badging-connector"></a>Schritt 3: Erstellen des physischen Badges-Connectors

Im nächsten Schritt erstellen Sie einen physikalischen Badges-Connector im Microsoft 365 Compliance Center. Nachdem Sie das Skript in Schritt 4 ausgeführt haben, wird die JSON-Datei, die Sie in Schritt 3 erstellt haben, verarbeitet und an den in Schritt 1 konfigurierten API-Endpunkt verschoben. In diesem Schritt müssen Sie unbedingt die JobID kopieren, die beim Erstellen des Connectors generiert wird. Sie verwenden das JobID, wenn Sie das Skript ausführen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann im linken Navigationsbereich auf **Datenverbindungen** .

2. Klicken Sie auf der Seite **Daten Konnektoren** unter **physikalische Badges** auf **Ansicht** .

3. Klicken Sie auf der Seite **physikalische Badges** auf **Connector hinzufügen** .

4. Führen Sie auf der Seite **Authentifizierungsanmeldeinformationen** folgende Schritte aus, und klicken Sie dann auf **weiter** :
  
   1. Geben Sie die Azure AD Anwendungs-ID für die Azure-App ein, die Sie in Schritt 1 erstellt haben, oder fügen Sie Sie ein.
  
   2. Laden Sie das Beispielschema für Ihren Verweis herunter, um die JSON-Datei zu erstellen.
  
   3. Geben Sie einen eindeutigen Namen für den physikalischen Badges-Connector ein.

5. Überprüfen Sie die Einstellungen auf der Seite **überprüfen** , und klicken Sie dann auf **Fertig stellen** , um den Connector zu erstellen.

6. Eine Statusseite wird angezeigt, die bestätigt, dass der Connector erstellt wurde. Diese Seite enthält auch die Auftrags-ID. Sie können die Auftrags-ID von dieser Seite oder von der Flyout-Seite für den Connector kopieren. Sie benötigen diese Auftrags-ID, wenn Sie das Skript ausführen.

   Die Seite Status enthält auch einen Link zum Skript. In diesem Skript erfahren Sie, wie Sie die JSON-Datei an den API-Endpunkt senden.

7. Klicken Sie auf **Fertig** .

   Der neue Connector wird in der Liste auf der Registerkarte **Connectors** angezeigt.

8. Klicken Sie auf den physischen Badges-Connector, den Sie soeben erstellt haben, um die Flyout-Seite anzuzeigen, die Eigenschaften und andere Informationen zum Connector enthält.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>Schritt 4: Ausführen des Skripts zum Bereitstellen der JSON-Datei mit physischen Badges-Daten

Der nächste Schritt beim Einrichten eines physischen Badges-Konnektors besteht darin, ein Skript auszuführen, mit dem die physischen Badges-Daten in der JSON-Datei (die Sie in Schritt 2 erstellt haben) an den in Schritt 1 erstellten API-Endpunkt übertragen werden. Wir stellen ein Beispielskript für Ihren Verweis bereit und können es verwenden oder ein eigenes Skript erstellen, um die JSON-Datei an den API-Endpunkt zu senden.

Nachdem Sie das Skript ausgeführt haben, wird die JSON-Datei mit den physikalischen Badges-Daten in Ihre Microsoft 365-Organisation verschoben, wo Sie von der Insider Risk Management-Lösung aufgerufen werden kann. Es wird empfohlen, täglich physische Badges-Daten zu Posten. Sie können dies tun, indem Sie den Prozess automatisieren, um die JSON-Datei jeden Tag aus Ihrem physischen Badges-System zu generieren und dann das Skript so zu planen, dass die Daten weiter geschoben werden.

> [!NOTE]
> Die maximale Anzahl von Datensätzen in der JSON-Datei, die von der API verarbeitet werden können, ist 50.000 Datensätze.

1. Wechseln Sie zu [dieser GitHub-Website](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) , um auf das Beispielskript zuzugreifen.

2. Klicken Sie auf die Schaltfläche **RAW** , um das Skript in der Textansicht anzuzeigen.

3. Kopieren Sie alle Zeilen im Beispielskript, und speichern Sie Sie in einer Textdatei.

4. Ändern Sie bei Bedarf das Beispielskript für Ihre Organisation.

5. Speichern Sie die Textdatei als Windows PowerShell Skriptdatei unter Verwendung des Datei namens Suffixes. ps1; Beispiel: PhysicalBadging.ps1.

6. Öffnen Sie eine Eingabeaufforderung auf dem lokalen Computer, und wechseln Sie zu dem Verzeichnis, in dem Sie das Skript gespeichert haben.

7. Führen Sie den folgenden Befehl aus, um die physischen Badges-Daten in der JSON-Datei in die Microsoft-Cloud zu verschieben. Zum Beispiel:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   In der folgenden Tabelle werden die Parameter beschrieben, die mit diesem Skript verwendet werden sollen, sowie die erforderlichen Werte. Informationen, die Sie in den vorherigen Schritten erhalten haben, werden in den Werten für diese Parameter verwendet.

   | Parameter | Beschreibung |
   |:-------------|:--------------|
   |tenantId | Dies ist die ID für Ihre Microsoft 365-Organisation, die Sie in Schritt 1 erhalten haben. Sie können die Mandanten-Nr für Ihre Organisation auch auf dem Blatt " **Übersicht** " im Azure AD Admin Center abrufen. Dies wird verwendet, um Ihre Organisation zu identifizieren. |
   |appId | Dies ist die Azure AD Anwendungs-ID für die APP, die Sie in Azure AD in Schritt 1 erstellt haben. Dies wird von Azure AD für die Authentifizierung verwendet, wenn das Skript versucht, auf Ihre Microsoft 365-Organisation zuzugreifen.                    |
   |appSecret | Dies ist der Azure AD geheime Anwendungsschlüssel für die APP, die Sie in Azure AD in Schritt 1 erstellt haben. Dies wird auch für die Authentifizierung verwendet.                                                        |
   |JobId | Dies ist die Auftrags-ID für den physischen Badges-Connector, den Sie in Schritt 3 erstellt haben. Dies wird verwendet, um die physischen Badges-Daten zuzuordnen, die mit dem physikalischen Badges-Connector an die Microsoft-Cloud gesendet werden.              |
   |JsonFilePath | Dies ist der Dateipfad auf dem lokalen Computer (den Sie zum Ausführen des Skripts verwenden) für die JSON-Datei, die Sie in Schritt 2 erstellt haben. Diese Datei muss dem in Schritt 3 beschriebenen Beispielschema entsprechen.|
   |||

   Im folgenden finden Sie ein Beispiel für die Syntax für das physikalische Badges-Connector-Skript unter Verwendung der tatsächlichen Werte für die einzelnen Parameter:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   Wenn der Upload erfolgreich war, zeigt das Skript die **erfolgreiche Nachricht hochladen** an.

   Wenn Sie mehrere JSON-Dateien haben, müssen Sie das Skript für jede Datei ausführen.

> [!NOTE]
> Sie können auch festlegen, dass die physikalischen Badges-Daten mit anderen Methoden als dem Ausführen des vorherigen Skripts an den API-Endpunkt verschoben werden. Hier ist beispielsweise ein Beispiel für die Verwendung von Postman zum Pushen Ihrer Daten an den API-Endpunkt.

## <a name="step-5-monitor-the-physical-badging-connector"></a>Schritt 5: Überwachen des physischen Badges-Connectors

Nachdem Sie den physischen Badges-Connector erstellt und ihre physischen Badges-Daten weiter gepusht haben, können Sie den Connector-und den Uploadstatus im Microsoft 365 Compliance Center anzeigen. Wenn Sie planen, dass das Skriptregel mäßig automatisch ausgeführt wird, können Sie auch den aktuellen Status nach der letzten Ausführung des Skripts anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann den physikalischen Badges Connector aus, um die Flyout-Seite anzuzeigen. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

   ![Status Flyout-Seite für physischen Badges-Connector](..\media\PhysicalBadgingStatusFlyout.png)

3. Klicken Sie unter **Letzter Import** auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen über jedes Mal, wenn das Skript ausgeführt wird, und lädt die Daten aus der CSV-Datei in die Microsoft-Cloud hoch.

   ![Physische Badges-Connector-Protokolldatei zeigt Nummern Zeilen aus JSON-Dateien an, die hochgeladen wurden](..\media\PhysicalBadgingConnectorLogFile.png)

   Das Feld **RecordsSaved** gibt die Anzahl der Zeilen in der CSV-Datei an, die hochgeladen wurden. Wenn die CSV-Datei beispielsweise vier Zeilen enthält, lautet der Wert der **RecordsSaved** -Felder 4, wenn das Skript alle Zeilen in der CSV-Datei erfolgreich hochgeladen hat.

Wenn Sie das Skript nicht in Schritt 4 ausgeführt haben, wird unter **Letzter Import** ein Link zum Herunterladen des Skripts angezeigt. Sie können das Skript herunterladen und dann die Schritte in Schritt 4 ausführen, um es auszuführen.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>Optional Schritt 6: Planen des automatischen Ausführens des Skripts

Um sicherzustellen, dass die neuesten physischen Badges-Daten aus Ihrer Organisation für Tools wie die Lösung für das Insider Risiko verfügbar sind, wird empfohlen, das Skript automatisch regelmäßig zu planen, beispielsweise einmal täglich. Dies erfordert auch, dass Sie die physischen Badges-Daten in der JSON-Datei auf einem ähnlichen (falls nicht demselben) Zeitplan aktualisieren, sodass er die neuesten Informationen zu Mitarbeitern enthält, die Ihre Organisation verlassen. Das Ziel besteht darin, die aktuellsten physischen Badges-Daten hochzuladen, sodass der physische Badges-Connector diese für die Insider Risk Management-Lösung zur Verfügung stellen kann.

Sie können die Task Planer-app in Windows so ausführen, dass das Skript jeden Tag automatisch ausgeführt wird.

1. Klicken Sie auf dem lokalen Computer auf die Schaltfläche Windows- **Start** , und geben Sie dann **Aufgabenplaner** ein.

2. Klicken Sie auf die **Task Planer** -APP, um Sie zu öffnen.

3. Klicken Sie im Abschnitt **Aktionen** auf **Aufgabe erstellen** .

4. Geben Sie auf der Registerkarte **Allgemein** einen beschreibenden Namen für den geplanten Vorgang ein. Beispiel: **Physical Badges Connector Script** . Sie können auch eine optionale Beschreibung hinzufügen.

5. Führen Sie unter **Sicherheitsoptionen** die folgenden Schritte aus:

   1. Bestimmen Sie, ob das Skript nur ausgeführt werden soll, wenn Sie am Computer angemeldet sind oder es ausführen, wenn Sie angemeldet sind oder nicht.

   2. Stellen Sie sicher, dass das Kontrollkästchen **mit den höchsten Rechten ausführen** aktiviert ist.

6. Wählen Sie die Registerkarte **Auslöser** aus, klicken Sie auf **neu** , und führen Sie dann die folgenden Schritte aus:

   1. Wählen Sie unter **Einstellungen** die Option **täglich** aus, und klicken Sie dann auf Datum und Uhrzeit, um das Skript zum ersten Mal auszuführen. Das Skript wird jeden Tag zur gleichen angegebenen Zeit.

   2. Stellen Sie unter **Erweiterte Einstellungen** sicher, dass das Kontrollkästchen **aktiviert** ausgewählt ist.

   3. Klicken Sie auf **OK** .

7. Wählen Sie die Registerkarte **Aktionen** aus, klicken Sie auf **neu** , und führen Sie dann die folgenden Schritte aus:

   ![Aktionseinstellungen zum Erstellen eines neuen geplanten Tasks für das physikalische Badges-Connector-Skript](..\media\SchedulePhysicalBadgingScript1.png)

   1. Stellen Sie in der Dropdownliste **Aktion** sicher, dass **Programm starten** ausgewählt ist.

   2. Klicken Sie im Feld **Programm/Skript** auf **Durchsuchen** , und wechseln Sie zum folgenden Speicherort, und wählen Sie ihn aus, damit der Pfad im Feld angezeigt wird: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe.

   3. Fügen Sie im Feld **Argumente hinzufügen (optional)** den gleichen Skriptbefehl ein, den Sie in Schritt 4 ausgeführt haben. Beispiel: .\PhysicalBadging.ps1-Mandanten-ID "d5723623-11CF-4e2e-b5a5-01d1506273g9"-Benutzerkennung "c12823b7-b55a-4989-faba-02de41bb97c3"-appSecret "MNubVGbcQDkGCnn"-JobID "e081f4f4-3831-48d6-7bb3-fcfab1581458"-jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. Fügen Sie im Feld **Start in (optional)** den Ordnerspeicherort des Skripts ein, das Sie in Schritt 4 ausgeführt haben. Beispiel: C:\Users\contosoadmin\Desktop\Scripts.

   5. Klicken Sie auf **OK** , um die Einstellungen für die neue Aktion zu speichern.

8. Klicken Sie im Fenster **Aufgaben erstellen** auf **OK** , um den geplanten Vorgang zu speichern. Möglicherweise werden Sie aufgefordert, Ihre Anmeldeinformationen für das Benutzerkonto einzugeben.

   Die neue Aufgabe wird in der Aufgabenplanungsbibliothek angezeigt.

   ![Die neue Aufgabe wird in der Aufgabenplanungsbibliothek angezeigt.](..\media\SchedulePhysicalBadgingScript2.png)

Die Uhrzeit, zu der das Skript zuletzt ausgeführt wurde, wird angezeigt, wenn das nächste Mal geplant wird. Sie können auf den Vorgang doppelklicken, um ihn zu bearbeiten.

Sie können auch überprüfen, wann das Skript zuletzt auf der Flyout-Seite des entsprechenden physikalischen Badges-Connectors im Compliance Center ausgeführt wurde.
