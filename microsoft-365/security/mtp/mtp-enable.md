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
ms.openlocfilehash: fa970b28939ad43bf6a2717e603013277bc9130f
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569170"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="b09af-104">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b09af-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="b09af-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b09af-105">**Applies to:**</span></span>
- <span data-ttu-id="b09af-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b09af-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b09af-107">Microsoft Threat Protection vereinheitlicht Ihren Reaktionsprozess auf Sicherheitsvorfälle durch die Integration der wichtigsten Funktionen von Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security und Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="b09af-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="b09af-108">Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="b09af-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="b09af-109">Um den optimalen Schutz zu erzielen und Microsoft Threat Protection zu optimieren, wird empfohlen, alle anwendbaren unterstützten Dienste in Ihrem Netzwerk bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b09af-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="b09af-110">Weitere Informationen finden [Sie unter Deploying supported Services](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="b09af-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="b09af-111">Überprüfen der Lizenz Berechtigung und der erforderlichen Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b09af-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="b09af-112">Eine Microsoft 365 E5, E5-oder A5-Lizenz oder eine gültige Kombination von Lizenzen bietet Zugriff auf unterstützte Dienste und berechtigt Sie zur Verwendung von Microsoft Threat Protection im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="b09af-112">A Microsoft 365 E5, E5 Security, or A5 license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

<span data-ttu-id="b09af-113">Ausführliche Lizenzierungsinformationen finden [Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="b09af-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="b09af-114">Überprüfen der Rolle</span><span class="sxs-lookup"><span data-stu-id="b09af-114">Check your role</span></span>
<span data-ttu-id="b09af-115">Sie müssen ein **globaler Administrator** oder ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft Threat Protection zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b09af-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="b09af-116">Anzeigen ihrer Rollen in Azure AD</span><span class="sxs-lookup"><span data-stu-id="b09af-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="b09af-117">Verwenden des Diensts – erste Schritte</span><span class="sxs-lookup"><span data-stu-id="b09af-117">Start using the service</span></span>
<span data-ttu-id="b09af-118">Microsoft Threat Protection aggregiert Daten aus den verschiedenen integrierten Diensten.</span><span class="sxs-lookup"><span data-stu-id="b09af-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="b09af-119">Die Daten werden zentral verarbeitet und gespeichert, um neue Erkenntnisse zu identifizieren und um zentralisierte Antwort Workflows zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b09af-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="b09af-120">Bevor Sie den Dienst aktivieren, zeigt das Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) die Microsoft Threat Protection-Willkommensseite an, wenn Sie **Vorfälle**, das **Aktionscenter**oder die **Suche** im Navigationsbereich auswählen.</span><span class="sxs-lookup"><span data-stu-id="b09af-120">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="b09af-121">Diese Navigationsoptionen werden nicht angezeigt, wenn Sie nicht berechtigt sind, Microsoft Threat Protection zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b09af-121">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="b09af-122">![Abbildung der Willkommensseite von Microsoft Threat Protection, die angezeigt wird, wenn Microsoft Threat Protection nicht](../../media/mtp-welcome.png)
auf der*Willkommensseite von Microsoft Threat Protection im Microsoft 365 Security Center* aktiviert wurde</span><span class="sxs-lookup"><span data-stu-id="b09af-122">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="b09af-123">Um Microsoft Threat Protection zu aktivieren, führen Sie den Vorgang einfach auf der Willkommensseite aus.</span><span class="sxs-lookup"><span data-stu-id="b09af-123">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="b09af-124">Sie können auch Microsoft Threat Protection aktivieren, indem Sie im Navigationsbereich auf **Einstellungen** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) zugreifen und **Microsoft Threat Protection**auswählen.</span><span class="sxs-lookup"><span data-stu-id="b09af-124">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="b09af-125">Wenn im Navigationsbereich keine **Einstellungen** angezeigt werden oder Sie nicht auf die Seite zugreifen können, überprüfen Sie Ihre Berechtigungen und Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="b09af-125">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="b09af-126">Auswählen des Datencenter Standorts</span><span class="sxs-lookup"><span data-stu-id="b09af-126">Select data center location</span></span>
<span data-ttu-id="b09af-127">Wenn Microsoft Defender ATP für Ihre Organisation bereitgestellt wurde, werden die Daten im selben Rechenzentrumsspeicherort gespeichert und verarbeitet, den Sie für [Ihre Microsoft Defender ATP-Daten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b09af-127">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="b09af-128">Wenn Sie nicht über Microsoft Defender ATP verfügen, werden Sie aufgefordert, einen neuen Rechenzentrumsspeicherort speziell für Microsoft Threat Protection zu wählen.</span><span class="sxs-lookup"><span data-stu-id="b09af-128">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="b09af-129">Sie müssen die Zustimmung erteilen, bevor Daten zwischen Diensten freigegeben und aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="b09af-129">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="b09af-130">Vergewissern Sie sich, dass der Dienst aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="b09af-130">Confirm that the service is on</span></span>
<span data-ttu-id="b09af-131">Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="b09af-131">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="b09af-132">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="b09af-132">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="b09af-133">Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="b09af-133">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="b09af-134">[Erweiterte Jagd](advanced-hunting-overview.md) Funktionen</span><span class="sxs-lookup"><span data-stu-id="b09af-134">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="b09af-135">![Bild des Microsoft 365 Security Center-Navigationsbereichs mit Microsoft Threat Protection](../../media/mtp-on.png)
 *-Features Microsoft 365 Security Center mit Incidents Management und anderen Microsoft Threat Protection-* Funktionen</span><span class="sxs-lookup"><span data-stu-id="b09af-135">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="b09af-136">Abrufen von Azure ATP-Daten</span><span class="sxs-lookup"><span data-stu-id="b09af-136">Getting Azure ATP data</span></span>
<span data-ttu-id="b09af-137">Stellen Sie sicher, dass Microsoft Cloud App Security und die Azure ATP-Integration aktiviert sind, um Azure ATP-Daten für Microsoft Threat Protection freizugeben.</span><span class="sxs-lookup"><span data-stu-id="b09af-137">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> <span data-ttu-id="b09af-138">Erfahren Sie mehr über [diese Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span><span class="sxs-lookup"><span data-stu-id="b09af-138">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span>


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="b09af-139">Deaktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b09af-139">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="b09af-140">Wenn Sie Microsoft Threat Protection nicht länger verwenden möchten, wechseln Sie zu **Einstellungen** > **Microsoft Threat Protection** > **Aktivieren/Deaktivieren** im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="b09af-140">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b09af-141">Heben Sie die Auswahl **Microsoft Threat Protection aktivieren** auf, und speichern Sie die Änderung.</span><span class="sxs-lookup"><span data-stu-id="b09af-141">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="b09af-142">Die entsprechenden Features werden aus dem Microsoft 365 Security Center entfernt.</span><span class="sxs-lookup"><span data-stu-id="b09af-142">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="b09af-143">Unterstützung erhalten</span><span class="sxs-lookup"><span data-stu-id="b09af-143">Get assistance</span></span>

<span data-ttu-id="b09af-144">Microsoft-Supportmitarbeiter können Ihnen helfen, den Dienst und die zugehörigen Ressourcen auf Ihrem Mandanten bereitzustellen oder zu entbinden.</span><span class="sxs-lookup"><span data-stu-id="b09af-144">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="b09af-145">Um Unterstützung zu erhalten, wählen Sie **need help?** im Microsoft 365 Security Center aus.</span><span class="sxs-lookup"><span data-stu-id="b09af-145">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b09af-146">Wenn Sie sich an den Support wenden, erwähnen Sie Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b09af-146">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b09af-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b09af-147">Related topics</span></span>

- [<span data-ttu-id="b09af-148">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b09af-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="b09af-149">Lizenzierungsanforderungen und andere Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b09af-149">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="b09af-150">Bereitstellen unterstützter Dienste</span><span class="sxs-lookup"><span data-stu-id="b09af-150">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="b09af-151">Übersicht über Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b09af-151">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="b09af-152">Übersicht über Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b09af-152">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="b09af-153">Übersicht über Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b09af-153">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="b09af-154">Übersicht über Azure ATP</span><span class="sxs-lookup"><span data-stu-id="b09af-154">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="b09af-155">Übersicht über Microsoft Defender ATP und Datenspeicherung</span><span class="sxs-lookup"><span data-stu-id="b09af-155">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
