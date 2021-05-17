---
title: Erstellen und Anzeigen von Ausnahmen für Sicherheitsempfehlungen – Bedrohungs- und Sicherheitsrisikomanagement
description: Erstellen und überwachen Sie Ausnahmen für Sicherheitsempfehlungen in Bedrohungs- und Sicherheitsrisikomanagement.
keywords: Microsoft Defender for Endpoint tvm remediation, Microsoft Defender for Endpoint tvm, Bedrohungs- und Sicherheitsrisikomanagement, threat & Sicherheitsrisikomanagement, threat & Sicherheitsrisikomanagement remediation, tvm remediation intune, tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1af8e5ec9d3aef560c739de5212e8118cf89cd7a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933745"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="b2921-104">Erstellen und Anzeigen von Ausnahmen für Sicherheitsempfehlungen – Bedrohungs- und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="b2921-104">Create and view exceptions for security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b2921-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b2921-105">**Applies to:**</span></span>

- [<span data-ttu-id="b2921-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2921-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b2921-107">Bedrohung und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="b2921-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b2921-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2921-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="b2921-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b2921-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b2921-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b2921-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="b2921-111">Als Alternative zu einer Korrekturanforderung, wenn eine Empfehlung derzeit nicht relevant ist, können Sie Ausnahmen für Empfehlungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="b2921-111">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> <span data-ttu-id="b2921-112">Wenn Ihre Organisation über Gerätegruppen verfügt, können Sie die Ausnahme auf bestimmte Gerätegruppen austeilen.</span><span class="sxs-lookup"><span data-stu-id="b2921-112">If your organization has device groups, you will be able to scope the exception to specific device groups.</span></span> <span data-ttu-id="b2921-113">Ausnahmen können entweder für ausgewählte Gerätegruppen oder für alle früheren und aktuellen Gerätegruppen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b2921-113">Exceptions can either be created for selected device groups, or for all device groups past and present.</span></span>  

<span data-ttu-id="b2921-114">Wenn eine Ausnahme für eine Empfehlung erstellt wird, ist die Empfehlung erst am Ende der Ausnahmedauer aktiv.</span><span class="sxs-lookup"><span data-stu-id="b2921-114">When an exception is created for a recommendation, the recommendation will not be active until the end of the exception duration.</span></span> <span data-ttu-id="b2921-115">Der Empfehlungsstatus wird in **Vollständige Ausnahme** oder **Teilausnahme** (nach Gerätegruppe) geändert.</span><span class="sxs-lookup"><span data-stu-id="b2921-115">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

## <a name="permissions"></a><span data-ttu-id="b2921-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b2921-116">Permissions</span></span>

<span data-ttu-id="b2921-117">Nur Benutzer mit Berechtigungen zur Behandlung von Ausnahmen können Ausnahmen verwalten (einschließlich Erstellen oder Abbrechen).</span><span class="sxs-lookup"><span data-stu-id="b2921-117">Only users with “exceptions handling” permissions can manage exceptions (including creating or canceling).</span></span> <span data-ttu-id="b2921-118">[Erfahren Sie mehr über RBAC-Rollen](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b2921-118">[Learn more about RBAC roles](user-roles.md).</span></span>

![Ansicht der Ausnahmebehandlungsberechtigung.](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a><span data-ttu-id="b2921-120">Erstellen einer Ausnahme</span><span class="sxs-lookup"><span data-stu-id="b2921-120">Create an exception</span></span>

<span data-ttu-id="b2921-121">Wählen Sie eine Sicherheitsempfehlung aus, für die Sie eine Ausnahme erstellen möchten, und wählen Sie dann Ausnahmeoptionen **aus,** und füllen Sie das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="b2921-121">Select a security recommendation you would like create an exception for, and then select **Exception options** and fill out the form.</span></span>  

![Zeigt an, wo sich die Schaltfläche für "Ausnahmeoptionen" in einem Flyout für Sicherheitsempfehlungen befindet.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a><span data-ttu-id="b2921-123">Ausnahme nach Gerätegruppe</span><span class="sxs-lookup"><span data-stu-id="b2921-123">Exception by device group</span></span>

<span data-ttu-id="b2921-124">Wenden Sie die Ausnahme auf alle aktuellen Gerätegruppen an, oder wählen Sie bestimmte Gerätegruppen aus.</span><span class="sxs-lookup"><span data-stu-id="b2921-124">Apply the exception to all current device groups or choose specific device groups.</span></span> <span data-ttu-id="b2921-125">Zukünftige Gerätegruppen werden nicht in die Ausnahme einbezogen.</span><span class="sxs-lookup"><span data-stu-id="b2921-125">Future device groups won't be included in the exception.</span></span> <span data-ttu-id="b2921-126">Gerätegruppen, die bereits über eine Ausnahme verfügen, werden nicht in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2921-126">Device groups that already have an exception will not be displayed in the list.</span></span> <span data-ttu-id="b2921-127">Wenn Sie nur bestimmte Gerätegruppen auswählen, wird der Empfehlungsstatus von "aktiv" in "Teilausnahme" geändert.</span><span class="sxs-lookup"><span data-stu-id="b2921-127">If you only select certain device groups, the recommendation state will change from “active” to “partial exception.”</span></span> <span data-ttu-id="b2921-128">Der Status wird in "vollständige Ausnahme" geändert, wenn Sie alle Gerätegruppen auswählen.</span><span class="sxs-lookup"><span data-stu-id="b2921-128">The state will change to “full exception” if you select all the device groups.</span></span>

![Anzeigen des Gerätegruppendropdowns.](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a><span data-ttu-id="b2921-130">Gefilterte Ansichten</span><span class="sxs-lookup"><span data-stu-id="b2921-130">Filtered views</span></span>

<span data-ttu-id="b2921-131">Wenn Sie auf einer der Bedrohungs- und Sicherheitsrisikomanagement nach Gerätegruppe gefiltert haben, werden nur die gefilterten Gerätegruppen als Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2921-131">If you have filtered by device group on any of the threat and vulnerability management pages, only your filtered device groups will appear as options.</span></span>

<span data-ttu-id="b2921-132">Dies ist die Schaltfläche zum Filtern nach Gerätegruppe auf einer der Bedrohungs- und Sicherheitsrisikomanagement Seiten:</span><span class="sxs-lookup"><span data-stu-id="b2921-132">This is the button to filter by device group on any of the threat and vulnerability management pages:</span></span> 

![Anzeigen ausgewählter Gerätegruppenfilter.](images/tvm-selected-device-groups.png)

<span data-ttu-id="b2921-134">Ausnahmeansicht mit gefilterten Gerätegruppen:</span><span class="sxs-lookup"><span data-stu-id="b2921-134">Exception view with filtered device groups:</span></span>

![Anzeigen gefilterter Gerätegruppendropdowns.](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a><span data-ttu-id="b2921-136">Große Anzahl von Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="b2921-136">Large number of device groups</span></span>

<span data-ttu-id="b2921-137">Wenn Ihre Organisation über mehr als 20 Gerätegruppen verfügt, wählen Sie **Neben** der gefilterten Gerätegruppe bearbeiten aus.</span><span class="sxs-lookup"><span data-stu-id="b2921-137">If your organization has more than 20 device groups, select **Edit** next to the filtered device group option.</span></span>

![Zeigt, wie eine große Anzahl von Gruppen bearbeitet wird.](images/tvm-exception-edit-groups.png)

<span data-ttu-id="b2921-139">Es wird ein Flyout angezeigt, in dem Sie Gerätegruppen suchen und auswählen können, die sie enthalten möchten.</span><span class="sxs-lookup"><span data-stu-id="b2921-139">A flyout will appear where you can search and choose device groups you want included.</span></span> <span data-ttu-id="b2921-140">Aktivieren Sie das Häkchensymbol unter Suchen, um alle zu überprüfen/deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b2921-140">Select the check mark icon below Search to check/uncheck all.</span></span>

![Zeigt das Flyout für große Gerätegruppen an.](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a><span data-ttu-id="b2921-142">Globale Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="b2921-142">Global exceptions</span></span>

<span data-ttu-id="b2921-143">Wenn Sie über globale Administratorberechtigungen verfügen, können Sie eine globale Ausnahme erstellen und abbrechen.</span><span class="sxs-lookup"><span data-stu-id="b2921-143">If you have global administrator permissions, you will be able to create and cancel a global exception.</span></span> <span data-ttu-id="b2921-144">Sie wirkt **sich auf** alle aktuellen und zukünftigen Gerätegruppen in Ihrer Organisation aus, und nur ein Benutzer mit einer ähnlichen Berechtigung kann sie ändern.</span><span class="sxs-lookup"><span data-stu-id="b2921-144">It affects **all** current and future device groups in your organization, and only a user with similar permission would be able to change it.</span></span> <span data-ttu-id="b2921-145">Der Empfehlungsstatus wird von "aktiv" in "vollständige Ausnahme" geändert.</span><span class="sxs-lookup"><span data-stu-id="b2921-145">The recommendation state will change from “active” to “full exception.”</span></span>

![Zeigt die globale Ausnahmeoption an.](images/tvm-exception-global.png)

<span data-ttu-id="b2921-147">Einige Dinge, die Sie beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="b2921-147">Some things to keep in mind:</span></span>

- <span data-ttu-id="b2921-148">Wenn eine Empfehlung einer globalen Ausnahme unterläuft, werden neu erstellte Ausnahmen für Gerätegruppen angehalten, bis die globale Ausnahme abgelaufen oder abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="b2921-148">If a recommendation is under global exception, then newly created exceptions for device groups will be suspended until the global exception has expired or been cancelled.</span></span> <span data-ttu-id="b2921-149">Danach werden die ausnahmen für neue Gerätegruppen wirksam, bis sie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="b2921-149">After that point, the new device group exceptions will go into effect until they expire.</span></span>
- <span data-ttu-id="b2921-150">Wenn eine Empfehlung bereits Ausnahmen für bestimmte Gerätegruppen hat und eine globale Ausnahme erstellt wird, wird die Gerätegruppenausnahme angehalten, bis sie abläuft oder die globale Ausnahme abgebrochen wird, bevor sie abläuft.</span><span class="sxs-lookup"><span data-stu-id="b2921-150">If a recommendation already has exceptions for specific device groups and a global exception is created, then the device group exception will be suspended until it expires or the global exception is cancelled before it expires.</span></span>

### <a name="justification"></a><span data-ttu-id="b2921-151">Begründung</span><span class="sxs-lookup"><span data-stu-id="b2921-151">Justification</span></span>

<span data-ttu-id="b2921-152">Wählen Sie Ihre Begründung für die Ausnahme aus, die Sie erstellen müssen, anstatt die in Frage gestellte Sicherheitsempfehlung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b2921-152">Select your justification for the exception you need to file instead of remediating the security recommendation in question.</span></span> <span data-ttu-id="b2921-153">Füllen Sie den Begründungskontext aus, und legen Sie dann die Ausnahmedauer ein.</span><span class="sxs-lookup"><span data-stu-id="b2921-153">Fill out the justification context, then set the exception duration.</span></span>

<span data-ttu-id="b2921-154">In der folgenden Liste werden die Begründungen für die Ausnahmeoptionen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="b2921-154">The following list details the justifications behind the exception options:</span></span>

- <span data-ttu-id="b2921-155">**Drittanbieterkontrolle** – Ein Produkt oder eine Software eines Drittanbieters hat diese Empfehlung bereits adressiert : Wenn Sie diesen Begründungstyp auswählen, wird Ihre Belichtungsnote gesenkt und Ihre sichere Bewertung erhöht, da Ihr Risiko reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="b2921-155">**Third party control** - A third party product or software already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="b2921-156">**Alternative Gegenmaßnahmen** – Ein internes Tool hat diese Empfehlung bereits adressiert: Wenn Sie diesen Begründungstyp auswählen, wird Ihre Risikopunktzahl gesenkt und Ihre sichere Bewertung erhöht, da Ihr Risiko reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="b2921-156">**Alternate mitigation** - An internal tool already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="b2921-157">**Risiko akzeptiert** – Birgt ein geringes Risiko und/oder die Implementierung der Empfehlung ist zu teuer</span><span class="sxs-lookup"><span data-stu-id="b2921-157">**Risk accepted** - Poses low risk and/or implementing the recommendation is too expensive</span></span>
- <span data-ttu-id="b2921-158">**Geplante Korrektur (Nachfrist)** – Bereits geplant, aber wartet auf Ausführung oder Autorisierung</span><span class="sxs-lookup"><span data-stu-id="b2921-158">**Planned remediation (grace)** - Already planned but is awaiting execution or authorization</span></span>

## <a name="view-all-exceptions"></a><span data-ttu-id="b2921-159">Anzeigen aller Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="b2921-159">View all exceptions</span></span>

<span data-ttu-id="b2921-160">Navigieren Sie **auf** der Seite **Korrektur** zur Registerkarte Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="b2921-160">Navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="b2921-161">Sie können nach Begründung, Typ und Status filtern.</span><span class="sxs-lookup"><span data-stu-id="b2921-161">You can filter by justification, type, and status.</span></span>

 <span data-ttu-id="b2921-162">Wählen Sie eine Ausnahme aus, um ein Flyout mit weiteren Details zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b2921-162">Select an exception to open a flyout with more details.</span></span> <span data-ttu-id="b2921-163">Ausnahmen pro Gerätegruppe enthalten eine Liste aller Gerätegruppen, die die Ausnahme behandelt, die Sie exportieren können.</span><span class="sxs-lookup"><span data-stu-id="b2921-163">Exceptions per devices group will have a list of every device group the exception covers, which you can export.</span></span> <span data-ttu-id="b2921-164">Sie können auch die zugehörige Empfehlung anzeigen oder die Ausnahme abbrechen.</span><span class="sxs-lookup"><span data-stu-id="b2921-164">You can also view the related recommendation or cancel the exception.</span></span>

![Zeigt die Registerkarte "Ausnahmen" auf der Seite Korrektur an.](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a><span data-ttu-id="b2921-166">Abbrechen einer Ausnahme</span><span class="sxs-lookup"><span data-stu-id="b2921-166">How to cancel an exception</span></span>

<span data-ttu-id="b2921-167">Zum Abbrechen einer Ausnahme navigieren Sie auf der Seite Korrektur zur **Registerkarte** **Ausnahmen.**</span><span class="sxs-lookup"><span data-stu-id="b2921-167">To cancel an exception, navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="b2921-168">Wählen Sie die Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="b2921-168">Select the exception.</span></span>

<span data-ttu-id="b2921-169">Wählen Sie zum Abbrechen der Ausnahme für alle Gerätegruppen oder für eine globale Ausnahme die Schaltfläche **Abbrechen für alle Gerätegruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="b2921-169">To cancel the exception for all device groups or for a global exception, select the **Cancel exception for all device groups** button.</span></span> <span data-ttu-id="b2921-170">Ausnahmen können nur für Gerätegruppen abgebrochen werden, für die Sie über Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="b2921-170">You will only be able to cancel exceptions for device groups you have permissions for.</span></span>

![Die Schaltfläche Abbrechen.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a><span data-ttu-id="b2921-172">Abbrechen der Ausnahme für eine bestimmte Gerätegruppe</span><span class="sxs-lookup"><span data-stu-id="b2921-172">Cancel the exception for a specific device group</span></span>

<span data-ttu-id="b2921-173">Wählen Sie die bestimmte Gerätegruppe aus, um die Ausnahme für sie abbricht.</span><span class="sxs-lookup"><span data-stu-id="b2921-173">Select the specific device group to cancel the exception for it.</span></span> <span data-ttu-id="b2921-174">Für die Gerätegruppe wird ein Flyout angezeigt, und Sie können Die Ausnahme **abbrechen auswählen.**</span><span class="sxs-lookup"><span data-stu-id="b2921-174">A flyout will appear for the device group, and you can select **Cancel exception**.</span></span>

![Zeigt, wie eine bestimmte Gerätegruppe ausgewählt wird.](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a><span data-ttu-id="b2921-176">Anzeigen von Auswirkungen nach der Anwendung von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="b2921-176">View impact after exceptions are applied</span></span>

<span data-ttu-id="b2921-177">Wählen Sie auf Empfehlungen Seite  Sicherheit Spalten anpassen aus, und aktivieren Sie die Kontrollkästchen für Verfügbar gemachte Geräte **(nach Ausnahmen)** und **Auswirkung (nach Ausnahmen).**</span><span class="sxs-lookup"><span data-stu-id="b2921-177">In the Security Recommendations page, select **Customize columns** and check the boxes for **Exposed devices (after exceptions)** and **Impact (after exceptions)**.</span></span>

![Anzeigen von Optionen zum Anpassen von Spalten.](images/tvm-after-exceptions.png)

<span data-ttu-id="b2921-179">In der Spalte verfügbar gemachte Geräte (nach Ausnahmen) werden die verbleibenden Geräte angezeigt, die nach der Anwendung von Ausnahmen weiterhin Sicherheitsrisiken ausgesetzt sind.</span><span class="sxs-lookup"><span data-stu-id="b2921-179">The exposed devices (after exceptions) column shows the remaining devices that are still exposed to vulnerabilities after exceptions are applied.</span></span> <span data-ttu-id="b2921-180">Zu den Ausnahmen, die sich auf die Risikoexposition auswirken, gehören "Kontrolle durch Dritte" und "alternative Gegenmaßnahmen".</span><span class="sxs-lookup"><span data-stu-id="b2921-180">Exception justifications that affect the exposure include ‘third party control’ and ‘alternate mitigation’.</span></span> <span data-ttu-id="b2921-181">Andere Begründungen verringern die Belichtung eines Geräts nicht und gelten weiterhin als verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b2921-181">Other justifications do not reduce the exposure of a device, and they are still considered exposed.</span></span>

<span data-ttu-id="b2921-182">Die Auswirkung (nach Ausnahmen) zeigt die verbleibenden Auswirkungen auf die Bewertung der Belichtung oder die sichere Bewertung, nachdem Ausnahmen angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="b2921-182">The impact (after exceptions) shows remaining impact to exposure score or secure score after exceptions are applied.</span></span> <span data-ttu-id="b2921-183">Ausnahmegrundwerte, die sich auf die Bewertungen auswirken, sind "Drittanbietersteuerung" und "alternative Gegenmaßnahmen".</span><span class="sxs-lookup"><span data-stu-id="b2921-183">Exception justifications that affect the scores include ‘third party control’ and ‘alternate mitigation.’</span></span> <span data-ttu-id="b2921-184">Andere Begründungen verringern die Belichtung eines Geräts nicht, sodass sich die Belichtungs- und Sicherheitspunktzahl nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="b2921-184">Other justifications do not reduce the exposure of a device, and so the exposure score and secure score do not change.</span></span>

![Zeigt die Spalten in der Tabelle an.](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a><span data-ttu-id="b2921-186">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b2921-186">Related topics</span></span>

- [<span data-ttu-id="b2921-187">Übersicht über Bedrohungen Sicherheitsrisikomanagement Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="b2921-187">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b2921-188">Sicherheitsrisiken korrigieren</span><span class="sxs-lookup"><span data-stu-id="b2921-188">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="b2921-189">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="b2921-189">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="b2921-190">Gefährdungsscore</span><span class="sxs-lookup"><span data-stu-id="b2921-190">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="b2921-191">Microsoft-Sicherheitsbewertung für Geräte</span><span class="sxs-lookup"><span data-stu-id="b2921-191">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
