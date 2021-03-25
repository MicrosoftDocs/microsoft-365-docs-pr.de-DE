---
title: Behandeln von Lizenzproblemen für Microsoft Defender ATP für Mac
description: Behandeln von Lizenzproblemen in Microsoft Defender ATP für Mac.
keywords: microsoft, defender, atp, mac, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 645c3657bdd1540ac95b68460b4dff6d25627c2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185926"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="57c7b-104">Behandeln von Lizenzproblemen für Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="57c7b-104">Troubleshoot license issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="57c7b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="57c7b-105">**Applies to:**</span></span>

- [<span data-ttu-id="57c7b-106">Microsoft Defender für Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="57c7b-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="57c7b-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="57c7b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="57c7b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57c7b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="57c7b-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="57c7b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="57c7b-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="57c7b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="57c7b-111">Während Sie Microsoft Defender for Endpoint [](mac-install-manually.md) für [Mac](microsoft-defender-endpoint-mac.md) und manuelle Bereitstellungstests oder einen Proof Of Concept (PoC) durchführen, wird möglicherweise der folgende Fehler angezeigt:</span><span class="sxs-lookup"><span data-stu-id="57c7b-111">While you are going through [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Abbildung des Lizenzfehlers](images/no-license-found.png)

<span data-ttu-id="57c7b-113">**Nachricht:**</span><span class="sxs-lookup"><span data-stu-id="57c7b-113">**Message:**</span></span> 

<span data-ttu-id="57c7b-114">Keine Lizenz gefunden</span><span class="sxs-lookup"><span data-stu-id="57c7b-114">No license found</span></span>

<span data-ttu-id="57c7b-115">Es sieht so aus, als verfügt Ihre Organisation nicht über eine Lizenz für Microsoft 365 Enterprise-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="57c7b-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="57c7b-116">Weitere Informationen erhalten Sie von Ihrem Administrator.</span><span class="sxs-lookup"><span data-stu-id="57c7b-116">Contact your administrator for help.</span></span>

<span data-ttu-id="57c7b-117">**Ursache:**</span><span class="sxs-lookup"><span data-stu-id="57c7b-117">**Cause:**</span></span> 

<span data-ttu-id="57c7b-118">Sie haben das Microsoft Defender for Endpoint für macOS-Paket ("Installationspaket herunterladen") bereitgestellt und/oder installiert, aber möglicherweise haben Sie das Konfigurationsskript ("Onboardingpaket herunterladen") ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="57c7b-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="57c7b-119">**Lösung:**</span><span class="sxs-lookup"><span data-stu-id="57c7b-119">**Solution:**</span></span>

<span data-ttu-id="57c7b-120">Befolgen Sie die MicrosoftDefenderATPOnboardingMacOs.py, die hier dokumentiert sind: [Clientkonfiguration](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="57c7b-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

