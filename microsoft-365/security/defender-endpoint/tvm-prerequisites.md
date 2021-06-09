---
title: Voraussetzungen & Berechtigungen – Bedrohungs- und Sicherheitsrisikomanagement
description: Bevor Sie mit der Verwendung von Bedrohungs- und Sicherheitsrisikomanagement beginnen, stellen Sie sicher, dass Sie über die entsprechenden Konfigurationen und Berechtigungen verfügen.
keywords: Voraussetzungen für bedrohungs- & Sicherheitsrisikomanagement Berechtigungen, Bedrohungs- und Sicherheitsrisikomanagement Berechtigungsvoraussetzungen, Microsoft Defender für Endpunkt-TVM-Berechtigungsvoraussetzungen, Sicherheitsrisikomanagement
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843950"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="2ea0e-104">Voraussetzungen & Berechtigungen – Bedrohungs- und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="2ea0e-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ea0e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2ea0e-105">**Applies to:**</span></span>

- [<span data-ttu-id="2ea0e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2ea0e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2ea0e-107">Bedrohung und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="2ea0e-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="2ea0e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ea0e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2ea0e-109">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="2ea0e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2ea0e-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2ea0e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="2ea0e-111">Stellen Sie sicher, dass Ihre Geräte:</span><span class="sxs-lookup"><span data-stu-id="2ea0e-111">Ensure that your devices:</span></span>

- <span data-ttu-id="2ea0e-112">Sind in Microsoft Defender für Endpunkt integriert</span><span class="sxs-lookup"><span data-stu-id="2ea0e-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="2ea0e-113">Ausführen [unterstützter Betriebssysteme und Plattformen](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="2ea0e-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="2ea0e-114">Installieren und bereitstellen Sie die folgenden obligatorischen Updates in Ihrem Netzwerk, um die Erkennungsraten ihrer Sicherheitslücken zu erhöhen:</span><span class="sxs-lookup"><span data-stu-id="2ea0e-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="2ea0e-115">Freigabe</span><span class="sxs-lookup"><span data-stu-id="2ea0e-115">Release</span></span> | <span data-ttu-id="2ea0e-116">KB-Nummer und Verknüpfung für Sicherheitsupdate</span><span class="sxs-lookup"><span data-stu-id="2ea0e-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="2ea0e-117">Windows 10 Version 1709</span><span class="sxs-lookup"><span data-stu-id="2ea0e-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="2ea0e-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) und [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="2ea0e-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="2ea0e-119">Windows 10 Version 1803</span><span class="sxs-lookup"><span data-stu-id="2ea0e-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="2ea0e-120">[KB4493464](https://support.microsoft.com/help/4493464) und [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="2ea0e-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="2ea0e-121">Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="2ea0e-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="2ea0e-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="2ea0e-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="2ea0e-123">Windows 10 Version 1903</span><span class="sxs-lookup"><span data-stu-id="2ea0e-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="2ea0e-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="2ea0e-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="2ea0e-125">Sind in [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) und [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) integriert, um von Bedrohungs- und Sicherheitsrisikomanagement gefundene Bedrohungen zu beheben.</span><span class="sxs-lookup"><span data-stu-id="2ea0e-125">Are onboarded to [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="2ea0e-126">Wenn Sie Configuration Manager verwenden, aktualisieren Sie Die Konsole auf die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="2ea0e-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="2ea0e-127">**Hinweis:** Wenn Sie die Intune-Verbindung aktiviert haben, erhalten Sie eine Option zum Erstellen einer Intune-Sicherheitsaufgabe beim Erstellen einer Wartungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="2ea0e-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="2ea0e-128">Diese Option wird nicht angezeigt, wenn die Verbindung nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2ea0e-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="2ea0e-129">Sie haben mindestens eine Sicherheitsempfehlung, die auf der Geräteseite angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ea0e-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="2ea0e-130">Als coverwaltet gekennzeichnet oder gekennzeichnet werden</span><span class="sxs-lookup"><span data-stu-id="2ea0e-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="2ea0e-131">Relevante Berechtigungsoptionen</span><span class="sxs-lookup"><span data-stu-id="2ea0e-131">Relevant permission options</span></span>

1. <span data-ttu-id="2ea0e-132">Melden Sie sich bei Microsoft Defender Security Center mit einem Konto an, dem ein Sicherheitsadministrator oder eine globale Administratorrolle zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="2ea0e-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="2ea0e-133">Wählen Sie im Navigationsbereich **Einstellungen > Rollen** aus.</span><span class="sxs-lookup"><span data-stu-id="2ea0e-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="2ea0e-134">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="2ea0e-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="2ea0e-135">Anzeigen von Daten</span><span class="sxs-lookup"><span data-stu-id="2ea0e-135">View data</span></span>

- <span data-ttu-id="2ea0e-136">**Sicherheitsvorgänge** – Anzeigen aller Sicherheitsvorgänge im Portal</span><span class="sxs-lookup"><span data-stu-id="2ea0e-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="2ea0e-137">**Bedrohung und Sicherheitsrisikomanagement** – Anzeigen Bedrohungs- und Sicherheitsrisikomanagement Daten im Portal</span><span class="sxs-lookup"><span data-stu-id="2ea0e-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="2ea0e-138">Aktive Abhilfemaßnahmen</span><span class="sxs-lookup"><span data-stu-id="2ea0e-138">Active remediation actions</span></span>

- <span data-ttu-id="2ea0e-139">**Sicherheitsvorgänge** – Ergreifen von Reaktionsaktionen, Genehmigen oder Schließen ausstehender Korrekturaktionen, Verwalten zugelassener/blockierter Listen für Automatisierung und Indikatoren</span><span class="sxs-lookup"><span data-stu-id="2ea0e-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="2ea0e-140">**Bedrohung und Sicherheitsrisikomanagement – Ausnahmebehandlung** – Erstellen neuer Ausnahmen und Verwalten aktiver Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="2ea0e-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="2ea0e-141">**Bedrohung und Sicherheitsrisikomanagement – Behandlung** von Korrekturen – Übermitteln neuer Wartungsanforderungen, Erstellen von Tickets und Verwalten vorhandener Wartungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="2ea0e-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="2ea0e-142">Weitere Informationen finden Sie unter [RBAC-Berechtigungsoptionen](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="2ea0e-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="2ea0e-143">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="2ea0e-143">Related articles</span></span>

- [<span data-ttu-id="2ea0e-144">Übersicht über Bedrohungen und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="2ea0e-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="2ea0e-145">Unterstützte Betriebssysteme und Plattformen</span><span class="sxs-lookup"><span data-stu-id="2ea0e-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="2ea0e-146">Zuweisen des Gerätewerts</span><span class="sxs-lookup"><span data-stu-id="2ea0e-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="2ea0e-147">Dashboard für Bedrohungen und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="2ea0e-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

