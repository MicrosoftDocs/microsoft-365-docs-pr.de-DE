---
title: Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützigen Organisationen und andere agile Organisationen
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
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: Strat_O365_Enterprise
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: 'Zusammenfassung: Planungs- und Implementierungsleitfaden für sich schnell wandelnde Organisationen mit einem erhöhten Bedrohungsprofil.'
ms.openlocfilehash: 475707f2c98ade03f3bd558d5e9ea9eb9b5c64df
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082532"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="f8f12-103">Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützigen Organisationen und andere agile Organisationen</span><span class="sxs-lookup"><span data-stu-id="f8f12-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

 <span data-ttu-id="f8f12-104">**Zusammenfassung:** Planungs- und Implementierungsleitfaden für sich schnell wandelnde Organisationen mit einem erhöhten Bedrohungsprofil.</span><span class="sxs-lookup"><span data-stu-id="f8f12-104">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>
  
<span data-ttu-id="f8f12-p101">Wenn Ihre Organisation nach Agile-Prinzipien agiert, Sie ein kleines IT-Team haben und Ihr Bedrohungsprofil höher ist als der Durchschnitt, ist dieser Leitfaden für Sie genau richtig. Diese Lösung veranschaulicht, wie Sie schnell eine Umgebung mit grundlegenden Clouddiensten erstellen können, die von Anfang an sichere Kontrollmechanismen umfasst. Dieser Leitfaden umfasst bindende Sicherheitsempfehlungen zum Schutz von Daten, Identitäten, E-Mail und Zugriff über mobile Geräte.</span><span class="sxs-lookup"><span data-stu-id="f8f12-p101">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you. This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start. This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>
  
## <a name="security-solution-guidance"></a><span data-ttu-id="f8f12-108">Anleitungen für Sicherheitslösungen</span><span class="sxs-lookup"><span data-stu-id="f8f12-108">Security solution guidance</span></span>

<span data-ttu-id="f8f12-p102">Diese Anleitung beschreibt, wie eine sichere Cloudumgebung implementiert wird. Die Anleitung für die Lösung kann von jeder Organisation verwendet werden. Sie bietet zusätzliche Hilfe für agile Organisationen mit dem BYOD-Zugriff und Gastkonten. Sie können diesen Leitfaden als Startpunkt für den Entwurf Ihrer eigenen Umgebung verwenden. Wir freuen uns über Ihr Feedback unter [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f8f12-p102">This guidance describes how to implement a secure cloud environment. The solution guidance can be used by any organization. It includes extra help for agile organizations with BYOD access and guest accounts. You can use this guidance as a starting-point for designing your own environment. We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f8f12-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="f8f12-114">**Item**</span></span> <br/> |<span data-ttu-id="f8f12-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f8f12-115">**Description**</span></span> <br/> |
|<span data-ttu-id="f8f12-116">**Microsoft-Sicherheitsanleitungen von Microsoft für politische Kampagnen**</span><span class="sxs-lookup"><span data-stu-id="f8f12-116">**Microsoft Security Guidance for Political Campaigns**</span></span> <br/> <span data-ttu-id="f8f12-117">[![Miniaturansicht für Miniposter festgelegt.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)          ](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="f8f12-117">[![Thumb nail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)          ](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br/> <span data-ttu-id="f8f12-118">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)  \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="f8f12-118">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)  \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span> <br/> |<span data-ttu-id="f8f12-p103">Dieser Leitfaden verwendet eine Organisation für politische Kampagnen als Beispiel. Verwenden Sie diesen Leitfaden als Grundlage für eine beliebige Umgebung.</span><span class="sxs-lookup"><span data-stu-id="f8f12-p103">This guidance uses a political campaign organization as an example. Use this guidance as a starting point for any environment.</span></span>  <br/> |
|<span data-ttu-id="f8f12-121">**Sicherheitsanleitungen von Microsoft für gemeinnützige Organisationen**</span><span class="sxs-lookup"><span data-stu-id="f8f12-121">**Microsoft Security Guidance for Nonprofits**</span></span> <br/> <span data-ttu-id="f8f12-122">[![Miniaturbild für eine herunterladbare Datei](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)          ](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="f8f12-122">[![Thumnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)          ](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br/> <span data-ttu-id="f8f12-123">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)  \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="f8f12-123">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)  \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span> <br/> |<span data-ttu-id="f8f12-p104">Dieser Leitfaden wurde für gemeinnützige Organisationen geringfügig überarbeitet. Er verweist beispielsweise auf Office 365-Pläne für gemeinnützige Organisation. Die technische Anleitung ist identisch wie im Leitfaden für politische Kampagnen.</span><span class="sxs-lookup"><span data-stu-id="f8f12-p104">This guide is slightly revised for nonprofit organizations. For example, it references Office 365 Nonprofit plans. The technical guidance is the same as the political campaign solution guide.</span></span>  <br/> |
   
## <a name="test-lab-guides"></a><span data-ttu-id="f8f12-127">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="f8f12-127">Test Lab Guides</span></span>

<span data-ttu-id="f8f12-128">Um eine Entwicklungs-/Testumgebung für diese Lösung zu erstellen, verwenden Sie die folgenden Testumgebungsanleitungen:</span><span class="sxs-lookup"><span data-stu-id="f8f12-128">To create a dev/test environment for this solution, use the following test lab guides:</span></span> 
  
- [<span data-ttu-id="f8f12-129">Konfigurieren von Gruppen und Benutzern für eine politische Kampagne in einer Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="f8f12-129">Configure groups and users for a political campaign dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/configure-groups-and-users-for-a-political-campaign-dev-test-environment)
    
     <span data-ttu-id="f8f12-130">Erstellen Sie Testabonnements für Office 365 und EMS, und erstellen Sie Gruppen und Benutzer für eine repräsentative politische Kampagne.</span><span class="sxs-lookup"><span data-stu-id="f8f12-130">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>
    
- [<span data-ttu-id="f8f12-131">Erstellen von Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne</span><span class="sxs-lookup"><span data-stu-id="f8f12-131">Create team sites in a political campaign dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/create-team-sites-in-a-political-campaign-dev-test-environment)
    
    <span data-ttu-id="f8f12-132">Erstellen Sie vier SharePoint Online-Teamwebsites mit den Sicherheitsebenen „Intern“, „Privat“, „Sensibel“ und „Streng vertraulich“.</span><span class="sxs-lookup"><span data-stu-id="f8f12-132">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>
    
<span data-ttu-id="f8f12-133">Weitere Sicherheitsfunktionen für die Vorführung oder Machbarkeitsstudie finden Sie unter [Office 365-Testumgebungsanleitungen](https://aka.ms/o365tlgs).</span><span class="sxs-lookup"><span data-stu-id="f8f12-133">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](https://aka.ms/o365tlgs).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f8f12-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8f12-134">See Also</span></span>

[<span data-ttu-id="f8f12-135">Testumgebungsanleitungen (TLGs) zur Cloudakzeptanz</span><span class="sxs-lookup"><span data-stu-id="f8f12-135">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="f8f12-136">Ressourcen zur Cloud-IT-Architektur von Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8f12-136">Microsoft Cloud IT architecture resources</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources)



