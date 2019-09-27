---
title: Troublshooting häufige eDiscovery-Probleme
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Untersuchen, beheben und beheben Sie häufige Probleme in Office 365 eDiscovery.
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207292"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Untersuchen, beheben und Beheben allgemeiner eDiscovery-Probleme

In diesem Thema werden grundlegende Schritte zur Problembehandlung beschrieben, die Sie zum Identifizieren und Beheben von Problemen durchführen können, die während einer eDiscovery-Suche oder an einer anderen Stelle im eDiscovery-Prozess auftreten können. Zum Beheben einiger dieser Szenarien benötigen Sie Hilfe von den Kunden Support Diensten (CSS). Informationen zum Zeitpunkt der Kontaktaufnahme mit CSS sind in den Lösungsschritten enthalten.

## <a name="errorissue-ambiguous-location"></a>Fehler/Problem-mehrdeutiger Speicherort

Dieser Fehler wird angezeigt "die kompatibilitätssuche enthält den folgenden ungültigen `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` Speicherort, wenn Sie versucht haben, den Postfachspeicherort des Benutzers zur Suche hinzuzufügen, und es gibt doppelte oder widersprüchliche Objekte mit derselben Benutzer-ID im Exchange Online Schutz (EoP). Directory.

### <a name="resolution"></a>Auflösung

Suchen Sie nach doppelten Benutzern oder Verteilerlisten mit derselben Benutzer-ID.

1. Stellen Sie eine Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) her.
2. Rufen Sie alle Instanzen des Benutzernamens ab, und geben Sie Folgendes ein:

```powershell
Get-Recipient <username>
```

Die Ausgabe für "useralias@contoso.com" kann

> 
> |Name  |RecipientType  |
> |---------|---------|
> |Alias, Benutzer     |MailUser         |
> |Alias, Benutzer     |Benutzer         |

3. Wenn mehrere Benutzer zurückgegeben werden, suchen und beheben Sie das Konflikt verursachende Objekt.

## <a name="errorissue-search-fails-on-specific-locations"></a>Fehler/Problemsuche an bestimmten Speicherorten fehlgeschlagen

