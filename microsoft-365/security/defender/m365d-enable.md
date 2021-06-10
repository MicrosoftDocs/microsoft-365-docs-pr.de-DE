---
title: Aktivieren Microsoft 365 Defender im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Microsoft 365 Defender aktivieren und mit der Integration Ihres Sicherheitsvorfalls und Ihrer Reaktion beginnen.
keywords: erste Schritte, aktivieren sie Microsoft 365 Defender, Microsoft 365 Defender, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenzberechtigung, Einstellungsseite
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3f05cc8c9b2509f8c95b802f56905e2859221cd2
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861599"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="36c82-104">Microsoft 365 Defender aktivieren</span><span class="sxs-lookup"><span data-stu-id="36c82-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="36c82-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="36c82-105">**Applies to:**</span></span>
- <span data-ttu-id="36c82-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36c82-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="36c82-107">[Microsoft 365 Defender](microsoft-365-defender.md) vereinheitlicht Ihren Vorfallreaktionsprozess, indem wichtige Funktionen in Microsoft Defender für Endpunkt, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity integriert werden.</span><span class="sxs-lookup"><span data-stu-id="36c82-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="36c82-108">Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="36c82-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="36c82-109">Microsoft 365 Defender wird automatisch aktiviert, wenn berechtigte Kunden mit den erforderlichen Berechtigungen Microsoft 365 Security Center besuchen.</span><span class="sxs-lookup"><span data-stu-id="36c82-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="36c82-110">Lesen Sie diesen Artikel, um verschiedene Voraussetzungen zu verstehen und zu erfahren, wie Microsoft 365 Defender bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="36c82-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="36c82-111">Überprüfen der Lizenzberechtigung und der erforderlichen Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="36c82-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="36c82-112">Eine Lizenz für ein Microsoft 365-Sicherheitsprodukt berechtigt Sie in der Regel dazu, Microsoft 365 Defender im Microsoft 365 Security Center ohne zusätzliche Lizenzierungskosten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="36c82-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="36c82-113">Es wird empfohlen, eine Microsoft 365 E5-, E5 Security-, A5- oder A5 Security-Lizenz oder eine gültige Kombination von Lizenzen zu erhalten, die Zugriff auf alle unterstützten Dienste bietet.</span><span class="sxs-lookup"><span data-stu-id="36c82-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="36c82-114">Ausführliche Informationen zur Lizenzierung [finden Sie in den Lizenzierungsanforderungen.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="36c82-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="36c82-115">Überprüfen Ihrer Rolle</span><span class="sxs-lookup"><span data-stu-id="36c82-115">Check your role</span></span>

<span data-ttu-id="36c82-116">Sie müssen ein **globaler Administrator** oder **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="36c82-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="36c82-117">Anzeigen Ihrer Rollen in Azure AD</span><span class="sxs-lookup"><span data-stu-id="36c82-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="36c82-118">Unterstützte Dienste</span><span class="sxs-lookup"><span data-stu-id="36c82-118">Supported services</span></span>

<span data-ttu-id="36c82-119">Microsoft 365 Defender aggregiert Daten aus den verschiedenen unterstützten Diensten, die Sie bereits bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="36c82-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="36c82-120">Sie verarbeitet und speichert Daten zentral, um neue Erkenntnisse zu identifizieren und zentrale Reaktionsworkflows zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="36c82-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="36c82-121">Dies geschieht ohne Auswirkungen auf vorhandene Bereitstellungen, Einstellungen oder Daten, die den integrierten Diensten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="36c82-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="36c82-122">Um den besten Schutz zu erhalten und Microsoft 365 Defender zu optimieren, empfehlen wir die Bereitstellung aller anwendbaren unterstützten Dienste in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="36c82-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="36c82-123">Weitere Informationen [finden Sie unter "Bereitstellen unterstützter Dienste".](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="36c82-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="36c82-124">Onboarding in den Dienst</span><span class="sxs-lookup"><span data-stu-id="36c82-124">Onboard to the service</span></span>
<span data-ttu-id="36c82-125">Das Onboarding in Microsoft 365 Defender ist einfach.</span><span class="sxs-lookup"><span data-stu-id="36c82-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="36c82-126">Wählen Sie im Navigationsmenü alle Microsoft 365 Defender-Elemente aus, z. B. Vorfälle, Suche, Info-Center oder Bedrohungsanalyse, um den Integrationsprozess zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="36c82-126">From the navigation menu, select any Microsoft 365 Defender items, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="36c82-127">Rechenzentrumsstandort</span><span class="sxs-lookup"><span data-stu-id="36c82-127">Data center location</span></span>

<span data-ttu-id="36c82-128">Microsoft 365 Defender speichert und verarbeitet Daten am gleichen Speicherort, der [von Microsoft Defender für Endpunkt verwendet wird.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="36c82-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="36c82-129">Wenn Sie nicht über Microsoft Defender für Endpunkt verfügen, wird basierend auf dem Standort der aktiven Microsoft 365 Sicherheitsdienste automatisch ein neuer Rechenzentrumsstandort ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="36c82-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="36c82-130">Der ausgewählte Rechenzentrumsstandort wird auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36c82-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="36c82-131">Wählen Sie **"Benötigen Sie Hilfe?"** im Microsoft 365 Security Center aus, um sich an den Microsoft-Support zu wenden, um Microsoft 365 Defender an einem anderen Rechenzentrumsstandort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="36c82-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="36c82-132">In der Vergangenheit wurde Microsoft Defender für Endpunkt automatisch in Rechenzentren der Europäischen Union (EU) bereitgestellt, wenn es über Azure Defender aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="36c82-132">In the past, Microsoft Defender for Endpoint automatically provisioned in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="36c82-133">Microsoft 365 Defender stellt automatisch im selben EU-Rechenzentrum für Kunden bereit, die Defender für Endpunkt in der Vergangenheit auf diese Weise bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="36c82-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner in the past.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="36c82-134">Vergewissern Sie sich, dass der Dienst aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="36c82-134">Confirm that the service is on</span></span>

<span data-ttu-id="36c82-135">Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="36c82-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="36c82-136">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="36c82-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="36c82-137">Benachrichtigungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="36c82-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="36c82-138">Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="36c82-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="36c82-139">[Erweiterte Suchfunktionen](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="36c82-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="36c82-140">Bedrohungsanalyse</span><span class="sxs-lookup"><span data-stu-id="36c82-140">Threat analytics</span></span>

<span data-ttu-id="36c82-141">![Abbildung des Navigationsbereichs Microsoft 365 Sicherheitscenters mit Microsoft 365 Defender-Features ](../../media/overview-incident.png)
 *Microsoft 365 Security Center mit Vorfallverwaltung und anderen Microsoft 365 Defender-Funktionen*</span><span class="sxs-lookup"><span data-stu-id="36c82-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/overview-incident.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="36c82-142">Abrufen von Microsoft Defender for Identity-Daten</span><span class="sxs-lookup"><span data-stu-id="36c82-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="36c82-143">Um die Integration in Microsoft Cloud App Security zu aktivieren, müssen Sie sich mindestens einmal beim Microsoft Cloud App Security anmelden.</span><span class="sxs-lookup"><span data-stu-id="36c82-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="36c82-144">Unterstützung erhalten</span><span class="sxs-lookup"><span data-stu-id="36c82-144">Get assistance</span></span>

<span data-ttu-id="36c82-145">Um Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von Microsoft 365 Defender zu erhalten, [lesen Sie die häufig gestellten Fragen.](m365d-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="36c82-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="36c82-146">Microsoft-Supportmitarbeiter können ihnen dabei helfen, den Dienst und die zugehörigen Ressourcen auf Ihrem Mandanten bereitzustellen oder aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="36c82-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="36c82-147">Um Hilfe zu erhalten, wählen **Sie "Benötigen Sie Hilfe?"** im Microsoft 365 Security Center aus.</span><span class="sxs-lookup"><span data-stu-id="36c82-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="36c82-148">Wenn Sie sich an den Support wenden, erwähnen Sie Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="36c82-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="36c82-149">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="36c82-149">Related topics</span></span>

- [<span data-ttu-id="36c82-150">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="36c82-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="36c82-151">Lizenzierungsanforderungen und andere Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="36c82-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="36c82-152">Bereitstellen unterstützter Dienste</span><span class="sxs-lookup"><span data-stu-id="36c82-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="36c82-153">Microsoft 365 Übersicht über Defender</span><span class="sxs-lookup"><span data-stu-id="36c82-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="36c82-154">Übersicht über Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="36c82-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="36c82-155">Übersicht über Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="36c82-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="36c82-156">Übersicht über Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="36c82-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="36c82-157">Übersicht über Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="36c82-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="36c82-158">Microsoft Defender für Endpunkt-Datenspeicherung</span><span class="sxs-lookup"><span data-stu-id="36c82-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
