---
title: Zusätzliche Netzwerksicherheitsanforderungen für Office 365 GCC High und DoD
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
description: 'Zusammenfassung: Office 365 GCC High und DoD haben zusätzliche Netzwerksicherheitsanforderungen'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690575"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="312b1-103">Zusätzliche Anforderungen an die Netzwerksicherheit für Office 365 GCC High und DOD</span><span class="sxs-lookup"><span data-stu-id="312b1-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="312b1-104">*Dieser Artikel gilt für Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High und Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="312b1-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="312b1-105">Office 365 GCC High und DOD sind sichere Cloudumgebungen, die den Anforderungen der US-Regierung und ihrer Lieferanten und Auftragnehmer entsprechen.</span><span class="sxs-lookup"><span data-stu-id="312b1-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="312b1-106">Diese Cloudumgebungen verfügen über zusätzliche Netzwerkeinschränkungen, auf die externe Endpunkte zugreifen dürfen, auf die die Dienste zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="312b1-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="312b1-107">GCC Kunden mit hoher Und-DoD-Anzahl, die Verbundidentitäten oder hybride Koexistenz verwenden möchten, müssen möglicherweise von Microsoft eingehenden und/oder ausgehenden Zugriff auf Ihre vorhandenen lokalen Bereitstellungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="312b1-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="312b1-108">Beispiele für diese Aktivitäten sind:</span><span class="sxs-lookup"><span data-stu-id="312b1-108">Examples of these activities include:</span></span>

* <span data-ttu-id="312b1-109">Verwendung von Verbundidentitäten (mit Active Directory Federation Services oder ähnlichen unterstützten STS)</span><span class="sxs-lookup"><span data-stu-id="312b1-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="312b1-110">Hybride Koexistenz mit einer lokalen Exchange Server oder Skype for Business Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="312b1-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="312b1-111">Migration vorhandener Benutzerinhalte aus einem lokalen System</span><span class="sxs-lookup"><span data-stu-id="312b1-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="312b1-112">Damit der Dienst mit Ihren lokalen Endpunkten  kommunizieren kann, müssen Sie eine E-Mail an Office 365 für Netzwerkänderungen senden.</span><span class="sxs-lookup"><span data-stu-id="312b1-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="312b1-113">Alle Anforderungen verfügen über eine SLA **von** drei Wochen und können aufgrund der erforderlichen Sicherheits- und Compliancekontrollen und Bereitstellungspipelines nicht beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="312b1-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="312b1-114">Dies umfasst anfängliche Onboardingnetzwerkanforderungen sowie alle Änderungen nach der Migration zum Dienst.</span><span class="sxs-lookup"><span data-stu-id="312b1-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="312b1-115">Stellen Sie sicher, dass Ihre Netzwerkteams diese Zeitachse kennen und in ihre Planungszyklen einfügen.</span><span class="sxs-lookup"><span data-stu-id="312b1-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="312b1-116">Senden Sie eine E-Mail [an Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) mit den folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="312b1-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="312b1-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="312b1-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="312b1-118">**From**: A tenant administrator – the send email **must match** a Global Administrator contact in your tenant</span><span class="sxs-lookup"><span data-stu-id="312b1-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="312b1-119">**E-Mail-Betreff**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (ersetzen Sie dies durch Ihren Mandantennamen)</span><span class="sxs-lookup"><span data-stu-id="312b1-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="312b1-120">Der Nachrichtentext sollte die folgenden Daten enthalten:</span><span class="sxs-lookup"><span data-stu-id="312b1-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="312b1-121">Ihr Microsoft Online Services Mandantenname (d. h. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="312b1-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="312b1-122">Eine E-Mail-Verteilerliste, mit der Microsoft für die aktuelle Kommunikation im Zusammenhang mit Netzwerkänderungen und/oder der Nachverteiler für ungültige Subnetze kommuniziert</span><span class="sxs-lookup"><span data-stu-id="312b1-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="312b1-123">Geben Sie an, ob Sie Microsoft Teams hybride Koexistenz mit Ihren lokalen Bereitstellungen verwenden möchten</span><span class="sxs-lookup"><span data-stu-id="312b1-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="312b1-124">Extern zugängliche URL des Verbundidentitätssystems (z. B. sts.contoso.com) und IP-Adressbereich in CIDR-Notation (z. B. 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="312b1-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="312b1-125">Lokale PKI-Zertifikatsperrlisten-URL und IP-Adressbereich in CIDR-Notation</span><span class="sxs-lookup"><span data-stu-id="312b1-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="312b1-126">Extern zugänglicher URL- und IP-Adressbereich für Exchange Server lokale Bereitstellung in CIDR-Notation</span><span class="sxs-lookup"><span data-stu-id="312b1-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="312b1-127">Extern zugänglicher URL- und IP-Adressbereich für Skype for Business lokale Bereitstellung in CIDR-Notation</span><span class="sxs-lookup"><span data-stu-id="312b1-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="312b1-128">Beachten Sie aus Sicherheits- und Compliancegründen die folgenden Einschränkungen für Ihre Anforderung:</span><span class="sxs-lookup"><span data-stu-id="312b1-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="312b1-129">Es gibt eine Vier-Subnetz-Beschränkung pro Mandant</span><span class="sxs-lookup"><span data-stu-id="312b1-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="312b1-130">Subnetze müssen sich in CIDR Notation befinden (z. B. 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="312b1-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="312b1-131">Subnetzbereiche dürfen nicht größer als /24</span><span class="sxs-lookup"><span data-stu-id="312b1-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="312b1-132">Wir **können Anforderungen** zum Zulassen des Zugriffs auf kommerzielle Clouddienste (kommerzielle Office 365, Google G-Suite, Amazon Web Services usw.) nicht erfüllen.</span><span class="sxs-lookup"><span data-stu-id="312b1-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="312b1-133">Sobald Ihre Anforderung von Microsoft empfangen und genehmigt wurde, gibt es eine dreiwöchige SLA für die Implementierung und kann nicht beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="312b1-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="312b1-134">Sie erhalten eine erste Bestätigung, wenn wir Ihre Anforderung erhalten haben, und eine endgültige Bestätigung, nachdem sie abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="312b1-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
