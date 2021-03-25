---
title: Behandeln von Problemen mit dem Microsoft Defender for Endpoint-Dienst
description: Finden Sie Lösungen und arbeiten Sie um bekannte Probleme wie Serverfehler, wenn Sie versuchen, auf den Dienst zu zugreifen.
keywords: Problembehandlung bei Microsoft Defender für Endpunkt, Problembehandlung bei Windows ATP, Serverfehler, Zugriff verweigert, ungültige Anmeldeinformationen, keine Daten, Dashboardportal, zulassen, Ereignisanzeige
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: bd211a56ee9ed6aa871c8d55149247a4755bc863
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064864"
---
# <a name="troubleshoot-service-issues"></a><span data-ttu-id="424b2-104">Behandeln von Dienstproblemen</span><span class="sxs-lookup"><span data-stu-id="424b2-104">Troubleshoot service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="424b2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="424b2-105">**Applies to:**</span></span>
- [<span data-ttu-id="424b2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="424b2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="424b2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="424b2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="424b2-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="424b2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="424b2-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="424b2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="424b2-110">In diesem Abschnitt werden Probleme behandelt, die bei der Verwendung des Microsoft Defender Advanced Threat-Diensts auftreten können.</span><span class="sxs-lookup"><span data-stu-id="424b2-110">This section addresses issues that might arise as you use the Microsoft Defender Advanced Threat service.</span></span>

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a><span data-ttu-id="424b2-111">Serverfehler : Zugriff wird aufgrund ungültiger Anmeldeinformationen verweigert</span><span class="sxs-lookup"><span data-stu-id="424b2-111">Server error - Access is denied due to invalid credentials</span></span>
<span data-ttu-id="424b2-112">Wenn beim Zugriff auf den Dienst ein Serverfehler auftritt, müssen Sie ihre Browsercookieeinstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="424b2-112">If you encounter a server error when trying to access the service, you’ll need to change your browser cookie settings.</span></span>
<span data-ttu-id="424b2-113">Konfigurieren Sie Ihren Browser so, dass Cookies zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="424b2-113">Configure your browser to allow cookies.</span></span>

## <a name="elements-or-data-missing-on-the-portal"></a><span data-ttu-id="424b2-114">Elemente oder Daten fehlen im Portal</span><span class="sxs-lookup"><span data-stu-id="424b2-114">Elements or data missing on the portal</span></span>
<span data-ttu-id="424b2-115">Wenn einige Benutzeroberflächenelemente oder Daten im Microsoft Defender Security Center fehlen, ist es möglich, dass Proxyeinstellungen sie blockieren.</span><span class="sxs-lookup"><span data-stu-id="424b2-115">If some UI elements or data is missing on Microsoft Defender Security Center it’s possible that proxy settings are blocking it.</span></span>

<span data-ttu-id="424b2-116">Stellen Sie sicher, `*.securitycenter.windows.com` dass die Liste der Proxy-Zulässigen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="424b2-116">Make sure that `*.securitycenter.windows.com` is included the proxy allow list.</span></span>


> [!NOTE]
> <span data-ttu-id="424b2-117">Sie müssen das HTTPS-Protokoll verwenden, wenn Sie die folgenden Endpunkte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="424b2-117">You must use the HTTPS protocol when adding the following endpoints.</span></span>

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a><span data-ttu-id="424b2-118">Microsoft Defender for Endpoint-Dienst zeigt Ereignis- oder Fehlerprotokolle in der Ereignisanzeige an.</span><span class="sxs-lookup"><span data-stu-id="424b2-118">Microsoft Defender for Endpoint service shows event or error logs in the Event Viewer</span></span>

<span data-ttu-id="424b2-119">Im Thema Überprüfen von Ereignissen und Fehlern mithilfe der [Ereignisanzeige](event-error-codes.md) finden Sie eine Liste der Ereignis-IDs, die vom Microsoft Defender for Endpoint-Dienst gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="424b2-119">See the topic [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="424b2-120">Das Thema enthält auch Schritte zur Problembehandlung bei Ereignisfehlern.</span><span class="sxs-lookup"><span data-stu-id="424b2-120">The topic also contains troubleshooting steps for event errors.</span></span>

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a><span data-ttu-id="424b2-121">Microsoft Defender for Endpoint-Dienst kann nach einem Neustart nicht gestartet werden und zeigt Fehler 577 an.</span><span class="sxs-lookup"><span data-stu-id="424b2-121">Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577</span></span>

<span data-ttu-id="424b2-122">Wenn das Onboarding von Geräten erfolgreich abgeschlossen wurde, Microsoft Defender for Endpoint jedoch nach einem Neustart nicht gestartet wird und Fehler 577 angezeigt wird, überprüfen Sie, ob Windows Defender nicht durch eine Richtlinie deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="424b2-122">If onboarding devices successfully completes but Microsoft Defender for Endpoint does not start after a reboot and shows error 577, check that Windows Defender is not disabled by a policy.</span></span>

<span data-ttu-id="424b2-123">Weitere Informationen finden Sie unter [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="424b2-123">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

## <a name="known-issues-with-regional-formats"></a><span data-ttu-id="424b2-124">Bekannte Probleme mit regionalen Formaten</span><span class="sxs-lookup"><span data-stu-id="424b2-124">Known issues with regional formats</span></span>

<span data-ttu-id="424b2-125">**Datums- und Uhrzeitformate**</span><span class="sxs-lookup"><span data-stu-id="424b2-125">**Date and time formats**</span></span><br>
<span data-ttu-id="424b2-126">Es gibt einige bekannte Probleme mit den Uhrzeit- und Datumsformaten.</span><span class="sxs-lookup"><span data-stu-id="424b2-126">There are some known issues with the time and date formats.</span></span> 

<span data-ttu-id="424b2-127">Die folgenden Datumsformate werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="424b2-127">The following date formats are supported:</span></span>
- <span data-ttu-id="424b2-128">MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="424b2-128">MM/dd/yyyy</span></span>
- <span data-ttu-id="424b2-129">dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="424b2-129">dd/MM/yyyy</span></span>

<span data-ttu-id="424b2-130">Die folgenden Datums- und Uhrzeitformate werden derzeit nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="424b2-130">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="424b2-131">Datumsformat yyyy/MM/dd</span><span class="sxs-lookup"><span data-stu-id="424b2-131">Date format yyyy/MM/dd</span></span>
- <span data-ttu-id="424b2-132">Datumsformat dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="424b2-132">Date format dd/MM/yy</span></span>
- <span data-ttu-id="424b2-133">Datumsformat mit yy.</span><span class="sxs-lookup"><span data-stu-id="424b2-133">Date format with yy.</span></span> <span data-ttu-id="424b2-134">Zeigt nur yyyy an.</span><span class="sxs-lookup"><span data-stu-id="424b2-134">Will only show yyyy.</span></span>
- <span data-ttu-id="424b2-135">Das Zeitformat HH:mm:ss wird nicht unterstützt (das 12-Stunden-FORMAT am/PM wird nicht unterstützt).</span><span class="sxs-lookup"><span data-stu-id="424b2-135">Time format HH:mm:ss is not supported (the 12 hour AM/PM format is not supported).</span></span> <span data-ttu-id="424b2-136">Es wird nur das 24-Stunden-Format unterstützt.</span><span class="sxs-lookup"><span data-stu-id="424b2-136">Only the 24-hour format is supported.</span></span>

<span data-ttu-id="424b2-137">**Verwenden von Komma zur Angabe von Tausend**</span><span class="sxs-lookup"><span data-stu-id="424b2-137">**Use of comma to indicate thousand**</span></span><br>
<span data-ttu-id="424b2-138">Die Verwendung von Kommas als Trennzeichen in Zahlen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="424b2-138">Support of use of comma as a separator in numbers are not supported.</span></span> <span data-ttu-id="424b2-139">Regionen, in denen eine Zahl durch ein Komma getrennt ist, um tausend anzugeben, wird nur die Verwendung eines Punkts als Trennzeichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="424b2-139">Regions where a number is separated with a comma to indicate a thousand, will only see the use of a dot as a separator.</span></span> <span data-ttu-id="424b2-140">Beispielsweise wird 15,5K als 15,5K angezeigt.</span><span class="sxs-lookup"><span data-stu-id="424b2-140">For example, 15,5K is displayed as 15.5K.</span></span>

><span data-ttu-id="424b2-141">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="424b2-141">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="424b2-142">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="424b2-142">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a><span data-ttu-id="424b2-143">Microsoft Defender for Endpoint-Mandant wurde automatisch in Europa erstellt</span><span class="sxs-lookup"><span data-stu-id="424b2-143">Microsoft Defender for Endpoint tenant was automatically created in Europe</span></span>
<span data-ttu-id="424b2-144">Wenn Sie Azure Security Center zum Überwachen von Servern verwenden, wird automatisch ein Microsoft Defender for Endpoint-Mandant erstellt.</span><span class="sxs-lookup"><span data-stu-id="424b2-144">When you use Azure Security Center to monitor servers, a Microsoft Defender for Endpoint tenant is automatically created.</span></span> <span data-ttu-id="424b2-145">Die Microsoft Defender for Endpoint-Daten werden standardmäßig in Europa gespeichert.</span><span class="sxs-lookup"><span data-stu-id="424b2-145">The Microsoft Defender for Endpoint data is stored in Europe by default.</span></span>





## <a name="related-topics"></a><span data-ttu-id="424b2-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="424b2-146">Related topics</span></span>
- [<span data-ttu-id="424b2-147">Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="424b2-147">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
- [<span data-ttu-id="424b2-148">Überprüfen von Ereignissen und Fehlern mithilfe der Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="424b2-148">Review events and errors using Event Viewer</span></span>](event-error-codes.md)
