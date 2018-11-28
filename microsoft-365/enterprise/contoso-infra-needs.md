---
title: IT-Infrastruktur und geschäftliche Anforderungen von Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zur grundlegenden Struktur der lokalen IT-Infrastruktur von Contoso und wie die Unternehmensanforderungen mithilfe von Microsoft 365 Enterprise erfüllt werden können.
ms.openlocfilehash: 995944e52258ad4890bc5d964b59975e81e315e1
ms.sourcegitcommit: 91c1b45cff441f194ebac670aaf1feb77a1409ee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "23978005"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="fe9ab-103">IT-Infrastruktur und geschäftliche Anforderungen von Contoso</span><span class="sxs-lookup"><span data-stu-id="fe9ab-103">Contoso's IT infrastructure and needs</span></span>

<span data-ttu-id="fe9ab-104">**Zusammenfassung:** Informationen zur grundlegenden Struktur der lokalen IT-Infrastruktur von Contoso und wie die Unternehmensanforderungen mithilfe von Microsoft 365 Enterprise erfüllt werden können.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-104">**Summary:**  Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft's cloud offerings.</span></span>


<span data-ttu-id="fe9ab-105">Contoso ist dabei, von der lokalen zentralen IT-Infrastruktur auf eine cloudeinschließende Infrastruktur umzustellen, die aus cloudbasierten persönlichen Produktivitätsarbeitslasten und Anwendungen besteht.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-105">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads, applications, and hybrid scenarios.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="fe9ab-106">Contosos vorhandene IT-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="fe9ab-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="fe9ab-107">Contoso nutzt eine weitestgehend zentrale lokale IT-Infrastruktur mit Anwendungsrechenzentren in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="fe9ab-108">Abbildung 1 zeigt eine Unternehmenszentrale mit Anwendungsrechenzentren, einer DMZ und Internet.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="fe9ab-109">**Abbildung 1: Contosos vorhandene IT-Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="fe9ab-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="fe9ab-110">In den lokalen Anwendungsrechenzentren wird Folgendes gehostet:</span><span class="sxs-lookup"><span data-stu-id="fe9ab-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="fe9ab-111">Benutzerdefinierte Branchenanwendungen, die SQL Server und andere Linux-Datenbanken verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="fe9ab-112">Eine Reihe von älteren SharePoint-Servern.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="fe9ab-113">Server auf Organisations- und Teamebene für das Speichern von Dateien.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="fe9ab-p101">Darüber hinaus jedes regionales Hub-Büro, das eine Reihe von Servern mit einer ähnlichen Gruppe von Anwendungen unterstützt. Diese Server werden von regionalen IT-Abteilungen gesteuert.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-p101">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="fe9ab-116">Die Durchsuchbarkeit über die Anwendungen und Daten dieser separaten Rechenzentren an mehreren geografischen Standorten hinweg bleibt eine Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="fe9ab-117">In der DMZ am Hauptsitz von Contoso bieten verschiedene Servergruppen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fe9ab-117">In Contoso’s DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="fe9ab-118">VPN-basierter Remotezugriff auf das Contoso-Intranet und Webproxyfunktion für Mitarbeiter in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-118">Remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>
- <span data-ttu-id="fe9ab-119">Hosting der öffentlichen Contoso-Website, über die Kunden Produkte, Teile, Zubehör oder Dienstleistungen bestellen können.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-119">Hosting for the Contoso public web site, from which customers can order products, parts, or supplies.</span></span>
- <span data-ttu-id="fe9ab-120">Hosting für das Contoso-Partnerextranet für die Kommunikation und Zusammenarbeit mit Partnern.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="fe9ab-121">Contosos Geschäftsanforderungen</span><span class="sxs-lookup"><span data-stu-id="fe9ab-121">Contoso’s business needs</span></span>

<span data-ttu-id="fe9ab-122">Die Geschäftsanforderungen von Contoso können in fünf Hauptkategorien unterteilt werden.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="fe9ab-123">Produktivität:</span><span class="sxs-lookup"><span data-stu-id="fe9ab-123">Productivity</span></span>

- <span data-ttu-id="fe9ab-124">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="fe9ab-124">Make collaboration easier</span></span>

  <span data-ttu-id="fe9ab-125">Ersetzen Sie die auf E-Mails und Dateifreigaben basierte Zusammenarbeit durch ein Onlinemodell, das Echtzeitänderungen an Dokumenten, einfachere Onlinebesprechungen und erfasste Unterhaltungsthreads ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="fe9ab-126">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="fe9ab-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="fe9ab-127">Viele Mitarbeiter arbeiten von zu Hause aus oder unterwegs – ersetzen Sie daher die zu Engpässen führende VPN-Lösung durch leistungsstarken Zugriff auf Contoso-Daten und -Ressourcen in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="fe9ab-128">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="fe9ab-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="fe9ab-129">Nutzen Sie die Vorteile der neuesten visuellen Lern- und Ideenfindungsmethoden, einschließlich Freihand und 3D-Visualisierung.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="fe9ab-130">Sicherheit:</span><span class="sxs-lookup"><span data-stu-id="fe9ab-130">Security</span></span>

