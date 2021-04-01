---
title: Zeitzoneneinstellungen für Microsoft Defender Security Center
description: Verwenden Sie die hier enthaltenen Informationen, um die Microsoft Defender Security Center-Zeitzoneneinstellungen zu konfigurieren und Lizenzinformationen anzeigen.
keywords: Einstellungen, Microsoft Defender, Cybersecurity Threat Intelligence, Advanced Threat Protection, Zeitzone, utc, Ortszeit, Lizenz
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e395420b92c29977f1c802d1c10683492c1aba10
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470465"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a>Zeitzoneneinstellungen für Microsoft Defender Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

Verwenden Sie **das Zeitzonenmenü** ![ Zeitzoneneinstellungen ](images/atp-time-zone.png) symbol1, um die Zeitzone zu konfigurieren und Lizenzinformationen anzuzeigen.

## <a name="time-zone-settings"></a>Zeitzoneneinstellungen
Der Zeitaspekt ist wichtig bei der Bewertung und Analyse von wahrgenommenen und tatsächlichen Cyberangriffen.

Cyberforensische Untersuchungen beruhen häufig auf Zeitstempeln, um die Abfolge von Ereignissen zu verbinden. Es ist wichtig, dass Ihr System die richtigen Zeitzoneneinstellungen widerspiegelt.

Microsoft Defender for Endpoint kann entweder koordinierte Weltzeit (UTC) oder Ortszeit anzeigen.

Ihre aktuelle Zeitzoneneinstellung wird im Menü Microsoft Defender for Endpoint angezeigt. Sie können die angezeigte Zeitzone im **Menü** Zeitzone ändern.

![Zeitzoneneinstellungen (Symbol2)](images/atp-time-zone-menu.png).

### <a name="utc-time-zone"></a>UTC-Zeitzone
Microsoft Defender for Endpoint verwendet standardmäßig UTC-Zeit.

Wenn Sie die Microsoft Defender for Endpoint-Zeitzone auf UTC festlegen, werden alle Systemzeitstempel (Warnungen, Ereignisse und andere) in UTC für alle Benutzer angezeigt. Dies kann Sicherheitsanalysten, die an verschiedenen Orten auf der ganzen Welt arbeiten, dabei helfen, die gleichen Zeitstempel zu verwenden, während Sie Ereignisse untersuchen.

### <a name="local-time-zone"></a>Lokale Zeitzone
Sie können festlegen, dass Microsoft Defender for Endpoint lokale Zeitzoneneinstellungen verwendet. Alle Warnungen und Ereignisse werden mithilfe Ihrer lokalen Zeitzone angezeigt.

Die lokale Zeitzone wird aus den regionalen Einstellungen Ihres Geräts übernommen. Wenn Sie Ihre regionalen Einstellungen ändern, ändert sich auch die Microsoft Defender for Endpoint-Zeitzone. Wenn Sie diese Einstellung auswählen, werden die in Microsoft Defender for Endpoint angezeigten Zeitstempel für alle Microsoft Defender for Endpoint-Benutzer an der Ortszeit ausgerichtet. Analysten, die sich an verschiedenen globalen Standorten befinden, sehen nun die Microsoft Defender for Endpoint-Warnungen entsprechend ihren regionalen Einstellungen.

Die Verwendung der Ortszeit kann hilfreich sein, wenn sich die Analysten an einem einzigen Standort befinden. In diesem Fall ist es möglicherweise einfacher, Ereignisse mit der Ortszeit zu korrelieren, z. B. wenn ein lokaler Benutzer auf einen verdächtigen E-Mail-Link geklickt hat.

### <a name="set-the-time-zone"></a>Festlegen der Zeitzone
Die Microsoft Defender for Endpoint-Zeitzone ist standardmäßig auf UTC festgelegt.
Durch festlegen der Zeitzone werden auch die Zeiten für alle Microsoft Defender for Endpoint-Ansichten geändert.
So legen Sie die Zeitzone ein:

1. Klicken Sie **auf das Zeitzonenmenü** ![ Zeitzoneneinstellungen Symbol3 ](images/atp-time-zone.png) .
2. Wählen Sie **den Zeitzonen-UTC-Indikator** aus.
3. Wählen **Sie Zeitzone UTC** oder Ihre lokale Zeitzone aus, z. B. -7:00.

### <a name="regional-settings"></a>Regionale Einstellungen
Verwenden Sie regionale Einstellungen für Internet Explorer (IE) und Microsoft Edge (Edge), um unterschiedliche Datumsformate für Microsoft Defender for Endpoint anzuwenden. Wenn Sie einen anderen Browser wie Google Chrome verwenden, führen Sie die erforderlichen Schritte aus, um die Zeit- und Datumseinstellungen für diesen Browser zu ändern. 


**Internet Explorer (IE) und Microsoft Edge**

IE und Microsoft  Edge verwenden die Region-Einstellungen, die in der Systemsteuerung in der Option **Uhren,** Sprache und Region konfiguriert sind. 


#### <a name="known-issues-with-regional-formats"></a>Bekannte Probleme mit regionalen Formaten

**Datums- und Uhrzeitformate**<br>
Es gibt einige bekannte Probleme mit den Uhrzeit- und Datumsformaten. Wenn Sie Ihre regionalen Einstellungen auf andere als die unterstützten Formate konfigurieren, gibt das Portal möglicherweise ihre Einstellungen nicht richtig wieder.

Die folgenden Datums- und Uhrzeitformate werden unterstützt:
- Datumsformat MM/dd/yyyy
- Datumsformat dd/MM/yyyy
- Zeitformat hh:mm:ss (12-Stunden-Format)

Die folgenden Datums- und Uhrzeitformate werden derzeit nicht unterstützt:
- Datumsformat yyyy-MM-dd
- Datumsformat dd-MMM-yy
- Datumsformat dd/MM/yy
- Datumsformat MM/dd/yy
- Datumsformat mit yy. Zeigt nur yyyy an.
- Zeitformat HH:mm:ss (24-Stunden-Format)

**Dezimalsymbol, das in Zahlen verwendet wird**<br>
Das verwendete Dezimalsymbol ist immer ein Punkt, auch wenn in den Einstellungen für das **Zahlenformat** in den Regioneneinstellungen ein **Komma ausgewählt** ist. Beispielsweise wird 15,5K als 15,5K angezeigt.


