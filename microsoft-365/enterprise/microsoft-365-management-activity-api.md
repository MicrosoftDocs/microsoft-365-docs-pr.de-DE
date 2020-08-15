---
title: Office 365-Verwaltungsaktivitäts-API
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
- M365-analytics
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie eine kurze Zusammenfassung der API für die Office 365-Verwaltungsaktivität und der Informationen, die Sie in Aktivitätsprotokollen bereitstellt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea08673f4c26c9ee4b7093ba420b69bed91abc81
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690761"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="d784f-103">Office 365-Verwaltungsaktivitäts-API</span><span class="sxs-lookup"><span data-stu-id="d784f-103">Office 365 Management Activity API</span></span>

<span data-ttu-id="d784f-104">Microsoft stellt Reporting Services bereit, die Sie zum Abrufen aggregierter Transaktionsinformationen zu Ihrem Office 365 Mandanten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d784f-104">Microsoft provides reporting services you can use to obtain aggregated transactional information about your Office 365 tenant.</span></span> <span data-ttu-id="d784f-105">Die [Office 365-Verwaltungs Aktivitäts-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview#office-365-management-activity-api) verwendet einen branchenüblichen Rest-Entwurf und OAuth v2 für die Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d784f-105">The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview#office-365-management-activity-api) uses an industry-standard RESTful design and OAuth v2 for authentication.</span></span> <span data-ttu-id="d784f-106">Auf diese Weise wird das Experimentieren mit dem Abrufen von Daten und der Einnahme in Visualisierungstools und-Anwendungen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="d784f-106">This makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications.</span></span> <span data-ttu-id="d784f-107">Die API stellt einen Datenfeed mit Informationen zu Benutzern, Administratoren, Vorgängen und Sicherheitsaktivitäten in Office 365 bereit.</span><span class="sxs-lookup"><span data-stu-id="d784f-107">The API provides a data feed with information about user, administrator, operations, and security activity in Office 365.</span></span> <span data-ttu-id="d784f-108">Die Daten können zu behördlichen Zwecken aufbewahrt werden oder in Kombination mit Protokolldaten, die über eine lokale Infrastruktur oder andere Quellen beschafft werden.</span><span class="sxs-lookup"><span data-stu-id="d784f-108">The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources.</span></span> <span data-ttu-id="d784f-109">Auf diese Weise können Sie eine Überwachungslösung für Vorgänge, Sicherheit und Compliance im gesamten Unternehmen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d784f-109">This helps build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="d784f-110">Die Office 365-Verwaltungsaktivitäts-API bietet Informationen über verschiedene Benutzer-, Verwaltungs-, System- und Richtlinienaktionen und -ereignisse aus Office 365 und Azure Active Directory-Aktivitätsprotokollen.</span><span class="sxs-lookup"><span data-stu-id="d784f-110">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="d784f-111">Die API bietet ein konsistentes Überwachungsschema mit mehr als 10 Feldern, die für alle Dienste gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="d784f-111">The API provides a consistent audit schema with over 10 fields common across all the services.</span></span> <span data-ttu-id="d784f-112">Die API ermöglicht es Organisationen, einfache Verbindungen zwischen Ereignissen herzustellen, und ermöglicht neue Wege zur Begründung der Daten.</span><span class="sxs-lookup"><span data-stu-id="d784f-112">The API allows organizations to make easy connections between events, and enables new ways to reason over the data.</span></span>

<span data-ttu-id="d784f-113">Dutzende von unabhängigen Software Anbietern (Independent Software Vendors, ISVs) haben mit Microsoft zusammenarbeiten und Lösungen basierend auf der API entwickelt.</span><span class="sxs-lookup"><span data-stu-id="d784f-113">Dozens of Independent Software Vendors (ISVs) partnered with Microsoft and have built solutions based on the API.</span></span> <span data-ttu-id="d784f-114">Einige Lösungen konzentrieren sich ausschließlich auf Office 365 Daten und andere Quelldaten von mehreren Cloud-Anbietern und lokalen Systemen, um eine einheitliche Ansicht der Vorgänge, der Sicherheit und der Konformitäts bezogenen Aktivitäten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d784f-114">Some solutions focus solely on Office 365 data and others source data from multiple cloud providers and on-premises systems to create a unified view of operations, security, and compliance-related activity.</span></span> 

<span data-ttu-id="d784f-115">Weitere Informationen finden Sie in der [API-Referenz zur Office 365-Verwaltungsaktivität](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="d784f-115">For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>
