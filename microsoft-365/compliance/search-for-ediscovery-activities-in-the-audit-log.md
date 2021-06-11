---
title: Suchen nach eDiscovery-Aktivitäten im Überwachungsprotokoll
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Erfahren Sie, welche Ereignisse protokolliert werden, wenn Benutzer, denen eDiscovery-Berechtigungen zugewiesen sind, Inhaltssuche, Core eDiscovery und Advanced eDiscovery Aufgaben im Microsoft 365 Compliance Center ausführen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cca0cdc02e2c23231637acf6eba2b07144266e36
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888409"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>Suchen nach eDiscovery-Aktivitäten im Überwachungsprotokoll

Inhaltssuche und eDiscovery-bezogene Aktivitäten (für Core eDiscovery und Advanced eDiscovery), die im Microsoft 365 Compliance Center oder durch Ausführen der entsprechenden PowerShell-Cmdlets ausgeführt werden, werden im Überwachungsprotokoll protokolliert. Ereignisse werden protokolliert, wenn Administratoren oder eDiscovery-Manager (oder ein beliebiger Benutzer, dem eDiscovery-Berechtigungen zugewiesen sind) die folgenden Aufgaben für die Inhaltssuche und core eDiscovery im Microsoft 365 Compliance Center ausführen:
  
- Erstellen und Verwalten von Core- und Advanced eDiscovery Fällen

- Erstellen, Starten und Bearbeiten von Inhaltssuchen

- Durchführen von Suchaktionen, z. B. Anzeigen der Vorschau, Exportieren und Löschen von Suchergebnissen

- Verwalten von Verwahrern und Prüfdateisätzen in Advanced eDiscovery

- Konfigurieren der Berechtigungsfilterung für die Inhaltssuche

- Verwalten der eDiscovery-Administratorrolle
  
Weitere Informationen zum Durchsuchen des Überwachungsprotokolls, zu den erforderlichen Berechtigungen und zum Exportieren von Suchergebnissen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Microsoft 365 Compliance Center.](search-the-audit-log-in-security-and-compliance.md)
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Suchen und Anzeigen von eDiscovery-Aktivitäten

Derzeit müssen Sie einige spezifische Aktionen ausführen, um eDiscovery-Aktivitäten im Überwachungsprotokoll anzuzeigen. Die gehen so:
  
1. Wechseln Sie zu <https://compliance.microsoft.com>, und melden Sie sich mit Ihrem Arbeits-, Uni- oder Schulkonto an.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf **"Überwachen".**

3. Klicken Sie in der Dropdownliste **"Aktivitäten"** unter **eDiscovery-Aktivitäten** oder **Advanced eDiscovery Aktivitäten** auf eine oder mehrere Aktivitäten, nach denen gesucht werden soll.

    > [!NOTE]
    > Die Dropdownliste **"Aktivitäten"** enthält auch eine Gruppe von Aktivitäten namens **eDiscovery-Cmdlet-Aktivitäten,** die Datensätze aus dem Cmdlet-Überwachungsprotokoll zurückgeben.
  
4. Wählen Sie einen Datums- und Uhrzeitbereich aus, um eDiscovery-Ereignisse anzuzeigen, die innerhalb dieses Zeitraums aufgetreten sind.

5. Wählen Sie im Feld **"Benutzer"** einen oder mehrere Benutzer aus, für die Suchergebnisse angezeigt werden sollen. Lassen Sie dieses Feld leer, um Einträge für alle Benutzer zurückzugeben.

6. Klicken Sie auf **Suchen**, um die Suche anhand der Suchkriterien auszuführen. 

7. Nachdem die Suchergebnisse angezeigt wurden, können Sie auf **"Ergebnisse** filtern" klicken, um die resultierenden Aktivitätsdatensätze zu filtern oder zu sortieren. Leider können Sie die Filterung nicht verwenden, um bestimmte Aktivitäten explizit auszuschließen. 

