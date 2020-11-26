---
title: Problembehandlung bei gängigen eDiscovery-Problemen
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
description: Erfahren Sie mehr über die grundlegenden Schritte zur Problembehandlung, die Sie zur Lösung häufig auftretender Probleme in Office 365 eDiscovery ausführen können.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a2db7fac04f29587f451b8feff5b641624e0cf45
ms.sourcegitcommit: 8ad481ed61cb6dabf8afb0fb04296666fa166450
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49422864"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Untersuchen, beheben und Beheben allgemeiner eDiscovery-Probleme

In diesem Thema werden grundlegende Schritte zur Problembehandlung beschrieben, die Sie zum Identifizieren und Beheben von Problemen durchführen können, die während einer eDiscovery-Suche oder an einer anderen Stelle im eDiscovery-Prozess auftreten können. Das Auflösen einiger dieser Szenarien erfordert Unterstützung durch den Microsoft-Support. Die Lösungsschritte enthalten Informationen zum Zeitpunkt der Kontaktaufnahme mit dem Microsoft-Support.

## <a name="errorissue-ambiguous-location"></a>Fehler/Problem: nicht eindeutiger Speicherort

Wenn Sie versuchen, den Postfachspeicherort des Benutzers zur Suche hinzuzufügen, und es sich um doppelte oder widersprüchliche Objekte mit derselben UserID im Verzeichnis Exchange Online Protection (EoP) handelt, wird dieser Fehler angezeigt: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Lösung

Suchen Sie nach doppelten Benutzern oder Verteilerlisten mit derselben Benutzer-ID.

1. Stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)her.

2. Führen Sie den folgenden Befehl aus, um alle Instanzen des Benutzernamens abzurufen:

    ```powershell
    Get-Recipient <username>
    ```

   Die Ausgabe für "useralias@contoso.com" würde etwa wie folgt aussehen:

   > 
   > |Name|RecipientType|
   > |---|---|
   > |Alias, Benutzer|MailUser|
   > |Alias, Benutzer|Benutzer|

3. Wenn mehrere Benutzer zurückgegeben werden, suchen und beheben Sie das Konflikt verursachende Objekt.

## <a name="errorissue-search-fails-on-specific-locations"></a>Fehler/Problem: Suchfehler an bestimmten Speicherorten

Eine eDiscovery-oder Inhaltssuche kann den folgenden Fehler ergeben:
>Diese Suche wurde mit (#) Fehlern abgeschlossen.  Möchten Sie die Suche an den fehlgeschlagenen Speicherorten wiederholen?

![Screenshot der suchspezifischen Speicherort Fehler](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Lösung

Wenn Sie diesen Fehler erhalten, wird empfohlen, dass Sie die Speicherorte überprüfen, die bei der Suche fehlgeschlagen sind, und die Suche dann nur für die fehlerhaften Speicherorte erneut ausführen.

1. Stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) her, und führen Sie dann den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Zeigen Sie in der PowerShell-Ausgabe die fehlerhaften Speicherorte im Feld Fehler oder von den Statusdetails in dem Fehler aus der Suchausgabe an.

3. Wiederholen Sie die eDiscovery-Suche nur auf den fehlerhaften Speicherorten.

4. Wenn Sie diese Fehler weiterhin erhalten, finden Sie weitere Informationen zur Problembehandlung unter wieder [holen fehlgeschlagener Speicherorte](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) .

## <a name="errorissue-file-not-found"></a>Fehler/Problem: Datei nicht gefunden

Wenn Sie eine eDiscovery-Suche durchführen, die SharePoint Online und ein Laufwerk für Geschäftsstandorte enthält, wird möglicherweise die Fehlermeldung angezeigt, `File Not Found` Obwohl sich die Datei auf der Website befindet. Dieser Fehler tritt in den Export Warnungen und-errors.csv auf oder wird übersprungen items.csv. Dies kann vorkommen, wenn die Datei nicht auf der Website gefunden werden kann oder wenn der Index veraltet ist. Hier ist der Text eines tatsächlichen Fehlers (mit Nachdruck hinzugefügt).

> 28.06.2019 10:02:19_FailedToExportItem_Failed zum Herunterladen von Inhalten. Zusätzliche Diagnoseinformationen: Microsoft. Office. Compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: Fehler beim Herunterladen aus dem Inhalts 6ea52149-91cd-4965-b5bb-82ca6a3ec9be vom Typ Document. Korrelations-ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode:-2147024894---> Microsoft. SharePoint. Client. ServerException: die ***Datei wurde nicht gefunden***. unter Microsoft. SharePoint. Client. ClientRequest. ProcessResponseStream (Stream responseStream) unter Microsoft. SharePoint. Client. ClientRequest. ProcessResponse ()---Ende der internen Ausnahmestapelüberwachung---

### <a name="resolution"></a>Lösung

1. Überprüfen Sie die in der Suche identifizierte Position, um sicherzustellen, dass der Speicherort der Datei richtig ist und an den Suchpfaden hinzugefügt wurde.

2. Verwenden Sie die Verfahren unter [Manuelles anfordern des Durchforstens und erneuten Indizierens einer Website, einer Bibliothek oder einer Liste](https://docs.microsoft.com/sharepoint/crawl-site-content) zum Neuindizieren der Website.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Fehler/Problem: die Suche schlägt fehl, da der Empfänger nicht gefunden wurde.

Bei einer eDiscovery-Suche tritt ein Fehler auf `recipient not found` . Dieser Fehler kann auftreten, wenn das Benutzerobjekt in Exchange Online Protection (EoP) nicht gefunden werden kann, da das Objekt nicht synchronisiert wurde.

### <a name="resolution"></a>Lösung

1. Stellen Sie eine Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) her.

2. Führen Sie den folgenden Befehl aus, um zu überprüfen, ob der Benutzer mit Exchange Online Schutz synchronisiert ist:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Es sollte ein e-Mail-Benutzerobjekt für die Benutzerfrage geben. Wenn Nothing zurückgegeben wird, überprüfen Sie das User-Objekt. Wenden Sie sich an den Microsoft-Support, wenn das Objekt nicht synchronisiert werden kann.

## <a name="errorissue-exporting-search-results-is-slow"></a>Fehler/Problem: das Exportieren von Suchergebnissen ist langsam

Beim Exportieren von Suchergebnissen aus der eDiscovery-oder Inhaltssuche im Security and Compliance Center dauert der Download länger als erwartet.  Sie können überprüfen, ob die Datenmenge heruntergeladen und möglicherweise die Exportgeschwindigkeit erhöht werden soll.

### <a name="resolution"></a>Lösung

1. Stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) her, und führen Sie dann den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Ermitteln Sie die Menge der Daten, die in den searchresults-und SearchStatistics-Parametern heruntergeladen werden sollen.

