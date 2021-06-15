---
title: Bewerten des Berichts Microsoft 365 aktive Benutzer
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
description: Erfahren Sie, wie Sie einen Bericht "Aktive Benutzer" über das Dashboard Microsoft 365 Berichte im Microsoft 365 Admin Center abrufen und herausfinden, wie viele Produktlizenzen verwendet werden.
ms.openlocfilehash: 8ea9feeb18cb1885023ec14f1ffb4d77b2775877
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924371"
---
# <a name="assess-the-microsoft-365-active-users-report"></a>Bewerten des Berichts Microsoft 365 aktive Benutzer

Das Dashboard Microsoft 365 **Berichte** zeigt Ihnen die Aktivitätsübersicht für alle Produkte in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Sie können beispielsweise den Bericht **Aktive Benutzer** verwenden, um herauszufinden, wie viele Produktlizenzen von einzelnen Personen in Ihrem Unternehmen verwendet werden, und einen Drilldown zu Informationen darüber ausführen, welche Produkte von den jeweiligen Benutzern verwendet werden. Dieser Bericht kann Administratoren beim Ermitteln von unzureichend genutzten Produkten oder nicht ausgelasteten Benutzern helfen, die möglicherweise zusätzliche Schulungen oder Informationen benötigen. 
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtsleser in Microsoft 365 oder Exchange, SharePoint, Teams Dienst, Teams Kommunikation oder Skype for Business Administrator sein, um Berichte anzeigen zu können.  

## <a name="how-to-get-to-the-active-users-report"></a>Informationen zum Abrufen des Berichts für aktive Benutzer

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **"Weitere Anzeigen"** auf der Karte "Aktive Benutzer – Microsoft 365 Dienste".

## <a name="interpret-the-active-users-report"></a>Interpretieren des Berichts für aktive Benutzer

Sie können aktive Benutzer im bericht Office 365 anzeigen, indem Sie die Registerkarte **"Aktive Benutzer"** auswählen.<br/>![Microsoft 365 Berichte – Microsoft Office 365 aktive Benutzer.](../../media/56fe2e54-76ad-49e5-886f-1344c2697258.png)

- Im Bericht Aktive Benutzer werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag anzeigen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).

- Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.

- Im Diagramm "Benutzer" werden täglich aktive Benutzer im Berichtszeitraum nach Produkt getrennt angezeigt.
Das Diagramm "Aktivität" zeigt die Anzahl der täglichen Aktivitäten im Berichtszeitraum nach Produkt getrennt an.
Das Diagramm Dienste zeigt Ihnen die Anzahl der Benutzer nach Aktivitätstyp und Dienst an.

- Im Diagramm Benutzer zeigt die X-Achse den ausgewählten Berichtszeitraum und auf der Y-Achse werden die täglich aktiven Benutzer getrennt und nach Lizenztyp codiert angezeigt.
Im Diagramm Aktivität zeigt die X-Achse den ausgewählten Berichtszeitraum an, und auf der y-Achse wird die Anzahl der täglichen Aktivitäten getrennt und die Farbe nach Lizenztyp codiert angezeigt.
Im Aktivitätsdiagramm Dienste zeigt die X-Achse die einzelnen Dienste an, für die Ihre Benutzer im festgelegten Zeitraum aktiviert sind, während die Y-Achse die Anzahl der Benutzer nach farblich gekennzeichnetem Aktivitätsstatus angibt.

- Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert.

- Sie können die Berichtsdaten auch in eine Excel .csv Datei exportieren, indem Sie den Link "Exportieren" auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.

- Mithilfe von Spaltensteuerelementen können Sie ändern, welche Informationen im Raster angezeigt werden.
Wenn Ihr Abonnement von 21Vianet betrieben wird, wird Yammer nicht angezeigt.



Wenn die Richtlinien Ihrer Organisation eine Anzeige von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt **Ausblenden von Details auf Benutzerebene** in [Aktivitätsberichte im Microsoft 365 Admin Center](activity-reports.md).  
