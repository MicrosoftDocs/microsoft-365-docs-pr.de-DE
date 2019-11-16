---
title: Automatische Untersuchung und Reaktion auf Bedrohungen in Office 365
keywords: Luft, autoIR, ATP, automatisiert, Untersuchung, Antwort, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 11/15/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Erste Schritte mit der Verwendung von automatisierten Vorfall Antwortfunktionen in Office 365 Advanced Threat Protection-Plan 2.
ms.openlocfilehash: 13f7e95829b8cf3adf17a40cf7b02c5322b15ea7
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673421"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="c99a4-104">Automatische Untersuchung und Reaktion auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="c99a4-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="c99a4-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c99a4-105">Overview</span></span>

<span data-ttu-id="c99a4-106">In Abhängigkeit von Ihrem Abonnement kann [Office 365 Advanced Threat Protection](office-365-atp.md) die Funktion "Automated Incident Response (Air)" enthalten, mit der Sie die Zeit und den Aufwand für Sicherheitsvorgänge im Umgang mit Warnungen und Bedrohungen speichern können.</span><span class="sxs-lookup"><span data-stu-id="c99a4-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated incident response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="c99a4-107">Verwenden Sie diesen Artikel, um die Verwendung von Air-Funktionen in Office 365 zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="c99a4-107">To get started using AIR capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="c99a4-108">Wenn Sie einen Überblick über die Funktionsweise von Air erhalten möchten, finden Sie weitere Informationen unter [Automated Incident Response (Air) in Office 365](automated-investigation-response-office.md).</span><span class="sxs-lookup"><span data-stu-id="c99a4-108">To get an overview of how AIR works, see [Automated incident response (AIR) in Office 365](automated-investigation-response-office.md).</span></span>

<span data-ttu-id="c99a4-109">Wenn bestimmte Warnungen ausgelöst werden, werden ein oder mehrere Sicherheits-Textbuch initiiert, und die automatische Untersuchung beginnt.</span><span class="sxs-lookup"><span data-stu-id="c99a4-109">With AIR, when certain alerts are triggered, one or more security playbooks initiate, and automated investigation begins.</span></span> <span data-ttu-id="c99a4-110">Während und nach einem automatisierten Ermittlungsprozess können Administratoren und Sicherheitsteams folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="c99a4-110">During and after an automated investigation process, your administrators and security operations team can:</span></span>

