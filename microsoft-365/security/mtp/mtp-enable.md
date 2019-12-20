---
title: Aktivieren von Microsoft Threat Protection im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Microsoft Threat Protection aktivieren und Ihre Reaktionen auf Sicherheitsvorfälle ergänzen können.
keywords: Erste Schritte, MTP, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherorte
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 7790e079d4b39b5d41961a26bb17009adb1bec1d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808450"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="80efa-104">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="80efa-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="80efa-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="80efa-105">**Applies to:**</span></span>
- <span data-ttu-id="80efa-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="80efa-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="80efa-107">Microsoft Threat Protection vereinheitlicht Ihren Reaktionsprozess auf Sicherheitsvorfälle durch die Integration der wichtigsten Funktionen von Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security und Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="80efa-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="80efa-108">Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="80efa-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-your-eligibility"></a><span data-ttu-id="80efa-109">Überprüfen Sie Ihre Berechtigung</span><span class="sxs-lookup"><span data-stu-id="80efa-109">Check your eligibility</span></span>
<span data-ttu-id="80efa-110">Kunden, die über eine Microsoft 365 E5- oder eine entsprechende Lizenz verfügen, können Microsoft Threat Protection verwenden.</span><span class="sxs-lookup"><span data-stu-id="80efa-110">Customers with a Microsoft 365 E5 or equivalent license can use Microsoft Threat Protection.</span></span> <span data-ttu-id="80efa-111">Weitere Informationen finden Sie unter [Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="80efa-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="80efa-112">Verwenden des Diensts – erste Schritte</span><span class="sxs-lookup"><span data-stu-id="80efa-112">Start using the service</span></span>
<span data-ttu-id="80efa-113">Durch die Aktivierung des Microsoft Threat Protection-Diensts werden Daten aus den verschiedenen integrierten Diensten zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="80efa-113">Turning on the Microsoft Threat Protection service aggregates data from the various integrated services.</span></span> <span data-ttu-id="80efa-114">Diese Daten werden zentral verarbeitet und gespeichert, um neue Erkenntnisse zu gewinnen und um zentralisierte Reaktionsabläufe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="80efa-114">The data will be processed and stored centrally to identify new insights and to make centralized response workflows possible.</span></span>

<span data-ttu-id="80efa-115">Vor der Aktivierung des Dienstes werden im Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) die Optionen **Vorfälle** und **Info-Center** nicht im Menü angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80efa-115">Before you turn the service on, Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) does not show the **Incidents** and the **Action center** options on the menu.</span></span>

<span data-ttu-id="80efa-116">![Abbildung des Microsoft 365 Security Center-Menüs ohne Microsoft Threat Protection-Funktionen](../images/mtp-off.png)
*Microsoft 365 Security Center mit deaktiviertem Microsoft Threat Protection*</span><span class="sxs-lookup"><span data-stu-id="80efa-116">![Image of Microsoft 365 security center menu without Microsoft Threat Protection features](../images/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="80efa-117">Wenn Sie den Microsoft Threat Protection-Dienst aktivieren möchten, wechseln Sie zu **Einstellungen** > **Microsoft Threat Protection** > **Aktivieren/Deaktivieren** im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="80efa-117">To turn the Microsoft Threat Protection service on, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="80efa-118">Sie müssen ein globaler Administrator oder ein Sicherheitsadministrator in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) sein, um diese Aktion ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="80efa-118">You will need to be a global administrator or a security administrator in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to perform this task.</span></span>

