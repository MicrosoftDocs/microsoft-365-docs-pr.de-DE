---
title: Überprüfen des Integritätsstatus des Sensors in Microsoft Defender for Endpoint
description: Überprüfen Sie den Sensorzustand auf Geräten, um zu ermitteln, welche Sensordaten falsch konfiguriert, inaktiv sind oder keine Sensordaten melden.
keywords: sensor, sensor health, misconfigured, inactive, no sensor data, sensor data, impaired communications, communication
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904164"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c1f41-104">Überprüfen des Sensorintestatus in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c1f41-104">Check sensor health state in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c1f41-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c1f41-105">**Applies to:**</span></span>
- [<span data-ttu-id="c1f41-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c1f41-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c1f41-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1f41-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c1f41-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="c1f41-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c1f41-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c1f41-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

<span data-ttu-id="c1f41-110">Die **Kachel Geräte mit Sensorproblemen** befindet sich im Dashboard für Sicherheitsvorgänge.</span><span class="sxs-lookup"><span data-stu-id="c1f41-110">The **Devices with sensor issues** tile is found on the Security Operations dashboard.</span></span> <span data-ttu-id="c1f41-111">Diese Kachel enthält Informationen zur Fähigkeit des einzelnen Geräts, Sensordaten zur Verfügung zu stellen und mit dem Defender for Endpoint-Dienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="c1f41-111">This tile provides information on the individual device’s ability to provide sensor data and communicate with the Defender for Endpoint service.</span></span> <span data-ttu-id="c1f41-112">Es berichtet, wie viele Geräte Aufmerksamkeit erfordern und hilft Ihnen, problematische Geräte zu identifizieren und Maßnahmen zur Korrektur bekannter Probleme zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="c1f41-112">It reports how many devices require attention and helps you identify problematic devices and take action to correct known issues.</span></span>

<span data-ttu-id="c1f41-113">Auf der Kachel befinden sich zwei Statusindikatoren, die Informationen zur Anzahl der Geräte bereitstellen, die dem Dienst nicht ordnungsgemäß melden:</span><span class="sxs-lookup"><span data-stu-id="c1f41-113">There are two status indicators on the tile that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="c1f41-114">**Falsch konfiguriert** – Diese Geräte melden möglicherweise teilweise Sensordaten an den Defender for Endpoint-Dienst und können Konfigurationsfehler haben, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c1f41-114">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="c1f41-115">**Inaktiv** : Geräte, die die Berichterstellung an den Defender for Endpoint-Dienst im letzten Monat für mehr als sieben Tage beendet haben.</span><span class="sxs-lookup"><span data-stu-id="c1f41-115">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="c1f41-116">Wenn Sie auf eine der Gruppen klicken, werden Sie zur **Geräteliste ,** gefiltert nach Ihrer Wahl, gefiltert.</span><span class="sxs-lookup"><span data-stu-id="c1f41-116">Clicking any of the groups directs you to **Devices list**, filtered according to your choice.</span></span>

![Screenshot der Kachel Geräte mit Sensorproblemen](images/atp-devices-with-sensor-issues-tile.png)

<span data-ttu-id="c1f41-118">In **der Liste Geräte** können Sie die Integritätsstatusliste nach dem folgenden Status filtern:</span><span class="sxs-lookup"><span data-stu-id="c1f41-118">On **Devices list**, you can filter the health state list by the following status:</span></span>
- <span data-ttu-id="c1f41-119">**Aktiv** – Geräte, die aktiv an den Defender for Endpoint-Dienst melden.</span><span class="sxs-lookup"><span data-stu-id="c1f41-119">**Active** - Devices that are actively reporting to the Defender for Endpoint service.</span></span>
- <span data-ttu-id="c1f41-120">**Falsch konfiguriert –** Diese Geräte melden möglicherweise teilweise Sensordaten an den Defender for Endpoint-Dienst, haben jedoch Konfigurationsfehler, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c1f41-120">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service but have configuration errors that need to be corrected.</span></span> <span data-ttu-id="c1f41-121">Falsch konfigurierte Geräte können entweder eine oder eine Kombination der folgenden Probleme haben:</span><span class="sxs-lookup"><span data-stu-id="c1f41-121">Misconfigured devices can have either one or a combination of the following issues:</span></span>
  - <span data-ttu-id="c1f41-122">**Keine Sensordaten** – Geräte haben das Senden von Sensordaten beendet.</span><span class="sxs-lookup"><span data-stu-id="c1f41-122">**No sensor data** - Devices has stopped sending sensor data.</span></span> <span data-ttu-id="c1f41-123">Vom Gerät können eingeschränkte Warnungen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="c1f41-123">Limited alerts can be triggered from the device.</span></span>
  - <span data-ttu-id="c1f41-124">**Beeinträchtigte Kommunikation** : Die Kommunikation mit dem Gerät ist beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="c1f41-124">**Impaired communications** - Ability to communicate with device is impaired.</span></span> <span data-ttu-id="c1f41-125">Das Senden von Dateien für eine tiefe Analyse, das Blockieren von Dateien, das Isolieren des Geräts vom Netzwerk und andere Aktionen, die eine Kommunikation mit dem Gerät erfordern, funktionieren möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="c1f41-125">Sending files for deep analysis, blocking files, isolating device from network and other actions that require communication with the device may not work.</span></span>
- <span data-ttu-id="c1f41-126">**Inaktiv** – Geräte, die die Berichterstellung an den Defender for Endpoint-Dienst beendet haben.</span><span class="sxs-lookup"><span data-stu-id="c1f41-126">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service.</span></span>

<span data-ttu-id="c1f41-127">Sie können die gesamte Liste auch im CSV-Format mit dem **Export-Feature** herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c1f41-127">You can also download the entire list in CSV format using the **Export** feature.</span></span> <span data-ttu-id="c1f41-128">Weitere Informationen zu Filtern finden Sie unter [Anzeigen und Organisieren der Geräteliste](machines-view-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c1f41-128">For more information on filters, see [View and organize the Devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="c1f41-129">Exportieren Sie die Liste im CSV-Format, um die ungefilterten Daten anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="c1f41-129">Export the list in CSV format to display the unfiltered data.</span></span> <span data-ttu-id="c1f41-130">Die CSV-Datei enthält alle Geräte in der Organisation, unabhängig davon, welche Filterung in der Ansicht selbst angewendet wird. Je nachdem, wie groß Ihre Organisation ist, kann es sehr viel Zeit dauern, bis sie heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="c1f41-130">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.</span></span>

![Screenshot der Gerätelistenseite](images/atp-devices-list-page.png)

<span data-ttu-id="c1f41-132">Sie können die Gerätedetails anzeigen, wenn Sie auf ein falsch konfiguriertes oder inaktives Gerät klicken.</span><span class="sxs-lookup"><span data-stu-id="c1f41-132">You can view the device details when you click on a misconfigured or inactive device.</span></span>

## <a name="related-topic"></a><span data-ttu-id="c1f41-133">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="c1f41-133">Related topic</span></span>
- [<span data-ttu-id="c1f41-134">Beheben fehlerhafter Sensoren in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c1f41-134">Fix unhealthy sensors in Defender for Endpoint</span></span>](fix-unhealthy-sensors.md)
