---
title: Grundlegendes zur Enterprise Business Continuity-Verwaltung mit Clouddiensten
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: Hier erfahren Sie, wie sich die Planung und Implementierung von Geschäftskontinuität ändert, wenn Clouddienste Bestandteil Ihres IT-Angebots sind.
ms.openlocfilehash: bb9f3f1367b376c63b8779f3ff62f05b0312ef55
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "43030106"
---
# <a name="enterprise-business-continuity-management-ebcm-with-cloud-services"></a><span data-ttu-id="b4bdf-103">Enterprise Business Continuity-Verwaltung (EBCM) mit Clouddiensten</span><span class="sxs-lookup"><span data-stu-id="b4bdf-103">Enterprise business continuity management (EBCM) with cloud services</span></span>

<span data-ttu-id="b4bdf-104">Als Bestandteil der digitalen Transformation Ihrer Organisation müssen Sie Ihre Notfallwiederherstellungs- und Geschäftskontinuitätspläne überprüfen und aktualisieren, um die Geschäftsprozesse zu berücksichtigen, die von Microsoft 365-Clouddiensten abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-104">As part of your organizations digital transformation, you need to revisit and update your disaster recovery and business continuity plans to account for the business process that depend on Microsoft 365 Cloud services.</span></span> <span data-ttu-id="b4bdf-105">Konzeption und Betrieb von Microsoft 365-Clouddiensten wie Exchange Online, SharePoint Online und OneDrive for Business sind auf hohe Ausfallsicherheit ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-105">Microsoft 365 Cloud services, like Exchange Online, SharePoint Online and OneDrive for Business are designed and operated to be highly resilient.</span></span>

> [!NOTE]
> <span data-ttu-id="b4bdf-106">Weitere Informationen zum eigenen EBCM-Plan finden Sie im [Whitepaper zum Enterprise Business Continuity Management-Programm](https://go.microsoft.com/fwlink/?linkid=2121521) von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-106">You can learn more about Microsoft's own EBCM plan in the [Enterprise Business Continuity Management Program whitepaper](https://go.microsoft.com/fwlink/?linkid=2121521).</span></span> <span data-ttu-id="b4bdf-107">Anmeldung ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-107">Login is required.</span></span>

<span data-ttu-id="b4bdf-108">Aber selbst bei hoher Ausfallsicherheit können Dienstincidents auftreten.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-108">Even with this resilience, service incidents do occur.</span></span> <span data-ttu-id="b4bdf-109">In diesen Fällen sollte Ihre Organisation vorbereitet sein und über eine definierte Geschäftskontinuitätsstrategie verfügen.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-109">When they do, your organization should be prepared and have a well-defined business continuity strategy.</span></span>

<span data-ttu-id="b4bdf-110">Wenn Sie Ihre Pläne noch nicht aktualisiert haben, hilft Ihnen diese Themenreihe bei der Planung Ihrer Strategie, damit ihre Dienste bei einen Fehler mit einem bekannten Status wiederhergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-110">If you haven't updated your plans yet this series of topics helps you to plan your strategy so your services can fail to a known state.</span></span> <span data-ttu-id="b4bdf-111">In diesen Themen werden die Hauptüberlegungen zur Verbesserung der Kontinuitätsbereitschaft behandelt.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-111">These topics highlight key considerations for improving your continuity readiness.</span></span>

## <a name="list-of-topics-with-links"></a><span data-ttu-id="b4bdf-112">Liste der Themen mit Links</span><span class="sxs-lookup"><span data-stu-id="b4bdf-112">List of topics with links</span></span>

- [<span data-ttu-id="b4bdf-113">Verantwortlichkeit von Kunden und Cloudpartnern</span><span class="sxs-lookup"><span data-stu-id="b4bdf-113">Customer and cloud partner responsibilities</span></span>](ebcm-customer-and-cloud-partner-ebcm-responsibilities.md)
- [<span data-ttu-id="b4bdf-114">Microsoft 365-Dienstausfallsicherheit</span><span class="sxs-lookup"><span data-stu-id="b4bdf-114">Microsoft 365 service resiliency</span></span>](ebcm-m365-service-resiliency.md)
- [<span data-ttu-id="b4bdf-115">Entwickeln Ihres Kontinuitätsplans</span><span class="sxs-lookup"><span data-stu-id="b4bdf-115">Developing your continuity plan</span></span>](ebcm-developing-your-ebcm-plan.md)
- [<span data-ttu-id="b4bdf-116">Schadensbegrenzungsszenarien für Microsoft 365-Dienstincidents</span><span class="sxs-lookup"><span data-stu-id="b4bdf-116">Microsoft 365 service incident mitigation scenarios</span></span>](ebcm-microsoft-365-mitigations.md)
- [<span data-ttu-id="b4bdf-117">Microsoft 365-Geschäftskontinuitätsplan – Training und Probelauf</span><span class="sxs-lookup"><span data-stu-id="b4bdf-117">Microsoft 365 business continuity plan training and rehearsal</span></span>](ebcm-enterprise-business-continuity-management-plan-rehearsal-and-user-training.md)

## <a name="see-also"></a><span data-ttu-id="b4bdf-118">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="b4bdf-118">See also</span></span>

- [<span data-ttu-id="b4bdf-119">Enterprise-Geschäftskontinuität – Haftungsausschluss</span><span class="sxs-lookup"><span data-stu-id="b4bdf-119">Enterprise business continuity legal disclaimer</span></span>](ebcm-legal-disclaimer.md)
