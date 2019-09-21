---
title: Suchen nach eDiscovery-Aktivitäten im Office 365 Überwachungsprotokoll
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: 'Hier erfahren Sie, wie Sie das Office 365 Überwachungsprotokoll nach Ereignissen durchsuchen, die protokolliert werden, wenn Compliance-Administratoren Inhaltssuche-und eDiscovery-Fall Aufgaben im Security #a0 Compliance Center ausführen.'
ms.openlocfilehash: 7be0cbd5a6cbdad0158228b808802200034265d5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081953"
---
# <a name="search-for-ediscovery-activities-in-the-office-365-audit-log"></a>Suchen nach eDiscovery-Aktivitäten im Office 365 Überwachungsprotokoll

Die Inhaltssuche und eDiscovery-bezogene Aktivitäten, die im Sicherheits #a0 Compliance Center oder durch Ausführen der entsprechenden Windows PowerShell-Cmdlets ausgeführt werden, werden im Office 365 Überwachungsprotokoll protokolliert. Ereignisse werden protokolliert, wenn Administratoren oder Compliance-Administratoren (oder ein beliebiger Benutzer, dem eDiscovery-Berechtigungen zugewiesen sind) die folgenden Aufgaben im Security #a0 Compliance Center ausführen:
  
- Erstellen und Verwalten von eDiscovery-Fällen
    
- Erstellen, starten und Bearbeiten von Inhalts suchen
    
- Ausführen von Inhalts Suchaktionen wie Vorschau, Export und Löschen von Suchergebnissen
    
- Konfigurieren der Berechtigungs Filterung für die Inhaltssuche
    
- Verwalten der eDiscovery-Administrator Rolle
    
> [!IMPORTANT]
> Die in diesem Artikel beschriebenen Aktivitäten sind nur das Ergebnis von eDiscovery-Aufgaben, die mithilfe des Security #a0 Compliance Centers ausgeführt werden. eDiscovery-Aufgaben, die mit dem in-Place-eDiscovery-Tool in Exchange Online oder dem eDiscovery Center in SharePoint Online durchgeführt wurden, sind nicht enthalten. 
  
Weitere Informationen zum Durchsuchen des Office 365 Überwachungsprotokolls, zu den erforderlichen Berechtigungen und zum Exportieren von Suchergebnissen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security #a0 Compliance Center](search-the-audit-log-in-security-and-compliance.md).
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Suchen und Anzeigen von eDiscovery-Aktivitäten

Derzeit müssen Sie einige spezifische Aufgaben durchführen, um eDiscovery-Aktivitäten im Office 365 Überwachungsprotokoll anzuzeigen. Die gehen so:
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich bei Office 365 mit Ihrem Geschäfts-, Schul- oder Unikonto an.
    
3. Klicken Sie im linken Bereich auf **Suchen**, und klicken Sie dann auf **Überwachungsprotokoll Suche**.
    
4. Klicken Sie in der Dropdownliste **Aktivitäten** unter **eDiscovery-Aktivitäten**auf eine oder mehrere Aktivitäten, nach denen gesucht werden soll. Sie können auch auf **eDiscovery-Aktivitäten** klicken, um nach allen eDiscovery-bezogenen Aktivitäten zu suchen. 
    
    > [!NOTE]
    > Die Dropdownliste Aktivitäten enthält auch eine Gruppe von Aktivitäten mit dem Namen **eDiscovery-Cmdlet-Aktivitäten** , mit denen Datensätze aus dem Cmdlet-Überwachungsprotokoll zurückgegeben werden. 
  
5.  Wählen Sie einen Datums-und Zeitbereich aus, um eDiscovery-Ereignisse anzuzeigen, die innerhalb dieses Zeitraums aufgetreten sind. 
    
6. Wählen Sie im Feld **Benutzer** einen oder mehrere Benutzer aus, für die Suchergebnisse angezeigt werden sollen. Lassen Sie dieses Feld leer, um Einträge für alle Benutzer zurückzugeben. 
    
7. Klicken Sie auf **Suchen** , um die Suche mit Ihren Suchkriterien auszuführen. 
    
