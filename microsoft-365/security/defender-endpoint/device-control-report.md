---
title: Schützen der Daten Ihrer Organisation mit Gerätesteuerung
description: Überwachen Sie die Datensicherheit Ihrer Organisation über Gerätesteuerungsberichte.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: dansimp
author: dansimp
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: ee8e7be20076bde41867981008e53a70c134e47e
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893799"
---
# <a name="protect-your-organizations-data-with-device-control"></a><span data-ttu-id="11d11-103">Schützen der Daten Ihrer Organisation mit Gerätesteuerung</span><span class="sxs-lookup"><span data-stu-id="11d11-103">Protect your organization’s data with device control</span></span>

<span data-ttu-id="11d11-104">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span><span class="sxs-lookup"><span data-stu-id="11d11-104">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span></span>

<span data-ttu-id="11d11-105">Die Gerätesteuerung von Microsoft Defender for Endpoint schützt vor Datenverlust durch Überwachen und Steuern der Mediennutzung durch Geräte in Ihrer Organisation, z. B. die Verwendung von Wechselmedien und USB-Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="11d11-105">Microsoft Defender for Endpoint device control protects against data loss, by monitoring and controlling media use by devices in your organization, such as the use of removable storage devices and USB drives.</span></span>

<span data-ttu-id="11d11-106">Mit dem Gerätesteuerungsbericht können Sie Ereignisse anzeigen, die sich auf die Mediennutzung beziehen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="11d11-106">With the device control report, you can view events that relate to media usage, such as:</span></span>

- <span data-ttu-id="11d11-107">**Überwachungsereignisse:** Zeigt die Anzahl der Überwachungsereignisse an, die auftreten, wenn externe Medien verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="11d11-107">**Audit events:** Shows the number of audit events that occur when external media is connected.</span></span>
- <span data-ttu-id="11d11-108">**Richtlinienereignisse:** Zeigt die Anzahl der Richtlinienereignisse an, die auftreten, wenn eine Gerätesteuerungsrichtlinie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="11d11-108">**Policy events:** Shows the number of policy events that occur when a device control policy is triggered.</span></span>

> [!NOTE]
> <span data-ttu-id="11d11-109">Das Überwachungsereignis zum Nachverfolgen der Mediennutzung ist standardmäßig für Geräte aktiviert, die in Microsoft Defender for Endpoint onboarded sind.</span><span class="sxs-lookup"><span data-stu-id="11d11-109">The audit event to track media usage is enabled by default for devices onboarded to Microsoft Defender for Endpoint.</span></span>

## <a name="understanding-the-audit-events"></a><span data-ttu-id="11d11-110">Grundlegendes zu den Überwachungsereignissen</span><span class="sxs-lookup"><span data-stu-id="11d11-110">Understanding the audit events</span></span>

<span data-ttu-id="11d11-111">Zu den Überwachungsereignissen gehören:</span><span class="sxs-lookup"><span data-stu-id="11d11-111">The audit events include:</span></span>

- <span data-ttu-id="11d11-112">**USB-Laufwerkhalterung und Unmount:** Überwachung von Ereignissen, die generiert werden, wenn ein USB-Laufwerk bereitgestellt oder nicht bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="11d11-112">**USB drive mount and unmount:** Audit events that are generated when a USB drive is mounted or unmounted.</span></span>
- <span data-ttu-id="11d11-113">**PnP:** Plug-and-Play-Überwachungsereignisse werden generiert, wenn wechselbarer Speicher, ein Drucker oder Bluetooth angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="11d11-113">**PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.</span></span>

## <a name="monitor-device-control-security"></a><span data-ttu-id="11d11-114">Überwachen der Gerätesteuerungssicherheit</span><span class="sxs-lookup"><span data-stu-id="11d11-114">Monitor device control security</span></span>

<span data-ttu-id="11d11-115">Die Gerätesteuerung in Microsoft Defender for Endpoint ermöglicht Sicherheitsadministratoren Tools, mit denen sie die Gerätesteuerungssicherheit ihrer Organisation über Berichte nachverfolgen können.</span><span class="sxs-lookup"><span data-stu-id="11d11-115">Device control in Microsoft Defender for Endpoint empowers security administrators with tools that enable them to track their organization’s device control security through reports.</span></span> <span data-ttu-id="11d11-116">Den Gerätesteuerungsbericht finden Sie im Microsoft 365 Security Center unter **Berichte > Geräteschutz**.</span><span class="sxs-lookup"><span data-stu-id="11d11-116">You can find the device control report in the Microsoft 365 security center by going to **Reports > Device protection**.</span></span>