3. Führen Sie den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. Suchen Sie im Feld Ergebnisse die Daten, die exportiert wurden, und zeigen Sie alle aufgetretenen Fehler an.

5. Überprüfen Sie die Datei Trace. log, die sich in dem Verzeichnis befindet, in das Sie den Inhalt exportiert haben, auf Fehler.

6. Wenn Sie weiterhin Probleme haben, sollten Sie die Suche teilen, die eine große Gruppe von Ergebnissen in kleinere suchen zurückgeben. Beispielsweise können Sie Datumsbereiche in Suchabfragen verwenden, um einen kleineren Datensatz von Ergebnissen zurückzugeben, die schneller heruntergeladen werden können.

## <a name="errorissue-internal-server-error-500-occurred"></a>Fehler/Problem: "Interner Serverfehler (500) aufgetreten"

Wenn eine eDiscovery-Suche ausgeführt wird und die Suche kontinuierlich fehlschlägt und Fehler wie "Internal Server Error (500)" aufgetreten sind, müssen Sie die Suche möglicherweise nur an bestimmten Postfachspeicher Orten erneut ausführen.

![Interner Serverfehler 500 Screenshot](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Lösung

1. Unterbrechen Sie die Suche in kleinere suchen, und führen Sie die Suche erneut aus.  Versuchen Sie, einen kleineren Datumsbereich zu verwenden oder die Anzahl der durchsuchten Speicherorte zu begrenzen.

2. Stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) her, und führen Sie dann den folgenden Befehl aus:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Überprüfen Sie die Ausgabe auf Ergebnisse und Fehler.

4. Überprüfen Sie die Datei Trace. log. Sie befindet sich im gleichen Ordner, in den Sie die Suchergebnisse exportiert haben.

5. Wenden Sie sich an den Support von Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Fehler/Problem: hält keine Synchronisierung

eDiscovery Case Hold Policy Sync-Verteilungsfehler. Der Fehler lautet:

> "Ressourcen: die Bereitstellung der Richtlinie dauert länger als erwartet. Es kann weitere 2 Stunden dauern, bis Sie den endgültigen Bereitstellungsstatus aktualisiert haben, also schauen Sie sich in ein paar Stunden zurück. "

### <a name="resolution"></a>Lösung

1. Stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) her, und führen Sie dann den folgenden Befehl für einen eDiscovery-Aufbewahrungs Fall aus:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Führen Sie für eine Aufbewahrungsrichtlinie den folgenden Befehl aus:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Überprüfen Sie den Wert im Parameter DistributionDetail auf Fehler wie die folgenden:

   > Fehler: Ressourcen: die Bereitstellung der Richtlinie dauert länger als erwartet. Es kann weitere 2 Stunden dauern, bis Sie den endgültigen Bereitstellungsstatus aktualisiert haben, also schauen Sie sich in ein paar Stunden zurück. "

3. Versuchen Sie, den RetryDistribution-Parameter für die betreffende Richtlinie auszuführen:

   Für eDiscovery Case Holds:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   Für Aufbewahrungsrichtlinien:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Wenden Sie sich an den Support von Microsoft.

## <a name="see-also"></a>Siehe auch

- [Tipps zum Vermeiden von Inhaltsspeicherort Fehlern](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
