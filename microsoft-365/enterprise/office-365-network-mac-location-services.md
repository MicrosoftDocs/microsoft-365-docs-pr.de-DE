---
title: Microsoft 365 Network Connectivity Location Services (Vorschau)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/31/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Connectivity Location Services (Vorschau)
ms.openlocfilehash: e614e719069a74ea087b07ca624ae0450790c763
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690707"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a><span data-ttu-id="528a2-103">Microsoft 365 Network Connectivity Location Services (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="528a2-103">Microsoft 365 Network Connectivity Location Services (preview)</span></span>

<span data-ttu-id="528a2-104">Das Microsoft 365 Admin Center zeigt nun **Netzwerk Einblicke und Leistungsempfehlungen**an, bei denen es sich um Live-Leistungs Metriken handelt, die von Ihrem Microsoft 365-Mandanten gesammelt und nur für administrative Benutzer in Ihrem Mandanten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="528a2-104">The Microsoft 365 Admin Center now shows **Network Insights and performance recommendations**, which are live performance metrics collected from your Microsoft 365 tenant and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="528a2-105">Die Netzwerkkonnektivität des Unternehmens wird pro Bürostandort über einen Netzwerk Ausstieg-Standort im Internet entwickelt.</span><span class="sxs-lookup"><span data-stu-id="528a2-105">Organizational network connectivity is designed per office location through a network egress location to the Internet.</span></span> <span data-ttu-id="528a2-106">Die Microsoft 365-Clientkonnektivität verwendet diese Route und dann über das Internet an Microsoft-Dienst-Front-Door-Server.</span><span class="sxs-lookup"><span data-stu-id="528a2-106">Microsoft 365 client connectivity uses that route and then across the Internet to Microsoft service front door servers.</span></span> <span data-ttu-id="528a2-107">Das Identifizieren von Office-Standorten ist der Schlüssel, um diese Netzwerk Einblicke anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="528a2-107">Identifying office locations is key to being able to show these network insights.</span></span>

## <a name="location-in-network-measurements"></a><span data-ttu-id="528a2-108">Speicherort in Netzwerk Messungen</span><span class="sxs-lookup"><span data-stu-id="528a2-108">Location in network measurements</span></span>

<span data-ttu-id="528a2-109">Der Administrator einer Organisation kann sich dafür entscheiden, dass der Standort in die Netzwerk Messungen einbezogen wird, die von dieser Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="528a2-109">An organization's administrator can opt in for location to be included in the network measurements used by this feature.</span></span> <span data-ttu-id="528a2-110">Dadurch wird die automatische Erkennung der Stadt ermöglicht, in der sich die einzelnen Büros befinden.</span><span class="sxs-lookup"><span data-stu-id="528a2-110">This enables auto-discovery of the city where each office is located.</span></span> <span data-ttu-id="528a2-111">Standortinformationen sind nicht präzise und werden bis zu 300m verborgen und nach Ort kategorisiert.</span><span class="sxs-lookup"><span data-stu-id="528a2-111">Location information is not precise and is obfuscated to 300m and categorized by city.</span></span> <span data-ttu-id="528a2-112">Zu dem Zeitpunkt, an dem ein Standort auf einem Windows-Gerät erfasst wird, wird ein **Standort** Symbol in der Taskleiste angezeigt, und Administratoren möchten Benutzer möglicherweise darüber informieren.</span><span class="sxs-lookup"><span data-stu-id="528a2-112">At the time when location is captured on a Windows device it will show a **Location In-Use** icon in the tool tray and administrators may want to notify users of this.</span></span> <span data-ttu-id="528a2-113">Bei dieser Verarbeitung wird der Standort als Organisationsbüro Standort und nicht als Standort einer Person oder eines Geräts behandelt.</span><span class="sxs-lookup"><span data-stu-id="528a2-113">With this processing, the location is treated as the organization office location and not the location of a person or a device.</span></span> <span data-ttu-id="528a2-114">Netzwerk Einblicke können an diesen entdeckten Bürostandort Städten gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="528a2-114">Network insights can be shown at these discovered office location cities.</span></span> <span data-ttu-id="528a2-115">Wenn eine größere Genauigkeit von Empfehlungen gewünscht wird, kann ein Administrator bestimmte Office-Standortadressen eingeben, und die Einblicke in das Netzwerk werden auf diese statt aggregiert.</span><span class="sxs-lookup"><span data-stu-id="528a2-115">If greater accuracy of recommendations is desired, an administrator can enter specific office location addresses and the network insights will be aggregated to those instead.</span></span> <span data-ttu-id="528a2-116">Office-Standorte können nicht enger als 300 Meter aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="528a2-116">Office locations cannot be aggregated more closely than 300 meters.</span></span>

