---
title: Zusätzliche Netzwerksicherheitsanforderungen für Office 365 gcc High und DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Zusammenfassung: Office 365 gcc High und DoD bieten zusätzliche Netzwerksicherheitsanforderungen'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690575"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="5f957-103">Zusätzliche Netzwerksicherheitsanforderungen für Office 365 gcc High und DoD</span><span class="sxs-lookup"><span data-stu-id="5f957-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="5f957-104">*Dieser Artikel bezieht sich auf Office 365 gcc High, Office 365 DoD, Microsoft 365 gcc High und Microsoft 365 DoD.*</span><span class="sxs-lookup"><span data-stu-id="5f957-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="5f957-105">Office 365 gcc High und DoD sind sichere Cloud-Umgebungen, die den Anforderungen der US-Regierung und ihrer Zulieferer und Auftragnehmer gerecht werden.</span><span class="sxs-lookup"><span data-stu-id="5f957-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="5f957-106">Diese Cloud-Umgebungen weisen zusätzliche Netzwerkeinschränkungen auf, auf welche externen Endpunkten die Dienste zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="5f957-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="5f957-107">GCC High-und DoD-Kunden, die die Verwendung von Verbundidentitäten oder hybrider Koexistenz planen, erfordern möglicherweise, dass Microsoft eingehende und/oder ausgehende Zugriffe auf Ihre vorhandenen lokalen Bereitstellungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="5f957-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="5f957-108">Beispiele für diese Aktivitäten sind:</span><span class="sxs-lookup"><span data-stu-id="5f957-108">Examples of these activities include:</span></span>

* <span data-ttu-id="5f957-109">Verwendung von Verbundidentitäten (mit Active Directory Verbunddiensten oder ähnlichen unterstützten STS)</span><span class="sxs-lookup"><span data-stu-id="5f957-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="5f957-110">Hybride Koexistenz mit einer lokalen Exchange Server-oder Skype for Business-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="5f957-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="5f957-111">Migration vorhandener Benutzer Inhalte aus einem lokalen System</span><span class="sxs-lookup"><span data-stu-id="5f957-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="5f957-112">Wenn Sie zulassen möchten, dass der Dienst mit Ihren lokalen Endpunkten kommuniziert, **müssen** Sie eine e-Mail an Office 365 Engineering für Netzwerkänderungen senden.</span><span class="sxs-lookup"><span data-stu-id="5f957-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="5f957-113">Alle Anforderungen haben eine **dreiwöchige** SLA und können aufgrund der erforderlichen Sicherheits-und Konformitätskontrollen und Bereitstellungs Pipelines nicht beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="5f957-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="5f957-114">Dies umfasst die anfänglichen Onboarding-Netzwerkanforderungen sowie alle Änderungen, die nach dem Migrieren zu dem Dienst vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="5f957-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="5f957-115">Stellen Sie sicher, dass Ihre Netzwerkteams diese Zeitachse kennen und in Ihre Planungszyklen einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="5f957-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="5f957-116">Senden Sie eine e-Mail an [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) mit den folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="5f957-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="5f957-117">**An**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="5f957-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="5f957-118">**Von**: ein mandantenadministrator-die Sende-e-Mail **muss** mit einem globalen Administratorkontakt in Ihrem Mandanten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5f957-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="5f957-119">**E-Mail-Betreff**: Office 365 gcc High Network Request-contoso.onmicrosoft.US (ersetzen Sie dies durch ihren Mandantennamen)</span><span class="sxs-lookup"><span data-stu-id="5f957-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="5f957-120">Der Textkörper der Nachricht sollte die folgenden Daten enthalten:</span><span class="sxs-lookup"><span data-stu-id="5f957-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="5f957-121">Ihr Microsoft Online Services-Mandantenname (dh contoso.onmicrosoft.com, fabrikam.onmicrosoft.US)</span><span class="sxs-lookup"><span data-stu-id="5f957-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="5f957-122">Eine e-Mail-Verteilerliste, mit der Microsoft für die laufende Kommunikation im Zusammenhang mit Netzwerkänderungen und/oder der Nachverfolgung Ungültiger Subnetze kommuniziert</span><span class="sxs-lookup"><span data-stu-id="5f957-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="5f957-123">Geben Sie an, ob Sie Microsoft Teams Hybrid Koexistenz mit Ihren lokalen Bereitstellungen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5f957-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="5f957-124">Verbund Identitätssystem extern zugängliche URL (beispielsweise STS.contoso.com) und IP-Adressbereich in der CIDR-Notation (z.b. 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="5f957-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="5f957-125">Lokale PKI-Zertifikatsperrlisten-URL und IP-Adressbereich in der CIDR-Notation</span><span class="sxs-lookup"><span data-stu-id="5f957-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="5f957-126">Extern zugängliche URL und IP-Adressbereich für Exchange Server lokale Bereitstellung in der CIDR-Notation</span><span class="sxs-lookup"><span data-stu-id="5f957-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="5f957-127">Extern zugängliche URL und IP-Adressbereich für Skype for Business lokale Bereitstellung in der CIDR-Notation</span><span class="sxs-lookup"><span data-stu-id="5f957-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="5f957-128">Aus Sicherheits-und Kompatibilitätsgründen sollten Sie die folgenden Einschränkungen für Ihre Anforderung beachten:</span><span class="sxs-lookup"><span data-stu-id="5f957-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="5f957-129">Es gibt eine Begrenzung für vier Subnetze pro Mandanten.</span><span class="sxs-lookup"><span data-stu-id="5f957-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="5f957-130">Subnetze müssen sich in der CIDR-Notation befinden (z.b. 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="5f957-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="5f957-131">Subnetzbereiche dürfen nicht größer als/24 sein</span><span class="sxs-lookup"><span data-stu-id="5f957-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="5f957-132">Wir **können keine** Anfragen für den Zugriff auf kommerzielle Cloud-Dienste (kommerzielle Office 365, Google G-Suite, Amazon-Webdienste usw.) erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5f957-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="5f957-133">Nachdem Ihre Anfrage empfangen und von Microsoft genehmigt wurde, gibt es eine dreiwöchige SLA für die Implementierung und kann nicht beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="5f957-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="5f957-134">Sie erhalten eine erste Bestätigung, wenn wir Ihre Anfrage und eine abschließende Bestätigung erhalten haben, nachdem Sie abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="5f957-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
