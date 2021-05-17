---
title: Contoso IT-Infrastruktur und Geschäftsanforderungen
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Grundlegende Informationen zur grundlegenden Struktur der lokalen Contoso-IT-Infrastruktur und dazu, wie die geschäftlichen Anforderungen des Unternehmens von unternehmen Microsoft 365 erfüllt werden.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558406"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="154fb-103">Contoso IT-Infrastruktur und Geschäftsanforderungen</span><span class="sxs-lookup"><span data-stu-id="154fb-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="154fb-104">Contoso wandelt von einer lokalen, zentralisierten IT-Infrastruktur zu einem cloud-inklusiven Setup um, das cloudbasierte Arbeitsauslastungen und Anwendungen für persönliche Produktivität umfasst.</span><span class="sxs-lookup"><span data-stu-id="154fb-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="154fb-105">Vorhandene Contoso-IT-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="154fb-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="154fb-106">Contoso nutzt eine weitestgehend zentrale lokale IT-Infrastruktur mit Anwendungsrechenzentren in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="154fb-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="154fb-107">Hier ist die Zentrale mit Anwendungsdatencentern, einer DMZ und dem Internet.</span><span class="sxs-lookup"><span data-stu-id="154fb-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Vorhandene Contoso-IT-Infrastruktur](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="154fb-109">In den lokalen Anwendungsrechenzentren wird Folgendes gehostet:</span><span class="sxs-lookup"><span data-stu-id="154fb-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="154fb-110">Benutzerdefinierte Geschäftsanwendungen, die SQL Server und andere Linux-Datenbanken verwenden.</span><span class="sxs-lookup"><span data-stu-id="154fb-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="154fb-111">Eine Reihe von älteren SharePoint-Servern.</span><span class="sxs-lookup"><span data-stu-id="154fb-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="154fb-112">Server auf Organisations- und Teamebene für das Speichern von Dateien.</span><span class="sxs-lookup"><span data-stu-id="154fb-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="154fb-113">Darüber hinaus unterstützt jedes regionales Hub-Büro eine Reihe von Servern mit einer ähnlichen Gruppe von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="154fb-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="154fb-114">Diese Server werden von regionalen IT-Abteilungen gesteuert.</span><span class="sxs-lookup"><span data-stu-id="154fb-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="154fb-115">Die Durchsuchbarkeit über die Anwendungen und Daten dieser separaten Rechenzentren an mehreren geografischen Standorten hinweg bleibt eine Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="154fb-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="154fb-116">In der Contoso-Zentrale DMZ bieten verschiedene Servergruppen:</span><span class="sxs-lookup"><span data-stu-id="154fb-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="154fb-117">Hosting für die öffentliche Contoso-Website, auf der Kunden Produkte, Teile, Lieferungen und Dienste bestellen können.</span><span class="sxs-lookup"><span data-stu-id="154fb-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="154fb-118">Hosting für das Contoso-Partnerextranet für die Kommunikation und Zusammenarbeit mit Partnern.</span><span class="sxs-lookup"><span data-stu-id="154fb-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="154fb-119">VPN-basierter Remotezugriff (virtuelles privates Netzwerk) auf das Contoso-Intranet und Webproxyfunktion für Mitarbeiter in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="154fb-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="154fb-120">Contoso-Geschäftsanforderungen</span><span class="sxs-lookup"><span data-stu-id="154fb-120">Contoso business needs</span></span>

<span data-ttu-id="154fb-121">Die Unternehmensanforderungen von Contoso sind in fünf Hauptkategorien unterteilt:</span><span class="sxs-lookup"><span data-stu-id="154fb-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="154fb-122">**Produktivität**</span><span class="sxs-lookup"><span data-stu-id="154fb-122">**Productivity**</span></span>

- <span data-ttu-id="154fb-123">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="154fb-123">Make collaboration easier</span></span>

  <span data-ttu-id="154fb-124">Ersetzen Sie die E-Mail- und Dateifreigabe-basierte Zusammenarbeit durch ein Onlinemodell, das Echtzeitänderungen an Dokumenten, einfachere Onlinebesprechungen und aufgezeichnete Unterhaltungsthreads ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="154fb-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="154fb-125">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="154fb-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="154fb-126">Da viele Mitarbeiter von zu Hause oder in der Umgebung arbeiten, ersetzen Sie die eng engpässe VPN-Lösung durch einen performanten Zugriff auf Contoso-Daten und -Ressourcen in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="154fb-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="154fb-127">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="154fb-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="154fb-128">Nutzen Sie die Vorteile der neuesten visuellen Lern- und Ideenfindungsmethoden, einschließlich Freihand und 3D-Visualisierung.</span><span class="sxs-lookup"><span data-stu-id="154fb-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="154fb-129">**Sicherheit**</span><span class="sxs-lookup"><span data-stu-id="154fb-129">**Security**</span></span>

- <span data-ttu-id="154fb-130">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="154fb-130">Identity and access management</span></span>

  <span data-ttu-id="154fb-131">Erzwingen Sie mehrstufige und andere Authentifizierungsmethoden, und schützen Sie Die Anmeldeinformationen für Benutzer- und Administratorkonten.</span><span class="sxs-lookup"><span data-stu-id="154fb-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="154fb-132">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="154fb-132">Threat protection</span></span>

  <span data-ttu-id="154fb-133">Schutz vor externen Sicherheitsrisiken, einschließlich Schadsoftware, die auf E-Mails oder dem Betriebssystem basiert.</span><span class="sxs-lookup"><span data-stu-id="154fb-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="154fb-134">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="154fb-134">Information protection</span></span>

  <span data-ttu-id="154fb-135">Sperren Sie den Zugriff auf wichtige digitale Ressourcen, und verschlüsseln Sie diese (z. B. Kundendaten, Entwurfs- und Fertigungsspezifikationen und Mitarbeiterinformationen).</span><span class="sxs-lookup"><span data-stu-id="154fb-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="154fb-136">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="154fb-136">Security management</span></span>

  <span data-ttu-id="154fb-137">Überwachen Sie die Sicherheitslage, erkennen und reagieren Sie auf Bedrohungen in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="154fb-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="154fb-138">**Remote- und Mobilzugriff und Geschäftspartner**</span><span class="sxs-lookup"><span data-stu-id="154fb-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="154fb-139">Verbessern der Sicherheit für Remote- und mobile Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="154fb-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="154fb-140">Implementieren Sie bring your own device (BYOD) and company-owned device management, um sicheren Zugriff, korrektes Anwendungsverhalten und Unternehmensdatenschutz sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="154fb-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="154fb-141">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="154fb-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="154fb-142">Reduzieren Sie Wartungs- und Supportkosten, und verbessern Sie die Leistung der Remotezugriffslösung, indem Sie häufig verwendete Ressourcen in die Cloud verschieben.</span><span class="sxs-lookup"><span data-stu-id="154fb-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="154fb-143">Bessere Konnektivität und geringerer Aufwand für Business-to-Susiness (B2B)-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="154fb-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="154fb-144">Ersetzen Sie ein veraltetes und teures Partner-Extranet durch eine cloudbasierte Lösung, die die Verbundauthentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="154fb-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="154fb-145">**Compliance**</span><span class="sxs-lookup"><span data-stu-id="154fb-145">**Compliance**</span></span>

- <span data-ttu-id="154fb-146">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="154fb-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="154fb-147">Sicherstellen der Einhaltung der branchen- und regionalen Vorschriften für Datenspeicherung, Verschlüsselung, Datenschutz und personenbezogene Daten, wie z. B. die DSGVO für die Europäische Union.</span><span class="sxs-lookup"><span data-stu-id="154fb-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="154fb-148">**Verwaltung**</span><span class="sxs-lookup"><span data-stu-id="154fb-148">**Management**</span></span>

- <span data-ttu-id="154fb-149">Geringerer IT-Aufwand für die Verwaltung von Software, die auf Client-PCs und -Geräten ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="154fb-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="154fb-150">Automatisieren Sie die Installation von Updates Windows Betriebssystem und Microsoft 365 Apps for Enterprise in der gesamten Organisation.</span><span class="sxs-lookup"><span data-stu-id="154fb-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="154fb-151">Zuordnung von Contoso-Unternehmen muss Microsoft 365 unternehmen</span><span class="sxs-lookup"><span data-stu-id="154fb-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="154fb-152">Die Contoso-IT-Abteilung hat die folgende Zuordnung der Geschäftsanforderungen für Microsoft 365 E5 vor der Bereitstellung bestimmt:</span><span class="sxs-lookup"><span data-stu-id="154fb-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="154fb-153">Kategorie</span><span class="sxs-lookup"><span data-stu-id="154fb-153">Category</span></span> | <span data-ttu-id="154fb-154">Geschäftsanforderung</span><span class="sxs-lookup"><span data-stu-id="154fb-154">Business need</span></span> | <span data-ttu-id="154fb-155">Microsoft 365 für Enterprise-Produkte oder -Features</span><span class="sxs-lookup"><span data-stu-id="154fb-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="154fb-156">Produktivität</span><span class="sxs-lookup"><span data-stu-id="154fb-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="154fb-157">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="154fb-157">Make collaboration easier</span></span> | <span data-ttu-id="154fb-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="154fb-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="154fb-159">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="154fb-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="154fb-160">Microsoft 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="154fb-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="154fb-161">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="154fb-161">Increase creativity and innovation</span></span> | <span data-ttu-id="154fb-162">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="154fb-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="154fb-163">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="154fb-163">Security</span></span> |  |  |
|  | <span data-ttu-id="154fb-164">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="154fb-164">Identity & access management</span></span> | <span data-ttu-id="154fb-165">Dedizierte globale Administratorkonten mit Azure AD Multi-Factor Authentication (MFA) und Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="154fb-165">Dedicated global administrator accounts with Azure AD Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="154fb-166">Mehrstufige Authentifizierung (MFA) für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="154fb-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="154fb-167">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="154fb-167">Conditional Access</span></span> <BR> <span data-ttu-id="154fb-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="154fb-168">Windows Hello</span></span> <BR> <span data-ttu-id="154fb-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="154fb-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="154fb-170">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="154fb-170">Threat protection</span></span> | <span data-ttu-id="154fb-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="154fb-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="154fb-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="154fb-172">Windows Defender</span></span> <BR> <span data-ttu-id="154fb-173">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="154fb-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="154fb-174">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="154fb-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="154fb-175">Microsoft 365 und Reaktion auf Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="154fb-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="154fb-176">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="154fb-176">Information protection</span></span> | <span data-ttu-id="154fb-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="154fb-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="154fb-178">Verhinderung von Datenverlust (Data Loss Prevention, DLP)</span><span class="sxs-lookup"><span data-stu-id="154fb-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="154fb-179">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="154fb-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="154fb-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="154fb-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="154fb-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="154fb-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="154fb-182">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="154fb-182">Security management</span></span> | <span data-ttu-id="154fb-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="154fb-183">Azure Defender</span></span>  <BR> <span data-ttu-id="154fb-184">Windows Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="154fb-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="154fb-185">Remote- und Mobilzugriff und Geschäftspartner</span><span class="sxs-lookup"><span data-stu-id="154fb-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="154fb-186">Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="154fb-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="154fb-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="154fb-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="154fb-188">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="154fb-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="154fb-189">Microsoft 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="154fb-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="154fb-190">Verbessern der Konnektivität und geringerer Aufwand für B2B-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="154fb-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="154fb-191">Verbundauthentifizierung und cloudbasierte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="154fb-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="154fb-192">Compliance</span><span class="sxs-lookup"><span data-stu-id="154fb-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="154fb-193">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="154fb-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="154fb-194">DSGVO-Features in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="154fb-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="154fb-195">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="154fb-195">Management</span></span> |  |  |
|  | <span data-ttu-id="154fb-196">Geringerer IT-Aufwand für die Installation von Clientupdates</span><span class="sxs-lookup"><span data-stu-id="154fb-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="154fb-197">Windows 10 Enterprise-Updates</span><span class="sxs-lookup"><span data-stu-id="154fb-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="154fb-198">Microsoft 365 Apps for Enterprise-Updates</span><span class="sxs-lookup"><span data-stu-id="154fb-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="154fb-199">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="154fb-199">Next step</span></span>

<span data-ttu-id="154fb-200">Erfahren Sie mehr über das lokale Netzwerk der Contoso [Corporation](contoso-networking.md) und darüber, wie es für den Zugriff und die Wartezeit auf Microsoft 365 cloudbasierten Ressourcen optimiert wurde.</span><span class="sxs-lookup"><span data-stu-id="154fb-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="154fb-201">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="154fb-201">See also</span></span>

[<span data-ttu-id="154fb-202">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="154fb-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="154fb-203">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="154fb-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
