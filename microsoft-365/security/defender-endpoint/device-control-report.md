---
title: Schützen der Daten Ihrer Organisation mit gerätesteuerung
description: Überwachen Sie die Datensicherheit Ihrer Organisation über Gerätesteuerungsberichte.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 47eb80af58c948db5997dc9f5edfa5737a796837
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772365"
---
# <a name="protect-your-organizations-data-with-device-control"></a><span data-ttu-id="f67a1-103">Schützen der Daten Ihrer Organisation mit gerätesteuerung</span><span class="sxs-lookup"><span data-stu-id="f67a1-103">Protect your organization’s data with device control</span></span>

<span data-ttu-id="f67a1-104">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span><span class="sxs-lookup"><span data-stu-id="f67a1-104">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span></span>

<span data-ttu-id="f67a1-105">Die Gerätesteuerung von Microsoft Defender für Endpunkt schützt vor Datenverlust, indem die Mediennutzung durch Geräte in Ihrer Organisation überwacht und gesteuert wird, z. B. die Verwendung von Wechselmedien und USB-Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="f67a1-105">Microsoft Defender for Endpoint device control protects against data loss, by monitoring and controlling media use by devices in your organization, such as the use of removable storage devices and USB drives.</span></span>

<span data-ttu-id="f67a1-106">Mit dem Gerätesteuerungsbericht können Sie Ereignisse anzeigen, die sich auf die Mediennutzung beziehen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="f67a1-106">With the device control report, you can view events that relate to media usage, such as:</span></span>

- <span data-ttu-id="f67a1-107">**Überwachungsereignisse:** Zeigt die Anzahl der Überwachungsereignisse an, die auftreten, wenn externe Medien verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="f67a1-107">**Audit events:** Shows the number of audit events that occur when external media is connected.</span></span>
- <span data-ttu-id="f67a1-108">**Richtlinienereignisse:** Zeigt die Anzahl der Richtlinienereignisse an, die auftreten, wenn eine Gerätesteuerungsrichtlinie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f67a1-108">**Policy events:** Shows the number of policy events that occur when a device control policy is triggered.</span></span>

> [!NOTE]
> <span data-ttu-id="f67a1-109">Das Überwachungsereignis zum Nachverfolgen der Mediennutzung ist standardmäßig für Geräte aktiviert, die in Microsoft Defender für Endpunkt integriert sind.</span><span class="sxs-lookup"><span data-stu-id="f67a1-109">The audit event to track media usage is enabled by default for devices onboarded to Microsoft Defender for Endpoint.</span></span>

## <a name="understanding-the-audit-events"></a><span data-ttu-id="f67a1-110">Grundlegendes zu den Überwachungsereignissen</span><span class="sxs-lookup"><span data-stu-id="f67a1-110">Understanding the audit events</span></span>

<span data-ttu-id="f67a1-111">Zu den Überwachungsereignissen gehören:</span><span class="sxs-lookup"><span data-stu-id="f67a1-111">The audit events include:</span></span>

- <span data-ttu-id="f67a1-112">**USB-Laufwerkshalterung und Aufheben der Bereitstellung:** Überwachungsereignisse, die generiert werden, wenn ein USB-Laufwerk bereitgestellt oder die Bereitstellung aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="f67a1-112">**USB drive mount and unmount:** Audit events that are generated when a USB drive is mounted or unmounted.</span></span>
- <span data-ttu-id="f67a1-113">**PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.</span><span class="sxs-lookup"><span data-stu-id="f67a1-113">**PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.</span></span>

## <a name="monitor-device-control-security"></a><span data-ttu-id="f67a1-114">Überwachen der Gerätesteuerungssicherheit</span><span class="sxs-lookup"><span data-stu-id="f67a1-114">Monitor device control security</span></span>

<span data-ttu-id="f67a1-115">Die Gerätesteuerung in Microsoft Defender für Endpunkt ermöglicht Sicherheitsadministratoren Tools, mit denen sie die Gerätesteuerungssicherheit ihrer Organisation über Berichte nachverfolgen können.</span><span class="sxs-lookup"><span data-stu-id="f67a1-115">Device control in Microsoft Defender for Endpoint empowers security administrators with tools that enable them to track their organization’s device control security through reports.</span></span> <span data-ttu-id="f67a1-116">Sie finden den Gerätesteuerungsbericht im Microsoft 365 Security Center, indem Sie zu **"Berichte > Geräteschutz"** wechseln.</span><span class="sxs-lookup"><span data-stu-id="f67a1-116">You can find the device control report in the Microsoft 365 security center by going to **Reports > Device protection**.</span></span>

