---
title: Behandeln von Problemen mit Berichterstellungstools für Microsoft Defender AV
description: Identifizieren und Lösen gängiger Probleme beim Versuch, den Status des Microsoft Defender AV-Schutzes in Update Compliance zu melden
keywords: Problembehandlung, Fehler, Behebung, Updatekonformität, Oms, Monitor, Bericht, Microsoft Defender AV
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
ms.openlocfilehash: ca62db922a13ab2cb3226eaf0efb92bfaf8c572b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274892"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="df843-104">Behandeln von Problemen bei der Microsoft Defender Antivirus-Berichterstattung in Update Compliance</span><span class="sxs-lookup"><span data-stu-id="df843-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="df843-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="df843-105">**Applies to:**</span></span>

- [<span data-ttu-id="df843-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="df843-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="df843-107">Am 31. März 2020 wird das Microsoft Defender Antivirus-Berichterstellungsfeature der Update compliance entfernt.</span><span class="sxs-lookup"><span data-stu-id="df843-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="df843-108">Sie können weiterhin Richtlinien für die Sicherheitskonformität mithilfe von [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)definieren und überprüfen, was eine feine steuerung der Sicherheitsfeatures und -updates ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="df843-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="df843-109">Sie können Microsoft Defender Antivirus mit Update compliance verwenden.</span><span class="sxs-lookup"><span data-stu-id="df843-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="df843-110">Der Status für E3-, B-, F1-, VL- und Pro-Lizenzen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df843-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="df843-111">Für E5-Lizenzen müssen Sie jedoch das [Microsoft Defender for Endpoint-Portal verwenden.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="df843-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="df843-112">Weitere Informationen zu Lizenzierungsoptionen finden Sie unter [Windows 10 Product Licensing Options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span><span class="sxs-lookup"><span data-stu-id="df843-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="df843-113">Wenn Sie [Windows Analytics Update Compliance](/windows/deployment/update/update-compliance-using#wdav-assessment) verwenden, um Berichte über den Schutzstatus von Geräten oder Endpunkten in Ihrem Netzwerk zu erhalten, die Microsoft Defender Antivirus verwenden, können Probleme oder Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="df843-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="df843-114">In der Regel sind die häufigsten Indikatoren für ein Problem:</span><span class="sxs-lookup"><span data-stu-id="df843-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="df843-115">Es wird nur eine kleine Anzahl oder Teilmenge aller Geräte angezeigt, die Sie erwartet haben.</span><span class="sxs-lookup"><span data-stu-id="df843-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="df843-116">Es werden keine Geräte angezeigt</span><span class="sxs-lookup"><span data-stu-id="df843-116">You do not see any devices at all</span></span>
- <span data-ttu-id="df843-117">Die Berichte und Informationen, die Sie sehen, sind veraltet (älter als ein paar Tage)</span><span class="sxs-lookup"><span data-stu-id="df843-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="df843-118">Allgemeine Fehlercodes und Ereignis-IDs im Zusammenhang mit dem Microsoft Defender Antivirus-Dienst, die nicht im Zusammenhang mit der Update-Compliance stehen, finden Sie unter [Microsoft Defender Antivirus-Ereignisse](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="df843-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="df843-119">Es gibt drei Schritte zur Problembehandlung:</span><span class="sxs-lookup"><span data-stu-id="df843-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="df843-120">Bestätigen, dass alle Voraussetzungen erfüllt sind</span><span class="sxs-lookup"><span data-stu-id="df843-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="df843-121">Überprüfen der Konnektivität Windows Defender cloudbasierten Diensts</span><span class="sxs-lookup"><span data-stu-id="df843-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="df843-122">Übermitteln von Supportprotokollen</span><span class="sxs-lookup"><span data-stu-id="df843-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="df843-123">Es dauert in der Regel 3 Tage, bis Geräte in update compliance angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="df843-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="df843-124">Bestätigen von Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="df843-124">Confirm prerequisites</span></span>

<span data-ttu-id="df843-125">Damit Geräte ordnungsgemäß in der Updatekonformität angezeigt werden, müssen Sie bestimmte Voraussetzungen sowohl für den Update compliance-Dienst als auch für Microsoft Defender Antivirus erfüllen:</span><span class="sxs-lookup"><span data-stu-id="df843-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="df843-126">Endpunkte verwenden Microsoft Defender Antivirus als einzige Antivirenschutz-App.</span><span class="sxs-lookup"><span data-stu-id="df843-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="df843-127">[Wenn Sie eine andere Antiviren-App verwenden, wird Microsoft Defender AV](microsoft-defender-antivirus-compatibility.md) selbst deaktiviert, und der Endpunkt wird nicht in Update Compliance gemeldet.</span><span class="sxs-lookup"><span data-stu-id="df843-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="df843-128">[Der in der Cloud zugestellte Schutz ist aktiviert.](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="df843-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="df843-129">Endpunkte können [eine Verbindung mit der Microsoft Defender AV-Cloud herstellen](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="df843-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="df843-130">Wenn auf dem Endpunkt Windows 10, Version 1607 oder früher ausgeführt wird, müssen [Windows 10-Diagnosedaten](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)auf die Erweiterte Ebene festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="df843-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="df843-131">Seit 3 Tagen sind alle Anforderungen erfüllt</span><span class="sxs-lookup"><span data-stu-id="df843-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="df843-132">"Sie können Microsoft Defender Antivirus mit Update compliance verwenden.</span><span class="sxs-lookup"><span data-stu-id="df843-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="df843-133">Der Status für E3-, B-, F1-, VL- und Pro-Lizenzen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df843-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="df843-134">Für E5-Lizenzen müssen Sie jedoch das Microsoft Defender for Endpoint-Portal ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) verwenden.</span><span class="sxs-lookup"><span data-stu-id="df843-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="df843-135">Weitere Informationen zu Lizenzierungsoptionen finden Sie unter Windows 10-Produktlizenzierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="df843-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="df843-136">Wenn alle oben genannten Voraussetzungen erfüllt sind, müssen Sie möglicherweise mit dem nächsten Schritt fortfahren, um Diagnoseinformationen zu sammeln und an uns zu senden.</span><span class="sxs-lookup"><span data-stu-id="df843-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="df843-137">Sammeln von Diagnosedaten für die Problembehandlung bei der Updatekonformität</span><span class="sxs-lookup"><span data-stu-id="df843-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="df843-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="df843-138">Related topics</span></span>

- [<span data-ttu-id="df843-139">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="df843-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="df843-140">Bereitstellen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="df843-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)