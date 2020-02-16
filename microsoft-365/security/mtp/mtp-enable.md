---
title: Aktivieren von Microsoft Threat Protection im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Microsoft Threat Protection aktivieren und Ihre Reaktionen auf Sicherheitsvorfälle ergänzen können.
keywords: Erste Schritte, Aktivieren von MTP, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenz Berechtigung, Seite "Einstellungen"
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 8f966060ebc9a30166647b397b93f2b45356df74
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083724"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="8d57a-104">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8d57a-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="8d57a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8d57a-105">**Applies to:**</span></span>
- <span data-ttu-id="8d57a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8d57a-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8d57a-107">Microsoft Threat Protection vereinheitlicht Ihren Reaktionsprozess auf Sicherheitsvorfälle durch die Integration der wichtigsten Funktionen von Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security und Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="8d57a-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="8d57a-108">Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="8d57a-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="8d57a-109">Überprüfen der Lizenz Berechtigung und der erforderlichen Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8d57a-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="8d57a-110">Kunden mit Microsoft 365 E5, Microsoft 365 E5 Security oder einer äquivalenten Kombination von Lizenzen können Microsoft Threat Protection verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d57a-110">Customers with Microsoft 365 E5, Microsoft 365 E5 Security, or an equivalent combination of licenses can use Microsoft Threat Protection.</span></span> <span data-ttu-id="8d57a-111">Weitere Informationen finden Sie unter [Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="8d57a-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

<span data-ttu-id="8d57a-112">Sie müssen ein **globaler Administrator** oder ein **Sicherheitsadministrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) sein, um Microsoft Threat Protection zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8d57a-112">You must be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to turn on Microsoft Threat Protection.</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="8d57a-113">Verwenden des Diensts – erste Schritte</span><span class="sxs-lookup"><span data-stu-id="8d57a-113">Start using the service</span></span>
<span data-ttu-id="8d57a-114">Microsoft Threat Protection aggregiert Daten aus den verschiedenen integrierten Diensten.</span><span class="sxs-lookup"><span data-stu-id="8d57a-114">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="8d57a-115">Die Daten werden zentral verarbeitet und gespeichert, um neue Erkenntnisse zu identifizieren und um zentralisierte Antwort Workflows zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8d57a-115">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="8d57a-116">Bevor Sie den Dienst aktivieren, zeigt das Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) keine **Vorfälle** und **Aktionscenter** Optionen im Navigationsbereich an.</span><span class="sxs-lookup"><span data-stu-id="8d57a-116">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) doesn't show the **Incidents** and the **Action center** options in the navigation pane.</span></span>

