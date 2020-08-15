---
title: Microsoft 365 Überwachung und Überwachung von Zugriffssteuerungen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 'Zusammenfassung: eine Zusammenfassung der verschiedenen Überwachungs-und Überwachungs Zugriffssteuerungen, die in Microsoft 365 verfügbar sind.'
ms.openlocfilehash: f1302c4056bfd605e35aae08d8f5355f8d204db2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690611"
---
# <a name="monitoring-and-auditing-access-controls-in-microsoft-365"></a><span data-ttu-id="80f9b-103">Überwachen und Überwachen von Zugriffssteuerungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="80f9b-103">Monitoring and Auditing Access Controls in Microsoft 365</span></span>

<span data-ttu-id="80f9b-104">Microsoft führt eine umfassende Überwachung und Überwachung aller Delegierungen, Berechtigungen und Vorgänge durch, die in Microsoft 365 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="80f9b-104">Microsoft performs extensive monitoring and auditing of all delegation, privileges, and operations that occur within Microsoft 365.</span></span> <span data-ttu-id="80f9b-105">Microsoft 365 Zugriffssteuerung ist ein automatisierter Prozess, der auf dem Prinzip der geringsten Rechte basiert und Datenzugriffs Steuerelemente und-Überprüfungen integriert:</span><span class="sxs-lookup"><span data-stu-id="80f9b-105">Microsoft 365 access control is an automated process built on the principle of least privilege and incorporating data access controls and audits:</span></span>

- <span data-ttu-id="80f9b-106">Alle zulässigen Zugriffe können auf einen eindeutigen Benutzer zurückgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="80f9b-106">All permitted access is traceable to a unique user.</span></span> <span data-ttu-id="80f9b-107">Administratoren sind für die Verarbeitung von Kundeninhalten verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="80f9b-107">Administrators are accountable for their handling of customer content.</span></span>
- <span data-ttu-id="80f9b-108">Zugriffssteuerungsanforderungen, Genehmigungen und Administrative Operations Protokolle werden zur Analyse von Sicherheit und böswilligen Ereignissen erfasst.</span><span class="sxs-lookup"><span data-stu-id="80f9b-108">Access control requests, approvals, and administrative operations logs are captured for analysis of security and malicious events.</span></span>
- <span data-ttu-id="80f9b-109">Zugriffsebenen werden basierend auf der Sicherheitsgruppenmitgliedschaft nahezu in Echtzeit überprüft, um sicherzustellen, dass nur Benutzer mit autorisierten geschäftlichen Begründungen und den Berechtigungsanforderungen Zugriff auf die Systeme haben.</span><span class="sxs-lookup"><span data-stu-id="80f9b-109">Access levels are reviewed in near real-time based on security group membership to ensure that only users who have authorized business justifications and meet the eligibility requirements have access to the systems.</span></span>
- <span data-ttu-id="80f9b-110">Microsoft 365, die Zugriffssteuerung und die unterstützenden Dienste, einschließlich Azure Active Directory und physische Rechenzentren, werden regelmäßig von unabhängigen Drittanbietern für die Einhaltung von [ISO/IEC 27001](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/TrustCenter/Compliance/FedRAMP)und anderen [Standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)überwacht.</span><span class="sxs-lookup"><span data-stu-id="80f9b-110">Microsoft 365, its access controls, and supporting services, including Azure Active Directory and physical datacenters, are regularly audited by independent third-parties for compliance with [ISO/IEC 27001](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/TrustCenter/Compliance/FedRAMP), and other [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span>
- <span data-ttu-id="80f9b-111">Microsoft 365-Techniker müssen jährliche Sicherheitsschulungen durchführen, die bewährten Methoden für erhöhten Zugriff überprüfen und die Sicherheits-und Datenschutzrichtlinien von Microsoft anerkennen, um die Berechtigungen für den Dienst beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="80f9b-111">Microsoft 365 engineers must take yearly security training, review elevated access best procedures, and acknowledge Microsoft's security and privacy policies to maintain entitlements to the service.</span></span>

<span data-ttu-id="80f9b-112">Automatische Warnungen werden ausgelöst, wenn verdächtige Aktivitäten erkannt werden, beispielsweise mehrere fehlgeschlagene Anmeldungen innerhalb eines kurzen Zeitraums.</span><span class="sxs-lookup"><span data-stu-id="80f9b-112">Automated alerts trigger when suspicious activity is detected, such as multiple failed logins within a short period.</span></span> <span data-ttu-id="80f9b-113">Das Microsoft 365-Sicherheitsantwort Team verwendet Maschinelles Lernen und eine große Datenanalyse, um Aktivitäten zu überprüfen und zu analysieren, nach unregelmäßigen Zugriffsmustern zu suchen und proaktiv auf anomale und unerlaubte Aktivitäten zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="80f9b-113">The Microsoft 365 Security Response team uses machine learning and big data analysis to review and analyze activity, look for irregular access patterns, and proactively respond to anomalous and illicit activities.</span></span> <span data-ttu-id="80f9b-114">Microsoft beschäftigt außerdem ein dediziertes Team von Penetrations Testern und engagiert sich in regelmäßigen roten Team-und blauen Teamübungen, um Sicherheits-und Zugriffssteuerungsprobleme im Dienst zu finden.</span><span class="sxs-lookup"><span data-stu-id="80f9b-114">Microsoft also employs a dedicated team of penetration testers and engages in periodic Red Team and Blue Team exercises to find security and access control issues in the service.</span></span> <span data-ttu-id="80f9b-115">Kunden können die Effektivität von Zugriffs Steuerungssystemen mithilfe von Überwachungsberichten und der von Microsoft 365 bereitgestellten Verwaltungs Aktivitäts-API überprüfen.</span><span class="sxs-lookup"><span data-stu-id="80f9b-115">Customers can verify the effectiveness of access control systems by using audit reports and the management activity API provided by Microsoft 365.</span></span>

<span data-ttu-id="80f9b-116">Weitere Informationen finden Sie unter [Office 365 Management Activity API Reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) and [Auditing and Reporting in Microsoft 365](microsoft-365-auditing-and-reporting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="80f9b-116">For more information, see [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) and [Auditing and reporting in Microsoft 365](microsoft-365-auditing-and-reporting-overview.md).</span></span>