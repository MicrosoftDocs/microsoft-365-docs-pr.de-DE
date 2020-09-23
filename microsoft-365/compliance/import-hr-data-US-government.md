---
title: Einrichten eines Connectors zum Importieren von HR-Daten in die US Government Cloud
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
ROBOTS: NOINDEX, NOFOLLOW
description: Administratoren in der US Government Cloud können einen Daten Konnektor einrichten, um Mitarbeiterdaten aus dem Personal System (HR) Ihrer Organisation nach Microsoft 365 zu importieren. Auf diese Weise können Sie Personaldaten in Richtlinien für das Insider Risikomanagement verwenden, um die Aktivität bestimmter Benutzer zu ermitteln, die eine interne Bedrohung für Ihre Organisation darstellen können.
ms.openlocfilehash: c1382cd94fcbba1d2ba561657c756e509af21dae
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196388"
---
# <a name="set-up-a-connector-to-import-hr-data-in-us-government"></a>Einrichten eines Connectors zum Importieren von HR-Daten in US Government

Sie können einen Daten Konnektor im Microsoft 365 Compliance Center einrichten, um Personalressourcen Daten in ihre US-Regierungsorganisation zu importieren. Zu den Personaldaten gehören das Datum, an dem ein Mitarbeiter seinen Rücktritt eingereicht hat, und das Datum des letzten Tages des Mitarbeiters. Diese HR-Daten können dann von Microsoft Information Protection-Lösungen wie der [Insider Risikomanagement-Lösung](insider-risk-management.md)verwendet werden, um Ihre Organisation vor böswilligen Aktivitäten oder Datendiebstahl in Ihrer Organisation zu schützen. Das Einrichten eines HR-Konnektors besteht darin, eine app in Azure Active Directory zu erstellen, die für die Authentifizierung über Connector verwendet wird, das Erstellen einer CSV-Zuordnungsdateien, die Ihre HR-Daten enthalten, das Erstellen eines datenkonnektors im Compliance Center und das anschließende Ausführen eines Skripts (geplant), das die HR-Daten in der CSV-Datei in die Microsoft-Cloud einnimmt. Anschließend wird der Data Connector vom Insider Risk Management-Tool verwendet, um auf die HR-Daten zuzugreifen, die in Ihre Microsoft 365 US Government-Organisation importiert wurden.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Ihre Organisation muss einwilligen, dass der Office 365-Import Dienst auf Daten in Ihrer Organisation zugreifen kann. Um dieser Anforderung zuzustimmen, gehen Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), melden Sie sich mit den Anmeldeinformationen eines globalen Administrators von Microsoft 365 an, und nehmen Sie dann die Anforderung an. Sie müssen diesen Schritt ausführen, bevor Sie den HR-Connector in Schritt 3 erfolgreich erstellen können.

- Dem Benutzer, der den HR-Connector in Schritt 3 erstellt, muss in Exchange Online die Rolle "Post Fach Import Export" zugewiesen sein. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine neue Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Sie müssen bestimmen, wie die Daten aus dem HR-System Ihrer Organisation (regelmäßig) abgerufen oder exportiert und der CSV-Datei hinzugefügt werden, die in Schritt 2 beschrieben wird. Mit dem in Schritt 4 ausgeführten Skript werden die HR-Daten in der CSV-Datei in die Microsoft-Cloud hochgeladen.

- Mit dem in Schritt 4 ausgeführten Beispielskript werden HR-Daten in die Microsoft-Cloud hochgeladen, sodass Sie von anderen Microsoft-Tools wie der Lösung für das Insider Risiko-Management verwendet werden können. Dieses Beispielskript wird unter keinem Microsoft Standard Support Programm oder-Dienst unterstützt. Das Beispielskript wird ohne jegliche Gewährleistung bereitgestellt. Microsoft schließt ferner alle konkludenten Gewährleistungen, einschließlich, aber nicht beschränkt auf konkludente Gewährleistungen der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Das gesamte Risiko, das aus der Verwendung oder der Leistung des Beispielskripts und der Dokumentation erwachsen, bleibt bei Ihnen. In keinem Fall sind Microsoft, seine Autoren oder an der Erstellung, Produktion oder Übermittlung der Skripts beteiligte Personen für Schäden jeglicher Art (einschließlich und ohne Einschränkung Schäden durch Verlust entgangener Gewinne, Geschäftsunterbrechungen, Verlust von Geschäftsinformationen oder andere geldliche Verluste) haftbar, die aus der Nutzung bzw. Unfähigkeit zur Nutzung der Beispielskripts oder Dokumentation entstehen, auch wenn Microsoft auf die Möglichkeit solcher Schäden hingewiesen wurde.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer APP in Azure Active Directory

