---
title: Reagieren auf Webbedrohungen in Microsoft Defender ATP
description: Reagieren Sie auf Warnungen im Zusammenhang mit schädlichen und unerwünschten Websites. Verstehen, wie der Schutz von Webbedrohungen Endbenutzer über ihre Webbrowser und Windows-Benachrichtigungen informiert
keywords: Webschutz, Webbedrohungenschutz, Webbrowsing, Warnungen, Antwort, Sicherheit, Phishing, Schadsoftware, Exploit, Websites, Netzwerkschutz, Edge, Internet Explorer, Chrome, Firefox, Webbrowser, Benachrichtigungen, Endbenutzer, Windows-Benachrichtigungen, Sperrseite,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 339944b94ca55c5d73fafaabfe3f7bc26dafe7bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063679"
---
# <a name="respond-to-web-threats"></a><span data-ttu-id="f7562-105">Reagieren auf Webbedrohungen</span><span class="sxs-lookup"><span data-stu-id="f7562-105">Respond to web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f7562-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f7562-106">**Applies to:**</span></span>
- [<span data-ttu-id="f7562-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f7562-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f7562-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7562-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f7562-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f7562-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f7562-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f7562-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="f7562-111">Mit web protection in Microsoft Defender for Endpoint können Sie Warnungen im Zusammenhang mit schädlichen Websites und Websites in Ihrer benutzerdefinierten Indikatorliste effizient untersuchen und darauf reagieren.</span><span class="sxs-lookup"><span data-stu-id="f7562-111">Web protection in Microsoft Defender for Endpoint lets you efficiently investigate and respond to alerts related to malicious websites and websites in your custom indicator list.</span></span>

## <a name="view-web-threat-alerts"></a><span data-ttu-id="f7562-112">Anzeigen von Webbedrohungswarnungen</span><span class="sxs-lookup"><span data-stu-id="f7562-112">View web threat alerts</span></span>
<span data-ttu-id="f7562-113">Microsoft Defender for Endpoint generiert die folgenden [Warnungen für](manage-alerts.md) böswillige oder verdächtige Webaktivitäten:</span><span class="sxs-lookup"><span data-stu-id="f7562-113">Microsoft Defender for Endpoint generates the following [alerts](manage-alerts.md) for malicious or suspicious web activity:</span></span>
- <span data-ttu-id="f7562-114">**Verdächtige** Verbindung, die vom Netzwerkschutz blockiert wird – diese Warnung wird generiert, wenn der Versuch, auf eine schädliche Website oder eine Website in Ihrer benutzerdefinierten Indikatorliste zu zugreifen, durch den Netzwerkschutz im  *Sperrmodus beendet* wird.</span><span class="sxs-lookup"><span data-stu-id="f7562-114">**Suspicious connection blocked by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is *stopped* by network protection in *block* mode</span></span>
- <span data-ttu-id="f7562-115">**Verdächtige** Verbindung, die vom Netzwerkschutz erkannt wird – diese Warnung wird generiert, wenn ein Versuch, auf eine schädliche Website oder eine Website in Ihrer benutzerdefinierten Indikatorliste zu zugreifen, vom Netzwerkschutz im Überwachungsmodus erkannt *wird.*</span><span class="sxs-lookup"><span data-stu-id="f7562-115">**Suspicious connection detected by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is detected by network protection in *audit only* mode</span></span>

<span data-ttu-id="f7562-116">Jede Warnung enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="f7562-116">Each alert provides the following information:</span></span> 
- <span data-ttu-id="f7562-117">Gerät, das versucht hat, auf die blockierte Website zu zugreifen</span><span class="sxs-lookup"><span data-stu-id="f7562-117">Device that attempted to access the blocked website</span></span>
- <span data-ttu-id="f7562-118">Anwendung oder Programm zum Senden der Webanforderung</span><span class="sxs-lookup"><span data-stu-id="f7562-118">Application or program used to send the web request</span></span>
- <span data-ttu-id="f7562-119">Bösartige URL oder URL in der Liste der benutzerdefinierten Indikatoren</span><span class="sxs-lookup"><span data-stu-id="f7562-119">Malicious URL or URL in the custom indicator list</span></span>
- <span data-ttu-id="f7562-120">Empfohlene Aktionen für Responder</span><span class="sxs-lookup"><span data-stu-id="f7562-120">Recommended actions for responders</span></span>

![Abbildung einer Warnung im Zusammenhang mit dem Schutz von Webbedrohungen](images/wtp-alert.png)

>[!Note]
><span data-ttu-id="f7562-122">Um das Volumen der Warnungen zu reduzieren, konsolidiert Microsoft Defender for Endpoint die Erkennung von Webbedrohungen für dieselbe Domäne auf demselben Gerät jeden Tag in einer einzelnen Warnung.</span><span class="sxs-lookup"><span data-stu-id="f7562-122">To reduce the volume of alerts, Microsoft Defender for Endpoint consolidates web threat detections for the same domain on the same device each day to a single alert.</span></span> <span data-ttu-id="f7562-123">Es wird nur eine Warnung generiert und in den [Webschutzbericht gezählt.](web-protection-monitoring.md)</span><span class="sxs-lookup"><span data-stu-id="f7562-123">Only one alert is generated and counted into the [web protection report](web-protection-monitoring.md).</span></span>

## <a name="inspect-website-details"></a><span data-ttu-id="f7562-124">Überprüfen von Websitedetails</span><span class="sxs-lookup"><span data-stu-id="f7562-124">Inspect website details</span></span>
<span data-ttu-id="f7562-125">Sie können tiefer gehen, indem Sie die URL oder Domäne der Website in der Warnung auswählen.</span><span class="sxs-lookup"><span data-stu-id="f7562-125">You can dive deeper by selecting the URL or domain of the website in the alert.</span></span> <span data-ttu-id="f7562-126">Dadurch wird eine Seite zu dieser bestimmten URL oder Domäne mit verschiedenen Informationen geöffnet, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="f7562-126">This opens a page about that particular URL or domain with various information, including:</span></span>
- <span data-ttu-id="f7562-127">Geräte, die versucht haben, auf die Website zu zugreifen</span><span class="sxs-lookup"><span data-stu-id="f7562-127">Devices that attempted to access website</span></span>
- <span data-ttu-id="f7562-128">Vorfälle und Warnungen im Zusammenhang mit der Website</span><span class="sxs-lookup"><span data-stu-id="f7562-128">Incidents and alerts related to the website</span></span>
- <span data-ttu-id="f7562-129">Wie häufig die Website in Ereignissen in Ihrer Organisation gesehen wurde</span><span class="sxs-lookup"><span data-stu-id="f7562-129">How frequent the website was seen in events in your organization</span></span>

    ![Abbildung der Seite "Domänen- oder URL-Entitätsdetails"](images/wtp-website-details.png)

[<span data-ttu-id="f7562-131">Weitere Informationen zu URL- oder Domänenentitätsseiten</span><span class="sxs-lookup"><span data-stu-id="f7562-131">Learn more about URL or domain entity pages</span></span>](investigate-domain.md)

## <a name="inspect-the-device"></a><span data-ttu-id="f7562-132">Überprüfen des Geräts</span><span class="sxs-lookup"><span data-stu-id="f7562-132">Inspect the device</span></span>
<span data-ttu-id="f7562-133">Sie können auch das Gerät überprüfen, das versucht hat, auf eine blockierte URL zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f7562-133">You can also check the device that attempted to access a blocked URL.</span></span> <span data-ttu-id="f7562-134">Wenn Sie den Namen des Geräts auf der Warnungsseite auswählen, wird eine Seite mit umfassenden Informationen zum Gerät geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f7562-134">Selecting the name of the device on the alert page opens a page with comprehensive information about the device.</span></span>

[<span data-ttu-id="f7562-135">Weitere Informationen zu Geräteentitätsseiten</span><span class="sxs-lookup"><span data-stu-id="f7562-135">Learn more about device entity pages</span></span>](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a><span data-ttu-id="f7562-136">Webbrowser- und Windows-Benachrichtigungen für Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="f7562-136">Web browser and Windows notifications for end users</span></span>

<span data-ttu-id="f7562-137">Mit dem Webschutz in Microsoft Defender for Endpoint werden Endbenutzer daran gehindert, schädliche oder unerwünschte Websites mit Microsoft Edge oder anderen Browsern zu besuchen.</span><span class="sxs-lookup"><span data-stu-id="f7562-137">With web protection in Microsoft Defender for Endpoint, your end users will be prevented from visiting malicious or unwanted websites using Microsoft Edge or other browsers.</span></span> <span data-ttu-id="f7562-138">Da das Blockieren durch den [Netzwerkschutz ausgeführt wird,](network-protection.md)wird ein allgemeiner Fehler vom Webbrowser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7562-138">Because blocking is performed by [network protection](network-protection.md), they will see a generic error from the web browser.</span></span> <span data-ttu-id="f7562-139">Außerdem wird eine Benachrichtigung von Windows angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7562-139">They will also see a notification from Windows.</span></span>

<span data-ttu-id="f7562-140">![Abbildung von Microsoft Edge mit einem 403-Fehler und der Windows-Benachrichtigungswebbedrohung, die ](images/wtp-browser-blocking-page.png)
 *auf Microsoft Edge blockiert ist*</span><span class="sxs-lookup"><span data-stu-id="f7562-140">![Image of Microsoft Edge showing a 403 error and the Windows notification](images/wtp-browser-blocking-page.png)
*Web threat blocked on Microsoft Edge*</span></span>

<span data-ttu-id="f7562-141">![Abbildung des Chrome-Webbrowsers, der eine Warnung für sichere Verbindungen und die Windows-Benachrichtigungswebbedrohung zeigt, die ](images/wtp-chrome-browser-blocking-page.png)
 *in Chrome blockiert ist*</span><span class="sxs-lookup"><span data-stu-id="f7562-141">![Image of Chrome web browser showing a secure connection warning and the Windows notification](images/wtp-chrome-browser-blocking-page.png)
*Web threat blocked on Chrome*</span></span>

## <a name="related-topics"></a><span data-ttu-id="f7562-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f7562-142">Related topics</span></span>
- [<span data-ttu-id="f7562-143">Übersicht über den Webschutz</span><span class="sxs-lookup"><span data-stu-id="f7562-143">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="f7562-144">Filtern von Webinhalten</span><span class="sxs-lookup"><span data-stu-id="f7562-144">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="f7562-145">Schutz vor Webbedrohungen</span><span class="sxs-lookup"><span data-stu-id="f7562-145">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="f7562-146">Überwachen der Websicherheit</span><span class="sxs-lookup"><span data-stu-id="f7562-146">Monitor web security</span></span>](web-protection-monitoring.md)
