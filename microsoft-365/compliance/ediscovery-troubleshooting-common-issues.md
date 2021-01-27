---
title: Problembehandlung bei häufigen eDiscovery-Problemen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Erfahren Sie mehr über die grundlegenden Schritte zur Problembehandlung, die Sie ausführen können, um häufige Probleme in Office 365 eDiscovery zu beheben.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1fbda23b730956db42d8e7a92218fb9837868b8
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988139"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Untersuchen, Behandeln und Beheben häufiger eDiscovery-Probleme

In diesem Thema werden grundlegende Schritte zur Problembehandlung behandelt, die Sie ausführen können, um Probleme zu identifizieren und zu beheben, die während einer eDiscovery-Suche oder an anderer Stelle im eDiscovery-Prozess auftreten können. Um einige dieser Szenarien zu beheben, benötigen Sie Hilfe vom Microsoft-Support. Informationen dazu, wann Sie den Microsoft-Support kontaktieren können, sind in den Lösungsschritten enthalten.

## <a name="errorissue-ambiguous-location"></a>Fehler/Problem: Mehrdeutiger Speicherort

Wenn Sie versuchen, den Postfachspeicherort des Benutzers für die Suche hinzuzufügen, und es doppelte oder widersprüchliche Objekte mit derselben UserID im Exchange Online Protection (EOP)-Verzeichnis gibt, wird die fehlermeldung angezeigt: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Lösung

Suchen Sie nach doppelten Benutzern oder Verteilerlisten mit derselben Benutzer-ID.

