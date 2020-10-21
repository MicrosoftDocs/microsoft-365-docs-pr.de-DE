---
title: Contoso-IT-Infrastruktur und geschäftliche Anforderungen
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Hier finden Sie Informationen zur grundlegenden Struktur der lokalen Contoso-IT-Infrastruktur und dazu, wie die geschäftlichen Anforderungen von Microsoft 365 für Unternehmen erfüllt werden.
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637175"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="ece27-103">Contoso-IT-Infrastruktur und geschäftliche Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ece27-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="ece27-104">Contoso wechselt von einer lokalen, zentralisierten IT-Infrastruktur zu einem Cloud-inclusive-Setup, das Cloud-basierte persönliche Produktivitäts Arbeitslasten und-Anwendungen enthält.</span><span class="sxs-lookup"><span data-stu-id="ece27-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="ece27-105">Vorhandene Contoso-IT-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="ece27-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="ece27-106">Contoso nutzt eine weitestgehend zentrale lokale IT-Infrastruktur mit Anwendungsrechenzentren in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="ece27-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="ece27-107">In Abbildung 1 ist die Hauptniederlassung mit Anwendungsdaten Centern, einer DMZ und dem Internet dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ece27-107">Figure 1 shows the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Vorhandene Contoso-IT-Infrastruktur](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="ece27-109">**Abbildung 1: vorhandene Contoso-IT-Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="ece27-109">**Figure 1: Existing Contoso IT infrastructure**</span></span>
 
<span data-ttu-id="ece27-110">In den lokalen Anwendungsrechenzentren wird Folgendes gehostet:</span><span class="sxs-lookup"><span data-stu-id="ece27-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="ece27-111">Benutzerdefinierte Branchenanwendungen, die SQL Server und andere Linux-Datenbanken verwenden.</span><span class="sxs-lookup"><span data-stu-id="ece27-111">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="ece27-112">Eine Reihe von älteren SharePoint-Servern.</span><span class="sxs-lookup"><span data-stu-id="ece27-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="ece27-113">Server auf Organisations- und Teamebene für das Speichern von Dateien.</span><span class="sxs-lookup"><span data-stu-id="ece27-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="ece27-114">Darüber hinaus unterstützt jedes regionales Hub-Büro eine Reihe von Servern mit einer ähnlichen Gruppe von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ece27-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="ece27-115">Diese Server werden von regionalen IT-Abteilungen gesteuert.</span><span class="sxs-lookup"><span data-stu-id="ece27-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="ece27-116">Die Durchsuchbarkeit über die Anwendungen und Daten dieser separaten Rechenzentren an mehreren geografischen Standorten hinweg bleibt eine Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="ece27-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="ece27-117">In der DMZ "Contoso Headquarters" bieten verschiedene Servergruppen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ece27-117">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="ece27-118">Hosten für die öffentliche Contoso-Website, von der Kunden Produkte, Teile, Lieferungen und Dienste bestellen können.</span><span class="sxs-lookup"><span data-stu-id="ece27-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="ece27-119">Hosting für das Contoso-Partnerextranet für die Kommunikation und Zusammenarbeit mit Partnern.</span><span class="sxs-lookup"><span data-stu-id="ece27-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="ece27-120">VPN-basierter Remotezugriff (virtuelles privates Netzwerk) auf das Contoso-Intranet und Webproxyfunktion für Mitarbeiter in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="ece27-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="ece27-121">Contoso-Geschäftsanforderungen</span><span class="sxs-lookup"><span data-stu-id="ece27-121">Contoso business needs</span></span>

<span data-ttu-id="ece27-122">Die geschäftlichen Anforderungen von Contoso unterliegen fünf Hauptkategorien:</span><span class="sxs-lookup"><span data-stu-id="ece27-122">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="ece27-123">**Produktivität**</span><span class="sxs-lookup"><span data-stu-id="ece27-123">**Productivity**</span></span>

- <span data-ttu-id="ece27-124">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="ece27-124">Make collaboration easier</span></span>

  <span data-ttu-id="ece27-125">Ersetzen Sie die e-Mail-und Dateifreigabe basierte Zusammenarbeit durch ein Online Modell, das Echtzeitänderungen an Dokumenten, einfachere Onlinebesprechungen und aufgezeichnete Unterhaltungsthemen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ece27-125">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="ece27-126">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="ece27-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="ece27-127">Wenn viele Mitarbeiter von zu Hause oder im Feld arbeiten, ersetzen Sie die Engpass-VPN-Lösung durch den leistungsfähigen Zugriff auf contoso-Daten und-Ressourcen in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="ece27-127">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="ece27-128">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="ece27-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="ece27-129">Nutzen Sie die Vorteile der neuesten visuellen Lern- und Ideenfindungsmethoden, einschließlich Freihand und 3D-Visualisierung.</span><span class="sxs-lookup"><span data-stu-id="ece27-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="ece27-130">**Sicherheit**</span><span class="sxs-lookup"><span data-stu-id="ece27-130">**Security**</span></span>

