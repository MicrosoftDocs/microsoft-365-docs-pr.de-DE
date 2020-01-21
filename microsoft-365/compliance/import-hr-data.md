---
title: Einrichten eines Connectors zum Importieren von HR-Daten
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Administratoren können einen Daten Konnektor einrichten, um Mitarbeiterdaten aus dem Personalwesen (HR) Ihrer Organisation nach Microsoft 365 zu importieren. Auf diese Weise können Sie Personaldaten in Richtlinien für das Insider Risikomanagement verwenden, um die Aktivität bestimmter Benutzer zu ermitteln, die eine interne Bedrohung für Ihre Organisation darstellen können.
ms.openlocfilehash: ba673f6328751a7eee10d5ab4097aa334c09f339
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247652"
---
# <a name="set-up-a-connector-to-import-hr-data"></a>Einrichten eines Connectors zum Importieren von HR-Daten

Sie können einen Daten Konnektor im Microsoft 365 Compliance Center einrichten, um Personaldaten (HR) zu importieren, beispielsweise das Datum, an dem ein Mitarbeiter seinen Rücktritt gesendet hat, und das Datum des letzten Tages des Mitarbeiters. Diese HR-Daten können dann von Microsoft Information Protection-Lösungen wie der neuen [Insider Risiko-Verwaltungslösung](insider-risk-management.md)verwendet werden, um Ihre Organisation vor böswilligen Aktivitäten oder Datendiebstahl in Ihrer Organisation zu schützen. Das Einrichten eines HR-Konnektors besteht darin, eine app in Azure Active Directory zu erstellen, die für die Authentifizierung über Connector verwendet wird, indem Sie eine CSV-Zuordnungsdatei erstellt, die Ihre HR-Daten enthält, einen Data Connector im Compliance Center erstellt und dann ein Skript ausführt (auf einem geplante Basis), die die HR-Daten in der CSV-Datei in die Microsoft-Cloud einnimmt. Der Data Connector verwendet dann Microsoft-Compliance-Lösungen (wie Insider Risk Management), um auf die in Ihre Microsoft 365-Organisation importierten HR-Daten zuzugreifen.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Ihre Organisation muss einwilligen, dass der Office 365-Import Dienst auf Daten in Ihrer Organisation zugreifen kann. Um dieser Anforderung zuzustimmen, gehen Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), melden Sie sich mit den Anmeldeinformationen eines globalen Administrators von Microsoft 365 an, und nehmen Sie dann die Anforderung an. Sie müssen diesen Schritt ausführen, bevor Sie den HR-Connector in Schritt 3 erfolgreich erstellen können.

- Dem Benutzer, der den HR-Connector in Schritt 3 erstellt, muss in Exchange Online die Rolle "Post Fach Import Export" zugewiesen sein. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine neue Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Sie müssen bestimmen, wie Sie die Daten aus dem HR-System Ihrer Organisation (regelmäßig) abrufen oder exportieren und die CSV-Datei hinzufügen, die in Schritt 2 beschrieben wird. Mit dem in Schritt 4 ausgeführten Skript werden die HR-Daten in der CSV-Datei in die Microsoft-Cloud hochgeladen.

- Mit dem in Schritt 4 ausgeführten Beispielskript werden HR-Daten in die Microsoft-Cloud hochgeladen, sodass Sie von anderen Microsoft-Tools wie der Lösung für das Insider Risiko-Management verwendet werden können. Dieses Beispielskript wird unter keinem Microsoft Standard Support Programm oder-Dienst unterstützt. Das Beispielskript wird ohne jegliche Gewährleistung bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Das gesamte Risiko, das aus der Verwendung oder der Leistung des Beispielskripts und der Dokumentation erwachsen, bleibt bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer APP in Azure Active Directory

Der erste Schritt besteht darin, eine neue app in Azure Active Directory (AAD) zu erstellen und zu registrieren. Die APP entspricht dem HR-Konnektor, den Sie in Schritt 3 erstellen.  Durch das Erstellen dieser APP kann Aad den HR-Konnektor bei der Ausführung authentifizieren und versucht, auf Ihre Organisation zuzugreifen. Diese APP wird auch verwendet, um das Skript zu authentifizieren, das Sie in Schritt 4 ausführen, um Ihre HR-Daten in die Microsoft-Cloud hochzuladen. Achten Sie beim Erstellen dieser Aad-App darauf, die folgenden Informationen zu speichern. Diese Werte werden in späteren Schritten in diesem Prozess verwendet.

