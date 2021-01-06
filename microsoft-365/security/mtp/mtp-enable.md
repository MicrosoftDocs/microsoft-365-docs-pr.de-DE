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
ms.openlocfilehash: b052f70c1b618adef12c4f70c2b3fe55741697d5
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760506"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="6297b-104">Aktivieren von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6297b-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6297b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6297b-105">**Applies to:**</span></span>
- <span data-ttu-id="6297b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6297b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6297b-107">[Microsoft 365 Defender](microsoft-threat-protection.md) vereinigt ihren Vorfall Antwortprozess durch die Integration wichtiger Funktionen in Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="6297b-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="6297b-108">Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="6297b-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="6297b-109">Microsoft 365 Defender aktiviert automatisch, wenn berechtigte Kunden mit den erforderlichen Berechtigungen Microsoft 365 Security Center besuchen.</span><span class="sxs-lookup"><span data-stu-id="6297b-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="6297b-110">Lesen Sie diesen Artikel, um die verschiedenen Voraussetzungen und die Vorgehensweise von Microsoft 365 Defender zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="6297b-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="6297b-111">Überprüfen der Lizenz Berechtigung und der erforderlichen Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6297b-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="6297b-112">Eine Lizenz für ein Microsoft 365-Sicherheitsprodukt berechtigt Sie im Allgemeinen zur Verwendung von Microsoft 365 Defender im Microsoft 365 Security Center ohne zusätzliche Lizenzierungskosten.</span><span class="sxs-lookup"><span data-stu-id="6297b-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="6297b-113">Es wird empfohlen, eine Sicherheitslizenz für Microsoft 365 E5, E5, A5 oder A5 oder eine gültige Kombination von Lizenzen zu erhalten, die Zugriff auf alle unterstützten Dienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6297b-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="6297b-114">Ausführliche Lizenzierungsinformationen finden [Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="6297b-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="6297b-115">Überprüfen der Rolle</span><span class="sxs-lookup"><span data-stu-id="6297b-115">Check your role</span></span>

<span data-ttu-id="6297b-116">Sie müssen ein **globaler Administrator** oder ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6297b-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="6297b-117">Anzeigen ihrer Rollen in Azure AD</span><span class="sxs-lookup"><span data-stu-id="6297b-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="6297b-118">Unterstützte Dienste</span><span class="sxs-lookup"><span data-stu-id="6297b-118">Supported services</span></span>

<span data-ttu-id="6297b-119">Microsoft 365 Defender aggregiert Daten aus den verschiedenen unterstützten Diensten, die Sie bereits bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="6297b-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="6297b-120">Die Daten werden zentral verarbeitet und gespeichert, um neue Erkenntnisse zu identifizieren und um zentralisierte Antwort Workflows zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6297b-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="6297b-121">Dies geschieht ohne Beeinträchtigung vorhandener Bereitstellungen, Einstellungen oder Daten, die den integrierten Diensten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6297b-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="6297b-122">Um den besten Schutz zu erhalten und Microsoft 365 Defender zu optimieren, wird empfohlen, alle anwendbaren unterstützten Dienste in Ihrem Netzwerk bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6297b-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="6297b-123">Weitere Informationen finden [Sie unter Deploying supported Services](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="6297b-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="6297b-124">Vor dem Starten des Diensts</span><span class="sxs-lookup"><span data-stu-id="6297b-124">Before starting the service</span></span>

<span data-ttu-id="6297b-125">Bevor Sie den Dienst aktivieren, zeigt das Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) die Seite Microsoft 365 Defender-Einstellungen an, wenn Sie im Navigationsbereich **Vorfälle**, das **Aktionscenter** oder die **Suche** auswählen.</span><span class="sxs-lookup"><span data-stu-id="6297b-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="6297b-126">Diese Navigationselemente werden nicht angezeigt, wenn Sie nicht berechtigt sind, Microsoft 365 Defender zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6297b-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="6297b-127">![Abbildung der Seite Microsoft 365 Defender-Einstellungen, die angezeigt wird, wenn Microsoft 365 Defender nicht auf ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender-Einstellungen im Microsoft 365 Security Center* aktiviert wurde</span><span class="sxs-lookup"><span data-stu-id="6297b-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="6297b-128">Starten des Diensts</span><span class="sxs-lookup"><span data-stu-id="6297b-128">Starting the service</span></span>

