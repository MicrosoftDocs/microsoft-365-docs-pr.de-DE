---
title: Konfigurieren der Integration von Microsoft Cloud App Security
ms.reviewer: ''
description: Erfahren Sie, wie Sie die Einstellungen aktivieren, um die Integration von Microsoft Defender for Endpoint in Microsoft Cloud App Security zu aktivieren.
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
ms.openlocfilehash: ddf32b26191826ab6ecbad6b9d047ac7bbb6276a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068535"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="d53f8-104">Konfigurieren von Microsoft Cloud App Security in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d53f8-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d53f8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d53f8-105">**Applies to:**</span></span>
- [<span data-ttu-id="d53f8-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d53f8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="d53f8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d53f8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d53f8-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d53f8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d53f8-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d53f8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="d53f8-110">Um von Microsoft Defender for Endpoint Cloud App Discovery-Signalen zu profitieren, aktivieren Sie die Microsoft Cloud App Security-Integration.</span><span class="sxs-lookup"><span data-stu-id="d53f8-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="d53f8-111">Dieses Feature ist mit einer E5-Lizenz für [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) auf Geräten mit Windows 10, Version 1709 (Os Build 16299.1085 mit [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, verfügbar. Version 1803 (Betriebssystem build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, Version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) oder höher Windows 10-Versionen.</span><span class="sxs-lookup"><span data-stu-id="d53f8-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="d53f8-112">Ausführliche Informationen zur Integration von Microsoft Defender for Endpoint [in Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) finden Sie unter Microsoft Defender for Endpoint in Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="d53f8-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="d53f8-113">Aktivieren von Microsoft Cloud App Security in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d53f8-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="d53f8-114">Wählen Sie im Navigationsbereich Einstellungen **einrichten Erweiterte**  >  **Features aus.**</span><span class="sxs-lookup"><span data-stu-id="d53f8-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="d53f8-115">Wählen **Sie Microsoft Cloud App Security aus,** und wechseln Sie zu **Ein**.</span><span class="sxs-lookup"><span data-stu-id="d53f8-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="d53f8-116">Klicken **Sie auf Einstellungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="d53f8-116">Click **Save preferences**.</span></span>

<span data-ttu-id="d53f8-117">Nach der Aktivierung beginnt Microsoft Defender for Endpoint sofort mit der Weiterleitung von Erkennungssignalen an Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="d53f8-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="d53f8-118">Anzeigen der erfassten Daten</span><span class="sxs-lookup"><span data-stu-id="d53f8-118">View the data collected</span></span>

<span data-ttu-id="d53f8-119">Informationen zum Anzeigen und Zugreifen auf Microsoft Defender for Endpoint-Daten in Microsoft Cloud Apps Security finden Sie unter Untersuchen von Geräten [in Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="d53f8-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="d53f8-120">Weitere Informationen zur Clouderkennung finden Sie unter [Arbeiten mit ermittelten Apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="d53f8-120">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="d53f8-121">Wenn Sie Microsoft Cloud App Security ausprobieren möchten, lesen Sie [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span><span class="sxs-lookup"><span data-stu-id="d53f8-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="d53f8-122">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="d53f8-122">Related topic</span></span>
- [<span data-ttu-id="d53f8-123">Integration von Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d53f8-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