- Aad-Anwendungs-ID (auch als *App-ID* oder *Client-ID*bezeichnet)

- Aad-Anwendungs Geheimnis (auch als *geheimer Client Schlüssel*bezeichnet)

- Mandanten-ID (auch als *Verzeichnis-ID*bezeichnet)

Eine Schritt-für-Schritt-Anleitung zum Erstellen einer APP in Aad finden Sie unter [Erstellen einer Aad-Anwendung](https://docs.microsoft.com/azure/kusto/management/access-control/how-to-provision-aad-app) .

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a>Schritt 2: Vorbereiten einer CSV-Datei mit ihren HR-Daten

Der nächste Schritt besteht darin, eine CSV-Datei zu erstellen, die Informationen zu Mitarbeitern enthält, die Ihre Organisation verlassen haben. Wie im Abschnitt bevor Sie beginnen beschrieben, müssen Sie bestimmen, wie diese CSV-Datei aus dem HR-System Ihrer Organisation generiert wird. Das folgende Beispiel zeigt eine abgeschlossene CSV-Datei (im Editor geöffnet), die die drei erforderlichen Parameter (Spalten) enthält. Es ist viel einfacher, die CSV-Datei in Microsoft Excel zu bearbeiten.

```text
EmailAddress,TerminationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

In der ersten Zeile oder Kopfzeile der CSV-Datei werden die erforderlichen Spaltennamen aufgelistet. Der Name, der in jeder Spaltenüberschrift verwendet wird, liegt bei Ihnen (im vorherigen Beispiel sind Vorschläge). Die gleichen Spaltennamen, die Sie in der CSV-Datei verwenden, *müssen* jedoch bei der Erstellung des HR-Konnektors in Schritt 3 angegeben werden. Schließen Sie keine Leerzeichen in die Spaltennamen ein.

In der folgenden Tabelle werden die einzelnen Spalten in der CSV-Datei beschrieben:

|**Spaltenname**|**Beschreibung**|
|:-----|:-----|
| **EmailAddress** <br/> |Gibt die e-Mail-Adresse des terminierten Mitarbeiters an.|
| **TerminationDate** <br/> |Gibt das Datum an, an dem die Erwerbstätigkeit der Person in Ihrer Organisation offiziell gekündigt wurde. Dies kann beispielsweise das Datum sein, an dem der Mitarbeiter seine Nachricht über das verlassen Ihrer Organisation mitgeteilt hat. Dieses Datum kann unterschiedlich sein als das Datum des letzten Arbeitstags des Benutzers. Sie müssen das folgende Datumsformat verwenden: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`, das ist das [ISO 8601-Format für Datum und Uhrzeit](https://www.iso.org/iso-8601-date-and-time-format.html).|
|**LastWorkingDate**|Gibt den letzten Tag der Arbeit für den terminierten Mitarbeiter an. Sie müssen das folgende Datumsformat verwenden: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`, das ist das [ISO 8601-Format für Datum und Uhrzeit](https://www.iso.org/iso-8601-date-and-time-format.html).|
|||

Nachdem Sie die CSV-Datei mit den erforderlichen HR-Daten erstellt haben, speichern Sie Sie auf einem lokalen Computer oder Netzwerkspeicherort, der beim Ausführen des Skripts in Schritt 4 angegeben werden kann. Sie sollten auch eine Updatestrategie implementieren, damit die CSV-Datei immer die aktuellsten Informationen enthält, sodass unabhängig von der Ausführung des Skripts die aktuellsten Mitarbeiter Terminierungsdaten in die Microsoft-Cloud hochgeladen werden.

## <a name="step-3-create-the-hr-connector"></a>Schritt 3: Erstellen des HR-Connectors

Im nächsten Schritt erstellen Sie einen HR-Connector im Microsoft 365 Compliance Center. Nachdem Sie das Skript in Schritt 4 ausgeführt haben, wird der von Ihnen erstellte HR-Konnektor die HR-Daten aus der CSV-Datei in Ihre Microsoft 365-Organisation aufnehmen. In diesem Schritt müssen Sie unbedingt die JobID kopieren, die beim Erstellen des Connectors generiert wird. Sie verwenden das JobID, wenn Sie das Skript ausführen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie dann im linken Navigationsbereich auf **Datenverbindungen** .

2. Klicken Sie auf der Seite **Daten Konnektoren (Vorschau)** unter **HR**auf **Ansicht**.

3. Klicken Sie auf der Seite **HR** auf **Connector hinzufügen**.

4. Führen Sie auf der Seite **Authentifizierungsanmeldeinformationen** folgende Schritte aus, und klicken Sie dann auf **weiter**:

   a. Geben Sie die Aad-Anwendungs-ID für die Azure-App ein, die Sie in Schritt 1 erstellt haben, oder fügen Sie Sie ein.

   b. Geben Sie einen Namen für den HR-Konnektor ein.

5. Geben Sie auf der Seite **Dateizuordnung** die drei Spalten überschriftennamen ein (auch als *Parameter* aus der CSV-Datei, die Sie in Schritt 2 in jedem der entsprechenden Felder erstellt haben. Bei den Namen wird die Groß-/Kleinschreibung nicht beachtet. Wie bereits erläutert, müssen die Namen, die Sie in diese Felder eingeben, mit den Parameternamen in der CSV-Datei übereinstimmen. Im folgenden Screenshot sind beispielsweise die Parameternamen aus dem Beispiel in der CSV-Beispieldatei in Schritt 2 dargestellt.

   ![Spaltenüberschrift Namen entsprechen denen in der CSV-Datei](media/HRConnectorWizard3.png)

6. Überprüfen Sie die Einstellungen auf der Seite **überprüfen** , und klicken Sie dann auf **Fertig stellen** , um den Connector zu erstellen.

   Eine Statusseite wird angezeigt, die bestätigt, dass der Connector erstellt wurde. Diese Seite enthält auch die Auftrags-ID. Sie benötigen diese Auftrags-ID, um das Skript im nächsten Schritt auszuführen. Sie können es von dieser Seite oder von der Flyout-Seite für den Connector kopieren.

7. Klicken Sie auf **Fertig**.
   
   Der neue Connector wird in der Liste auf der Registerkarte **Connectors** angezeigt. 

8. Klicken Sie auf den soeben erstellten HR-Konnektor, um die Flyout-Seite anzuzeigen, die Eigenschaften und andere Informationen zum Connector enthält. 

   ![Flyout-Seite für neuen HR-Connector](media/HRConnectorWizard7.png)

   Wenn Sie dies nicht bereits getan haben, können Sie die Werte für die **Azure-APP-ID** und die **Connector-Auftrags-ID**kopieren. Sie benötigen diese, um das Skript im nächsten Schritt auszuführen. Sie können das Skript auch über die Flyout-Seite herunterladen (oder es über den Link im nächsten Schritt herunterladen).

   Sie können auch auf **Bearbeiten** klicken, um die Azure-APP-ID oder die Namen der Spaltenüberschrift zu ändern, die Sie auf der Seite **Dateizuordnung** definiert haben.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Schritt 4: Ausführen des Beispielskripts zum Hochladen Ihrer HR-Daten

Der letzte Schritt beim Einrichten eines HR-Konnektors besteht darin, ein Beispielskript auszuführen, mit dem die HR-Daten in der CSV-Datei (die Sie in Schritt 2 erstellt haben) in die Microsoft-Cloud hochgeladen werden. Nachdem Sie das Skript ausgeführt haben, kann der in Schritt 3 erstellte HR-Konnektor auf die Daten in Ihrer Microsoft 365-Organisation zugreifen und diese importieren, wo Sie von anderen Compliance-Tools wie der Insider Risikomanagement-Lösung aufgerufen werden kann. Nachdem Sie das Skript ausgeführt haben, sollten Sie eine Aufgabe so planen, dass Sie täglich automatisch ausgeführt wird, damit die aktuellsten Mitarbeiter Terminierungsdaten in die Microsoft-Cloud hochgeladen werden. Siehe [Planen des automatischen Ausführens des Skripts](#optional-step-6-schedule-the-script-to-run-automatically).

1. Wechseln Sie zu [dieser GitHub-Website](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) , um auf das Beispielskript zuzugreifen.

2. Klicken Sie auf die Schaltfläche **RAW** , um das Skript in der Textansicht anzuzeigen.

3. Kopieren Sie alle Zeilen im Beispielskript, und speichern Sie Sie in einer Textdatei.

4. Ändern Sie bei Bedarf das Beispielskript für Ihre Organisation.

5. Speichern Sie die Textdatei als Windows PowerShell Skriptdatei unter Verwendung des `.ps1`Suffixes filename; Beispiel: `HRConnector.ps1`.

6. Öffnen Sie eine Eingabeaufforderung auf dem lokalen Computer, und wechseln Sie zu dem Verzeichnis, in dem Sie das Skript gespeichert haben.

7. Führen Sie den folgenden Befehl aus, um die HR-Daten in der CSV-Datei in die Microsoft-Cloud hochzuladen. Zum Beispiel:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   In der folgenden Tabelle werden die Parameter beschrieben, die mit diesem Skript verwendet werden sollen, sowie die erforderlichen Werte. Die Informationen, die Sie in den vorherigen Schritten erhalten haben, werden in den Werten für diese Parameter verwendet.

   |**Parameter**|**Beschreibung**
   |:-----|:-----|:-----|
   |`tenantId`|Dies ist die ID für Ihre Microsoft 365-Organisation, die Sie in Schritt 1 erhalten haben. Sie können die Mandanten-Nr für Ihre Organisation auch auf dem Blatt " **Übersicht** " im Azure AD Admin Center abrufen. Dies wird verwendet, um Ihre Organisation zu identifizieren.|
   |`appId` |Dies ist die Aad-Anwendungs-ID für die APP, die Sie in Schritt 1 in Azure AD erstellt haben. Dies wird von Azure AD für die Authentifizierung verwendet, wenn das Skript versucht, auf Ihre Microsoft 365-Organisation zuzugreifen. | 
   |`appSecret`|Dies ist der Aad-Anwendungsschlüssel für die APP, die Sie in Schritt 1 in Azure AD erstellt haben. Dies wird auch für die Authentifizierung verwendet.|
   |`jobId`|Dies ist die Auftrags-ID für den HR-Konnektor, den Sie in Schritt 3 erstellt haben. Dies wird verwendet, um die HR-Daten, die in die Microsoft-Cloud hochgeladen werden, mit dem HR-Connector zuzuordnen.|
   |`csvFilePath`|Dies ist der Dateipfad auf dem lokalen Computer (den Sie zum Ausführen des Skripts verwenden) für die CSV-Datei, die Sie in Schritt 2 erstellt haben. Wenn sich die CSV-Datei an einem freigegebenen Netzwerkspeicherort befindet, müssen Sie den vollständigen Dateipfad für diesen Speicherort angeben. Versuchen Sie, Leerzeichen im Dateipfad zu vermeiden; Verwenden Sie andernfalls einfache Anführungszeichen.|
   |||
   
   Im folgenden finden Sie ein Beispiel für die Syntax für das HR-Connector-Skript mit Istwerten für jeden Parameter:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Wenn der Upload erfolgreich war, zeigt das Skript die **erfolgreiche Nachricht hochladen** an.

## <a name="step-5-monitor-the-hr-connector"></a>Schritt 5: Überwachen des HR-Connectors

Nachdem Sie den HR-Connector erstellt und das Skript zum Hochladen Ihrer HR-Daten ausgeführt haben, können Sie den Connector-und den Uploadstatus im Microsoft 365 Compliance Center anzeigen. Wenn Sie planen, dass das Skriptregel mäßig automatisch ausgeführt wird, können Sie auch den aktuellen Status nach der letzten Ausführung des Skripts anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann den HF-Konnektor aus, um die Flyout-Seite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

   ![Flyoutseite "HR-Konnektor" mit Eigenschaften und Status](media/HRConnectorFlyout1.png)

3. Klicken Sie unter **Status**auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen über jedes Mal, wenn das Skript ausgeführt wird, und lädt die Daten aus der CSV-Datei in die Microsoft-Cloud hoch. 

   ![Protokolldatei des HR-Konnektors zeigt Nummern Zeilen aus der CSV-Datei an, die hochgeladen wurden](media/HRConnectorLogFile.png)

   Das Feld **RecordsSaved** gibt die Anzahl der Zeilen in der CSV-Datei an, die hochgeladen wurden. Wenn die CSV-Datei beispielsweise 4 Zeilen enthält, lautet der Wert der **RecordsSaved** -Felder 4, wenn das Skript alle Zeilen in der CSV-Datei erfolgreich hochgeladen hat.

Wenn Sie das Skript nicht in Schritt 4 ausgeführt haben, wird unter **Letzter Import**ein Link zum Herunterladen des Skripts angezeigt. Sie können das Skript herunterladen und dann die Schritte in Schritt 4 ausführen, um es auszuführen.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>Optional Schritt 6: Planen des automatischen Ausführens des Skripts

Um sicherzustellen, dass die neuesten HR-Daten aus Ihrer Organisation für Tools wie die Insider Risk Management-Lösung zur Verfügung stehen, wird empfohlen, das Skript automatisch regelmäßig zu planen, beispielsweise einmal täglich. Dies erfordert auch, dass Sie die HR-Daten in der CSV-Datei in einem ähnlichen (falls nicht identischen) Zeitplan aktualisieren, sodass Sie die neuesten Informationen zu Mitarbeitern enthält, die Ihre Organisation verlassen. Das Ziel besteht darin, die aktuellsten HR-Daten hochzuladen, sodass der HR-Connector diese für die Insider Risk Management-Lösung zur Verfügung stellen kann.

Sie können die Task Planer-app in Windows so ausführen, dass das Skript jeden Tag automatisch ausgeführt wird.

1. Klicken Sie auf dem lokalen Computer auf die Schaltfläche Windows- **Start** , und geben Sie dann **Aufgabenplaner**ein.

2. Klicken Sie auf die **Task Planer** -APP, um Sie zu öffnen.

3. Klicken Sie im Abschnitt **Aktionen** auf **Aufgabe erstellen**.

4. Geben Sie auf der Registerkarte **Allgemein** einen beschreibenden Namen für den geplanten Vorgang ein. Beispiel: **HR-Connector-Skript**. Sie können auch eine optionale Beschreibung hinzufügen. 

5. Führen Sie unter **Sicherheitsoptionen**die folgenden Aktionen aus:

   a. Bestimmen Sie, ob das Skript nur ausgeführt werden soll, wenn Sie am Computer angemeldet sind oder es ausführen, wenn Sie angemeldet sind oder nicht.
   
   b. Stellen Sie sicher, dass das Kontrollkästchen **mit den höchsten Rechten ausführen** aktiviert ist.

6. Wählen Sie die Registerkarte **Auslöser** aus, klicken Sie auf **neu**, und führen Sie dann die folgenden Schritte aus:

   a. Wählen Sie unter **Einstellungen**die Option **täglich** aus, und klicken Sie dann auf Datum und Uhrzeit, um das Skript zum ersten Mal auszuführen. Das Skript wird jeden Tag zur gleichen angegebenen Zeit.
   
   b. Stellen Sie unter **Erweiterte Einstellungen**sicher, dass das Kontrollkästchen **aktiviert** ausgewählt ist.
   
   c. Klicken Sie auf **OK**.

7. Wählen Sie die Registerkarte **Aktionen** aus, klicken Sie auf **neu**, und führen Sie dann die folgenden Schritte aus:

   ![Aktionseinstellungen zum Erstellen eines neuen geplanten Tasks für das HR-Connector-Skript](media/HRConnectorScheduleTask1.png)

   a. Stellen Sie in der Dropdownliste **Aktion** sicher, dass **Programm starten** ausgewählt ist.

   b. Klicken Sie im Feld **Programm/Skript** auf **Durchsuchen**, und wechseln Sie zum folgenden Speicherort, und wählen Sie ihn aus, damit der Pfad im `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe`Feld angezeigt wird:.

   c. Fügen Sie im Feld **Argumente hinzufügen (optional)** den gleichen Skriptbefehl ein, den Sie in Schritt 4 ausgeführt haben. Beispiel: `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   d. Fügen Sie im Feld **Start in (optional)** den Ordnerspeicherort des Skripts ein, das Sie in Schritt 4 ausgeführt haben. Beispiel: `C:\Users\contosoadmin\Desktop\Scripts`.

   e. Klicken Sie auf **OK** , um die Einstellungen für die neue Aktion zu speichern.

8. Klicken Sie im Fenster **Aufgaben erstellen** auf **OK** , um den geplanten Vorgang zu speichern. Möglicherweise werden Sie aufgefordert, Ihre Anmeldeinformationen für das Benutzerkonto einzugeben.

   Die neue Aufgabe wird in der Aufgabenplanungsbibliothek angezeigt.

   ![Die neue Aufgabe wird in der Aufgabenplanungsbibliothek angezeigt.](media/HRConnectorTaskSchedulerLibrary.png)

   Das letzte Mal und das nächste Mal, wenn das Skript ausgeführt wird, ist die Ausführung geplant wird angezeigt. Sie können auf den Vorgang doppelklicken, um ihn zu bearbeiten.

   Sie können auch überprüfen, wann das Skript zuletzt auf der Flyout-Seite des entsprechenden HR-Konnektors im Compliance Center ausgeführt wurde.
