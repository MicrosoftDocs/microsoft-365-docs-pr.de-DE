---
title: Testen Sie Microsoft Defender for Identity, richten Sie Konfigurationsbenchmarks, Standards, Richtlinien und Lernprogramme zum Erkennen und Beheben verschiedener Identitätsbedrohungen wie Reconnaissance, kompromittierte Anmeldeinformationen, laterale Bewegung, Domänendominanz und Exfiltrationswarnungen ein, führen Sie eine Untersuchung von Benutzer-, Computer-, Entitäts- und lateralen Bewegungspfaden durch.
description: Testen Sie Microsoft Defender for Identity, legen Sie Benchmarks fest, nehmen Sie Lernprogramme zu Reconnaissance, kompromittierten Anmeldeinformationen, lateraler Bewegung, Domänendominanz und Exfiltrationswarnungen vor.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458056"
---
# <a name="pilot-microsoft-defender-for-identity"></a><span data-ttu-id="d5124-103">Pilot-Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="d5124-103">Pilot Microsoft Defender for Identity</span></span>


<span data-ttu-id="d5124-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d5124-104">**Applies to:**</span></span>
- <span data-ttu-id="d5124-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5124-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="d5124-106">Dieser Artikel ist [Schritt 3 von 3](eval-defender-identity-overview.md) beim Einrichten der Evaluierungsumgebung für Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="d5124-106">This article is [Step 3 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="d5124-107">Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d5124-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="d5124-108">Führen Sie die folgenden Schritte aus, um das Pilotprojekt für Microsoft Defender for Identity einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d5124-108">Use the following steps to setup and configure the pilot for Microsoft Defender for identity.</span></span> <span data-ttu-id="d5124-109">Beachten Sie, dass die Empfehlungen nicht das Einrichten einer Pilotgruppe umfassen.</span><span class="sxs-lookup"><span data-stu-id="d5124-109">Note that the recommendations don't include setting up a pilot group.</span></span> <span data-ttu-id="d5124-110">Die bewährte Methode besteht darin, den Sensor auf allen Servern zu installieren, auf denen Active Directory Domain Services (AD DS) und Active Directory-Verbunddienste (AD FS) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d5124-110">The best practice is to go ahead and install the sensor on all of your servers running Active Directory Domain Services (AD DS) and Active Directory Federated Services (AD FS).</span></span>

![Schritte zum Hinzufügen von Microsoft Defender for Identity zur Defender-Evaluierungsumgebung](../../media/defender/m365-defender-identity-pilot-steps.png)

<span data-ttu-id="d5124-112">In der folgenden Tabelle werden die Schritte in der Abbildung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d5124-112">The following table describes the steps in the illustration.</span></span>

