---
title: Übersicht über Microsoft 365 Defender-APIs
description: Informationen zu den verfügbaren APIs in Microsoft 365 Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0fbe8751a9f82a8e264f1a38207744d091b57474
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922186"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="f6960-104">Übersicht über Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="f6960-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f6960-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f6960-105">**Applies to:**</span></span>

- <span data-ttu-id="f6960-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6960-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6960-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="f6960-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f6960-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="f6960-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="f6960-109">Microsoft 365 Defender baut auf einer integrationsbereiten Plattform auf.</span><span class="sxs-lookup"><span data-stu-id="f6960-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="f6960-110">Verwenden Sie die Microsoft 365 Defender-APIs, um Workflows basierend auf dem gemeinsam genutzten Vorfall und erweiterten Nachschlagetabellen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="f6960-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="f6960-111">**[Warteschlange für kombinierte](api-incident.md)** Vorfälle – Konzentrieren Sie sich auf das Wichtige, indem Sie den vollständigen Angriffsbereich und alle sich auswirkenden Ressourcen unter der Vorfall-API gruppieren.</span><span class="sxs-lookup"><span data-stu-id="f6960-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="f6960-112">**[Produktübergreifende](api-advanced-hunting.md)** Bedrohungssuche : Nutzen Sie das Organisationswissen Ihres Sicherheitsteams, um nach Anzeichen von Kompromissen zu fahnen, indem Sie Eigene benutzerdefinierte Abfragen erstellen, um Rohdaten zu siften, die in mehreren Schutzprodukten gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="f6960-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="f6960-113">Zusammen mit diesen microsoft 365 Defender-spezifischen APIs stellen unsere anderen Sicherheitsprodukte zusätzliche [APIs](api-articles.md) bereit, um die vorteile ihrer einzigartigen Funktionen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="f6960-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="f6960-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6960-114">Learn more</span></span>

| <span data-ttu-id="f6960-115">**Informationen zum Zugriff auf die APIs**</span><span class="sxs-lookup"><span data-stu-id="f6960-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="f6960-116">Informationen zu API-Kontingenten und -Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="f6960-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="f6960-117">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="f6960-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="f6960-118">**Erstellen von Apps**</span><span class="sxs-lookup"><span data-stu-id="f6960-118">**Build apps**</span></span> |
| [<span data-ttu-id="f6960-119">Erstellen einer "Hello world"-App</span><span class="sxs-lookup"><span data-stu-id="f6960-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="f6960-120">Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="f6960-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="f6960-121">Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer</span><span class="sxs-lookup"><span data-stu-id="f6960-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="f6960-122">Erstellen einer App mit Mehr-Mandanten-Partnerzugriff auf Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="f6960-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="f6960-123">**Problembehandlung und Wartung Ihrer Apps**</span><span class="sxs-lookup"><span data-stu-id="f6960-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="f6960-124">Verstehen von API-Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="f6960-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="f6960-125">Verwalten von Geheimschlüsseln in Ihren Apps mit Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="f6960-125">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="f6960-126">Implementieren der OAuth 2.0-Autorisierung für die Benutzer-Anmeldung</span><span class="sxs-lookup"><span data-stu-id="f6960-126">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |