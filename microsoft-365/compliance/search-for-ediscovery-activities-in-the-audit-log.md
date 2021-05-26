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
description: Erfahren Sie, welche Ereignisse protokolliert werden, wenn Benutzer, denen eDiscovery-Berechtigungen zugewiesen sind, inhaltssuche, Core eDiscovery und Advanced eDiscovery Aufgaben im Microsoft 365 ausführen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ce0dcc50c13ad705cb36f065639a4e971d032f22
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653499"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>Suchen nach eDiscovery-Aktivitäten im Überwachungsprotokoll

Inhaltssuche und eDiscovery-bezogene Aktivitäten (für Core eDiscovery und Advanced eDiscovery), die im Microsoft 365 Compliance Center oder durch Ausführen der entsprechenden PowerShell-Cmdlets ausgeführt werden, werden im Überwachungsprotokoll protokolliert. Ereignisse werden protokolliert, wenn Administratoren oder eDiscovery-Manager (oder benutzer zugewiesene eDiscovery-Berechtigungen) die folgenden Aufgaben für die Inhaltssuche und die Core eDiscovery im Microsoft 365 Compliance Center ausführen:
  
- Erstellen und Verwalten von Core- und Advanced eDiscovery Fällen

- Erstellen, Starten und Bearbeiten von Inhaltssuchen

- Ausführen von Suchaktionen, z. B. Vorschau, Exportieren und Löschen von Suchergebnissen

- Verwalten von Verwahrern und Überprüfungssätzen in Advanced eDiscovery

- Konfigurieren der Berechtigungsfilterung für die Inhaltssuche

- Verwalten der eDiscovery-Administratorrolle
  
Weitere Informationen zum Durchsuchen des Überwachungsprotokolls, zu den erforderlichen Berechtigungen und zum Exportieren von Suchergebnissen finden Sie unter Durchsuchen des Überwachungsprotokolls [im Microsoft 365 Compliance Center](search-the-audit-log-in-security-and-compliance.md).
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Suchen und Anzeigen von eDiscovery-Aktivitäten

Derzeit müssen Sie einige spezifische Schritte zum Anzeigen von eDiscovery-Aktivitäten im Überwachungsprotokoll tun. Die gehen so:
  
1. Wechseln Sie <https://compliance.microsoft.com> zu, und melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Klicken Sie im linken Navigationsbereich Microsoft 365 Compliance Center auf **Alle** anzeigen, und klicken Sie dann auf **Überwachung**.

3. Klicken Sie **in** der Dropdownliste Aktivitäten unter **eDiscovery-Aktivitäten** **oder Advanced eDiscovery** auf eine oder mehrere Aktivitäten, nach der gesucht werden soll.

    > [!NOTE]
    > Die **Dropdownliste** Aktivitäten enthält auch eine Gruppe von Aktivitäten namens **eDiscovery-Cmdletaktivitäten,** die Datensätze aus dem Cmdlet-Überwachungsprotokoll zurückgeben.
  
4. Wählen Sie einen Datums- und Zeitbereich aus, um eDiscovery-Ereignisse anzeigen zu können, die innerhalb dieses Zeitraums aufgetreten sind.

5. Wählen Sie **im Feld Benutzer** einen oder mehrere Benutzer aus, für die Suchergebnisse angezeigt werden sollen. Lassen Sie dieses Feld leer, um Einträge für alle Benutzer zurückzukehren.

6. Klicken Sie auf **Suchen**, um die Suche anhand der Suchkriterien auszuführen. 

7. Nachdem die Suchergebnisse angezeigt wurden, können Sie auf **Ergebnisse filtern** klicken, um die resultierenden Aktivitätseinträge zu filtern oder zu sortieren. Leider können Sie die Filterung nicht verwenden, um bestimmte Aktivitäten explizit auszuschließen. 

