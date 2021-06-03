---
title: Übersicht über Microsoft 365 Defender-APIs
description: Erfahren Sie mehr über die verfügbaren APIs in Microsoft 365 Defender
keywords: api, apis, overview, incident, incidents, threat hunting, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b19a6072be5f97b90c117f053ccae4593587c43d
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730894"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="eb087-104">Übersicht über Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="eb087-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="eb087-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="eb087-105">**Applies to:**</span></span>

- <span data-ttu-id="eb087-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb087-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb087-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="eb087-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="eb087-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="eb087-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="eb087-109">Microsoft 365 Defender baut auf einer integrationsbereiten Plattform auf.</span><span class="sxs-lookup"><span data-stu-id="eb087-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="eb087-110">Verwenden Sie die Microsoft 365 Defender-APIs, um Workflows basierend auf dem freigegebenen Vorfall und erweiterten Nachschlagetabellen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="eb087-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="eb087-111">**[Warteschlange für kombinierte](api-incident.md)** Vorfälle – Konzentrieren Sie sich auf das Wichtige, indem Sie den vollständigen Angriffsbereich und alle sich auswirkenden Ressourcen unter der Vorfall-API gruppieren.</span><span class="sxs-lookup"><span data-stu-id="eb087-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="eb087-112">**[Produktübergreifende](api-advanced-hunting.md)** Bedrohungssuche : Nutzen Sie das Organisationswissen Ihres Sicherheitsteams, um nach Anzeichen von Kompromissen zu fahnen, indem Sie Eigene benutzerdefinierte Abfragen erstellen, um Rohdaten zu siften, die in mehreren Schutzprodukten gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="eb087-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="eb087-113">Verwenden Sie [die Streaming-API,](../defender-endpoint/raw-data-export.md) um Echtzeitereignisse und Warnungen von Instanzen zu senden, die innerhalb eines einzelnen Datenstroms auftreten.</span><span class="sxs-lookup"><span data-stu-id="eb087-113">Use the [Streaming API](../defender-endpoint/raw-data-export.md) to ship real-time events and alerts from instances as they occur within a single data stream.</span></span>


<span data-ttu-id="eb087-114">Zusammen mit diesen Microsoft 365 defender-spezifischen APIs stellen unsere anderen Sicherheitsprodukte zusätzliche [APIs](api-articles.md) bereit, damit Sie ihre einzigartigen Funktionen nutzen können.</span><span class="sxs-lookup"><span data-stu-id="eb087-114">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="eb087-115">Der Übergang zum einheitlichen Portal sollte sich nicht auf die PowerBi-Dashboards auswirken, die auf Microsoft Defender for Endpoint-APIs basieren.</span><span class="sxs-lookup"><span data-stu-id="eb087-115">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="eb087-116">Sie können unabhängig vom interaktiven Portalübergang weiterhin mit den vorhandenen APIs arbeiten.</span><span class="sxs-lookup"><span data-stu-id="eb087-116">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="eb087-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb087-117">Learn more</span></span>

| <span data-ttu-id="eb087-118">**Informationen zum Zugriff auf die APIs**</span><span class="sxs-lookup"><span data-stu-id="eb087-118">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="eb087-119">Informationen zu API-Kontingenten und -Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="eb087-119">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="eb087-120">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="eb087-120">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="eb087-121">**Erstellen von Apps**</span><span class="sxs-lookup"><span data-stu-id="eb087-121">**Build apps**</span></span> |
| [<span data-ttu-id="eb087-122">Erstellen einer "Hello world"-App</span><span class="sxs-lookup"><span data-stu-id="eb087-122">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="eb087-123">Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Namen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="eb087-123">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="eb087-124">Erstellen einer App für den Zugriff Microsoft 365 Defender ohne Benutzer</span><span class="sxs-lookup"><span data-stu-id="eb087-124">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="eb087-125">Erstellen einer App mit Mehr-Mandanten-Partnerzugriff auf Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="eb087-125">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="eb087-126">**Problembehandlung und Wartung Ihrer Apps**</span><span class="sxs-lookup"><span data-stu-id="eb087-126">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="eb087-127">Verstehen von API-Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="eb087-127">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="eb087-128">Verwalten von Geheimschlüsseln in Ihren Apps mit Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="eb087-128">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="eb087-129">Implementieren der OAuth 2.0-Autorisierung für die Benutzer-Anmeldung</span><span class="sxs-lookup"><span data-stu-id="eb087-129">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |