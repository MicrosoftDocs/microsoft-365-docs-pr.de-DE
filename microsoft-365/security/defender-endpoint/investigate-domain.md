---
title: Untersuchen von Microsoft Defender for Endpoint-Domänen
description: Verwenden Sie die Untersuchungsoptionen, um zu sehen, ob Geräte und Server mit bösartigen Domänen kommuniziert haben.
keywords: Untersuchen von Domäne, Domäne, bösartiger Domäne, Microsoft Defender for Endpoint, Warnung, URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7826229ba67384137c033745a5b85e557fc9c4a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933469"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Untersuchen einer Domäne, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

Untersuchen Sie eine Domäne, um zu ermitteln, ob Geräte und Server in Ihrem Unternehmensnetzwerk mit einer bekannten bösartigen Domäne kommuniziert haben.

Sie können eine Domäne untersuchen, indem Sie das Suchfeature verwenden oder über die Gerätezeitachse auf einen Domänenlink **klicken.**

Informationen aus den folgenden Abschnitten finden Sie in der URL-Ansicht:

- URL-Details, Kontakte, Nameserver
- Warnungen im Zusammenhang mit dieser URL 
- URL in der Organisation
- Zuletzt beobachtete Geräte mit URL

## <a name="url-worldwide"></a>URL weltweit

Der **Abschnitt URL Worldwide** enthält die URL, einen Link zu weiteren Details unter Whois, die Anzahl der damit verbundenen offenen Vorfälle und die Anzahl der aktiven Warnungen.

## <a name="incident"></a>Vorfall

Die **Karte Vorfall** zeigt ein Balkendiagramm aller aktiven Warnungen bei Vorfällen in den letzten 180 Tagen an.

## <a name="prevalence"></a>Prävalenz

Die **Prävalenzkarte** enthält Details zur Verbreitung der URL innerhalb der Organisation über einen bestimmten Zeitraum.

Obwohl der Standardzeitraum die letzten 30 Tage ist, können Sie den Bereich anpassen, indem Sie den nach unten zeigenden Pfeil in der Ecke der Karte auswählen. Der kürzeste verfügbare Bereich ist für die Verbreitung über den letzten Tag, während der längste Bereich über die letzten 6 Monate liegt.

## <a name="alerts"></a>Warnungen

Die **Registerkarte Warnungen** enthält eine Liste der Warnungen, die der URL zugeordnet sind. Die hier gezeigte Tabelle ist eine gefilterte Version der Warnungen, die auf dem Warteschleifenbildschirm angezeigt wird und nur Warnungen enthält, die der Domäne zugeordnet sind, ihren Schweregrad, status, den zugeordneten Vorfall, die Klassifizierung, den Untersuchungsstatus und vieles mehr.

Die Registerkarte Warnungen kann angepasst werden, um  mehr oder weniger Informationen anzuzeigen, indem Sie im Aktionsmenü oberhalb der Spaltenüberschriften Spalten anpassen auswählen. Die Anzahl der angezeigten Elemente kann auch angepasst werden, indem Elemente pro **Seite im** gleichen Menü ausgewählt werden.

## <a name="observed-in-organization"></a>Beobachtet in der Organisation

Die **Registerkarte Beobachtet in der** Organisation bietet eine chronologische Ansicht der Ereignisse und zugeordneten Warnungen, die in der URL beobachtet wurden. Diese Registerkarte enthält eine Zeitachse und eine anpassbare Tabelle, in der Ereignisdetails wie Uhrzeit, Gerät und eine kurze Beschreibung der Ereignisse aufgeführt sind. 

Sie können Ereignisse aus unterschiedlichen Zeiträumen anzeigen, indem Sie die Datumsangaben in die Textfelder oberhalb der Tabellenkopfzeilen eingeben. Sie können den Zeitraum auch anpassen, indem Sie unterschiedliche Bereiche der Zeitachse auswählen.

**Untersuchen einer Domäne:**

1. Wählen **Sie url** im **Dropdownmenü Suchleiste** aus.
2. Geben Sie die URL in das Feld **Suche** ein.
3. Klicken Sie auf das Suchsymbol, oder drücken Sie die **EINGABETASTE.** Details zur URL werden angezeigt. Hinweis: Suchergebnisse werden nur für URLs zurückgegeben, die in der Kommunikation von Geräten in der Organisation beobachtet werden.
4. Verwenden Sie die Suchfilter, um die Suchkriterien zu definieren. Sie können auch das Zeitachsensuchfeld verwenden, um die angezeigten Ergebnisse aller Geräte in der Organisation zu filtern, die bei der Kommunikation mit der URL, der der Kommunikation zugeordneten Datei und dem letzten beobachteten Datum beobachtet wurden.
5. Wenn Sie auf einen der Gerätenamen klicken, werden Sie zur Ansicht dieses Geräts angezeigt, in der Sie gemeldete Warnungen, Verhaltensweisen und Ereignisse weiterhin untersuchen können.

## <a name="related-topics"></a>Verwandte Themen
- [Anzeigen und Organisieren der Microsoft Defender for Endpoint Alerts-Warteschlange](alerts-queue.md)
- [Verwalten von Microsoft Defender for Endpoint-Warnungen](manage-alerts.md)
- [Untersuchen von Microsoft Defender for Endpoint-Warnungen](investigate-alerts.md)
- [Untersuchen einer Datei, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist](investigate-files.md)
- [Untersuchen von Geräten in der Microsoft Defender for Endpoint Devices-Liste](investigate-machines.md)
- [Untersuchen einer einer Microsoft Defender for Endpoint-Warnung zugeordneten IP-Adresse](investigate-ip.md)
- [Untersuchen eines Benutzerkontos in Microsoft Defender for Endpoint](investigate-user.md)
