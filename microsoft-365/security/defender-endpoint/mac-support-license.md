---
title: Behandeln von Lizenzproblemen für Microsoft Defender for Endpoint auf dem Mac
description: Behandeln von Lizenzproblemen in Microsoft Defender for Endpoint auf Dem Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, performance
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
ms.openlocfilehash: 1f8428c2995eec2dece290049eda67a3683b4c1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244980"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="22eb8-104">Behandeln von Lizenzproblemen für Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="22eb8-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="22eb8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="22eb8-105">**Applies to:**</span></span>

- [<span data-ttu-id="22eb8-106">Microsoft Defender für Endpunkt unter Mac OS</span><span class="sxs-lookup"><span data-stu-id="22eb8-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="22eb8-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="22eb8-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22eb8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22eb8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="22eb8-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="22eb8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="22eb8-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="22eb8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="22eb8-111">Während Sie Microsoft Defender for Endpoint auf [macOS](microsoft-defender-endpoint-mac.md) und [manuellen](mac-install-manually.md) Bereitstellungstests oder einem Proof Of Concept (PoC) durch führen, wird möglicherweise der folgende Fehler angezeigt:</span><span class="sxs-lookup"><span data-stu-id="22eb8-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Abbildung des Lizenzfehlers](images/no-license-found.png)

<span data-ttu-id="22eb8-113&quot;>**Nachricht:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22eb8-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;22eb8-114&quot;>Keine Lizenz gefunden</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22eb8-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;22eb8-115&quot;>Es sieht so aus, als verfügt Ihre Organisation nicht über eine Lizenz für Microsoft 365 Enterprise Abonnement.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22eb8-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;22eb8-116&quot;>Weitere Informationen erhalten Sie von Ihrem Administrator.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22eb8-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;22eb8-117&quot;>**Ursache:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22eb8-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;22eb8-118&quot;>Sie haben das Microsoft Defender for Endpoint für macOS-Paket (&quot;Installationspaket herunterladen") bereitgestellt und/oder installiert, aber Möglicherweise haben Sie das Konfigurationsskript ("Onboardingpaket herunterladen") ausgeführt, oder Sie haben dem Benutzer keine Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="22eb8-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package"), but you might have run the configuration script ("Download onboarding package"), or you have not assigned a license to the user.</span></span>

<span data-ttu-id="22eb8-119">**Lösung:**</span><span class="sxs-lookup"><span data-stu-id="22eb8-119">**Solution:**</span></span>

<span data-ttu-id="22eb8-120">Befolgen Sie die MicrosoftDefenderATPOnboardingMacOs.py, die hier dokumentiert sind: [Clientkonfiguration](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="22eb8-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>
