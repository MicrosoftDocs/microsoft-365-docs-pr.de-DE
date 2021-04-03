---
title: Bericht über anfällige Geräte – Bedrohungs- und Sicherheitsrisikoverwaltung
description: Ein Bericht mit anfälligen Gerätetrends und aktuellen Statistiken. Das Ziel ist, dass Sie den Atem und umfang Ihrer Gerätebelichtung verstehen.
keywords: mdatp-tvm vulnerable devices, mdatp, tvm, reduce threat & vulnerability exposure, reduce threat and vulnerability, monitor security configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f481ddca897594bd73de9b5f4762903f23fb24c6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500459"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="d1159-105">Bericht über anfällige Geräte – Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="d1159-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d1159-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d1159-106">**Applies to:**</span></span>

- [<span data-ttu-id="d1159-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d1159-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d1159-108">Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="d1159-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="d1159-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1159-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d1159-110">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d1159-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d1159-111">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d1159-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="d1159-112">Der Bericht zeigt Diagramme und Balkendiagramme mit anfälligen Gerätetrends und aktuellen Statistiken.</span><span class="sxs-lookup"><span data-stu-id="d1159-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="d1159-113">Das Ziel ist, dass Sie den Atem und umfang Ihrer Gerätebelichtung verstehen.</span><span class="sxs-lookup"><span data-stu-id="d1159-113">The goal is for you to understand the breath and scope of your device exposure.</span></span> 

<span data-ttu-id="d1159-114">Greifen Sie auf den Bericht im Microsoft Defender Security Center zu Berichte **> gefährdeten Geräten zu**</span><span class="sxs-lookup"><span data-stu-id="d1159-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="d1159-115">Es gibt zwei Spalten:</span><span class="sxs-lookup"><span data-stu-id="d1159-115">There are two columns:</span></span>

- <span data-ttu-id="d1159-116">Trends (im Laufe der Zeit).</span><span class="sxs-lookup"><span data-stu-id="d1159-116">Trends (over time).</span></span> <span data-ttu-id="d1159-117">Kann die letzten 30 Tage, 3 Monate, 6 Monate oder einen benutzerdefinierten Datumsbereich anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d1159-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="d1159-118">Heute (aktuelle Informationen)</span><span class="sxs-lookup"><span data-stu-id="d1159-118">Today (current information)</span></span>

<span data-ttu-id="d1159-119">**Filter**: Sie können die Daten nach Schweregraden der Sicherheitsanfälligkeit, Exploitverfügbarkeit, Sicherheitsrisikoalter, Betriebssystemplattform, Windows 10-Version oder Gerätegruppe filtern.</span><span class="sxs-lookup"><span data-stu-id="d1159-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="d1159-120">**Drilldown**: Wenn Sie einen Einblick erhalten möchten, wählen Sie das entsprechende Balkendiagramm aus, um eine gefilterte Liste von Geräten auf der Seite Geräteinventar anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="d1159-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="d1159-121">Von dort können Sie die Liste exportieren.</span><span class="sxs-lookup"><span data-stu-id="d1159-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="d1159-122">Schweregraddiagramme</span><span class="sxs-lookup"><span data-stu-id="d1159-122">Severity level graphs</span></span>

<span data-ttu-id="d1159-123">Jedes Gerät wird nur einmal nach der schwersten Sicherheitslücke auf diesem Gerät gezählt.</span><span class="sxs-lookup"><span data-stu-id="d1159-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![Ein Diagramm der aktuellen Schweregrade für Sicherheitslücken für Geräte und ein Diagramm, das die Ebenen im Laufe der Zeit zeigt.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="d1159-125">Exploit-Verfügbarkeitsdiagramme</span><span class="sxs-lookup"><span data-stu-id="d1159-125">Exploit availability graphs</span></span>

<span data-ttu-id="d1159-126">Jedes Gerät wird basierend auf der höchsten Stufe bekannter Exploits nur einmal gezählt.</span><span class="sxs-lookup"><span data-stu-id="d1159-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![Ein Diagramm der aktuellen Verfügbarkeit von Geräte-Exploits und ein Diagramm, das die Verfügbarkeit im Laufe der Zeit zeigt.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="d1159-128">Altersdiagramme für Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="d1159-128">Vulnerability age graphs</span></span>

<span data-ttu-id="d1159-129">Jedes Gerät wird nur einmal unter dem ältesten Datum für die Veröffentlichung von Sicherheitslücken gezählt.</span><span class="sxs-lookup"><span data-stu-id="d1159-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="d1159-130">Ältere Sicherheitsrisiken haben eine höhere Wahrscheinlichkeit, ausgebeutet zu werden.</span><span class="sxs-lookup"><span data-stu-id="d1159-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![Ein Diagramm des aktuellen Alters von Sicherheitslücken für Geräte und ein Diagramm, das das Alter im Laufe der Zeit zeigt.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="d1159-132">Anfällige Geräte nach Betriebssystemplattformdiagrammen</span><span class="sxs-lookup"><span data-stu-id="d1159-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="d1159-133">Die Anzahl der Geräte auf jedem Betriebssystem, die aufgrund von Softwarerisiken verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d1159-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![Ein Diagramm der aktuellen anfälligen Geräte nach Betriebssystemplattform und ein Diagramm, das anfällige Geräte nach Betriebssystemplattformen im Laufe der Zeit zeigt.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="d1159-135">Anfällige Geräte nach Windows 10-Versionsdiagrammen</span><span class="sxs-lookup"><span data-stu-id="d1159-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="d1159-136">Die Anzahl der Geräte auf jeder Windows 10-Version, die aufgrund anfälliger Anwendungen oder Betriebssysteme verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d1159-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![Ein Diagramm der aktuellen anfälligen Geräte nach Windows 10-Version und ein Diagramm mit anfälligen Geräten nach Windows 10-Version im Laufe der Zeit.](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="d1159-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d1159-138">Related topics</span></span>

- [<span data-ttu-id="d1159-139">Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="d1159-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="d1159-140">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="d1159-140">Security recommendations</span></span>](tvm-security-recommendation.md)
