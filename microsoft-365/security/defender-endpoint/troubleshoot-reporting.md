---
title: Behandeln von Problemen mit Berichterstellungstools für Microsoft Defender AV
description: Identifizieren und Lösen gängiger Probleme beim Versuch, den Status des Microsoft Defender AV-Schutzes in Update Compliance zu melden
keywords: Problembehandlung, Fehler, Behebung, Updatekonformität, Oms, Monitor, Bericht, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50136c620450861c41513650f27bf24fc782e968
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764531"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Behandeln von Microsoft Defender Antivirus-Berichten in Update compliance

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> Am 31. März 2020 wird das Microsoft Defender Antivirus-Berichterstellungsfeature der Update compliance entfernt. Sie können weiterhin Richtlinien für die Sicherheitskonformität mithilfe von [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)definieren und überprüfen, was eine feine steuerung der Sicherheitsfeatures und -updates ermöglicht.

Sie können Microsoft Defender Antivirus mit Update compliance verwenden. Der Status für E3-, B-, F1-, VL- und Pro-Lizenzen wird angezeigt. Für E5-Lizenzen müssen Sie jedoch das [Microsoft Defender for Endpoint-Portal verwenden.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) Weitere Informationen zu Lizenzierungsoptionen finden Sie unter [Windows 10 Product Licensing Options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).

Wenn Sie [Windows Analytics Update Compliance](/windows/deployment/update/update-compliance-using#wdav-assessment) verwenden, um Berichte über den Schutzstatus von Geräten oder Endpunkten in Ihrem Netzwerk zu erhalten, die Microsoft Defender Antivirus verwenden, können Probleme oder Probleme auftreten.

In der Regel sind die häufigsten Indikatoren für ein Problem:
- Es wird nur eine kleine Anzahl oder Teilmenge aller Geräte angezeigt, die Sie erwartet haben.
- Es werden keine Geräte angezeigt
- Die Berichte und Informationen, die Sie sehen, sind veraltet (älter als ein paar Tage)

Allgemeine Fehlercodes und Ereignis-IDs im Zusammenhang mit dem Microsoft Defender Antivirus-Dienst, die nicht im Zusammenhang mit der Update-Compliance stehen, finden Sie unter [Microsoft Defender Antivirus-Ereignisse](troubleshoot-microsoft-defender-antivirus.md). 

Es gibt drei Schritte zur Problembehandlung:

1. Bestätigen, dass alle Voraussetzungen erfüllt sind
2. Überprüfen der Konnektivität Windows Defender cloudbasierten Diensts
3. Übermitteln von Supportprotokollen

>[!IMPORTANT]
>Es dauert in der Regel 3 Tage, bis Geräte in update compliance angezeigt werden.


## <a name="confirm-prerequisites"></a>Bestätigen von Voraussetzungen

Damit Geräte ordnungsgemäß in der Updatekonformität angezeigt werden, müssen Sie bestimmte Voraussetzungen sowohl für den Update compliance-Dienst als auch für Microsoft Defender Antivirus erfüllen:

>[!div class="checklist"]
>- Endpunkte verwenden Microsoft Defender Antivirus als einzige Antivirenschutz-App. [Wenn Sie eine andere Antiviren-App verwenden, wird Microsoft Defender AV](microsoft-defender-antivirus-compatibility.md) selbst deaktiviert, und der Endpunkt wird nicht in Update Compliance gemeldet.
> - [Der in der Cloud zugestellte Schutz ist aktiviert.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - Endpunkte können [eine Verbindung mit der Microsoft Defender AV-Cloud herstellen](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Wenn auf dem Endpunkt Windows 10, Version 1607 oder früher ausgeführt wird, müssen [Windows 10-Diagnosedaten](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)auf die Erweiterte Ebene festgelegt werden.
> - Seit 3 Tagen sind alle Anforderungen erfüllt

"Sie können Microsoft Defender Antivirus mit Update compliance verwenden. Der Status für E3-, B-, F1-, VL- und Pro-Lizenzen wird angezeigt. Für E5-Lizenzen müssen Sie jedoch das Microsoft Defender for Endpoint-Portal ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) verwenden. Weitere Informationen zu Lizenzierungsoptionen finden Sie unter Windows 10-Produktlizenzierungsoptionen.

Wenn alle oben genannten Voraussetzungen erfüllt sind, müssen Sie möglicherweise mit dem nächsten Schritt fortfahren, um Diagnoseinformationen zu sammeln und an uns zu senden.

> [!div class="nextstepaction"]
> [Sammeln von Diagnosedaten für die Problembehandlung bei der Updatekonformität](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)