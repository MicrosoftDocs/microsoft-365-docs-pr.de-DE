---
title: Vorschaufeatures in Microsoft 365 Defender
description: Informationen zu den neuen Features in Microsoft 365 Security.
keywords: Vorschau, neu, m365 security, Sicherheit, 365, Funktionen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 088dbd16c3667331843ff934c80f85aa8d3a837f
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430816"
---
# <a name="microsoft-365-defender-preview-features"></a><span data-ttu-id="927f8-104">Microsoft 365 Defender Vorschaufeatures</span><span class="sxs-lookup"><span data-stu-id="927f8-104">Microsoft 365 Defender preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="927f8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="927f8-105">**Applies to:**</span></span>
- <span data-ttu-id="927f8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="927f8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="927f8-107">Der Microsoft 365 Defender-Dienst wird ständig aktualisiert, um neue Featureverbesserungen und -funktionen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="927f8-107">The Microsoft 365 Defender service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="927f8-108">Erfahren Sie mehr über die neuen Features in der Microsoft 365 Defender Preview-Version und gehören Sie zu den ersten, die anstehende Features ausprobieren, indem Sie die Vorschau aktivieren.</span><span class="sxs-lookup"><span data-stu-id="927f8-108">Learn about new features in the Microsoft 365 Defender preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="927f8-109">Weitere Informationen zu neuen Funktionen, die allgemein verfügbar sind, finden Sie unter [Neuigkeiten in Microsoft 365 Defender](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="927f8-109">For more information on new capabilities that are generally available, see [What's new in Microsoft 365 Defender](whats-new.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="927f8-110">Wissenswertes</span><span class="sxs-lookup"><span data-stu-id="927f8-110">What you need to know</span></span>

<span data-ttu-id="927f8-111">Beim Arbeiten mit Features in der öffentlichen Vorschau werden die folgenden Features verwendet:</span><span class="sxs-lookup"><span data-stu-id="927f8-111">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="927f8-112">Kann eingeschränkte oder eingeschränkte Funktionen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="927f8-112">May have restricted or limited functionality.</span></span> <span data-ttu-id="927f8-113">Beispielsweise kann das Feature nur für eine Plattform gelten.</span><span class="sxs-lookup"><span data-stu-id="927f8-113">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="927f8-114">Durchlaufen Sie in der Regel Funktionsänderungen, bevor sie allgemein verfügbar sind (GA).</span><span class="sxs-lookup"><span data-stu-id="927f8-114">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="927f8-115">Werden von Microsoft vollständig unterstützt.</span><span class="sxs-lookup"><span data-stu-id="927f8-115">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="927f8-116">Kann nur in ausgewählten geografischen Regionen oder Cloudumgebungen verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="927f8-116">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="927f8-117">Beispielsweise ist das Feature möglicherweise nicht in der Government Cloud vorhanden.</span><span class="sxs-lookup"><span data-stu-id="927f8-117">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="927f8-118">Einzelne Features in der Vorschau weisen möglicherweise mehr Nutzungs- und Supporteinschränkungen auf.</span><span class="sxs-lookup"><span data-stu-id="927f8-118">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="927f8-119">Wenn ja, werden diese Informationen in der Regel in der Featuredokumentation aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="927f8-119">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="927f8-120">Die Vorschauversionen werden standardmäßig unterstützt und können für Produktionsumgebungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="927f8-120">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="required-permissions"></a><span data-ttu-id="927f8-121">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="927f8-121">Required permissions</span></span>

<span data-ttu-id="927f8-122">Konten, die den folgenden Azure Active Directory (Azure AD)-Rollen zugewiesen sind, können Microsoft 365 Defender Vorschaufeatures aktivieren:</span><span class="sxs-lookup"><span data-stu-id="927f8-122">Accounts assigned the following Azure Active Directory (Azure AD) roles can turn on Microsoft 365 Defender Preview features:</span></span>

- <span data-ttu-id="927f8-123">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="927f8-123">Global administrator</span></span>
- <span data-ttu-id="927f8-124">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="927f8-124">Security administrator</span></span>
- <span data-ttu-id="927f8-125">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="927f8-125">Security Operator</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="927f8-126">Vorschaufeatures aktivieren</span><span class="sxs-lookup"><span data-stu-id="927f8-126">Turn on preview features</span></span>

<span data-ttu-id="927f8-127">Sie haben Zugriff auf bevorstehende Features, zu denen Sie Feedback geben können, um die Gesamterfahrung zu verbessern, bevor Features allgemein verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="927f8-127">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="927f8-128">Aktivieren Sie die Einstellung für die Vorschauerfahrung, um zu den ersten zu gehören, die kommende Features ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="927f8-128">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="927f8-129">Wählen Sie im Navigationsbereich **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="927f8-129">In the navigation pane, select **Settings**.</span></span>
2. <span data-ttu-id="927f8-130">Wählen Sie **Microsoft 365 Defender** aus.</span><span class="sxs-lookup"><span data-stu-id="927f8-130">Select **Microsoft 365 Defender**.</span></span>
3. <span data-ttu-id="927f8-131">Wählen Sie **Vorschaufeatures** > **Aktivieren Sie Vorschaufeatures**.</span><span class="sxs-lookup"><span data-stu-id="927f8-131">Select **Preview features** > **Turn on preview features**.</span></span> 
4. <span data-ttu-id="927f8-132">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="927f8-132">Select **Save**.</span></span>

<span data-ttu-id="927f8-133">Sie wissen, dass Sie Vorschaufeatures aktiviert haben, wenn Sie sehen, dass das Kontrollkästchen **Vorschaufeatures aktivieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="927f8-133">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="927f8-134">Vorschaufeatures</span><span class="sxs-lookup"><span data-stu-id="927f8-134">Preview features</span></span>

<span data-ttu-id="927f8-135">Die folgenden Features und Verbesserungen sind derzeit in der Vorschau verfügbar:</span><span class="sxs-lookup"><span data-stu-id="927f8-135">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="927f8-136">**[Anzeigen von Berichten pro Bedrohungstags](threat-analytics.md#view-reports-per-threat-tags)** – Bedrohungstags helfen Ihnen, sich auf bestimmte Bedrohungskategorien zu konzentrieren und die relevantesten Berichte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="927f8-136">**[View reports per threat tags](threat-analytics.md#view-reports-per-threat-tags)** - Threat tags help you focus on specific threat categories and review the most relevant reports.</span></span>
- <span data-ttu-id="927f8-137">**[Streaming-API](../defender-endpoint/raw-data-export.md)** – Microsoft 365 Defender unterstützt das Streamen aller über die erweiterte Suche verfügbaren Ereignisse an Event Hubs und/oder Azure-Speicherkonten.</span><span class="sxs-lookup"><span data-stu-id="927f8-137">**[Streaming API](../defender-endpoint/raw-data-export.md)** - Microsoft 365 Defender supports streaming all the events available through Advanced Hunting to an Event Hubs and/or Azure storage account.</span></span>
- <span data-ttu-id="927f8-138">**[Microsoft 365 Defender-APIs](api-overview.md)** : Mit den APIs auf oberster Ebene Microsoft 365 Defender können Sie Workflows basierend auf den freigegebenen Vorfall- und erweiterten Suchtabellen automatisieren.</span><span class="sxs-lookup"><span data-stu-id="927f8-138">**[Microsoft 365 Defender APIs](api-overview.md)** - The top-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span> 
- <span data-ttu-id="927f8-139">**[Ergreifen Sie Maßnahmen bei der erweiterten Suche](advanced-hunting-take-action.md)** – Schließen Sie schnell Bedrohungen ein, oder beheben Sie kompromittierte Ressourcen, die Sie bei der [erweiterten Suche](advanced-hunting-overview.md)finden.</span><span class="sxs-lookup"><span data-stu-id="927f8-139">**[Take action in advanced hunting](advanced-hunting-take-action.md)** - Quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md).</span></span>
- <span data-ttu-id="927f8-140">**[In-Portal-Schemareferenz](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** – Abrufen von Informationen zu Schematabellen für die erweiterte Suche direkt im Security Center.</span><span class="sxs-lookup"><span data-stu-id="927f8-140">**[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - Get information about advanced hunting schema tables directly in the security center.</span></span> <span data-ttu-id="927f8-141">Zusätzlich zu Tabellen- und Spaltenbeschreibungen enthält diese Referenz unterstützte Ereignistypen ( `ActionType` Werte) und Beispielabfragen.</span><span class="sxs-lookup"><span data-stu-id="927f8-141">In addition to table and column descriptions, this reference includes supported event types (`ActionType` values) and sample queries.</span></span>
- <span data-ttu-id="927f8-142">**[DeviceFromIP()-Funktion](advanced-hunting-devicefromip-function.md)** – Abrufen von Informationen darüber, welchen Geräten zu einem bestimmten Zeitraum eine bestimmte IP-Adresse oder Adressen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="927f8-142">**[DeviceFromIP() function](advanced-hunting-devicefromip-function.md)** - Get information about which devices have been assigned a specific IP address or addresses at a given time range.</span></span>
