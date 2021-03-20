---
title: Einrichten eines Connectors zum Importieren physischer Daten
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
description: Administratoren können einen Datenconnector einrichten, um Daten aus dem physischen System ihrer Organisation zu Microsoft 365 zu importieren. Auf diese Weise können Sie diese Daten in Insider-Risikomanagementrichtlinien verwenden, um Ihnen zu helfen, den Zugriff auf Ihre physischen Gebäude durch bestimmte Benutzer zu erkennen, die auf eine mögliche interne Bedrohung für Ihre Organisation hinweisen können.
ms.openlocfilehash: c07dfcbefa338f7499f2c45f595bf2ccda6387fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911365"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>Einrichten eines Connectors zum Importieren physischer Daten (Vorschau)

Sie können einen Datenconnector im Microsoft 365 Compliance Center einrichten, um physische Daten zu importieren, z. B. unformatierte physische Zugriffsereignisse des Mitarbeiters oder physische Zugriffsalarme, die durch das Schlechtungssystem Ihrer Organisation generiert werden. Beispiele für physische Zugriffspunkte sind ein Eintrag in ein Gebäude oder ein Eintrag in server room oder data center. Physische Schaddaten können von der Microsoft [](insider-risk-management.md) 365-Insider-Risikomanagementlösung verwendet werden, um Ihre Organisation vor böswilligen Aktivitäten oder Datendiebstahl in Ihrer Organisation zu schützen.

Das Einrichten eines physischen Verbindungsstücks besteht aus den folgenden Aufgaben:

- Erstellen einer App in Azure Active Directory (Azure AD), um auf einen API-Endpunkt zu zugreifen, der eine JSON-Nutzlast akzeptiert, die physische Daten enthält.

- Erstellen der JSON-Nutzlast mit einem Schema, das durch einen physischen Datenconnector definiert ist.

- Erstellen eines physischen Datenconnector für ungültige Daten im Microsoft 365 Compliance Center.

- Ausführen eines Skripts zum Pushen der physischen Daten zum Api-Endpunkt.

- Optional können Sie das Skript so planen, dass es automatisch ausgeführt wird, um aktuell physische Daten zu importieren.

## <a name="before-you-set-up-the-connector"></a>Vor dem Einrichten des Connectors

- Dem Benutzer, der in Schritt 3 den konnektor für physische Verfeinerungen erstellt, muss die Rolle Postfachimportexport in Exchange Online zugewiesen werden. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine neue Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Sie müssen bestimmen, wie Sie die Daten aus dem physischen System für die Verletzung Ihrer Organisation (täglich) abrufen oder exportieren und eine JSON-Datei erstellen, die in Schritt 2 beschrieben wird. Das Skript, das Sie in Schritt 4 ausführen, pusht die Daten in der JSON-Datei an den API-Endpunkt.

- Das Beispielskript, das Sie in Schritt 4 ausführen, pusht die physischen Daten aus der JSON-Datei an die Connector-API, sodass sie von der Insider-Risikomanagementlösung verwendet werden können. Dieses Beispielskript wird in keinem Standardsupportprogramm oder -dienst von Microsoft unterstützt. Das Beispielskript wird wie besehen ohne jegliche Gewährleistung zur Verfügung gestellt. Microsoft schließt ferner alle konkludenten Gewährleistungen, einschließlich, aber nicht beschränkt auf konkludente Gewährleistungen der Marktgängigkeit oder Eignung für einen bestimmten Zweck aus. Das gesamte Risiko, das mit der Verwendung oder Leistung des Beispielskripts und der Dokumentation einhergeht, liegt bei Ihnen. In keinem Fall sind Microsoft, seine Autoren oder an der Erstellung, Produktion oder Übermittlung der Skripts beteiligte Personen für Schäden jeglicher Art (einschließlich und ohne Einschränkung Schäden durch Verlust entgangener Gewinne, Geschäftsunterbrechungen, Verlust von Geschäftsinformationen oder andere geldliche Verluste) haftbar, die aus der Nutzung bzw. Unfähigkeit zur Nutzung der Beispielskripts oder Dokumentation entstehen, auch wenn Microsoft auf die Möglichkeit solcher Schäden hingewiesen wurde.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer App in Azure Active Directory

