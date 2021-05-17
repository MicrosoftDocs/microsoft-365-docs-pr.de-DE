---
title: Erste Schritte mit dem Dashboard zur Verhinderung von Datenverlust
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Beginnen Sie mit dem Definieren und Verwalten von Warnungen für Richtlinien zur Verhinderung von Datenverlust.
ms.openlocfilehash: 7f070dd960cc00ad7899c75117cd2a3fcf679973
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760726"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a><span data-ttu-id="e1c00-103">Erste Schritte mit dem Dashboard zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="e1c00-103">Get started with the data loss prevention alert dashboard</span></span>

<span data-ttu-id="e1c00-104">Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) können Schutzmaßnahmen ergreifen, um die unbeabsichtigte Freigabe vertraulicher Elemente zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="e1c00-104">Data loss prevention (DLP) policies can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="e1c00-105">Wenn eine Aktion für ein vertrauliches Element ergriffen wird, können Sie benachrichtigt werden, indem Sie Warnungen für DLP konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e1c00-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="e1c00-106">In diesem Artikel erfahren Sie, wie Sie umfassende Warnungsrichtlinien definieren, die mit Ihren Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="e1c00-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="e1c00-107">Sie erfahren, wie Sie das Dashboard für die [DLP-Warnungsverwaltung](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) verwenden, um Warnungen, Ereignisse und zugehörige Metadaten für Verstöße gegen DLP-Richtlinien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e1c00-107">You'll see how to use the [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<span data-ttu-id="e1c00-108">Wenn Sie mit DLP-Warnungen neu sind, sollten Sie Informationen zum Dashboard für Benachrichtigungen zur Verhinderung von [Datenverlust lesen.](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="e1c00-108">If you are new to DLP alerts, you should review [Learn about the data loss prevention alerts dashboard](dlp-alerts-dashboard-learn.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e1c00-109">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="e1c00-109">Before you begin</span></span>

