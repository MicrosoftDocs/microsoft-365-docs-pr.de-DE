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
ms.openlocfilehash: 25f2fc979cd6ffe82ba16e1ab870c97cdf4fcfe9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066072"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="80092-104">Zeitzoneneinstellungen für Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="80092-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="80092-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="80092-105">**Applies to:**</span></span>
- [<span data-ttu-id="80092-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="80092-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="80092-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80092-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)




><span data-ttu-id="80092-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="80092-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="80092-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="80092-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="80092-110">Verwenden Sie **das Zeitzonenmenü** ![ Zeitzoneneinstellungen ](images/atp-time-zone.png) symbol1, um die Zeitzone zu konfigurieren und Lizenzinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="80092-110">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="80092-111">Zeitzoneneinstellungen</span><span class="sxs-lookup"><span data-stu-id="80092-111">Time zone settings</span></span>
<span data-ttu-id="80092-112">Der Zeitaspekt ist wichtig bei der Bewertung und Analyse von wahrgenommenen und tatsächlichen Cyberangriffen.</span><span class="sxs-lookup"><span data-stu-id="80092-112">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="80092-113">Cyberforensische Untersuchungen beruhen häufig auf Zeitstempeln, um die Abfolge von Ereignissen zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="80092-113">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="80092-114">Es ist wichtig, dass Ihr System die richtigen Zeitzoneneinstellungen widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="80092-114">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="80092-115">Microsoft Defender for Endpoint kann entweder koordinierte Weltzeit (UTC) oder Ortszeit anzeigen.</span><span class="sxs-lookup"><span data-stu-id="80092-115">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="80092-116">Ihre aktuelle Zeitzoneneinstellung wird im Menü Microsoft Defender for Endpoint angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80092-116">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="80092-117">Sie können die angezeigte Zeitzone im **Menü** Zeitzone ändern.</span><span class="sxs-lookup"><span data-stu-id="80092-117">You can change the displayed time zone in the **Time zone** menu.</span></span>

![Zeitzoneneinstellungen (Symbol2)](images/atp-time-zone-menu.png)<span data-ttu-id="80092-119">.</span><span class="sxs-lookup"><span data-stu-id="80092-119">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="80092-120">UTC-Zeitzone</span><span class="sxs-lookup"><span data-stu-id="80092-120">UTC time zone</span></span>
<span data-ttu-id="80092-121">Microsoft Defender for Endpoint verwendet standardmäßig UTC-Zeit.</span><span class="sxs-lookup"><span data-stu-id="80092-121">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="80092-122">Wenn Sie die Microsoft Defender for Endpoint-Zeitzone auf UTC festlegen, werden alle Systemzeitstempel (Warnungen, Ereignisse und andere) in UTC für alle Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80092-122">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="80092-123">Dies kann Sicherheitsanalysten, die an verschiedenen Orten auf der ganzen Welt arbeiten, dabei helfen, die gleichen Zeitstempel zu verwenden, während Sie Ereignisse untersuchen.</span><span class="sxs-lookup"><span data-stu-id="80092-123">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="80092-124">Lokale Zeitzone</span><span class="sxs-lookup"><span data-stu-id="80092-124">Local time zone</span></span>
<span data-ttu-id="80092-125">Sie können festlegen, dass Microsoft Defender for Endpoint lokale Zeitzoneneinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="80092-125">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="80092-126">Alle Warnungen und Ereignisse werden mithilfe Ihrer lokalen Zeitzone angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80092-126">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="80092-127">Die lokale Zeitzone wird aus den regionalen Einstellungen Ihres Geräts übernommen.</span><span class="sxs-lookup"><span data-stu-id="80092-127">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="80092-128">Wenn Sie Ihre regionalen Einstellungen ändern, ändert sich auch die Microsoft Defender for Endpoint-Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="80092-128">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="80092-129">Wenn Sie diese Einstellung auswählen, werden die in Microsoft Defender for Endpoint angezeigten Zeitstempel für alle Microsoft Defender for Endpoint-Benutzer an der Ortszeit ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="80092-129">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="80092-130">Analysten, die sich an verschiedenen globalen Standorten befinden, sehen nun die Microsoft Defender for Endpoint-Warnungen entsprechend ihren regionalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="80092-130">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="80092-131">Die Verwendung der Ortszeit kann hilfreich sein, wenn sich die Analysten an einem einzigen Standort befinden.</span><span class="sxs-lookup"><span data-stu-id="80092-131">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="80092-132">In diesem Fall ist es möglicherweise einfacher, Ereignisse mit der Ortszeit zu korrelieren, z. B. wenn ein lokaler Benutzer auf einen verdächtigen E-Mail-Link geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="80092-132">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="80092-133">Festlegen der Zeitzone</span><span class="sxs-lookup"><span data-stu-id="80092-133">Set the time zone</span></span>
<span data-ttu-id="80092-134">Die Microsoft Defender for Endpoint-Zeitzone ist standardmäßig auf UTC festgelegt.</span><span class="sxs-lookup"><span data-stu-id="80092-134">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="80092-135">Durch festlegen der Zeitzone werden auch die Zeiten für alle Microsoft Defender for Endpoint-Ansichten geändert.</span><span class="sxs-lookup"><span data-stu-id="80092-135">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="80092-136">So legen Sie die Zeitzone ein:</span><span class="sxs-lookup"><span data-stu-id="80092-136">To set the time zone:</span></span>

1. <span data-ttu-id="80092-137">Klicken Sie **auf das Zeitzonenmenü** ![ Zeitzoneneinstellungen Symbol3 ](images/atp-time-zone.png) .</span><span class="sxs-lookup"><span data-stu-id="80092-137">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="80092-138">Wählen Sie **den Zeitzonen-UTC-Indikator** aus.</span><span class="sxs-lookup"><span data-stu-id="80092-138">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="80092-139">Wählen **Sie Zeitzone UTC** oder Ihre lokale Zeitzone aus, z. B. -7:00.</span><span class="sxs-lookup"><span data-stu-id="80092-139">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="80092-140">Regionale Einstellungen</span><span class="sxs-lookup"><span data-stu-id="80092-140">Regional settings</span></span>
<span data-ttu-id="80092-141">Verwenden Sie regionale Einstellungen für Internet Explorer (IE) und Microsoft Edge (Edge), um unterschiedliche Datumsformate für Microsoft Defender for Endpoint anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="80092-141">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="80092-142">Wenn Sie einen anderen Browser wie Google Chrome verwenden, führen Sie die erforderlichen Schritte aus, um die Zeit- und Datumseinstellungen für diesen Browser zu ändern.</span><span class="sxs-lookup"><span data-stu-id="80092-142">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="80092-143">**Internet Explorer (IE) und Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="80092-143">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="80092-144">IE und Microsoft  Edge verwenden die Region-Einstellungen, die in der Systemsteuerung in der Option **Uhren,** Sprache und Region konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="80092-144">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="80092-145">Bekannte Probleme mit regionalen Formaten</span><span class="sxs-lookup"><span data-stu-id="80092-145">Known issues with regional formats</span></span>

<span data-ttu-id="80092-146">**Datums- und Uhrzeitformate**</span><span class="sxs-lookup"><span data-stu-id="80092-146">**Date and time formats**</span></span><br>
<span data-ttu-id="80092-147">Es gibt einige bekannte Probleme mit den Uhrzeit- und Datumsformaten.</span><span class="sxs-lookup"><span data-stu-id="80092-147">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="80092-148">Wenn Sie Ihre regionalen Einstellungen auf andere als die unterstützten Formate konfigurieren, gibt das Portal möglicherweise ihre Einstellungen nicht richtig wieder.</span><span class="sxs-lookup"><span data-stu-id="80092-148">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="80092-149">Die folgenden Datums- und Uhrzeitformate werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="80092-149">The following date and time formats are supported:</span></span>
- <span data-ttu-id="80092-150">Datumsformat MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="80092-150">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="80092-151">Datumsformat dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="80092-151">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="80092-152">Zeitformat hh:mm:ss (12-Stunden-Format)</span><span class="sxs-lookup"><span data-stu-id="80092-152">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="80092-153">Die folgenden Datums- und Uhrzeitformate werden derzeit nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="80092-153">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="80092-154">Datumsformat yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="80092-154">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="80092-155">Datumsformat dd-MMM-yy</span><span class="sxs-lookup"><span data-stu-id="80092-155">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="80092-156">Datumsformat dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="80092-156">Date format dd/MM/yy</span></span>
- <span data-ttu-id="80092-157">Datumsformat MM/dd/yy</span><span class="sxs-lookup"><span data-stu-id="80092-157">Date format MM/dd/yy</span></span>
- <span data-ttu-id="80092-158">Datumsformat mit yy.</span><span class="sxs-lookup"><span data-stu-id="80092-158">Date format with yy.</span></span> <span data-ttu-id="80092-159">Zeigt nur yyyy an.</span><span class="sxs-lookup"><span data-stu-id="80092-159">Will only show yyyy.</span></span>
- <span data-ttu-id="80092-160">Zeitformat HH:mm:ss (24-Stunden-Format)</span><span class="sxs-lookup"><span data-stu-id="80092-160">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="80092-161">**Dezimalsymbol, das in Zahlen verwendet wird**</span><span class="sxs-lookup"><span data-stu-id="80092-161">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="80092-162">Das verwendete Dezimalsymbol ist immer ein Punkt, auch wenn in den Einstellungen für das **Zahlenformat** in den Regioneneinstellungen ein **Komma ausgewählt** ist.</span><span class="sxs-lookup"><span data-stu-id="80092-162">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="80092-163">Beispielsweise wird 15,5K als 15,5K angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80092-163">For example, 15,5K is displayed as 15.5K.</span></span>