- [<span data-ttu-id="d5124-113">Schritt 1: Konfigurieren von Benchmarkempfehlungen für Ihre Identitätsumgebung</span><span class="sxs-lookup"><span data-stu-id="d5124-113">Step 1: Configure benchmark recommendations for your identity environment</span></span>](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [<span data-ttu-id="d5124-114">Schritt 2: Testen von Funktionen – Exemplarische Anleitungen zum Identifizieren und Beheben verschiedener Angriffstypen </span><span class="sxs-lookup"><span data-stu-id="d5124-114">Step 2: Try out capabilities — Walk through tutorials for identifying and remediating different attack types </span></span>](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a><span data-ttu-id="d5124-115">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="d5124-115">Step 1.</span></span> <span data-ttu-id="d5124-116">Konfigurieren von Benchmarkempfehlungen für Ihre Identitätsumgebung</span><span class="sxs-lookup"><span data-stu-id="d5124-116">Configure benchmark recommendations for your identity environment</span></span>

<span data-ttu-id="d5124-117">Microsoft bietet Empfehlungen für Sicherheits-Benchmark für Kunden, die Microsoft Cloud Services verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5124-117">Microsoft provides security benchmark recommendations for customers using Microsoft Cloud services.</span></span> <span data-ttu-id="d5124-118">Der [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) bietet vordefinierte bewährte Methoden und Empfehlungen, um die Sicherheit von Workloads, Daten und Diensten in Azure zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d5124-118">The [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) provides prescriptive best practices and recommendations to help improve the security of workloads, data, and services on Azure.</span></span>

<span data-ttu-id="d5124-119">Diese Benchmarkempfehlungen umfassen [Azure-Sicherheitsgrundwerte für Microsoft Defender for Identity.](/security/benchmark/azure/baselines/defender-for-identity-security-baseline)</span><span class="sxs-lookup"><span data-stu-id="d5124-119">These benchmark recommendations include [Azure security baseline for Microsoft Defender for Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline).</span></span> <span data-ttu-id="d5124-120">Die Implementierung dieser Empfehlungen kann einige Zeit in Anspruch nehmen, um sie zu planen und zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="d5124-120">Implementing these recommendations can take some time to plan and implement.</span></span> <span data-ttu-id="d5124-121">Obwohl diese die Sicherheit Ihrer Identitätsumgebung erheblich erhöhen, sollten sie Sie nicht daran hindern, Microsoft Defender for Identity weiter auszuwerten und zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="d5124-121">While these will greatly increase the security of your identity environment, they shouldn't prevent you from continuing to evaluate and implement Microsoft Defender for Identity.</span></span> <span data-ttu-id="d5124-122">Diese werden hier für Ihr Bewusstsein bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d5124-122">These are provided here for your awareness.</span></span>

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a><span data-ttu-id="d5124-123">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="d5124-123">Step 2.</span></span> <span data-ttu-id="d5124-124">Testen von Funktionen – Exemplarische Lernprogramme zum Identifizieren und Beheben verschiedener Angriffstypen</span><span class="sxs-lookup"><span data-stu-id="d5124-124">Try out capabilities — Walk through tutorials for identifying and remediating different attack types</span></span>

<span data-ttu-id="d5124-125">Die Microsoft Defender for Identity-Dokumentation enthält eine Reihe von Lernprogrammen, die den Prozess der Identifizierung und Behebung verschiedener Angriffstypen durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="d5124-125">The Microsoft Defender for Identity documentation includes a series of tutorials that walk through the process of identifying and remediating various attack types.</span></span>

<span data-ttu-id="d5124-126">Testen Sie Defender for Identity-Lernprogramme:</span><span class="sxs-lookup"><span data-stu-id="d5124-126">Try out Defender for Identity tutorials:</span></span>
- [<span data-ttu-id="d5124-127">Reconnaissance-Warnungen</span><span class="sxs-lookup"><span data-stu-id="d5124-127">Reconnaissance alerts</span></span>](/defender-for-identity/reconnaissance-alerts)
- [<span data-ttu-id="d5124-128">Warnungen bei kompromittierten Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="d5124-128">Compromised credential alerts</span></span>](/defender-for-identity/compromised-credentials-alerts)
- [<span data-ttu-id="d5124-129">Warnungen bei lateralen Bewegungen</span><span class="sxs-lookup"><span data-stu-id="d5124-129">Lateral movement alerts</span></span>](/defender-for-identity/lateral-movement-alerts)
- [<span data-ttu-id="d5124-130">Domänendominanzwarnungen</span><span class="sxs-lookup"><span data-stu-id="d5124-130">Domain dominance alerts</span></span>](/defender-for-identity/domain-dominance-alerts)
- [<span data-ttu-id="d5124-131">Exfiltrationswarnungen</span><span class="sxs-lookup"><span data-stu-id="d5124-131">Exfiltration alerts</span></span>](/defender-for-identity/exfiltration-alerts)
- [<span data-ttu-id="d5124-132">Untersuchen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="d5124-132">Investigate a user</span></span>](/defender-for-identity/investigate-a-user)
- [<span data-ttu-id="d5124-133">Untersuchen eines Computers</span><span class="sxs-lookup"><span data-stu-id="d5124-133">Investigate a computer</span></span>](/defender-for-identity/investigate-a-computer)
- [<span data-ttu-id="d5124-134">Untersuchen lateraler Bewegungspfade</span><span class="sxs-lookup"><span data-stu-id="d5124-134">Investigate lateral movement paths</span></span>](/defender-for-identity/investigate-lateral-movement-path)
- [<span data-ttu-id="d5124-135">Untersuchen von Entitäten</span><span class="sxs-lookup"><span data-stu-id="d5124-135">Investigate entities</span></span>](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a><span data-ttu-id="d5124-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d5124-136">Next steps</span></span>

[<span data-ttu-id="d5124-137">Auswerten von Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="d5124-137">Evaluate Microsoft Defender for Office 365</span></span>](eval-defender-office-365-overview.md)

<span data-ttu-id="d5124-138">Kehren Sie zur Übersicht für ["Auswerten von Microsoft Defender für Office 365"](eval-defender-office-365-overview.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="d5124-138">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="d5124-139">Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d5124-139">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>