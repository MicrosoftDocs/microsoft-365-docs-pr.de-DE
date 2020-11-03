---
title: Contoso-IT-Infrastruktur und geschäftliche Anforderungen
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
description: Hier finden Sie Informationen zur grundlegenden Struktur der lokalen Contoso-IT-Infrastruktur und dazu, wie die geschäftlichen Anforderungen von Microsoft 365 für Unternehmen erfüllt werden.
ms.openlocfilehash: 0a837a457869fc579d94ee5e5f9bb114cb93f641
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847130"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="9a8a4-103">Contoso-IT-Infrastruktur und geschäftliche Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a8a4-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="9a8a4-104">Contoso wechselt von einer lokalen, zentralisierten IT-Infrastruktur zu einem Cloud-inclusive-Setup, das Cloud-basierte persönliche Produktivitäts Arbeitslasten und-Anwendungen enthält.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="9a8a4-105">Vorhandene Contoso-IT-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="9a8a4-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="9a8a4-106">Contoso nutzt eine weitestgehend zentrale lokale IT-Infrastruktur mit Anwendungsrechenzentren in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="9a8a4-107">Hier finden Sie die Hauptniederlassung mit Anwendungsdaten Centern, eine DMZ und das Internet.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Vorhandene Contoso-IT-Infrastruktur](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="9a8a4-109">In den lokalen Anwendungsrechenzentren wird Folgendes gehostet:</span><span class="sxs-lookup"><span data-stu-id="9a8a4-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="9a8a4-110">Benutzerdefinierte Branchenanwendungen, die SQL Server und andere Linux-Datenbanken verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="9a8a4-111">Eine Reihe von älteren SharePoint-Servern.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="9a8a4-112">Server auf Organisations- und Teamebene für das Speichern von Dateien.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="9a8a4-113">Darüber hinaus unterstützt jedes regionales Hub-Büro eine Reihe von Servern mit einer ähnlichen Gruppe von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="9a8a4-114">Diese Server werden von regionalen IT-Abteilungen gesteuert.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="9a8a4-115">Die Durchsuchbarkeit über die Anwendungen und Daten dieser separaten Rechenzentren an mehreren geografischen Standorten hinweg bleibt eine Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="9a8a4-116">In der DMZ "Contoso Headquarters" bieten verschiedene Servergruppen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9a8a4-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="9a8a4-117">Hosten für die öffentliche Contoso-Website, von der Kunden Produkte, Teile, Lieferungen und Dienste bestellen können.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="9a8a4-118">Hosting für das Contoso-Partnerextranet für die Kommunikation und Zusammenarbeit mit Partnern.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="9a8a4-119">VPN-basierter Remotezugriff (virtuelles privates Netzwerk) auf das Contoso-Intranet und Webproxyfunktion für Mitarbeiter in der Pariser Zentrale.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="9a8a4-120">Contoso-Geschäftsanforderungen</span><span class="sxs-lookup"><span data-stu-id="9a8a4-120">Contoso business needs</span></span>

<span data-ttu-id="9a8a4-121">Die geschäftlichen Anforderungen von Contoso unterliegen fünf Hauptkategorien:</span><span class="sxs-lookup"><span data-stu-id="9a8a4-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="9a8a4-122">**Produktivität**</span><span class="sxs-lookup"><span data-stu-id="9a8a4-122">**Productivity**</span></span>

- <span data-ttu-id="9a8a4-123">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="9a8a4-123">Make collaboration easier</span></span>

  <span data-ttu-id="9a8a4-124">Ersetzen Sie die e-Mail-und Dateifreigabe basierte Zusammenarbeit durch ein Online Modell, das Echtzeitänderungen an Dokumenten, einfachere Onlinebesprechungen und aufgezeichnete Unterhaltungsthemen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="9a8a4-125">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="9a8a4-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="9a8a4-126">Wenn viele Mitarbeiter von zu Hause oder im Feld arbeiten, ersetzen Sie die Engpass-VPN-Lösung durch den leistungsfähigen Zugriff auf contoso-Daten und-Ressourcen in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="9a8a4-127">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="9a8a4-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="9a8a4-128">Nutzen Sie die Vorteile der neuesten visuellen Lern- und Ideenfindungsmethoden, einschließlich Freihand und 3D-Visualisierung.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="9a8a4-129">**Sicherheit**</span><span class="sxs-lookup"><span data-stu-id="9a8a4-129">**Security**</span></span>

- <span data-ttu-id="9a8a4-130">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="9a8a4-130">Identity and access management</span></span>

  <span data-ttu-id="9a8a4-131">Erzwingen Sie mehrstufige und andere Formen der Authentifizierung, und schützen Sie die Anmeldeinformationen von Benutzer-und Administratorkonten.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="9a8a4-132">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="9a8a4-132">Threat protection</span></span>

  <span data-ttu-id="9a8a4-133">Schutz vor externen Sicherheitsrisiken, einschließlich Schadsoftware, die auf E-Mails oder dem Betriebssystem basiert.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="9a8a4-134">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="9a8a4-134">Information protection</span></span>

  <span data-ttu-id="9a8a4-135">Sperren Sie den Zugriff auf wichtige digitale Ressourcen, und verschlüsseln Sie diese (z. B. Kundendaten, Entwurfs- und Fertigungsspezifikationen und Mitarbeiterinformationen).</span><span class="sxs-lookup"><span data-stu-id="9a8a4-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="9a8a4-136">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="9a8a4-136">Security management</span></span>

  <span data-ttu-id="9a8a4-137">Überwachen der Sicherheitsposition und erkennen und reagieren auf Bedrohungen in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="9a8a4-138">**Remote- und Mobilzugriff und Geschäftspartner**</span><span class="sxs-lookup"><span data-stu-id="9a8a4-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="9a8a4-139">Verbessern der Sicherheit für Remote-und mobile Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="9a8a4-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="9a8a4-140">Implementieren Sie Ihr eigenes Gerät (BYOD) und die unternehmenseigene Geräteverwaltung, um sicherzustellen, dass ein geschützter Zugriff, ein korrektes Anwendungsverhalten und Datenschutz für Unternehmen gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="9a8a4-141">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="9a8a4-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="9a8a4-142">Reduzieren Sie Wartungs-und Supportkosten und verbessern Sie die Leistung für die Remotezugriffslösung durch Verschieben häufig abgerufener Ressourcen in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="9a8a4-143">Bereitstellen besserer Konnektivität und geringerer Overhead für Business-to-Susi-Transaktionen (B2B)</span><span class="sxs-lookup"><span data-stu-id="9a8a4-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="9a8a4-144">Ersetzen Sie ein alterndes und kostspieliges Partner Extranet durch eine Cloud-basierte Lösung, die die Verbundauthentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="9a8a4-145">**Compliance**</span><span class="sxs-lookup"><span data-stu-id="9a8a4-145">**Compliance**</span></span>

- <span data-ttu-id="9a8a4-146">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="9a8a4-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="9a8a4-147">Stellen Sie sicher, dass die Branchen-und regionalen Bestimmungen für Datenspeicherung, Verschlüsselung, Datenschutz und personenbezogene Daten, wie etwa die allgemeine Datenschutzverordnung (dsgvo) für die Europäische Union, eingehaltenwerden.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="9a8a4-148">**Verwaltung**</span><span class="sxs-lookup"><span data-stu-id="9a8a4-148">**Management**</span></span>

- <span data-ttu-id="9a8a4-149">Weniger IT-Aufwand für die Verwaltung von Software, die auf Client-PCs und Geräten läuft</span><span class="sxs-lookup"><span data-stu-id="9a8a4-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="9a8a4-150">Automatisieren der Installation von Updates für das Windows-Betriebssystem und Microsoft 365-Apps für Unternehmen in der gesamten Organisation.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="9a8a4-151">Zuordnen von Contoso-Geschäftsanforderungen zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="9a8a4-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="9a8a4-152">Die IT-Abteilung von Contoso hat vor der Bereitstellung die folgende Zuordnung der geschäftlichen Anforderungen zu Microsoft 365 E5-Funktionen ermittelt:</span><span class="sxs-lookup"><span data-stu-id="9a8a4-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="9a8a4-153">Kategorie</span><span class="sxs-lookup"><span data-stu-id="9a8a4-153">Category</span></span> | <span data-ttu-id="9a8a4-154">Geschäftsanforderung</span><span class="sxs-lookup"><span data-stu-id="9a8a4-154">Business need</span></span> | <span data-ttu-id="9a8a4-155">Microsoft 365 für Enterprise-Produkte oder-Features</span><span class="sxs-lookup"><span data-stu-id="9a8a4-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="9a8a4-156">Produktivität</span><span class="sxs-lookup"><span data-stu-id="9a8a4-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="9a8a4-157">Vereinfachen der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="9a8a4-157">Make collaboration easier</span></span> | <span data-ttu-id="9a8a4-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="9a8a4-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="9a8a4-159">Mehr Produktivität für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="9a8a4-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="9a8a4-160">Microsoft 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="9a8a4-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="9a8a4-161">Mehr Kreativität und Innovation</span><span class="sxs-lookup"><span data-stu-id="9a8a4-161">Increase creativity and innovation</span></span> | <span data-ttu-id="9a8a4-162">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="9a8a4-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="9a8a4-163">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9a8a4-163">Security</span></span> |  |  |
|  | <span data-ttu-id="9a8a4-164">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="9a8a4-164">Identity & access management</span></span> | <span data-ttu-id="9a8a4-165">Dedizierte globale Administratorkonten mit Azure Multi-Factor Authentication (MFA) und Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="9a8a4-165">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="9a8a4-166">Mehrstufige Authentifizierung (MFA) für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="9a8a4-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="9a8a4-167">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="9a8a4-167">Conditional Access</span></span> <BR> <span data-ttu-id="9a8a4-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="9a8a4-168">Windows Hello</span></span> <BR> <span data-ttu-id="9a8a4-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="9a8a4-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="9a8a4-170">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="9a8a4-170">Threat protection</span></span> | <span data-ttu-id="9a8a4-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="9a8a4-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="9a8a4-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="9a8a4-172">Windows Defender</span></span> <BR> <span data-ttu-id="9a8a4-173">Verteidiger für Office 365</span><span class="sxs-lookup"><span data-stu-id="9a8a4-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="9a8a4-174">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="9a8a4-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="9a8a4-175">Untersuchung und Antwort von Microsoft 365 Threat</span><span class="sxs-lookup"><span data-stu-id="9a8a4-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="9a8a4-176">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="9a8a4-176">Information protection</span></span> | <span data-ttu-id="9a8a4-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="9a8a4-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="9a8a4-178">Verhinderung von Datenverlust (Data Loss Prevention, DLP)</span><span class="sxs-lookup"><span data-stu-id="9a8a4-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="9a8a4-179">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="9a8a4-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="9a8a4-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9a8a4-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="9a8a4-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9a8a4-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="9a8a4-182">Sicherheitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="9a8a4-182">Security management</span></span> | <span data-ttu-id="9a8a4-183">Azure Defender \*</span><span class="sxs-lookup"><span data-stu-id="9a8a4-183">Azure Defender\*</span></span>  <BR> <span data-ttu-id="9a8a4-184">Windows Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="9a8a4-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="9a8a4-185">Remote- und Mobilzugriff und Geschäftspartner</span><span class="sxs-lookup"><span data-stu-id="9a8a4-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="9a8a4-186">Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="9a8a4-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="9a8a4-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9a8a4-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="9a8a4-188">Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="9a8a4-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="9a8a4-189">Microsoft 365-Arbeitslasten und cloudbasierte Daten</span><span class="sxs-lookup"><span data-stu-id="9a8a4-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="9a8a4-190">Verbessern der Konnektivität und des niedrigeren Overheads für B2B-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="9a8a4-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="9a8a4-191">Verbundauthentifizierung und cloudbasierte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9a8a4-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="9a8a4-192">Compliance</span><span class="sxs-lookup"><span data-stu-id="9a8a4-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="9a8a4-193">Einhalten von regionalen gesetzlichen Vorschriften</span><span class="sxs-lookup"><span data-stu-id="9a8a4-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="9a8a4-194">Dsgvo-Features in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9a8a4-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="9a8a4-195">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="9a8a4-195">Management</span></span> |  |  |
|  | <span data-ttu-id="9a8a4-196">Weniger IT-Aufwand für die Installation von Clientupdates</span><span class="sxs-lookup"><span data-stu-id="9a8a4-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="9a8a4-197">Windows 10 Enterprise-Updates</span><span class="sxs-lookup"><span data-stu-id="9a8a4-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="9a8a4-198">Microsoft 365 Apps for Enterprise-Updates</span><span class="sxs-lookup"><span data-stu-id="9a8a4-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="9a8a4-199">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="9a8a4-199">Next step</span></span>

<span data-ttu-id="9a8a4-200">Erfahren Sie mehr über das [lokale](contoso-networking.md) Contoso Corporation-Netzwerk und wie es für den Zugriff und die Wartezeit auf Cloud-basierte Microsoft 365-Ressourcen optimiert wurde.</span><span class="sxs-lookup"><span data-stu-id="9a8a4-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a8a4-201">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a8a4-201">See also</span></span>

[<span data-ttu-id="9a8a4-202">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9a8a4-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9a8a4-203">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="9a8a4-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