<span data-ttu-id="6297b-129">Wählen Sie zum Aktivieren von Microsoft 365 Defender einfach **Microsoft 365 Defender aktivieren** aus, und wenden Sie die Änderung an.</span><span class="sxs-lookup"><span data-stu-id="6297b-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="6297b-130">Sie können auf diese Option auch zugreifen, indem Sie im Navigationsbereich **Einstellungen** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) auswählen und dann **Microsoft 365 Defender** auswählen.</span><span class="sxs-lookup"><span data-stu-id="6297b-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="6297b-131">Wenn im Navigationsbereich keine **Einstellungen** angezeigt werden oder Sie nicht auf die Seite zugreifen können, überprüfen Sie Ihre Berechtigungen und Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="6297b-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="6297b-132">Rechenzentrumsstandort</span><span class="sxs-lookup"><span data-stu-id="6297b-132">Data center location</span></span>

<span data-ttu-id="6297b-133">Microsoft 365 Defender speichert und verarbeitet Daten am [gleichen Speicherort, der von Microsoft Defender für Endpoint verwendet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)wird.</span><span class="sxs-lookup"><span data-stu-id="6297b-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="6297b-134">Wenn Sie nicht über Microsoft Defender für Endpoint verfügen, wird automatisch ein neuer datencenterstandort basierend auf dem Speicherort der aktiven Microsoft 365-Sicherheitsdienste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="6297b-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="6297b-135">Der ausgewählte Speicherort des Rechenzentrums wird auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6297b-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="6297b-136">Wählen Sie **need help aus?** im Microsoft 365 Security Center können Sie sich an den Microsoft-Support wenden, um Microsoft 365 Defender in einem anderen rechenzentrumsstandort zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="6297b-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="6297b-137">Microsoft Defender für Endpoint stellt in den Datencentern der Europäischen Union (EU) automatisch Rückstellungen bereit, wenn Sie über Azure Defender aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="6297b-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="6297b-138">Microsoft 365 Defender wird automatisch im gleichen EU-Rechenzentrum für Kunden bereitgestellt, die auf diese Weise einen Defender für Endpoint bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="6297b-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="6297b-139">Vergewissern Sie sich, dass der Dienst aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="6297b-139">Confirm that the service is on</span></span>

<span data-ttu-id="6297b-140">Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="6297b-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="6297b-141">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="6297b-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="6297b-142">Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="6297b-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="6297b-143">[Erweiterte Jagd](advanced-hunting-overview.md) Funktionen</span><span class="sxs-lookup"><span data-stu-id="6297b-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="6297b-144">![Bild des Microsoft 365 Security Center-Navigationsbereichs mit Microsoft 365 Defender Features ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Security Center mit Incidents Management und anderen Microsoft 365 Defender-Funktionen*</span><span class="sxs-lookup"><span data-stu-id="6297b-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="6297b-145">Aufrufen von Microsoft Defender für Identitätsdaten</span><span class="sxs-lookup"><span data-stu-id="6297b-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="6297b-146">Um Microsoft Defender für Identitätsdaten mit Microsoft 365 Defender freizugeben, stellen Sie sicher, dass Microsoft Cloud App Security und Microsoft Defender for Identity Integration aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6297b-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="6297b-147">[Erfahren Sie mehr über diese Integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="6297b-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="6297b-148">Unterstützung erhalten</span><span class="sxs-lookup"><span data-stu-id="6297b-148">Get assistance</span></span>

<span data-ttu-id="6297b-149">Wenn Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von Microsoft 365 Defender erhalten möchten, [Lesen Sie die FAQ](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="6297b-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="6297b-150">Microsoft-Supportmitarbeiter können Ihnen helfen, den Dienst und die zugehörigen Ressourcen auf Ihrem Mandanten bereitzustellen oder zu entbinden.</span><span class="sxs-lookup"><span data-stu-id="6297b-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="6297b-151">Um Unterstützung zu erhalten, wählen Sie **need help?** im Microsoft 365 Security Center aus.</span><span class="sxs-lookup"><span data-stu-id="6297b-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="6297b-152">Wenn Sie sich an den Support wenden, erwähnen Sie Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6297b-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6297b-153">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6297b-153">Related topics</span></span>

- [<span data-ttu-id="6297b-154">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="6297b-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="6297b-155">Lizenzierungsanforderungen und andere Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6297b-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="6297b-156">Bereitstellen unterstützter Dienste</span><span class="sxs-lookup"><span data-stu-id="6297b-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="6297b-157">Microsoft 365 Defender (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="6297b-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="6297b-158">Microsoft Defender für Endpoint (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="6297b-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="6297b-159">Verteidiger für Office 365 Übersicht</span><span class="sxs-lookup"><span data-stu-id="6297b-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="6297b-160">Übersicht über Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6297b-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="6297b-161">Übersicht über Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="6297b-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="6297b-162">Microsoft Defender für die Endpunkt Datenspeicherung</span><span class="sxs-lookup"><span data-stu-id="6297b-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