<span data-ttu-id="80efa-119">Wenn Microsoft Defender ATP für Ihre Organisation bereitgestellt wurde, werden die Daten im selben Rechenzentrumsspeicherort gespeichert und verarbeitet, den Sie für [Ihre Microsoft Defender ATP-Daten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="80efa-119">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="80efa-120">Wenn Sie nicht über Microsoft Defender ATP verfügen, werden Sie aufgefordert, einen neuen Rechenzentrumsspeicherort speziell für Microsoft Threat Protection zu wählen.</span><span class="sxs-lookup"><span data-stu-id="80efa-120">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> <span data-ttu-id="80efa-121">Sie müssen die entsprechende Zustimmung geben, bevor Daten zwischen den Diensten geteilt und zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="80efa-121">You will need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="80efa-122">Vergewissern Sie sich, dass der Dienst aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="80efa-122">Confirm that the service is on</span></span>
<span data-ttu-id="80efa-123">Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="80efa-123">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="80efa-124">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="80efa-124">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="80efa-125">Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="80efa-125">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="80efa-126">[Erweiterte Suchfunktionen](advanced-hunting-overview.md) für die bestehende **Such**-Seite</span><span class="sxs-lookup"><span data-stu-id="80efa-126">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="80efa-127">![Abbildung des Microsoft 365 Security Center-Menüs mit Microsoft Threat Protection-Funktionen](../images/mtp-on.png)
*Microsoft 365 Security Center mit Funktionen für die Verwaltung von Vorfällen und anderen Microsoft Threat Protection-Funktionen*</span><span class="sxs-lookup"><span data-stu-id="80efa-127">![Image of Microsoft 365 security center menu with Microsoft Threat Protection features](../images/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection features*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="80efa-128">Abrufen von Azure ATP-Daten</span><span class="sxs-lookup"><span data-stu-id="80efa-128">Getting Azure ATP data</span></span>
<span data-ttu-id="80efa-129">Stellen Sie sicher, dass Microsoft Cloud App Security und die Azure ATP-Integration aktiviert sind, um Azure ATP-Daten für Microsoft Threat Protection freizugeben.</span><span class="sxs-lookup"><span data-stu-id="80efa-129">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> <span data-ttu-id="80efa-130">Erfahren Sie mehr über [diese Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span><span class="sxs-lookup"><span data-stu-id="80efa-130">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span>


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="80efa-131">Deaktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="80efa-131">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="80efa-132">Wenn Sie Microsoft Threat Protection nicht länger verwenden möchten, wechseln Sie zu **Einstellungen** > **Microsoft Threat Protection** > **Aktivieren/Deaktivieren** im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="80efa-132">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="80efa-133">Heben Sie die Auswahl **Microsoft Threat Protection aktivieren** auf, und speichern Sie die Änderung.</span><span class="sxs-lookup"><span data-stu-id="80efa-133">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="80efa-134">Die Daten werden dauerhaft gelöscht, und die entsprechenden Funktionen werden aus dem Microsoft 365 Security Center entfernt.</span><span class="sxs-lookup"><span data-stu-id="80efa-134">Data will be permanently deleted and corresponding features will be removed from Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="80efa-135">Unterstützung erhalten</span><span class="sxs-lookup"><span data-stu-id="80efa-135">Get assistance</span></span>

<span data-ttu-id="80efa-136">Microsoft-Mitarbeiter können Sie dabei unterstützen, den Dienst und die zugehörigen Ressourcen in Ihrem Mandanten bereitzustellen oder die Bereitstellung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="80efa-136">Microsoft staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="80efa-137">Wenn Sie Hilfe benötigen, wenden Sie sich an den [Premier Support](https://go.microsoft.com/fwlink/?LinkID=733758).</span><span class="sxs-lookup"><span data-stu-id="80efa-137">For assistance, [contact premier support](https://go.microsoft.com/fwlink/?LinkID=733758).</span></span>

## <a name="related-topics"></a><span data-ttu-id="80efa-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="80efa-138">Related topics</span></span>

- [<span data-ttu-id="80efa-139">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="80efa-139">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="80efa-140">Lizenzierungsanforderungen und andere Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="80efa-140">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="80efa-141">Übersicht über Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="80efa-141">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="80efa-142">Übersicht über Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="80efa-142">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="80efa-143">Übersicht über Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="80efa-143">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="80efa-144">Übersicht über Azure ATP</span><span class="sxs-lookup"><span data-stu-id="80efa-144">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="80efa-145">Übersicht über Microsoft Defender ATP und Datenspeicherung</span><span class="sxs-lookup"><span data-stu-id="80efa-145">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
