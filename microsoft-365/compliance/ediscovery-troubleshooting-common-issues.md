---
title: Behandeln allgemeiner eDiscovery-Probleme
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
description: Erfahren Sie mehr über grundlegende Schritte zur Problembehandlung, die Sie ausführen können, um allgemeine Probleme in Office 365 eDiscovery zu beheben.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 26ca41774e1e09619fdf5e518258f8acf3a9d938
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809119"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Untersuchen, Beheben und Beheben allgemeiner eDiscovery-Probleme

In diesem Thema werden grundlegende Schritte zur Problembehandlung behandelt, die Sie ausführen können, um Probleme zu identifizieren und zu beheben, die während einer eDiscovery-Suche oder an anderer Stelle im eDiscovery-Prozess auftreten können. Die Lösung einiger dieser Szenarien erfordert Hilfe vom Microsoft-Support. Informationen dazu, wann Sie den Microsoft-Support kontaktieren können, sind in den Lösungsschritten enthalten.

## <a name="errorissue-ambiguous-location"></a>Fehler/Problem: Mehrdeutiger Speicherort

Wenn Sie versuchen, den Postfachspeicherort des Benutzers zur Suche hinzuzufügen, und es doppelte oder in Konflikt stehende Objekte mit derselben Benutzer-ID im Verzeichnis Exchange Online Protection (EOP) gibt, wird der folgende Fehler angezeigt: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Lösung

Suchen Sie nach doppelten Benutzern oder Verteilerlisten mit derselben Benutzer-ID.

1. Verbinden zu [Security & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)

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

3. Wenn mehrere Benutzer zurückgegeben werden, suchen Sie das in Konflikt stehende Objekt, und beheben Sie es.

## <a name="errorissue-search-fails-on-specific-locations"></a>Fehler/Problem: Suche schlägt an bestimmten Speicherorten fehl

