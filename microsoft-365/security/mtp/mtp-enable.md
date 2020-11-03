---
title: Aktivieren von Microsoft 365 Defender im Microsoft 365 Security Center
description: In diesem Artikel erfahren Sie, wie Sie Microsoft 365 Defender aktivieren und ihre Sicherheitsvorfälle und-Antworten integrieren.
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
ms.openlocfilehash: b5bb99ed4b8cee7ea920679e20f69c7a0e002d26
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843636"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="c23e5-104">Aktivieren von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c23e5-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c23e5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c23e5-105">**Applies to:**</span></span>
- <span data-ttu-id="c23e5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c23e5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c23e5-107">[Microsoft 365 Defender](microsoft-threat-protection.md) vereinigt ihren Vorfall Antwortprozess durch die Integration wichtiger Funktionen in Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="c23e5-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="c23e5-108">Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c23e5-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="c23e5-109">Microsoft 365 Defender aktiviert automatisch, wenn berechtigte Kunden mit den erforderlichen Berechtigungen Microsoft 365 Security Center besuchen.</span><span class="sxs-lookup"><span data-stu-id="c23e5-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="c23e5-110">Lesen Sie diesen Artikel, um die verschiedenen Voraussetzungen und die Vorgehensweise von Microsoft 365 Defender zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="c23e5-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="c23e5-111">Überprüfen der Lizenz Berechtigung und der erforderlichen Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c23e5-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="c23e5-112">Eine Lizenz für ein Microsoft 365-Sicherheitsprodukt berechtigt Sie im Allgemeinen zur Verwendung von Microsoft 365 Defender im Microsoft 365 Security Center ohne zusätzliche Lizenzierungskosten.</span><span class="sxs-lookup"><span data-stu-id="c23e5-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="c23e5-113">Es wird empfohlen, eine Sicherheitslizenz für Microsoft 365 E5, E5, A5 oder A5 oder eine gültige Kombination von Lizenzen zu erhalten, die Zugriff auf alle unterstützten Dienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c23e5-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="c23e5-114">Ausführliche Lizenzierungsinformationen finden [Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="c23e5-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="c23e5-115">Überprüfen der Rolle</span><span class="sxs-lookup"><span data-stu-id="c23e5-115">Check your role</span></span>
<span data-ttu-id="c23e5-116">Sie müssen ein **globaler Administrator** oder ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c23e5-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="c23e5-117">Anzeigen ihrer Rollen in Azure AD</span><span class="sxs-lookup"><span data-stu-id="c23e5-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="c23e5-118">Unterstützte Dienste</span><span class="sxs-lookup"><span data-stu-id="c23e5-118">Supported services</span></span>
<span data-ttu-id="c23e5-119">Microsoft 365 Defender aggregiert Daten aus den verschiedenen unterstützten Diensten, die Sie bereits bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="c23e5-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="c23e5-120">Die Daten werden zentral verarbeitet und gespeichert, um neue Erkenntnisse zu identifizieren und um zentralisierte Antwort Workflows zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c23e5-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="c23e5-121">Dies geschieht ohne Beeinträchtigung vorhandener Bereitstellungen, Einstellungen oder Daten, die den integrierten Diensten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c23e5-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="c23e5-122">Um den besten Schutz zu erhalten und Microsoft 365 Defender zu optimieren, wird empfohlen, alle anwendbaren unterstützten Dienste in Ihrem Netzwerk bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c23e5-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="c23e5-123">Weitere Informationen finden [Sie unter Deploying supported Services](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="c23e5-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="c23e5-124">Vor dem Starten des Diensts</span><span class="sxs-lookup"><span data-stu-id="c23e5-124">Before starting the service</span></span>
<span data-ttu-id="c23e5-125">Bevor Sie den Dienst aktivieren, zeigt das Microsoft 365 Security Center ( [Security.Microsoft.com](https://security.microsoft.com)) die Seite Microsoft 365 Defender-Einstellungen an, wenn Sie im Navigationsbereich **Vorfälle** , das **Aktionscenter** oder die **Suche** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c23e5-125">Before you turn on the service, the Microsoft 365 security center ( [security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents** , **Action center** , or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="c23e5-126">Diese Navigationselemente werden nicht angezeigt, wenn Sie nicht berechtigt sind, Microsoft 365 Defender zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c23e5-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="c23e5-127">![Abbildung der Seite Microsoft 365 Defender-Einstellungen, die angezeigt wird, wenn Microsoft 365 Defender nicht auf ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender-Einstellungen im Microsoft 365 Security Center* aktiviert wurde</span><span class="sxs-lookup"><span data-stu-id="c23e5-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="c23e5-128">Starten des Diensts</span><span class="sxs-lookup"><span data-stu-id="c23e5-128">Starting the service</span></span>
<span data-ttu-id="c23e5-129">Wählen Sie zum Aktivieren von Microsoft 365 Defender einfach **Microsoft 365 Defender aktivieren** aus, und wenden Sie die Änderung an.</span><span class="sxs-lookup"><span data-stu-id="c23e5-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="c23e5-130">Sie können auf diese Option auch zugreifen, indem Sie im Navigationsbereich **Einstellungen** ( [Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) auswählen und dann **Microsoft 365 Defender** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c23e5-130">You can also access this option by selecting **Settings** ( [security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

>[!NOTE]
><span data-ttu-id="c23e5-131">Wenn im Navigationsbereich keine **Einstellungen** angezeigt werden oder Sie nicht auf die Seite zugreifen können, überprüfen Sie Ihre Berechtigungen und Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="c23e5-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="c23e5-132">Rechenzentrumsstandort</span><span class="sxs-lookup"><span data-stu-id="c23e5-132">Data center location</span></span>
<span data-ttu-id="c23e5-133">Microsoft 365 Defender speichert und verarbeitet Daten am [gleichen Speicherort, der von Microsoft Defender für Endpoint verwendet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)wird.</span><span class="sxs-lookup"><span data-stu-id="c23e5-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="c23e5-134">Wenn Sie nicht über Microsoft Defender für Endpoint verfügen, wird automatisch ein neuer datencenterstandort basierend auf dem Speicherort der aktiven Microsoft 365-Sicherheitsdienste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="c23e5-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="c23e5-135">Der ausgewählte Speicherort des Rechenzentrums wird auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c23e5-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="c23e5-136">Wählen Sie **need help aus?** im Microsoft 365 Security Center können Sie sich an den Microsoft-Support wenden, um Microsoft 365 Defender in einem anderen rechenzentrumsstandort zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="c23e5-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="c23e5-137">Microsoft Defender für Endpoint stellt automatisch Vorkehrungen in den Rechenzentren in der Europäischen Union (EU) bereit, wenn es über Azure Defender \* aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="c23e5-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender\*.</span></span> <span data-ttu-id="c23e5-138">Microsoft 365 Defender wird automatisch im gleichen EU-Rechenzentrum für Kunden bereitgestellt, die auf diese Weise einen Defender für Endpoint bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="c23e5-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="c23e5-139">Vergewissern Sie sich, dass der Dienst aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="c23e5-139">Confirm that the service is on</span></span>
<span data-ttu-id="c23e5-140">Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="c23e5-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="c23e5-141">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="c23e5-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="c23e5-142">Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="c23e5-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="c23e5-143">[Erweiterte Jagd](advanced-hunting-overview.md) Funktionen</span><span class="sxs-lookup"><span data-stu-id="c23e5-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="c23e5-144">![Bild des Microsoft 365 Security Center-Navigationsbereichs mit Microsoft 365 Defender Features ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Security Center mit Incidents Management und anderen Microsoft 365 Defender-Funktionen*</span><span class="sxs-lookup"><span data-stu-id="c23e5-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="c23e5-145">Aufrufen von Microsoft Defender für Identitätsdaten</span><span class="sxs-lookup"><span data-stu-id="c23e5-145">Getting Microsoft Defender for Identity data</span></span>
<span data-ttu-id="c23e5-146">Um Microsoft Defender für Identitätsdaten mit Microsoft 365 Defender freizugeben, stellen Sie sicher, dass Microsoft Cloud App Security und Microsoft Defender for Identity Integration aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c23e5-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="c23e5-147">Erfahren Sie mehr über [diese Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span><span class="sxs-lookup"><span data-stu-id="c23e5-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span>


## <a name="turn-off-microsoft-365-defender"></a><span data-ttu-id="c23e5-148">Microsoft 365 Defender deaktivieren</span><span class="sxs-lookup"><span data-stu-id="c23e5-148">Turn off Microsoft 365 Defender</span></span>
<span data-ttu-id="c23e5-149">Um die Verwendung von Microsoft 365 Defender zu beenden, wechseln Sie zu **Einstellungen**  >  **Microsoft 365 Defender**  >  **Opt-in/Opt-out** im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="c23e5-149">To stop using Microsoft 365 Defender, go to **Settings** > **Microsoft 365 Defender** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="c23e5-150">Deaktivieren Sie **Microsoft 365 Defender aktivieren** , und wenden Sie die Änderungen an.</span><span class="sxs-lookup"><span data-stu-id="c23e5-150">Unselect **Turn on Microsoft 365 Defender** and apply the changes.</span></span>

<span data-ttu-id="c23e5-151">Die entsprechenden Features werden aus dem Microsoft 365 Security Center entfernt.</span><span class="sxs-lookup"><span data-stu-id="c23e5-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="c23e5-152">Unterstützung erhalten</span><span class="sxs-lookup"><span data-stu-id="c23e5-152">Get assistance</span></span>

<span data-ttu-id="c23e5-153">Wenn Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von Microsoft 365 Defender erhalten möchten, [Lesen Sie die FAQ](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="c23e5-153">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="c23e5-154">Microsoft-Supportmitarbeiter können Ihnen helfen, den Dienst und die zugehörigen Ressourcen auf Ihrem Mandanten bereitzustellen oder zu entbinden.</span><span class="sxs-lookup"><span data-stu-id="c23e5-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="c23e5-155">Um Unterstützung zu erhalten, wählen Sie **need help?** im Microsoft 365 Security Center aus.</span><span class="sxs-lookup"><span data-stu-id="c23e5-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="c23e5-156">Wenn Sie sich an den Support wenden, erwähnen Sie Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c23e5-156">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c23e5-157">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c23e5-157">Related topics</span></span>

- [<span data-ttu-id="c23e5-158">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="c23e5-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="c23e5-159">Lizenzierungsanforderungen und andere Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c23e5-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="c23e5-160">Bereitstellen unterstützter Dienste</span><span class="sxs-lookup"><span data-stu-id="c23e5-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="c23e5-161">Microsoft 365 Defender (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="c23e5-161">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="c23e5-162">Microsoft Defender für Endpoint (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="c23e5-162">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="c23e5-163">Verteidiger für Office 365 Übersicht</span><span class="sxs-lookup"><span data-stu-id="c23e5-163">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="c23e5-164">Übersicht über Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c23e5-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="c23e5-165">Übersicht über Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="c23e5-165">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="c23e5-166">Microsoft Defender für die Endpunkt Datenspeicherung</span><span class="sxs-lookup"><span data-stu-id="c23e5-166">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