Der erste Schritt besteht im Erstellen und Registrieren einer neuen App in Azure Active Directory (Azure AD). Die App entspricht dem physischen Badging Connector, den Sie in Schritt 3 erstellen. Durch das Erstellen dieser App kann Azure AD die Pushanforderung für die JSON-Nutzlast authentifizieren, die datenbelastende Daten enthält. Achten Sie beim Erstellen dieser Azure AD-App darauf, die folgenden Informationen zu speichern. Diese Werte werden in späteren Schritten verwendet.

- Azure AD-Anwendungs-ID (auch als *App-ID oder* *Client-ID bezeichnet)*

- Geheimer Azure AD-Anwendungsgeheimnis (auch als Geheimer *Clientgeheimnis bezeichnet)*

- Mandanten-ID (auch *Verzeichnis-ID genannt)*

Schrittweise Anweisungen zum Erstellen einer App in Azure AD finden Sie unter Registrieren einer Anwendung [bei der Microsoft Identity Platform](/azure/active-directory/develop/quickstart-register-app).

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>Schritt 2: Vorbereiten einer JSON-Datei mit datenbearbeitenden Daten

Im nächsten Schritt erstellen Sie eine JSON-Datei, die Informationen zu den physischen Zugriffsdaten der Mitarbeiter enthält. Wie im Abschnitt vor Beginn erläutert, müssen Sie bestimmen, wie diese JSON-Datei aus dem system für physische Verletzung Ihrer Organisation generiert wird.

Die JSON-Datei muss der vom Connector erforderlichen Schemadefinition entsprechen. Im Folgenden finden Sie Beschreibungen der erforderlichen Schemaeigenschaften für die JSON-Datei:

| Eigenschaft | Beschreibung | Datentyp |
|:-----------|:--------------|:------------|
|UserId|Ein Mitarbeiter kann über mehrere digitale Identitäten in den Systemen verfügen. Für die Eingabe muss die Azure AD-ID bereits vom Quellsystem aufgelöst werden. |UPN oder E-Mail-Adresse|
|AssetId|Die Referenz-ID der physischen Ressource oder des physischen Zugriffspunkts.| Alphanumerische Zeichenfolge|
|AssetName|Der Anzeigename der physischen Ressource oder des physischen Zugriffspunkts.|Alphanumerische Zeichenfolge|
|EventTime|Der Zeitstempel des Zugriffs.|Datum und Uhrzeit im UTC-Format|
|AccessStatus|Wert von `Success` oder `Failed`| String|
|||

Im Folgenden finden Sie ein Beispiel für eine JSON-Datei, die dem erforderlichen Schema entspricht:

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
Sie können auch die folgende Schemadefinition für die JSON-Datei aus dem Assistenten herunterladen, wenn Sie den konnektor für physische Sperre in Schritt 3 erstellen.

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

## <a name="step-3-create-the-physical-badging-connector"></a>Schritt 3: Erstellen des physischen Badgingconnector

Im nächsten Schritt erstellen Sie im Microsoft 365 Compliance Center einen physischen Badging Connector. Nachdem Sie das Skript in Schritt 4 ausgeführt haben, wird die in Schritt 3 erstellte JSON-Datei verarbeitet und an den in Schritt 1 konfigurierten API-Endpunkt gesendet. Kopieren Sie in diesem Schritt unbedingt die JobId, die beim Erstellen des Connectors generiert wird. Sie verwenden die JobId, wenn Sie das Skript ausführen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu,  und klicken Sie dann im linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf der Seite** Datenconnectors unter **Physisches Badging** auf **Ansicht**.

3. Klicken Sie **auf der Seite Physisches Badging** auf **Connector hinzufügen.**

4. Gehen Sie auf der Seite **Authentifizierungsanmeldeinformationen** wie folgt vor, und klicken Sie dann auf **Weiter**:
  
   1. Geben Sie die Azure AD-Anwendungs-ID für die Azure-App ein, die Sie in Schritt 1 erstellt haben, oder fügen Sie sie ein.
  
   2. Laden Sie das Beispielschema für Ihren Verweis herunter, um die JSON-Datei zu erstellen.
  
   3. Geben Sie einen eindeutigen Namen für den physischen Badgingconnector ein.

