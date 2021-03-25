---
title: Voraussetzungen & Berechtigungen – Bedrohungs- und Sicherheitsrisikoverwaltung
description: Bevor Sie mit der Verwaltung von Bedrohungen und Sicherheitslücken beginnen, stellen Sie sicher, dass Sie über die entsprechenden Konfigurationen und Berechtigungen verfügen.
keywords: Voraussetzungen & sicherheitsrisikoverwaltungsberechtigungen, Voraussetzungen für die Bedrohungs- und Sicherheitsrisikoverwaltung, MDATP-TVM-Berechtigungen, Sicherheitsrisikoverwaltung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ca095a7a65a114182d736176840fdd4e651a8646
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066807"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="b831a-104">Voraussetzungen & Berechtigungen – Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="b831a-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b831a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b831a-105">**Applies to:**</span></span>

- [<span data-ttu-id="b831a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b831a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b831a-107">Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="b831a-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b831a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b831a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b831a-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b831a-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b831a-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b831a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="b831a-111">Stellen Sie sicher, dass Ihre Geräte:</span><span class="sxs-lookup"><span data-stu-id="b831a-111">Ensure that your devices:</span></span>

- <span data-ttu-id="b831a-112">Werden in Microsoft Defender for Endpoint onboarded</span><span class="sxs-lookup"><span data-stu-id="b831a-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="b831a-113">Ausführen [unterstützter Betriebssysteme und Plattformen](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="b831a-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="b831a-114">Die folgenden obligatorischen Updates müssen in Ihrem Netzwerk installiert und bereitgestellt werden, um die Erkennungsraten für Sicherheitslücken zu erhöhen:</span><span class="sxs-lookup"><span data-stu-id="b831a-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="b831a-115">Freigabe</span><span class="sxs-lookup"><span data-stu-id="b831a-115">Release</span></span> | <span data-ttu-id="b831a-116">Sicherheitsupdate KB-Nummer und Link</span><span class="sxs-lookup"><span data-stu-id="b831a-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="b831a-117">Windows 10 Version 1709</span><span class="sxs-lookup"><span data-stu-id="b831a-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="b831a-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) und [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="b831a-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="b831a-119">Windows 10 Version 1803</span><span class="sxs-lookup"><span data-stu-id="b831a-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="b831a-120">[KB4493464](https://support.microsoft.com/help/4493464) und [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="b831a-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="b831a-121">Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="b831a-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="b831a-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="b831a-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="b831a-123">Windows 10 Version 1903</span><span class="sxs-lookup"><span data-stu-id="b831a-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="b831a-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="b831a-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="b831a-125">Werden in [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) und  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) onboarded, um bedrohungs- und sicherheitsrisikobedrohungen zu helfen.</span><span class="sxs-lookup"><span data-stu-id="b831a-125">Are onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="b831a-126">Wenn Sie Configuration Manager verwenden, aktualisieren Sie Ihre Konsole auf die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="b831a-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="b831a-127">**Hinweis:** Wenn Sie die Intune-Verbindung aktiviert haben, erhalten Sie eine Option zum Erstellen einer Intune-Sicherheitsaufgabe beim Erstellen einer Korrekturanforderung.</span><span class="sxs-lookup"><span data-stu-id="b831a-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="b831a-128">Diese Option wird nicht angezeigt, wenn die Verbindung nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b831a-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="b831a-129">Mindestens eine Sicherheitsempfehlung, die auf der Geräteseite angezeigt werden kann</span><span class="sxs-lookup"><span data-stu-id="b831a-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="b831a-130">Markiert oder als gemeinsam verwaltet gekennzeichnet</span><span class="sxs-lookup"><span data-stu-id="b831a-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="b831a-131">Relevante Berechtigungsoptionen</span><span class="sxs-lookup"><span data-stu-id="b831a-131">Relevant permission options</span></span>

1. <span data-ttu-id="b831a-132">Melden Sie sich beim Microsoft Defender Security Center mit einem Konto an, dem ein Sicherheitsadministrator oder eine globale Administratorrolle zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b831a-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="b831a-133">Wählen Sie im Navigationsbereich Einstellungen **> Rollen aus.**</span><span class="sxs-lookup"><span data-stu-id="b831a-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="b831a-134">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="b831a-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="b831a-135">Anzeigen von Daten</span><span class="sxs-lookup"><span data-stu-id="b831a-135">View data</span></span>

- <span data-ttu-id="b831a-136">**Sicherheitsvorgänge** – Anzeigen aller Daten zu Sicherheitsvorgängen im Portal</span><span class="sxs-lookup"><span data-stu-id="b831a-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="b831a-137">**Bedrohungs- und Sicherheitsrisikoverwaltung** – Anzeigen von Daten zur Verwaltung von Bedrohungen und Sicherheitslücken im Portal</span><span class="sxs-lookup"><span data-stu-id="b831a-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="b831a-138">Aktive Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="b831a-138">Active remediation actions</span></span>

- <span data-ttu-id="b831a-139">**Sicherheitsvorgänge** – Ergreifen von Reaktionsaktionen, Genehmigen oder Schließen ausstehender Korrekturaktionen, Verwalten zulässiger/blockierter Listen für Automatisierung und Indikatoren</span><span class="sxs-lookup"><span data-stu-id="b831a-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="b831a-140">**Bedrohungs- und Sicherheitsrisikoverwaltung – Ausnahmebehandlung** – Erstellen neuer Ausnahmen und Verwalten aktiver Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="b831a-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="b831a-141">**Bedrohungs- und Sicherheitsrisikoverwaltung – Behandlung** von Abhilfemaßnahmen – Übermitteln neuer Behebungsanforderungen, Erstellen von Tickets und Verwalten vorhandener Abhilfemaßnahmen</span><span class="sxs-lookup"><span data-stu-id="b831a-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="b831a-142">Weitere Informationen finden Sie unter [RBAC-Berechtigungsoptionen.](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="b831a-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="b831a-143">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="b831a-143">Related articles</span></span>

- [<span data-ttu-id="b831a-144">Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="b831a-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b831a-145">Unterstützte Betriebssysteme und Plattformen</span><span class="sxs-lookup"><span data-stu-id="b831a-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="b831a-146">Zuweisen des Gerätewerts</span><span class="sxs-lookup"><span data-stu-id="b831a-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="b831a-147">Dashboard zur Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="b831a-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

