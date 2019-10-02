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
ms.openlocfilehash: d22763cede23d28c76a28c95a6e4772af81a996c
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369586"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="886e5-103">IT-Infrastruktur und geschäftliche Anforderungen von Contoso</span><span class="sxs-lookup"><span data-stu-id="886e5-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="886e5-104">**Zusammenfassung:** Informationen zur grundlegenden Struktur der lokalen IT-Infrastruktur von Contoso und wie die Unternehmensanforderungen mithilfe von Microsoft 365 Enterprise erfüllt wurden.</span><span class="sxs-lookup"><span data-stu-id="886e5-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="886e5-105">Contoso ist dabei, von der lokalen zentralen IT-Infrastruktur auf eine cloudeinschließende Infrastruktur umzustellen, die aus cloudbasierten persönlichen Produktivitätsarbeitslasten und Anwendungen besteht.</span><span class="sxs-lookup"><span data-stu-id="886e5-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="886e5-106">Contosos vorhandene IT-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="886e5-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="886e5-107">Contoso nutzt eine weitestgehend zentrale lokale IT-Infrastruktur mit Anwendungsrechenzentren in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="886e5-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="886e5-108">Abbildung 1 zeigt eine Unternehmenszentrale mit Anwendungsrechenzentren, einer DMZ und Internet.</span><span class="sxs-lookup"><span data-stu-id="886e5-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Contosos vorhandene IT-Infrastruktur](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="886e5-110">**Abbildung 1: Contosos vorhandene IT-Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="886e5-110">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="886e5-111">In den lokalen Anwendungsrechenzentren wird Folgendes gehostet:</span><span class="sxs-lookup"><span data-stu-id="886e5-111">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="886e5-112">Benutzerdefinierte Branchenanwendungen, die SQL Server und andere Linux-Datenbanken verwenden.</span><span class="sxs-lookup"><span data-stu-id="886e5-112">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="886e5-113">Eine Reihe von älteren SharePoint-Servern.</span><span class="sxs-lookup"><span data-stu-id="886e5-113">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="886e5-114">Server auf Organisations- und Teamebene für das Speichern von Dateien.</span><span class="sxs-lookup"><span data-stu-id="886e5-114">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="886e5-115">Darüber hinaus unterstützt jedes regionales Hub-Büro eine Reihe von Servern mit einer ähnlichen Gruppe von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="886e5-115">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span> <span data-ttu-id="886e5-116">Diese Server werden von regionalen IT-Abteilungen gesteuert.</span><span class="sxs-lookup"><span data-stu-id="886e5-116">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="886e5-117">Die Durchsuchbarkeit über die Anwendungen und Daten dieser separaten Rechenzentren an mehreren geografischen Standorten hinweg bleibt eine Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="886e5-117">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="886e5-118">In der DMZ am Hauptsitz von Contoso bieten verschiedene Servergruppen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="886e5-118">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="886e5-119">Hosting der öffentlichen Contoso-Website, über die Kunden Produkte, Teile, Zubehör oder Dienstleistungen bestellen können.</span><span class="sxs-lookup"><span data-stu-id="886e5-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="886e5-120">Hosting für das Contoso-Partnerextranet für die Kommunikation und Zusammenarbeit mit Partnern.</span><span class="sxs-lookup"><span data-stu-id="886e5-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="886e5-121">VPN-basierter Remotezugriff (virtuelles privates Netzwerk) auf das Contoso-Intranet und Webproxyfunktion für Mitarbeiter in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="886e5-121">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="886e5-122">Contosos Geschäftsanforderungen</span><span class="sxs-lookup"><span data-stu-id="886e5-122">Contoso's business needs</span></span>

<span data-ttu-id="886e5-123">Die Geschäftsanforderungen von Contoso können in fünf Hauptkategorien unterteilt werden.</span><span class="sxs-lookup"><span data-stu-id="886e5-123">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="886e5-124">Produktivität:</span><span class="sxs-lookup"><span data-stu-id="886e5-124">Productivity:</span></span>

- <span data-ttu-id="886e5-125">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="886e5-125">Make collaboration easier</span></span>

  <span data-ttu-id="886e5-126">Ersetzen Sie die auf E-Mails und Dateifreigaben basierte Zusammenarbeit durch ein Onlinemodell, das Echtzeitänderungen an Dokumenten, einfachere Onlinebesprechungen und erfasste Unterhaltungsthreads ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="886e5-126">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="886e5-127">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="886e5-127">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="886e5-128">Viele Mitarbeiter arbeiten von zu Hause aus oder unterwegs – ersetzen Sie daher die zu Engpässen führende VPN-Lösung durch leistungsstarken Zugriff auf Contoso-Daten und -Ressourcen in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="886e5-128">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="886e5-129">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="886e5-129">Increase creativity and innovation</span></span>

  <span data-ttu-id="886e5-130">Nutzen Sie die Vorteile der neuesten visuellen Lern- und Ideenfindungsmethoden, einschließlich Freihand und 3D-Visualisierung.</span><span class="sxs-lookup"><span data-stu-id="886e5-130">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="886e5-131">Sicherheit:</span><span class="sxs-lookup"><span data-stu-id="886e5-131">Security:</span></span>