5. Überprüfen Sie **auf** der Seite Überprüfen Ihre Einstellungen, und klicken Sie dann auf **Fertig** stellen, um den Connector zu erstellen.

6. Es wird eine Statusseite angezeigt, die bestätigt, dass der Connector erstellt wurde. Diese Seite enthält auch die Auftrags-ID. Sie können die Auftrags-ID von dieser Seite oder von der Flyoutseite für den Connector kopieren. Sie benötigen diese Auftrags-ID, wenn Sie das Skript ausführen.

   Die Statusseite enthält auch einen Link zum Skript. Lesen Sie dieses Skript, um zu verstehen, wie die JSON-Datei an den API-Endpunkt gesendet wird.

7. Klicken Sie auf **Fertig**.

   Der neue Connector wird in der Liste auf der Registerkarte **Connectors** angezeigt.

8. Klicken Sie auf den gerade erstellten physischen Verbinder zum Anzeigen der Flyoutseite, die Eigenschaften und andere Informationen zum Connector enthält.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>Schritt 4: Führen Sie das Skript aus, um Ihre JSON-Datei mit physischen Daten zu veröffentlichen

Der nächste Schritt beim Einrichten eines Konnektors für physische Badging besteht in der Ausführung eines Skripts, das die physischen Daten in der JSON-Datei (die Sie in Schritt 2 erstellt haben) an den in Schritt 1 erstellten API-Endpunkt pusht. Wir stellen ein Beispielskript für Ihren Verweis bereit, und Sie können es verwenden oder ein eigenes Skript erstellen, um die JSON-Datei an den API-Endpunkt zu posten.

Nachdem Sie das Skript ausgeführt haben, wird die JSON-Datei mit den physischen Daten zum Risikomanagement per Push an Ihre Microsoft 365-Organisation gesendet, auf die die Insider-Risikomanagementlösung zugreifen kann. Es wird empfohlen, physische Daten täglich zu veröffentlichen. Sie können dies tun, indem Sie den Prozess automatisieren, um die JSON-Datei täglich aus Ihrem physischen System zu generieren, und dann das Skript zum Pushen der Daten planen.

> [!NOTE]
> Die maximale Anzahl von Datensätzen in der JSON-Datei, die von der API verarbeitet werden können, beträgt 50.000 Datensätze.

1. Wechseln Sie [zu dieser GitHub-Website,](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) um auf das Beispielskript zu zugreifen.

2. Klicken Sie auf **die Schaltfläche Raw,** um das Skript in der Textansicht anzeigen zu können.

3. Kopieren Sie alle Zeilen im Beispielskript, und speichern Sie sie dann in einer Textdatei.

4. Ändern Sie bei Bedarf das Beispielskript für Ihre Organisation.

5. Speichern Sie die Textdatei als Windows PowerShell Skriptdatei, indem Sie ein Dateinamensuffix von .ps1 verwenden. Beispiel: PhysicalBadging.ps1.

6. Öffnen Sie eine Eingabeaufforderung auf dem lokalen Computer, und wechseln Sie zu dem Verzeichnis, in dem Sie das Skript gespeichert haben.