<span data-ttu-id="f67a1-117">Die Karte "Geräteschutz" im **Dashboard "Berichte"** zeigt die Anzahl von Überwachungsereignissen an, die vom Medientyp in den letzten 180 Tagen generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f67a1-117">The Device protection card on the **Reports** dashboard shows the number of audit events generated by media type, over the last 180 days.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f67a1-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span><span class="sxs-lookup"><span data-stu-id="f67a1-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span></span>

<span data-ttu-id="f67a1-119">Die Schaltfläche **"Details anzeigen"** zeigt weitere Mediennutzungsdaten auf der Berichtsseite des **Gerätesteuerelements** an.</span><span class="sxs-lookup"><span data-stu-id="f67a1-119">The **View details** button shows more media usage data in the **device control report** page.</span></span>

<span data-ttu-id="f67a1-120">Die Seite bietet ein Dashboard mit der aggregierten Anzahl von Ereignissen pro Typ und einer Liste von Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="f67a1-120">The page provides a dashboard with aggregated number of events per type and a list of events.</span></span> <span data-ttu-id="f67a1-121">Administratoren können nach Zeitbereich, Medienklassenname und Geräte-ID filtern.</span><span class="sxs-lookup"><span data-stu-id="f67a1-121">Administrators can filter on time range, media class name, and device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f67a1-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span><span class="sxs-lookup"><span data-stu-id="f67a1-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span></span>

<span data-ttu-id="f67a1-123">Wenn Sie ein Ereignis auswählen, wird ein Flyout mit weiteren Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f67a1-123">When you select an event, a flyout appears that shows you more information:</span></span>

- <span data-ttu-id="f67a1-124">**Allgemeine Details:** Datum, Aktionsmodus und die Richtlinie dieses Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="f67a1-124">**General details:** Date, Action mode, and the policy of this event.</span></span>
- <span data-ttu-id="f67a1-125">**Medieninformationen:** Medieninformationen umfassen Medienname, Klassenname, Klassen-GUID, Geräte-ID, Anbieter-ID, Volume, Seriennummer und Bustyp.</span><span class="sxs-lookup"><span data-stu-id="f67a1-125">**Media information:** Media information includes Media name, Class name, Class GUID, Device ID, Vendor ID, Volume, Serial number, and Bus type.</span></span>
- <span data-ttu-id="f67a1-126">**Standortdetails:** Gerätename und MDATP Geräte-ID.</span><span class="sxs-lookup"><span data-stu-id="f67a1-126">**Location details:** Device name and MDATP device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f67a1-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span><span class="sxs-lookup"><span data-stu-id="f67a1-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span></span>

<span data-ttu-id="f67a1-128">Um Echtzeitaktivitäten für diese Medien in der gesamten Organisation anzuzeigen, wählen Sie die Schaltfläche **"Erweiterte Suche öffnen"** aus.</span><span class="sxs-lookup"><span data-stu-id="f67a1-128">To see real-time activity for this media across the organization, select the **Open Advanced hunting** button.</span></span> <span data-ttu-id="f67a1-129">Dazu gehört eine eingebettete, vordefinierte Abfrage.</span><span class="sxs-lookup"><span data-stu-id="f67a1-129">This includes an embedded, pre-defined query.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f67a1-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span><span class="sxs-lookup"><span data-stu-id="f67a1-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span></span>

<span data-ttu-id="f67a1-131">Um die Sicherheit des Geräts anzuzeigen, wählen Sie die Schaltfläche **"Geräteseite öffnen"** im Flyout aus.</span><span class="sxs-lookup"><span data-stu-id="f67a1-131">To see the security of the device, select the **Open device page** button on the flyout.</span></span> <span data-ttu-id="f67a1-132">Mit dieser Schaltfläche wird die Geräteentitätsseite geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f67a1-132">This button opens the device entity page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f67a1-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span><span class="sxs-lookup"><span data-stu-id="f67a1-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span></span>

## <a name="reporting-delays"></a><span data-ttu-id="f67a1-134">Melden von Verzögerungen</span><span class="sxs-lookup"><span data-stu-id="f67a1-134">Reporting delays</span></span>

<span data-ttu-id="f67a1-135">Der Gerätesteuerungsbericht kann eine 12-Stunden-Verzögerung von dem Zeitpunkt, zu dem eine Medienverbindung auftritt, bis zu dem Zeitpunkt haben, an dem das Ereignis auf der Karte oder in der Domänenliste wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f67a1-135">The device control report can have a 12-hour delay from the time a media connection occurs to the time the event is reflected in the card or in the domain list.</span></span>
