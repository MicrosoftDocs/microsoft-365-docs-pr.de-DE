---
title: Microsoft-Sicherheitsleitfaden – Politische Kampagnen und gemeinnützige Organisationen
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: 'Zusammenfassung: Planungs- und Implementierungsleitfaden für sich schnell wandelnde Organisationen mit einem erhöhten Bedrohungsprofil.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f8ed01d2c41529782c5c714bfe66096b97300712
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287401"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="a785d-103">Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützigen Organisationen und andere agile Organisationen</span><span class="sxs-lookup"><span data-stu-id="a785d-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a785d-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="a785d-104">**Applies to**</span></span>
- [<span data-ttu-id="a785d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a785d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a785d-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="a785d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

 <span data-ttu-id="a785d-107">**Zusammenfassung:** Planungs- und Implementierungsleitfaden für sich schnell wandelnde Organisationen mit einem erhöhten Bedrohungsprofil.</span><span class="sxs-lookup"><span data-stu-id="a785d-107">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>

<span data-ttu-id="a785d-p101">Wenn Ihre Organisation nach Agile-Prinzipien agiert, Sie ein kleines IT-Team haben und Ihr Bedrohungsprofil höher ist als der Durchschnitt, ist dieser Leitfaden für Sie genau richtig. Diese Lösung veranschaulicht, wie Sie schnell eine Umgebung mit grundlegenden Clouddiensten erstellen können, die von Anfang an sichere Kontrollmechanismen umfasst. Dieser Leitfaden umfasst bindende Sicherheitsempfehlungen zum Schutz von Daten, Identitäten, E-Mail und Zugriff über mobile Geräte.</span><span class="sxs-lookup"><span data-stu-id="a785d-p101">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you. This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start. This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>

## <a name="security-solution-guidance"></a><span data-ttu-id="a785d-111">Anleitungen für Sicherheitslösungen</span><span class="sxs-lookup"><span data-stu-id="a785d-111">Security solution guidance</span></span>

<span data-ttu-id="a785d-p102">Diese Anleitung beschreibt, wie eine sichere Cloudumgebung implementiert wird. Die Anleitung für die Lösung kann von jeder Organisation verwendet werden. Sie bietet zusätzliche Hilfe für agile Organisationen mit dem BYOD-Zugriff und Gastkonten. Sie können diesen Leitfaden als Startpunkt für den Entwurf Ihrer eigenen Umgebung verwenden. Wir freuen uns über Ihr Feedback unter [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a785d-p102">This guidance describes how to implement a secure cloud environment. The solution guidance can be used by any organization. It includes extra help for agile organizations with BYOD access and guest accounts. You can use this guidance as a starting-point for designing your own environment. We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span>

****

|<span data-ttu-id="a785d-117">Element</span><span class="sxs-lookup"><span data-stu-id="a785d-117">Item</span></span>|<span data-ttu-id="a785d-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a785d-118">Description</span></span>|
|---|---|
|<span data-ttu-id="a785d-119">**Microsoft-Sicherheitsanleitungen von Microsoft für politische Kampagnen**</span><span class="sxs-lookup"><span data-stu-id="a785d-119">**Microsoft Security Guidance for Political Campaigns**</span></span> <br> <span data-ttu-id="a785d-120">[![Miniaturansicht für Miniposter festgelegt.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="a785d-120">[![Thumbnail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br> <span data-ttu-id="a785d-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="a785d-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span>|<span data-ttu-id="a785d-p103">Dieser Leitfaden verwendet eine Organisation für politische Kampagnen als Beispiel. Verwenden Sie diesen Leitfaden als Grundlage für eine beliebige Umgebung.</span><span class="sxs-lookup"><span data-stu-id="a785d-p103">This guidance uses a political campaign organization as an example. Use this guidance as a starting point for any environment.</span></span>|
|<span data-ttu-id="a785d-124">**Sicherheitsanleitungen von Microsoft für gemeinnützige Organisationen**</span><span class="sxs-lookup"><span data-stu-id="a785d-124">**Microsoft Security Guidance for Nonprofits**</span></span> <br> <span data-ttu-id="a785d-125">[![Miniaturbild für eine herunterladbare Datei](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="a785d-125">[![Thumbnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br> <span data-ttu-id="a785d-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="a785d-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span>|<span data-ttu-id="a785d-p104">Dieser Leitfaden wurde für gemeinnützige Organisationen geringfügig überarbeitet. Er verweist beispielsweise auf Office 365-Pläne für gemeinnützige Organisation. Die technische Anleitung ist identisch wie im Leitfaden für politische Kampagnen.</span><span class="sxs-lookup"><span data-stu-id="a785d-p104">This guide is slightly revised for nonprofit organizations. For example, it references Office 365 Nonprofit plans. The technical guidance is the same as the political campaign solution guide.</span></span>|
|

## <a name="test-lab-guides"></a><span data-ttu-id="a785d-130">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="a785d-130">Test Lab Guides</span></span>

<span data-ttu-id="a785d-131">Um eine Entwicklungs-/Testumgebung für diese Lösung zu erstellen, verwenden Sie die folgenden Testumgebungsanleitungen:</span><span class="sxs-lookup"><span data-stu-id="a785d-131">To create a dev/test environment for this solution, use the following test lab guides:</span></span>

- [<span data-ttu-id="a785d-132">Konfigurieren von Gruppen und Benutzern für eine politische Kampagne in einer Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="a785d-132">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="a785d-133">Erstellen Sie Testabonnements für Office 365 und EMS, und erstellen Sie Gruppen und Benutzer für eine repräsentative politische Kampagne.</span><span class="sxs-lookup"><span data-stu-id="a785d-133">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>

- [<span data-ttu-id="a785d-134">Erstellen von Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne</span><span class="sxs-lookup"><span data-stu-id="a785d-134">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="a785d-135">Erstellen Sie vier SharePoint Online-Teamwebsites mit den Sicherheitsebenen „Intern“, „Privat“, „Sensibel“ und „Streng vertraulich“.</span><span class="sxs-lookup"><span data-stu-id="a785d-135">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>

<span data-ttu-id="a785d-136">Weitere Sicherheitsfunktionen für die Vorführung oder Machbarkeitsstudie finden Sie unter [Office 365-Testumgebungsanleitungen](https://aka.ms/o365tlgs).</span><span class="sxs-lookup"><span data-stu-id="a785d-136">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](https://aka.ms/o365tlgs).</span></span>

## <a name="see-also"></a><span data-ttu-id="a785d-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a785d-137">See Also</span></span>

[<span data-ttu-id="a785d-138">Testumgebungsanleitungen (TLGs) zur Cloudakzeptanz</span><span class="sxs-lookup"><span data-stu-id="a785d-138">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="a785d-139">Ressourcen zur Cloud-IT-Architektur von Microsoft</span><span class="sxs-lookup"><span data-stu-id="a785d-139">Microsoft Cloud IT architecture resources</span></span>](../../solutions/cloud-architecture-models.md)