7. Führen Sie den folgenden Befehl aus, um die physischen Daten in der #A0 in die #A1 zu pushen. Zum Beispiel:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   In der folgenden Tabelle werden die Parameter beschrieben, die mit diesem Skript verwendet werden müssen, und deren erforderliche Werte. Informationen, die Sie in den vorherigen Schritten erhalten haben, werden in den Werten für diese Parameter verwendet.

   | Parameter | Beschreibung |
   |:-------------|:--------------|
   |tenantId | Dies ist die ID für Ihre Microsoft 365-Organisation, die Sie in Schritt 1 erhalten haben. Sie können die tenantId für Ihre Organisation auch auf dem **Blatt Übersicht im** Azure AD Admin Center abrufen. Dies wird verwendet, um Ihre Organisation zu identifizieren. |
   |appId | Dies ist die Azure AD-Anwendungs-ID für die App, die Sie in Azure AD in Schritt 1 erstellt haben. Dies wird von Azure AD für die Authentifizierung verwendet, wenn das Skript versucht, auf Ihre Microsoft 365-Organisation zu zugreifen.                    |
   |appSecret | Dies ist der geheime Azure AD-Anwendungsgeheimnis für die App, die Sie in Azure AD in Schritt 1 erstellt haben. Dies wird auch für die Authentifizierung verwendet.                                                        |
   |jobId | Dies ist die Auftrags-ID für den in Schritt 3 erstellten connector für physische Badging. Dies wird verwendet, um die physischen Daten zu zuordnen, die an die Microsoft Cloud gesendet werden, dem physischen Badging-Connector.              |
   |JsonFilePath | Dies ist der Dateipfad auf dem lokalen Computer (der Dateipfad, den Sie zum Ausführen des Skripts verwenden) für die JSON-Datei, die Sie in Schritt 2 erstellt haben. Diese Datei muss dem in Schritt 3 beschriebenen Beispielschema folgen.|
   |||

   Im Folgenden finden Sie ein Beispiel für die Syntax für das Skript für das physische Badging Connector, das die tatsächlichen Werte für jeden Parameter verwendet:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   Wenn der Upload erfolgreich war, zeigt das Skript die **Meldung Erfolgreich hochladen** an.

   Wenn Sie über mehrere JSON-Dateien verfügen, müssen Sie das Skript für jede Datei ausführen.

> [!NOTE]
> Sie können auch festlegen, dass die physischen Daten zum Ausschmieren mit anderen Methoden als dem vorherigen Skript an den API-Endpunkt gesendet werden. Hier finden Sie beispielsweise ein Beispiel für die Verwendung von Postman zum Pushen Ihrer Daten an den API-Endpunkt.

## <a name="step-5-monitor-the-physical-badging-connector"></a>Schritt 5: Überwachen des physischen Verbindungsstücks

Nachdem Sie den connector für physische Meldungen erstellt und Ihre physischen Daten zum Ausschmieren übertragen haben, können Sie den Connector und den Uploadstatus im Microsoft 365 Compliance Center anzeigen. Wenn Sie planen, dass das Skript regelmäßig automatisch ausgeführt wird, können Sie auch den aktuellen Status nach dem letzten Ausführen des Skripts anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie auf **die** Registerkarte Connectors, und wählen Sie dann den physischen Verbinder aus, um die Flyoutseite anzeigen zu können. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

   ![Statusf flyout page for physical badging connector](..\media\PhysicalBadgingStatusFlyout.png)

3. Klicken **Sie unter Letzter Import** auf den Link Protokoll **herunterladen,** um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen zu jedem Ausführen und Hochladen der Daten aus der CSV-Datei in die Microsoft Cloud.

   ![Protokolldatei des physischen Verbinders zeigt Nummernzeilen aus der hochgeladenen JSON-Datei an.](..\media\PhysicalBadgingConnectorLogFile.png)

   Das **Feld RecordsSaved** gibt die Anzahl der Zeilen in der hochgeladenen CSV-Datei an. Wenn die CSV-Datei beispielsweise vier Zeilen enthält, ist der Wert der **RecordsSaved-Felder** 4, wenn das Skript alle Zeilen in der CSV-Datei erfolgreich hochgeladen hat.

Wenn Sie das Skript in Schritt 4 nicht ausgeführt haben, wird unter Letzter Import ein Link zum Herunterladen des **Skripts angezeigt.** Sie können das Skript herunterladen und dann die Schritte in Schritt 4 ausführen, um es auszuführen.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Optional) Schritt 6: Planen der automatischen Ausführung des Skripts

Um sicherzustellen, dass tools wie der Insider-Risikomanagement-Lösung die neuesten physischen Daten aus Ihrer Organisation zur Verfügung stehen, wird empfohlen, dass Sie das Skript so planen, dass es regelmäßig ausgeführt wird, z. B. einmal am Tag. Dies erfordert auch, dass Sie die physischen Daten in der JSON-Datei nach einem ähnlichen (wenn nicht demselben) Zeitplan aktualisieren, damit sie die neuesten Informationen zu Mitarbeitern enthält, die Ihre Organisation verlassen. Das Ziel besteht in dem Hochladen der aktuellen Daten zu physischen Gefährdungsrisiken, damit der Connector für physisches Badging diese für die Lösung für das Insiderrisikomanagement zur Verfügung stellen kann.

