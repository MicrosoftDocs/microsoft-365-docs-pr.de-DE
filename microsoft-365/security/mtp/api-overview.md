---
title: Übersicht über Microsoft 365 Defender-APIs
description: Erfahren Sie mehr über die verfügbaren APIs in Microsoft 365 Defender
keywords: API, APIs, Übersicht, Vorfall, Vorfälle, Bedrohungs Suche, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719190"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="901da-104">Übersicht über Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="901da-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="901da-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="901da-105">**Applies to:**</span></span>

- <span data-ttu-id="901da-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="901da-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="901da-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="901da-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="901da-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="901da-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="901da-109">Microsoft 365 Defender ist auf einer integrationsfähigen Plattform aufgebaut.</span><span class="sxs-lookup"><span data-stu-id="901da-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="901da-110">Verwenden Sie die Microsoft 365 Defender-APIs, um Workflows basierend auf den freigegebenen Vorfällen und erweiterten Jagd Tabellen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="901da-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="901da-111">**[Kombinierte Vorfälle-Warteschlange](api-incident.md)** – konzentrieren Sie sich auf das, was kritisch ist, indem Sie den vollständigen Angriffsbereich und alle betroffenen Objekte zusammen mit der Vorfall-API gruppieren.</span><span class="sxs-lookup"><span data-stu-id="901da-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="901da-112">**[Produktübergreifende Bedrohungs Suche](api-advanced-hunting.md)** – nutzen Sie das organisatorische wissen Ihres Sicherheitsteams, um nach Zeichen von Kompromissen zu suchen, indem Sie Ihre eigenen benutzerdefinierten Abfragen erstellen, um die Rohdaten zu Sichten, die über mehrere Schutzprodukte gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="901da-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="901da-113">Zusammen mit diesen Microsoft 365 Defender-spezifischen APIs stellen alle unsere anderen Sicherheitsprodukte [zusätzliche APIs](api-articles.md) bereit, die Ihnen dabei helfen, ihre einzigartigen Funktionen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="901da-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="901da-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="901da-114">Learn more</span></span>

| <span data-ttu-id="901da-115">**Grundlegendes zum Zugriff auf die APIs**</span><span class="sxs-lookup"><span data-stu-id="901da-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="901da-116">Informationen zu API-Kontingenten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="901da-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="901da-117">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="901da-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="901da-118">**Erstellen von Apps**</span><span class="sxs-lookup"><span data-stu-id="901da-118">**Build apps**</span></span> |
| [<span data-ttu-id="901da-119">Erstellen einer "Hello World"-App</span><span class="sxs-lookup"><span data-stu-id="901da-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="901da-120">Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="901da-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="901da-121">Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer</span><span class="sxs-lookup"><span data-stu-id="901da-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="901da-122">Erstellen einer APP mit mehr Mandanten fähigem Partner Zugriff auf Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="901da-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="901da-123">**Problembehandlung und Wartung Ihrer Apps**</span><span class="sxs-lookup"><span data-stu-id="901da-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="901da-124">Grundlegendes zu API-Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="901da-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="901da-125">Verwalten von Geheimnissen in ihren apps mit Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="901da-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="901da-126">Implementieren der OAuth 2,0-Autorisierung für die Benutzeranmeldung</span><span class="sxs-lookup"><span data-stu-id="901da-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
