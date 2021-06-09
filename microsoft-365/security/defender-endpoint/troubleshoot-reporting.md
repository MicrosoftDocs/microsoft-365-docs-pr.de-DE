---
title: Behandeln von Problemen mit Berichterstellungstools für Microsoft Defender AV
description: Identifizieren und Lösen allgemeiner Probleme bei dem Versuch, den Status des Microsoft Defender AV-Schutzes in der Updatecompliance zu melden
keywords: Troubleshoot, error, fix, update compliance, oms, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ab987089c20d0a1d0baed152e7ddcfdd2878cc65
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843458"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Behandeln von Problemen bei der Microsoft Defender Antivirus-Berichterstattung in Update Compliance

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> Am 31. März 2020 wird das Microsoft Defender Antivirus Berichterstellungsfeature der Updatecompliance entfernt. Sie können weiterhin Sicherheitscompliancerichtlinien [mithilfe von Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)definieren und überprüfen, was eine präzisere Kontrolle über Sicherheitsfeatures und -updates ermöglicht.

Sie können Microsoft Defender Antivirus mit Updatecompliance verwenden. Sie sehen den Status für E3-, B-, F1-, VL- und Pro Lizenzen. Für E5-Lizenzen müssen Sie jedoch das [Microsoft Defender für Endpunkt-Portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)verwenden. Weitere Informationen zu Lizenzierungsoptionen finden Sie unter [Windows 10 Produktlizenzierungsoptionen.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)

Wenn Sie [Windows Analytics Update Compliance verwenden, um Berichte über den Schutzstatus von Geräten oder Endpunkten](/windows/deployment/update/update-compliance-using#wdav-assessment) in Ihrem Netzwerk zu erhalten, die Microsoft Defender Antivirus verwenden, treten möglicherweise Probleme oder Probleme auf.

In der Regel sind die häufigsten Indikatoren für ein Problem:
- Es wird nur eine kleine Anzahl oder Teilmenge aller Geräte angezeigt, die Sie erwartet haben.
- Es werden überhaupt keine Geräte angezeigt.
- Die Angezeigten Berichte und Informationen sind veraltet (älter als einige Tage).

Allgemeine Fehlercodes und Ereignis-IDs im Zusammenhang mit dem Microsoft Defender Antivirus Dienst, die nicht mit der Updatecompliance zusammenhängen, finden Sie unter [Microsoft Defender Antivirus Ereignisse.](troubleshoot-microsoft-defender-antivirus.md) 

Es gibt drei Schritte, um diese Probleme zu beheben:

1. Vergewissern Sie sich, dass alle Voraussetzungen erfüllt sind.
2. Überprüfen Der Konnektivität mit dem Windows Defender cloudbasierten Dienst
3. Übermitteln von Supportprotokollen

>[!IMPORTANT]
>Es dauert in der Regel 3 Tage, bis Geräte in der Updatecompliance angezeigt werden.


## <a name="confirm-prerequisites"></a>Bestätigen der Voraussetzungen

Damit Geräte ordnungsgemäß in der Updatecompliance angezeigt werden, müssen Sie bestimmte Voraussetzungen sowohl für den Updatekompatibilitätsdienst als auch für Microsoft Defender Antivirus erfüllen:

>[!div class="checklist"]
>- Endpunkte verwenden Microsoft Defender Antivirus als einzige Antivirenschutz-App. [Die Verwendung einer anderen Antiviren-App bewirkt, dass Microsoft Defender AV sich selbst deaktiviert,](microsoft-defender-antivirus-compatibility.md) und der Endpunkt wird nicht in der Updatecompliance gemeldet.
> - [Der über die Cloud bereitgestellte Schutz ist aktiviert.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - Endpunkte können [eine Verbindung mit der Microsoft Defender AV-Cloud herstellen](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Wenn der Endpunkt Windows 10 Version 1607 oder früher ausgeführt wird, [müssen Windows 10 Diagnosedaten auf die Stufe "Erweitert" festgelegt werden.](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)
> - Es sind 3 Tage vergangen, seit alle Anforderungen erfüllt sind.

"Sie können Microsoft Defender Antivirus mit Updatecompliance verwenden. Sie sehen den Status für E3-, B-, F1-, VL- und Pro Lizenzen. Für E5-Lizenzen müssen Sie jedoch das Microsoft Defender für Endpunkt-Portal (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) verwenden. Weitere Informationen zu Lizenzierungsoptionen finden Sie unter Windows 10 Produktlizenzierungsoptionen."

Wenn alle oben genannten Voraussetzungen erfüllt sind, müssen Sie möglicherweise mit dem nächsten Schritt fortfahren, um Diagnoseinformationen zu sammeln und sie an uns zu senden.

> [!div class="nextstepaction"]
> [Sammeln von Diagnosedaten für die Problembehandlung bei der Updatecompliance](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)