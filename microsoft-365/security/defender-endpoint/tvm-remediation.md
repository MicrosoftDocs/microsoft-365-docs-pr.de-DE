---
title: Behebung von Sicherheitsrisiken mit Bedrohungs- und Sicherheitsrisikoverwaltung
description: Beheben von Sicherheitslücken, die durch Sicherheitsempfehlungen entdeckt wurden, und bei Bedarf Ausnahmen bei der Bedrohungs- und Sicherheitsrisikoverwaltung.
keywords: microsoft defender atp tvm remediation, mdatp tvm, threat and vulnerability management, threat & vulnerability management, threat & vulnerability management remediation, tvm remediation intune, tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0a0f70d81c3060f14f917cac49851af2e9dae210
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068687"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a><span data-ttu-id="55875-104">Behebung von Sicherheitsrisiken mit Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="55875-104">Remediate vulnerabilities with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55875-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="55875-105">**Applies to:**</span></span>
- [<span data-ttu-id="55875-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="55875-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="55875-107">Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="55875-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="55875-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55875-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="55875-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="55875-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="55875-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="55875-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a><span data-ttu-id="55875-111">Anforderungsbehebung</span><span class="sxs-lookup"><span data-stu-id="55875-111">Request remediation</span></span>

<span data-ttu-id="55875-112">Die Bedrohungs- und Sicherheitsrisikoverwaltungsfunktion in Microsoft Defender for Endpoint überbrückt die Lücke zwischen Sicherheits- und IT-Administratoren über den Workflow zur Behebungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="55875-112">The threat and vulnerability management capability in Microsoft Defender for Endpoint bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="55875-113">Sicherheitsadministratoren wie Sie können den IT-Administrator bitten, eine  Sicherheitslücke von den Sicherheitsempfehlungsseiten auf Intune zu be behebung.</span><span class="sxs-lookup"><span data-stu-id="55875-113">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** pages to Intune.</span></span>

### <a name="enable-microsoft-intune-connection"></a><span data-ttu-id="55875-114">Aktivieren der Microsoft Intune-Verbindung</span><span class="sxs-lookup"><span data-stu-id="55875-114">Enable Microsoft Intune connection</span></span>

<span data-ttu-id="55875-115">Um diese Funktion zu verwenden, aktivieren Sie Ihre Microsoft Intune-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="55875-115">To use this capability, enable your Microsoft Intune connections.</span></span> <span data-ttu-id="55875-116">Navigieren Sie im Microsoft Defender Security Center zu **Einstellungen**  >  **Allgemeine erweiterte**  >  **Features**.</span><span class="sxs-lookup"><span data-stu-id="55875-116">In the Microsoft Defender Security Center, navigate to **Settings** > **General** > **Advanced features**.</span></span> <span data-ttu-id="55875-117">Scrollen Sie nach unten, und suchen **Sie nach Microsoft Intune-Verbindung.**</span><span class="sxs-lookup"><span data-stu-id="55875-117">Scroll down and look for **Microsoft Intune connection**.</span></span> <span data-ttu-id="55875-118">Standardmäßig ist der Umschalter deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="55875-118">By default, the toggle is turned off.</span></span> <span data-ttu-id="55875-119">Schalten Sie **Ihre Microsoft Intune-Verbindung** **ein.**</span><span class="sxs-lookup"><span data-stu-id="55875-119">Turn your **Microsoft Intune connection** toggle **On**.</span></span>

<span data-ttu-id="55875-120">**Hinweis:** Wenn Sie die Intune-Verbindung aktiviert haben, erhalten Sie eine Option zum Erstellen einer Intune-Sicherheitsaufgabe beim Erstellen einer Korrekturanforderung.</span><span class="sxs-lookup"><span data-stu-id="55875-120">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="55875-121">Diese Option wird nicht angezeigt, wenn die Verbindung nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="55875-121">This option does not appear if the connection is not set.</span></span>

<span data-ttu-id="55875-122">Weitere [Informationen finden Sie unter Verwenden](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) von Intune zur Behebung von von Microsoft Defender for Endpoint identifizierten Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="55875-122">See [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) for details.</span></span>

### <a name="remediation-request-steps"></a><span data-ttu-id="55875-123">Schritte zur Behebungsanforderung</span><span class="sxs-lookup"><span data-stu-id="55875-123">Remediation request steps</span></span>

1. <span data-ttu-id="55875-124">Wechseln Sie zum Navigationsmenü zur Bedrohungs- und Sicherheitsrisikoverwaltung im Microsoft Defender Security Center, und wählen Sie [**Sicherheitsempfehlungen aus.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="55875-124">Go to the threat and vulnerability management navigation menu in the Microsoft Defender Security Center, and select [**Security recommendations**](tvm-security-recommendation.md).</span></span>

2. <span data-ttu-id="55875-125">Wählen Sie eine Sicherheitsempfehlung aus, für die Sie eine Korrektur anfordern möchten, und wählen Sie dann **Korrekturoptionen aus.**</span><span class="sxs-lookup"><span data-stu-id="55875-125">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span>

3. <span data-ttu-id="55875-126">Füllen Sie das Formular aus, einschließlich der Informationen, für die Sie eine Korrektur anfordern, anwendbare Gerätegruppen, Priorität, Fälligkeitsdatum und optionale Notizen.</span><span class="sxs-lookup"><span data-stu-id="55875-126">Fill out the form, including what you are requesting remediation for, applicable device groups, priority, due date, and optional notes.</span></span>
    1. <span data-ttu-id="55875-127">Wenn Sie die Option "Aufmerksamkeit erforderlich" auswählen, ist die Auswahl eines Fälligkeitsdatums nicht verfügbar, da keine bestimmte Aktion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="55875-127">If you choose the "attention required" remediation option, selecting a due date will not be available since there is no specific action.</span></span>

4. <span data-ttu-id="55875-128">Wählen **Sie Anforderung übermitteln aus.**</span><span class="sxs-lookup"><span data-stu-id="55875-128">Select **Submit request**.</span></span> <span data-ttu-id="55875-129">Durch das Übermitteln einer Korrekturanforderung wird ein Problembehebungsaktivitätselement innerhalb der Bedrohungs- und Sicherheitsrisikoverwaltung erstellt, das zum Überwachen des Behebungsfortschritts für diese Empfehlung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="55875-129">Submitting a remediation request creates a remediation activity item within threat and vulnerability management, which can be used for monitoring the remediation progress for this recommendation.</span></span> <span data-ttu-id="55875-130">Dadurch wird keine Korrektur ausgelöst oder Änderungen auf Geräten angewendet.</span><span class="sxs-lookup"><span data-stu-id="55875-130">This will not trigger a remediation or apply any changes to devices.</span></span>

5. <span data-ttu-id="55875-131">Benachrichtigen Sie Ihren IT-Administrator über die neue Anforderung, und lassen Sie sie sich bei Intune anmelden, um die Anforderung zu genehmigen oder abzulehnen und eine Paketbereitstellung zu starten.</span><span class="sxs-lookup"><span data-stu-id="55875-131">Notify your IT Administrator about the new request and have them log into Intune to approve or reject the request and start a package deployment.</span></span>

6. <span data-ttu-id="55875-132">Wechseln Sie zur [**Seite Korrektur,**](tvm-remediation.md) um den Status Ihrer Behebungsanforderung zu sehen.</span><span class="sxs-lookup"><span data-stu-id="55875-132">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span>

<span data-ttu-id="55875-133">Wenn Sie überprüfen möchten, wie das Ticket in Intune angezeigt wird, finden Sie weitere Informationen unter Verwenden von Intune zur Behebung von von [Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) identifizierten Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="55875-133">If you want to check how the ticket shows up in Intune, see [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) for details.</span></span>

>[!NOTE]
><span data-ttu-id="55875-134">Wenn Ihre Anforderung die Behebung von mehr als 10.000 Geräten umfasst, können wir nur 10.000 Geräte zur Behebung an Intune senden.</span><span class="sxs-lookup"><span data-stu-id="55875-134">If your request involves remediating more than 10,000 devices, we can only send 10,000 devices for remediation to Intune.</span></span>

<span data-ttu-id="55875-135">Nachdem die Cybersicherheitsschwächen Ihrer Organisation identifiziert und den Empfehlungen für umsetzbare Sicherheit zugeordnet [wurden,](tvm-security-recommendation.md)beginnen Sie mit dem Erstellen von Sicherheitsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="55875-135">After your organization's cybersecurity weaknesses are identified and mapped to actionable [security recommendations](tvm-security-recommendation.md), start creating security tasks.</span></span> <span data-ttu-id="55875-136">Sie können Aufgaben über die Integration mit Microsoft Intune erstellen, in der Wartungstickets erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="55875-136">You can create tasks through the integration with Microsoft Intune where remediation tickets are created.</span></span>

<span data-ttu-id="55875-137">Verringern Sie die Gefährdung Ihrer Organisation durch Sicherheitsrisiken, und erhöhen Sie Ihre Sicherheitskonfiguration, indem Sie die Sicherheitsempfehlungen abstellen.</span><span class="sxs-lookup"><span data-stu-id="55875-137">Lower your organization's exposure from vulnerabilities and increase your security configuration by remediating the security recommendations.</span></span>

## <a name="view-your-remediation-activities"></a><span data-ttu-id="55875-138">Anzeigen Ihrer Korrekturaktivitäten</span><span class="sxs-lookup"><span data-stu-id="55875-138">View your remediation activities</span></span>

<span data-ttu-id="55875-139">Wenn Sie eine Behebungsanforderung von der Seite Sicherheitsempfehlungen übermitteln, wird eine Korrekturaktivität ins Jahr 2013 starten.</span><span class="sxs-lookup"><span data-stu-id="55875-139">When you submit a remediation request from the Security recommendations page, it kicks-off a remediation activity.</span></span> <span data-ttu-id="55875-140">Es wird eine Sicherheitsaufgabe erstellt, die auf der  Seite Zur Behebung von Bedrohungen und Sicherheitsrisiken nachverfolgt werden kann, und in Microsoft Intune wird ein Behebungsticket erstellt.</span><span class="sxs-lookup"><span data-stu-id="55875-140">A security task is created that can be tracked in the threat and vulnerability management **Remediation** page, and a remediation ticket is created in Microsoft Intune.</span></span>

<span data-ttu-id="55875-141">Wenn Sie die Option "Aufmerksamkeit erforderlich" ausgewählt haben, gibt es keine Statusanzeige, keinen Ticketstatus oder kein Fälligkeitsdatum, da es keine tatsächliche Aktion gibt, die wir überwachen können.</span><span class="sxs-lookup"><span data-stu-id="55875-141">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there is no actual action we can monitor.</span></span>

<span data-ttu-id="55875-142">Sobald Sie sich auf der Seite Korrektur befinden, wählen Sie die Korrekturaktivität aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="55875-142">Once you are in the Remediation page, select the remediation activity that you want to view.</span></span> <span data-ttu-id="55875-143">Sie können die Korrekturschritte ausführen, den Fortschritt nachverfolgen, die zugehörige Empfehlung anzeigen, in CSV exportieren oder als abgeschlossen markieren.</span><span class="sxs-lookup"><span data-stu-id="55875-143">You can follow the remediation steps, track progress, view the related recommendation, export to CSV, or mark as complete.</span></span>
<span data-ttu-id="55875-144">![Beispiel für die Seite "Korrektur" mit einer ausgewählten Korrekturaktivität und dem Flyout dieser Aktivität, in dem die Beschreibung, die IT-Dienst- und Geräteverwaltungstools sowie der Fortschritt der Gerätebehebung auflistet werden.](images/remediation_flyouteolsw.png)</span><span class="sxs-lookup"><span data-stu-id="55875-144">![Example of the Remediation page, with a selected remediation activity, and that activity's flyout listing the description, IT service and device management tools, and device remediation progress.](images/remediation_flyouteolsw.png)</span></span>

>[!NOTE]
> <span data-ttu-id="55875-145">Es gibt einen Aufbewahrungszeitraum von 180 Tage für abgeschlossene Korrekturaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="55875-145">There is a 180 day retention period for completed remediation activities.</span></span> <span data-ttu-id="55875-146">Damit die Korrekturseite optimal funktioniert, wird die Behebungsaktivität 6 Monate nach abschluss entfernt.</span><span class="sxs-lookup"><span data-stu-id="55875-146">To keep the Remediation page performing optimally, the remediation activity will be removed 6 months after its completion.</span></span>

### <a name="completed-by-column"></a><span data-ttu-id="55875-147">Nach Spalte abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="55875-147">Completed by column</span></span>

<span data-ttu-id="55875-148">Verfolgen Sie, wer die Korrekturaktivität mit der Spalte "Abgeschlossen von" auf der Seite Korrektur geschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="55875-148">Track who closed the remediation activity with the "Completed by" column on the Remediation page.</span></span>

- <span data-ttu-id="55875-149">**E-Mail-Adresse**: Die E-Mail der Person, die die Aufgabe manuell abgeschlossen hat</span><span class="sxs-lookup"><span data-stu-id="55875-149">**Email address**: The email of the person who manually completed the task</span></span>
- <span data-ttu-id="55875-150">**Systembestätigung**: Die Aufgabe wurde automatisch abgeschlossen (alle Geräte wurden behoben)</span><span class="sxs-lookup"><span data-stu-id="55875-150">**System confirmation**: The task was automatically completed (all devices remediated)</span></span>
- <span data-ttu-id="55875-151">**N/A**: Informationen sind nicht verfügbar, da wir nicht wissen, wie diese ältere Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="55875-151">**N/A**: Information is not available because we don't know how this older task was completed</span></span>

![Erstellt von und wird von Spalten mit zwei Zeilen abgeschlossen.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a><span data-ttu-id="55875-154">Die obersten Korrekturaktivitäten im Dashboard</span><span class="sxs-lookup"><span data-stu-id="55875-154">Top remediation activities in the dashboard</span></span>

<span data-ttu-id="55875-155">Sehen **Sie sich im** Dashboard für die Verwaltung von Bedrohungen und Sicherheitslücken die aktivitäten zur Behebung von Bedrohungen und [Sicherheitslücken an.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="55875-155">View **Top remediation activities** in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span> <span data-ttu-id="55875-156">Wählen Sie einen der Einträge aus, die zur Seite **Korrektur wechseln.**</span><span class="sxs-lookup"><span data-stu-id="55875-156">Select any of the entries to go to the **Remediation** page.</span></span> <span data-ttu-id="55875-157">Sie können die Korrekturaktivität als abgeschlossen markieren, nachdem das IT-Administratorteam die Aufgabe behoben hat.</span><span class="sxs-lookup"><span data-stu-id="55875-157">You can mark the remediation activity as completed after the IT admin team remediates the task.</span></span>

![Beispiel für die Karte "Top remediation activities" mit einer Tabelle, in der die top Aktivitäten aufgeführt sind, die aus Sicherheitsempfehlungen generiert wurden.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a><span data-ttu-id="55875-159">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="55875-159">Related articles</span></span>

- [<span data-ttu-id="55875-160">Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="55875-160">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="55875-161">Dashboard</span><span class="sxs-lookup"><span data-stu-id="55875-161">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="55875-162">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="55875-162">Security recommendations</span></span>](tvm-security-recommendation.md)