<span data-ttu-id="e1c00-110">Bevor Sie beginnen, stellen Sie sicher, dass Sie über die erforderlichen Voraussetzungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="e1c00-110">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="e1c00-111">Lizenzierung für das DLP-Benachrichtigungsverwaltungsdashboard</span><span class="sxs-lookup"><span data-stu-id="e1c00-111">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="e1c00-112">Lizenzierung für Warnungskonfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="e1c00-112">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="e1c00-113">Rollen</span><span class="sxs-lookup"><span data-stu-id="e1c00-113">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="e1c00-114">Lizenzierung für das DLP-Warnungsverwaltungsdashboard</span><span class="sxs-lookup"><span data-stu-id="e1c00-114">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="e1c00-115">Alle berechtigten Mandanten für Office 365 DLP können auf das DLP-Warnungsverwaltungsdashboard zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e1c00-115">All eligible tenants for Office 365 DLP can access the DLP alert management dashboard.</span></span> <span data-ttu-id="e1c00-116">Für die ersten Schritte sollten Sie berechtigt sein, Office 365 DLP für Exchange Online, SharePoint Online und OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="e1c00-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="e1c00-117">Weitere Informationen zu den Lizenzierungsanforderungen für Office 365 DLP finden Sie unter Welche Lizenzen bieten die Rechte für einen Benutzer, von dem Dienst [zu profitieren?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span><span class="sxs-lookup"><span data-stu-id="e1c00-117">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="e1c00-118">Kunden, die [Endpoint DLP](endpoint-dlp-learn-about.md) verwenden, die für Teams [DLP](dlp-microsoft-teams.md) berechtigt sind, sehen ihre DLP-Richtlinienwarnungen für Endpunkte und Teams im DLP-Warnungsverwaltungsdashboard.</span><span class="sxs-lookup"><span data-stu-id="e1c00-118">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

<span data-ttu-id="e1c00-119">Das **Feature für die** Inhaltsvorschau ist nur für diese Lizenzen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="e1c00-119">The **content preview** feature is available only for these licenses:</span></span>

- <span data-ttu-id="e1c00-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="e1c00-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="e1c00-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="e1c00-121">Office 365 (E5)</span></span>
- <span data-ttu-id="e1c00-122">Advanced Compliance (E5) add on</span><span class="sxs-lookup"><span data-stu-id="e1c00-122">Advanced Compliance (E5) add on</span></span>
- <span data-ttu-id="e1c00-123">Microsoft 365 E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="e1c00-123">Microsoft 365 E5/A5 Information Protection and Governance</span></span>
- <span data-ttu-id="e1c00-124">Microsft 365 E5/A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="e1c00-124">Microsft 365 E5/A5 Compliance</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="e1c00-125">Lizenzierung für Warnungskonfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="e1c00-125">Licensing for alert configuration options</span></span>

<span data-ttu-id="e1c00-126">Konfiguration von Einzelereigniswarnungen: Organisationen mit einem E1-, F1- oder G1-Abonnement oder einem E3- oder **G3-Abonnement** können Nur dann Warnungsrichtlinien erstellen, wenn bei jedem Auftreten einer Aktivität eine Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e1c00-126">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>

<span data-ttu-id="e1c00-127">**Aggregierte Warnungskonfiguration:** Zum Konfigurieren aggregierter Warnungsrichtlinien basierend auf einem Schwellenwert müssen Sie eine der folgenden Lizenzierungskonfigurationen verwenden:</span><span class="sxs-lookup"><span data-stu-id="e1c00-127">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must one of these licensing configurations:</span></span>

- <span data-ttu-id="e1c00-128">Ein E5- oder G5-Abonnement</span><span class="sxs-lookup"><span data-stu-id="e1c00-128">An E5 or G5 subscription</span></span>
- <span data-ttu-id="e1c00-129">Ein E1-, F1- oder G1-Abonnement oder ein E3- oder G3-Abonnement, das eine der folgenden Features umfasst:</span><span class="sxs-lookup"><span data-stu-id="e1c00-129">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
    - <span data-ttu-id="e1c00-130">Office 365 Advanced Threat Protection Plan 2</span><span class="sxs-lookup"><span data-stu-id="e1c00-130">Office 365 Advanced Threat Protection Plan 2</span></span>
    - <span data-ttu-id="e1c00-131">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="e1c00-131">Microsoft 365 E5 Compliance</span></span>
    - <span data-ttu-id="e1c00-132">Microsoft 365 eDiscovery- und Audit-Add-On-Lizenz</span><span class="sxs-lookup"><span data-stu-id="e1c00-132">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="e1c00-133">Rollen</span><span class="sxs-lookup"><span data-stu-id="e1c00-133">Roles</span></span>


<span data-ttu-id="e1c00-134">Wenn Sie das Dashboard für die DLP-Warnungsverwaltung anzeigen oder die Konfigurationsoptionen für Warnungen in einer DLP-Richtlinie bearbeiten möchten, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="e1c00-134">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

- <span data-ttu-id="e1c00-135">Complianceadministrator</span><span class="sxs-lookup"><span data-stu-id="e1c00-135">Compliance Administrator</span></span>
- <span data-ttu-id="e1c00-136">Compliancedatenadministrator</span><span class="sxs-lookup"><span data-stu-id="e1c00-136">Compliance Data Administrator</span></span>
- <span data-ttu-id="e1c00-137">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="e1c00-137">Security Administrator</span></span>
- <span data-ttu-id="e1c00-138">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="e1c00-138">Security Operator</span></span>
- <span data-ttu-id="e1c00-139">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="e1c00-139">Security Reader</span></span>

<span data-ttu-id="e1c00-140">Für den Zugriff auf das DLP-Warnungsverwaltungsdashboard benötigen Sie die:</span><span class="sxs-lookup"><span data-stu-id="e1c00-140">To access the DLP alert management dashboard, you need the:</span></span>

- <span data-ttu-id="e1c00-141">Verwalten von Warnungen</span><span class="sxs-lookup"><span data-stu-id="e1c00-141">Manage alerts</span></span>

<span data-ttu-id="e1c00-142">und eine der beiden folgenden Rollen:</span><span class="sxs-lookup"><span data-stu-id="e1c00-142">and either of these two roles:</span></span>

- <span data-ttu-id="e1c00-143">DLP-Complianceverwaltung</span><span class="sxs-lookup"><span data-stu-id="e1c00-143">DLP Compliance Management</span></span>
- <span data-ttu-id="e1c00-144">View-Only DLP Compliance Management</span><span class="sxs-lookup"><span data-stu-id="e1c00-144">View-Only DLP Compliance Management</span></span>

<span data-ttu-id="e1c00-145">Um auf das Feature für die Inhaltsvorschau und die Features für abgestimmte vertrauliche Inhalte und Kontexte zu zugreifen, müssen Sie Mitglied von:</span><span class="sxs-lookup"><span data-stu-id="e1c00-145">To access the Content preview feature and the Matched sensitive content and context features you must be a member of:</span></span>

- <span data-ttu-id="e1c00-146">Inhalts-Explorer-Inhaltsanzeige-Rollengruppe</span><span class="sxs-lookup"><span data-stu-id="e1c00-146">Content Explorer Content Viewer role group</span></span>

<span data-ttu-id="e1c00-147">der die Rolle der Inhaltsanzeige für die Datenklassifizierung vorab zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e1c00-147">which has the data classification content viewer role pre-assigned.</span></span>

## <a name="dlp-alert-configuration"></a><span data-ttu-id="e1c00-148">Konfiguration von DLP-Warnungen</span><span class="sxs-lookup"><span data-stu-id="e1c00-148">DLP alert configuration</span></span>

<span data-ttu-id="e1c00-149">Informationen zum Konfigurieren einer Warnung in Ihrer DLP-Richtlinie finden Sie unter [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span><span class="sxs-lookup"><span data-stu-id="e1c00-149">To learn how to configure an alert in your DLP policy, see [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span></span>

### <a name="aggregate-event-alert-configuration"></a><span data-ttu-id="e1c00-150">Konfiguration von Aggregatereigniswarnungen</span><span class="sxs-lookup"><span data-stu-id="e1c00-150">Aggregate event alert configuration</span></span>

<span data-ttu-id="e1c00-151">Wenn Ihre Organisation für aggregierte Warnungskonfigurationsoptionen lizenziert [ist,](#licensing-for-alert-configuration-options)werden diese Optionen angezeigt, wenn Sie eine DLP-Richtlinie erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e1c00-151">If your org is licensed for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot mit Optionen für Vorfallberichte für Benutzer, die für aggregierte Warnungskonfigurationsoptionen berechtigt sind." border="false":::

<span data-ttu-id="e1c00-153">Mit dieser Konfiguration können Sie eine Richtlinie einrichten, um eine Warnung jedes Mal zu generieren, wenn eine Aktivität den Richtlinienbedingungen entspricht oder ein bestimmter Schwellenwert überschritten wird, basierend auf der Anzahl der Aktivitäten oder basierend auf dem Umfang der exfiltrierten Daten.</span><span class="sxs-lookup"><span data-stu-id="e1c00-153">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

### <a name="single-event-alert-configuration"></a><span data-ttu-id="e1c00-154">Konfiguration einzelner Ereigniswarnungen</span><span class="sxs-lookup"><span data-stu-id="e1c00-154">Single event alert configuration</span></span>

<span data-ttu-id="e1c00-155">Wenn Ihre Organisation für Konfigurationsoptionen für einzelne Ereignisse lizenziert ist, werden diese Optionen angezeigt, wenn Sie eine [DLP-Richtlinie](#licensing-for-alert-configuration-options)erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e1c00-155">If your org is licensed for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span> <span data-ttu-id="e1c00-156">Verwenden Sie diese Option, um eine Warnung zu erstellen, die jedes Mal ausgelöst wird, wenn eine DLP-Regel übereinstimmung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="e1c00-156">Use this option to create an alert that's raised every time a DLP rule match happens.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot mit Optionen für Vorfallberichte für Benutzer, die für Konfigurationsoptionen für einzelne Ereignisse berechtigt sind." border="false":::

## <a name="investigate-a-dlp-alert"></a><span data-ttu-id="e1c00-158">Untersuchen einer DLP-Warnung</span><span class="sxs-lookup"><span data-stu-id="e1c00-158">Investigate a DLP alert</span></span>

<span data-ttu-id="e1c00-159">So arbeiten Sie mit dem DLP-Warnungsverwaltungsdashboard:</span><span class="sxs-lookup"><span data-stu-id="e1c00-159">To work with the DLP alert management dashboard:</span></span>

1. <span data-ttu-id="e1c00-160">Wechseln Sie [Microsoft 365 Compliance Center](https://www.compliance.microsoft.com)zu Verhinderung von **Datenverlust.**</span><span class="sxs-lookup"><span data-stu-id="e1c00-160">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>
2. <span data-ttu-id="e1c00-161">Wählen Sie die **Registerkarte Warnungen** aus, um das DLP-Benachrichtigungsdashboard anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e1c00-161">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>
3. <span data-ttu-id="e1c00-162">Wählen Sie eine Warnung aus, um Details anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="e1c00-162">Select an alert to see details:</span></span>

:::image type="content" source="../media/alert-details.png" alt-text="Screenshot mit Warnungsdetails im DLP-Warnungsverwaltungsdashboard." border="false":::

4. <span data-ttu-id="e1c00-164">Wählen Sie die **Registerkarte Ereignisse** aus, um alle Ereignisse zu sehen, die der Warnung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e1c00-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="e1c00-165">Sie können ein bestimmtes Ereignis auswählen, um dessen Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e1c00-165">You can choose a particular event to view its details.</span></span> <span data-ttu-id="e1c00-166">Eine Liste einiger verfügbarer Ereignisdetails finden Sie unter Informationen zum Dashboard für Warnungen zur Verhinderung von [Datenverlust.](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="e1c00-166">For a list of some of the available event details, see, [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span></span>
5. <span data-ttu-id="e1c00-167">Wählen **Sie Details** aus, um die Seite **Übersicht** für die Warnung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e1c00-167">Select **Details** to open the **Overview** page for the alert.</span></span> <span data-ttu-id="e1c00-168">Die Übersichtsseite enthält eine Zusammenfassung:</span><span class="sxs-lookup"><span data-stu-id="e1c00-168">The overview page provides a summary:</span></span>
    1. <span data-ttu-id="e1c00-169">von dem, was passiert ist</span><span class="sxs-lookup"><span data-stu-id="e1c00-169">of what happened</span></span>
    1. <span data-ttu-id="e1c00-170">Die Personen, die die Aktionen ausgeführt haben, die die Richtlinien übereinstimmung verursacht haben</span><span class="sxs-lookup"><span data-stu-id="e1c00-170">who performed the actions that caused the policy match</span></span>
    1. <span data-ttu-id="e1c00-171">Informationen zur abgestimmten Richtlinie und mehr</span><span class="sxs-lookup"><span data-stu-id="e1c00-171">information about the matched policy, and more</span></span> 

6. <span data-ttu-id="e1c00-172">Wählen Sie die **Registerkarte Ereignisse** aus, um auf die zu zugreifen:</span><span class="sxs-lookup"><span data-stu-id="e1c00-172">Choose the **Events** tab to access the:</span></span>
    1. <span data-ttu-id="e1c00-173">Beteiligter Inhalt</span><span class="sxs-lookup"><span data-stu-id="e1c00-173">content involved</span></span>
    1. <span data-ttu-id="e1c00-174">Übereinstimmende Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="e1c00-174">sensitive information types matched</span></span>
    1. <span data-ttu-id="e1c00-175">Metadaten</span><span class="sxs-lookup"><span data-stu-id="e1c00-175">metadata</span></span>

7. <span data-ttu-id="e1c00-176">Wählen Sie die **Registerkarte Typen** vertraulicher Informationen aus, um Details zu den im Inhalt erkannten Typen vertraulicher Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e1c00-176">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="e1c00-177">Details umfassen Vertrauen, Anzahl und den Inhalt, der dem Typ vertraulicher Informationen entspricht.</span><span class="sxs-lookup"><span data-stu-id="e1c00-177">Details include confidence, count, and the content that matches the sensitive information type.</span></span>

8. <span data-ttu-id="e1c00-178">Nachdem Sie die Warnung untersucht  haben, kehren Sie zur Registerkarte Übersicht zurück, auf der Sie die Triage verwalten und die Disposition der Warnung verwalten und Kommentare hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="e1c00-178">After you investigate the alert, return to the **Overview** tab where you can manage triage and manage the disposition of the alert and add comments.</span></span>

- <span data-ttu-id="e1c00-179">Um den Verlauf der Workflowverwaltung zu sehen, wählen Sie **Verwaltungsprotokoll aus.**</span><span class="sxs-lookup"><span data-stu-id="e1c00-179">To see the history of workflow management, choose **Management log**.</span></span>
- <span data-ttu-id="e1c00-180">Nachdem Sie die erforderliche Aktion für die Warnung ergreifen, legen Sie den Status der Warnung auf **Resolved .**</span><span class="sxs-lookup"><span data-stu-id="e1c00-180">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1c00-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1c00-181">See also</span></span>

- [<span data-ttu-id="e1c00-182">Informationen zu Warnungen zur Verhinderung von Datenverlust und zum Benachrichtigungsdashboard</span><span class="sxs-lookup"><span data-stu-id="e1c00-182">Learn about data loss prevention alerts and the alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)
- [<span data-ttu-id="e1c00-183">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e1c00-183">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)