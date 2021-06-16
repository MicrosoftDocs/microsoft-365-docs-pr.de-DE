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
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926559"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="22ef8-103">Zusätzliche Anforderungen an die Netzwerksicherheit für Office 365 GCC High und DOD</span><span class="sxs-lookup"><span data-stu-id="22ef8-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="22ef8-104">*Dieser Artikel bezieht sich auf Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High und Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="22ef8-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="22ef8-105">Office 365 GCC High und DOD sind sichere Cloudumgebungen, die den Anforderungen der US-Regierung und ihrer Lieferanten und Auftragnehmer entsprechen.</span><span class="sxs-lookup"><span data-stu-id="22ef8-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="22ef8-106">Diese Cloudumgebungen haben zusätzliche Netzwerkeinschränkungen, auf die externe Endpunkte zugreifen dürfen, auf die die Dienste zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="22ef8-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="22ef8-107">GCC High- und DOD-Kunden, die Verbundidentitäten oder hybride Koexistenz planen, erfordern möglicherweise, dass Microsoft eingehenden und/oder ausgehenden Zugriff auf Ihre vorhandenen lokalen Bereitstellungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="22ef8-107">GCC High and DOD customers planning to use federated identities or hybrid coexistence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="22ef8-108">Beispiele für diese Aktivitäten sind:</span><span class="sxs-lookup"><span data-stu-id="22ef8-108">Examples of these activities include:</span></span>

* <span data-ttu-id="22ef8-109">Verwendung von Verbundidentitäten (mit Active Directory-Verbunddiensten oder ähnlichen unterstützten STS)</span><span class="sxs-lookup"><span data-stu-id="22ef8-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="22ef8-110">Hybrid koexistenz mit einer lokalen Exchange Server oder Skype for Business Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="22ef8-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="22ef8-111">Migration vorhandener Benutzerinhalte aus einem lokalen System</span><span class="sxs-lookup"><span data-stu-id="22ef8-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="22ef8-112">Damit der Dienst mit Ihren lokalen Endpunkten kommunizieren kann, **müssen** Sie eine E-Mail an Office 365 Engineering für Netzwerkänderungen senden.</span><span class="sxs-lookup"><span data-stu-id="22ef8-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="22ef8-113">Alle Anforderungen verfügen über eine **dreiwöchige** SLA und können aufgrund der erforderlichen Sicherheits- und Compliance-Kontrollen und Bereitstellungspipelines nicht beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="22ef8-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="22ef8-114">Dies umfasst das anfängliche Onboarding von Netzwerkanforderungen sowie alle Änderungen nach der Migration zum Dienst.</span><span class="sxs-lookup"><span data-stu-id="22ef8-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="22ef8-115">Stellen Sie sicher, dass Ihre Netzwerkteams diese Zeitachse kennen, und fügen Sie sie in ihre Planungszyklen ein.</span><span class="sxs-lookup"><span data-stu-id="22ef8-115">Make sure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="22ef8-116">Senden Sie eine E-Mail mit den folgenden Informationen an [Office 365 Government Allow-List Anforderungen:](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="22ef8-116">Send an email to [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="22ef8-117">**To**: [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="22ef8-117">**To**: [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="22ef8-118">**From**: A tenant administrator – the send email **must** match a Global Administrator contact in your tenant</span><span class="sxs-lookup"><span data-stu-id="22ef8-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="22ef8-119">**E-Mail-Betreff:** Office 365 GCC High Network Request – contoso.onmicrosoft.us (ersetzen Sie durch Ihren Mandantennamen)</span><span class="sxs-lookup"><span data-stu-id="22ef8-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace with your tenant name)</span></span>

<span data-ttu-id="22ef8-120">Der Nachrichtentext sollte die folgenden Daten enthalten:</span><span class="sxs-lookup"><span data-stu-id="22ef8-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="22ef8-121">Ihr Microsoft Online Services-Mandantenname (z. B. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="22ef8-121">Your Microsoft Online Services tenant name (for example, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="22ef8-122">Eine E-Mail-Verteilerliste, mit der Microsoft für laufende Kommunikationen im Zusammenhang mit Netzwerkänderungen und/oder Nachverfolgung ungültiger Subnetze kommuniziert</span><span class="sxs-lookup"><span data-stu-id="22ef8-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="22ef8-123">Geben Sie an, ob Sie Microsoft Teams hybride Koexistenz mit Ihren lokalen Bereitstellungen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="22ef8-123">Indicate whether you plan to use Microsoft Teams hybrid coexistence with your on-premises deployments</span></span>
* <span data-ttu-id="22ef8-124">Url des Verbundidentitätssystems mit externem Zugriff (z. B. sts.contoso.com) und IP-Adressbereich in CIDR-Notation (z. B.</span><span class="sxs-lookup"><span data-stu-id="22ef8-124">Federated identity system externally accessible URL (for example, sts.contoso.com) and IP address range in CIDR notation (for example,.</span></span> <span data-ttu-id="22ef8-125">10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="22ef8-125">10.1.1.0/28)</span></span>
* <span data-ttu-id="22ef8-126">Url der lokalen PKI-Zertifikatsperrliste und IP-Adressbereich in CIDR-Notation</span><span class="sxs-lookup"><span data-stu-id="22ef8-126">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="22ef8-127">URL und IP-Adressbereich für Exchange Server lokale Bereitstellung in CIDR-Notation</span><span class="sxs-lookup"><span data-stu-id="22ef8-127">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="22ef8-128">URL und IP-Adressbereich für Skype for Business lokale Bereitstellung in CIDR-Notation</span><span class="sxs-lookup"><span data-stu-id="22ef8-128">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="22ef8-129">Beachten Sie aus Sicherheits- und Compliancegründen die folgenden Einschränkungen für Ihre Anforderung:</span><span class="sxs-lookup"><span data-stu-id="22ef8-129">For security and compliance reasons, keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="22ef8-130">Es gibt vier Subnetzeinschränkungen pro Mandant</span><span class="sxs-lookup"><span data-stu-id="22ef8-130">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="22ef8-131">Subnetze müssen sich in CIDR-Notation befinden (z. B. 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="22ef8-131">Subnets must be in CIDR Notation (for example, 10.1.1.0/28)</span></span>
* <span data-ttu-id="22ef8-132">Subnetzbereiche dürfen nicht größer als /24</span><span class="sxs-lookup"><span data-stu-id="22ef8-132">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="22ef8-133">Wir **können keine** Anforderungen erfüllen, um den Zugriff auf kommerzielle Clouddienste (kommerzielle Office 365, Google G-Suite, Amazon Web Services usw.) zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="22ef8-133">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="22ef8-134">Sobald Ihre Anforderung von Microsoft empfangen und genehmigt wurde, gibt es eine dreiwöchige SLA für die Implementierung und kann nicht beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="22ef8-134">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="22ef8-135">Sie erhalten eine anfängliche Bestätigung, wenn wir Ihre Anforderung erhalten haben, und eine endgültige Bestätigung, sobald sie abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="22ef8-135">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgment once it has been completed.</span></span>