- <span data-ttu-id="ece27-131">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ece27-131">Identity and access management</span></span>

  <span data-ttu-id="ece27-132">Erzwingen Sie mehrstufige und andere Formen der Authentifizierung, und schützen Sie die Anmeldeinformationen von Benutzer-und Administratorkonten.</span><span class="sxs-lookup"><span data-stu-id="ece27-132">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="ece27-133">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="ece27-133">Threat protection</span></span>

  <span data-ttu-id="ece27-134">Schutz vor externen Sicherheitsrisiken, einschließlich Schadsoftware, die auf E-Mails oder dem Betriebssystem basiert.</span><span class="sxs-lookup"><span data-stu-id="ece27-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="ece27-135">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="ece27-135">Information protection</span></span>

  <span data-ttu-id="ece27-136">Sperren Sie den Zugriff auf wichtige digitale Ressourcen, und verschlüsseln Sie diese (z. B. Kundendaten, Entwurfs- und Fertigungsspezifikationen und Mitarbeiterinformationen).</span><span class="sxs-lookup"><span data-stu-id="ece27-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="ece27-137">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ece27-137">Security management</span></span>

  <span data-ttu-id="ece27-138">Überwachen der Sicherheitsposition und erkennen und reagieren auf Bedrohungen in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="ece27-138">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="ece27-139">**Remote- und Mobilzugriff und Geschäftspartner**</span><span class="sxs-lookup"><span data-stu-id="ece27-139">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="ece27-140">Verbessern der Sicherheit für Remote-und mobile Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="ece27-140">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="ece27-141">Implementieren Sie Ihr eigenes Gerät (BYOD) und die unternehmenseigene Geräteverwaltung, um sicherzustellen, dass ein geschützter Zugriff, ein korrektes Anwendungsverhalten und Datenschutz für Unternehmen gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="ece27-141">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="ece27-142">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="ece27-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="ece27-143">Reduzieren Sie Wartungs-und Supportkosten und verbessern Sie die Leistung für die Remotezugriffslösung durch Verschieben häufig abgerufener Ressourcen in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="ece27-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="ece27-144">Bereitstellen besserer Konnektivität und geringerer Overhead für Business-to-Susi-Transaktionen (B2B)</span><span class="sxs-lookup"><span data-stu-id="ece27-144">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="ece27-145">Ersetzen Sie ein alterndes und kostspieliges Partner Extranet durch eine Cloud-basierte Lösung, die die Verbundauthentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ece27-145">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="ece27-146">**Compliance**</span><span class="sxs-lookup"><span data-stu-id="ece27-146">**Compliance**</span></span>

- <span data-ttu-id="ece27-147">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="ece27-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="ece27-148">Stellen Sie sicher, dass die Branchen-und regionalen Bestimmungen für Datenspeicherung, Verschlüsselung, Datenschutz und personenbezogene Daten, wie etwa die allgemeine Datenschutzverordnung (dsgvo) für die Europäische Union, eingehaltenwerden.</span><span class="sxs-lookup"><span data-stu-id="ece27-148">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="ece27-149">**Verwaltung**</span><span class="sxs-lookup"><span data-stu-id="ece27-149">**Management**</span></span>