<span data-ttu-id="8d57a-117">![Bild des Microsoft 365 Security Center-Navigationsbereichs ohne Microsoft Threat Protection](../../media/mtp-off.png)
-Features*Microsoft 365 Security Center mit Microsoft Threat Protection deaktiviert*</span><span class="sxs-lookup"><span data-stu-id="8d57a-117">![Image of Microsoft 365 security center navigation pane without Microsoft Threat Protection features](../../media/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="8d57a-118">Um Microsoft Threat Protection zu aktivieren, wählen Sie im Navigationsbereich die Option **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="8d57a-118">To turn on Microsoft Threat Protection, select **Settings** in the navigation pane.</span></span> <span data-ttu-id="8d57a-119">Wechseln Sie auf der **[Seite Einstellungen](https://security.microsoft.com/settings)** zu **Microsoft Threat Protection** > **Opt-in/Opt-out**.</span><span class="sxs-lookup"><span data-stu-id="8d57a-119">In the **[Settings page](https://security.microsoft.com/settings)**, go to **Microsoft Threat Protection** > **Opt-in / Opt-out**.</span></span>

>[!NOTE]
><span data-ttu-id="8d57a-120">Wenn im Navigationsbereich keine **Einstellungen** angezeigt werden oder Sie nicht auf die Seite zugreifen können, überprüfen Sie Ihre Berechtigungen und Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="8d57a-120">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="8d57a-121">Auswählen des Datencenter Standorts</span><span class="sxs-lookup"><span data-stu-id="8d57a-121">Select data center location</span></span>
<span data-ttu-id="8d57a-122">Wenn Microsoft Defender ATP für Ihre Organisation bereitgestellt wurde, werden die Daten im selben Rechenzentrumsspeicherort gespeichert und verarbeitet, den Sie für [Ihre Microsoft Defender ATP-Daten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="8d57a-122">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="8d57a-123">Wenn Sie nicht über Microsoft Defender ATP verfügen, werden Sie aufgefordert, einen neuen Rechenzentrumsspeicherort speziell für Microsoft Threat Protection zu wählen.</span><span class="sxs-lookup"><span data-stu-id="8d57a-123">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="8d57a-124">Sie müssen die Zustimmung erteilen, bevor Daten zwischen Diensten freigegeben und aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="8d57a-124">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="8d57a-125">Vergewissern Sie sich, dass der Dienst aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="8d57a-125">Confirm that the service is on</span></span>
<span data-ttu-id="8d57a-126">Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="8d57a-126">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="8d57a-127">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="8d57a-127">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="8d57a-128">Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="8d57a-128">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="8d57a-129">[Erweiterte Suchfunktionen](advanced-hunting-overview.md) für die bestehende **Such**-Seite</span><span class="sxs-lookup"><span data-stu-id="8d57a-129">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="8d57a-130">![Bild des Microsoft 365 Security Center-Navigationsbereichs mit Microsoft Threat Protection](../../media/mtp-on.png)
 *-Features Microsoft 365 Security Center mit Incidents Management und anderen Microsoft Threat Protection-* Funktionen</span><span class="sxs-lookup"><span data-stu-id="8d57a-130">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="8d57a-131">Abrufen von Azure ATP-Daten</span><span class="sxs-lookup"><span data-stu-id="8d57a-131">Getting Azure ATP data</span></span>
<span data-ttu-id="8d57a-132">Stellen Sie sicher, dass Microsoft Cloud App Security und die Azure ATP-Integration aktiviert sind, um Azure ATP-Daten für Microsoft Threat Protection freizugeben.</span><span class="sxs-lookup"><span data-stu-id="8d57a-132">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> <span data-ttu-id="8d57a-133">Erfahren Sie mehr über [diese Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span><span class="sxs-lookup"><span data-stu-id="8d57a-133">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span>


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="8d57a-134">Deaktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8d57a-134">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="8d57a-135">Wenn Sie Microsoft Threat Protection nicht länger verwenden möchten, wechseln Sie zu **Einstellungen** > **Microsoft Threat Protection** > **Aktivieren/Deaktivieren** im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="8d57a-135">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="8d57a-136">Heben Sie die Auswahl **Microsoft Threat Protection aktivieren** auf, und speichern Sie die Änderung.</span><span class="sxs-lookup"><span data-stu-id="8d57a-136">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="8d57a-137">Daten werden endgültig gelöscht, und die entsprechenden Features werden aus dem Microsoft 365 Security Center entfernt.</span><span class="sxs-lookup"><span data-stu-id="8d57a-137">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="8d57a-138">Unterstützung erhalten</span><span class="sxs-lookup"><span data-stu-id="8d57a-138">Get assistance</span></span>

<span data-ttu-id="8d57a-139">Microsoft-Supportmitarbeiter können Ihnen helfen, den Dienst und die zugehörigen Ressourcen auf Ihrem Mandanten bereitzustellen oder zu entbinden.</span><span class="sxs-lookup"><span data-stu-id="8d57a-139">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="8d57a-140">Um Unterstützung zu erhalten, wählen Sie **need help?** im Microsoft 365 Security Center aus.</span><span class="sxs-lookup"><span data-stu-id="8d57a-140">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="8d57a-141">Wenn Sie sich an den Support wenden, erwähnen Sie Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="8d57a-141">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d57a-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8d57a-142">Related topics</span></span>

- [<span data-ttu-id="8d57a-143">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8d57a-143">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="8d57a-144">Lizenzierungsanforderungen und andere Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8d57a-144">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="8d57a-145">Übersicht über Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8d57a-145">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="8d57a-146">Übersicht über Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="8d57a-146">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="8d57a-147">Übersicht über Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8d57a-147">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="8d57a-148">Übersicht über Azure ATP</span><span class="sxs-lookup"><span data-stu-id="8d57a-148">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="8d57a-149">Übersicht über Microsoft Defender ATP und Datenspeicherung</span><span class="sxs-lookup"><span data-stu-id="8d57a-149">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
