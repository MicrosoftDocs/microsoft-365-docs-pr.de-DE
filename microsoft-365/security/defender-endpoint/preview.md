---
title: Microsoft Defender ATP-Vorschaufeatures
description: Erfahren Sie, wie Sie auf Microsoft Defender for Endpoint-Vorschaufeatures zugreifen.
keywords: Vorschau, Vorschau, Microsoft Defender for Endpoint, Features, Updates
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
ms.openlocfilehash: 370048586c5ddfa6fa9ea265e929608357adf5df
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186881"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="9e140-104">Microsoft Defender for Endpoint -Vorschaufeatures</span><span class="sxs-lookup"><span data-stu-id="9e140-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="9e140-105">Die Vorschauversionen werden ohne Vereinbarung zum Servicelevel bereitgestellt und werden für Produktionsworkloads nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9e140-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="9e140-106">Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen möglicherweise über eingeschränkte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="9e140-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="9e140-107">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9e140-107">**Applies to:**</span></span>
- [<span data-ttu-id="9e140-108">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9e140-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9e140-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e140-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9e140-110">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9e140-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9e140-111">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9e140-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="9e140-112">Der Defender for Endpoint-Dienst wird ständig aktualisiert, um neue Funktionserweiterungen und -funktionen zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="9e140-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

> [!TIP]
> <span data-ttu-id="9e140-113">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9e140-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9e140-114">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9e140-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-abovefoldlink)

<span data-ttu-id="9e140-115">Erfahren Sie mehr über neue Features in der Defender for Endpoint-Vorschauversion, und testen Sie als erstes die kommenden Features, indem Sie die Vorschaufunktion aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9e140-115">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="9e140-116">Erhalten Sie eine Benachrichtigung, wenn diese Seite aktualisiert wird, indem Sie die folgende URL in Ihren Feedleser kopieren und einfügen: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span><span class="sxs-lookup"><span data-stu-id="9e140-116">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span></span>

<span data-ttu-id="9e140-117">Weitere Informationen zu neuen Funktionen, die allgemein verfügbar sind, finden Sie unter [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span><span class="sxs-lookup"><span data-stu-id="9e140-117">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="9e140-118">Vorschaufeatures aktivieren</span><span class="sxs-lookup"><span data-stu-id="9e140-118">Turn on preview features</span></span>

<span data-ttu-id="9e140-119">Sie haben Zugriff auf anstehende Features, zu der Sie Feedback geben können, um die Allgemeine Erfahrung zu verbessern, bevor Features allgemein verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9e140-119">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="9e140-120">Aktivieren Sie die Einstellung für die Vorschauerfahrung, um zu den ersten zu gehören, die kommende Features ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="9e140-120">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="9e140-121">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Erweiterte Features**  >  **Vorschaufeatures aus.**</span><span class="sxs-lookup"><span data-stu-id="9e140-121">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="9e140-122">Umschalten Sie die Einstellung zwischen **Ein** und **Aus,** und wählen **Sie Einstellungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="9e140-122">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="9e140-123">Vorschaufeatures</span><span class="sxs-lookup"><span data-stu-id="9e140-123">Preview features</span></span>

<span data-ttu-id="9e140-124">In der Vorschauversion sind die folgenden Features enthalten:</span><span class="sxs-lookup"><span data-stu-id="9e140-124">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="9e140-125">Webinhaltsfilterung</span><span class="sxs-lookup"><span data-stu-id="9e140-125">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="9e140-126">Die Webinhaltsfilterung ist Teil der Webschutzfunktionen in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9e140-126">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9e140-127">Sie ermöglicht Es Ihrer Organisation, den Zugriff auf Websites basierend auf ihren Inhaltskategorien nachverfolgt und zu regeln.</span><span class="sxs-lookup"><span data-stu-id="9e140-127">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="9e140-128">Viele dieser Websites sind zwar nicht bösartig, können jedoch aufgrund von Compliancebestimmungen, Bandbreitennutzung oder anderen Bedenken problematisch sein.</span><span class="sxs-lookup"><span data-stu-id="9e140-128">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="9e140-129">Bericht über Geräteintegität und -kompatibilität</span><span class="sxs-lookup"><span data-stu-id="9e140-129">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="9e140-130">Der Bericht über geräteintehitäts- und compliance enthält informationen auf hoher Ebene zu den Geräten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9e140-130">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

- [<span data-ttu-id="9e140-131">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="9e140-131">Information protection</span></span>](information-protection-in-windows-overview.md)<BR>
<span data-ttu-id="9e140-132">Der Informationsschutz ist ein integraler Bestandteil der Microsoft 365 Enterprise-Suite und bietet intelligenten Schutz, um vertrauliche Daten zu schützen und gleichzeitig die Produktivität am Arbeitsplatz zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9e140-132">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span> <span data-ttu-id="9e140-133">Microsoft Defender for Endpoint ist nahtlos in Microsoft Threat Protection integriert, um eine vollständige und umfassende Lösung zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) für Windows-Geräte zu bieten.</span><span class="sxs-lookup"><span data-stu-id="9e140-133">Microsoft Defender for Endpoint is seamlessly integrated in Microsoft Threat Protection to provide a complete and comprehensive data loss prevention (DLP) solution for Windows devices.</span></span>

    >[!NOTE]
    ><span data-ttu-id="9e140-134">Teilweise verfügbar unter Windows 10, Version 1809.</span><span class="sxs-lookup"><span data-stu-id="9e140-134">Partially available from Windows 10, version 1809.</span></span>

- [<span data-ttu-id="9e140-135">Onboarding von Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="9e140-135">Onboard Windows Server 2019</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-version-1803-and-windows-server-2019) <BR> <span data-ttu-id="9e140-136">Microsoft Defender for Endpoint bietet jetzt Unterstützung für Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9e140-136">Microsoft Defender for Endpoint now adds support for Windows Server 2019.</span></span> <span data-ttu-id="9e140-137">Sie können Windows Server 2019 mit derselben Methode integrieren, die für Windows 10-Clientgeräte verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9e140-137">You'll be able to onboard Windows Server 2019 in the same method available for Windows 10 client devices.</span></span>


> [!TIP] 
> <span data-ttu-id="9e140-138">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9e140-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9e140-139">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9e140-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
