---
title: Überwachen und Melden des Microsoft Defender Antivirus Schutzes
description: Verwenden Sie Configuration Manager oder SIEM-Tools (Security Information and Event Management), um Berichte zu nutzen, und überwachen Sie Microsoft Defender AV mit PowerShell und WMI.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 91891af35def83f21b3db8c7e8fa4b320bef563c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926163"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Berichte zu Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus ist in Windows 10, Windows Server 2019 und Windows Server 2016 integriert. Microsoft Defender Antivirus gehört zu Ihrem Schutz der nächsten Generation in Microsoft Defender für Endpunkt. Der Schutz der nächsten Generation schützt Ihre Geräte vor Softwarebedrohungen wie Viren, Schadsoftware und Spyware über E-Mails, Apps, die Cloud und das Web hinweg.

Mit Microsoft Defender Antivirus haben Sie mehrere Optionen zum Überprüfen des Schutzstatus und von Warnungen. Sie können Microsoft Endpoint Manager verwenden, um Microsoft Defender Antivirus zu [überwachen](/configmgr/protect/deploy-use/monitor-endpoint-protection) oder [E-Mail-Benachrichtigungen zu erstellen.](/configmgr/protect/deploy-use/endpoint-configure-alerts) Sie können den Schutz auch mit [Microsoft Intune](/intune/introduction-intune)überwachen.  

Microsoft Operations Management Suite verfügt über ein [Updatecompliance-Add-In,](/windows/deployment/update/update-compliance-get-started) das wichtige Microsoft Defender Antivirus Probleme meldet, einschließlich Schutzupdates und Echtzeit-Schutzeinstellungen.

Wenn Sie über einen SIEM-Server (Security Information and Event Management) eines Drittanbieters verfügen, können Sie auch [Windows Defender Clientereignisse](/windows/win32/events/windows-events)nutzen. 

Windows Ereignisse umfassen mehrere Sicherheitsereignisquellen, einschließlich Security Account Manager (SAM)-Ereignisse[(für Windows 10 erweitert,](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)siehe auch das Thema ["Sicherheitsüberwachung")](/windows/device-security/auditing/security-auditing-overview) und [Windows Defender Ereignisse.](troubleshoot-microsoft-defender-antivirus.md) 

Diese Ereignisse können zentral mithilfe des [Windows Ereignissammlers](/windows/win32/wec/windows-event-collector)aggregiert werden. Häufig verfügen SIEM-Server über Connectors für Windows Ereignisse, sodass Sie alle Sicherheitsereignisse in Ihrem SIEM-Server korrelieren können. 

Sie können [Schadsoftwareereignisse auch mithilfe der Lösung zur Schadsoftwarebewertung in Log Analytics überwachen.](/azure/log-analytics/log-analytics-malware)

Informationen zum Überwachen oder Ermitteln des Status mit PowerShell, WMI oder Microsoft Azure finden Sie in der [Tabelle mit Bereitstellungs-, Verwaltungs- und Berichtsoptionen.](deploy-manage-report-microsoft-defender-antivirus.md#ref2)

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus auf Windows Server 2016 und 2019](microsoft-defender-antivirus-on-windows-server.md)
- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)