---
title: DSGVO für Office-Server
description: Erfahren Sie, wie Sie mit Anforderungen der Datenschutz-Grundverordnung (DSGVO) in lokalen Office-Servern umgehen.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5ee42a12f65ad5eff0a33ef2b61d328ebdc7af3e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547331"
---
# <a name="gdpr-for-office-on-premises-servers"></a><span data-ttu-id="3b0b1-103">DSGVO für lokale Office-Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-103">GDPR for Office on-premises Servers</span></span>

<span data-ttu-id="3b0b1-p101">Im Rahmen der Datenschutz-Grundverordnung (DSGVO) werden Anforderungen für Unternehmen zum Schutz personenbezogener Daten und zur angemessenen Reaktion auf Datensubjektanforderungen eingeführt. Diese Artikelreihe bietet empfohlene Ansätze für lokale Workloads:</span><span class="sxs-lookup"><span data-stu-id="3b0b1-p101">The General Data Protection Regulation (GDPR) introduces requirements for organizations to protect personal data and respond appropriately to data subject requests. This series of articles provides recommended approaches for on-premises workloads:</span></span>

- [<span data-ttu-id="3b0b1-106">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-106">SharePoint Server</span></span>](gdpr-for-sharepoint-server.md)

- [<span data-ttu-id="3b0b1-107">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-107">Exchange Server</span></span>](gdpr-for-exchange-server.md)

- [<span data-ttu-id="3b0b1-108">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-108">Skype for Business Server</span></span>](gdpr-for-skype-for-business-server.md)

- [<span data-ttu-id="3b0b1-109">Project Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-109">Project Server</span></span>](gdpr-for-project-server.md)

- [<span data-ttu-id="3b0b1-110">Office Web Apps Server und Office Online Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-110">Office Web Apps Server and Office Online Server</span></span>](gdpr-for-office-online-server.md)

- [<span data-ttu-id="3b0b1-111">Lokale Dateifreigaben</span><span class="sxs-lookup"><span data-stu-id="3b0b1-111">On-premises file shares</span></span>](gdpr-for-on-premises-file-shares.md)

<span data-ttu-id="3b0b1-112">Weitere Informationen zu der DSGVO und dazu, wie Microsoft Ihnen helfen kann, finden Sie im [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).</span><span class="sxs-lookup"><span data-stu-id="3b0b1-112">For more information about the GDPR and how Microsoft can help you, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).</span></span>

<span data-ttu-id="3b0b1-p102">Vor der Arbeit mit lokalen Daten wenden Sie sich an die Teams Ihrer Rechts- und Compliance-Abteilung, um Hilfestellung und Informationen zu vorhandenen Klassifizierungsschemata und Ansätzen für die Arbeit mit personenbezogenen Daten zu erhalten. Microsoft bietet Empfehlungen für die Entwicklung und Erweiterung von Klassifizierungsschemata im DSGVO-bezogenen Data Discovery Toolkit von Microsoft unter [ https://aka.ms/gdprpartners ](<https://aka.ms/gdprpartners>). In diesem Toolkit werden auch Vorgehensweisen beschrieben, mit denen Sie lokale Daten in die Cloud verschieben können, wo Sie bei Bedarf komplexere Daten-Governance-Funktionen verwenden können. In den Artikeln in diesem Abschnitt werden Empfehlungen für Daten gegeben, die lokal gespeichert bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="3b0b1-p102">Before doing any work with on-premises data, consult with your legal and compliance teams to seek guidance and to learn about existing classification schemas and approaches to working with personal data. Microsoft provides recommendations for developing and extending classifications schemas in the Microsoft GDPR Data Discovery Toolkit at [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). This toolkit also describes approaches for moving on-premises data to the cloud where you can use more sophisticated data governance capabilities, if this is desired. The articles in this section provide recommendations for data that is intended to remain on premises.</span></span>

<span data-ttu-id="3b0b1-p103">In der folgenden Abbildung werden empfohlene Funktionen aufgeführt, die in jedem dieser Workloads zum Ermitteln, Klassifizieren, Schützen und Überwachen personenbezogener Daten verwendet werden können. Weitere Informationen finden Sie in den Artikeln in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="3b0b1-p103">The following illustration lists recommended capabilities to use across each of these workloads to discover, classify, protect, and monitor personal data. See the articles in this section for more information.</span></span>

![Diagramm, das beschreibt, wie personenbezogene Daten über Workloads hinweg ermittelt, klassifiziert, geschützt und überwacht werden können](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a><span data-ttu-id="3b0b1-120">Beschreibung der Abbildung</span><span class="sxs-lookup"><span data-stu-id="3b0b1-120">Illustration description</span></span>

<span data-ttu-id="3b0b1-121">Für Zwecke der Barrierefreiheit enthält die folgende Tabelle die gleichen Beispiele wie die Abbildung.</span><span class="sxs-lookup"><span data-stu-id="3b0b1-121">For accessibility, the following table provides the same examples in the illustration.</span></span>

****

|<span data-ttu-id="3b0b1-122">Aktion</span><span class="sxs-lookup"><span data-stu-id="3b0b1-122">Action</span></span>|<span data-ttu-id="3b0b1-123">Windows Server-Dateifreigaben</span><span class="sxs-lookup"><span data-stu-id="3b0b1-123">Windows Server file shares</span></span>|<span data-ttu-id="3b0b1-124">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-124">SharePoint Server</span></span>|<span data-ttu-id="3b0b1-125">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-125">Exchange Server</span></span>|<span data-ttu-id="3b0b1-126">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3b0b1-126">Skype for Business</span></span>|<span data-ttu-id="3b0b1-127">Project Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-127">Project Server</span></span>|
|---|---|---|---|---|---|
|<span data-ttu-id="3b0b1-128">Ermitteln</span><span class="sxs-lookup"><span data-stu-id="3b0b1-128">Discover</span></span>|<span data-ttu-id="3b0b1-129">Azure Information Protection-Scanner<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b0b1-129">Azure Information Protection scanner<sup>\*</sup></span></span>|<span data-ttu-id="3b0b1-130">Suchcenter oder eDiscovery (nach Klassifizierung der Daten)</span><span class="sxs-lookup"><span data-stu-id="3b0b1-130">Search Center or eDiscovery (after data is classified)</span></span> <br/><br/> <span data-ttu-id="3b0b1-131">Azure Information Protection-Scanner<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b0b1-131">Azure Information Protection scanner<sup>\*</sup></span></span>|<span data-ttu-id="3b0b1-132">Exchange-eDiscovery-Portal</span><span class="sxs-lookup"><span data-stu-id="3b0b1-132">Exchange eDiscovery Portal</span></span>|<span data-ttu-id="3b0b1-133">Exchange-eDiscovery-Portal</span><span class="sxs-lookup"><span data-stu-id="3b0b1-133">Exchange eDiscovery portal</span></span>|<span data-ttu-id="3b0b1-134">SQL-Skripts für Ermittlung und Export</span><span class="sxs-lookup"><span data-stu-id="3b0b1-134">SQL scripts for discovery and exporting</span></span>|
|<span data-ttu-id="3b0b1-135">Klassifizieren</span><span class="sxs-lookup"><span data-stu-id="3b0b1-135">Classify</span></span>|<span data-ttu-id="3b0b1-136">Azure Information Protection-Scanner<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b0b1-136">Azure Information Protection scanner<sup>\*</sup></span></span> <br/><br/> <span data-ttu-id="3b0b1-137">Typen vertraulicher Informationen in Office 365</span><span class="sxs-lookup"><span data-stu-id="3b0b1-137">Office 365 sensitive information types</span></span>|<span data-ttu-id="3b0b1-138">Azure Information Protection-Scanner<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b0b1-138">Azure Information Protection scanner<sup>\*</sup></span></span> <br/><br/> <span data-ttu-id="3b0b1-139">Typen vertraulicher Informationen in Office 365</span><span class="sxs-lookup"><span data-stu-id="3b0b1-139">Office 365 sensitive information types</span></span>|<span data-ttu-id="3b0b1-140">Aufbewahrungstags und Aufbewahrungsrichtlinien in Exchange</span><span class="sxs-lookup"><span data-stu-id="3b0b1-140">Exchange retention tags and retention policies</span></span>|<span data-ttu-id="3b0b1-141">Aufbewahrungstags und Aufbewahrungsrichtlinien in Exchange</span><span class="sxs-lookup"><span data-stu-id="3b0b1-141">Exchange retention tags and retention policies</span></span>||
|<span data-ttu-id="3b0b1-142">Schützen</span><span class="sxs-lookup"><span data-stu-id="3b0b1-142">Protect</span></span>||<span data-ttu-id="3b0b1-143">Regeln zur Verhinderung von Datenverlust für Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-143">Exchange Server data loss prevention rules</span></span> <br/><br/> <span data-ttu-id="3b0b1-144">Berechtigungen, IRM – Schutz für Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="3b0b1-144">Permissions, IRM-protection for libraries</span></span>|<span data-ttu-id="3b0b1-145">Regeln zur Verhinderung von Datenverlust für Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-145">Exchange Server data loss prevention rules</span></span> <br/><br/> <span data-ttu-id="3b0b1-146">IRM-Integration in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3b0b1-146">IRM integration with Exchange Server</span></span>|||
|<span data-ttu-id="3b0b1-147">Überwachen</span><span class="sxs-lookup"><span data-stu-id="3b0b1-147">Monitor</span></span>|<span data-ttu-id="3b0b1-148">Protokolle in SIEM-Tools integrieren</span><span class="sxs-lookup"><span data-stu-id="3b0b1-148">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="3b0b1-149">Protokolle in SIEM-Tools integrieren</span><span class="sxs-lookup"><span data-stu-id="3b0b1-149">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="3b0b1-150">Protokolle in SIEM-Tools integrieren</span><span class="sxs-lookup"><span data-stu-id="3b0b1-150">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="3b0b1-151">Protokolle in SIEM-Tools integrieren</span><span class="sxs-lookup"><span data-stu-id="3b0b1-151">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="3b0b1-152">Protokolle in SIEM-Tools integrieren</span><span class="sxs-lookup"><span data-stu-id="3b0b1-152">Integrate logs with SIEM tools</span></span>|
|

<span data-ttu-id="3b0b1-153"><sup>\*</sup> Durch Schutz wird die Datei verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="3b0b1-153"><sup>\*</sup> Note that protection encrypts the file.</span></span> <span data-ttu-id="3b0b1-154">Folglich kann der SharePoint Server die Typen vertraulicher Informationen in geschützten Dateien nicht finden.</span><span class="sxs-lookup"><span data-stu-id="3b0b1-154">Consequently, SharePoint Server can't find the sensitive information types in protected files.</span></span>
