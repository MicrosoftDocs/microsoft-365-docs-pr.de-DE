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
description: Erfahren Sie mehr über grundlegende Schritte zur Problembehandlung, die Sie zum Beheben gängiger Probleme in eDiscovery Office 365 können.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3d3d0830ac677ea812a0d09793de8214245d6b2a
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52060990"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Untersuchen, Beheben und Beheben gängiger eDiscovery-Probleme

In diesem Thema werden grundlegende Schritte zur Problembehandlung behandelt, mit deren Hilfe Sie Probleme identifizieren und beheben können, die bei einer eDiscovery-Suche oder an anderer Stelle im eDiscovery-Prozess auftreten können. Die Lösung einiger dieser Szenarien erfordert Hilfe vom Microsoft-Support. Informationen dazu, wann Sie den Microsoft-Support kontaktieren, sind in den Lösungsschritten enthalten.

## <a name="errorissue-ambiguous-location"></a>Fehler/Problem: Mehrdeutiger Speicherort

Wenn Sie versuchen, den Postfachspeicherort des Benutzers zur Suche hinzuzufügen, und im Verzeichnis Exchange Online Protection (EOP) doppelte oder in Konflikt konfliktende Objekte mit derselben userID vorhanden sind, wird der fehler angezeigt: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Lösung

Suchen Sie nach doppelten Benutzern oder Verteilerlisten mit derselben Benutzer-ID.

1. Verbinden [security & Compliance Center PowerShell .](/powershell/exchange/connect-to-scc-powershell)

2. Führen Sie den folgenden Befehl aus, um alle Instanzen des Benutzernamens abzurufen:

    ```powershell
    Get-Recipient <username>
    ```

   Die Ausgabe für "useralias@contoso.com" würde der folgenden ähneln:

   > 
   > |Name|RecipientType|
   > |---|---|
   > |Alias, Benutzer|MailUser|
   > |Alias, Benutzer|Benutzer|

3. Wenn mehrere Benutzer zurückgegeben werden, suchen und beheben Sie das in Konflikt konfliktende Objekt.

## <a name="errorissue-search-fails-on-specific-locations"></a>Fehler/Problem: Suche schlägt an bestimmten Speicherorten fehl