- <span data-ttu-id="fe9ab-131">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="fe9ab-131">Identity and access management</span></span>

  <span data-ttu-id="fe9ab-132">Erzwingen Sie die mehrstufige Authentifizierung und andere Formen der Authentifizierung, und schützen Sie Anmeldeinformationen von Benutzer- und Administratorkonten.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="fe9ab-133">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="fe9ab-133">Threat Protection</span></span>

  <span data-ttu-id="fe9ab-134">Schutz vor externen Sicherheitsrisiken, einschließlich Schadsoftware, die auf E-Mails oder dem Betriebssystem basiert.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="fe9ab-135">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="fe9ab-135">Information protection</span></span>

  <span data-ttu-id="fe9ab-136">Sperren Sie den Zugriff auf wichtige digitale Ressourcen, und verschlüsseln Sie diese (z. B. Kundendaten, Entwurfsspezifikationen und Mitarbeiterinformationen).</span><span class="sxs-lookup"><span data-stu-id="fe9ab-136">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="fe9ab-137">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="fe9ab-137">Security incident management</span></span>

  <span data-ttu-id="fe9ab-138">Überwachen des Sicherheitszustands und Ermitteln von sowie Reagieren auf Bedrohungen in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="fe9ab-139">Remote- und Mobilzugriff und Geschäftspartner:</span><span class="sxs-lookup"><span data-stu-id="fe9ab-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="fe9ab-140">Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="fe9ab-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="fe9ab-141">Führen Sie BYOD (Bring Your Own Device) und die Verwaltung von firmeneigenen Geräten ein, um einen sicheren Zugriff, ein korrektes Anwendungsverhalten sowie den Schutz von Unternehmensdaten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="fe9ab-142">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="fe9ab-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="fe9ab-143">Senken Sie die Wartungs- und Supportkosten, und verbessern Sie die Leistung für Remotezugriffslösungen, indem Sie Ressourcen, auf die häufig zugegriffen wird, in die Cloud verschieben.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-143">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="fe9ab-144">Bessere Konnektivität und weniger Aufwand für Business-to-Business-Transaktionen (B2B)</span><span class="sxs-lookup"><span data-stu-id="fe9ab-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="fe9ab-145">Ersetzen Sie das in die Jahre gekommene Partnerextranet durch eine cloudbasierte Lösung, für die Verbundauthentifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="fe9ab-146">Compliance:</span><span class="sxs-lookup"><span data-stu-id="fe9ab-146">Compliance</span></span>

- <span data-ttu-id="fe9ab-147">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="fe9ab-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="fe9ab-148">Halten Sie branchenübliche und regionale Vorschriften für Datenspeicherung, Verschlüsselung und Datenschutz sowie Vorschriften für personenbezogene Daten ein, z. B. die DSGVO für die Europäische Union.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="fe9ab-149">Verwaltung:</span><span class="sxs-lookup"><span data-stu-id="fe9ab-149">Management</span></span>