<span data-ttu-id="11d11-117">Die Geräteschutzkarte im Dashboard **Berichte** zeigt die Anzahl der Überwachungsereignisse an, die in den letzten 180 Tagen vom Medientyp generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="11d11-117">The Device protection card on the **Reports** dashboard shows the number of audit events generated by media type, over the last 180 days.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11d11-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span><span class="sxs-lookup"><span data-stu-id="11d11-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span></span>

<span data-ttu-id="11d11-119">Die **Schaltfläche Details anzeigen** zeigt auf der Seite Gerätesteuerungsbericht weitere **Mediennutzungsdaten** an.</span><span class="sxs-lookup"><span data-stu-id="11d11-119">The **View details** button shows more media usage data in the **device control report** page.</span></span>

<span data-ttu-id="11d11-120">Die Seite stellt ein Dashboard mit der aggregierten Anzahl von Ereignissen pro Typ und einer Liste von Ereignissen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="11d11-120">The page provides a dashboard with aggregated number of events per type and a list of events.</span></span> <span data-ttu-id="11d11-121">Administratoren können nach Zeitbereich, Medienklassenname und Geräte-ID filtern.</span><span class="sxs-lookup"><span data-stu-id="11d11-121">Administrators can filter on time range, media class name, and device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11d11-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span><span class="sxs-lookup"><span data-stu-id="11d11-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span></span>

<span data-ttu-id="11d11-123">Wenn Sie ein Ereignis auswählen, wird ein Flyout mit weiteren Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="11d11-123">When you select an event, a flyout appears that shows you more information:</span></span>

- <span data-ttu-id="11d11-124">**Allgemeine Details:** Datum, Aktionsmodus und die Richtlinie dieses Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="11d11-124">**General details:** Date, Action mode, and the policy of this event.</span></span>
- <span data-ttu-id="11d11-125">**Medieninformationen:** Medieninformationen umfassen Medienname, Klassenname, Klassen-GUID, Geräte-ID, Hersteller-ID, Volume, Seriennummer und Bustyp.</span><span class="sxs-lookup"><span data-stu-id="11d11-125">**Media information:** Media information includes Media name, Class name, Class GUID, Device ID, Vendor ID, Volume, Serial number, and Bus type.</span></span>
- <span data-ttu-id="11d11-126">**Standortdetails:** Gerätename und MDATP-Geräte-ID.</span><span class="sxs-lookup"><span data-stu-id="11d11-126">**Location details:** Device name and MDATP device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11d11-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span><span class="sxs-lookup"><span data-stu-id="11d11-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span></span>

<span data-ttu-id="11d11-128">Um Echtzeitaktivitäten für diese Medien in der gesamten Organisation zu sehen, wählen Sie die Schaltfläche **Erweiterte** Suche öffnen aus.</span><span class="sxs-lookup"><span data-stu-id="11d11-128">To see real-time activity for this media across the organization, select the **Open Advanced hunting** button.</span></span> <span data-ttu-id="11d11-129">Dies umfasst eine eingebettete, vordefinierte Abfrage.</span><span class="sxs-lookup"><span data-stu-id="11d11-129">This includes an embedded, pre-defined query.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11d11-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span><span class="sxs-lookup"><span data-stu-id="11d11-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span></span>

<span data-ttu-id="11d11-131">Um die Sicherheit des Geräts zu sehen, wählen Sie im **Flyout** die Schaltfläche Geräteseite öffnen aus.</span><span class="sxs-lookup"><span data-stu-id="11d11-131">To see the security of the device, select the **Open device page** button on the flyout.</span></span> <span data-ttu-id="11d11-132">Mit dieser Schaltfläche wird die Geräteentitätsseite geöffnet.</span><span class="sxs-lookup"><span data-stu-id="11d11-132">This button opens the device entity page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11d11-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span><span class="sxs-lookup"><span data-stu-id="11d11-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span></span>

## <a name="reporting-delays"></a><span data-ttu-id="11d11-134">Verzögerungen bei der Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="11d11-134">Reporting delays</span></span>

<span data-ttu-id="11d11-135">Der Gerätesteuerungsbericht kann eine Verzögerung von 12 Stunden von dem Zeitpunkt einer Medienverbindung bis zu dem Zeitpunkt haben, zu dem das Ereignis in der Karte oder in der Domänenliste widergespiegelt wird.</span><span class="sxs-lookup"><span data-stu-id="11d11-135">The device control report can have a 12-hour delay from the time a media connection occurs to the time the event is reflected in the card or in the domain list.</span></span>
