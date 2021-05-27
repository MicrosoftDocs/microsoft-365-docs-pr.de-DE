---
title: Planen von Software- und Softwareversionen zum Ende der Unterstützung
description: Ermitteln und planen Sie Software- und Softwareversionen, die nicht mehr unterstützt werden und keine Sicherheitsupdates erhalten.
keywords: Bedrohungs- und Sicherheitsrisikomanagement, Microsoft Defender for Endpoint tvm-Sicherheitsempfehlung, Cybersicherheitsempfehlung, Empfehlung zur Sicherheit mit Aktionen
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
ms.openlocfilehash: 1800cfdabd402321c49b737eff7f9d67639eb300
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689001"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="bbc55-104">Planen von Software- und Softwareversionen am Ende der Unterstützung mit Bedrohungs- und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="bbc55-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bbc55-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bbc55-105">**Applies to:**</span></span>

- [<span data-ttu-id="bbc55-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bbc55-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bbc55-107">Bedrohung und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="bbc55-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="bbc55-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbc55-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bbc55-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="bbc55-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bbc55-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bbc55-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="bbc55-111">End-of-Support (EOS), auch als End-of-Life (EOL) bezeichnet, bedeutet für Software- oder Softwareversionen, dass sie nicht mehr unterstützt oder in Betrieb sind und keine Sicherheitsupdates erhalten.</span><span class="sxs-lookup"><span data-stu-id="bbc55-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="bbc55-112">Wenn Sie Software- oder Softwareversionen mit beendeter Unterstützung verwenden, setzen Sie Ihre Organisation Sicherheitsrisiken, rechtlichen und finanziellen Risiken aus.</span><span class="sxs-lookup"><span data-stu-id="bbc55-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="bbc55-113">Es ist wichtig, dass Sicherheits- und IT-Administratoren zusammenarbeiten und sicherstellen, dass das Softwareinventar der Organisation für optimale Ergebnisse, Compliance und ein gesundes Netzwerkökosystem konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="bbc55-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="bbc55-114">Sie sollten die Optionen zum Entfernen oder Ersetzen von Apps untersuchen, die das Ende der Support- und Updateversionen erreicht haben, die nicht mehr unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="bbc55-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="bbc55-115">Es ist am besten, einen  Plan vor dem Ende der Supporttermine zu erstellen und zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="bbc55-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

>[!NOTE]
> <span data-ttu-id="bbc55-116">Die End-of-Support-Funktion ist derzeit nur für Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bbc55-116">End-of-support capability is currently available only for Windows products.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="bbc55-117">Suchen nach Software- oder Softwareversionen, die nicht mehr unterstützt werden</span><span class="sxs-lookup"><span data-stu-id="bbc55-117">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="bbc55-118">Navigieren Sie Bedrohungs- und Sicherheitsrisikomanagement Menü zu [**Sicherheitsempfehlungen**](tvm-security-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="bbc55-118">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="bbc55-119">Wechseln Sie zum **Bereich Filter,** und suchen Sie nach dem Abschnitt Tags.</span><span class="sxs-lookup"><span data-stu-id="bbc55-119">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="bbc55-120">Wählen Sie eine oder mehrere der EOS-Tagoptionen aus.</span><span class="sxs-lookup"><span data-stu-id="bbc55-120">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="bbc55-121">Wenden Sie **dann an**.</span><span class="sxs-lookup"><span data-stu-id="bbc55-121">Then **Apply**.</span></span>

    ![Screenshottags, die EOS-Software, EOS-Versionen und bevorstehende EOS-Versionen enthalten.](images/tvm-eos-tag.png)

3. <span data-ttu-id="bbc55-123">Sie sehen eine Liste der Empfehlungen im Zusammenhang mit Software mit beendeter Unterstützung, Softwareversionen, die ende des Support sind, oder Versionen mit bevorstehendem Ende des Support.</span><span class="sxs-lookup"><span data-stu-id="bbc55-123">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="bbc55-124">Diese Tags sind auch auf der Seite [softwareinventar](tvm-software-inventory.md) sichtbar.</span><span class="sxs-lookup"><span data-stu-id="bbc55-124">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![Empfehlungen mit DEM EOS-Tag.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="bbc55-126">Liste der Versionen und Datumsangaben</span><span class="sxs-lookup"><span data-stu-id="bbc55-126">List of versions and dates</span></span>

<span data-ttu-id="bbc55-127">Führen Sie die folgenden Schritte aus, um eine Liste der Versionen anzeigen zu können, die das Ende des Supportendes erreicht haben oder bald enden oder den Support bald beenden und diese Datumsangaben enthalten:</span><span class="sxs-lookup"><span data-stu-id="bbc55-127">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="bbc55-128">Eine Meldung wird im Flyout für Sicherheitsempfehlungen für Software mit Versionen angezeigt, die das Ende der Unterstützung erreicht haben oder bald das Ende des Support erreichen.</span><span class="sxs-lookup"><span data-stu-id="bbc55-128">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![Screenshot des Links zur Versionsverteilung.](images/eos-upcoming-eos.png)

2. <span data-ttu-id="bbc55-130">Wählen Sie **den Link zur** Versionsverteilung aus, um zur Software-Drilldownseite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="bbc55-130">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="bbc55-131">Dort sehen Sie eine gefilterte Liste von Versionen mit Tags, die sie als Ende des Support oder bevorstehendes Ende des Support identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bbc55-131">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![Screenshot der Software-Drilldownseite mit Ende der Supportsoftware.](images/software-drilldown-eos.png)

3. <span data-ttu-id="bbc55-133">Wählen Sie eine der Versionen in der zu öffnende Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="bbc55-133">Select one of the versions in the table to open.</span></span> <span data-ttu-id="bbc55-134">Beispiel: Version 10.0.18362.1.</span><span class="sxs-lookup"><span data-stu-id="bbc55-134">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="bbc55-135">Ein Flyout wird mit dem Ende des Supportdatums angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bbc55-135">A flyout will appear with the end of support date.</span></span>

    ![Screenshot des Enddatums des Supportdatums.](images/version-eos-date.png)

<span data-ttu-id="bbc55-137">Nachdem Sie ermittelt haben, welche Software- und Softwareversionen aufgrund ihres Status am Ende des Supportstatus anfällig sind, müssen Sie entscheiden, ob Sie sie aus Ihrer Organisation aktualisieren oder entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="bbc55-137">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="bbc55-138">Dadurch wird die Gefährdung Ihrer Organisation durch Sicherheitsrisiken und erweiterte dauerhafte Bedrohungen gesenkt.</span><span class="sxs-lookup"><span data-stu-id="bbc55-138">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bbc55-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bbc55-139">Related topics</span></span>

- [<span data-ttu-id="bbc55-140">Übersicht über Bedrohungen Sicherheitsrisikomanagement Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="bbc55-140">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="bbc55-141">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="bbc55-141">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="bbc55-142">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="bbc55-142">Software inventory</span></span>](tvm-software-inventory.md)