8. Um Details zu einer Aktivität anzuzeigen, klicken Sie in der Liste der Suchergebnisse auf den Aktivitätsdatensatz. 

    Es **wird eine** Fly-Out-Seite details angezeigt, die die detaillierten Eigenschaften des Ereignisdatensatz enthält. Klicken Sie auf Weitere Informationen, um weitere **Details anzuzeigen.** Eine Beschreibung dieser Eigenschaften finden Sie im Abschnitt [Detaillierte Eigenschaften für eDiscovery-Aktivitäten.](#detailed-properties-for-ediscovery-activities)

9. Bei Bedarf können Sie die Suchergebnisse des Überwachungsprotokolls in eine CSV-Datei exportieren und dann das feature Excel Power Query verwenden, um diese Datensätze zu formatieren und zu filtern. Weitere Informationen finden Sie unter[Exportieren, Konfigurieren und Anzeigen von Überwachungsprotokoll-Datensätzen](export-view-audit-log-records.md).

## <a name="ediscovery-activities"></a>eDiscovery-Aktivitäten

In der folgenden Tabelle werden die Aktivitäten Inhaltssuche und eDiscovery-Kern beschrieben, die protokolliert werden, wenn ein Administrator oder eDiscovery-Manager eine eDiscovery-bezogene Aktivität mithilfe des Compliance Centers ausführt oder das entsprechende Cmdlet in Security & Compliance Center PowerShell ausführt. Beachten Sie auch, dass einige Aktivitäten, die in Advanced eDiscovery ausgeführt werden, möglicherweise zurückgegeben werden, wenn Sie nach Aktivitäten in dieser Liste suchen.
  
> [!NOTE]
> Die in diesem Abschnitt beschriebenen eDiscovery-Aktivitäten enthalten ähnliche Informationen wie die im nächsten Abschnitt beschriebenen eDiscovery-Cmdletaktivitäten. Es wird empfohlen, die in diesem Abschnitt beschriebenen eDiscovery-Aktivitäten zu verwenden, da sie innerhalb von 30 Minuten in den Suchergebnissen des Überwachungsprotokolls angezeigt werden. Es dauert bis zu 24 Stunden, bis die eDiscovery-Cmdletaktivitäten in den Suchergebnissen des Überwachungsprotokolls angezeigt werden.
  
|**Anzeigename**|**Vorgang**|**Entsprechendes Cmdlet**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Mitglied zum eDiscovery-Fall hinzugefügt  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls hinzugefügt. Als Mitglied eines Falls kann ein Benutzer verschiedene fallbezogene Aufgaben ausführen, je nachdem, ob ihm die erforderlichen Berechtigungen zugewiesen wurden.  <br/> |
|Geänderte Inhaltssuche  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |Eine vorhandene Inhaltssuche wurde geändert. Änderungen können das Hinzufügen oder Entfernen von Inhaltspositionen oder das Bearbeiten der Suchabfrage umfassen.  <br/> |
|Geänderte eDiscovery-Administratormitgliedschaft  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |Die Liste der eDiscovery-Administratoren in Ihrer Organisation wurde geändert. Diese Aktivität wird protokolliert, wenn die Liste der eDiscovery-Administratoren durch eine Gruppe neuer Benutzer ersetzt wird. Wenn ein einzelner Benutzer hinzugefügt oder entfernt wird, wird der CaseAdminAdded-Vorgang protokolliert.  <br/> |
|EDiscovery-Fall geändert  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Ein eDiscovery-Fall wurde geändert. Änderungen umfassen das Schließen eines geöffneten Falls oder das erneute Öffnen eines geschlossenen Falls.  <br/> |
|Geänderte eDiscovery-Fallmitgliedschaft  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |Die Mitgliedschaftsliste eines eDiscovery-Falls wurde geändert. Diese Aktivität wird protokolliert, wenn alle Mitglieder durch eine Gruppe neuer Benutzer ersetzt werden. Wenn ein einzelnes Element hinzugefügt oder entfernt wird, wird caseMemberAdded- oder CaseMemberRemoved-Vorgang protokolliert.  <br/> |
|Filter für geänderte Suchberechtigungen  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |Ein Filter für Suchberechtigungen wurde geändert.  <br/> |
|Geänderte Suchabfrage für die eDiscovery-Fallaufberaumung  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Ein abfragebasierter Halteraum, der einem eDiscovery-Fall zugeordnet ist, wurde geändert. Mögliche Änderungen umfassen das Bearbeiten der Abfrage oder des Datumsbereichs für einen abfragebasierten Haltebereich.  <br/> |
|Vorschauelement für die Inhaltssuche heruntergeladen  <br/> |PreviewItemDownloaded  <br/> |Nicht zutreffend  <br/> |Ein Benutzer hat ein Element auf seinen  lokalen Computer heruntergeladen (durch Klicken auf den Link Ursprüngliches Element herunterladen) bei der Vorschau der Suchergebnisse.  <br/> |
|Vorschauelement für die Inhaltssuche aufgelistet  <br/> |PreviewItemListed  <br/> |Nicht zutreffend  <br/> |Ein Benutzer hat auf **Suchergebnisse anzeigen geklickt,** um die Vorschausuchergebnisseite anzuzeigen, die bis zu 1.000 Elemente aus den Ergebnissen einer Inhaltssuche auflistet.  <br/> |
|Vorschauelement für die Inhaltssuche angezeigt  <br/> |PreviewItemRendered  <br/> |Nicht zutreffend  <br/> |Ein eDiscovery-Manager hat ein Element angezeigt, indem er bei der Vorschau der Suchergebnisse darauf geklickt hat.  <br/> |
|Erstellte Inhaltssuche  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |Eine neue Inhaltssuche wurde erstellt.  <br/> |
|Erstellter eDiscovery-Administrator  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Ein Benutzer wurde als eDiscovery-Administrator in der Organisation hinzugefügt.  <br/> |
|EDiscovery-Fall erstellt  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |Ein eDiscovery-Fall wurde erstellt. Wenn ein Fall erstellt wird, müssen Sie ihm nur einen Namen geben. Andere fallbezogene Aufgaben wie das Hinzufügen von Mitgliedern, das Erstellen von Halte- und Inhaltssuchen im Zusammenhang mit dem Fall führen dazu, dass zusätzliche Ereignisse protokolliert werden.  <br/> |
|Filter für Suchberechtigungen erstellt  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |Ein Filter für Suchberechtigungen wurde erstellt.  <br/> |
|Suchabfrage für die eDiscovery-Fallaufbehebung erstellt  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |Ein abfragebasierter Halteraum, der einem eDiscovery-Fall zugeordnet ist, wurde erstellt.  <br/> |
|Suche nach gelöschten Inhalten  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Eine vorhandene Inhaltssuche wurde gelöscht.  <br/> |
|Gelöschter eDiscovery-Administrator  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Ein eDiscovery-Administrator wurde aus Ihrer Organisation gelöscht.  <br/> |
|Fall "Gelöschte eDiscovery"  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Ein eDiscovery-Fall wurde gelöscht. Alle dem Fall zugeordneten Halteschleifen müssen entfernt werden, bevor der Fall gelöscht werden kann.  <br/> |
|Filter für gelöschte Suchberechtigungen  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Ein Filter für Suchberechtigungen wurde gelöscht.  <br/> |
|Gelöschte Suchabfrage für die eDiscovery-Fallaufbehebung  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Ein abfragebasierter Halteraum, der einem eDiscovery-Fall zugeordnet ist, wurde gelöscht. Das Entfernen der Abfrage aus dem Halteraum ist häufig das Ergebnis des Löschens eines Halteraums. Wenn eine Halte- oder Halteabfrage gelöscht wird, werden die In-Hold-Speicherorte freigegeben.  <br/> |
|Heruntergeladener Export der Inhaltssuche  <br/> |SearchExportDownloaded  <br/> |Nicht zutreffend  <br/> |Ein Benutzer hat die Ergebnisse einer Inhaltssuche auf seinen lokalen Computer heruntergeladen. Ein **gestarteter Export von Inhaltssuchaktivitäten** muss initiiert werden, bevor Suchergebnisse heruntergeladen werden können.  <br/> |
|Vorschau der Ergebnisse der Inhaltssuche  <br/> |SearchPreviewed  <br/> |Nicht zutreffend  <br/> |Ein Benutzer hat eine Vorschau der Ergebnisse einer Inhaltssuche angezeigt.  <br/> |
|Gelöschte Ergebnisse der Inhaltssuche  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Ein Benutzer hat die Ergebnisse einer Inhaltssuche gelöscht, indem er den **Befehl New-ComplianceSearchAction -Purge** ausgeführt hat.  <br/> |
|Analyse der Inhaltssuche entfernt  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Vorbereitungsaktion für die Inhaltssuche (zum Vorbereiten von Suchergebnissen für Advanced eDiscovery) wurde gelöscht. Wenn die Vorbereitungsaktion weniger als zwei Wochen alt war, wurden die Suchergebnisse, die für Advanced eDiscovery vorbereitet wurden, aus dem Microsoft Azure gelöscht. Wenn die Vorbereitungsaktion älter als 2 Wochen war, gibt dieses Ereignis an, dass nur die entsprechende Vorbereitungsaktion gelöscht wurde.  <br/> |
|Export der Inhaltssuche entfernt  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Inhaltssuchexportaktion wurde gelöscht. Wenn die Exportaktion weniger als zwei Wochen alt war, wurden die Suchergebnisse, die in den Microsoft Azure speicherbereich hochgeladen wurden, gelöscht. Wenn die Exportaktion älter als 2 Wochen war, gibt dieses Ereignis an, dass nur die entsprechende Exportaktion gelöscht wurde.  <br/> |
|Member aus eDiscovery-Fall entfernt  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls entfernt.  <br/> |
|Vorschauergebnisse der Inhaltssuche entfernt  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Vorschauaktion für die Inhaltssuche wurde gelöscht.  <br/> |
|Entfernte Bereinigungsaktion, die bei der Inhaltssuche ausgeführt wurde  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Inhaltssuche wurde gelöscht.  <br/> |
|Suchbericht entfernt  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Aktion für den Inhaltssuchenexportbericht wurde gelöscht.  <br/> |
|Analyse der Inhaltssuche gestartet  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Die Ergebnisse einer Inhaltssuche wurden für die Analyse in Advanced eDiscovery.  <br/> |
|Gestartete Inhaltssuche  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Eine Inhaltssuche wurde gestartet. Wenn Sie eine Inhaltssuche mithilfe der gui Microsoft 365 erstellen oder ändern, wird die Suche automatisch gestartet. Wenn Sie eine Suche mithilfe des **Cmdlets New-ComplianceSearch** oder **Set-ComplianceSearch** erstellen oder ändern, müssen Sie das **Cmdlet Start-ComplianceSearch** ausführen, um die Suche zu starten.  <br/> |
|Export von Inhaltssuche gestartet  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Ein Benutzer hat die Ergebnisse einer Inhaltssuche exportiert.  <br/> |
|Exportbericht gestartet  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Ein Benutzer hat einen Bericht zur Inhaltssuche exportiert.  <br/> |
|Beendete Inhaltssuche  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Ein Benutzer hat eine Inhaltssuche beendet.  <br/> |
|(keine)|CaseViewed|Get-ComplianceCase|Ein Benutzer hat die Liste der Fälle auf der Seite **Core eDiscovery** im Compliance Center oder durch Ausführen des cmdlets Get-ComplianceCase angezeigt.|
|(keine)|SearchViewed|Get-ComplianceSearch|Ein Benutzer hat die Liste für Inhaltssuchen (auf der Registerkarte Suchen aufgeführt) im Compliance Center oder durch Ausführen des Cmdlets angezeigt.  Diese Aktivität wird auch protokolliert, wenn ein Benutzer die Liste der Inhaltssuchen im  Zusammenhang mit einem eDiscovery-Fall (durch Klicken auf die Registerkarte Suchen in einem Fall) oder durch Ausführen des **Befehls Get-ComplianceSearch -Case** aufruft.|
|(keine)|ViewedSearchExported|Get-ComplianceSearchAction -Export|Ein Benutzer hat die Liste der Exportaufträge  für die Inhaltssuche (auf der Registerkarte Exporte aufgeführt) im Compliance Center oder durch Ausführen des Cmdlets angezeigt. Diese Aktivität wird auch protokolliert, wenn ein Benutzer die Liste der Exportaufträge  in einem eDiscovery-Fall (in einem Fall auf der Registerkarte Exporte aufgeführt) oder durch Ausführen des **Befehls Get-ComplianceSearchAction -Case -Export** aufruft.|
|(keine)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|Ein Benutzer zeigt eine Vorschau der Ergebnisse einer Inhaltssuche im Compliance Center oder durch Ausführen des Cmdlets an.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>Advanced eDiscovery-Aktivitäten

In der folgenden Tabelle werden die Advanced eDiscovery im Überwachungsprotokoll protokollierten Aktivitäten beschrieben. Diese Aktivitäten können verwendet werden, um den Verlauf der Aktivität in einem fall Advanced eDiscovery verfolgen.

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

## <a name="ediscovery-cmdlet-activities"></a>eDiscovery-Cmdletaktivitäten

In der folgenden Tabelle sind die Cmdlet-Überwachungsprotokolleinträge aufgeführt, die protokolliert werden, wenn ein Administrator oder Benutzer eine eDiscovery-bezogene Aktivität mithilfe des Compliance Centers oder durch Ausführen des entsprechenden Cmdlets in Security & Compliance Center PowerShell ausführt. Die detaillierten Informationen im Überwachungsprotokolldatensatz unterscheiden sich für die cmdlet-Aktivitäten in dieser Tabelle und die im vorherigen Abschnitt beschriebenen eDiscovery-Aktivitäten.
  
Wie bereits erwähnt, dauert es bis zu 24 Stunden, bis eDiscovery-Cmdletaktivitäten in den Suchergebnissen des Überwachungsprotokolls angezeigt werden.
  
> [!TIP]
> Die Cmdlets in der **Spalte Vorgang** in der folgenden Tabelle sind mit dem entsprechenden Hilfethema für Cmdlets auf TechNet verknüpft. Eine Beschreibung der verfügbaren Parameter für jedes Cmdlet finden Sie im Hilfethema cmdlet. Der Parameter und der Parameterwert, die mit einem Cmdlet verwendet wurden, sind im Überwachungsprotokolleintrag für jede protokollierte eDiscovery-Cmdletaktivität enthalten. 
  
|**Anzeigename**|**Vorgang (Cmdlet)**|**Beschreibung**|
|:-----|:-----|:-----|
|Erstellter Halteraum im eDiscovery-Fall  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |Für einen eDiscovery-Fall wurde ein Haltefall erstellt. Ein Halteraum kann mit oder ohne Angabe einer Inhaltsquelle erstellt werden. Wenn Inhaltsquellen angegeben werden, werden sie im Überwachungsprotokolleintrag identifiziert.  <br/> |
|Gelöschter Halteraum aus dem eDiscovery-Fall  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |Ein halte, der einem eDiscovery-Fall zugeordnet ist, wurde gelöscht. Durch Löschen eines Halteortes werden alle Inhaltspositionen aus dem Halteraum entfernt. Das Löschen des Halteraums führt auch zum Löschen der fall hold rules associated with the hold (siehe **Remove-CaseHoldRule** weiter unten).  <br/> |
|Geänderter Halteraum im eDiscovery-Fall  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |Ein halte, der einer eDiscovery zugeordnet ist, wurde geändert. Mögliche Änderungen sind das Hinzufügen oder Entfernen von Inhaltsstandorten oder das Deaktivieren (Deaktivieren) des Halteraums.  <br/> |
|Suchabfrage für die eDiscovery-Fallaufbehebung erstellt  <br/> |[New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule) <br/> |Ein abfragebasierter Halteraum, der einem eDiscovery-Fall zugeordnet ist, wurde erstellt.  <br/> |
|Gelöschte Suchabfrage für die eDiscovery-Fallaufbehebung  <br/> |[Remove-CaseHoldRule](/powershell/module/exchange/remove-caseholdrule) <br/> |Ein abfragebasierter Halteraum, der einem eDiscovery-Fall zugeordnet ist, wurde gelöscht. Das Entfernen der Abfrage aus dem Halteraum ist häufig das Ergebnis des Löschens eines Halteraums. Wenn eine Halte- oder Halteabfrage gelöscht wird, werden die In-Hold-Speicherorte freigegeben.  <br/> |
|Geänderte Suchabfrage für die eDiscovery-Fallaufberaumung  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |Ein abfragebasierter Halteraum, der einem eDiscovery-Fall zugeordnet ist, wurde geändert. Mögliche Änderungen umfassen das Bearbeiten der Abfrage oder des Datumsbereichs für einen abfragebasierten Haltebereich.  <br/> |
|EDiscovery-Fall erstellt  <br/> |[New-ComplianceCase](/powershell/module/exchange/new-compliancecase) <br/> |Ein eDiscovery-Fall wurde erstellt. Wenn ein Fall erstellt wird, müssen Sie ihm nur einen Namen geben. Andere fallbezogene Aufgaben wie das Hinzufügen von Mitgliedern, das Erstellen von Halte- und Inhaltssuchen im Zusammenhang mit dem Fall führen dazu, dass zusätzliche Ereignisse protokolliert werden.  <br/> |
|Fall "Gelöschte eDiscovery"  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |Ein eDiscovery-Fall wurde gelöscht. Alle dem Fall zugeordneten Halteschleifen müssen entfernt werden, bevor der Fall gelöscht werden kann.  <br/> |
|EDiscovery-Fall geändert  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |Ein eDiscovery-Fall wurde geändert. Änderungen umfassen das Schließen eines geöffneten Falls oder das erneute Öffnen eines geschlossenen Falls.  <br/> |
|Mitglied zum eDiscovery-Fall hinzugefügt  <br/> |[Add-ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls hinzugefügt. Als Mitglied eines Falls kann ein Benutzer verschiedene fallbezogene Aufgaben ausführen, je nachdem, ob ihm die erforderlichen Berechtigungen zugewiesen wurden.  <br/> |
|Member aus eDiscovery-Fall entfernt  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls entfernt.  <br/> |
|Geänderte eDiscovery-Fallmitgliedschaft  <br/> |[Update-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |Die Mitgliedschaftsliste eines eDiscovery-Falls wurde geändert. Diese Aktivität wird protokolliert, wenn alle Mitglieder durch eine Gruppe neuer Benutzer ersetzt werden. Wenn ein einzelnes Element hinzugefügt oder entfernt wird, wird der **Add-ComplianceCaseMember-** oder **Remove-ComplianceCaseMember-Vorgang** protokolliert.  <br/> |
|Erstellte Inhaltssuche  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |Eine neue Inhaltssuche wurde erstellt.  <br/> |
|Suche nach gelöschten Inhalten  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |Eine vorhandene Inhaltssuche wurde gelöscht.  <br/> |
|Geänderte Inhaltssuche  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |Eine vorhandene Inhaltssuche wurde geändert. Zu den Änderungen kann das Hinzufügen oder Entfernen von Inhaltsstandorten gehören, die durchsucht und die Suchabfrage bearbeitet werden.  <br/> |
|Gestartete Inhaltssuche  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |Eine Inhaltssuche wurde gestartet. Wenn Sie eine Inhaltssuche mithilfe der Compliance Center-GUI erstellen oder ändern, wird die Suche automatisch gestartet. Wenn Sie eine Suche mithilfe des **Cmdlets New-ComplianceSearch** oder **Set-ComplianceSearch** erstellen oder ändern, müssen Sie das **Cmdlet Start-ComplianceSearch** ausführen, um die Suche zu starten.  <br/> |
|Beendete Inhaltssuche  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |Eine ausgeführte Inhaltssuche wurde beendet.  <br/> |
|Aktion zur Inhaltssuche erstellt  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |Es wurde eine Inhaltssuchaktion erstellt. Inhaltssuchaktionen umfassen die Vorschau von Suchergebnissen, das Exportieren von Suchergebnissen, das Vorbereiten von Suchergebnissen für die Analyse in Advanced eDiscovery und das dauerhafte Löschen von Elementen, die den Suchkriterien einer Inhaltssuche entsprechen.  <br/> |
|Aktion für die Suche nach gelöschten Inhalten  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |Eine Inhaltssuchaktion wurde gelöscht.  <br/> |
|Filter für Suchberechtigungen erstellt  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |Ein Filter für Suchberechtigungen wurde erstellt.  <br/> |
|Filter für gelöschte Suchberechtigungen  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |Ein Filter für Suchberechtigungen wurde gelöscht.  <br/> |
|Filter für geänderte Suchberechtigungen  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |Ein Filter für Suchberechtigungen wurde geändert.  <br/> |
|Erstellter eDiscovery-Administrator  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |Ein Benutzer wurde als eDiscovery-Administrator in Ihrer Organisation hinzugefügt.  <br/> |
|Gelöschter eDiscovery-Administrator  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |Ein eDiscovery-Administrator wurde aus Ihrer Organisation gelöscht.  <br/> |
|Geänderte eDiscovery-Administratormitgliedschaft  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |Die Liste der eDiscovery-Administratoren in Ihrer Organisation wurde geändert. Diese Aktivität wird protokolliert, wenn die Liste der eDiscovery-Administratoren durch eine Gruppe neuer Benutzer ersetzt wird. Wenn ein einzelner Benutzer hinzugefügt oder entfernt wird, wird der **Add-eDiscoveryCaseAdmin-** oder **Remove-eDiscoveryCaseAdmin-Vorgang** protokolliert.  <br/> |

## <a name="detailed-properties-for-ediscovery-activities"></a>Detaillierte Eigenschaften für eDiscovery-Aktivitäten

In der folgenden Tabelle werden die  Eigenschaften beschrieben, die enthalten sind, wenn Sie auf der Seite **Details** auf Weitere Informationen für eine eDiscovery-Aktivität klicken, die in den Suchergebnissen aufgeführt ist. Diese Eigenschaften sind auch in der CSV-Datei enthalten, wenn Sie die Suchergebnisse des Überwachungsprotokolls exportieren. Ein Überwachungsprotokolldatensatz für eine eDiscovery-Aktivität enthält nicht alle unten aufgeführten detaillierten Eigenschaften.
  
> [!TIP]
> Wenn Sie die Suchergebnisse exportieren, enthält die CSV-Datei eine Spalte mit dem Namen **Detail**, die die detaillierten Eigenschaften enthält, die in der folgenden Tabelle in einer Mehrwerteigenschaft beschrieben sind. Sie können das Power Query-Feature in Excel verwenden, um diese Spalte in mehrere Spalten aufteilen, sodass jede Eigenschaft eine eigene Spalte hat. Dadurch können Sie eine oder mehrere dieser Eigenschaften sortieren und filtern. Weitere Informationen finden Sie im Abschnitt "Exportieren der Suchergebnisse in eine Datei" unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file). 
  
|**Eigenschaft**|**Beschreibung**|
|:-----|:-----|
|Fall  <br/> |Die Identität (GUID) des eDiscovery-Falls, der erstellt, geändert oder gelöscht wurde.  <br/> |
|ClientApplication  <br/> |eDiscovery-Cmdletaktivitäten haben einen Wert von **EMC** für diese Eigenschaft. Dies gibt an, dass die Aktivität mithilfe der Compliance Center-GUI oder ausführen des Cmdlets in PowerShell ausgeführt wurde.  <br/> |
|ClientIP  <br/> |Die IP-Adresse des Geräts, das verwendet wurde, als die Aktivität protokolliert wurde. Die IP-Adresse wird im Adressformat IPv4 oder IPv6 angezeigt.  <br/> |
|ClientRequestId  <br/> | Bei eDiscovery-Aktivitäten ist diese Eigenschaft in der Regel leer.  <br/> |
|CmdletVersion  <br/> |Die Buildnummer für die Version des Compliance Centers, das in Ihrer Organisation ausgeführt wird.  <br/> |
|CreationTime  <br/> |Datum und Uhrzeit in koordinierter Weltzeit (Coordinated Universal Time, UTC), als die eDiscovery-Aktivität abgeschlossen wurde.  <br/> |
|EffectiveOrganization  <br/> |Der Name der Microsoft 365-Organisation.  <br/> |
|ExchangeLocations  <br/> |Die Exchange Online, die in einer Inhaltssuche enthalten sind oder in einem eDiscovery-Fall in einem Archiv platziert werden.  <br/> |
|Ausschlüsse  <br/> |Postfach- oder Websitespeicherorte, die von einer Inhaltssuche oder einem Archiv in einem eDiscovery-Fall ausgeschlossen sind.  <br/> |
|ExtendedProperties  <br/> |Zusätzliche Eigenschaften aus einer Inhaltssuche, einer Inhaltssuchaktion oder einem Halten in einem eDiscovery-Fall, z. B. die Objekt-GUID und die entsprechenden Cmdlet- und Cmdletparameter, die bei der Aktivität verwendet wurden.  <br/> |
|Id  <br/> |Die ID des Berichtseintrags. Die ID identifiziert den Überwachungsprotokolleintrag eindeutig.  <br/> |
|NonPIIParameters  <br/> |Eine Liste der Parameter (ohne Werte), die mit dem cmdlet verwendet wurden, das in der Operation-Eigenschaft identifiziert wurde. Die in dieser Eigenschaft aufgeführten Parameter sind mit denen in der Parameters-Eigenschaft identisch.  <br/> |
|ObjectId  <br/> |Die GUID oder der Name des Objekts (z. B. eine Inhaltssuche oder ein eDiscovery-Fall), das von der in der Operation-Eigenschaft aufgeführten Aktivität erstellt, geändert oder gelöscht wurde. Dieses Objekt wird auch in der Spalte Element in den Suchergebnissen des Überwachungsprotokolls identifiziert.  <br/> |
|ObjectType  <br/> |Der Typ des eDiscovery-Objekts, das der Benutzer erstellt, gelöscht oder geändert hat. Beispielsweise eine Inhaltssuchaktion (Vorschau, Export oder Bereinigung), ein eDiscovery-Fall oder eine Inhaltssuche.  <br/> |
|Vorgang  <br/> |Der Name des Vorgangs, der der ausgeführten eDiscovery-Aktivität entspricht.  <br/> |
|OrganizationId  <br/> |Die GUID für Microsoft 365 Organisation.  <br/> |
|Parameter  <br/> |Der Name und der Wert für die Parameter, die mit dem entsprechenden Cmdlet verwendet wurden.  <br/> |
|PublicFolderLocations  <br/> |Die Speicherorte für öffentliche Ordner in Exchange Online, die in einer Inhaltssuche enthalten sind oder in einem eDiscovery-Fall in einem Haltefeld platziert werden.  <br/> |
|Abfrage  <br/> |Die der Aktivität zugeordnete Suchabfrage, z. B. eine Inhaltssuche oder ein abfragebasierter Halteraum.  <br/> |
|RecordType  <br/> |Der vom Datensatz angegebene Vorgangstyp. Der Wert **18** gibt ein Ereignis im Zusammenhang mit einer Aktivität an, die im [Abschnitt eDiscovery-Cmdletaktivitäten aufgeführt](#ediscovery-cmdlet-activities) ist. Der Wert **24** gibt ein Ereignis im Zusammenhang mit einer Aktivität an, das im Abschnitt Suchen und Anzeigen von [eDiscovery-Aktivitäten aufgeführt](#how-to-search-for-and-view-ediscovery-activities) ist.  <br/> |
|ResultStatus  <br/> |Gibt an, ob die Aktion (in der Eigenschaft "Operation" angegeben) erfolgreich war oder nicht.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Gibt an, dass die Aktivität ein Compliance Center-Ereignis war. Alle eDiscovery-Aktivitäten haben den Wert **0** für diese Eigenschaft.  <br/> |
|SharepointLocations  <br/> |The SharePoint Online sites that are included in a content search or placed on hold in a eDiscovery case.  <br/> |
|StartTime  <br/> |Datum und Uhrzeit in koordinierter Weltzeit (Coordinated Universal Time, UTC), wenn die eDiscovery-Aktivität gestartet wurde.  <br/> |
|UserId  <br/> |Der Benutzer, der die (in der Operation-Eigenschaft angegebene) Aktivität ausgeführt hat, die dazu geführt hat, dass der Datensatz protokolliert wurde. Datensätze für eDiscovery-Aktivitäten, die von Systemkonten (z. B. NT AUTHORITY\SYSTEM) ausgeführt werden, sind ebenfalls im Überwachungsprotokoll enthalten.  <br/> |
|UserKey  <br/> |Eine alternative ID für den in der UserId-Eigenschaft identifizierten Benutzer. Bei eDiscovery-Aktivitäten ist der Wert für diese Eigenschaft in der Regel identisch mit der UserId-Eigenschaft.  <br/> |
|UserServicePlan  <br/> |Das von Ihrer Organisation verwendete Abonnement. Bei eDiscovery-Aktivitäten ist diese Eigenschaft in der Regel leer.  <br/> |
|UserType  <br/> |Der Typ des Benutzers, der den Vorgang ausgeführt hat. Die folgenden Werte geben den Benutzertyp an.  <br/> 0 Ein regulärer Benutzer. 2 Ein Administrator in Ihrer Organisation. 3 Ein Microsoft Datacenter-Administrator- oder Datencentersystemkonto. 4 Ein Systemkonto. 5 Eine Anwendung. 6 Ein Dienstprinzipal. |
|Version  <br/> |Gibt die Versionsnummer der Aktivität (identifiziert durch die Operation-Eigenschaft) an, die protokolliert wird.  <br/> |
|Arbeitslast  <br/> |Der Dienst, in dem die Aktivität aufgetreten ist. Für eDiscovery-Aktivitäten ist der Wert **SecurityComplianceCenter**.  <br/> |