- <span data-ttu-id="886e5-132">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="886e5-132">Identity and access management</span></span>

  <span data-ttu-id="886e5-133">Erzwingen Sie die mehrstufige Authentifizierung und andere Formen der Authentifizierung, und schützen Sie Anmeldeinformationen von Benutzer- und Administratorkonten.</span><span class="sxs-lookup"><span data-stu-id="886e5-133">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="886e5-134">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="886e5-134">Threat protection</span></span>

  <span data-ttu-id="886e5-135">Schutz vor externen Sicherheitsrisiken, einschließlich Schadsoftware, die auf E-Mails oder dem Betriebssystem basiert.</span><span class="sxs-lookup"><span data-stu-id="886e5-135">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="886e5-136">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="886e5-136">Information protection</span></span>

  <span data-ttu-id="886e5-137">Sperren Sie den Zugriff auf wichtige digitale Ressourcen, und verschlüsseln Sie diese (z. B. Kundendaten, Entwurfs- und Fertigungsspezifikationen und Mitarbeiterinformationen).</span><span class="sxs-lookup"><span data-stu-id="886e5-137">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="886e5-138">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="886e5-138">Security management</span></span>

  <span data-ttu-id="886e5-139">Überwachen des Sicherheitszustands und Ermitteln von sowie Reagieren auf Bedrohungen in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="886e5-139">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="886e5-140">Remote- und Mobilzugriff und Geschäftspartner:</span><span class="sxs-lookup"><span data-stu-id="886e5-140">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="886e5-141">Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="886e5-141">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="886e5-142">Führen Sie BYOD (Bring Your Own Device) und die Verwaltung von firmeneigenen Geräten ein, um einen sicheren Zugriff, ein korrektes Anwendungsverhalten sowie den Schutz von Unternehmensdaten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="886e5-142">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="886e5-143">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="886e5-143">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="886e5-144">Senken Sie die Wartungs- und Supportkosten, und verbessern Sie die Leistung für Remotezugriffslösungen, indem Sie Ressourcen, auf die häufig zugegriffen wird, in die Cloud verschieben.</span><span class="sxs-lookup"><span data-stu-id="886e5-144">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="886e5-145">Bessere Konnektivität und weniger Aufwand für Business-to-Business-Transaktionen (B2B)</span><span class="sxs-lookup"><span data-stu-id="886e5-145">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="886e5-146">Ersetzen Sie das in die Jahre gekommene Partnerextranet durch eine cloudbasierte Lösung, für die Verbundauthentifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="886e5-146">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="886e5-147">Compliance:</span><span class="sxs-lookup"><span data-stu-id="886e5-147">Compliance:</span></span>

- <span data-ttu-id="886e5-148">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="886e5-148">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="886e5-149">Halten Sie branchenübliche und regionale Vorschriften für Datenspeicherung, Verschlüsselung und Datenschutz sowie Vorschriften für personenbezogene Daten ein, z. B. die DSGVO für die Europäische Union.</span><span class="sxs-lookup"><span data-stu-id="886e5-149">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="886e5-150">Verwaltung:</span><span class="sxs-lookup"><span data-stu-id="886e5-150">Management:</span></span>

