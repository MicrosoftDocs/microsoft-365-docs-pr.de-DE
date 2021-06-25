---
title: Microsoft 365 Berichte im Admin Center – Microsoft-Browsernutzung
ms.author: waxiaoyu
author: sarahwxy
manager: scotv
audience: Admin
ms.topic: article
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
description: Erfahren Sie, wie Sie einen Microsoft-Browsernutzungsbericht über das Dashboard Microsoft 365 Berichte im Microsoft 365 Admin Center abrufen.
ms.openlocfilehash: f2d8d8347e7b71375958c56f6649fbb911155d46
ms.sourcegitcommit: b42dd3e706ebf9638cd893b35f75eaa56dd8fd7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "53125414"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-browser-usage"></a>Microsoft 365 Berichte im Admin Center – Microsoft-Browsernutzung

Das Dashboard Microsoft 365 **Berichte** zeigt Ihnen eine Aktivitätsübersicht über alle Produkte in Ihrer Organisation. Sie können einen Drilldown in einzelne Berichte auf Produktebene ausführen, um Ihnen detailliertere Einblicke in die Aktivitäten in den einzelnen Produkten zu geben. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Im Microsoft-Browsernutzungsbericht erhalten Sie Einblicke in Internet Explorer, Vorgängerversion von Microsoft Edge und neue Microsoft Edge Nutzung. Die Nutzungsberichterstellung basiert auf Microsoft 365 Onlinediensten, auf die mithilfe eines Microsoft-Browsers zugegriffen wird.

 > [!NOTE]
 > Sie müssen ein globaler Administrator, globaler Leser oder Berichtsleser in Microsoft 365 oder ein Exchange-, SharePoint- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.

## <a name="how-to-get-to-the-microsoft-browser-usage-report"></a>So gelangen Sie zum Microsoft Browser-Nutzungsbericht

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **"Weitere Anzeigen"** auf der Microsoft Browser-Nutzungskarte.

## <a name="how-to-notify-users-to-upgrade-their-browser"></a>So benachrichtigen Sie Benutzer, ihren Browser zu aktualisieren

![Microsoft-Browsernutzungsbericht – Aktionsfluss](../../media/1ef4eb08-18b8-4dda-aa15-1aad013ecd70.png)

Globale Administratoren können sich für das Senden von Nachrichten an Benutzer anmelden, die Microsoft 365 Dienste in Edge Legacy (nicht unterstützt) und Internet Explorer (bald nicht unterstützt) verwenden. Diese Zielnachricht benachrichtigt Benutzer, dass die Unterstützung für diese Browser bald beendet wird, und sie enthält Links zu einem Supportartikel mit Informationen zu Microsoft Edge und einfachen Schritten zum Wechseln von Browsern. 

Dieses Feature finden Sie auf der Berichtsseite. Nachdem die Nachricht erstellt wurde, werden die Benutzer mit der bis zum 17. August 2021 angegebenen Häufigkeit benachrichtigt. Sie können dieses Feature jederzeit deaktivieren, um das Senden von Benachrichtigungen an Benutzer zu beenden. Um erneut mit dem Senden von Benachrichtigungen zu beginnen, aktivieren Sie das Feature wieder.

Weitere Informationen finden Sie unter [Microsoft Edge Hilfe & Lernens.](https://support.microsoft.com/microsoft-edge)

## <a name="interpret-the-microsoft-browser-usage-report"></a>Interpretieren des Microsoft-Browsernutzungsberichts

![Microsoft-Browsernutzungsbericht](../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png)

|Element|Beschreibung|
 |:-----|:-----|
 |1. <br/> |Der **Microsoft-Browsernutzungsbericht** kann für Trends der letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt werden.  <br/> |
 |2. <br/> |Die Daten in den einzelnen Berichten umfassen in der Regel bis zu den letzten sieben Tagen. <br/> |
 |3. <br/> |Im Diagramm **Täglich aktive** Benutzer wird die anzahl der täglichen Benutzer für Microsoft Edge, Vorgängerversion von Microsoft Edge und Internet Explorer angezeigt, wenn sie für den Zugriff auf Microsoft 365 Dienste verwendet wird. <br/> |
 |4.<br/>|Das Diagramm **"Aktive Benutzer"** zeigt die Gesamtanzahl der Benutzer an, die Microsoft Edge, Vorgängerversion von Microsoft Edge und Internet Explorer verwenden, wenn sie für den Zugriff auf Microsoft 365 Dienste über den ausgewählten Zeitraum verwendet werden.<br/>|
 |5.<br/>|Die Tabelle zeigt eine Auflistung der Daten nach Benutzerebene. Sie können Spalten zur Tabelle hinzufügen oder aus der Tabelle entfernen.  <br/><br/>**Der Benutzername** ist die E-Mail-Adresse des Benutzers, der über Microsoft-Browser mit Microsoft 365 Diensten verbunden ist.<br><br/>**Wird Microsoft Edge verwendet,** wird ein Teilstrich angezeigt, wenn der Benutzer Microsoft Edge zum Herstellen einer Verbindung mit Microsoft 365 Diensten verwendet hat.<br/><br/>**Wird Vorgängerversion von Microsoft Edge verwendet,** wird eine Teilstrichmarkierung angezeigt, wenn der Benutzer Vorgängerversion von Microsoft Edge zum Herstellen einer Verbindung mit Microsoft 365 Diensten verwendet hat.<br/><br/>**Der verwendete Internet Explorer** zeigt eine Teilstrichmarkierung an, wenn der Benutzer Internet Explorer zum Herstellen einer Verbindung mit Microsoft 365 Diensten verwendet hat. |
 |6.<br/>|Wählen Sie das Symbol **"Spalten auswählen"** aus, um Dem Bericht Spalten hinzuzufügen oder daraus zu entfernen.|
 |7.<br/>|Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten für alle Benutzer exportiert, und Sie können einfache Aggregations-, Sortier- und Filtervorgänge zur weiteren Analyse durchführen. Wenn Sie weniger als 100 Benutzer haben, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie mehr als 100 Benutzer haben, müssen Sie zum Filtern und Sortieren die Daten exportieren.|