## <a name="location-in-the-microsoft-365-admin-center"></a><span data-ttu-id="528a2-117">Speicherort im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="528a2-117">Location in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="528a2-118">Im Microsoft 365 Admin Center werden Bing Map-Steuerelemente verwendet, um anzuzeigen, wo sich die Standort Organisation befinden, und um die Netzwerkumkreis Topologie für einen ausgewählten Office-Standort anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="528a2-118">In the Microsoft 365 Admin Center, Bing map controls are used to show where organization office locations are and to show network perimeter topology for a selected office location.</span></span> <span data-ttu-id="528a2-119">Wenn ein Administrator bestimmte Adressdetails für Office-Standorte hinzufügt, wird Bing Maps auch verwendet, um Adressen anzudeuten, um die Dateneingabe zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="528a2-119">When an administrator adds specific address details for office locations, Bing Maps is also used to suggest addresses to make data entry easier.</span></span>

## <a name="terms-of-use"></a><span data-ttu-id="528a2-120">Nutzungsbedingungen</span><span class="sxs-lookup"><span data-stu-id="528a2-120">Terms of Use</span></span>

<span data-ttu-id="528a2-121">Alle Inhalte, die über Bing Maps zur Verfügung gestellt werden, einschließlich Geocodes, können nur innerhalb des Produkts verwendet werden, über das der Inhalt bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="528a2-121">Any content provided through Bing Maps, including geocodes, can only be used within the product through which the content is provided.</span></span> <span data-ttu-id="528a2-122">Die Verwendung des Microsoft 365 Admin Center Location Services-Features, betrieben von Bing Maps, richtet sich nach den _Nutzungsbedingungen von Bing Maps Endbenutzer_ , <https://go.microsoft.com/?linkid=9710837> die unter und der _Microsoft-Datenschutzerklärung_ verfügbar sind unter <https://go.microsoft.com/fwlink/?LinkID=248686.></span><span class="sxs-lookup"><span data-stu-id="528a2-122">Customer's use of the Microsoft 365 Admin Center Location Services feature, powered by Bing Maps, is governed by the _Bing Maps End User Terms of Use_ available at <https://go.microsoft.com/?linkid=9710837> and the _Microsoft Privacy Statement_ available at <https://go.microsoft.com/fwlink/?LinkID=248686.></span></span>

<span data-ttu-id="528a2-123">Dieses Feature, das über Bing Maps bereitgestellt wird, wird auch von **here Technologies**unterstützt.</span><span class="sxs-lookup"><span data-stu-id="528a2-123">This feature, provided through Bing Maps, is also supported by **Here Technologies**.</span></span> <span data-ttu-id="528a2-124">Wie Bing Maps die von hier bereitgestellten Standortdienste nutzt Technologien unterliegen den _hier angebotenen Technologien-Dienstbedingungen_ <https://legal.here.com/en-gb/terms> .</span><span class="sxs-lookup"><span data-stu-id="528a2-124">How Bing Maps leverages location services provided by Here Technologies is governed by the _Here Technologies Service Terms_ available at <https://legal.here.com/en-gb/terms>.</span></span>