Eine eDiscovery-oder Inhaltssuche kann den folgenden Fehler ergeben:
>Diese Suche wurde mit (#) Fehlern abgeschlossen.  Möchten Sie die Suche an den fehlgeschlagenen Speicherorten wiederholen?

![Screenshot der suchspezifischen Position fails Fehler]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Auflösung

Wenn dieser Fehler auftritt, wird empfohlen, dass Sie die Speicherorte überprüfen, bei denen die Suche fehlgeschlagen ist, und führen Sie die Suche dann nur für die fehlerhaften Speicherorte erneut aus.

1. Stellen Sie eine Verbindung mit [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)her.
1. Typ:

```powershell
Get-Compliancesearch searchname|fl 
```

3. Zeigen Sie in der PowerShell-Ausgabe die fehlerhaften Speicherorte im Feld Fehler oder von den Statusdetails in dem Fehler aus der Suchausgabe an.
1. Wiederholen Sie die eDiscovery-Suche nur auf den fehlerhaften Speicherorten.
1. Wenn diese Fehlermeldung weiterhin angezeigt wird, finden Sie weitere Informationen zur Problembehandlung unter wieder [holen fehlgeschlagener Speicherorte](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) .

## <a name="errorissue-file-not-found"></a>Fehler/Problem Datei nicht gefunden

Wenn Sie eine eDiscovery-Suche durchführen, die SharePoint Online und ein Laufwerk für Geschäftsstandorte enthält, wird `File Not Found` möglicherweise die Fehlermeldung angezeigt, obwohl sich die Datei auf der Website befindet. Dieser Fehler tritt in den Export Warnungen und Errors. CSV oder Skipped Items. CSV auf, wenn die Datei nicht auf der Website gefunden werden kann oder der Index veraltet ist. Hier ist der Text eines tatsächlichen Fehlers, wobei der Schwerpunkt hinzugefügt wurde.
  
> 28.06.2019 10:02:19_FailedToExportItem_Failed zum Herunterladen von Inhalten. Zusätzliche Diagnoseinformationen: Microsoft. Office. Compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: Fehler beim Herunterladen aus dem Inhalts 6ea52149-91cd-4965-b5bb-82ca6a3ec9be vom Typ Document. Korrelations-ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode:-2147024894---#a0 Microsoft. SharePoint. Client. ServerException: die ***Datei wurde nicht gefunden***. unter Microsoft. SharePoint. Client. ClientRequest. ProcessResponseStream (Stream responseStream) unter Microsoft. SharePoint. Client. ClientRequest. ProcessResponse ()---Ende der internen Ausnahmestapelüberwachung---

### <a name="resolution"></a>Auflösung

1. Überprüfen Sie die in der Suche identifizierte Position, um sicherzustellen, dass der Speicherort der Datei richtig ist und an den Suchpfaden hinzugefügt wurde.
2. Verwenden Sie die Verfahren unter [Manuelles anfordern des Durchforstens und erneuten Indizierens einer Website, einer Bibliothek oder einer Liste](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) zum erneuten Indizieren der Website.

## <a name="errorissue-search-fails-recipient-not-found"></a>Fehler/Problemsuche fehlgeschlagen Empfänger nicht gefunden

die eDiscovery-Suche schlägt `recipient not found`fehl mit dem Fehler. Dieser Fehler kann auftreten, wenn das Benutzerobjekt in Exchange Online Protection (EoP) nicht gefunden werden kann, da das Objekt nicht synchronisiert wurde.

### <a name="resolution"></a>Auflösung

1. Stellen Sie eine Verbindung mit [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)her.
1. Überprüfen Sie, ob das Benutzerobjekt mit Exchange Online Schutztyp synchronisiert ist:

```powershell
Get-Recipient userId|fl
```

3. Es sollte ein MailUser-Objekt für die Benutzerfrage geben. Wenn Nothing zurückgegeben wird, überprüfen Sie das User-Objekt. Wenden Sie sich an CSS, wenn das Objekt nicht synchronisiert werden kann.

## <a name="errorissue-exporting-search-results-is-slow"></a>Fehler/Problem beim Exportieren der Suchergebnisse ist langsam

Beim Exportieren von Suchergebnissen aus der eDiscovery-oder Inhaltssuche im Security and Compliance Center dauert der Download länger als erwartet.  Sie können überprüfen, ob die Datenmenge heruntergeladen und möglicherweise die Exportgeschwindigkeit erhöht werden soll.

### <a name="resolution"></a>Auflösung

1.  Versuchen Sie es mit den Schritten im Artikel [increase Download speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).
2.  Wenn Sie weiterhin Probleme haben, stellen Sie eine Verbindung mit [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) her, und geben Sie Folgendes ein:

```powershell
Get-ComplianceSearch searchname\fl
```

4. Ermitteln Sie die Menge der Daten, die in den searchresults-und SearchStatistics-Parametern heruntergeladen werden sollen.
5. Typ:

```powershell
Get-ComplianceSearchAction |fl
```

6. Suchen Sie im Feld Ergebnisse die Daten, die exportiert wurden, und zeigen Sie alle aufgetretenen Fehler an.
7. Überprüfen Sie die Datei Trace. log, die sich in dem Verzeichnis befindet, in das Sie den Inhalt exportiert haben, auf Fehler.

## <a name="errorissue-internal-server-error-500-occurred"></a>Fehler/Problem "Interner Serverfehler (500) aufgetreten"

Wenn eine eDiscovery-Suche ausgeführt wird und die Suche kontinuierlich fehlschlägt und Fehler wie "Internal Server Error (500)" aufgetreten sind, müssen Sie die Suche möglicherweise nur an bestimmten Postfachspeicher Orten erneut ausführen.

![Interner Serverfehler 500 Screenshot](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Auflösung

1. Unterbrechen Sie die Suche in kleinere suchen, und führen Sie die Suche erneut aus.  Versuchen Sie, einen kleineren Datumsbereich zu verwenden oder die Anzahl der durchsuchten Speicherorte zu begrenzen.
2. Stellen Sie eine Verbindung mit [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) her und geben Sie Folgendes ein:

```powershell
Get-ComplianceSearch searchname |fl
```

3. Überprüfen Sie die Ausgabe auf Ergebnisse und Fehler.
3. Überprüfen Sie die Datei Trace. log. Es befindet sich in demselben Ordner, an den Sie den Export gesendet haben.
4. Wenden Sie sich an den Support CSS.

## <a name="errorissue-holds-dont-sync"></a>Fehler/Problem hält nicht synchronisiert

eDiscovery Case Hold Policy Sync-Verteilungsfehler. Der Fehler lautet:

> "Ressourcen: die Bereitstellung der Richtlinie dauert länger als erwartet. Es kann weitere zwei Stunden dauern, bis der endgültige Bereitstellungsstatus aktualisiert wurde, daher sollten Sie sich in ein paar Stunden wieder einfinden. "

### <a name="resolution"></a>Auflösung

1.  Stellen Sie eine Verbindung mit [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) her und geben Sie Folgendes ein:

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. Überprüfen Sie den Wert im Parameter Distributiondetail auf Fehler wie die folgenden:

> Wenn ein Fehler vorliegt, erstellen Sie eine Eskalation an PG, um eine manuelle erneute Synchronisierung für die Richtlinie zu erzwingen.

3. Wenden Sie sich an CSS.

## <a name="see-also"></a>Siehe auch
- [Tipps zum Vermeiden von Inhaltsspeicherort Fehlern](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)