- [<span data-ttu-id="c99a4-111">Anzeigen der Details einer Untersuchung</span><span class="sxs-lookup"><span data-stu-id="c99a4-111">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="c99a4-112">Überprüfen und Genehmigen von Aktionen als Ergebnis einer Untersuchung</span><span class="sxs-lookup"><span data-stu-id="c99a4-112">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="c99a4-113">Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung</span><span class="sxs-lookup"><span data-stu-id="c99a4-113">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> <span data-ttu-id="c99a4-114">Sie müssen über die entsprechenden Berechtigungen zum Ausführen der in diesem Artikel beschriebenen Aufgaben verfügen.</span><span class="sxs-lookup"><span data-stu-id="c99a4-114">You must have appropriate permissions to perform the tasks described in this article.</span></span> <span data-ttu-id="c99a4-115">Sie sind beispielsweise ein globaler Administrator, Sicherheitsadministrator, Sicherheits Operator oder Sicherheits Leser.</span><span class="sxs-lookup"><span data-stu-id="c99a4-115">For example, you myst be a global administrator, security administrator, security operator, or security reader.</span></span> <span data-ttu-id="c99a4-116">[Erfahren Sie mehr über die Rollen und Berechtigungen des Microsoft 365-Sicherheitscenters](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span><span class="sxs-lookup"><span data-stu-id="c99a4-116">[Learn more about Microsoft 365 security center roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="c99a4-117">Air ist in den folgenden Abonnements enthalten:</span><span class="sxs-lookup"><span data-stu-id="c99a4-117">AIR is included in the following subscriptions:</span></span>
- <span data-ttu-id="c99a4-118">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c99a4-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="c99a4-119">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="c99a4-119">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="c99a4-120">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="c99a4-120">Office 365 E5</span></span>
- <span data-ttu-id="c99a4-121">Office 365 Advanced Threat Protection Plan 2</span><span class="sxs-lookup"><span data-stu-id="c99a4-121">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="c99a4-122">Wenn Sie nicht über eines dieser Abonnements verfügen, [Starten Sie eine ﻿kostenlose Testversion](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="c99a4-122">If you don't have one of these subscriptions, [start a free trial](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="c99a4-123">Anzeigen von Details einer Untersuchung</span><span class="sxs-lookup"><span data-stu-id="c99a4-123">View details of an investigation</span></span>

1. <span data-ttu-id="c99a4-124">Wechseln Sie als Office 365 globaler Administrator, Sicherheitsadministrator oder Sicherheits Leser zu und melden [https://protection.office.com](https://protection.office.com) Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="c99a4-124">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="c99a4-125">Sie gelangen auf das Sicherheits #a0 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="c99a4-125">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="c99a4-126">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c99a4-126">Do one of the following:</span></span>

    - <span data-ttu-id="c99a4-127">Wechseln Sie zu **Threat Management** > **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="c99a4-127">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="c99a4-128">Dadurch gelangen Sie zum [Sicherheits Dashboard](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="c99a4-128">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="c99a4-129">Die Air-Widgets werden am oberen Rand des [Sicherheits Dashboards](security-dashboard.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c99a4-129">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="c99a4-130">Wählen Sie ein Widget aus, beispielsweise **Zusammenfassung der Untersuchungen**.</span><span class="sxs-lookup"><span data-stu-id="c99a4-130">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="c99a4-131">Wechseln Sie zu **Threat Management** > **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="c99a4-131">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="c99a4-132">Mit beiden Methoden gelangen Sie zu einer Liste von Untersuchungen.</span><span class="sxs-lookup"><span data-stu-id="c99a4-132">Either method takes you to a list of investigations.</span></span>

    ![Haupt Untersuchungs Seite für Air](../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="c99a4-134">Wählen Sie in der Liste der Untersuchungen ein Element in der Spalte **ID** aus.</span><span class="sxs-lookup"><span data-stu-id="c99a4-134">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="c99a4-135">Dadurch wird die Seite Ermittlungs Details geöffnet, beginnend mit dem unter Such Diagramm in der Ansicht.</span><span class="sxs-lookup"><span data-stu-id="c99a4-135">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![Seite "Luft Untersuchungs Diagramm"](../media/air-investigationgraphpage.png)

4. <span data-ttu-id="c99a4-137">Verwenden Sie die verschiedenen Registerkarten, um mehr über die Untersuchung zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="c99a4-137">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="c99a4-138">Überprüfen und Genehmigen von Aktionen</span><span class="sxs-lookup"><span data-stu-id="c99a4-138">Review and approve actions</span></span>

<span data-ttu-id="c99a4-139">In Office 365 führen automatisierte Untersuchungen normalerweise zu einer oder mehreren empfohlenen Aktionen.</span><span class="sxs-lookup"><span data-stu-id="c99a4-139">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="c99a4-140">Es werden jedoch keine Aktionen ausgeführt, bis Sie vom Sicherheits Betriebsteam genehmigt wurden.</span><span class="sxs-lookup"><span data-stu-id="c99a4-140">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="c99a4-141">Verwenden Sie das folgende Verfahren, um Aktionen zu überprüfen und zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="c99a4-141">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="c99a4-142">Wechseln Sie als Office 365 globaler Administrator, Sicherheitsadministrator oder Sicherheits Leser zu und melden [https://protection.office.com](https://protection.office.com) Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="c99a4-142">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="c99a4-143">Wechseln Sie zu **Threat Management** > **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="c99a4-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="c99a4-144">Wählen Sie in der Liste der Untersuchungen ein Element in der Spalte **ID** aus.</span><span class="sxs-lookup"><span data-stu-id="c99a4-144">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="c99a4-145">Wählen Sie in der Ansicht Ermittlungs Details die Registerkarte **Aktionen** aus. Alle Aktionen, für die eine Genehmigung aussteht, werden hier aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c99a4-145">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="c99a4-146">W?hlen Sie ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="c99a4-146">Select an item in the list.</span></span>

5. <span data-ttu-id="c99a4-147">Wählen Sie **genehmigen** aus, um die empfohlene Aktion zu ergreifen (oder **ablehnen** , um die Untersuchung ohne Aktion zu schließen).</span><span class="sxs-lookup"><span data-stu-id="c99a4-147">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="c99a4-148">Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung</span><span class="sxs-lookup"><span data-stu-id="c99a4-148">View details about an alert related to an investigation</span></span>

<span data-ttu-id="c99a4-149">Bestimmte Arten von Warnungen lösen eine automatische Untersuchung in Office 365 aus.</span><span class="sxs-lookup"><span data-stu-id="c99a4-149">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="c99a4-150">Weitere Informationen finden Sie unter [Alerts](automated-investigation-response-office.md#alerts).</span><span class="sxs-lookup"><span data-stu-id="c99a4-150">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="c99a4-151">Verwenden Sie das folgende Verfahren, um Details zu einer Warnung anzuzeigen, die einer automatisierten Untersuchung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c99a4-151">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="c99a4-152">Wechseln Sie als Office 365 globaler Administrator, Sicherheitsadministrator oder Sicherheits Leser zu und melden [https://protection.office.com](https://protection.office.com) Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="c99a4-152">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="c99a4-153">Sie gelangen auf das Sicherheits #a0 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="c99a4-153">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="c99a4-154">Wechseln Sie zu **Threat Management** > **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="c99a4-154">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="c99a4-155">Wählen Sie in der Liste der Untersuchungen ein Element in der Spalte **ID** aus.</span><span class="sxs-lookup"><span data-stu-id="c99a4-155">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="c99a4-156">Wenn Details zu einer Untersuchung geöffnet sind, wählen Sie die Registerkarte **Benachrichtigungen** aus. Alle Warnungen, die die Untersuchung ausgelöst haben, werden hier aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c99a4-156">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="c99a4-157">W?hlen Sie ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="c99a4-157">Select an item in the list.</span></span> <span data-ttu-id="c99a4-158">Ein Flyout mit Details zur Warnung und Links zu zusätzlichen Informationen und Aktionen wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c99a4-158">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="c99a4-159">Überprüfen Sie die Informationen im Flyout, und nehmen Sie abhängig von der jeweiligen Warnung eine Aktion vor, beispielsweise zum **Auflösen**, unter **drücken**oder **Benachrichtigen von Benutzern**.</span><span class="sxs-lookup"><span data-stu-id="c99a4-159">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="c99a4-160">**Resolve** entspricht dem Schließen einer Warnung.</span><span class="sxs-lookup"><span data-stu-id="c99a4-160">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="c99a4-161">Unter **drücken** bewirkt, dass eine Richtlinie Warnungen für einen bestimmten Zeitraum nicht auslöst</span><span class="sxs-lookup"><span data-stu-id="c99a4-161">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="c99a4-162">**Benutzer benachrichtigen** startet eine e-Mail mit bereits eingegebenen e-Mail-Adressen der Benutzer und ermöglicht es dem Team für Sicherheitsvorgänge, diesen Benutzern eine Nachricht zu geben.</span><span class="sxs-lookup"><span data-stu-id="c99a4-162">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="c99a4-163">(Dies ähnelt dem Senden einer Nachricht an Empfänger mithilfe von [Threat Explorer](threat-explorer.md).)</span><span class="sxs-lookup"><span data-stu-id="c99a4-163">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="c99a4-164">Verwenden der API für die Office 365-Verwaltungsaktivität für benutzerdefinierte oder Drittanbieter-Berichtslösungen</span><span class="sxs-lookup"><span data-stu-id="c99a4-164">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="c99a4-165">Wenn Ihre Organisation eine benutzerdefinierte oder Drittanbieter-Berichtslösung verwendet, können Sie Informationen zu automatisierten Untersuchungen in dieser Lösung mithilfe der API für die Office 365-Verwaltungsaktivität anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c99a4-165">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="c99a4-166">Verwenden Sie die folgenden Ressourcen, um dies einzurichten:</span><span class="sxs-lookup"><span data-stu-id="c99a4-166">Use the following resources to set this up:</span></span>

|<span data-ttu-id="c99a4-167">Ressource</span><span class="sxs-lookup"><span data-stu-id="c99a4-167">Resource</span></span>  |<span data-ttu-id="c99a4-168">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c99a4-168">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c99a4-169">[Übersicht über die Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="c99a4-169">[Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span></span>     |<span data-ttu-id="c99a4-170">Die Office 365-Verwaltungsaktivitäts-API bietet Informationen über verschiedene Benutzer-, Verwaltungs-, System- und Richtlinienaktionen und -ereignisse aus Office 365 und Azure Active Directory-Aktivitätsprotokollen.</span><span class="sxs-lookup"><span data-stu-id="c99a4-170">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="c99a4-171">Erste Schritte mit den Office 365-Verwaltungs-APIs</span><span class="sxs-lookup"><span data-stu-id="c99a4-171">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="c99a4-172">Die Office 365-Verwaltungs-API verwendet Azure AD, um Authentifizierungsdienste für Ihre Anwendung bereitzustellen, um auf Office 365 Daten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c99a4-172">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="c99a4-173">Führen Sie die Schritte in diesem Artikel aus, um dies einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c99a4-173">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="c99a4-174">Office 365-Verwaltungsaktivitäts-API – Referenz</span><span class="sxs-lookup"><span data-stu-id="c99a4-174">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="c99a4-175">Sie können die Office 365-Verwaltungs Aktivitäts-API verwenden, um Informationen zu Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und-Ereignissen aus Office 365-und Azure AD-Aktivitätsprotokollen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c99a4-175">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="c99a4-176">Lesen Sie diesen Artikel, um mehr über die Funktionsweise zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="c99a4-176">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="c99a4-177">Office 365-Verwaltungsaktivitäts-API –Schema</span><span class="sxs-lookup"><span data-stu-id="c99a4-177">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="c99a4-178">Erhalten Sie einen Überblick über das [allgemeine Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) und das [Office 365 ATP-und Threat-Ermittlungs-und-Antwortschema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) , um sich über bestimmte Arten von Daten zu informieren, die über die API für die Office 365-Verwaltungsaktivität verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c99a4-178">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="c99a4-179">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c99a4-179">Next steps</span></span>

[<span data-ttu-id="c99a4-180">Weitere Informationen zu Warnungen</span><span class="sxs-lookup"><span data-stu-id="c99a4-180">Learn more about alerts</span></span>](../../compliance/alert-policies.md)

[<span data-ttu-id="c99a4-181">Manuelles Suchen und untersuchen schädlicher e-Mails, die in Office 365 bereitgestellt wurden</span><span class="sxs-lookup"><span data-stu-id="c99a4-181">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

[<span data-ttu-id="c99a4-182">Informationen zu Air in Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="c99a4-182">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[<span data-ttu-id="c99a4-183">Besuchen Sie die Microsoft 365-Roadmap, um zu sehen, was bald kommt und wie Sie Rollen</span><span class="sxs-lookup"><span data-stu-id="c99a4-183">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)