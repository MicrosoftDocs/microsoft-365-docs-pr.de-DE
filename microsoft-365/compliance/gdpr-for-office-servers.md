---
title: DSGVO für Office-Server
description: Erfahren Sie, wie Sie mit DSGVO-Anforderungen auf lokalen Office-Servern umgehen.
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
ms.openlocfilehash: e18db2e5c180bd896e82d98506e8a65831550bce
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073237"
---
# <a name="gdpr-for-office-on-premises-servers"></a><span data-ttu-id="efefd-103">DSGVO für lokale Office-Server</span><span class="sxs-lookup"><span data-stu-id="efefd-103">GDPR for Office on-premises Servers</span></span>

<span data-ttu-id="efefd-p101">Im Rahmen der Datenschutz-Grundverordnung (DSGVO) werden Anforderungen für Unternehmen zum Schutz personenbezogener Daten und zur angemessenen Reaktion auf Datensubjektanforderungen eingeführt. Diese Artikelreihe bietet empfohlene Ansätze für lokale Workloads:</span><span class="sxs-lookup"><span data-stu-id="efefd-p101">The General Data Protection Regulation (GDPR) introduces requirements for organizations to protect personal data and respond appropriately to data subject requests. This series of articles provides recommended approaches for on-premises workloads:</span></span>

-   [<span data-ttu-id="efefd-106">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="efefd-106">SharePoint Server</span></span>](gdpr-for-sharepoint-server.md)

-   [<span data-ttu-id="efefd-107">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="efefd-107">Exchange Server</span></span>](gdpr-for-exchange-server.md)

-   [<span data-ttu-id="efefd-108">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="efefd-108">Skype for Business Server</span></span>](gdpr-for-skype-for-business-server.md)

-   [<span data-ttu-id="efefd-109">Project Server</span><span class="sxs-lookup"><span data-stu-id="efefd-109">Project Server</span></span>](gdpr-for-project-server.md)

-   [<span data-ttu-id="efefd-110">Office Web Apps Server und Office Online Server</span><span class="sxs-lookup"><span data-stu-id="efefd-110">Office Web Apps Server and Office Online Server</span></span>](gdpr-for-office-online-server.md)

-   [<span data-ttu-id="efefd-111">Lokale Dateifreigaben</span><span class="sxs-lookup"><span data-stu-id="efefd-111">On-premises file shares</span></span>](gdpr-for-on-premises-file-shares.md)