Der erste Schritt besteht darin, eine neue app in Azure Active Directory (Azure AD) zu erstellen und zu registrieren. Die APP entspricht dem HR-Konnektor, den Sie in Schritt 3 erstellen. Durch das Erstellen dieser APP kann Azure AD den HR-Konnektor bei der Ausführung authentifizieren und versucht, auf Ihre Organisation zuzugreifen. Diese APP wird auch verwendet, um das Skript zu authentifizieren, das Sie in Schritt 4 ausführen, um Ihre HR-Daten in die Microsoft-Cloud hochzuladen. Achten Sie beim Erstellen dieser Azure AD-App darauf, die folgenden Informationen zu speichern. Diese Werte werden in späteren Schritten verwendet.

- Azure AD Anwendungs-ID (auch als *App-ID* oder *Client-ID*bezeichnet)

- Geheime Azure AD Anwendung (auch als *geheimer Client Schlüssel*bezeichnet)

- Mandanten-ID (auch als *Verzeichnis-ID*bezeichnet)

Eine Schritt-für-Schritt-Anleitung zum Erstellen einer APP in Azure AD finden Sie unter [Registrieren einer Anwendung mit der Microsoft Identity-Plattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a>Schritt 2: Vorbereiten einer CSV-Datei mit ihren HR-Daten

Der nächste Schritt besteht darin, eine CSV-Datei zu erstellen, die Informationen zu Mitarbeitern enthält, die Ihre Organisation verlassen haben. Wie im Abschnitt bevor Sie beginnen beschrieben, müssen Sie bestimmen, wie diese CSV-Datei aus dem HR-System Ihrer Organisation generiert wird. Das folgende Beispiel zeigt eine abgeschlossene CSV-Datei (in Notizblock geöffnet), die die drei erforderlichen Parameter (Spalten) enthält. Es ist viel einfacher, die CSV-Datei in Microsoft Excel zu bearbeiten.

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
| **TerminationDate** <br/> |Gibt das Datum an, an dem die Erwerbstätigkeit der Person in Ihrer Organisation offiziell gekündigt wurde. Dies kann beispielsweise das Datum sein, an dem der Mitarbeiter seine Nachricht über das verlassen Ihrer Organisation mitgeteilt hat. Dieses Datum kann unterschiedlich sein als das Datum des letzten Arbeitstags des Benutzers. Verwenden Sie das folgende Datumsformat: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , also das [ISO 8601-Format für Datum und Uhrzeit](https://www.iso.org/iso-8601-date-and-time-format.html).|
|**LastWorkingDate**|Gibt den letzten Tag der Arbeit für den terminierten Mitarbeiter an. Verwenden Sie das folgende Datumsformat: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , also das [ISO 8601-Format für Datum und Uhrzeit](https://www.iso.org/iso-8601-date-and-time-format.html).|
|||

Nachdem Sie die CSV-Datei mit den erforderlichen HR-Daten erstellt haben, speichern Sie Sie auf dem gleichen System wie das Skript, das Sie in Schritt 4 ausführen. Stellen Sie sicher, dass Sie eine Updatestrategie implementieren, damit die CSV-Datei immer die aktuellsten Informationen enthält. Dadurch wird sichergestellt, dass unabhängig von der Ausführung des Skripts die aktuellsten Mitarbeiter Terminierungsdaten in die Microsoft-Cloud hochgeladen werden.

## <a name="step-3-create-the-hr-connector"></a>Schritt 3: Erstellen des HR-Connectors

Im nächsten Schritt erstellen Sie einen HR-Connector im Microsoft 365 Compliance Center. Nachdem Sie das Skript in Schritt 4 ausgeführt haben, wird der von Ihnen erstellte HR-Konnektor die HR-Daten aus der CSV-Datei in Ihre Microsoft 365-Organisation aufnehmen. In diesem Schritt müssen Sie unbedingt die Auftrags-ID kopieren, die beim Erstellen des Connectors generiert wird. Sie verwenden die Auftrags-ID, wenn Sie das Skript ausführen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie dann im linken Navigationsbereich auf **Datenverbindungen** .

2. Klicken Sie auf der Seite **Daten Konnektoren** unter **HR**auf **Ansicht**.

3. Klicken Sie auf der Seite **HR** auf **Connector hinzufügen**.

4. Führen Sie auf der Seite **Authentifizierungsanmeldeinformationen** folgende Schritte aus, und klicken Sie dann auf **weiter**:

   a. Geben Sie die Azure AD Anwendungs-ID für die Azure-App ein, die Sie in Schritt 1 erstellt haben, oder fügen Sie Sie ein.

   b. Geben Sie einen Namen für den HR-Konnektor ein.

5. Geben Sie auf der Seite **Dateizuordnung** die Namen der drei Spaltenüberschriften (auch als *Parameter*bezeichnet) aus der CSV-Datei ein, die Sie in Schritt 2 in jedem der entsprechenden Felder erstellt haben. Bei den Namen wird die Groß-/Kleinschreibung nicht beachtet. Wie bereits erläutert, müssen die Namen, die Sie in diese Felder eingeben, mit den Parameternamen in der CSV-Datei übereinstimmen. Im folgenden Screenshot sind beispielsweise die Parameternamen aus dem Beispiel in der CSV-Beispieldatei in Schritt 2 dargestellt.

   ![Spaltenüberschrift Namen entsprechen denen in der CSV-Datei](../media/HRConnectorWizard3.png)

6. Überprüfen Sie die Einstellungen auf der Seite **überprüfen** , und klicken Sie dann auf **Fertig stellen** , um den Connector zu erstellen.

   Eine Statusseite wird angezeigt, die bestätigt, dass der Connector erstellt wurde. Diese Seite enthält zwei wichtige Dinge, die Sie für den nächsten Schritt zum Ausführen des Beispielskripts zum Hochladen Ihrer HR-Daten benötigen.

   ![Seite überprüfen mit Auftrags-ID und Link zu GitHub für Beispielskript](../media/HRConnector_Confirmation.png)

   a. **Auftrags-ID.** Sie benötigen diese Auftrags-ID, um das Skript im nächsten Schritt auszuführen. Sie können es von dieser Seite oder von der Flyout-Seite des Konnektors kopieren.
   
   b. **Link zum Beispielskript.** Klicken Sie auf den Link **hier** , um zur GitHub-Website zu wechseln, um auf das Beispielskript zuzugreifen (der Link öffnet ein neues Fenster). Lassen Sie dieses Fenster geöffnet, damit Sie das Skript in Schritt 4 kopieren können. Alternativ können Sie das Ziel mit einem Lesezeichen versehen oder die URL kopieren, damit Sie in Schritt 4 erneut darauf zugreifen können. Dieser Link steht auch auf der Seite "Connector-Flyout" zur Verfügung.

7. Klicken Sie auf **Fertig**.

   Der neue Connector wird in der Liste auf der Registerkarte **Connectors** angezeigt. 

8. Klicken Sie auf den soeben erstellten HR-Konnektor, um die Flyout-Seite anzuzeigen, die Eigenschaften und andere Informationen zum Connector enthält.

   ![Flyout-Seite für neuen HR-Connector](../media/HRConnectorWizard7.png)

   Wenn Sie dies nicht bereits getan haben, können Sie die Werte für die **Azure-APP-ID** und die **Connector-Auftrags-ID**kopieren. Sie benötigen diese, um das Skript im nächsten Schritt auszuführen. Sie können das Skript auch über die Flyout-Seite herunterladen (oder es über den Link im nächsten Schritt herunterladen).

   Sie können auch auf **Bearbeiten** klicken, um die Azure-APP-ID oder die Namen der Spaltenüberschrift zu ändern, die Sie auf der Seite **Dateizuordnung** definiert haben.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Schritt 4: Ausführen des Beispielskripts zum Hochladen Ihrer HR-Daten

Der letzte Schritt beim Einrichten eines HR-Konnektors besteht darin, ein Beispielskript auszuführen, mit dem die HR-Daten in der CSV-Datei (die Sie in Schritt 2 erstellt haben) in die Microsoft-Cloud hochgeladen werden. Das Skript lädt die Daten insbesondere in den HR-Konnektor hoch. Nachdem Sie das Skript ausgeführt haben, importiert der in Schritt 3 erstellte HR-Konnektor die HR-Daten in Ihre Microsoft 365-Organisation, in der der Zugriff über andere Compliance-Tools wie die Insider Risiko-Management Lösung möglich ist. Nachdem Sie das Skript ausgeführt haben, sollten Sie eine Aufgabe so planen, dass Sie täglich automatisch ausgeführt wird, damit die aktuellsten Mitarbeiter Terminierungsdaten in die Microsoft-Cloud hochgeladen werden. Siehe [Planen des automatischen Ausführens des Skripts](#optional-step-6-schedule-the-script-to-run-automatically).

1. Wechseln Sie zu Fenster, das Sie im vorherigen Schritt geöffnet haben, um mit dem Beispielskript auf die GitHub-Website zuzugreifen. Alternativ können Sie die mit einer Lesezeichen versehene Website öffnen oder die URL verwenden, die Sie kopiert haben.

2. Klicken Sie auf die Schaltfläche **RAW** , um das Skript in der Textansicht anzuzeigen.

3. Kopieren Sie alle Zeilen im Beispielskript, und speichern Sie Sie in einer Textdatei.

4. Ändern Sie bei Bedarf das Beispielskript für Ihre Organisation.

5. Speichern Sie die Textdatei als Windows PowerShell Skriptdatei unter Verwendung des Suffixes filename `.ps1` ; beispielsweise `HRConnector.ps1` .

6. Öffnen Sie eine Eingabeaufforderung auf dem lokalen Computer, und wechseln Sie zu dem Verzeichnis, in dem Sie das Skript gespeichert haben.

7. Führen Sie den folgenden Befehl aus, um die HR-Daten in der CSV-Datei in die Microsoft-Cloud hochzuladen. Zum Beispiel:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   In der folgenden Tabelle werden die Parameter beschrieben, die mit diesem Skript verwendet werden sollen, sowie die erforderlichen Werte. Die Informationen, die Sie in den vorherigen Schritten erhalten haben, werden in den Werten für diese Parameter verwendet.

   |**Parameter**|**Beschreibung**
   |:-----|:-----|:-----|
   |`tenantId`|Die ID für Ihre Microsoft 365-Organisation, die Sie in Schritt 1 erhalten haben. Sie können die Mandanten-ID für Ihre Organisation auch auf dem Blatt " **Übersicht** " im Azure AD Admin Center abrufen. Dies wird verwendet, um Ihre Organisation zu identifizieren.|
   |`appId` |Die Azure AD Anwendungs-ID für die APP, die Sie in Azure AD in Schritt 1 erstellt haben. Dies wird von Azure AD für die Authentifizierung verwendet, wenn das Skript versucht, auf Ihre Microsoft 365-Organisation zuzugreifen. |
   |`appSecret`|Der geheime Azure AD Anwendungsschlüssel für die APP, die Sie in Azure AD in Schritt 1 erstellt haben. Dies wird auch für die Authentifizierung verwendet.|
   |`jobId`|Die Auftrags-ID für den HR-Konnektor, den Sie in Schritt 3 erstellt haben. Dies wird verwendet, um die HR-Daten, die in die Microsoft-Cloud hochgeladen werden, mit dem HR-Connector zuzuordnen.|
   |`csvFilePath`|Der Dateipfad für die CSV-Datei (auf dem gleichen System wie das Skript gespeichert), die Sie in Schritt 2 erstellt haben. Versuchen Sie, Leerzeichen im Dateipfad zu vermeiden; Verwenden Sie andernfalls einfache Anführungszeichen.|
   |||
   
   Im folgenden finden Sie ein Beispiel für die Syntax für das HR-Connector-Skript mit Istwerten für jeden Parameter:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Wenn der Upload erfolgreich war, zeigt das Skript die **erfolgreiche Nachricht hochladen** an.

   > [!NOTE]
   > Wenn beim Ausführen des vorherigen Befehls aufgrund von Ausführungsrichtlinien Probleme aufgetreten sind, finden Sie unter [Informationen zu Ausführungs](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies) Richtlinien und zum [Festlegen von ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) Anleitungen zum Festlegen von Ausführungsrichtlinien.

## <a name="step-5-monitor-the-hr-connector"></a>Schritt 5: Überwachen des HR-Connectors

Nachdem Sie den HR-Connector erstellt und das Skript zum Hochladen Ihrer HR-Daten ausgeführt haben, können Sie den Connector-und den Uploadstatus im Microsoft 365 Compliance Center anzeigen. Wenn Sie planen, dass das Skriptregel mäßig automatisch ausgeführt wird, können Sie auch den aktuellen Status nach der letzten Ausführung des Skripts anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann den HF-Konnektor aus, um die Flyout-Seite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

   ![Flyoutseite "HR-Konnektor" mit Eigenschaften und Status](../media/HRConnectorFlyout1.png)

3. Klicken Sie unter **Status**auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen über jedes Mal, wenn das Skript ausgeführt wird, und lädt die Daten aus der CSV-Datei in die Microsoft-Cloud hoch. 

   ![Protokolldatei des HR-Konnektors zeigt Nummern Zeilen aus der CSV-Datei an, die hochgeladen wurden](../media/HRConnectorLogFile.png)

   Das `RecordsSaved` Feld gibt die Anzahl der Zeilen in der CSV-Datei an, die hochgeladen wurden. Wenn die CSV-Datei beispielsweise vier Zeilen enthält, lautet der Wert der `RecordsSaved` Felder 4, wenn das Skript alle Zeilen in der CSV-Datei erfolgreich hochgeladen hat.

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

   ![Aktionseinstellungen zum Erstellen eines neuen geplanten Tasks für das HR-Connector-Skript](../media/HRConnectorScheduleTask1.png)

   a. Stellen Sie in der Dropdownliste **Aktion** sicher, dass **Programm starten** ausgewählt ist.

   b. Klicken Sie im Feld **Programm/Skript** auf **Durchsuchen**, und wechseln Sie zum folgenden Speicherort, und wählen Sie ihn aus, damit der Pfad im Feld angezeigt wird: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` .

   c. Fügen Sie im Feld **Argumente hinzufügen (optional)** den gleichen Skriptbefehl ein, den Sie in Schritt 4 ausgeführt haben. Beispiel: `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   d. Fügen Sie im Feld **Start in (optional)** den Ordnerspeicherort des Skripts ein, das Sie in Schritt 4 ausgeführt haben. Beispiel: `C:\Users\contosoadmin\Desktop\Scripts`.

   e. Klicken Sie auf **OK** , um die Einstellungen für die neue Aktion zu speichern.

8. Klicken Sie im Fenster **Aufgaben erstellen** auf **OK** , um den geplanten Vorgang zu speichern. Möglicherweise werden Sie aufgefordert, Ihre Anmeldeinformationen für das Benutzerkonto einzugeben.

   Die neue Aufgabe wird in der Aufgabenplanungsbibliothek angezeigt.

   ![Die neue Aufgabe wird in der Aufgabenplanungsbibliothek angezeigt.](../media/HRConnectorTaskSchedulerLibrary.png)

   Die Uhrzeit, zu der das Skript zuletzt ausgeführt wurde, wird angezeigt, wenn das nächste Mal geplant wird. Sie können auf den Vorgang doppelklicken, um ihn zu bearbeiten.

   Sie können auch überprüfen, wann das Skript zuletzt auf der Flyout-Seite des entsprechenden HR-Konnektors im Compliance Center ausgeführt wurde.
