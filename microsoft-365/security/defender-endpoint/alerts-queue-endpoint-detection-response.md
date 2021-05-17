---
title: Benachrichtigungswarteschlange in Microsoft Defender Security Center
ms.reviewer: ''
description: Anzeigen und Verwalten der Warnungen, die in der Microsoft Defender Security Center
keywords: ''
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
ms.topic: conceptual
ms.date: 09/03/2018
ms.technology: mde
ms.openlocfilehash: d40fc887f26dfe62e05f7ee6ac7bbbb8ac45a402
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067400"
---
# <a name="alerts-queue-in-microsoft-defender-security-center"></a><span data-ttu-id="87b79-103">Benachrichtigungswarteschlange in Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="87b79-103">Alerts queue in Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="87b79-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="87b79-104">**Applies to:**</span></span>
- [<span data-ttu-id="87b79-105">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="87b79-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="87b79-106">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="87b79-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="87b79-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="87b79-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="87b79-108">Erfahren Sie, wie Sie die Warteschlange anzeigen und verwalten können, damit Sie Bedrohungen effektiv untersuchen können, die auf Entitäten wie Geräten, Dateien oder Benutzerkonten zu sehen sind.</span><span class="sxs-lookup"><span data-stu-id="87b79-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="87b79-109">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="87b79-109">In this section</span></span>
<span data-ttu-id="87b79-110">Thema</span><span class="sxs-lookup"><span data-stu-id="87b79-110">Topic</span></span> | <span data-ttu-id="87b79-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87b79-111">Description</span></span> 
:---|:---
[<span data-ttu-id="87b79-112">Anzeigen und Organisieren der Benachrichtigungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="87b79-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="87b79-113">Zeigt eine Liste der Warnungen an, die in Ihrem Netzwerk gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="87b79-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="87b79-114">Verwalten von Warnungen</span><span class="sxs-lookup"><span data-stu-id="87b79-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="87b79-115">Erfahren Sie, wie Sie Warnungen verwalten können, z. B. den Status ändern, sie einem Mitglied des Sicherheitsbetriebs zuweisen und den Verlauf einer Warnung anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="87b79-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="87b79-116">Untersuchen von Warnungen</span><span class="sxs-lookup"><span data-stu-id="87b79-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="87b79-117">Untersuchen Sie Warnungen, die Sich auf Ihr Netzwerk ausdingen, verstehen Sie, was sie bedeuten, und wie Sie sie beheben können.</span><span class="sxs-lookup"><span data-stu-id="87b79-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="87b79-118">Untersuchen von Dateien</span><span class="sxs-lookup"><span data-stu-id="87b79-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="87b79-119">Untersuchen Sie die Details einer Datei, die einer bestimmten Warnung, einem bestimmten Verhalten oder einem bestimmten Ereignis zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="87b79-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="87b79-120">Untersuchen von Geräten</span><span class="sxs-lookup"><span data-stu-id="87b79-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="87b79-121">Untersuchen Sie die Details eines Geräts, das einer bestimmten Warnung, einem bestimmten Verhalten oder einem bestimmten Ereignis zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="87b79-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="87b79-122">Untersuchen einer IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="87b79-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="87b79-123">Untersuchen Sie die mögliche Kommunikation zwischen Geräten in Ihrem Netzwerk und ip-Adressen (External Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="87b79-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="87b79-124">Untersuchen einer Domain</span><span class="sxs-lookup"><span data-stu-id="87b79-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="87b79-125">Untersuchen Sie eine Domäne, um zu ermitteln, ob Geräte und Server in Ihrem Netzwerk mit einer bekannten bösartigen Domäne kommuniziert haben.</span><span class="sxs-lookup"><span data-stu-id="87b79-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="87b79-126">Untersuchen eines Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="87b79-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="87b79-127">Identifizieren Sie Benutzerkonten mit den aktivsten Warnungen, und untersuchen Sie Fälle potenzieller gefährdeter Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="87b79-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  


