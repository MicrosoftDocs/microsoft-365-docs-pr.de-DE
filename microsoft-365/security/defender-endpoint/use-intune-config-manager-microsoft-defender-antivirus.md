---
title: Konfigurieren Microsoft Defender Antivirus mithilfe Microsoft Endpoint Manager
description: Verwenden Microsoft Endpoint Manager und Microsoft Intune zum Konfigurieren von Microsoft Defender AV und Endpoint Protection
keywords: scep, intune, endpoint protection, configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683751"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="7f5ae-104">Verwenden Microsoft Endpoint Manager zum Konfigurieren und Verwalten von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="7f5ae-104">Use Microsoft Endpoint Manager to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7f5ae-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7f5ae-105">**Applies to:**</span></span>

- [<span data-ttu-id="7f5ae-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7f5ae-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7f5ae-107">Sie können die [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) zum Konfigurieren von Microsoft Defender Antivirus verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f5ae-107">You can use [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to configure Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="7f5ae-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) und [Configuration Manager](/mem/configmgr/core/understand/introduction) sind jetzt Teil Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="7f5ae-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Configuration Manager](/mem/configmgr/core/understand/introduction) are now part of Endpoint Manager.</span></span>  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a><span data-ttu-id="7f5ae-109">Konfigurieren Microsoft Defender Antivirus Scans in Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="7f5ae-109">Configure Microsoft Defender Antivirus scans in Endpoint Manager</span></span>

1. <span data-ttu-id="7f5ae-110">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="7f5ae-110">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), and sign in.</span></span>

2. <span data-ttu-id="7f5ae-111">Navigieren Sie zu **Endpunktsicherheit**.</span><span class="sxs-lookup"><span data-stu-id="7f5ae-111">Navigate to **Endpoint Security**.</span></span>

3. <span data-ttu-id="7f5ae-112">Wählen **Sie unter Verwalten** die Option Antivirus **aus.**</span><span class="sxs-lookup"><span data-stu-id="7f5ae-112">Under **Manage**, choose **Antivirus**.</span></span>

4. <span data-ttu-id="7f5ae-113">Wählen Sie ihre Microsoft Defender Antivirus aus.</span><span class="sxs-lookup"><span data-stu-id="7f5ae-113">Select your Microsoft Defender Antivirus policy.</span></span> 

5. <span data-ttu-id="7f5ae-114">Wählen Sie unter **Verwalten** die Option **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="7f5ae-114">Under **Manage**, choose **Properties**.</span></span>

6. <span data-ttu-id="7f5ae-115">Wählen Sie direkt neben **Konfigurationseinstellungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="7f5ae-115">Next to **Configuration settings**, choose **Edit**.</span></span>

7. <span data-ttu-id="7f5ae-116">Erweitern Sie den **Abschnitt Scan,** und überprüfen oder bearbeiten Sie Die Scaneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="7f5ae-116">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

8. <span data-ttu-id="7f5ae-117">Wählen Sie **Überprüfen + Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="7f5ae-117">Choose **Review + save**</span></span>


> [!TIP]
> <span data-ttu-id="7f5ae-118">Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="7f5ae-118">Need help?</span></span> <span data-ttu-id="7f5ae-119">Weitere [Informationen finden Sie unter Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span><span class="sxs-lookup"><span data-stu-id="7f5ae-119">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="7f5ae-120">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="7f5ae-120">Related articles</span></span>

- [<span data-ttu-id="7f5ae-121">Referenzartikel für Verwaltungs- und Konfigurationstools</span><span class="sxs-lookup"><span data-stu-id="7f5ae-121">Reference articles for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7f5ae-122">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="7f5ae-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)