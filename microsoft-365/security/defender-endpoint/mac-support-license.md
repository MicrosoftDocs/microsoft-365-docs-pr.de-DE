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
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689113"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="09c66-104">Behandeln von Lizenzproblemen für Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="09c66-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="09c66-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="09c66-105">**Applies to:**</span></span>

- [<span data-ttu-id="09c66-106">Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="09c66-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="09c66-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="09c66-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="09c66-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09c66-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="09c66-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="09c66-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="09c66-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="09c66-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="09c66-111">Während Sie Microsoft Defender for Endpoint auf [macOS](microsoft-defender-endpoint-mac.md) und [manuellen](mac-install-manually.md) Bereitstellungstests oder einem Proof Of Concept (PoC) durch führen, wird möglicherweise der folgende Fehler angezeigt:</span><span class="sxs-lookup"><span data-stu-id="09c66-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Abbildung des Lizenzfehlers](images/no-license-found.png)

<span data-ttu-id="09c66-113&quot;>**Nachricht:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;09c66-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;09c66-114&quot;>Keine Lizenz gefunden</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;09c66-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;09c66-115&quot;>Es sieht so aus, als verfügt Ihre Organisation nicht über eine Lizenz für Microsoft 365 Enterprise-Abonnements.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;09c66-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;09c66-116&quot;>Weitere Informationen erhalten Sie von Ihrem Administrator.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;09c66-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;09c66-117&quot;>**Ursache:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;09c66-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;09c66-118&quot;>Sie haben das Microsoft Defender for Endpoint auf macOS-Paket bereitgestellt und/oder installiert (&quot;Installationspaket herunterladen"), aber möglicherweise haben Sie das Konfigurationsskript ("Onboardingpaket herunterladen") ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="09c66-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="09c66-119">**Lösung:**</span><span class="sxs-lookup"><span data-stu-id="09c66-119">**Solution:**</span></span>

<span data-ttu-id="09c66-120">Befolgen Sie die MicrosoftDefenderATPOnboardingMacOs.py, die hier dokumentiert sind: [Clientkonfiguration](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="09c66-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

