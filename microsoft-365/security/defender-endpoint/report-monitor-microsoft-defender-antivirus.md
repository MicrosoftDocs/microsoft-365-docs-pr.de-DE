---
title: Überwachen und Melden des Microsoft Defender Antivirus-Schutzes
description: Verwenden Sie Configuration Manager oder Sicherheitsinformations- und Ereignisverwaltungstools (SIEM), um Berichte zu nutzen und Microsoft Defender AV mit PowerShell und WMI zu überwachen.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f0065792f525827ccd1471087b8a707989ef61ef
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690700"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Bericht über Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus ist in Windows 10, Windows Server 2019 und Windows Server 2016 integrierte. Microsoft Defender Antivirus ist ihr Schutz der nächsten Generation in Microsoft Defender for Endpoint. Der Schutz der nächsten Generation schützt Ihre Geräte vor Softwarebedrohungen wie Viren, Schadsoftware und Spyware über E-Mails, Apps, die Cloud und das Web.

Mit Microsoft Defender Antivirus haben Sie mehrere Optionen zum Überprüfen des Schutzstatus und von Warnungen. Sie können Microsoft Endpoint Manager verwenden, [um Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) zu überwachen oder [E-Mail-Benachrichtigungen zu erstellen.](/configmgr/protect/deploy-use/endpoint-configure-alerts) Oder Sie können den Schutz mithilfe von [Microsoft Intune überwachen.](/intune/introduction-intune)  

Microsoft Operations Management Suite verfügt über ein [Update Compliance-Add-In,](/windows/deployment/update/update-compliance-get-started) das über wichtige Microsoft Defender Antivirus-Probleme berichtet, einschließlich Schutzupdates und Echtzeitschutzeinstellungen.

Wenn Sie über einen SieM-Server (Security Information and Event Management) eines Drittanbieters verfügen, können Sie auch Windows Defender [verwenden.](/windows/win32/events/windows-events) 

Windows-Ereignisse umfassen mehrere Sicherheitsereignisquellen, einschließlich Security Account Manager (SAM)-Ereignisse [](/windows/device-security/auditing/security-auditing-overview) ( erweitert für[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), siehe auch das Thema Sicherheitsüberwachung) und [Windows Defender Ereignisse](troubleshoot-microsoft-defender-antivirus.md). 

Diese Ereignisse können mithilfe des Windows-Ereignissammlers [zentral aggregiert werden.](/windows/win32/wec/windows-event-collector) Häufig verfügen SIEM-Server über Connectors für Windows-Ereignisse, sodass Sie alle Sicherheitsereignisse auf Ihrem SIEM-Server korrelieren können. 

Sie können [Schadsoftwareereignisse auch mithilfe der Lösung zur Bewertung von](/azure/log-analytics/log-analytics-malware)Schadsoftware in Log Analytics überwachen.

Informationen zum Überwachen oder Bestimmen des Status mit PowerShell, WMI oder Microsoft Azure finden Sie in der Tabelle (Tabelle mit [Bereitstellungs-, Verwaltungs- und Berichtsoptionen).](deploy-manage-report-microsoft-defender-antivirus.md#ref2)

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus unter Windows Server 2016 und 2019](microsoft-defender-antivirus-on-windows-server.md)
- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)