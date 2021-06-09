---
title: Konfigurieren der Integration von Microsoft Cloud App Security
ms.reviewer: ''
description: Erfahren Sie, wie Sie die Einstellungen aktivieren, um die Integration von Microsoft Defender für Endpunkt in Microsoft Cloud App Security zu aktivieren.
keywords: Cloud, App, Sicherheit, Einstellungen, Integration, Ermittlung, Bericht
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
ms.openlocfilehash: 4f7aca5cb532510d55042c70d04d65f2aa08baa3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844754"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="781b6-104">Konfigurieren Microsoft Cloud App Security in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="781b6-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="781b6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="781b6-105">**Applies to:**</span></span>
- [<span data-ttu-id="781b6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="781b6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="781b6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="781b6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="781b6-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="781b6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="781b6-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="781b6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="781b6-110">Um von Microsoft Defender für Endpunkt Cloud App Discovery-Signalen zu profitieren, aktivieren Sie Microsoft Cloud App Security Integration.</span><span class="sxs-lookup"><span data-stu-id="781b6-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="781b6-111">Dieses Feature ist mit einer E5-Lizenz für [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) auf Geräten verfügbar, auf denen Windows 10 ausgeführt wird. Version 1709 (BS Build 16299.1085 mit [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, Version 1803 (Os Build 17134.704 mit [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, Version 1809 (Os Build 17763.379 mit [KB4489899)](https://support.microsoft.com/help/4489899)oder höher Windows 10 Versionen.</span><span class="sxs-lookup"><span data-stu-id="781b6-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="781b6-112">Informationen zur detaillierten Integration von Microsoft Defender für Endpunkt mit Microsoft Cloud App Security finden Sie unter Microsoft Defender für [Endpunktintegration mit](/cloud-app-security/mde-integration) Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="781b6-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="781b6-113">Aktivieren Microsoft Cloud App Security in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="781b6-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="781b6-114">Wählen Sie im Navigationsbereich **"Einstellungen einrichten**  >  **Erweiterte Features"** aus.</span><span class="sxs-lookup"><span data-stu-id="781b6-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="781b6-115">Wählen Sie **Microsoft Cloud App Security** aus, und schalten Sie die Umschaltfläche auf **"Ein".**</span><span class="sxs-lookup"><span data-stu-id="781b6-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="781b6-116">Klicken Sie auf **"Einstellungen speichern".**</span><span class="sxs-lookup"><span data-stu-id="781b6-116">Click **Save preferences**.</span></span>

<span data-ttu-id="781b6-117">Nach der Aktivierung beginnt Microsoft Defender für Endpunkt sofort mit der Weiterleitung von Erkennungssignalen an Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="781b6-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="781b6-118">Anzeigen der gesammelten Daten</span><span class="sxs-lookup"><span data-stu-id="781b6-118">View the data collected</span></span>

<span data-ttu-id="781b6-119">Informationen zum Anzeigen und Zugreifen auf Microsoft Defender für Endpunktdaten in Microsoft Cloud Apps Security finden Sie unter [Untersuchen von Geräten in Cloud App Security.](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="781b6-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="781b6-120">Weitere Informationen zur Cloudermittlung finden Sie unter [Arbeiten mit ermittelten Apps.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="781b6-120">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="781b6-121">Wenn Sie Microsoft Cloud App Security ausprobieren möchten, lesen Sie [Microsoft Cloud App Security Testversion.](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)</span><span class="sxs-lookup"><span data-stu-id="781b6-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="781b6-122">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="781b6-122">Related topic</span></span>
- [<span data-ttu-id="781b6-123">Microsoft Cloud App Security Integration</span><span class="sxs-lookup"><span data-stu-id="781b6-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
