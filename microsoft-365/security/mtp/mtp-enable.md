---
title: Aktivieren von Microsoft 365 Defender im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Microsoft 365 Defender aktivieren und mit der Integration Ihres Sicherheitsvorfalls und Ihrer Reaktion beginnen.
keywords: Erste Schritte, Aktivieren von MTP, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherort, erforderlichen Berechtigungen, Lizenzberechtigung, Einstellungsseite
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e7910866c494cf599022c17c29e3577e55cdba51
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928652"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="e62ba-104">Aktivieren von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e62ba-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e62ba-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e62ba-105">**Applies to:**</span></span>
- <span data-ttu-id="e62ba-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e62ba-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e62ba-107">[Microsoft 365 Defender](microsoft-threat-protection.md) vereint Ihren Prozess zur Reaktion auf Vorfälle, indem wichtige Funktionen in Microsoft Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity integriert werden.</span><span class="sxs-lookup"><span data-stu-id="e62ba-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="e62ba-108">Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e62ba-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="e62ba-109">Microsoft 365 Defender wird automatisch aktiviert, wenn berechtigte Kunden mit den erforderlichen Berechtigungen das Microsoft 365 Security Center besuchen.</span><span class="sxs-lookup"><span data-stu-id="e62ba-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="e62ba-110">Lesen Sie diesen Artikel, um die verschiedenen Voraussetzungen und die Bereitstellung von Microsoft 365 Defender zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="e62ba-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="e62ba-111">Überprüfen der Lizenzberechtigung und der erforderlichen Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e62ba-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="e62ba-112">Eine Lizenz für ein Microsoft 365-Sicherheitsprodukt berechtigt Sie im Allgemeinen, Microsoft 365 Defender im Microsoft 365 Security Center ohne zusätzliche Lizenzierungskosten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e62ba-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="e62ba-113">Es wird empfohlen, eine Microsoft 365 E5-, E5 Security-, A5- oder A5-Sicherheitslizenz oder eine gültige Kombination von Lizenzen zu erhalten, die Zugriff auf alle unterstützten Dienste bietet.</span><span class="sxs-lookup"><span data-stu-id="e62ba-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="e62ba-114">Ausführliche Lizenzierungsinformationen finden [Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="e62ba-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="e62ba-115">Überprüfen Ihrer Rolle</span><span class="sxs-lookup"><span data-stu-id="e62ba-115">Check your role</span></span>

<span data-ttu-id="e62ba-116">Sie müssen ein globaler Administrator **oder** **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender aktivieren zu können.</span><span class="sxs-lookup"><span data-stu-id="e62ba-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="e62ba-117">Anzeigen Ihrer Rollen in Azure AD</span><span class="sxs-lookup"><span data-stu-id="e62ba-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="e62ba-118">Unterstützte Dienste</span><span class="sxs-lookup"><span data-stu-id="e62ba-118">Supported services</span></span>

<span data-ttu-id="e62ba-119">Microsoft 365 Defender aggregiert Daten aus den verschiedenen unterstützten Diensten, die Sie bereits bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="e62ba-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="e62ba-120">Es wird Daten zentral verarbeiten und speichern, um neue Erkenntnisse zu identifizieren und zentrale Reaktionsworkflows zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e62ba-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="e62ba-121">Dies ohne Auswirkungen auf vorhandene Bereitstellungen, Einstellungen oder Daten, die den integrierten Diensten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e62ba-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="e62ba-122">Um den bestmöglichen Schutz zu erhalten und Microsoft 365 Defender zu optimieren, empfehlen wir die Bereitstellung aller anwendbaren unterstützten Dienste in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="e62ba-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="e62ba-123">Weitere Informationen finden Sie [unter Bereitstellen von unterstützten Diensten](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="e62ba-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="e62ba-124">Onboarding in den Dienst</span><span class="sxs-lookup"><span data-stu-id="e62ba-124">Onboard to the service</span></span>
<span data-ttu-id="e62ba-125">Das Onboarding in Microsoft 365 Defender ist einfach.</span><span class="sxs-lookup"><span data-stu-id="e62ba-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="e62ba-126">Wählen Sie im Navigationsmenü ein beliebiges Element im Abschnitt Endpunkte aus, z. B. Vorfälle, Suche, Aktionscenter oder Bedrohungsanalyse, um den Onboardingprozess zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="e62ba-126">From the navigation menu, select any item under the Endpoints section, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="e62ba-127">Rechenzentrumsspeicherort</span><span class="sxs-lookup"><span data-stu-id="e62ba-127">Data center location</span></span>

<span data-ttu-id="e62ba-128">Microsoft 365 Defender wird Daten am gleichen Speicherort speichern und verarbeiten, der von [Microsoft Defender for Endpoint verwendet wird.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="e62ba-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="e62ba-129">Wenn Sie nicht über Microsoft Defender for Endpoint verfügen, wird basierend auf dem Speicherort aktiver Microsoft 365-Sicherheitsdienste automatisch ein neuer Rechenzentrumsspeicherort ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e62ba-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="e62ba-130">Der ausgewählte Rechenzentrumsspeicherort wird auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e62ba-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="e62ba-131">Wählen **Sie Hilfe benötigen?** im Microsoft 365 Security Center aus, um den Microsoft-Support über die Bereitstellung von Microsoft 365 Defender an einem anderen Rechenzentrumsstandort zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="e62ba-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="e62ba-132">Microsoft Defender for Endpoint stellt automatisch In Rechenzentren in der Europäischen Union (EU) bereit, wenn sie über Azure Defender aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e62ba-132">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="e62ba-133">Microsoft 365 Defender stellt automatisch im gleichen EU-Rechenzentrum Kunden zur Verfügung, die Defender for Endpoint auf diese Weise bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="e62ba-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="e62ba-134">Vergewissern Sie sich, dass der Dienst aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="e62ba-134">Confirm that the service is on</span></span>

<span data-ttu-id="e62ba-135">Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="e62ba-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="e62ba-136">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="e62ba-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="e62ba-137">Benachrichtigungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="e62ba-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="e62ba-138">Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="e62ba-138">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="e62ba-139">[Erweiterte Funktionen für die Suche](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e62ba-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="e62ba-140">Bedrohungsanalyse</span><span class="sxs-lookup"><span data-stu-id="e62ba-140">Threat analytics</span></span>

<span data-ttu-id="e62ba-141">![Abbildung des Microsoft 365 Security Center-Navigationsbereichs mit Microsoft 365 Defender bietet Microsoft 365 Security Center mit Vorfallverwaltung und anderen ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender-Funktionen*</span><span class="sxs-lookup"><span data-stu-id="e62ba-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="e62ba-142">Abrufen von Microsoft Defender for Identity-Daten</span><span class="sxs-lookup"><span data-stu-id="e62ba-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="e62ba-143">Um die Integration in Microsoft Cloud App Security zu ermöglichen, müssen Sie sich mindestens einmal bei der Microsoft Cloud App Security anmelden.</span><span class="sxs-lookup"><span data-stu-id="e62ba-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="e62ba-144">Unterstützung erhalten</span><span class="sxs-lookup"><span data-stu-id="e62ba-144">Get assistance</span></span>

<span data-ttu-id="e62ba-145">Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von Microsoft 365 Defender finden Sie [in den häufig gestellten Fragen](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="e62ba-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="e62ba-146">Mitarbeiter des Microsoft-Support unterstützen Sie bei der Bereitstellung oder Deprovision des Diensts und der zugehörigen Ressourcen für Ihren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="e62ba-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="e62ba-147">Wenn Sie Unterstützung benötigen, **wählen Sie Hilfe?** im Microsoft 365 Security Center aus.</span><span class="sxs-lookup"><span data-stu-id="e62ba-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="e62ba-148">Wenn Sie den Support kontaktieren, erwähnen Sie Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e62ba-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e62ba-149">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e62ba-149">Related topics</span></span>

- [<span data-ttu-id="e62ba-150">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="e62ba-150">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="e62ba-151">Lizenzierungsanforderungen und andere Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e62ba-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="e62ba-152">Bereitstellen unterstützter Dienste</span><span class="sxs-lookup"><span data-stu-id="e62ba-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="e62ba-153">Übersicht über Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e62ba-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="e62ba-154">Übersicht über Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e62ba-154">Microsoft Defender for Endpoint overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="e62ba-155">Übersicht über Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="e62ba-155">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="e62ba-156">Übersicht über Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e62ba-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="e62ba-157">Übersicht über Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e62ba-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="e62ba-158">Datenspeicherung von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e62ba-158">Microsoft Defender for Endpoint data storage</span></span>](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)