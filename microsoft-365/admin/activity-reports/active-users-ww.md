---
title: Microsoft 365-Berichte im Admin Center – aktive Benutzer
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: fc1cf1d0-cd84-43fd-adb7-a4c4dfa8112d
description: Erfahren Sie, wie Sie einen Bericht über aktive Benutzer mithilfe des Microsoft 365 Reports-Dashboards im Microsoft 365 Admin Center erhalten und erfahren, wie viele Produktlizenzen verwendet werden.
ms.openlocfilehash: 8ca9e32a36be068ada8b59ce0f456a82541be8d9
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611924"
---
# <a name="microsoft-365-reports-in-the-admin-center---active-users"></a>Microsoft 365-Berichte im Admin Center – aktive Benutzer

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Sie können beispielsweise den Bericht **Aktive Benutzer** verwenden, um herauszufinden, wie viele Produktlizenzen von einzelnen Personen in Ihrem Unternehmen verwendet werden, und einen Drilldown zu Informationen darüber ausführen, welche Produkte von den jeweiligen Benutzern verwendet werden. Dieser Bericht kann Administratoren beim Ermitteln von unzureichend genutzten Produkten oder nicht ausgelasteten Benutzern helfen, die möglicherweise zusätzliche Schulungen oder Informationen benötigen. 
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  

## <a name="how-to-get-to-the-active-users-report"></a>Informationen zum Abrufen des Berichts für aktive Benutzer

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **mehr anzeigen** der aktiven Benutzer – Microsoft 365-Dienst Karte.

## <a name="interpret-the-active-users-report"></a>Interpretieren des Berichts für aktive Benutzer

Sie können aktive Benutzer im Bericht Office 365 anzeigen, indem Sie die Registerkarte **aktive Benutzer** auswählen.<br/>![Microsoft 365 Reports-Microsoft Office 365 aktive Benutzer.](../../media/56fe2e54-76ad-49e5-886f-1344c2697258.png)

|||
|:-----|:-----|
|1.  <br/> |Im Bericht **Aktive Benutzer** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag anzeigen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.  <br/> |
|3.  <br/> |Das **Benutzer** Diagramm zeigt Ihnen tägliche aktive Benutzer in der Berichtsperiode, die nach Produkt getrennt sind.  <br/> Das **Aktivitäts** Diagramm zeigt die Anzahl der täglichen Aktivitäten in der Berichtsperiode, getrennt nach Produkt. <br/> Das Diagramm **Dienste** zeigt Ihnen die Anzahl der Benutzer nach Aktivitätstyp und Dienst an.  <br/> |
|4.  <br/> | Im Diagramm **Benutzer** zeigt die x-Achse den ausgewählten Berichtszeitraum an, und die y-Achse zeigt die getrennten und farblich codierten täglichen aktiven Benutzer nach Lizenztyp an.  <br/>  Im **Aktivitäts**   Diagramm zeigt die x-Achse den ausgewählten Berichtszeitraum an, und die y-Achse zeigt die Anzahl der täglichen Aktivitäten getrennt und die Farbcodierung nach Lizenztyp an. <br/> Im Aktivitätsdiagramm **Dienste** zeigt die X-Achse die einzelnen Dienste an, für die Ihre Benutzer im festgelegten Zeitraum aktiviert sind, während die Y-Achse die Anzahl der Benutzer nach farblich gekennzeichnetem Aktivitätsstatus angibt.  <br/> |
|5.  <br/> |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert.  <br/> |
|6.  <br/> |Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> |
|7.  <br/> |Mithilfe von Spaltensteuerelementen können Sie ändern, welche Informationen im Raster angezeigt werden.  <br/> Wenn Ihr Abonnement von 21Vianet betrieben wird, wird Yammer nicht angezeigt. <br/> <br/> |
|||

Wenn die Richtlinien Ihrer Organisation eine Anzeige von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt **Ausblenden von Details auf Benutzerebene** in [Aktivitätsberichte im Microsoft 365 Admin Center](activity-reports.md).  