<span data-ttu-id="efefd-112">Weitere Informationen zu der DSGVO und dazu, wie Microsoft Ihnen helfen kann, finden Sie im [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="efefd-112">For more information about the GDPR and how Microsoft can help you, see the [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx).</span></span>

<span data-ttu-id="efefd-p102">Vor der Arbeit mit lokalen Daten wenden Sie sich an die Teams Ihrer Rechts- und Compliance-Abteilung, um Hilfestellung und Informationen zu vorhandenen Klassifizierungsschemata und Ansätzen für die Arbeit mit personenbezogenen Daten zu erhalten. Microsoft bietet Empfehlungen für die Entwicklung und Erweiterung von Klassifizierungsschemata im DSGVO-bezogenen Data Discovery Toolkit von Microsoft unter [ https://aka.ms/gdprpartners ](<https://aka.ms/gdprpartners>). In diesem Toolkit werden auch Vorgehensweisen beschrieben, mit denen Sie lokale Daten in die Cloud verschieben können, wo Sie bei Bedarf komplexere Daten-Governance-Funktionen verwenden können. In den Artikeln in diesem Abschnitt werden Empfehlungen für Daten gegeben, die lokal gespeichert bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="efefd-p102">Before doing any work with on-premises data, consult with your legal and compliance teams to seek guidance and to learn about existing classification schemas and approaches to working with personal data. Microsoft provides recommendations for developing and extending classifications schemas in the Microsoft GDPR Data Discovery Toolkit at [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). This toolkit also describes approaches for moving on-premises data to the cloud where you can use more sophisticated data governance capabilities, if this is desired. The articles in this section provide recommendations for data that is intended to remain on premises.</span></span>

<span data-ttu-id="efefd-p103">In der folgenden Abbildung werden empfohlene Funktionen aufgeführt, die in jedem dieser Workloads zum Ermitteln, Klassifizieren, Schützen und Überwachen personenbezogener Daten verwendet werden können. Weitere Informationen finden Sie in den Artikeln in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="efefd-p103">The following illustration lists recommended capabilities to use across each of these workloads to discover, classify, protect, and monitor personal data. See the articles in this section for more information.</span></span>

![](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a><span data-ttu-id="efefd-119">Beschreibung der Abbildung</span><span class="sxs-lookup"><span data-stu-id="efefd-119">Illustration description</span></span>

<span data-ttu-id="efefd-120">Für Zwecke der Barrierefreiheit enthält die folgende Tabelle die gleichen Beispiele wie die Abbildung.</span><span class="sxs-lookup"><span data-stu-id="efefd-120">For accessibility, the following table provides the same examples in the illustration.</span></span>

|             |<span data-ttu-id="efefd-121">Windows Server-Dateifreigaben</span><span class="sxs-lookup"><span data-stu-id="efefd-121">Windows Server file shares</span></span>|<span data-ttu-id="efefd-122">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="efefd-122">SharePoint Server</span></span>|<span data-ttu-id="efefd-123">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="efefd-123">Exchange Server</span></span>|<span data-ttu-id="efefd-124">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="efefd-124">Skype for Business</span></span>|<span data-ttu-id="efefd-125">Project Server</span><span class="sxs-lookup"><span data-stu-id="efefd-125">Project Server</span></span>|
|:------------|:-------------------------|:----------------|:--------------|:-----------------|:-------------|
|<span data-ttu-id="efefd-126">Ermitteln</span><span class="sxs-lookup"><span data-stu-id="efefd-126">Discover</span></span>|<span data-ttu-id="efefd-127">Azure Information Protection-Scanner\*</span><span class="sxs-lookup"><span data-stu-id="efefd-127">Azure Information Protection scanner\*</span></span>|<span data-ttu-id="efefd-128">Suchcenter oder eDiscovery (nachdem Daten klassifiziert wurden); Azure Information Protection-Scanner\*</span><span class="sxs-lookup"><span data-stu-id="efefd-128">Search Center or eDiscovery (after data is classified); Azure Information Protection scanner\*</span></span>|<span data-ttu-id="efefd-129">Exchange-eDiscovery-Portal</span><span class="sxs-lookup"><span data-stu-id="efefd-129">Exchange eDiscovery Portal</span></span>|<span data-ttu-id="efefd-130">Exchange-eDiscovery-Portal</span><span class="sxs-lookup"><span data-stu-id="efefd-130">Exchange eDiscovery portal</span></span>|<span data-ttu-id="efefd-131">SQL-Skripts für Ermittlung und Export</span><span class="sxs-lookup"><span data-stu-id="efefd-131">SQL scripts for discovery and exporting</span></span>|
|<span data-ttu-id="efefd-132">Klassifizieren</span><span class="sxs-lookup"><span data-stu-id="efefd-132">Classify</span></span>|<span data-ttu-id="efefd-133">Azure Information Protection-Scanner\*; Typen vertraulicher Informationen in Office 365</span><span class="sxs-lookup"><span data-stu-id="efefd-133">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="efefd-134">Azure Information Protection-Scanner\*; Typen vertraulicher Informationen in Office 365</span><span class="sxs-lookup"><span data-stu-id="efefd-134">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="efefd-135">Aufbewahrungstags und Aufbewahrungsrichtlinien in Exchange</span><span class="sxs-lookup"><span data-stu-id="efefd-135">Exchange retention tags and retention policies</span></span>|<span data-ttu-id="efefd-136">Aufbewahrungstags und Aufbewahrungsrichtlinien in Exchange</span><span class="sxs-lookup"><span data-stu-id="efefd-136">Exchange retention tags and retention policies</span></span>||
|<span data-ttu-id="efefd-137">Schützen</span><span class="sxs-lookup"><span data-stu-id="efefd-137">Protect</span></span>||<span data-ttu-id="efefd-138">Regeln zur Verhinderung von Datenverlust für Exchange Server; Berechtigungen, IRM-Schutz für Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="efefd-138">Exchange Server data loss prevention rules; Permissions, IRM-protection for libraries</span></span>|<span data-ttu-id="efefd-139">Regeln zur Verhinderung von Datenverlust für Exchange Server; IRM-Integration in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="efefd-139">Exchange Server data loss prevention rules; IRM integration with Exchange Server</span></span>|||
|<span data-ttu-id="efefd-140">Überwachen</span><span class="sxs-lookup"><span data-stu-id="efefd-140">Monitor</span></span>|<span data-ttu-id="efefd-141">Protokolle in SIEM-Tools integrieren</span><span class="sxs-lookup"><span data-stu-id="efefd-141">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="efefd-142">Protokolle in SIEM-Tools integrieren</span><span class="sxs-lookup"><span data-stu-id="efefd-142">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="efefd-143">Protokolle in SIEM-Tools integrieren</span><span class="sxs-lookup"><span data-stu-id="efefd-143">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="efefd-144">Protokolle in SIEM-Tools integrieren</span><span class="sxs-lookup"><span data-stu-id="efefd-144">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="efefd-145">Protokolle in SIEM-Tools integrieren</span><span class="sxs-lookup"><span data-stu-id="efefd-145">Integrate logs with SIEM tools</span></span>|

<span data-ttu-id="efefd-p104">\*Durch Schutz wird die Datei verschlüsselt. Folglich kann SharePoint Server die Typen vertraulicher Informationen in diesen Dateien nicht finden.</span><span class="sxs-lookup"><span data-stu-id="efefd-p104">\*Note that protection encrypts the file. Consequently, SharePoint Server can’t find the sensitive information types in protected files.</span></span>