- <span data-ttu-id="ece27-150">Weniger IT-Aufwand für die Verwaltung von Software, die auf Client-PCs und Geräten läuft</span><span class="sxs-lookup"><span data-stu-id="ece27-150">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="ece27-151">Automatisieren der Installation von Updates für das Windows-Betriebssystem und Microsoft 365-Apps für Unternehmen in der gesamten Organisation.</span><span class="sxs-lookup"><span data-stu-id="ece27-151">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="ece27-152">Zuordnen von Contoso-Geschäftsanforderungen zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="ece27-152">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="ece27-153">Die IT-Abteilung von Contoso hat vor der Bereitstellung die folgende Zuordnung der geschäftlichen Anforderungen zu Microsoft 365 E5-Funktionen ermittelt:</span><span class="sxs-lookup"><span data-stu-id="ece27-153">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="ece27-154">Kategorie</span><span class="sxs-lookup"><span data-stu-id="ece27-154">Category</span></span> | <span data-ttu-id="ece27-155">Geschäftsanforderung</span><span class="sxs-lookup"><span data-stu-id="ece27-155">Business need</span></span> | <span data-ttu-id="ece27-156">Microsoft 365 für Enterprise-Produkte oder-Features</span><span class="sxs-lookup"><span data-stu-id="ece27-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="ece27-157">Produktivität</span><span class="sxs-lookup"><span data-stu-id="ece27-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="ece27-158">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="ece27-158">Make collaboration easier</span></span> | <span data-ttu-id="ece27-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="ece27-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="ece27-160">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="ece27-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="ece27-161">Microsoft 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="ece27-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="ece27-162">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="ece27-162">Increase creativity and innovation</span></span> | <span data-ttu-id="ece27-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ece27-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="ece27-164">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ece27-164">Security</span></span> |  |  |
|  | <span data-ttu-id="ece27-165">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ece27-165">Identity & access management</span></span> | <span data-ttu-id="ece27-166">Dedizierte globale Administratorkonten mit Azure Multi-Factor Authentication (MFA) und Azure Active Directory Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="ece27-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="ece27-167">Mehrstufige Authentifizierung (MFA) für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="ece27-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="ece27-168">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="ece27-168">Conditional Access</span></span> <BR> <span data-ttu-id="ece27-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="ece27-169">Windows Hello</span></span> <BR> <span data-ttu-id="ece27-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="ece27-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="ece27-171">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="ece27-171">Threat protection</span></span> | <span data-ttu-id="ece27-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="ece27-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="ece27-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="ece27-173">Windows Defender</span></span> <BR> <span data-ttu-id="ece27-174">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ece27-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="ece27-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ece27-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="ece27-176">Untersuchung und Antwort von Microsoft 365 Threat</span><span class="sxs-lookup"><span data-stu-id="ece27-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="ece27-177">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="ece27-177">Information protection</span></span> | <span data-ttu-id="ece27-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="ece27-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="ece27-179">Verhinderung von Datenverlust (Data Loss Prevention, DLP)</span><span class="sxs-lookup"><span data-stu-id="ece27-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="ece27-180">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="ece27-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="ece27-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ece27-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="ece27-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ece27-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="ece27-183">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ece27-183">Security management</span></span> | <span data-ttu-id="ece27-184">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="ece27-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="ece27-185">Windows Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="ece27-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="ece27-186">Remote- und Mobilzugriff und Geschäftspartner</span><span class="sxs-lookup"><span data-stu-id="ece27-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="ece27-187">Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="ece27-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="ece27-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ece27-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="ece27-189">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="ece27-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="ece27-190">Microsoft 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="ece27-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="ece27-191">Verbessern der Konnektivität und des niedrigeren Overheads für B2B-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="ece27-191">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="ece27-192">Verbundauthentifizierung und cloudbasierte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ece27-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="ece27-193">Compliance</span><span class="sxs-lookup"><span data-stu-id="ece27-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="ece27-194">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="ece27-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="ece27-195">Dsgvo-Features in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ece27-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="ece27-196">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="ece27-196">Management</span></span> |  |  |
|  | <span data-ttu-id="ece27-197">Weniger IT-Aufwand für die Installation von Clientupdates</span><span class="sxs-lookup"><span data-stu-id="ece27-197">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="ece27-198">Bereitstellungsringe</span><span class="sxs-lookup"><span data-stu-id="ece27-198">Deployment rings</span></span> <BR> <span data-ttu-id="ece27-199">Windows 10 Enterprise-Updates</span><span class="sxs-lookup"><span data-stu-id="ece27-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="ece27-200">Microsoft 365 Apps for Enterprise-Updates</span><span class="sxs-lookup"><span data-stu-id="ece27-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="ece27-201">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ece27-201">Next step</span></span>

<span data-ttu-id="ece27-202">[Erfahren Sie mehr](contoso-networking.md) über das lokale Contoso Corporation-Netzwerk und wie es für den Zugriff und die Wartezeit auf Cloud-basierte Microsoft 365-Ressourcen optimiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ece27-202">[Learn](contoso-networking.md) about the Contoso Corporation on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="ece27-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ece27-203">See also</span></span>

[<span data-ttu-id="ece27-204">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ece27-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ece27-205">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="ece27-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