Eine eDiscovery- oder Inhaltssuche kann den folgenden Fehler liefern: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![Screenshot des Fehlerfehlers für suchspezifischen Speicherort](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Lösung

Wenn dieser Fehler angezeigt wird, empfehlen wir, dass Sie die Speicherorte überprüfen, die bei der Suche fehlgeschlagen sind, und die Suche dann nur für die fehlerhaften Speicherorte erneut ausführen.

1. Verbinden zu [Security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Zeigen Sie in der PowerShell-Ausgabe die fehlerhaften Speicherorte im Fehlerfeld oder die Statusdetails im Fehler aus der Suchausgabe an.

3. Wiederholen Sie die eDiscovery-Suche nur für die fehlgeschlagenen Speicherorte.

4. Wenn diese Fehler weiterhin angezeigt werden, finden Sie weitere Schritte zur Problembehandlung unter ["Fehlerwiederherstellung".](/Office365/SecurityCompliance/retry-failed-content-search)

## <a name="errorissue-file-not-found"></a>Fehler/Problem: Datei nicht gefunden

Wenn Sie eine eDiscovery-Suche ausführen, die SharePoint Online- und One Drive For Business-Speicherorte enthält, wird möglicherweise der Fehler angezeigt, `File Not Found` obwohl sich die Datei auf der Website befindet. Dieser Fehler wird in den Exportwarnungen angezeigt und items.csv errors.csv oder übersprungen. Dies kann vorkommen, wenn die Datei auf der Website nicht gefunden werden kann oder wenn der Index veraltet ist. Hier sehen Sie den Text eines tatsächlichen Fehlers (mit hinzugefügter Hervorhebung).

> 28.06.2019 10:02:19_FailedToExportItem_Failed zum Herunterladen von Inhalten. Zusätzliche Diagnoseinformationen: Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Fehler beim Herunterladen von Inhalt 6ea52149-91cd-4965-b5bb-82ca6a3ec9be vom Typ "Document". Korrelations-ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***Datei nicht gefunden.*** bei Microsoft. SharePoint. Client.ClientRequest.ProcessResponseStream(Stream responseStream) bei Microsoft. SharePoint. Client.ClientRequest.ProcessResponse() --- Ende der ablaufverfolgung des internen Ausnahmestapels ---

### <a name="resolution"></a>Lösung

1. Überprüfen Sie den in der Suche identifizierten Speicherort, um sicherzustellen, dass der Speicherort der Datei korrekt ist und an den Suchspeicherorten hinzugefügt wird.

2. Verwenden Sie die Verfahren bei [der manuellen Anforderung der Durchforstung und neuindizierung einer Website, einer Bibliothek oder einer Liste,](/sharepoint/crawl-site-content) um die Website neu zu indizieren.

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a>Fehler/Problem: Diese Datei wurde nicht exportiert, da sie nicht mehr vorhanden ist. Die Datei wurde in die Anzahl der geschätzten Suchergebnisse einbezogen, da sie noch im Index aufgeführt ist. Die Datei wird schließlich aus dem Index entfernt und verursacht in Zukunft keinen Fehler.

Dieser Fehler tritt möglicherweise auf, wenn Sie eine eDiscovery-Suche ausführen, die SharePoint Online- und One Drive For Business-Speicherorte enthält. eDiscovery basiert auf dem SPO-Index, um die Dateispeicherorte zu identifizieren. Wenn die Datei gelöscht wurde, der SPO-Index aber noch nicht aktualisiert wurde, tritt dieser Fehler möglicherweise auf.

### <a name="resolution"></a>Lösung 
Öffnen Sie den SPO-Speicherort, und stellen Sie sicher, dass diese Datei nicht vorhanden ist.
Die vorgeschlagene Lösung besteht darin, die Website manuell neu zu indizieren oder zu warten, bis die Website durch den automatischen Hintergrundprozess neu indiziert wird.


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artefact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a>Fehler/Problem: Dieses Suchergebnis wurde nicht heruntergeladen, da es sich um einen Ordner oder ein anderes Artefakt handelt, der nicht von selbst heruntergeladen werden kann. Alle Elemente innerhalb des Ordners oder der Bibliothek werden heruntergeladen.

Dieser Fehler tritt möglicherweise auf, wenn Sie eine eDiscovery-Suche ausführen, die SharePoint Online- und One Drive For Business-Speicherorte enthält. Dies bedeutet, dass wir das im Index gemeldete Element ausprobieren und exportieren wollten, es sich jedoch als Ordner herausstellte, sodass wir es nicht exportiert haben. Wie im Fehler erwähnt, exportieren wir keine Ordnerelemente, sondern deren Inhalte.


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Fehler/Problem: Suche schlägt fehl, weil Empfänger nicht gefunden wird

Bei einer eDiscovery-Suche tritt ein Fehler `recipient not found` auf. Dieser Fehler kann auftreten, wenn das Benutzerobjekt in Exchange Online Protection (EOP) nicht gefunden werden kann, da das Objekt nicht synchronisiert wurde.

### <a name="resolution"></a>Lösung

1. Stellen Sie eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) her.

2. Führen Sie den folgenden Befehl aus, um zu überprüfen, ob der Benutzer mit Exchange Online Protection synchronisiert wird:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Für die Benutzerfrage sollte ein E-Mail-Benutzerobjekt vorhanden sein. Wenn nichts zurückgegeben wird, untersuchen Sie das Benutzerobjekt. Wenden Sie sich an den Microsoft-Support, wenn das Objekt nicht synchronisiert werden kann.

## <a name="errorissue-exporting-search-results-is-slow"></a>Fehler/Problem: Das Exportieren von Suchergebnissen ist langsam

Beim Exportieren von Suchergebnissen aus eDiscovery oder inhaltssuche im Security and Compliance Center dauert der Download länger als erwartet.  Sie können überprüfen, wie viele Daten heruntergeladen werden sollen, und möglicherweise die Exportgeschwindigkeit erhöhen.

### <a name="resolution"></a>Lösung

1. Verbinden zu [Security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Suchen Sie die Datenmenge, die in den Parametern SearchResults und SearchStatistics heruntergeladen werden soll.

3. Führen Sie den folgenden Befehl aus:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. Suchen Sie im Ergebnisfeld nach den exportierten Daten, und zeigen Sie alle aufgetretenen Fehler an.

5. Überprüfen Sie die Datei "trace.log" im Verzeichnis, in das Sie den Inhalt exportiert haben, auf Fehler.

6. Wenn weiterhin Probleme auftreten, sollten Sie Suchvorgänge, die eine große Gruppe von Ergebnissen zurückgeben, in kleinere Suchen unterteilen. Beispielsweise können Sie Datumsbereiche in Suchabfragen verwenden, um eine kleinere Gruppe von Ergebnissen zurückzugeben, die schneller heruntergeladen werden können.

## <a name="errorissue-internal-server-error-500-occurred"></a>Fehler/Problem: "Interner Serverfehler (500) aufgetreten"

Wenn beim Ausführen einer eDiscovery-Suche ein kontinuierlicher Fehler mit dem Fehler "Interner Serverfehler (500) aufgetreten" auftritt, müssen Sie die Suche möglicherweise nur an bestimmten Postfachspeicherorten erneut ausführen.

![Screenshot des internen Serverfehlers 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Lösung

1. Teilen Sie die Suche in kleinere Suchvorgänge auf, und führen Sie die Suche erneut aus.  Versuchen Sie, einen kleineren Datumsbereich zu verwenden, oder begrenzen Sie die Anzahl der durchsuchten Orte.

2. Verbinden zu [Security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Überprüfen Sie die Ausgabe auf Ergebnisse und Fehler.

4. Überprüfen Sie die Datei trace.log. Er befindet sich in demselben Ordner, in den Sie die Suchergebnisse exportiert haben.

5. Wenden Sie sich an den Support von Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Fehler/Problem: Haltebereiche werden nicht synchronisiert

eDiscovery Case Hold Policy Sync Distribution error. Der Fehler lautet:

> "Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet. Es kann weitere 2 Stunden dauern, bis der endgültige Bereitstellungsstatus aktualisiert wurde. Schauen Sie sich also ein paar Stunden zurück."

### <a name="resolution"></a>Lösung

1. Verbinden zu [Security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl für eine eDiscovery-Fallsperre aus:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Führen Sie für eine Aufbewahrungsrichtlinie den folgenden Befehl aus:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Untersuchen Sie den Wert im Parameter DistributionDetail auf Fehler wie die folgenden:

   > Fehler: Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet. Es kann weitere 2 Stunden dauern, bis der endgültige Bereitstellungsstatus aktualisiert wurde. Schauen Sie sich also ein paar Stunden zurück."

3. Versuchen Sie, den RetryDistribution-Parameter für die betreffende Richtlinie auszuführen:

   Für eDiscovery-Fallarchive:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   Für Aufbewahrungsrichtlinien:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Wenden Sie sich an den Support von Microsoft.

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>Fehler: "Die mit http-bedingten Headern angegebene Bedingung ist nicht erfüllt"

Beim Herunterladen von Suchergebnissen mit dem eDiscovery-Exporttool wird möglicherweise der folgende Fehler angezeigt: Dies ist ein `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` vorübergehender Fehler, der in der Regel am Azure Storage-Speicherort auftritt.

### <a name="resolution"></a>Lösung

Um dieses Problem zu beheben, versuchen Sie erneut, [die Suchergebnisse herunterzuladen,](export-search-results.md#step-2-download-the-search-results)wodurch das eDiscovery-Exporttool neu gestartet wird.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Fehler/Problem: Heruntergeladener Export zeigt keine Ergebnisse an

Nach einem erfolgreichen Export zeigt der abgeschlossene Download über das Exporttool keine Dateien in den Ergebnissen an.

### <a name="resolution"></a>Lösung

Dies ist ein clientseitiges Problem, und um es zu beheben, versuchen Sie die folgenden Schritte:

1. Versuchen Sie, einen anderen Client/Computer zum Herunterladen zu verwenden.

2. Entfernen Sie alte Suchen, die nicht mehr benötigt werden, mit dem Cmdlet [Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch].

3. Stellen Sie sicher, dass Sie auf ein lokales Laufwerk herunterladen.

4. Stellen Sie sicher, dass der Virenscanner nicht ausgeführt wird.

5. Stellen Sie sicher, dass kein anderer Export in denselben Ordner oder einen übergeordneten Ordner heruntergeladen wird.

6. Wenn die vorherigen Schritte nicht funktioniert haben, deaktivieren Sie das Zipping und die Deduplizierung.

7. Wenn dies funktioniert, liegt das Problem an einem lokalen Virenscanner oder einem Datenträgerproblem.