8. Nachdem die Suchergebnisse angezeigt wurden, können Sie auf **Filterergebnisse** klicken, um die resultierenden Aktivitätsdatensätze zu filtern oder zu sortieren. Leider können Sie das Filtern nicht verwenden, um bestimmte Aktivitäten explizit auszuschließen. 
    
9. Wenn Sie Details zu einer Aktivität anzeigen möchten, klicken Sie in der Liste der Suchergebnisse auf den Aktivitäts Eintrag. 
    
    Eine Seite Fly Out **Details** wird angezeigt, die die detaillierten Eigenschaften aus dem Ereigniseintrag enthält. Klicken Sie auf **Weitere Informationen**, um weitere Details anzuzeigen. Eine Beschreibung dieser Eigenschaften finden Sie im Abschnitt [detaillierte Eigenschaften für eDiscovery-Aktivitäten](#detailed-properties-for-ediscovery-activities) . 

  
## <a name="ediscovery-activities"></a>eDiscovery-Aktivitäten

In der folgenden Tabelle werden die Inhaltssuche und eDiscovery-bezogene Aktivitäten beschrieben, die protokolliert werden, wenn ein Administrator oder Benutzer eine eDiscovery-bezogene Aktivität mithilfe des Security #a0 Compliance Center oder durch Ausführen des entsprechenden Cmdlets in Remote ausführt. PowerShell, die mit dem Sicherheits #a1 Compliance Center Ihres Unternehmens verbunden ist. 
  
> [!NOTE]
> Die in diesem Abschnitt beschriebenen eDiscovery-Aktivitäten bieten ähnliche Informationen zu den im nächsten Abschnitt beschriebenen eDiscovery-Cmdlet-Aktivitäten. Es wird empfohlen, die in diesem Abschnitt beschriebenen eDiscovery-Aktivitäten zu verwenden, da Sie innerhalb von 30 Minuten in den Überwachungsprotokoll-Suchergebnissen angezeigt werden. Es dauert bis zu 24 Stunden, bis die eDiscovery-Cmdlet-Aktivitäten in Überwachungsprotokoll-Suchergebnissen angezeigt werden. 
  
|**Anzeigename**|**Vorgang**|**Entsprechendes Cmdlet**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Mitglied zu eDiscovery-Fall hinzugefügt  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls hinzugefügt. Als Mitglied eines Falles kann ein Benutzer verschiedene fallbezogene Aufgaben ausführen, je nachdem, ob ihm die erforderlichen Berechtigungen zugewiesen wurden.  <br/> |
|Geänderte Inhaltssuche  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |Eine vorhandene Inhaltssuche wurde geändert. Zu den Änderungen können das Hinzufügen oder Entfernen von Inhaltsspeicherorten oder das Bearbeiten der Suchabfrage gehören.  <br/> |
|Geänderte eDiscovery-Administrator Mitgliedschaft  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |Die Liste der eDiscovery-Administratoren in Ihrer Organisation wurde geändert. Diese Aktivität wird protokolliert, wenn die Liste der eDiscovery-Administratoren durch eine Gruppe neuer Benutzer ersetzt wird. Wenn ein einzelner Benutzer hinzugefügt oder entfernt wird, wird der CaseAdminAdded-Vorgang protokolliert.  <br/> |
|Geänderter eDiscovery-Fall  <br/> |CaseUpdated  <br/> |Gruppe-ComplianceCase  <br/> |Ein eDiscovery-Fall wurde geändert. Zu den Änderungen gehören das Schließen eines offenen Falls oder das erneute Öffnen eines geschlossenen Falls.  <br/> |
|Geänderte eDiscovery-Fall Mitgliedschaft  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |Die Mitgliederliste eines eDiscovery-Falls wurde geändert. Diese Aktivität wird protokolliert, wenn alle Mitglieder durch eine Gruppe neuer Benutzer ersetzt werden. Wenn ein einzelnes Element hinzugefügt oder entfernt wird, wird der CaseMemberAdded-oder der CaseMemberRemoved-Vorgang protokolliert.  <br/> |
|Geänderter Such Berechtigungsfilter  <br/> |SearchPermissionUpdated  <br/> |Gruppe-ComplianceSecurityFilter  <br/> |Ein Such Berechtigungsfilter wurde geändert.  <br/> |
|Geänderte Suchabfrage für eDiscovery Case Hold  <br/> |HoldUpdated  <br/> |Gruppe-CaseHoldRule  <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde geändert. Mögliche Änderungen umfassen das Bearbeiten der Abfrage oder des Datumsbereichs für einen abfragebasierten Haltebereich.  <br/> |
|Vorschau Element für Inhaltssuche heruntergeladen  <br/> |PreviewItemDownloaded  <br/> |Nicht zutreffend  <br/> |Ein Benutzer hat ein Element auf den lokalen Computer heruntergeladen (durch Klicken auf den Link **ursprüngliches Element herunterladen** ), wenn die Suchergebnisse in der Vorschau angezeigt werden.  <br/> |
|Vorschau Element der Inhaltssuche aufgelistet  <br/> |PreviewItemListed  <br/> |Nicht zutreffend  <br/> |Ein Benutzer hat auf **Vorschau der Such** Ergebnisse geklickt, um die Seite Vorschau der Suchergebnisse anzuzeigen, in der bis zu 1000 Elemente aus den Ergebnissen einer Inhaltssuche aufgelistet werden.  <br/> |
|Vorschau Element "Inhaltssuche" angezeigt  <br/> |PreviewItemRendered  <br/> |Nicht zutreffend  <br/> |Ein eDiscovery-Manager hat ein Element angezeigt, indem er bei der Vorschau der Suchergebnisse darauf geklickt hat.  <br/> |
|Erstellte Inhaltssuche  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |Eine neue Inhaltssuche wurde erstellt.  <br/> |
|Erstellter eDiscovery-Administrator  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Ein Benutzer wurde als eDiscovery-Administrator in der Organisation hinzugefügt.  <br/> |
|Erstellter eDiscovery-Fall  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |Es wurde ein eDiscovery-Fall erstellt. Wenn ein Fall erstellt wird, müssen Sie ihm nur einen Namen geben. Andere fallbezogene Aufgaben wie das Hinzufügen von Mitgliedern, das Erstellen von Haltebereichen und das Erstellen von Inhalts suchen, die dem Fall zugeordnet sind, führen zu zusätzlichen Ereignissen, die protokolliert werden.  <br/> |
|Erstellter Such Berechtigungsfilter  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |Es wurde ein Such Berechtigungsfilter erstellt.  <br/> |
|Erstellte Suchabfrage für eDiscovery Case Hold  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde erstellt.  <br/> |
|Suche nach gelöschten Inhalten  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Eine vorhandene Inhaltssuche wurde gelöscht.  <br/> |
|Gelöschter eDiscovery-Administrator  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Ein eDiscovery-Administrator wurde aus Ihrer Organisation gelöscht.  <br/> |
|Gelöschter eDiscovery-Fall  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Ein eDiscovery-Fall wurde gelöscht. Beachten Sie, dass alle dem Fall zugeordneten Halterungen entfernt werden müssen, bevor der Fall gelöscht werden kann.  <br/> |
|Filter für gelöschte Suchberechtigungen  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Ein Such Berechtigungsfilter wurde gelöscht.  <br/> |
|Gelöschte Suchabfrage für eDiscovery Case Hold  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde gelöscht. Das Entfernen der Abfrage aus dem Haltestatus ist häufig das Ergebnis des Löschens eines Haltestatus. Wenn eine halte-oder halte Abfrage gelöscht wird, werden die Aufbewahrungsorte für Inhalte freigegeben.  <br/> |
|Heruntergeladener Export der Inhaltssuche  <br/> |SearchExportDownloaded  <br/> |Nicht zutreffend  <br/> |Ein Benutzer hat die Ergebnisse einer Inhaltssuche auf den lokalen Computer heruntergeladen. Beachten Sie, dass ein **gestarteter Export der Inhalts Such** Aktivität initiiert werden muss, bevor Suchergebnisse heruntergeladen werden können.  <br/> |
|Vorschau der Ergebnisse der Inhaltssuche  <br/> |SearchPreviewed  <br/> |Nicht zutreffend  <br/> |Ein Benutzer hat eine Vorschau der Ergebnisse einer Inhaltssuche angezeigt.  <br/> |
|Bereinigte Ergebnisse der Inhaltssuche  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Ein Benutzer hat die Ergebnisse einer Inhaltssuche gelöscht, indem er den Befehl **New-ComplianceSearchAction-Purge** ausführt.  <br/> |
|Analyse der Inhaltssuche entfernt  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Inhaltssuche Prepare-Aktion (zum Vorbereiten der Suchergebnisse für Office 365 Advanced eDiscovery) wurde gelöscht. Wenn die Vorbereitungs Aktion weniger als zwei Wochen alt war, wurden die Suchergebnisse, die für Advanced eDiscovery vorbereitet wurden, aus dem Microsoft Azure Speicherbereich gelöscht. Wenn die Vorbereitungs Aktion älter als 2 Wochen war, zeigt dieses Ereignis an, dass nur die entsprechende Vorbereitungs Aktion gelöscht wurde.  <br/> |
|Export der Inhaltssuche entfernt  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Exportaktion für Inhaltssuche wurde gelöscht. Wenn die Exportaktion weniger als zwei Wochen alt war, wurden die Suchergebnisse gelöscht, die in den Microsoft Azure Speicherbereich hochgeladen wurden. Wenn die Exportaktion älter als 2 Wochen war, gibt dieses Ereignis an, dass nur die entsprechende Exportaktion gelöscht wurde.  <br/> |
|Element aus eDiscovery-Fall entfernt  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls entfernt.  <br/> |
|Vorschau Ergebnisse der Inhaltssuche entfernt  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Vorschau Aktion für Inhaltssuche wurde gelöscht.  <br/> |
|Entfernte Löschaktion für die Inhaltssuche ausgeführt  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Eine Löschaktion für Inhaltssuche wurde gelöscht.  <br/> |
|Suchbericht entfernt  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Die Aktion Exportbericht für Inhaltssuche wurde gelöscht.  <br/> |
|Analyse der Inhaltssuche gestartet  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Die Ergebnisse einer Inhaltssuche wurden für die Analyse in Advanced eDiscovery vorbereitet.  <br/> |
|Gestartete Inhaltssuche  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Eine Inhaltssuche wurde gestartet. Wenn Sie eine Inhaltssuche mithilfe der Benutzeroberfläche für Sicherheits #a0 Compliance Center erstellen oder ändern, wird die Suche automatisch gestartet. Wenn Sie mithilfe des Cmdlets **New-ComplianceSearch** oder **setComplianceSearch** eine Suche erstellen oder ändern, müssen Sie das Cmdlet **Start-ComplianceSearch** ausführen, um die Suche zu starten.  <br/> |
|Export der Inhaltssuche wurde gestartet.  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Ein Benutzer hat die Ergebnisse einer Inhaltssuche exportiert.  <br/> |
|Exportbericht gestartet  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Ein Benutzer hat einen Inhalts Suchbericht exportiert.  <br/> |
|Gestoppte Inhaltssuche  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Ein Benutzer hat eine Inhaltssuche angehalten.  <br/> |
  
## <a name="ediscovery-cmdlet-activities"></a>eDiscovery-Cmdlet-Aktivitäten

In der folgenden Tabelle sind die Cmdlet-Überwachungsprotokolleinträge aufgeführt, die protokolliert werden, wenn ein Administrator oder Benutzer eine eDiscovery-bezogene Aktivität mithilfe des Security #a0 Compliance Center ausführt oder das entsprechende Cmdlet in der Remote-PowerShell ausführt, die mit verbunden ist. das Sicherheits #a1 Compliance Center Ihrer Organisation. Beachten Sie, dass die detaillierten Informationen im Überwachungsprotokolleintrag für die in dieser Tabelle aufgeführten Cmdlet-Aktivitäten und die im vorherigen Abschnitt beschriebenen eDiscovery-Aktivitäten unterschiedlich sind. 
  
Wie bereits erwähnt, dauert es bis zu 24 Stunden, bis eDiscovery-Cmdlet-Aktivitäten in den Überwachungsprotokoll-Suchergebnissen angezeigt werden.
  
> [!TIP]
> Die Cmdlets in der Spalte **Operation** in der folgenden Tabelle sind mit dem entsprechenden Cmdlet-Hilfethema auf TechNet verknüpft. Wechseln Sie zum Cmdlet-Hilfethema, um eine Beschreibung der verfügbaren Parameter für jedes Cmdlet zu erhalten. Der Parameter und der Parameterwert, die mit einem Cmdlet verwendet wurden, sind im Überwachungsprotokolleintrag für jede Aktivität des eDiscovery-Cmdlets enthalten, die protokolliert wird. 
  
|**Anzeigename**|**Operation (Cmdlet)**|**Beschreibung**|
|:-----|:-----|:-----|
|Erstellt im eDiscovery-Fall halten  <br/> |[New-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |Für einen eDiscovery-Fall wurde ein Aufbewahrungsplatz erstellt. Ein Haltebereich kann mit oder ohne Angabe einer Inhaltsquelle erstellt werden. Wenn Inhaltsquellen angegeben werden, werden Sie im Überwachungsprotokolleintrag identifiziert.  <br/> |
|Löschsperre aus eDiscovery-Fall  <br/> |[Remove-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |Ein Aufbewahrungsplatz, der einem eDiscovery-Fall zugeordnet ist, wurde gelöscht. Durch das Löschen eines Haltestatus werden alle inhaltsspeicherorte aus dem Haltestatus freigegeben. Wenn Sie den Haltebereich löschen, werden auch die mit dem Haltestatus verknüpften Case Hold-Regeln gelöscht (siehe **Remove-CaseHoldRule** unten).  <br/> |
|Aufbewahrungszeit im eDiscovery-Fall geändert  <br/> |[Gruppe-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |Ein Haltebereich, der einer eDiscovery zugeordnet ist, wurde geändert. Mögliche Änderungen umfassen das Hinzufügen oder Entfernen von Inhaltsspeicherorten oder das Deaktivieren des Haltestatus.  <br/> |
|Erstellte Suchabfrage für eDiscovery Case Hold  <br/> |[New-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde erstellt.  <br/> |
|Gelöschte Suchabfrage für eDiscovery Case Hold  <br/> |[Remove-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde gelöscht. Das Entfernen der Abfrage aus dem Haltestatus ist häufig das Ergebnis des Löschens eines Haltestatus. Wenn eine halte-oder halte Abfrage gelöscht wird, werden die Aufbewahrungsorte für Inhalte freigegeben.  <br/> |
|Geänderte Suchabfrage für eDiscovery Case Hold  <br/> |[Gruppe-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |Ein abfragebasierter Haltebereich, der einem eDiscovery-Fall zugeordnet ist, wurde geändert. Mögliche Änderungen umfassen das Bearbeiten der Abfrage oder des Datumsbereichs für einen abfragebasierten Haltebereich.  <br/> |
|Erstellter eDiscovery-Fall  <br/> |[New-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |Es wurde ein eDiscovery-Fall erstellt. Wenn ein Fall erstellt wird, müssen Sie ihm nur einen Namen geben. Andere fallbezogene Aufgaben wie das Hinzufügen von Mitgliedern, das Erstellen von Haltebereichen und das Erstellen von Inhalts suchen, die dem Fall zugeordnet sind, führen zu zusätzlichen Ereignissen, die protokolliert werden.  <br/> |
|Gelöschter eDiscovery-Fall  <br/> |[Remove-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |Ein eDiscovery-Fall wurde gelöscht. Beachten Sie, dass alle dem Fall zugeordneten Halterungen entfernt werden müssen, bevor der Fall gelöscht werden kann.  <br/> |
|Geänderter eDiscovery-Fall  <br/> |[Gruppe-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |Ein eDiscovery-Fall wurde geändert. Zu den Änderungen gehören das Schließen eines offenen Falls oder das erneute Öffnen eines geschlossenen Falls.  <br/> |
|Mitglied zu eDiscovery-Fall hinzugefügt  <br/> |[Add-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls hinzugefügt. Als Mitglied eines Falles kann ein Benutzer verschiedene fallbezogene Aufgaben ausführen, je nachdem, ob ihm die erforderlichen Berechtigungen zugewiesen wurden.  <br/> |
|Element aus eDiscovery-Fall entfernt  <br/> |[Remove-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |Ein Benutzer wurde als Mitglied eines eDiscovery-Falls entfernt.  <br/> |
|Geänderte eDiscovery-Fall Mitgliedschaft  <br/> |[Update-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |Die Mitgliederliste eines eDiscovery-Falls wurde geändert. Diese Aktivität wird protokolliert, wenn alle Mitglieder durch eine Gruppe neuer Benutzer ersetzt werden. Wenn ein einzelnes Element hinzugefügt oder entfernt wird, wird der Vorgang **Add-ComplianceCaseMember** oder **Remove-ComplianceCaseMember** protokolliert.  <br/> |
|Erstellte Inhaltssuche  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |Eine neue Inhaltssuche wurde erstellt.  <br/> |
|Suche nach gelöschten Inhalten  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |Eine vorhandene Inhaltssuche wurde gelöscht.  <br/> |
|Geänderte Inhaltssuche  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |Eine vorhandene Inhaltssuche wurde geändert. Zu den Änderungen können das Hinzufügen oder Entfernen von Inhaltsspeicherorten, die durchsucht werden, und Bearbeiten der Suchabfrage gehören.  <br/> |
|Gestartete Inhaltssuche  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |Eine Inhaltssuche wurde gestartet. Wenn Sie eine Inhaltssuche mithilfe der Benutzeroberfläche für Sicherheits #a0 Compliance Center erstellen oder ändern, wird die Suche automatisch gestartet. Wenn Sie mithilfe des Cmdlets **New-ComplianceSearch** oder **setComplianceSearch** eine Suche erstellen oder ändern, müssen Sie das Cmdlet **Start-ComplianceSearch** ausführen, um die Suche zu starten.  <br/> |
|Gestoppte Inhaltssuche  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |Eine Inhaltssuche, die gerade durchlaufen wurde, wurde angehalten.  <br/> |
|Aktion "Inhaltssuche erstellt"  <br/> |[New-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |Eine Inhaltssuche-Aktion wurde erstellt. Zu den Aktionen bei der Inhaltssuche gehören die Vorschau der Suchergebnisse, das Exportieren von Suchergebnissen, das Vorbereiten der Suchergebnisse für die Analyse in Office 365 Advanced eDiscovery und das dauerhafte Löschen von Elementen, die den Suchkriterien einer Inhaltssuche entsprechen.  <br/> |
|Aktion "gelöschte Inhaltssuche"  <br/> |[Remove-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |Eine Inhaltssuche-Aktion wurde gelöscht.  <br/> |
|Erstellter Such Berechtigungsfilter  <br/> |[New-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |Es wurde ein Such Berechtigungsfilter erstellt.  <br/> |
|Filter für gelöschte Suchberechtigungen  <br/> |[Remove-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |Ein Such Berechtigungsfilter wurde gelöscht.  <br/> |
|Geänderter Such Berechtigungsfilter  <br/> |[Gruppe-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |Ein Such Berechtigungsfilter wurde geändert.  <br/> |
|Erstellter eDiscovery-Administrator  <br/> |[Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |Ein Benutzer wurde in Ihrer Organisation als eDiscovery-Administrator hinzugefügt.  <br/> |
|Gelöschter eDiscovery-Administrator  <br/> |[Remove-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |Ein eDiscovery-Administrator wurde aus Ihrer Organisation gelöscht.  <br/> |
|Geänderte eDiscovery-Administrator Mitgliedschaft  <br/> |[Update-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |Die Liste der eDiscovery-Administratoren in Ihrer Organisation wurde geändert. Diese Aktivität wird protokolliert, wenn die Liste der eDiscovery-Administratoren durch eine Gruppe neuer Benutzer ersetzt wird. Wenn ein einzelner Benutzer hinzugefügt oder entfernt wird, wird der Vorgang **Add-eDiscoveryCaseAdmin** oder **Remove-eDiscoveryCaseAdmin** protokolliert.  <br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>Detaillierte Eigenschaften für eDiscovery-Aktivitäten

In der folgenden Tabelle werden die Eigenschaften beschrieben, die enthalten sind, wenn Sie auf der **Detail** Seite auf **Weitere Informationen** für eine eDiscovery-Aktivität klicken, die in den Suchergebnissen aufgeführt ist. Diese Eigenschaften sind auch in der CSV-Datei enthalten, wenn Sie die Überwachungsprotokoll-Suchergebnisse exportieren. Beachten Sie, dass ein Überwachungsprotokolleintrag für eine eDiscovery-Aktivität nicht alle unten aufgeführten detaillierten Eigenschaften enthält. 
  
> [!TIP]
> Wenn Sie die Suchergebnisse exportieren, enthält die CSV-Datei eine Spalte mit dem Namen **Detail**, die die in der folgenden Tabelle in einer mehrwertigen Eigenschaft beschriebenen detaillierten Eigenschaften enthält. Sie können die Power Query-Funktion in Excel verwenden, um diese Spalte in mehrere Spalten aufzuteilen, damit jede Eigenschaft eine eigene Spalte aufweist. Auf diese Weise können Sie eine oder mehrere dieser Eigenschaften sortieren und filtern. Weitere Informationen finden Sie im Abschnitt "Exportieren der Suchergebnisse in eine Datei" im [Überwachungsprotokoll durchsuchen](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file). 
  
|**Eigenschaft**|**Beschreibung**|
|:-----|:-----|
|Fall  <br/> |Die Identität (GUID) des eDiscovery-Falls, der erstellt, geändert oder gelöscht wurde.  <br/> |
|ClientApplication  <br/> |eDiscovery-Cmdlet-Aktivitäten haben einen Wert von **EMC** für diese Eigenschaft. Dies weist darauf hin, dass die Aktivität mithilfe der Benutzeroberfläche für Sicherheits #a0 Compliance Center oder durch Ausführen des Cmdlets in PowerShell ausgeführt wurde.  <br/> |
|ClientIP  <br/> |Die IP-Adresse des Geräts, das verwendet wurde, als die Aktivität protokolliert wurde. Die IP-Adresse wird im Adressformat IPv4 oder IPv6 angezeigt.  <br/> |
|ClientRequestId  <br/> | Für eDiscovery-Aktivitäten ist diese Eigenschaft normalerweise leer.  <br/> |
|CmdletVersion  <br/> |Die Buildnummer für die Version des Sicherheits #a0 Compliance Centers, das in Ihrer Organisation aktiv ist.  <br/> |
|CreationTime  <br/> |Das Datum und die Uhrzeit in koordinierter Weltzeit (Coordinated Universal Time, UTC), als die eDiscovery-Aktivität abgeschlossen wurde.  <br/> |
|EffectiveOrganization  <br/> |Der Name der Office 365 Organisation.  <br/> |
|ExchangeLocations  <br/> |Die Exchange Online Postfächer, die in einer Inhaltssuche enthalten sind oder in einem eDiscovery-Fall in den Haltebereich gestellt werden.  <br/> |
|Ausschlüsse  <br/> |Post Fach Standorte oder Websitespeicher Orte, die von einer Inhaltssuche oder einem Haltestatus in einem eDiscovery-Fall ausgeschlossen werden.  <br/> |
|ExtendedProperties  <br/> |Zusätzliche Eigenschaften aus einer Inhaltssuche, einer Aktion für Inhaltssuche oder halten in einem eDiscovery-Fall, beispielsweise die Objekt-GUID und die entsprechenden Cmdlet-und Cmdlet-Parameter, die beim Ausführen der Aktivität verwendet wurden.  <br/> |
|Id  <br/> |Die ID des Berichts Eintrags. Die ID identifiziert den Überwachungsprotokolleintrag eindeutig.  <br/> |
|NonPIIParameters  <br/> |Eine Liste der Parameter (ohne Werte), die mit dem Cmdlet verwendet wurden, das in der Operation-Eigenschaft angegeben wurde. Die in dieser Eigenschaft aufgeführten Parameter sind identisch mit den in der Parameters-Eigenschaft aufgeführten Parametern.  <br/> |
|ObjectId  <br/> |Die GUID oder der Name des Objekts (beispielsweise eine Inhaltssuche oder ein eDiscovery-Fall), die von der in der Operation-Eigenschaft aufgeführten Aktivität erstellt, geändert oder gelöscht wurde. Dieses Objekt wird auch in der Spalte Element in den Suchergebnissen des Überwachungsprotokolls identifiziert.  <br/> |
|ObjectType  <br/> |Der Typ des eDiscovery-Objekts, das vom Benutzer erstellt, gelöscht oder geändert wurde; beispielsweise eine Aktion zur Inhaltssuche (Vorschau, Export oder Bereinigung), einen eDiscovery-Fall oder eine Inhaltssuche.  <br/> |
|Vorgang  <br/> |Der Name des Vorgangs, der der ausgeführten eDiscovery-Aktivität entspricht.  <br/> |
|OrganizationId  <br/> |Die GUID für Ihre Office 365 Organisation.  <br/> |
|Parameter  <br/> |Der Name und der Wert für die Parameter, die mit dem entsprechenden Cmdlet verwendet wurden.  <br/> |
|PublicFolderLocations  <br/> |Die Speicherorte für Öffentliche Ordner in Exchange Online, die in einer Inhaltssuche enthalten sind oder in einem eDiscovery-Fall in den Haltebereich gestellt werden.  <br/> |
|Abfrage  <br/> |Die der Aktivität zugeordnete Suchabfrage, beispielsweise eine Inhaltssuche oder ein abfragebasierter Haltestatus.  <br/> |
|RecordType  <br/> |Der vom Datensatz angegebene Vorgangstyp. Der Wert **18** gibt ein Ereignis im Zusammenhang mit einer Aktivität an, die im Abschnitt [Aktivitäten des eDiscovery-Cmdlets](#ediscovery-cmdlet-activities) aufgeführt ist. Der Wert **24** gibt ein Ereignis im Zusammenhang mit einer Aktivität an, die im Abschnitt [Vorgehensweise zum Suchen und Anzeigen von eDiscovery-Aktivitäten](#how-to-search-for-and-view-ediscovery-activities) aufgeführt ist.  <br/> |
|ResultStatus  <br/> |Gibt an, ob die Aktion (in der Eigenschaft "Operation" angegeben) erfolgreich war oder nicht.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Gibt an, dass es sich bei der Aktivität um ein Sicherheits #a0 Compliance Center-Ereignis handelt. Für diese Eigenschaft wird für alle eDiscovery-Aktivitäten der Wert **0 (null** ) verwendet.  <br/> |
|SharepointLocations  <br/> |Die SharePoint Online Websites, die in einer Inhaltssuche enthalten sind oder in einem eDiscovery-Fall in den Haltebereich gestellt werden.  <br/> |
|StartTime  <br/> |Das Datum und die Uhrzeit in koordinierter Weltzeit (Coordinated Universal Time, UTC), als die eDiscovery-Aktivität gestartet wurde.  <br/> |
|UserId  <br/> |Der Benutzer, der die Aktivität ausgeführt hat (angegeben in der Operation-Eigenschaft), die dazu geführt hat, dass der Datensatz protokolliert wurde. Beachten Sie, dass Datensätze für eDiscovery-Aktivitäten, die von Systemkonten (wie NT-AUTHORITY\SYSTEM) ausgeführt werden, ebenfalls im Überwachungsprotokoll enthalten sind.  <br/> |
|UserKey  <br/> |Eine alternative ID für den in der UserId-Eigenschaft identifizierten Benutzer. Für eDiscovery-Aktivitäten ist der Wert für diese Eigenschaft in der Regel identisch mit der UserId-Eigenschaft.  <br/> |
|UserServicePlan  <br/> |Das Office 365 Abonnement, das von Ihrer Organisation verwendet wird. Für eDiscovery-Aktivitäten ist diese Eigenschaft normalerweise leer.  <br/> |
|UserType  <br/> |Der Typ des Benutzers, der den Vorgang ausgeführt hat. Die folgenden Werte geben den Benutzertyp an.  <br/> 0 ein regulärer Benutzer. 2 ein Administrator in Ihrer Office 365 Organisation. 3 ein Microsoft Datacenter-Administrator-oder Datacenter-Systemkonto. 4 ein Systemkonto. 5 eine Anwendung. 6 ein Dienstprinzipal. |
|Version  <br/> |Gibt die Versionsnummer der Aktivität an (identifiziert durch die Operation-Eigenschaft), die protokolliert wird.  <br/> |
|Arbeitslast  <br/> |Der Office 365 Dienst, in dem die Aktivität aufgetreten ist. Für eDiscovery-Aktivitäten lautet der Wert **SecurityComplianceCenter**.  <br/> |