- <span data-ttu-id="fe9ab-150">Reduzieren des IT-Aufwands für die Verwaltung von Software, die auf Clientcomputern und -geräten ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="fe9ab-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="fe9ab-151">Automatisieren Sie die Installation von Updates auf dem Windows-Betriebssystem und in Microsoft Office in der gesamten Organisation.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-151">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="fe9ab-152">Zuordnen der Geschäftsanforderungen von Contoso zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fe9ab-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="fe9ab-153">Von der IT-Abteilung von Contoso wurde vor der Bereitstellung die folgende Zuordnung von Geschäftsanforderungen zu den Features von Microsoft 365 Enterprise E5 vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="fe9ab-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="fe9ab-154">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="fe9ab-154">**Category**</span></span> | <span data-ttu-id="fe9ab-155">**Geschäftsanforderung**</span><span class="sxs-lookup"><span data-stu-id="fe9ab-155">**Business Need**</span></span> | <span data-ttu-id="fe9ab-156">**Produkte oder Features von Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="fe9ab-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="fe9ab-157">Produktivität</span><span class="sxs-lookup"><span data-stu-id="fe9ab-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="fe9ab-158">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="fe9ab-158">Make collaboration easier</span></span> | <span data-ttu-id="fe9ab-159">Teams, SharePoint Online, Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fe9ab-159">Teams, SharePoint Online, Skype for Business Online</span></span> |
|  | <span data-ttu-id="fe9ab-160">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="fe9ab-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="fe9ab-161">Office 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="fe9ab-161">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="fe9ab-162">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="fe9ab-162">Increase creativity and innovation</span></span> | <span data-ttu-id="fe9ab-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="fe9ab-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="fe9ab-164">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fe9ab-164">Security</span></span> |  |  |
|  | <span data-ttu-id="fe9ab-165">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="fe9ab-165">Identity and access management</span></span> | <span data-ttu-id="fe9ab-166">Dedizierte globale Administratorkonten mit mehrstufiger Authentifizierung (MFA) und Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="fe9ab-166">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="fe9ab-167">Mehrstufige Authentifizierung für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="fe9ab-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="fe9ab-168">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="fe9ab-168">Conditional access</span></span> <BR> <span data-ttu-id="fe9ab-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="fe9ab-169">Windows Hello,</span></span> <BR> <span data-ttu-id="fe9ab-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="fe9ab-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="fe9ab-171">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="fe9ab-171">Threat Protection</span></span> | <span data-ttu-id="fe9ab-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="fe9ab-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="fe9ab-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="fe9ab-173">Windows Defender</span></span> <BR> <span data-ttu-id="fe9ab-174">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fe9ab-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="fe9ab-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fe9ab-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="fe9ab-176">Informationen zu Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="fe9ab-176">Office 365 Threat Intelligence</span></span> <BR> |
|  | <span data-ttu-id="fe9ab-177">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="fe9ab-177">Information protection</span></span> | <span data-ttu-id="fe9ab-178">Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="fe9ab-178">Azure RMS renamed Azure Information Protection (AIP).</span></span> <BR> <span data-ttu-id="fe9ab-179">Verhinderung von Datenverlust in Office 365</span><span class="sxs-lookup"><span data-stu-id="fe9ab-179">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="fe9ab-180">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="fe9ab-180">Windows Information Protection</span></span> <BR> <span data-ttu-id="fe9ab-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fe9ab-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="fe9ab-182">Office 365 Cloud App Security (CAS)</span><span class="sxs-lookup"><span data-stu-id="fe9ab-182">Office 365 Cloud App Security</span></span> <BR> <span data-ttu-id="fe9ab-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fe9ab-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="fe9ab-184">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="fe9ab-184">Security incident management</span></span> | <span data-ttu-id="fe9ab-185">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="fe9ab-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="fe9ab-186">Windows Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="fe9ab-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="fe9ab-187">Remote- und Mobilzugriff und Geschäftspartner</span><span class="sxs-lookup"><span data-stu-id="fe9ab-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="fe9ab-188">Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="fe9ab-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="fe9ab-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fe9ab-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="fe9ab-190">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="fe9ab-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="fe9ab-191">Office 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="fe9ab-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="fe9ab-192">Bessere Konnektivität und weniger Aufwand für B2B-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="fe9ab-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="fe9ab-193">Verbundauthentifizierung und cloudbasierte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="fe9ab-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="fe9ab-194">Compliance</span><span class="sxs-lookup"><span data-stu-id="fe9ab-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="fe9ab-195">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="fe9ab-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="fe9ab-196">DSGVO-Features in Office 365</span><span class="sxs-lookup"><span data-stu-id="fe9ab-196">Demonstrate GDPR capabilities in Office 365.</span></span> |
| <span data-ttu-id="fe9ab-197">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="fe9ab-197">Management</span></span> |  |  |
|  | <span data-ttu-id="fe9ab-198">Reduzieren des IT-Aufwands für die Installation von Clientupdates</span><span class="sxs-lookup"><span data-stu-id="fe9ab-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="fe9ab-199">Bereitstellungsringe</span><span class="sxs-lookup"><span data-stu-id="fe9ab-199">Deployment rings</span></span> <BR> <span data-ttu-id="fe9ab-200">Vorhandenes Upgrade auf Windows 10 und Autopilot</span><span class="sxs-lookup"><span data-stu-id="fe9ab-200">Windows 10 upgrade in place and Autopilot</span></span> <BR> <span data-ttu-id="fe9ab-201">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="fe9ab-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="fe9ab-202">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="fe9ab-202">Next step</span></span>

<span data-ttu-id="fe9ab-203">[Erfahren Sie mehr](contoso-networking.md) über das lokale Netzwerk von Contoso und wie dieses im Hinblick auf Zugriff und Latenz für cloudbasierte Microsoft 365-Ressourcen in der gesamten Organisation optimiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fe9ab-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe9ab-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe9ab-204">See also</span></span>

[<span data-ttu-id="fe9ab-205">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="fe9ab-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="fe9ab-206">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="fe9ab-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
