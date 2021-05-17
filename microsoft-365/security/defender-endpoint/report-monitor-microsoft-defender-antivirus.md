---
title: Überwachen und Melden Microsoft Defender Antivirus Schutz
description: Verwenden Sie Configuration Manager oder Sicherheitsinformations- und Ereignisverwaltungstools (SIEM), um Berichte zu nutzen und Microsoft Defender AV mit PowerShell und WMI zu überwachen.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5780daaa65a4d83376dd7977e03e88e2d828befc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269588"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Berichte zu Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus ist in Windows 10, Windows Server 2019 und Windows Server 2016. Microsoft Defender Antivirus von Ihrem Schutz der nächsten Generation in Microsoft Defender for Endpoint. Der Schutz der nächsten Generation schützt Ihre Geräte vor Softwarebedrohungen wie Viren, Schadsoftware und Spyware über E-Mails, Apps, die Cloud und das Web.

Mit Microsoft Defender Antivirus haben Sie mehrere Optionen zum Überprüfen des Schutzstatus und von Warnungen. Sie können Microsoft Endpoint Manager [verwenden, um Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) zu überwachen [oder E-Mail-Benachrichtigungen zu erstellen.](/configmgr/protect/deploy-use/endpoint-configure-alerts) Sie können den Schutz auch mithilfe von [Microsoft Intune.](/intune/introduction-intune)  

Microsoft Operations Management Suite verfügt über ein [Update Compliance-Add-In,](/windows/deployment/update/update-compliance-get-started) das über wichtige Microsoft Defender Antivirus berichtet, einschließlich Schutzupdates und Echtzeitschutzeinstellungen.

Wenn Sie über einen SieM-Server (Security Information and Event Management) eines Drittanbieters verfügen, können Sie auch Windows Defender [verwenden.](/windows/win32/events/windows-events) 

Windows ereignisse umfassen mehrere Sicherheitsereignisquellen, einschließlich Security Account Manager (SAM)-Ereignisse (erweitert für[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), siehe auch das Thema Sicherheitsüberwachung) und [Windows Defender Ereignisse](troubleshoot-microsoft-defender-antivirus.md). [](/windows/device-security/auditing/security-auditing-overview) 

Diese Ereignisse können zentral mithilfe des Windows [aggregiert werden.](/windows/win32/wec/windows-event-collector) Häufig verfügen SIEM-Server über Connectors für Windows Ereignisse, sodass Sie alle Sicherheitsereignisse auf Ihrem SIEM-Server korrelieren können. 

Sie können [Schadsoftwareereignisse auch mithilfe der Lösung zur Bewertung von](/azure/log-analytics/log-analytics-malware)Schadsoftware in Log Analytics überwachen.

Informationen zum Überwachen oder Bestimmen des Status mit PowerShell, WMI oder Microsoft Azure finden Sie in der Tabelle (Tabelle mit [Bereitstellungs-,](deploy-manage-report-microsoft-defender-antivirus.md#ref2)Verwaltungs- und Berichtsoptionen).

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus auf Windows Server 2016 und 2019](microsoft-defender-antivirus-on-windows-server.md)
- [Bereitstellen Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)