- <span data-ttu-id="886e5-151">Reduzieren des IT-Aufwands für die Verwaltung von Software, die auf Clientcomputern und -geräten ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="886e5-151">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="886e5-152">Automatisieren Sie die Installation von Updates auf dem Windows-Betriebssystem und in Microsoft Office ProPlus in der gesamten Organisation.</span><span class="sxs-lookup"><span data-stu-id="886e5-152">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="886e5-153">Zuordnen der Geschäftsanforderungen von Contoso zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="886e5-153">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="886e5-154">Von der IT-Abteilung von Contoso wurde vor der Bereitstellung die folgende Zuordnung von Geschäftsanforderungen zu den Features von Microsoft 365 Enterprise E5 vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="886e5-154">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="886e5-155">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="886e5-155">**Category**</span></span> | <span data-ttu-id="886e5-156">**Geschäftsanforderung**</span><span class="sxs-lookup"><span data-stu-id="886e5-156">**Business need**</span></span> | <span data-ttu-id="886e5-157">**Produkte oder Features von Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="886e5-157">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="886e5-158">Produktivität</span><span class="sxs-lookup"><span data-stu-id="886e5-158">Productivity</span></span> |  |  |
|  | <span data-ttu-id="886e5-159">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="886e5-159">Make collaboration easier</span></span> | <span data-ttu-id="886e5-160">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="886e5-160">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="886e5-161">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="886e5-161">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="886e5-162">Microsoft 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="886e5-162">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="886e5-163">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="886e5-163">Increase creativity and innovation</span></span> | <span data-ttu-id="886e5-164">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="886e5-164">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="886e5-165">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="886e5-165">Security</span></span> |  |  |
|  | <span data-ttu-id="886e5-166">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="886e5-166">Identity & access management</span></span> | <span data-ttu-id="886e5-167">Dedizierte globale Administratorkonten mit Azure Multi-Factor Authentication (MFA) und Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="886e5-167">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="886e5-168">Mehrstufige Authentifizierung (MFA) für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="886e5-168">MFA for all user accounts</span></span> <BR> <span data-ttu-id="886e5-169">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="886e5-169">Conditional access</span></span> <BR> <span data-ttu-id="886e5-170">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="886e5-170">Windows Hello</span></span> <BR> <span data-ttu-id="886e5-171">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="886e5-171">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="886e5-172">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="886e5-172">Threat protection</span></span> | <span data-ttu-id="886e5-173">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="886e5-173">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="886e5-174">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="886e5-174">Windows Defender</span></span> <BR> <span data-ttu-id="886e5-175">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="886e5-175">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="886e5-176">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="886e5-176">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="886e5-177">Untersuchung von und Antwort auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="886e5-177">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="886e5-178">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="886e5-178">Information protection</span></span> | <span data-ttu-id="886e5-179">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="886e5-179">Azure Information Protection</span></span> <BR> <span data-ttu-id="886e5-180">Verhinderung von Datenverlust in Office 365</span><span class="sxs-lookup"><span data-stu-id="886e5-180">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="886e5-181">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="886e5-181">Windows Information Protection DataRecoveryCertificate</span></span> <BR> <span data-ttu-id="886e5-182">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="886e5-182">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="886e5-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="886e5-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="886e5-184">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="886e5-184">Security management</span></span> | <span data-ttu-id="886e5-185">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="886e5-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="886e5-186">Windows Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="886e5-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="886e5-187">Remote- und Mobilzugriff und Geschäftspartner</span><span class="sxs-lookup"><span data-stu-id="886e5-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="886e5-188">Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="886e5-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="886e5-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="886e5-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="886e5-190">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="886e5-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="886e5-191">Microsoft 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="886e5-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="886e5-192">Bessere Konnektivität und weniger Aufwand für B2B-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="886e5-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="886e5-193">Verbundauthentifizierung und cloudbasierte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="886e5-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="886e5-194">Compliance</span><span class="sxs-lookup"><span data-stu-id="886e5-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="886e5-195">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="886e5-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="886e5-196">DSGVO-Features in Office 365</span><span class="sxs-lookup"><span data-stu-id="886e5-196">GDPR features in Office 365</span></span> |
| <span data-ttu-id="886e5-197">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="886e5-197">Management</span></span> |  |  |
|  | <span data-ttu-id="886e5-198">Reduzieren des IT-Aufwands für die Installation von Clientupdates</span><span class="sxs-lookup"><span data-stu-id="886e5-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="886e5-199">Bereitstellungsringe</span><span class="sxs-lookup"><span data-stu-id="886e5-199">Deployment rings</span></span> <BR> <span data-ttu-id="886e5-200">Windows 10 Enterprise-Updates</span><span class="sxs-lookup"><span data-stu-id="886e5-200">Windows 10 Enterprise</span></span> <BR> <span data-ttu-id="886e5-201">Office 365 ProPlus-Updates</span><span class="sxs-lookup"><span data-stu-id="886e5-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="886e5-202">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="886e5-202">Next step</span></span>

<span data-ttu-id="886e5-203">[Erfahren Sie mehr](contoso-networking.md) über das lokale Netzwerk von Contoso und wie dieses im Hinblick auf Zugriff und Latenz für cloudbasierte Microsoft 365-Ressourcen optimiert wurde.</span><span class="sxs-lookup"><span data-stu-id="886e5-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="886e5-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="886e5-204">See also</span></span>

[<span data-ttu-id="886e5-205">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="886e5-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="886e5-206">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="886e5-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
