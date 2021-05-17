---
title: Microsoft Defender Security Center zeitzoneneinstellungen
description: Verwenden Sie die hier enthaltenen Informationen, um Microsoft Defender Security Center Zeitzoneneinstellungen zu konfigurieren und Lizenzinformationen anzeigen.
keywords: Einstellungen, Microsoft Defender, Cybersecurity Threat Intelligence, Microsoft Defender for Endpoint, Zeitzone, utc, Ortszeit, Lizenz
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
ms.openlocfilehash: df55a1b0e92c24b5f52032330ef95bf19aeb8cb3
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932631"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="9be28-104">Microsoft Defender Security Center zeitzoneneinstellungen</span><span class="sxs-lookup"><span data-stu-id="9be28-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9be28-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9be28-105">**Applies to:**</span></span>
- [<span data-ttu-id="9be28-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9be28-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="9be28-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9be28-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9be28-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9be28-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="9be28-109">Verwenden Sie **das Zeitzonenmenü** ![ Zeitzoneneinstellungen ](images/atp-time-zone.png) symbol1, um die Zeitzone zu konfigurieren und Lizenzinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9be28-109">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="9be28-110">Zeitzoneneinstellungen</span><span class="sxs-lookup"><span data-stu-id="9be28-110">Time zone settings</span></span>
<span data-ttu-id="9be28-111">Der Zeitaspekt ist wichtig bei der Bewertung und Analyse von wahrgenommenen und tatsächlichen Cyberangriffen.</span><span class="sxs-lookup"><span data-stu-id="9be28-111">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="9be28-112">Cyberforensische Untersuchungen beruhen häufig auf Zeitstempeln, um die Abfolge von Ereignissen zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="9be28-112">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="9be28-113">Es ist wichtig, dass Ihr System die richtigen Zeitzoneneinstellungen widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="9be28-113">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="9be28-114">Microsoft Defender for Endpoint kann entweder koordinierte Weltzeit (UTC) oder Ortszeit anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9be28-114">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="9be28-115">Ihre aktuelle Zeitzoneneinstellung wird im Menü Microsoft Defender for Endpoint angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9be28-115">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="9be28-116">Sie können die angezeigte Zeitzone im **Menü** Zeitzone ändern.</span><span class="sxs-lookup"><span data-stu-id="9be28-116">You can change the displayed time zone in the **Time zone** menu.</span></span>

![Zeitzoneneinstellungen (Symbol2)](images/atp-time-zone-menu.png)<span data-ttu-id="9be28-118">.</span><span class="sxs-lookup"><span data-stu-id="9be28-118">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="9be28-119">UTC-Zeitzone</span><span class="sxs-lookup"><span data-stu-id="9be28-119">UTC time zone</span></span>
<span data-ttu-id="9be28-120">Microsoft Defender for Endpoint verwendet standardmäßig UTC-Zeit.</span><span class="sxs-lookup"><span data-stu-id="9be28-120">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="9be28-121">Wenn Sie die Microsoft Defender for Endpoint-Zeitzone auf UTC festlegen, werden alle Systemzeitstempel (Warnungen, Ereignisse und andere) in UTC für alle Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9be28-121">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="9be28-122">Dies kann Sicherheitsanalysten, die an verschiedenen Orten auf der ganzen Welt arbeiten, dabei helfen, die gleichen Zeitstempel zu verwenden, während Sie Ereignisse untersuchen.</span><span class="sxs-lookup"><span data-stu-id="9be28-122">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="9be28-123">Lokale Zeitzone</span><span class="sxs-lookup"><span data-stu-id="9be28-123">Local time zone</span></span>
<span data-ttu-id="9be28-124">Sie können festlegen, dass Microsoft Defender for Endpoint lokale Zeitzoneneinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9be28-124">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="9be28-125">Alle Warnungen und Ereignisse werden mithilfe Ihrer lokalen Zeitzone angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9be28-125">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="9be28-126">Die lokale Zeitzone wird aus den regionalen Einstellungen Ihres Geräts übernommen.</span><span class="sxs-lookup"><span data-stu-id="9be28-126">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="9be28-127">Wenn Sie Ihre regionalen Einstellungen ändern, ändert sich auch die Microsoft Defender for Endpoint-Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="9be28-127">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="9be28-128">Wenn Sie diese Einstellung auswählen, werden die in Microsoft Defender for Endpoint angezeigten Zeitstempel für alle Microsoft Defender for Endpoint-Benutzer an der Ortszeit ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="9be28-128">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="9be28-129">Analysten, die sich an verschiedenen globalen Standorten befinden, sehen nun die Microsoft Defender for Endpoint-Warnungen entsprechend ihren regionalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9be28-129">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="9be28-130">Die Verwendung der Ortszeit kann hilfreich sein, wenn sich die Analysten an einem einzigen Standort befinden.</span><span class="sxs-lookup"><span data-stu-id="9be28-130">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="9be28-131">In diesem Fall ist es möglicherweise einfacher, Ereignisse mit der Ortszeit zu korrelieren, z. B. wenn ein lokaler Benutzer auf einen verdächtigen E-Mail-Link geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="9be28-131">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="9be28-132">Festlegen der Zeitzone</span><span class="sxs-lookup"><span data-stu-id="9be28-132">Set the time zone</span></span>
<span data-ttu-id="9be28-133">Die Microsoft Defender for Endpoint-Zeitzone ist standardmäßig auf UTC festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9be28-133">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="9be28-134">Durch festlegen der Zeitzone werden auch die Zeiten für alle Microsoft Defender for Endpoint-Ansichten geändert.</span><span class="sxs-lookup"><span data-stu-id="9be28-134">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="9be28-135">So legen Sie die Zeitzone ein:</span><span class="sxs-lookup"><span data-stu-id="9be28-135">To set the time zone:</span></span>

1. <span data-ttu-id="9be28-136">Klicken Sie **auf das Zeitzonenmenü** ![ Zeitzoneneinstellungen Symbol3 ](images/atp-time-zone.png) .</span><span class="sxs-lookup"><span data-stu-id="9be28-136">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="9be28-137">Wählen Sie **den Zeitzonen-UTC-Indikator** aus.</span><span class="sxs-lookup"><span data-stu-id="9be28-137">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="9be28-138">Wählen **Sie Zeitzone UTC** oder Ihre lokale Zeitzone aus, z. B. -7:00.</span><span class="sxs-lookup"><span data-stu-id="9be28-138">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="9be28-139">Regionale Einstellungen</span><span class="sxs-lookup"><span data-stu-id="9be28-139">Regional settings</span></span>
<span data-ttu-id="9be28-140">Verwenden Sie regionale Einstellungen für Internet Explorer (IE) und Microsoft Edge (Edge), um unterschiedliche Datumsformate für Microsoft Defender for Endpoint anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="9be28-140">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="9be28-141">Wenn Sie einen anderen Browser wie Google Chrome verwenden, führen Sie die erforderlichen Schritte aus, um die Zeit- und Datumseinstellungen für diesen Browser zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9be28-141">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="9be28-142">**Internet Explorer (IE) und Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="9be28-142">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="9be28-143">IE und Microsoft Edge verwenden  die Region-Einstellungen, die in der Systemsteuerung in der Option **Uhren,** Sprache und Region konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9be28-143">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="9be28-144">Bekannte Probleme mit regionalen Formaten</span><span class="sxs-lookup"><span data-stu-id="9be28-144">Known issues with regional formats</span></span>

<span data-ttu-id="9be28-145">**Datums- und Uhrzeitformate**</span><span class="sxs-lookup"><span data-stu-id="9be28-145">**Date and time formats**</span></span><br>
<span data-ttu-id="9be28-146">Es gibt einige bekannte Probleme mit den Uhrzeit- und Datumsformaten.</span><span class="sxs-lookup"><span data-stu-id="9be28-146">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="9be28-147">Wenn Sie Ihre regionalen Einstellungen auf andere als die unterstützten Formate konfigurieren, gibt das Portal möglicherweise ihre Einstellungen nicht richtig wieder.</span><span class="sxs-lookup"><span data-stu-id="9be28-147">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="9be28-148">Die folgenden Datums- und Uhrzeitformate werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9be28-148">The following date and time formats are supported:</span></span>
- <span data-ttu-id="9be28-149">Datumsformat MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="9be28-149">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="9be28-150">Datumsformat dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="9be28-150">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="9be28-151">Zeitformat hh:mm:ss (12-Stunden-Format)</span><span class="sxs-lookup"><span data-stu-id="9be28-151">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="9be28-152">Die folgenden Datums- und Uhrzeitformate werden derzeit nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9be28-152">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="9be28-153">Datumsformat yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="9be28-153">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="9be28-154">Datumsformat dd-MMM-yy</span><span class="sxs-lookup"><span data-stu-id="9be28-154">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="9be28-155">Datumsformat dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="9be28-155">Date format dd/MM/yy</span></span>
- <span data-ttu-id="9be28-156">Datumsformat MM/dd/yy</span><span class="sxs-lookup"><span data-stu-id="9be28-156">Date format MM/dd/yy</span></span>
- <span data-ttu-id="9be28-157">Datumsformat mit yy.</span><span class="sxs-lookup"><span data-stu-id="9be28-157">Date format with yy.</span></span> <span data-ttu-id="9be28-158">Zeigt nur yyyy an.</span><span class="sxs-lookup"><span data-stu-id="9be28-158">Will only show yyyy.</span></span>
- <span data-ttu-id="9be28-159">Zeitformat HH:mm:ss (24-Stunden-Format)</span><span class="sxs-lookup"><span data-stu-id="9be28-159">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="9be28-160">**Dezimalsymbol, das in Zahlen verwendet wird**</span><span class="sxs-lookup"><span data-stu-id="9be28-160">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="9be28-161">Das verwendete Dezimalsymbol ist immer ein Punkt, auch wenn in den Einstellungen für das **Zahlenformat** in den Regioneneinstellungen ein **Komma ausgewählt** ist.</span><span class="sxs-lookup"><span data-stu-id="9be28-161">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="9be28-162">Beispielsweise wird 15,5K als 15,5K angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9be28-162">For example, 15,5K is displayed as 15.5K.</span></span>


