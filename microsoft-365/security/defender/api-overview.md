---
title: Übersicht über Microsoft 365 Defender-APIs
description: Erfahren Sie mehr über die verfügbaren APIs in Microsoft 365 Defender
keywords: API, APIs, Übersicht, Vorfall, Vorfälle, Bedrohungssuche, Microsoft 365 Defender
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
ms.openlocfilehash: 2ca601c3c68df9f9f1cc4fb90bcfbe907850ce91
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029729"
---
# <a name="overview-of-microsoft-365-defender-apis"></a><span data-ttu-id="16fde-104">Übersicht über Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="16fde-104">Overview of Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="16fde-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="16fde-105">**Applies to:**</span></span>

- <span data-ttu-id="16fde-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16fde-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16fde-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="16fde-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="16fde-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="16fde-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="16fde-109">Microsoft 365 Defender basiert auf einer integrationsfähigen Plattform.</span><span class="sxs-lookup"><span data-stu-id="16fde-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="16fde-110">Verwenden Sie die Microsoft 365 Defender-APIs, um Workflows basierend auf den freigegebenen Vorfall- und erweiterten Suchtabellen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="16fde-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="16fde-111">**[Kombinierte Vorfallwarteschlange](api-incident.md)** – Konzentrieren Sie sich auf das, was wichtig ist, indem Sie den gesamten Angriffsbereich und alle betroffenen Ressourcen unter der Vorfall-API gruppieren.</span><span class="sxs-lookup"><span data-stu-id="16fde-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="16fde-112">**[Produktübergreifende Bedrohungssuche](api-advanced-hunting.md)** – Nutzen Sie das Organisationswissen Ihres Sicherheitsteams, um nach Gefährdungszeichen zu suchen, indem Sie Eigene benutzerdefinierte Abfragen erstellen, um rohe Daten zu durchsuchen, die über mehrere Schutzprodukte gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="16fde-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="16fde-113">Verwenden Sie die [Streaming-API,](../defender-endpoint/raw-data-export.md) um Echtzeitereignisse und Warnungen von Instanzen zu versenden, sobald sie innerhalb eines einzelnen Datenstroms auftreten.</span><span class="sxs-lookup"><span data-stu-id="16fde-113">Use the [Streaming API](../defender-endpoint/raw-data-export.md) to ship real-time events and alerts from instances as they occur within a single data stream.</span></span>

<span data-ttu-id="16fde-114">Zusammen mit diesen Microsoft 365 Defender-spezifischen APIs macht jedes unserer anderen Sicherheitsprodukte [zusätzliche APIs](api-articles.md) verfügbar, die Ihnen dabei helfen, ihre einzigartigen Funktionen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="16fde-114">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="16fde-115">Der Übergang zum einheitlichen Portal sollte sich nicht auf die PowerBi-Dashboards auswirken, die auf Microsoft Defender für Endpunkt-APIs basieren.</span><span class="sxs-lookup"><span data-stu-id="16fde-115">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="16fde-116">Sie können weiterhin mit den vorhandenen APIs arbeiten, unabhängig vom Übergang zum interaktiven Portal.</span><span class="sxs-lookup"><span data-stu-id="16fde-116">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>

## <a name="learn-more"></a><span data-ttu-id="16fde-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16fde-117">Learn more</span></span>

| <span data-ttu-id="16fde-118">**Grundlegendes zum Zugriff auf die APIs**</span><span class="sxs-lookup"><span data-stu-id="16fde-118">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="16fde-119">Informationen zu API-Kontingenten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="16fde-119">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="16fde-120">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="16fde-120">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="16fde-121">**Erstellen von Apps**</span><span class="sxs-lookup"><span data-stu-id="16fde-121">**Build apps**</span></span> |
| [<span data-ttu-id="16fde-122">Erstellen einer "Hello World"-App</span><span class="sxs-lookup"><span data-stu-id="16fde-122">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="16fde-123">Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Namen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="16fde-123">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="16fde-124">Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer</span><span class="sxs-lookup"><span data-stu-id="16fde-124">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="16fde-125">Erstellen einer App mit mehrinstanzenfähigem Partnerzugriff auf Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="16fde-125">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="16fde-126">**Problembehandlung und Verwaltung Ihrer Apps**</span><span class="sxs-lookup"><span data-stu-id="16fde-126">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="16fde-127">Grundlegendes zu API-Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="16fde-127">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="16fde-128">Verwalten geheimer Schlüssel in Ihren Apps mit Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="16fde-128">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="16fde-129">Implementieren der OAuth 2.0-Autorisierung für die Benutzeranmeldung</span><span class="sxs-lookup"><span data-stu-id="16fde-129">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |