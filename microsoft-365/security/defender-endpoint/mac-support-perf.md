---
title: Behandeln von Leistungsproblemen für Microsoft Defender for Endpoint für Mac
description: Behandeln von Leistungsproblemen in Microsoft Defender for Endpoint für Mac.
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
ms.openlocfilehash: 87190d9e0bb62d42642374bd7c9f6f3acad3c80a
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379386"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="6573f-104">Behandeln von Leistungsproblemen für Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="6573f-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6573f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6573f-105">**Applies to:**</span></span>

- [<span data-ttu-id="6573f-106">Microsoft Defender für Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="6573f-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="6573f-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6573f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6573f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6573f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6573f-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="6573f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6573f-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6573f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6573f-111">Dieses Thema enthält einige allgemeine Schritte, mit deren Unterstützung Leistungsprobleme im Zusammenhang mit Microsoft Defender for Endpoint für Mac eindr werden können.</span><span class="sxs-lookup"><span data-stu-id="6573f-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="6573f-112">Der Echtzeitschutz (Real-Time Protection, RTP) ist ein Feature von Microsoft Defender for Endpoint für Mac, das Ihr Gerät kontinuierlich überwacht und vor Bedrohungen schützt.</span><span class="sxs-lookup"><span data-stu-id="6573f-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="6573f-113">Es besteht aus Datei- und Prozessüberwachung und anderen Heuristiken.</span><span class="sxs-lookup"><span data-stu-id="6573f-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="6573f-114">Abhängig von den ausgeführten Anwendungen und den Gerätemerkmalen kann es bei der Ausführung von Microsoft Defender for Endpoint für Mac zu einer suboptimalen Leistung führen.</span><span class="sxs-lookup"><span data-stu-id="6573f-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="6573f-115">Insbesondere Anwendungen oder Systemprozesse, die über einen kurzen Zeitraum auf viele Ressourcen zugreifen, können zu Leistungsproblemen in Microsoft Defender for Endpoint für Mac führen.</span><span class="sxs-lookup"><span data-stu-id="6573f-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="6573f-116">Die folgenden Schritte können verwendet werden, um diese Probleme zu beheben und zu beheben:</span><span class="sxs-lookup"><span data-stu-id="6573f-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="6573f-117">Deaktivieren Sie den Echtzeitschutz mithilfe einer der folgenden Methoden, und beobachten Sie, ob sich die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="6573f-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="6573f-118">Dieser Ansatz hilft, die Leistungsprobleme von Microsoft Defender for Endpoint für Mac zu verengt.</span><span class="sxs-lookup"><span data-stu-id="6573f-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

    <span data-ttu-id="6573f-119">Wenn Ihr Gerät nicht von Ihrer Organisation verwaltet wird, kann der Echtzeitschutz mithilfe einer der folgenden Optionen deaktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="6573f-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="6573f-120">Über die Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="6573f-120">From the user interface.</span></span> <span data-ttu-id="6573f-121">Öffnen Sie Microsoft Defender for Endpoint für Mac, und navigieren Sie zu **Einstellungen verwalten.**</span><span class="sxs-lookup"><span data-stu-id="6573f-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![Verwalten des Screenshots für den Echtzeitschutz](images/mdatp-36-rtp.png)

    - <span data-ttu-id="6573f-123">Vom Terminal aus.</span><span class="sxs-lookup"><span data-stu-id="6573f-123">From the Terminal.</span></span> <span data-ttu-id="6573f-124">Aus Sicherheitsgründen erfordert dieser Vorgang eine Erhöhung.</span><span class="sxs-lookup"><span data-stu-id="6573f-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    <span data-ttu-id="6573f-125">Wenn Ihr Gerät von Ihrer Organisation verwaltet wird, kann der Echtzeitschutz von Ihrem Administrator mithilfe der Anweisungen unter Festlegen von Einstellungen für [Microsoft Defender for Endpoint für Mac deaktiviert werden.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="6573f-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

2. <span data-ttu-id="6573f-126">Öffnen Sie finder, und navigieren Sie zu   >  **Anwendungsprogramme**.</span><span class="sxs-lookup"><span data-stu-id="6573f-126">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="6573f-127">Öffnen **Sie Aktivitätsüberwachung,** und analysieren Sie, welche Anwendungen die Ressourcen auf Ihrem System verwenden.</span><span class="sxs-lookup"><span data-stu-id="6573f-127">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="6573f-128">Typische Beispiele sind Softwareupdater und Compiler.</span><span class="sxs-lookup"><span data-stu-id="6573f-128">Typical examples include software updaters and compilers.</span></span>

3. <span data-ttu-id="6573f-129">Konfigurieren Sie Microsoft Defender für Endpoint für Mac mit Ausschlüssen für die Prozesse oder Datenträgerspeicherorte, die zu Leistungsproblemen beitragen, und aktivieren Sie den Echtzeitschutz erneut.</span><span class="sxs-lookup"><span data-stu-id="6573f-129">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="6573f-130">Weitere Informationen finden Sie unter Configure [and validate exclusions for Microsoft Defender for Endpoint for Mac.](mac-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="6573f-130">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
