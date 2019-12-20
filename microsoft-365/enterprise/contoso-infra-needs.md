---
title: IT-Infrastruktur und geschäftliche Anforderungen von Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zur grundlegenden Struktur der lokalen IT-Infrastruktur von Contoso und wie die Unternehmensanforderungen mithilfe von Microsoft 365 Enterprise erfüllt wurden.
ms.openlocfilehash: d98f401ae4a39e3e04b5840e8f76c1e3e1b1a24d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802070"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="cd7a5-103">IT-Infrastruktur und geschäftliche Anforderungen von Contoso</span><span class="sxs-lookup"><span data-stu-id="cd7a5-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="cd7a5-104">Contoso ist dabei, von der lokalen zentralen IT-Infrastruktur auf eine cloudeinschließende Infrastruktur umzustellen, die aus cloudbasierten persönlichen Produktivitätsarbeitslasten und Anwendungen besteht.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-104">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="cd7a5-105">Contosos vorhandene IT-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="cd7a5-105">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="cd7a5-106">Contoso nutzt eine weitestgehend zentrale lokale IT-Infrastruktur mit Anwendungsrechenzentren in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="cd7a5-107">Abbildung 1 zeigt eine Unternehmenszentrale mit Anwendungsrechenzentren, einer DMZ und Internet.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-107">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Contosos vorhandene IT-Infrastruktur](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="cd7a5-109">**Abbildung 1: Contosos vorhandene IT-Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="cd7a5-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="cd7a5-110">In den lokalen Anwendungsrechenzentren wird Folgendes gehostet:</span><span class="sxs-lookup"><span data-stu-id="cd7a5-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="cd7a5-111">Benutzerdefinierte Branchenanwendungen, die SQL Server und andere Linux-Datenbanken verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="cd7a5-112">Eine Reihe von älteren SharePoint-Servern.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="cd7a5-113">Server auf Organisations- und Teamebene für das Speichern von Dateien.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="cd7a5-114">Darüber hinaus unterstützt jedes regionales Hub-Büro eine Reihe von Servern mit einer ähnlichen Gruppe von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="cd7a5-115">Diese Server werden von regionalen IT-Abteilungen gesteuert.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="cd7a5-116">Die Durchsuchbarkeit über die Anwendungen und Daten dieser separaten Rechenzentren an mehreren geografischen Standorten hinweg bleibt eine Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="cd7a5-117">In der DMZ am Hauptsitz von Contoso bieten verschiedene Servergruppen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cd7a5-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="cd7a5-118">Hosting der öffentlichen Contoso-Website, über die Kunden Produkte, Teile, Zubehör oder Dienstleistungen bestellen können.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="cd7a5-119">Hosting für das Contoso-Partnerextranet für die Kommunikation und Zusammenarbeit mit Partnern.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="cd7a5-120">VPN-basierter Remotezugriff (virtuelles privates Netzwerk) auf das Contoso-Intranet und Webproxyfunktion für Mitarbeiter in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="cd7a5-121">Contosos Geschäftsanforderungen</span><span class="sxs-lookup"><span data-stu-id="cd7a5-121">Contoso's business needs</span></span>

<span data-ttu-id="cd7a5-122">Die Geschäftsanforderungen von Contoso können in fünf Hauptkategorien unterteilt werden.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="cd7a5-123">Produktivität:</span><span class="sxs-lookup"><span data-stu-id="cd7a5-123">Productivity:</span></span>

- <span data-ttu-id="cd7a5-124">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="cd7a5-124">Make collaboration easier</span></span>

  <span data-ttu-id="cd7a5-125">Ersetzen Sie die auf E-Mails und Dateifreigaben basierte Zusammenarbeit durch ein Onlinemodell, das Echtzeitänderungen an Dokumenten, einfachere Onlinebesprechungen und erfasste Unterhaltungsthreads ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="cd7a5-126">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="cd7a5-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="cd7a5-127">Viele Mitarbeiter arbeiten von zu Hause aus oder unterwegs – ersetzen Sie daher die zu Engpässen führende VPN-Lösung durch leistungsstarken Zugriff auf Contoso-Daten und -Ressourcen in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="cd7a5-128">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="cd7a5-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="cd7a5-129">Nutzen Sie die Vorteile der neuesten visuellen Lern- und Ideenfindungsmethoden, einschließlich Freihand und 3D-Visualisierung.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="cd7a5-130">Sicherheit:</span><span class="sxs-lookup"><span data-stu-id="cd7a5-130">Security:</span></span>

- <span data-ttu-id="cd7a5-131">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="cd7a5-131">Identity and access management</span></span>

  <span data-ttu-id="cd7a5-132">Erzwingen Sie die mehrstufige Authentifizierung und andere Formen der Authentifizierung, und schützen Sie Anmeldeinformationen von Benutzer- und Administratorkonten.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="cd7a5-133">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="cd7a5-133">Threat protection</span></span>

  <span data-ttu-id="cd7a5-134">Schutz vor externen Sicherheitsrisiken, einschließlich Schadsoftware, die auf E-Mails oder dem Betriebssystem basiert.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="cd7a5-135">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="cd7a5-135">Information protection</span></span>

  <span data-ttu-id="cd7a5-136">Sperren Sie den Zugriff auf wichtige digitale Ressourcen, und verschlüsseln Sie diese (z. B. Kundendaten, Entwurfs- und Fertigungsspezifikationen und Mitarbeiterinformationen).</span><span class="sxs-lookup"><span data-stu-id="cd7a5-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="cd7a5-137">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="cd7a5-137">Security management</span></span>

  <span data-ttu-id="cd7a5-138">Überwachen des Sicherheitszustands und Ermitteln von sowie Reagieren auf Bedrohungen in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="cd7a5-139">Remote- und Mobilzugriff und Geschäftspartner:</span><span class="sxs-lookup"><span data-stu-id="cd7a5-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="cd7a5-140">Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="cd7a5-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="cd7a5-141">Führen Sie BYOD (Bring Your Own Device) und die Verwaltung von firmeneigenen Geräten ein, um einen sicheren Zugriff, ein korrektes Anwendungsverhalten sowie den Schutz von Unternehmensdaten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="cd7a5-142">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="cd7a5-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="cd7a5-143">Senken Sie die Wartungs- und Supportkosten, und verbessern Sie die Leistung für Remotezugriffslösungen, indem Sie Ressourcen, auf die häufig zugegriffen wird, in die Cloud verschieben.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly-accessed resources to the cloud.</span></span>

- <span data-ttu-id="cd7a5-144">Bessere Konnektivität und weniger Aufwand für Business-to-Business-Transaktionen (B2B)</span><span class="sxs-lookup"><span data-stu-id="cd7a5-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="cd7a5-145">Ersetzen Sie das in die Jahre gekommene Partnerextranet durch eine cloudbasierte Lösung, für die Verbundauthentifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="cd7a5-146">Compliance:</span><span class="sxs-lookup"><span data-stu-id="cd7a5-146">Compliance:</span></span>

- <span data-ttu-id="cd7a5-147">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="cd7a5-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="cd7a5-148">Halten Sie branchenübliche und regionale Vorschriften für Datenspeicherung, Verschlüsselung und Datenschutz sowie Vorschriften für personenbezogene Daten ein, z. B. die DSGVO für die Europäische Union.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="cd7a5-149">Verwaltung:</span><span class="sxs-lookup"><span data-stu-id="cd7a5-149">Management:</span></span>

- <span data-ttu-id="cd7a5-150">Reduzieren des IT-Aufwands für die Verwaltung von Software, die auf Clientcomputern und -geräten ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="cd7a5-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="cd7a5-151">Automatisieren Sie die Installation von Updates auf dem Windows-Betriebssystem und in Microsoft Office ProPlus in der gesamten Organisation.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-151">Automate the installation of updates to the Windows operating system and Microsoft Office ProPlus across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="cd7a5-152">Zuordnen der Geschäftsanforderungen von Contoso zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cd7a5-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="cd7a5-153">Von der IT-Abteilung von Contoso wurde vor der Bereitstellung die folgende Zuordnung von Geschäftsanforderungen zu den Features von Microsoft 365 E5 vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="cd7a5-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="cd7a5-154">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="cd7a5-154">**Category**</span></span> | <span data-ttu-id="cd7a5-155">**Geschäftsanforderung**</span><span class="sxs-lookup"><span data-stu-id="cd7a5-155">**Business need**</span></span> | <span data-ttu-id="cd7a5-156">**Produkte oder Features von Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="cd7a5-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="cd7a5-157">Produktivität</span><span class="sxs-lookup"><span data-stu-id="cd7a5-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="cd7a5-158">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="cd7a5-158">Make collaboration easier</span></span> | <span data-ttu-id="cd7a5-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="cd7a5-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="cd7a5-160">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="cd7a5-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="cd7a5-161">Microsoft 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="cd7a5-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="cd7a5-162">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="cd7a5-162">Increase creativity and innovation</span></span> | <span data-ttu-id="cd7a5-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cd7a5-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="cd7a5-164">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cd7a5-164">Security</span></span> |  |  |
|  | <span data-ttu-id="cd7a5-165">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="cd7a5-165">Identity & access management</span></span> | <span data-ttu-id="cd7a5-166">Dedizierte globale Administratorkonten mit Azure Multi-Factor Authentication (MFA) und Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="cd7a5-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="cd7a5-167">Mehrstufige Authentifizierung (MFA) für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="cd7a5-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="cd7a5-168">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="cd7a5-168">Conditional Access</span></span> <BR> <span data-ttu-id="cd7a5-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="cd7a5-169">Windows Hello</span></span> <BR> <span data-ttu-id="cd7a5-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="cd7a5-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="cd7a5-171">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="cd7a5-171">Threat protection</span></span> | <span data-ttu-id="cd7a5-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="cd7a5-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="cd7a5-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="cd7a5-173">Windows Defender</span></span> <BR> <span data-ttu-id="cd7a5-174">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cd7a5-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="cd7a5-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cd7a5-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="cd7a5-176">Untersuchung von und Antwort auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="cd7a5-176">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="cd7a5-177">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="cd7a5-177">Information protection</span></span> | <span data-ttu-id="cd7a5-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="cd7a5-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="cd7a5-179">Verhinderung von Datenverlust in Office 365</span><span class="sxs-lookup"><span data-stu-id="cd7a5-179">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="cd7a5-180">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="cd7a5-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="cd7a5-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cd7a5-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="cd7a5-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cd7a5-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="cd7a5-183">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="cd7a5-183">Security management</span></span> | <span data-ttu-id="cd7a5-184">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="cd7a5-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="cd7a5-185">Windows Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="cd7a5-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="cd7a5-186">Remote- und Mobilzugriff und Geschäftspartner</span><span class="sxs-lookup"><span data-stu-id="cd7a5-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="cd7a5-187">Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="cd7a5-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="cd7a5-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cd7a5-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="cd7a5-189">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="cd7a5-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="cd7a5-190">Microsoft 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="cd7a5-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="cd7a5-191">Bessere Konnektivität und weniger Aufwand für B2B-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="cd7a5-191">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="cd7a5-192">Verbundauthentifizierung und cloudbasierte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="cd7a5-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="cd7a5-193">Compliance</span><span class="sxs-lookup"><span data-stu-id="cd7a5-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="cd7a5-194">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="cd7a5-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="cd7a5-195">DSGVO-Features in Office 365</span><span class="sxs-lookup"><span data-stu-id="cd7a5-195">GDPR features in Office 365</span></span> |
| <span data-ttu-id="cd7a5-196">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="cd7a5-196">Management</span></span> |  |  |
|  | <span data-ttu-id="cd7a5-197">Reduzieren des IT-Aufwands für die Installation von Clientupdates</span><span class="sxs-lookup"><span data-stu-id="cd7a5-197">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="cd7a5-198">Bereitstellungsringe</span><span class="sxs-lookup"><span data-stu-id="cd7a5-198">Deployment rings</span></span> <BR> <span data-ttu-id="cd7a5-199">Windows 10 Enterprise-Updates</span><span class="sxs-lookup"><span data-stu-id="cd7a5-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="cd7a5-200">Office 365 ProPlus-Updates</span><span class="sxs-lookup"><span data-stu-id="cd7a5-200">Office 365 ProPlus updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="cd7a5-201">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="cd7a5-201">Next step</span></span>

<span data-ttu-id="cd7a5-202">[Erfahren Sie mehr](contoso-networking.md) über das lokale Netzwerk von Contoso und wie dieses im Hinblick auf Zugriff und Latenz für cloudbasierte Microsoft 365-Ressourcen optimiert wurde.</span><span class="sxs-lookup"><span data-stu-id="cd7a5-202">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd7a5-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd7a5-203">See also</span></span>

[<span data-ttu-id="cd7a5-204">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="cd7a5-204">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cd7a5-205">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="cd7a5-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