1. Herstellen einer [Verbindung mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Führen Sie den folgenden Befehl aus, um alle Instanzen des Benutzernamens abzurufen:

    ```powershell
    Get-Recipient <username>
    ```

   Die Ausgabe für "useralias@contoso.com" würde etwa wie folgt sein:

   > 
   > |Name|RecipientType|
   > |---|---|
   > |Alias, Benutzer|MailUser|
   > |Alias, Benutzer|Benutzer|

3. Wenn mehrere Benutzer zurückgegeben werden, suchen sie das in Konflikt konfliktende Objekt, und beheben Sie es.

## <a name="errorissue-search-fails-on-specific-locations"></a>Fehler/Problem: Suche schlägt an bestimmten Speicherorten fehl

Eine eDiscovery- oder Inhaltssuche kann zu folgendem Fehler führen: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![Screenshot des Fehlers "Fehler" bei suchspezifischem Speicherort](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Lösung

Wenn diese Fehlermeldung angezeigt wird, sollten Sie die Speicherorte überprüfen, die bei der Suche fehlgeschlagen sind, und dann die Suche nur für die fehlgeschlagenen Speicherorte erneut ausführen.

1. Stellen Sie [eine Verbindung & Security & Compliance Center PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Zeigen Sie in der PowerShell-Ausgabe die fehlgeschlagenen Speicherorte im Fehlerfeld oder aus den Statusdetails im Fehler aus der Suchausgabe an.

3. Wiederholen Sie die eDiscovery-Suche nur an den fehlgeschlagenen Speicherorten.

4. Wenn Sie diese Fehler weiterhin erhalten, finden Sie unter "Wiederholen fehlgeschlagener [Speicherorte"](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) weitere Schritte zur Problembehandlung.

## <a name="errorissue-file-not-found"></a>Fehler/Problem: Datei nicht gefunden

Wenn Sie eine eDiscovery-Suche ausführen, die SharePoint Online- und One Drive for Business-Speicherorte umfasst, wird möglicherweise die Fehlermeldung angezeigt, obwohl sich die Datei auf `File Not Found` der Website befindet. Dieser Fehler wird in den Exportwarnungen angezeigt und errors.csv oder übersprungen items.csv. Dies kann vorkommen, wenn die Datei auf der Website nicht gefunden werden kann oder wenn der Index veraltet ist. Hier ist der Text eines tatsächlichen Fehlers (mit hinzugefügter Betonung).

> 28.06.2019 10:02:19_FailedToExportItem_Failed inhalte herunterladen. Zusätzliche Diagnoseinformationen: Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Fehler beim Herunterladen von Inhalt 6ea52149-91cd-4965-b5bb-82ca6a3ec9be vom Typ "Document". Korrelations-ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***Datei nicht gefunden***. at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---

### <a name="resolution"></a>Lösung

1. Überprüfen Sie den in der Suche identifizierten Speicherort, um sicherzustellen, dass der Speicherort der Datei korrekt ist und in den Suchspeicherorten hinzugefügt wird.

2. Verwenden Sie die Verfahren unter [Manuelles Anfordern der Durchforstung](https://docs.microsoft.com/sharepoint/crawl-site-content) und erneuten Indizierung einer Website, einer Bibliothek oder einer Liste, um die Website neu zu indizieren.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Fehler/Problem: Suche schlägt fehl, weil der Empfänger nicht gefunden wurde

Bei einer eDiscovery-Suche tritt ein Fehler auf. `recipient not found` Dieser Fehler kann auftreten, wenn das Benutzerobjekt in Exchange Online Protection (EOP) nicht gefunden werden kann, da das Objekt nicht synchronisiert wurde.

### <a name="resolution"></a>Lösung

1. Stellen Sie eine Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) her.

2. Führen Sie den folgenden Befehl aus, um zu überprüfen, ob der Benutzer mit Exchange Online Protection synchronisiert ist:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Es sollte ein E-Mail-Benutzerobjekt für die Frage des Benutzers sein. Wenn nichts zurückgegeben wird, untersuchen Sie das Benutzerobjekt. Wenden Sie sich an den Microsoft-Support, wenn das Objekt nicht synchronisiert werden kann.

## <a name="errorissue-exporting-search-results-is-slow"></a>Fehler/Problem: Das Exportieren von Suchergebnissen ist langsam

Beim Exportieren von Suchergebnissen aus eDiscovery oder der Inhaltssuche im Security and Compliance Center dauert der Download länger als erwartet.  Sie können überprüfen, wie viele Daten heruntergeladen werden sollen, und die Exportgeschwindigkeit erhöhen.

### <a name="resolution"></a>Lösung

1. Stellen Sie [eine Verbindung & Security & Compliance Center PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Suchen Sie die Menge der Daten, die in den Parametern "SearchResults" und "SearchStatistics" heruntergeladen werden sollen.

3. Führen Sie den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. Suchen Sie im Ergebnisfeld nach den exportierten Daten, und zeigen Sie alle aufgetretenen Fehler an.

5. Überprüfen Sie die Datei "trace.log" im Verzeichnis, in das Sie den Inhalt exportiert haben, auf Fehler.

6. Wenn weiterhin Probleme auftreten, sollten Sie Suchen, die eine große Menge von Ergebnissen zurückgeben, in kleinere Suchen aufteilen. Beispielsweise können Sie Datumsbereiche in Suchabfragen verwenden, um eine kleinere Gruppe von Ergebnissen zurückzukehren, die schneller heruntergeladen werden können.

## <a name="errorissue-internal-server-error-500-occurred"></a>Fehler/Problem: "Interner Serverfehler (500) aufgetreten"

Wenn beim Ausführen einer eDiscovery-Suche die Suche ständig mit einem Fehler wie "Interner Serverfehler (500) aufgetreten" fehlschlägt, müssen Sie die Suche möglicherweise nur an bestimmten Postfachspeicherorten erneut ausführen.

![Screenshot des internen Serverfehlers 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Lösung

1. Unterbrechen Sie die Suche in kleinere Suchen, und führen Sie die Suche erneut aus.  Versuchen Sie, einen kleineren Datumsbereich zu verwenden oder die Anzahl der durchsuchten Speicherorte zu begrenzen.

2. Stellen Sie [eine Verbindung & Security & Compliance Center PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Untersuchen Sie die Ausgabe auf Ergebnisse und Fehler.

4. Überprüfen Sie die Datei "trace.log". Sie befindet sich in demselben Ordner, in den Sie die Suchergebnisse exportiert haben.

5. Wenden Sie sich an den Support von Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Fehler/Problem: Halte halte nicht synchronisiert

eDiscovery Case Hold Policy Sync Distribution error. Der Fehler lautet:

> "Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet. Es kann weitere 2 Stunden dauern, bis der endgültige Bereitstellungsstatus aktualisiert wurde. Checken Sie daher in ein paar Stunden zurück."

### <a name="resolution"></a>Lösung

1. Stellen Sie [eine Verbindung & Security & Compliance Center PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl für ein eDiscovery-Fall-Hold aus:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Führen Sie für eine Aufbewahrungsrichtlinie den folgenden Befehl aus:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Untersuchen Sie den Wert im Parameter "DistributionDetail" auf Fehler wie die folgenden:

   > Fehler: Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet. Es kann weitere 2 Stunden dauern, bis der endgültige Bereitstellungsstatus aktualisiert wurde. Checken Sie daher in ein paar Stunden zurück."

3. Führen Sie den Parameter "RetryDistribution" für die richtlinie aus:

   Für eDiscovery-Fall-Halte halte:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   Für Aufbewahrungsrichtlinien:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Wenden Sie sich an den Support von Microsoft.

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>Fehler: "Die mit bedingten HTTP-Headern angegebene Bedingung wird nicht erfüllt."

Beim Herunterladen von Suchergebnissen mit dem eDiscovery-Exporttool wird möglicherweise der folgende Fehler angezeigt: Dies ist ein vorübergehender Fehler, der in der Regel am `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure Storage-Speicherort auftritt.

### <a name="resolution"></a>Lösung

Um dieses Problem zu beheben, versuchen Sie erneut, die [Suchergebnisse herunterzuladen,](export-search-results.md#step-2-download-the-search-results)wodurch das eDiscovery-Exporttool neu gestartet wird.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Fehler/Problem: Heruntergeladener Export zeigt keine Ergebnisse an

Nach einem erfolgreichen Export zeigt der abgeschlossene Download über das Exporttool keine Dateien in den Ergebnissen an.

### <a name="resolution"></a>Lösung

Dies ist ein clientseitiges Problem, und um dieses Problem zu beheben, versuchen Sie die folgenden Schritte:

1. Versuchen Sie, einen anderen Client/Computer zum Herunterladen zu verwenden.

2. Stellen Sie sicher, dass sie auf ein lokales Laufwerk heruntergeladen werden.

3. Stellen Sie sicher, dass der Virenscanner nicht ausgeführt wird.

4. Stellen Sie sicher, dass kein anderer Export in denselben Ordner oder einen übergeordneten Ordner heruntergeladen wird.

5. Wenn die vorherigen Schritte nicht funktioniert haben, deaktivieren Sie zipping und Deduplizierung.

6. Wenn dies funktioniert, liegt das Problem an einem lokalen Virenscanner oder einem Datenträgerproblem.
