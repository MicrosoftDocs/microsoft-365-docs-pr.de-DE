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
ms.openlocfilehash: 0badae0d81b52b89c47f950b889109d4b9d35dda
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844597"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="6dc3b-104">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6dc3b-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="6dc3b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6dc3b-105">**Applies to:**</span></span>
- <span data-ttu-id="6dc3b-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6dc3b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6dc3b-107">[Microsoft Threat Protection](microsoft-threat-protection.md) vereinigt ihren Vorfall Antwortprozess durch die Integration wichtiger Funktionen in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security und Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="6dc3b-108">Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="6dc3b-109">Microsoft Threat Protection wird automatisch aktiviert, wenn berechtigte Kunden mit den erforderlichen Berechtigungen Microsoft 365 Security Center besuchen.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="6dc3b-110">Lesen Sie diesen Artikel, um die verschiedenen Voraussetzungen und den Schutz von Microsoft Threat Protection zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="6dc3b-111">Überprüfen der Lizenz Berechtigung und der erforderlichen Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6dc3b-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="6dc3b-112">Eine Lizenz für ein Microsoft 365-Sicherheitsprodukt berechtigt Sie im Allgemeinen zur Verwendung von Microsoft Threat Protection im Microsoft 365 Security Center ohne zusätzliche Lizenzierungskosten.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="6dc3b-113">Es wird empfohlen, eine Sicherheitslizenz für Microsoft 365 E5, E5, A5 oder A5 oder eine gültige Kombination von Lizenzen zu erhalten, die Zugriff auf alle unterstützten Dienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="6dc3b-114">Ausführliche Lizenzierungsinformationen finden [Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="6dc3b-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="6dc3b-115">Überprüfen der Rolle</span><span class="sxs-lookup"><span data-stu-id="6dc3b-115">Check your role</span></span>
<span data-ttu-id="6dc3b-116">Sie müssen ein **globaler Administrator** oder ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft Threat Protection zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="6dc3b-117">Anzeigen ihrer Rollen in Azure AD</span><span class="sxs-lookup"><span data-stu-id="6dc3b-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="6dc3b-118">Unterstützte Dienste</span><span class="sxs-lookup"><span data-stu-id="6dc3b-118">Supported services</span></span>
<span data-ttu-id="6dc3b-119">Microsoft Threat Protection aggregiert Daten aus den verschiedenen unterstützten Diensten, die Sie bereits bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="6dc3b-120">Die Daten werden zentral verarbeitet und gespeichert, um neue Erkenntnisse zu identifizieren und um zentralisierte Antwort Workflows zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="6dc3b-121">Dies geschieht ohne Beeinträchtigung vorhandener Bereitstellungen, Einstellungen oder Daten, die den integrierten Diensten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="6dc3b-122">Um den optimalen Schutz zu erzielen und Microsoft Threat Protection zu optimieren, wird empfohlen, alle anwendbaren unterstützten Dienste in Ihrem Netzwerk bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="6dc3b-123">Weitere Informationen finden [Sie unter Deploying supported Services](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="6dc3b-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="6dc3b-124">Vor dem Starten des Diensts</span><span class="sxs-lookup"><span data-stu-id="6dc3b-124">Before starting the service</span></span>
<span data-ttu-id="6dc3b-125">Bevor Sie den Dienst aktivieren, wird im Microsoft 365-Sicherheitscenter ([Security.Microsoft.com](https://security.microsoft.com)) die Seite Microsoft Threat Protection-Einstellungen angezeigt, wenn Sie im Navigationsbereich **Vorfälle**, das **Aktionscenter**oder die **Suche** auswählen.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="6dc3b-126">Diese Navigationselemente werden nicht angezeigt, wenn Sie nicht berechtigt sind, Microsoft Threat Protection zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="6dc3b-127">![Abbildung der Seite Microsoft Threat Protection-Einstellungen, die angezeigt wird, wenn Microsoft Threat Protection nicht auf ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft Threat Protection-Einstellungen im Microsoft 365 Security Center* aktiviert wurde</span><span class="sxs-lookup"><span data-stu-id="6dc3b-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="6dc3b-128">Starten des Diensts</span><span class="sxs-lookup"><span data-stu-id="6dc3b-128">Starting the service</span></span>
<span data-ttu-id="6dc3b-129">Wählen Sie zum Aktivieren von Microsoft Threat Protection einfach **Microsoft Threat Protection aktivieren** aus, und wenden Sie die Änderung an.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="6dc3b-130">Sie können auf diese Option auch zugreifen, indem Sie im Navigationsbereich **Einstellungen** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) auswählen und dann **Microsoft Threat Protection**auswählen.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="6dc3b-131">Wenn im Navigationsbereich keine **Einstellungen** angezeigt werden oder Sie nicht auf die Seite zugreifen können, überprüfen Sie Ihre Berechtigungen und Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="6dc3b-132">Rechenzentrumsstandort</span><span class="sxs-lookup"><span data-stu-id="6dc3b-132">Data center location</span></span>
<span data-ttu-id="6dc3b-133">Microsoft Threat Protection speichert und verarbeitet Daten am [gleichen Speicherort, der von Microsoft Defender ATP verwendet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)wird.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="6dc3b-134">Wenn Sie nicht über Microsoft Defender ATP verfügen, wird automatisch ein neuer rechenzentrumsstandort basierend auf dem Speicherort der aktiven Microsoft 365-Sicherheitsdienste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="6dc3b-135">Der ausgewählte Speicherort des Rechenzentrums wird auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-135">The selected data center location is shown in the screen.</span></span>

>[!NOTE]
><span data-ttu-id="6dc3b-136">Wählen Sie **need help?** im Microsoft 365 Security Center aus, um den Microsoft-Support zur Versorgung mit Microsoft Threat Protection an einem anderen rechenzentrumsstandort zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provision Microsoft Threat Protection in a different data center location.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="6dc3b-137">Vergewissern Sie sich, dass der Dienst aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="6dc3b-137">Confirm that the service is on</span></span>
<span data-ttu-id="6dc3b-138">Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="6dc3b-138">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="6dc3b-139">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="6dc3b-139">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="6dc3b-140">Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="6dc3b-140">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="6dc3b-141">[Erweiterte Jagd](advanced-hunting-overview.md) Funktionen</span><span class="sxs-lookup"><span data-stu-id="6dc3b-141">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="6dc3b-142">![Bild des Microsoft 365 Security Center-Navigationsbereichs mit Microsoft Threat Protection ](../../media/mtp-enable/mtp-on.png)
 *-Features Microsoft 365 Security Center mit Incidents Management und anderen Microsoft Threat Protection-* Funktionen</span><span class="sxs-lookup"><span data-stu-id="6dc3b-142">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="6dc3b-143">Abrufen von Azure ATP-Daten</span><span class="sxs-lookup"><span data-stu-id="6dc3b-143">Getting Azure ATP data</span></span>
<span data-ttu-id="6dc3b-144">Stellen Sie sicher, dass Microsoft Cloud App Security und die Azure ATP-Integration aktiviert sind, um Azure ATP-Daten für Microsoft Threat Protection freizugeben.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-144">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> <span data-ttu-id="6dc3b-145">Erfahren Sie mehr über [diese Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span><span class="sxs-lookup"><span data-stu-id="6dc3b-145">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span>


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="6dc3b-146">Deaktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6dc3b-146">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="6dc3b-147">Wenn Sie Microsoft Threat Protection nicht länger verwenden möchten, wechseln Sie zu **Einstellungen** > **Microsoft Threat Protection** > **Aktivieren/Deaktivieren** im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-147">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="6dc3b-148">Deaktivieren Sie **Microsoft Threat Protection aktivieren** , und wenden Sie die Änderungen an.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-148">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="6dc3b-149">Die entsprechenden Features werden aus dem Microsoft 365 Security Center entfernt.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-149">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="6dc3b-150">Unterstützung erhalten</span><span class="sxs-lookup"><span data-stu-id="6dc3b-150">Get assistance</span></span>

<span data-ttu-id="6dc3b-151">Wenn Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von Microsoft Threat Protection erhalten möchten, [Lesen Sie die FAQ](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="6dc3b-151">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="6dc3b-152">Microsoft-Supportmitarbeiter können Ihnen helfen, den Dienst und die zugehörigen Ressourcen auf Ihrem Mandanten bereitzustellen oder zu entbinden.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-152">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="6dc3b-153">Um Unterstützung zu erhalten, wählen Sie **need help?** im Microsoft 365 Security Center aus.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-153">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="6dc3b-154">Wenn Sie sich an den Support wenden, erwähnen Sie Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="6dc3b-154">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6dc3b-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6dc3b-155">Related topics</span></span>

- [<span data-ttu-id="6dc3b-156">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="6dc3b-156">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="6dc3b-157">Lizenzierungsanforderungen und andere Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6dc3b-157">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="6dc3b-158">Bereitstellen unterstützter Dienste</span><span class="sxs-lookup"><span data-stu-id="6dc3b-158">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="6dc3b-159">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6dc3b-159">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="6dc3b-160">Übersicht über Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="6dc3b-160">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="6dc3b-161">Übersicht über Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="6dc3b-161">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="6dc3b-162">Übersicht über Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6dc3b-162">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="6dc3b-163">Übersicht über Azure ATP</span><span class="sxs-lookup"><span data-stu-id="6dc3b-163">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="6dc3b-164">Übersicht über Microsoft Defender ATP und Datenspeicherung</span><span class="sxs-lookup"><span data-stu-id="6dc3b-164">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)