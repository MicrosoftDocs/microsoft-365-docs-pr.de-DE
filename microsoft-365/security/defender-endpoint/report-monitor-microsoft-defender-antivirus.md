---
title: Überwachen und Melden des Microsoft Defender Antivirus-Schutzes
description: Verwenden Sie Configuration Manager oder Sicherheitsinformations- und Ereignisverwaltungstools (SIEM), um Berichte zu nutzen und Microsoft Defender AV mit PowerShell und WMI zu überwachen.
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
ms.openlocfilehash: a31dfa7e5eba36937f4ab50205df938614e80b76
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765767"
---
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="bbed4-104">Bericht über Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbed4-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bbed4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bbed4-105">**Applies to:**</span></span>

- [<span data-ttu-id="bbed4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bbed4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bbed4-107">Microsoft Defender Antivirus ist in Windows 10, Windows Server 2019 und Windows Server 2016 integrierte.</span><span class="sxs-lookup"><span data-stu-id="bbed4-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="bbed4-108">Microsoft Defender Antivirus ist ihr Schutz der nächsten Generation in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bbed4-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bbed4-109">Der Schutz der nächsten Generation schützt Ihre Geräte vor Softwarebedrohungen wie Viren, Schadsoftware und Spyware über E-Mails, Apps, die Cloud und das Web.</span><span class="sxs-lookup"><span data-stu-id="bbed4-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="bbed4-110">Mit Microsoft Defender Antivirus haben Sie mehrere Optionen zum Überprüfen des Schutzstatus und von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="bbed4-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="bbed4-111">Sie können Microsoft Endpoint Manager verwenden, [um Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) zu überwachen oder [E-Mail-Benachrichtigungen zu erstellen.](/configmgr/protect/deploy-use/endpoint-configure-alerts)</span><span class="sxs-lookup"><span data-stu-id="bbed4-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="bbed4-112">Oder Sie können den Schutz mithilfe von [Microsoft Intune überwachen.](/intune/introduction-intune)</span><span class="sxs-lookup"><span data-stu-id="bbed4-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="bbed4-113">Microsoft Operations Management Suite verfügt über ein [Update Compliance-Add-In,](/windows/deployment/update/update-compliance-get-started) das über wichtige Microsoft Defender Antivirus-Probleme berichtet, einschließlich Schutzupdates und Echtzeitschutzeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="bbed4-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="bbed4-114">Wenn Sie über einen SieM-Server (Security Information and Event Management) eines Drittanbieters verfügen, können Sie auch Windows Defender [verwenden.](/windows/win32/events/windows-events)</span><span class="sxs-lookup"><span data-stu-id="bbed4-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="bbed4-115">Windows-Ereignisse umfassen mehrere Sicherheitsereignisquellen, einschließlich Security Account Manager (SAM)-Ereignisse [](/windows/device-security/auditing/security-auditing-overview) ( erweitert für[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), siehe auch das Thema Sicherheitsüberwachung) und [Windows Defender Ereignisse](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="bbed4-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="bbed4-116">Diese Ereignisse können mithilfe des Windows-Ereignissammlers [zentral aggregiert werden.](/windows/win32/wec/windows-event-collector)</span><span class="sxs-lookup"><span data-stu-id="bbed4-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="bbed4-117">Häufig verfügen SIEM-Server über Connectors für Windows-Ereignisse, sodass Sie alle Sicherheitsereignisse auf Ihrem SIEM-Server korrelieren können.</span><span class="sxs-lookup"><span data-stu-id="bbed4-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="bbed4-118">Sie können [Schadsoftwareereignisse auch mithilfe der Lösung zur Bewertung von](/azure/log-analytics/log-analytics-malware)Schadsoftware in Log Analytics überwachen.</span><span class="sxs-lookup"><span data-stu-id="bbed4-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="bbed4-119">Informationen zum Überwachen oder Bestimmen des Status mit PowerShell, WMI oder Microsoft Azure finden Sie in der Tabelle (Tabelle mit [Bereitstellungs-, Verwaltungs- und Berichtsoptionen).](deploy-manage-report-microsoft-defender-antivirus.md#ref2)</span><span class="sxs-lookup"><span data-stu-id="bbed4-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="bbed4-120">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="bbed4-120">Related articles</span></span>

- [<span data-ttu-id="bbed4-121">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="bbed4-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="bbed4-122">Microsoft Defender Antivirus unter Windows Server 2016 und 2019</span><span class="sxs-lookup"><span data-stu-id="bbed4-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="bbed4-123">Bereitstellen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbed4-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)