8. Um Details zu einer Aktivität anzuzeigen, klicken Sie auf den Aktivitätsdatensatz in der Liste der Suchergebnisse. 

    Es wird eine **Flyoutseite** für Details angezeigt, die die detaillierten Eigenschaften aus dem Ereignisdatensatz enthält. Klicken Sie auf **Weitere Informationen,** um weitere Details anzuzeigen. Eine Beschreibung dieser Eigenschaften finden Sie im Abschnitt ["Detaillierte Eigenschaften für eDiscovery-Aktivitäten".](#detailed-properties-for-ediscovery-activities)

9. Falls gewünscht, können Sie die Suchergebnisse des Überwachungsprotokolls in eine CSV-Datei exportieren und dann das Power Query-Feature Excel verwenden, um diese Datensätze zu formatieren und zu filtern. Weiter Informationen findn Sie unter[Exportieren, Konfigurieren und Anzeigen von Überwachungsprotokoll-Datensätzen](export-view-audit-log-records.md).

## <a name="ediscovery-activities"></a>eDiscovery-Aktivitäten

In der folgenden Tabelle werden die Inhaltssuche- und Core eDiscovery-Aktivitäten beschrieben, die protokolliert werden, wenn ein Administrator oder eDiscovery-Manager eine eDiscovery-bezogene Aktivität mithilfe des Microsoft 365 Compliance Centers ausführt. Einige in Advanced eDiscovery ausgeführte Aktivitäten werden möglicherweise zurückgegeben, wenn Sie nach Aktivitäten in dieser Liste suchen.
  
> [!NOTE]
> Die in diesem Abschnitt beschriebenen eDiscovery-Aktivitäten enthalten ähnliche Informationen wie die im nächsten Abschnitt beschriebenen eDiscovery-Cmdlet-Aktivitäten. Es wird empfohlen, die in diesem Abschnitt beschriebenen eDiscovery-Aktivitäten zu verwenden, da sie innerhalb von 30 Minuten in den Suchergebnissen des Überwachungsprotokolls angezeigt werden. Es kann bis zu 24 Stunden dauern, bis eDiscovery-Cmdlet-Aktivitäten in den Suchergebnissen des Überwachungsprotokolls angezeigt werden.
  
|**Anzeigename**|**Vorgang**|**Entsprechendes Cmdlet**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Mitglied zu eDiscovery-Fall hinzugefügt  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls hinzugefügt. Als Mitglied eines Falls kann ein Benutzer verschiedene fallbezogene Aufgaben ausführen, je nachdem, ob ihm die erforderlichen Berechtigungen zugewiesen wurden.  <br/> |
|Inhaltssuche geändert  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |Eine vorhandene Inhaltssuche wurde geändert. Änderungen können das Hinzufügen oder Entfernen von Inhaltsspeicherorten oder das Bearbeiten der Suchabfrage umfassen.  <br/> |
|eDiscovery-Administratormitgliedschaft geändert  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |Die Liste der eDiscovery-Administratoren in Ihrer Organisation wurde geändert. Diese Aktivität wird protokolliert, wenn die Liste der eDiscovery-Administratoren durch eine Gruppe neuer Benutzer ersetzt wird. Wenn ein einzelner Benutzer hinzugefügt oder entfernt wird, wird der CaseAdminAdded-Vorgang protokolliert.  <br/> |
|eDiscovery-Fall geändert  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Ein eDiscovery-Fall wurde geändert. Zu den Änderungen gehören das Schließen eines geöffneten Falls oder das erneute Öffnen eines geschlossenen Falls.  <br/> |
|eDiscovery-Fallmitgliedschaft geändert  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |Die Mitgliedschaftsliste eines eDiscovery-Falls wurde geändert. Diese Aktivität wird protokolliert, wenn alle Mitglieder durch eine Gruppe neuer Benutzer ersetzt werden. Wenn ein einzelnes Element hinzugefügt oder entfernt wird, wird der CaseMemberAdded- oder CaseMemberRemoved-Vorgang protokolliert.  <br/> |
|Suchberechtigungsfilter geändert  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |Ein Suchberechtigungsfilter wurde geändert.  <br/> |
|Suchabfrage für eDiscovery-Fallarchiv geändert  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde geändert. Mögliche Änderungen sind das Bearbeiten der Abfrage oder des Datumsbereichs für einen abfragebasierten Haltebereich.  <br/> |
|Vorschauelement der Inhaltssuche heruntergeladen  <br/> |PreviewItemDownloaded  <br/> |–  <br/> |Ein Benutzer hat ein Element auf den lokalen Computer heruntergeladen (durch Klicken auf den Link **"Ursprüngliches Element herunterladen")** bei der Vorschau der Suchergebnisse.  <br/> |
|Vorschauelement der Inhaltssuche aufgelistet  <br/> |PreviewItemListed  <br/> |–  <br/> |Ein Benutzer hat auf **die Suchergebnisse in** der Vorschau geklickt, um die Vorschau-Suchergebnisseite anzuzeigen, die bis zu 1.000 Elemente aus den Ergebnissen einer Suche auflistet.  <br/> |
|Vorschauelement der Inhaltssuche angezeigt  <br/> |PreviewItemRendered  <br/> |–  <br/> |Ein eDiscovery-Manager hat ein Element angezeigt, indem er bei der Vorschau der Suchergebnisse darauf geklickt hat.  <br/> |
|Inhaltssuche erstellt  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |Eine neue Inhaltssuche wurde erstellt.  <br/> |
|eDiscovery-Administrator erstellt  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Ein Benutzer wurde in der Organisation als eDiscovery-Administrator hinzugefügt.  <br/> |
|eDiscovery-Fall erstellt  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |Ein eDiscovery-Fall wurde erstellt. Wenn ein Fall erstellt wird, müssen Sie ihm nur einen Namen geben. Andere fallbezogene Aufgaben wie das Hinzufügen von Mitgliedern, das Erstellen von Haltebereichen und das Erstellen von Inhaltssuchen, die dem Fall zugeordnet sind, führen dazu, dass zusätzliche Ereignisse protokolliert werden.  <br/> |
|Suchberechtigungsfilter erstellt  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |Ein Suchberechtigungsfilter wurde erstellt.  <br/> |
|Suchabfrage für eDiscovery-Fallarchivierung erstellt  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde erstellt.  <br/> |
|Suche nach gelöschten Inhalten  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Eine vorhandene Inhaltssuche wurde gelöscht.  <br/> |
|eDiscovery-Administrator gelöscht  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Ein eDiscovery-Administrator wurde aus Ihrer Organisation gelöscht.  <br/> |
|eDiscovery-Fall gelöscht  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Ein eDiscovery-Fall wurde gelöscht. Jede dem Fall zugeordnete Aufbewahrung muss entfernt werden, bevor der Fall gelöscht werden kann.  <br/> |
|Filter für gelöschte Suchberechtigungen  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Ein Suchberechtigungsfilter wurde gelöscht.  <br/> |
|Gelöschte Suchabfrage für eDiscovery-Fallarchivierung  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde gelöscht. Das Entfernen der Abfrage aus dem Haltebereich ist häufig das Ergebnis des Löschens eines Haltebereichs. Wenn eine Aufbewahrungs- oder Haltebereichsabfrage gelöscht wird, werden die Speicherorte für inhalte freigegeben, die in der Warteschleife waren.  <br/> |
|Export der Inhaltssuche heruntergeladen  <br/> |SearchExportDownloaded  <br/> |–  <br/> |Ein Benutzer hat die Ergebnisse einer Inhaltssuche auf den lokalen Computer heruntergeladen. Ein **gestarteter Export von Inhaltssuchaktivitäten** muss initiiert werden, bevor Suchergebnisse heruntergeladen werden können.  <br/> |
|Ergebnisse der Inhaltssuche in der Vorschau anzeigen  <br/> |SearchPreviewed  <br/> |–  <br/> |Ein Benutzer hat eine Vorschau der Ergebnisse einer Inhaltssuche angezeigt.  <br/> |
|Gelöschte Ergebnisse der Inhaltssuche  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Ein Benutzer hat die Ergebnisse einer Inhaltssuche gelöscht, indem er den Befehl **"New-ComplianceSearchAction -Purge"** ausführte.  <br/> |
|Analyse der Inhaltssuche entfernt  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Vorbereitungsaktion für die Inhaltssuche (um Suchergebnisse für Advanced eDiscovery vorzubereiten) wurde gelöscht. Wenn die Vorbereitungsaktion weniger als zwei Wochen alt war, wurden die Suchergebnisse, die für Advanced eDiscovery vorbereitet wurden, aus dem Microsoft Azure Speicherbereich gelöscht. Wenn die Vorbereitungsaktion älter als 2 Wochen war, gibt dieses Ereignis an, dass nur die entsprechende Vorbereitungsaktion gelöscht wurde.  <br/> |
|Export der Inhaltssuche entfernt  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Exportaktion für die Inhaltssuche wurde gelöscht. Wenn die Exportaktion weniger als zwei Wochen alt war, wurden die Suchergebnisse, die in den Microsoft Azure-Speicherbereich hochgeladen wurden, gelöscht. Wenn die Exportaktion älter als 2 Wochen war, gibt dieses Ereignis an, dass nur die entsprechende Exportaktion gelöscht wurde.  <br/> |
|Mitglied aus eDiscovery-Fall entfernt  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls entfernt.  <br/> |
|Vorschauergebnisse der Inhaltssuche entfernt  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Vorschauaktion für die Inhaltssuche wurde gelöscht.  <br/> |
|Bei der Inhaltssuche ausgeführte Bereinigungsaktion entfernt  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Löschaktion für die Inhaltssuche wurde gelöscht.  <br/> |
|Suchbericht entfernt  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Exportberichtsaktion für die Inhaltssuche wurde gelöscht.  <br/> |
|Analyse der Inhaltssuche gestartet  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Die Ergebnisse einer Inhaltssuche wurden für die Analyse in Advanced eDiscovery vorbereitet.  <br/> |
|Inhaltssuche gestartet  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Eine Inhaltssuche wurde gestartet. Wenn Sie eine Inhaltssuche mithilfe des Microsoft 365 Compliance Centers erstellen oder ändern, wird die Suche automatisch gestartet.<br/> |
|Export der Inhaltssuche gestartet  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Ein Benutzer hat die Ergebnisse einer Inhaltssuche exportiert.  <br/> |
|Bericht "Export gestartet"  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Ein Benutzer hat einen Bericht zur Inhaltssuche exportiert.  <br/> |
|Beendete Inhaltssuche  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Ein Benutzer hat eine Inhaltssuche beendet.  <br/> |
|(keine)|CaseViewed|Get-ComplianceCase|Ein Benutzer hat einen Core eDiscovery-Fall im Compliance Center angezeigt. Der Überwachungsdatensatz für dieses Ereignis enthält den Namen des angezeigten Falls. |
|(keine)|SearchViewed|Get-ComplianceSearch|Ein Benutzer hat eine Inhaltssuche im Compliance Center angezeigt, indem er auf die Suche auf der Registerkarte **"Suchen"** in einem Core eDiscovery-Fall oder auf der **Seite "Inhaltssuche"** darauf zugreift. Der Überwachungsdatensatz für dieses Ereignis enthält die Identität der Suche, die angezeigt wurde.|
|(keine)|ViewedSearchExported|Get-ComplianceSearchAction -Export|Ein Benutzer hat einen Export der Inhaltssuche im Compliance Center angezeigt, indem er auf der Registerkarte **"Exporte"** auf der Seite **"Inhaltssuche"** auf den Export zugreift. Diese Aktivität wird auch protokolliert, wenn ein Benutzer einen Export anzeigt, der einem Core eDiscovery-Fall zugeordnet ist.|
|(keine)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|Ein Benutzer hat eine Vorschau der Ergebnisse einer Inhaltssuche im Compliance Center angezeigt. Diese Aktivität wird auch protokolliert, wenn ein Benutzer die Ergebnisse einer Suche anzeigt, die einem Core eDiscovery-Fall zugeordnet ist.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>Advanced eDiscovery-Aktivitäten

In der folgenden Tabelle werden die Advanced eDiscovery im Überwachungsprotokoll protokollierten Aktivitäten beschrieben. Diese Aktivitäten können verwendet werden, um den Fortschritt der Aktivität in einem Advanced eDiscovery Fall nachzuverfolgen.

|**Anzeigename**|**Vorgang**|**Beschreibung**|
|:-----|:-----|:-----|
|Daten zu einem anderen Prüfdateisatz hinzugefügt|AddWorkingSetQueryToWorkingSet|Der Benutzer hat Dokumente eines Prüfdateisatzes einem anderen hinzugefügt.|
|Daten zu einem Prüfdateisatz hinzugefügt|AddQueryToWorkingSet|Der Benutzer hat die Suchergebnisse einer Inhaltssuche, die einem Advanced eDiscovery-Fall zugeordnet sind, einem Prüfdateisatz zugeordnet.|
|Nicht von Microsoft 365 stammende Daten zu Prüfdateisatz hinzugefügt|AddNonOffice365DataToWorkingSet|Ein Benutzer hat nicht von Microsoft 365 stammende Daten zu einem Prüfdateisatz hinzugefügt.|
|Wiederhergestellte Dokumente zu Prüfdateisatz hinzugefügt|AddRemediatedData|Der Benutzer lädt Dokumente hoch, bei denen Indizierungsfehler aufgetreten sind, die in einem Prüfdateisatz festgehalten worden sind.|
|Daten im Prüfdateisatz analysiert|RunAlgo|Der Benutzer hat eine Analyse der Dokumente in einem Prüfdateisatz durchgeführt.|
|Dokument im Prüfdateisatz kommentiert|AnnotateDocument|Ein Benutzer hat ein Dokument in einem Prüfdateisatz kommentiert. „Kommentieren“ umfasst auch das Bearbeiten/Redigieren des Dokuments.|
|Ladesätze verglichen|LoadComparisonJob|Der Benutzer hat zwei verschiedene Ladesätze in einem Prüfdateisatz verglichen. Unter Ladesatz versteht man, dass Daten aus einer Inhaltssuche, die einem Fall zugeordnet sind, einem Prüfdateisatz hinzugefügt werden.|
|Dokumente in PDF-Dateien konvertiert|BurnJob|Der Benutzer hat alle redigierten Dokumente in einem Prüfdateisatz in PDF-Dateien konvertiert.|
|Prüfdateisatz erstellt|CreateWorkingSet|Der Benutzer hat einen Prüfdateisatz erstellt.|
|Prüfdateisatzsuche erstellt|CreateWorkingSetSearch|Der Benutzer hat eine Suchabfrage erstellt, die die Dokumente in einem Prüfdateisatz durchsuchen.|
|Tag erstellt|CreateTag|Ein Benutzer hat eine Tag-Gruppe in einem Prüfdateisatz erstellt. Eine Tag-Gruppe kann ein oder mehrere untergeordnete Tags enthalten. Diese Tags werden dann zum Taggen von Dokumenten im Prüfdateisatz verwendet.|
|Prüfdateisatzsuche gelöscht|DeleteWorkingSetSearch|Ein Benutzer hat eine Suchabfrage in einem Prüfdateisatz gelöscht.|
|Tag gelöscht|DeleteTag|Ein Benutzer hat ein Tag oder eine Tag-Gruppe in einem Prüfdateisatz gelöscht.|
|Heruntergeladenes Dokument|DownloadDocument|Ein Benutzer hat ein Dokument aus einem Prüfdateisatz heruntergeladen.|
|Tag bearbeitet|UpdateTag|Ein Benutzer hat ein Tag in einem Prüfdateisatz geändert.|
|Dokumente aus einem Prüfdateisatz exportiert|ExportJob|Der Benutzer hat Dokumente aus einem Prüfdateisatz exportiert.|
|Falleinstellungen geändert|UpdateCaseSettings|Der Benutzer hat die Einstellungen für einen Fall geändert. Die Falleinstellungen umfassen Fallinformationen, Zugriffsberechtigungen und Einstellungen, mit denen das Such- und Analyseverhalten gesteuert werden.|
|Prüfdateisatzsuche geändert|UpdateWorkingSetSearch|Ein Benutzer hat eine Suchabfrage in einem Prüfdateisatz geändert.|
|Vorschau einer Prüfdateisatzsuche angezeigt|PreviewWorkingSetSearch|Der Benutzer hat die Ergebnisse einer Suchabfrage in einem Prüfdateisatz in einer Vorschau angezeigt.|
|Fehler in Dokumenten behoben|ErrorRemediationJob|Der Benutzer behebt Dateien mit Indizierungsfehlern.|
|Dokument getaggt|TagFiles|Ein Benutzer hat ein Dokument in einem Prüfdateisatz mit Tags versehen.|
|Ergebnisse einer Abfrage getaggt|TagJob|Ein Benutzer hat alle Dokumente getaggt, die den Kriterien einer Suchabfrage in einem Prüfdateisatz entsprechen.|
|Dokument im Prüfdateisatz angezeigt|ViewDocument|Ein Benutzer hat ein Dokument in einem Prüfdateisatz angezeigt.|
|||

## <a name="ediscovery-cmdlet-activities"></a>eDiscovery-Cmdlet-Aktivitäten

In der folgenden Tabelle sind die Cmdlet-Überwachungsprotokolleinträge aufgeführt, die protokolliert werden, wenn ein Administrator oder Benutzer eine eDiscovery-bezogene Aktivität mithilfe des Compliance Centers oder durch Ausführen des entsprechenden Cmdlets in Security & Compliance Center PowerShell ausführt. Die detaillierten Informationen im Überwachungsprotokolleintrag unterscheiden sich für die in dieser Tabelle aufgeführten Cmdlet-Aktivitäten und die im vorherigen Abschnitt beschriebenen eDiscovery-Aktivitäten.
  
Wie bereits erwähnt, kann es bis zu 24 Stunden dauern, bis eDiscovery-Cmdlet-Aktivitäten in den Suchergebnissen des Überwachungsprotokolls angezeigt werden.
  
> [!TIP]
> Die Cmdlets in der Spalte **"Operation"** in der folgenden Tabelle sind mit dem entsprechenden Hilfethema zum Cmdlet auf TechNet verknüpft. Im Hilfethema zum Cmdlet finden Sie eine Beschreibung der verfügbaren Parameter für jedes Cmdlet. Der Parameter und der Parameterwert, die mit einem Cmdlet verwendet wurden, sind im Überwachungsprotokolleintrag für jede protokollierte eDiscovery-Cmdlet-Aktivität enthalten. 
  
|**Anzeigename**|**Operation (Cmdlet)**|**Beschreibung**|
|:-----|:-----|:-----|
|Aufbewahrung im eDiscovery-Fall erstellt  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |Für einen eDiscovery-Fall wurde eine Aufbewahrung erstellt. Ein Haltebereich kann mit oder ohne Angabe einer Inhaltsquelle erstellt werden. Wenn Inhaltsquellen angegeben werden, werden sie im Überwachungsprotokolleintrag identifiziert.  <br/> |
|Aufbewahrung von eDiscovery-Fall gelöscht  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |Ein Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde gelöscht. Beim Löschen eines Haltebereichs werden alle Inhaltsspeicherorte aus dem Haltebereich entfernt. Das Löschen des Haltebereichs führt auch zum Löschen der Fall-Halteregeln, die dem Haltebereich zugeordnet sind (siehe **"Remove-CaseHoldRule"** weiter unten).  <br/> |
|Haltebereich in eDiscovery-Fall geändert  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |Ein Haltebereich, der einer eDiscovery zugeordnet ist, wurde geändert. Mögliche Änderungen sind das Hinzufügen oder Entfernen von Inhaltsspeicherorten oder das Deaktivieren (Deaktivieren) des Haltebereichs.  <br/> |
|Suchabfrage für eDiscovery-Fallarchivierung erstellt  <br/> |[New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule) <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde erstellt.  <br/> |
|Gelöschte Suchabfrage für eDiscovery-Fallarchivierung  <br/> |[Remove-CaseHoldRule](/powershell/module/exchange/remove-caseholdrule) <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde gelöscht. Das Entfernen der Abfrage aus dem Haltebereich ist häufig das Ergebnis des Löschens eines Haltebereichs. Wenn eine Aufbewahrungs- oder Haltebereichsabfrage gelöscht wird, werden die Speicherorte für inhalte freigegeben, die in der Warteschleife waren.  <br/> |
|Suchabfrage für eDiscovery-Fallarchiv geändert  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde geändert. Mögliche Änderungen sind das Bearbeiten der Abfrage oder des Datumsbereichs für einen abfragebasierten Haltebereich.  <br/> |
|eDiscovery-Fall erstellt  <br/> |[New-ComplianceCase](/powershell/module/exchange/new-compliancecase) <br/> |Ein eDiscovery-Fall wurde erstellt. Wenn ein Fall erstellt wird, müssen Sie ihm nur einen Namen geben. Andere fallbezogene Aufgaben wie das Hinzufügen von Mitgliedern, das Erstellen von Haltebereichen und das Erstellen von Inhaltssuchen, die dem Fall zugeordnet sind, führen dazu, dass zusätzliche Ereignisse protokolliert werden.  <br/> |
|eDiscovery-Fall gelöscht  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |Ein eDiscovery-Fall wurde gelöscht. Jede dem Fall zugeordnete Aufbewahrung muss entfernt werden, bevor der Fall gelöscht werden kann.  <br/> |
|eDiscovery-Fall geändert  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |Ein eDiscovery-Fall wurde geändert. Zu den Änderungen gehören das Schließen eines geöffneten Falls oder das erneute Öffnen eines geschlossenen Falls.  <br/> |
|Mitglied zu eDiscovery-Fall hinzugefügt  <br/> |[Add-ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls hinzugefügt. Als Mitglied eines Falls kann ein Benutzer verschiedene fallbezogene Aufgaben ausführen, je nachdem, ob ihm die erforderlichen Berechtigungen zugewiesen wurden.  <br/> |
|Mitglied aus eDiscovery-Fall entfernt  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls entfernt.  <br/> |
|eDiscovery-Fallmitgliedschaft geändert  <br/> |[Update-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |Die Mitgliedschaftsliste eines eDiscovery-Falls wurde geändert. Diese Aktivität wird protokolliert, wenn alle Mitglieder durch eine Gruppe neuer Benutzer ersetzt werden. Wenn ein einzelnes Mitglied hinzugefügt oder entfernt wird, wird der **Vorgang "Add-ComplianceCaseMember"** oder **"Remove-ComplianceCaseMember"** protokolliert.  <br/> |
|Inhaltssuche erstellt  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |Eine neue Inhaltssuche wurde erstellt.  <br/> |
|Suche nach gelöschten Inhalten  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |Eine vorhandene Inhaltssuche wurde gelöscht.  <br/> |
|Inhaltssuche geändert  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |Eine vorhandene Inhaltssuche wurde geändert. Zu den Änderungen gehören das Hinzufügen oder Entfernen von Inhaltsspeicherorten, die durchsucht werden, und das Bearbeiten der Suchabfrage.  <br/> |
|Inhaltssuche gestartet  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |Eine Inhaltssuche wurde gestartet. Wenn Sie eine Inhaltssuche mithilfe der Compliance Center-GUI erstellen oder ändern, wird die Suche automatisch gestartet. Wenn Sie eine Suche mithilfe des **Cmdlets "New-ComplianceSearch"** oder **"Set-ComplianceSearch"** erstellen oder ändern, müssen Sie das Cmdlet **"Start-ComplianceSearch"** ausführen, um die Suche zu starten.  <br/> |
|Beendete Inhaltssuche  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |Eine Inhaltssuche, die ausgeführt wurde, wurde beendet.  <br/> |
|Aktion "Inhaltssuche erstellt"  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |Es wurde eine Inhaltssuche-Aktion erstellt. Zu den Inhaltssuchaktionen gehören das Anzeigen der Vorschau von Suchergebnissen, das Exportieren von Suchergebnissen, das Vorbereiten von Suchergebnissen für die Analyse in Advanced eDiscovery und das dauerhafte Löschen von Elementen, die den Suchkriterien einer Inhaltssuche entsprechen.  <br/> |
|Suchaktion für gelöschte Inhalte  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |Eine Inhaltssuche wurde gelöscht.  <br/> |
|Suchberechtigungsfilter erstellt  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |Ein Suchberechtigungsfilter wurde erstellt.  <br/> |
|Filter für gelöschte Suchberechtigungen  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |Ein Suchberechtigungsfilter wurde gelöscht.  <br/> |
|Suchberechtigungsfilter geändert  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |Ein Suchberechtigungsfilter wurde geändert.  <br/> |
|eDiscovery-Administrator erstellt  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |Ein Benutzer wurde in Ihrer Organisation als eDiscovery-Administrator hinzugefügt.  <br/> |
|eDiscovery-Administrator gelöscht  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |Ein eDiscovery-Administrator wurde aus Ihrer Organisation gelöscht.  <br/> |
|eDiscovery-Administratormitgliedschaft geändert  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |Die Liste der eDiscovery-Administratoren in Ihrer Organisation wurde geändert. Diese Aktivität wird protokolliert, wenn die Liste der eDiscovery-Administratoren durch eine Gruppe neuer Benutzer ersetzt wird. Wenn ein einzelner Benutzer hinzugefügt oder entfernt wird, wird der **Vorgang "Add-eDiscoveryCaseAdmin"** oder **"Remove-eDiscoveryCaseAdmin"** protokolliert.  <br/> |
|(keine)|[Get-ComplianceCase](/powershell/module/exchange/get-compliancecase) <br/>|Diese Aktivität wird protokolliert, wenn ein Benutzer eine Liste von Core eDiscovery- oder Advanced eDiscovery Fällen angezeigt hat. Diese Aktivität wird auch protokolliert, wenn ein Benutzer einen bestimmten Fall in Core eDiscovery anzeigt. Wenn ein Benutzer einen bestimmten Fall anzeigt, enthält der Überwachungsdatensatz die Identität des angezeigten Falls. Wenn der Benutzer nur eine Liste von Fällen angezeigt hat, enthält der Überwachungsdatensatz keine Fallidentität.|
|(keine)|[Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)|Diese Aktivität wird protokolliert, wenn ein Benutzer eine Liste der Inhaltssuchen oder sucht, die einem Core eDiscovery-Fall zugeordnet sind. Diese Aktivität wird auch protokolliert, wenn ein Benutzer eine bestimmte Inhaltssuche anzeigt oder eine bestimmte Suche anzeigt, die einem Core eDiscovery-Fall zugeordnet ist. Wenn ein Benutzer eine bestimmte Suche anzeigt, enthält der Überwachungsdatensatz die Identität der Suche, die angezeigt wurde. Wenn der Benutzer nur eine Liste von Suchvorgängen angezeigt hat, enthält der Überwachungsdatensatz keine Suchidentität.
|(keine)|[Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)|Diese Aktivität wird protokolliert, wenn ein Benutzer eine Liste der Compliance-Suchaktionen (z. B. Exporte, Vorschauen oder Löschvorgänge) oder Aktionen im Zusammenhang mit einem Core eDiscovery-Fall anzeigt. Diese Aktivität wird auch protokolliert, wenn ein Benutzer eine bestimmte Compliance-Suchaktion (z. B. einen Export) anzeigt oder eine bestimmte Aktion anzeigt, die einem Core eDiscovery-Fall zugeordnet ist. Wenn ein Benutzer eine Suchaktion anzeigt, enthält der Überwachungsdatensatz die Identität der Suchaktion, die angezeigt wurde. Wenn der Benutzer nur eine Liste von Aktionen angezeigt hat, enthält der Überwachungsdatensatz keine Aktionsidentität.|
||||

## <a name="detailed-properties-for-ediscovery-activities"></a>Detaillierte Eigenschaften für eDiscovery-Aktivitäten

In der folgenden Tabelle werden die Eigenschaften beschrieben, die enthalten sind, wenn Sie auf der Seite **"Details"** auf **weitere Informationen** für eine eDiscovery-Aktivität klicken, die in den Suchergebnissen aufgeführt ist. Diese Eigenschaften sind auch in der CSV-Datei enthalten, wenn Sie die Suchergebnisse des Überwachungsprotokolls exportieren. Ein Überwachungsprotokolleintrag für eine eDiscovery-Aktivität enthält nicht jede unten aufgeführte detaillierte Eigenschaft.
  
> [!TIP]
> Wenn Sie die Suchergebnisse exportieren, enthält die CSV-Datei eine Spalte mit dem Namen **"Detail",** die die in der folgenden Tabelle beschriebenen detaillierten Eigenschaften in einer mehrwertigen Eigenschaft enthält. Sie können das Power Query-Feature in Excel verwenden, um diese Spalte in mehrere Spalten aufzuteilen, sodass jede Eigenschaft über eine eigene Spalte verfügt. Auf diese Weise können Sie nach einer oder mehreren dieser Eigenschaften sortieren und filtern. Weitere Informationen finden Sie im Abschnitt "Exportieren der Suchergebnisse in eine Datei" im [Abschnitt "Durchsuchen des Überwachungsprotokolls".](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file) 
  
|**Eigenschaft**|**Beschreibung**|
|:-----|:-----|
|Fall  <br/> |Die Identität (GUID) des eDiscovery-Falls, der erstellt, geändert oder gelöscht wurde.  <br/> |
|ClientApplication  <br/> |eDiscovery-Cmdlet-Aktivitäten weisen für diese Eigenschaft den Wert **EMC** auf. Dies gibt an, dass die Aktivität mithilfe der Compliance Center-GUI oder dem Ausführen des Cmdlets in PowerShell ausgeführt wurde.  <br/> |
|ClientIP  <br/> |Die IP-Adresse des Geräts, das verwendet wurde, als die Aktivität protokolliert wurde. Die IP-Adresse wird im Adressformat IPv4 oder IPv6 angezeigt.  <br/> |
|ClientRequestId  <br/> | Für eDiscovery-Aktivitäten ist diese Eigenschaft in der Regel leer.  <br/> |
|CmdletVersion  <br/> |Die Buildnummer für die Version des Compliance Centers, das in Ihrer Organisation ausgeführt wird.  <br/> |
|CreationTime  <br/> |Das Datum und die Uhrzeit in koordinierter Weltzeit (UTC), zu der die eDiscovery-Aktivität abgeschlossen wurde.  <br/> |
|EffectiveOrganization  <br/> |Der Name der Microsoft 365-Organisation.  <br/> |
|ExchangeLocations  <br/> |Die Exchange Online Postfächer, die in einer Inhaltssuche enthalten sind oder in einem eDiscovery-Fall aufbewahrt werden.  <br/> |
|Ausschlüsse  <br/> |Postfach- oder Websitespeicherorte, die von einer Inhaltssuche oder einem Haltebereich in einem eDiscovery-Fall ausgeschlossen sind.  <br/> |
|ExtendedProperties  <br/> |Zusätzliche Eigenschaften aus einer Inhaltssuche, einer Inhaltssucheaktion oder einer Aufbewahrung in einem eDiscovery-Fall, z. B. die Objekt-GUID und die entsprechenden Cmdlet- und Cmdlet-Parameter, die bei der Ausführung der Aktivität verwendet wurden.  <br/> |
|Id  <br/> |Die ID des Berichtseintrags. Die ID identifiziert den Überwachungsprotokolleintrag eindeutig.  <br/> |
|NonPIIParameters  <br/> |Eine Liste der Parameter (ohne Werte), die mit dem in der Operation-Eigenschaft identifizierten Cmdlet verwendet wurden. Die in dieser Eigenschaft aufgeführten Parameter sind identisch mit den parametern, die in der Parameters-Eigenschaft aufgeführt sind.  <br/> |
|ObjectId  <br/> |Die GUID oder der Name des Objekts (z. B. eine Inhaltssuche oder ein Core eDiscovery-Fall), die von der in der Operation -Eigenschaft aufgelisteten Aktivität erstellt, aufgerufen, geändert oder gelöscht wurde. Dieses Objekt wird auch in der Spalte "Element" in den Suchergebnissen des Überwachungsprotokolls identifiziert.  <br/> |
|ObjectType  <br/> |Der Typ des eDiscovery-Objekts, das der Benutzer erstellt, gelöscht oder geändert hat; Beispielsweise eine Inhaltssuche (Vorschau, Export oder Bereinigung), ein eDiscovery-Fall oder eine Inhaltssuche.  <br/> |
|Vorgang  <br/> |Der Name des Vorgangs, der der eDiscovery-Aktivität entspricht, die ausgeführt wurde.  <br/> |
|OrganizationId  <br/> |Die GUID für Ihre Microsoft 365 Organisation.  <br/> |
|Parameter  <br/> |Der Name und Wert für die Parameter, die mit dem entsprechenden Cmdlet verwendet wurden.  <br/> |
|PublicFolderLocations  <br/> |Die Speicherorte öffentlicher Ordner in Exchange Online, die in einer Inhaltssuche enthalten sind oder in einem eDiscovery-Fall aufbewahrt werden.  <br/> |
|Abfrage  <br/> |Die der Aktivität zugeordnete Suchabfrage, z. B. eine Inhaltssuche oder eine abfragebasierte Aufbewahrung.  <br/> |
|RecordType  <br/> |Der vom Datensatz angegebene Vorgangstyp. Der Wert **18** gibt ein Ereignis im Zusammenhang mit einer Aktivität an, die im Abschnitt ["eDiscovery-Cmdlet-Aktivitäten"](#ediscovery-cmdlet-activities) aufgeführt ist. Der Wert **24** gibt ein Ereignis im Zusammenhang mit einer Aktivität an, die im Abschnitt "Suchen und Anzeigen von [eDiscovery-Aktivitäten"](#how-to-search-for-and-view-ediscovery-activities) aufgeführt ist.  <br/> |
|ResultStatus  <br/> |Gibt an, ob die Aktion (in der Eigenschaft "Operation" angegeben) erfolgreich war oder nicht.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Gibt an, dass die Aktivität ein Compliance Center-Ereignis war. Alle eDiscovery-Aktivitäten haben den Wert **0** für diese Eigenschaft.  <br/> |
|SharepointLocations  <br/> |Die SharePoint Onlinewebsites, die in einer Inhaltssuche enthalten sind oder in einem eDiscovery-Fall aufbewahrt werden.  <br/> |
|StartTime  <br/> |Das Datum und die Uhrzeit in koordinierter Weltzeit (UTC), zu der die eDiscovery-Aktivität gestartet wurde.  <br/> |
|UserId  <br/> |Der Benutzer, der die (in der Operation-Eigenschaft angegebene) Aktivität ausgeführt hat, die zum Protokollieren des Datensatzes geführt hat. Datensätze für eDiscovery-Aktivitäten, die von Systemkonten (z. B. NT AUTHORITY\SYSTEM) ausgeführt werden, sind ebenfalls im Überwachungsprotokoll enthalten.  <br/> |
|UserKey  <br/> |Eine alternative ID für den in der UserId-Eigenschaft identifizierten Benutzer. Bei eDiscovery-Aktivitäten ist der Wert für diese Eigenschaft in der Regel identisch mit der UserId-Eigenschaft.  <br/> |
|UserServicePlan  <br/> |Das von Ihrer Organisation verwendete Abonnement. Für eDiscovery-Aktivitäten ist diese Eigenschaft in der Regel leer.  <br/> |
|UserType  <br/> |Der Typ des Benutzers, der den Vorgang ausgeführt hat. Die folgenden Werte geben den Benutzertyp an.  <br/> 0 Ein normaler Benutzer. 2 Ein Administrator in Ihrer Organisation. 3 Ein Microsoft-Rechenzentrumsadministrator- oder -Rechenzentrumssystemkonto. 4 Ein Systemkonto. 5 Eine Anwendung. 6 Ein Dienstprinzipal. |
|Version  <br/> |Gibt die Versionsnummer der protokollierten Aktivität an (identifiziert durch die Operation-Eigenschaft).  <br/> |
|Arbeitslast  <br/> |Der Dienst, in dem die Aktivität aufgetreten ist. Für eDiscovery-Aktivitäten ist der Wert **SecurityComplianceCenter**.  <br/> |