Eine eDiscovery- oder Inhaltssuche kann den folgenden Fehler ergeben: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![Fehler screenshot des suchspezifischen Speicherorts](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Lösung

Wenn dieser Fehler angezeigt wird, wird empfohlen, dass Sie die Speicherorte überprüfen, die bei der Suche fehlgeschlagen sind, und dann die Suche nur an den fehlgeschlagenen Speicherorten erneut ausführen.

1. Verbinden [Security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Zeigen Sie in der PowerShell-Ausgabe die fehlgeschlagenen Speicherorte im Fehlerfeld oder in den Statusdetails im Fehler aus der Suchausgabe an.

3. Wiederholen Sie die eDiscovery-Suche nur an den fehlgeschlagenen Speicherorten.

4. Wenn Sie diese Fehler weiterhin erhalten, finden Sie weitere Schritte zur Problembehandlung unter [Wiederholen](/Office365/SecurityCompliance/retry-failed-content-search) fehlgeschlagener Speicherorte.

## <a name="errorissue-file-not-found"></a>Fehler/Problem: Datei nicht gefunden

Wenn Sie eine eDiscovery-Suche ausführen, die SharePoint Online- und One Drive For Business-Speicherorte enthält, wird möglicherweise der Fehler angezeigt, obwohl sich die Datei auf der `File Not Found` Website befindet. Dieser Fehler ist in den Exportwarnungen und errors.csv oder übersprungen items.csv. Dies kann auftreten, wenn die Datei nicht auf der Website gefunden werden kann oder der Index veraltet ist. Hier ist der Text eines tatsächlichen Fehlers (mit hinzugefügter Betonung).

> 28.06.2019 10:02:19_FailedToExportItem_Failed Inhalte herunterladen. Zusätzliche Diagnoseinformationen: Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Fehler beim Herunterladen von Inhalten 6ea52149-91cd-4965-b5bb-82ca6a3ec9be vom Typ Document. Korrelations-ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***Datei nicht gefunden***. bei Microsoft. SharePoint. Client.ClientRequest.ProcessResponseStream(Stream responseStream) bei Microsoft. SharePoint. Client.ClientRequest.ProcessResponse() --- Ende der inneren ---

### <a name="resolution"></a>Lösung

1. Überprüfen Sie den in der Suche identifizierten Speicherort, um sicherzustellen, dass der Speicherort der Datei korrekt ist und in den Suchspeicherorten hinzugefügt wird.

2. Verwenden Sie die Verfahren unter [Manuelles Anfordern](/sharepoint/crawl-site-content) der Durchforstung und erneuten Indizierung einer Website, Bibliothek oder Liste, um die Website neu zu indizieren.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Fehler/Problem: Suche schlägt fehl, weil der Empfänger nicht gefunden wurde

Bei einer eDiscovery-Suche tritt ein Fehler auf, der `recipient not found` . Dieser Fehler kann auftreten, wenn das Benutzerobjekt nicht in Exchange Online Protection (EOP) gefunden werden kann, da das Objekt nicht synchronisiert wurde.

### <a name="resolution"></a>Lösung

1. Stellen Sie eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) her.

2. Führen Sie den folgenden Befehl aus, um zu überprüfen, ob der Benutzer mit Exchange Online Protection:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Es sollte ein E-Mail-Benutzerobjekt für die Benutzerfrage sein. Wenn nichts zurückgegeben wird, untersuchen Sie das Benutzerobjekt. Wenden Sie sich an den Microsoft-Support, wenn das Objekt nicht synchronisiert werden kann.

## <a name="errorissue-exporting-search-results-is-slow"></a>Fehler/Problem: Das Exportieren von Suchergebnissen ist langsam

Beim Exportieren von Suchergebnissen aus eDiscovery oder Inhaltssuche im Security and Compliance Center dauert der Download länger als erwartet.  Sie können überprüfen, wie viele Daten heruntergeladen werden sollen, und möglicherweise die Exportgeschwindigkeit erhöhen.

### <a name="resolution"></a>Lösung

1. Verbinden [Security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Suchen Sie die Datenmenge, die in den Parametern SearchResults und SearchStatistics heruntergeladen werden soll.

3. Führen Sie den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. Suchen Sie im Ergebnisfeld nach den exportierten Daten, und zeigen Sie alle aufgetretenen Fehler an.

5. Überprüfen Sie die Datei trace.log im Verzeichnis, in das Sie den Inhalt exportiert haben, auf Fehler.

6. Wenn weiterhin Probleme auftreten, sollten Sie Suchen, die eine große Gruppe von Ergebnissen zurückgeben, in kleinere Suchen unterteilen. Beispielsweise können Sie Datumsbereiche in Suchabfragen verwenden, um einen kleineren Satz von Ergebnissen zurückzukehren, die schneller heruntergeladen werden können.

## <a name="errorissue-internal-server-error-500-occurred"></a>Fehler/Problem: "Interner Serverfehler (500) aufgetreten"

Wenn beim Ausführen einer eDiscovery-Suche der Fehler "Interner Serverfehler (500) aufgetreten" bei der Suche kontinuierlich fehlschlägt, müssen Sie die Suche möglicherweise nur an bestimmten Postfachspeicherorten erneut ausführen.

![Screenshot des internen Serverfehlers 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Lösung

1. Unterbrechen Sie die Suche in kleinere Suchen, und führen Sie die Suche erneut aus.  Versuchen Sie, einen kleineren Datumsbereich zu verwenden oder die Anzahl der durchsuchten Speicherorte zu begrenzen.

2. Verbinden [Security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Untersuchen Sie die Ausgabe auf Ergebnisse und Fehler.

4. Untersuchen Sie die datei trace.log. Sie befindet sich in dem Ordner, in den Sie die Suchergebnisse exportiert haben.

5. Wenden Sie sich an den Support von Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Fehler/Problem: Halte halte nicht synchronisiert

eDiscovery Case Hold Policy Sync Distribution Fehler. Der Fehler lautet:

> "Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet. Es kann weitere 2 Stunden dauern, um den endgültigen Bereitstellungsstatus zu aktualisieren. Überprüfen Sie daher in ein paar Stunden."

### <a name="resolution"></a>Lösung

1. Verbinden [security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl für eine eDiscovery-Fallaufbehebung aus:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Führen Sie für eine Aufbewahrungsrichtlinie den folgenden Befehl aus:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Untersuchen Sie den Wert im Parameter DistributionDetail auf Fehler wie die folgenden:

   > Fehler: Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet. Es kann weitere 2 Stunden dauern, um den endgültigen Bereitstellungsstatus zu aktualisieren. Überprüfen Sie daher in ein paar Stunden."

3. Führen Sie den Parameter RetryDistribution für die richtlinie aus:

   Für eDiscovery-Fälle gilt:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   Für Aufbewahrungsrichtlinien:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Wenden Sie sich an den Support von Microsoft.

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>Fehler: "Die bedingungsbedingte HTTP-Kopfzeile ist nicht erfüllt"

Beim Herunterladen von Suchergebnissen mithilfe des eDiscovery-Exporttools wird möglicherweise der folgende Fehler angezeigt: Dies ist ein vorübergehender Fehler, der in der Regel am Speicherort Azure Storage `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` wird.

### <a name="resolution"></a>Lösung

Um dieses Problem zu beheben, versuchen Sie es erneut, [die Suchergebnisse herunterzuladen,](export-search-results.md#step-2-download-the-search-results)wodurch das eDiscovery-Exporttool neu gestartet wird.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Fehler/Problem: Heruntergeladener Export zeigt keine Ergebnisse an

Nach einem erfolgreichen Export zeigt der abgeschlossene Download über das Exporttool keine Dateien in den Ergebnissen an.

### <a name="resolution"></a>Lösung

Dies ist ein clientseitiges Problem, und um es zu beheben, gehen Sie wie folgt vor:

1. Versuchen Sie, einen anderen Client/Computer zum Herunterladen zu verwenden.

2. Entfernen Sie alte Suchen, die nicht mehr benötigt werden, mithilfe des Cmdlets [Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch].

3. Stellen Sie sicher, dass Sie auf ein lokales Laufwerk herunterladen.

4. Stellen Sie sicher, dass der Virenscanner nicht ausgeführt wird.

5. Stellen Sie sicher, dass kein anderer Export in denselben Ordner oder übergeordneten Ordner heruntergeladen wird.

6. Wenn die vorherigen Schritte nicht funktioniert haben, deaktivieren Sie das Zipping und die Deduplizierung.

7. Wenn dies funktioniert, liegt das Problem an einem lokalen Virenscanner oder einem Datenträgerproblem.
