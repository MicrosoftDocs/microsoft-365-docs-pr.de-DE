---
title: Vorschaufeatures für Microsoft Defender für Endpunkt
description: Erfahren Sie, wie Sie auf die Vorschaufeatures von Microsoft Defender für Endpunkt zugreifen.
keywords: Vorschau, Vorschau, Microsoft Defender für Endpunkt, Features, Updates
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0ed494cc29eb990430be590e62db5f0365ace494
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322425"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="99379-104">Vorschaufeatures für Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="99379-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="99379-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="99379-105">**Applies to:**</span></span>
- [<span data-ttu-id="99379-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="99379-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="99379-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99379-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="99379-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="99379-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="99379-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="99379-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="99379-110">Der Defender für Endpunkt-Dienst wird ständig aktualisiert, um neue Featureverbesserungen und Funktionen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="99379-110">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="99379-111">Erfahren Sie mehr über die neuen Features in der Defender für Endpunkt-Vorschauversion und gehören Sie zu den ersten, die anstehende Features ausprobieren, indem Sie die Vorschau aktivieren.</span><span class="sxs-lookup"><span data-stu-id="99379-111">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="99379-112">Erhalten Sie Benachrichtigungen, wenn diese Seite aktualisiert wird, indem Sie die folgende URL kopieren und in Ihren Feedleser einfügen: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="99379-112">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="99379-113">Weitere Informationen zu neuen Funktionen, die allgemein verfügbar sind, finden Sie unter [Neuigkeiten in Defender für Endpunkt.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="99379-113">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="99379-114">Wissenswertes</span><span class="sxs-lookup"><span data-stu-id="99379-114">What you need to know</span></span>

<span data-ttu-id="99379-115">Beim Arbeiten mit Features in der öffentlichen Vorschau werden die folgenden Features verwendet:</span><span class="sxs-lookup"><span data-stu-id="99379-115">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="99379-116">Kann eingeschränkte oder eingeschränkte Funktionen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="99379-116">May have restricted or limited functionality.</span></span> <span data-ttu-id="99379-117">Beispielsweise kann das Feature nur für eine Plattform gelten.</span><span class="sxs-lookup"><span data-stu-id="99379-117">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="99379-118">Durchlaufen Sie in der Regel Funktionsänderungen, bevor sie allgemein verfügbar sind (GA).</span><span class="sxs-lookup"><span data-stu-id="99379-118">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="99379-119">Werden von Microsoft vollständig unterstützt.</span><span class="sxs-lookup"><span data-stu-id="99379-119">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="99379-120">Kann nur in ausgewählten geografischen Regionen oder Cloudumgebungen verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="99379-120">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="99379-121">Beispielsweise ist das Feature möglicherweise nicht in der Government Cloud vorhanden.</span><span class="sxs-lookup"><span data-stu-id="99379-121">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="99379-122">Einzelne Features in der Vorschau weisen möglicherweise mehr Nutzungs- und Supporteinschränkungen auf.</span><span class="sxs-lookup"><span data-stu-id="99379-122">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="99379-123">Wenn ja, werden diese Informationen in der Regel in der Featuredokumentation aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="99379-123">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="99379-124">Die Vorschauversionen werden mit einer standardmäßigen Supportstufe bereitgestellt und für Produktionsarbeitslasten empfohlen.</span><span class="sxs-lookup"><span data-stu-id="99379-124">The preview versions are provided with a standard support level, and it is recommended for production workloads.</span></span> 



## <a name="turn-on-preview-features"></a><span data-ttu-id="99379-125">Vorschaufeatures aktivieren</span><span class="sxs-lookup"><span data-stu-id="99379-125">Turn on preview features</span></span>

<span data-ttu-id="99379-126">Sie haben Zugriff auf bevorstehende Features, zu denen Sie Feedback geben können, um die Gesamterfahrung zu verbessern, bevor Features allgemein verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="99379-126">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="99379-127">Aktivieren Sie die Einstellung für die Vorschauerfahrung, um zu den ersten zu gehören, die kommende Features ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="99379-127">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="99379-128">Wählen Sie im Navigationsbereich **Einstellungen**  >    >  **Vorschaufeatures** für erweiterte Features aus.</span><span class="sxs-lookup"><span data-stu-id="99379-128">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="99379-129">Schalten Sie die Einstellung zwischen **"Ein"** und **"Aus"** um, und wählen Sie **"Einstellungen speichern" aus.**</span><span class="sxs-lookup"><span data-stu-id="99379-129">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="99379-130">Vorschaufeatures</span><span class="sxs-lookup"><span data-stu-id="99379-130">Preview features</span></span>

<span data-ttu-id="99379-131">In der Vorschauversion sind die folgenden Features enthalten:</span><span class="sxs-lookup"><span data-stu-id="99379-131">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="99379-132">Webinhaltsfilterung</span><span class="sxs-lookup"><span data-stu-id="99379-132">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="99379-133">Die Webinhaltsfilterung ist Teil der Webschutzfunktionen in Microsoft Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="99379-133">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="99379-134">Es ermöglicht Ihrer Organisation, den Zugriff auf Websites basierend auf ihren Inhaltskategorien nachzuverfolgen und zu regeln.</span><span class="sxs-lookup"><span data-stu-id="99379-134">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="99379-135">Viele dieser Websites, obwohl sie nicht bösartig sind, können aufgrund von Compliance-Vorschriften, Bandbreitennutzung oder anderen Bedenken problematisch sein.</span><span class="sxs-lookup"><span data-stu-id="99379-135">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="99379-136">Bericht „Geräteintegrität und -Compliance“</span><span class="sxs-lookup"><span data-stu-id="99379-136">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="99379-137">Der Bericht über Geräteintegrität und -compliance enthält allgemeine Informationen zu den Geräten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="99379-137">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="99379-138">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="99379-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="99379-139">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="99379-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