Sie können die TaskPlaner-App in Windows verwenden, um das Skript täglich automatisch auszuführen.

1. Klicken Sie auf dem lokalen Computer auf die Schaltfläche Windows **Start,** und geben Sie **task scheduler ein.**

2. Klicken Sie auf **die TaskPlaner-App,** um sie zu öffnen.

3. Klicken Sie **im Abschnitt** Aktionen auf **Aufgabe erstellen.**

4. Geben Sie **auf** der Registerkarte Allgemein einen beschreibenden Namen für den geplanten Vorgang ein. Beispiel: Script für **physisches Badging.** Sie können auch eine optionale Beschreibung hinzufügen.

5. Gehen **Sie unter** Sicherheitsoptionen wie folgt vor:

   1. Bestimmen Sie, ob das Skript nur ausgeführt werden soll, wenn Sie am Computer angemeldet sind, oder führen Sie es aus, wenn Sie angemeldet sind oder nicht.

   2. Stellen Sie sicher, dass das **Kontrollkästchen Ausführen** mit den höchsten Rechten aktiviert ist.

6. Wählen Sie **die Registerkarte Trigger aus,** klicken Sie auf **Neu**, und gehen Sie dann wie folgt vor:

   1. Wählen **Sie unter** Einstellungen die Option **Täglich** aus, und wählen Sie dann Datum und Uhrzeit aus, um das Skript zum ersten Mal auszuführen. Das Skript wird jeden Tag zur angegebenen Zeit ausgeführt.

   2. Stellen **Sie unter Erweiterte Einstellungen** sicher, dass das Kontrollkästchen Aktiviert aktiviert ist. 

   3. Klicken Sie auf **OK**.

7. Wählen Sie die **Registerkarte** Aktionen aus, klicken **Sie auf Neu**, und gehen Sie dann wie folgt vor:

   ![Aktionseinstellungen zum Erstellen einer neuen geplanten Aufgabe für das Skript für das physische Badging Connector](..\media\SchedulePhysicalBadgingScript1.png)

   1. Stellen Sie in der **Dropdownliste** Aktion sicher, dass **Programm starten** ausgewählt ist.

   2. Klicken Sie im Feld **Programm/Skript** auf **Durchsuchen,** und wechseln Sie zum folgenden Speicherort, und wählen Sie ihn aus, damit der Pfad im Feld angezeigt wird: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe.

   3. Fügen Sie im Feld Argumente **hinzufügen (optional)** denselben Skriptbefehl ein, den Sie in Schritt 4 ausgeführt haben. Beispiel: .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. Fügen Sie **im Feld Start in (optional)** den Ordnerspeicherort des Skripts ein, das Sie in Schritt 4 ausgeführt haben. Beispiel: C:\Users\contosoadmin\Desktop\Scripts.

   5. Klicken **Sie auf Ok,** um die Einstellungen für die neue Aktion zu speichern.

8. Klicken Sie **im Fenster Aufgabe** erstellen auf **Ok,** um den geplanten Vorgang zu speichern. Möglicherweise werden Sie aufgefordert, Ihre Benutzerkontoanmeldeinformationen ein eingeben.

   Der neue Vorgang wird in der Taskplanerbibliothek angezeigt.

   ![Der neue Vorgang wird in der Taskplanerbibliothek angezeigt.](..\media\SchedulePhysicalBadgingScript2.png)

Das letzte Mal, bei dem das Skript ausgeführt wurde, und das nächste Mal, wenn es ausgeführt werden soll, wird angezeigt. Sie können auf die Aufgabe doppelklicken, um sie zu bearbeiten.

Sie können auch überprüfen, wie lange das Skript zuletzt auf der Flyoutseite des entsprechenden physischen Badging-Connectors im Compliance Center ausgeführt wurde.