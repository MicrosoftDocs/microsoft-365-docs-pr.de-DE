---
title: Beheben von Sicherheitsrisiken mit Bedrohungs- und Sicherheitsrisikomanagement
description: Beheben Von Sicherheitsschwächen, die durch Sicherheitsempfehlungen erkannt werden, und Erstellen von Ausnahmen bei Bedarf in Bedrohungs- und Sicherheitsrisikomanagement.
keywords: Microsoft Defender für Endpunkt-TVM-Wartung, Microsoft Defender für Endpunkt-TVM, Bedrohungs- und Sicherheitsrisikomanagement, Bedrohungs-& Sicherheitsrisikomanagement, Bedrohungs-& Sicherheitsrisikomanagement-Wartung, TVM-Wartungs-Intune, TVM-Korrektur sccm
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
ms.openlocfilehash: 602a38d8ad27505e81628db265681ac89218e593
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840911"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a><span data-ttu-id="e6811-104">Beheben von Sicherheitsrisiken mit Bedrohungs- und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="e6811-104">Remediate vulnerabilities with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e6811-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e6811-105">**Applies to:**</span></span>
- [<span data-ttu-id="e6811-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e6811-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e6811-107">Bedrohung und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="e6811-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e6811-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6811-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e6811-109">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="e6811-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e6811-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e6811-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a><span data-ttu-id="e6811-111">Korrektur anfordern</span><span class="sxs-lookup"><span data-stu-id="e6811-111">Request remediation</span></span>

<span data-ttu-id="e6811-112">Die Bedrohungs- und Sicherheitsrisikomanagement-Funktion in Microsoft Defender für Endpunkt schließt die Lücke zwischen Sicherheits- und IT-Administratoren über den Korrekturanforderungsworkflow.</span><span class="sxs-lookup"><span data-stu-id="e6811-112">The threat and vulnerability management capability in Microsoft Defender for Endpoint bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="e6811-113">Sicherheitsadministratoren wie Sie können anfordern, dass der IT-Administrator eine Sicherheitslücke von den **Sicherheitsempfehlungen** an Intune behebt.</span><span class="sxs-lookup"><span data-stu-id="e6811-113">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** pages to Intune.</span></span>

### <a name="enable-microsoft-intune-connection"></a><span data-ttu-id="e6811-114">Aktivieren Microsoft Intune Verbindung</span><span class="sxs-lookup"><span data-stu-id="e6811-114">Enable Microsoft Intune connection</span></span>

<span data-ttu-id="e6811-115">Um diese Funktion zu verwenden, aktivieren Sie Ihre Microsoft Intune Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="e6811-115">To use this capability, enable your Microsoft Intune connections.</span></span> <span data-ttu-id="e6811-116">Navigieren Sie im Microsoft Defender Security Center zu **Einstellungen**  >  **Allgemeinen**  >  **erweiterten Features.**</span><span class="sxs-lookup"><span data-stu-id="e6811-116">In the Microsoft Defender Security Center, navigate to **Settings** > **General** > **Advanced features**.</span></span> <span data-ttu-id="e6811-117">Scrollen Sie nach unten, und suchen Sie **nach Microsoft Intune Verbindung.**</span><span class="sxs-lookup"><span data-stu-id="e6811-117">Scroll down and look for **Microsoft Intune connection**.</span></span> <span data-ttu-id="e6811-118">Standardmäßig ist die Umschaltfläche deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e6811-118">By default, the toggle is turned off.</span></span> <span data-ttu-id="e6811-119">Schalten Sie die **Microsoft Intune Verbindungsschaltfläche** **ein.**</span><span class="sxs-lookup"><span data-stu-id="e6811-119">Turn your **Microsoft Intune connection** toggle **On**.</span></span>

<span data-ttu-id="e6811-120">**Hinweis:** Wenn Sie die Intune-Verbindung aktiviert haben, erhalten Sie eine Option zum Erstellen einer Intune-Sicherheitsaufgabe beim Erstellen einer Wartungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="e6811-120">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="e6811-121">Diese Option wird nicht angezeigt, wenn die Verbindung nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e6811-121">This option does not appear if the connection is not set.</span></span>

<span data-ttu-id="e6811-122">Weitere Informationen finden Sie unter ["Verwenden von Intune zum Beheben von Von Microsoft Defender für Endpunkt identifizierten Sicherheitsrisiken".](/intune/atp-manage-vulnerabilities)</span><span class="sxs-lookup"><span data-stu-id="e6811-122">See [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

### <a name="remediation-request-steps"></a><span data-ttu-id="e6811-123">Schritte zur Korrekturanforderung</span><span class="sxs-lookup"><span data-stu-id="e6811-123">Remediation request steps</span></span>

1. <span data-ttu-id="e6811-124">Wechseln Sie im Microsoft Defender Security Center zum navigationsmenü Bedrohungs- und Sicherheitsrisikomanagement, und wählen Sie [**Sicherheitsempfehlungen aus.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="e6811-124">Go to the threat and vulnerability management navigation menu in the Microsoft Defender Security Center, and select [**Security recommendations**](tvm-security-recommendation.md).</span></span>

2. <span data-ttu-id="e6811-125">Wählen Sie eine Sicherheitsempfehlung aus, für die Sie eine Korrektur anfordern möchten, und wählen Sie dann **Korrekturoptionen** aus.</span><span class="sxs-lookup"><span data-stu-id="e6811-125">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span>

3. <span data-ttu-id="e6811-126">Füllen Sie das Formular aus, einschließlich der Informationen, für die Sie eine Korrektur anfordern, zutreffender Gerätegruppen, Priorität, Fälligkeitsdatum und optionaler Hinweise.</span><span class="sxs-lookup"><span data-stu-id="e6811-126">Fill out the form, including what you are requesting remediation for, applicable device groups, priority, due date, and optional notes.</span></span>
    1. <span data-ttu-id="e6811-127">Wenn Sie die Korrekturoption "Achtung erforderlich" auswählen, ist die Auswahl eines Fälligkeitsdatums nicht verfügbar, da keine bestimmte Aktion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e6811-127">If you choose the "attention required" remediation option, selecting a due date will not be available since there is no specific action.</span></span>

4. <span data-ttu-id="e6811-128">Wählen Sie **"Anforderung senden"** aus.</span><span class="sxs-lookup"><span data-stu-id="e6811-128">Select **Submit request**.</span></span> <span data-ttu-id="e6811-129">Durch das Senden einer Korrekturanforderung wird innerhalb Bedrohungs- und Sicherheitsrisikomanagement ein Wartungsaktivitätselement erstellt, das zum Überwachen des Wartungsfortschritts für diese Empfehlung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e6811-129">Submitting a remediation request creates a remediation activity item within threat and vulnerability management, which can be used for monitoring the remediation progress for this recommendation.</span></span> <span data-ttu-id="e6811-130">Dies löst keine Korrektur aus oder wendet keine Änderungen auf Geräte an.</span><span class="sxs-lookup"><span data-stu-id="e6811-130">This will not trigger a remediation or apply any changes to devices.</span></span>

5. <span data-ttu-id="e6811-131">Benachrichtigen Sie Ihren IT-Administrator über die neue Anforderung, und lassen Sie ihn sich bei Intune anmelden, um die Anforderung zu genehmigen oder abzulehnen und eine Paketbereitstellung zu starten.</span><span class="sxs-lookup"><span data-stu-id="e6811-131">Notify your IT Administrator about the new request and have them log into Intune to approve or reject the request and start a package deployment.</span></span>

6. <span data-ttu-id="e6811-132">Wechseln Sie zur Seite [**"Korrektur",**](tvm-remediation.md) um den Status Ihrer Korrekturanfrage anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e6811-132">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span>

<span data-ttu-id="e6811-133">Wenn Sie überprüfen möchten, wie das Ticket in Intune angezeigt wird, finden Sie weitere Informationen unter [Verwenden von Intune zum Beheben von Sicherheitsrisiken,](/intune/atp-manage-vulnerabilities) die von Microsoft Defender für Endpunkt identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="e6811-133">If you want to check how the ticket shows up in Intune, see [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

>[!NOTE]
><span data-ttu-id="e6811-134">Wenn Ihre Anforderung die Behebung von mehr als 10.000 Geräten umfasst, können wir nur 10.000 Geräte zur Behebung an Intune senden.</span><span class="sxs-lookup"><span data-stu-id="e6811-134">If your request involves remediating more than 10,000 devices, we can only send 10,000 devices for remediation to Intune.</span></span>

<span data-ttu-id="e6811-135">Nachdem die Cybersicherheitsschwächen Ihrer Organisation identifiziert und umsetzbaren [Sicherheitsempfehlungen](tvm-security-recommendation.md)zugeordnet wurden, beginnen Sie mit der Erstellung von Sicherheitsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="e6811-135">After your organization's cybersecurity weaknesses are identified and mapped to actionable [security recommendations](tvm-security-recommendation.md), start creating security tasks.</span></span> <span data-ttu-id="e6811-136">Sie können Aufgaben durch die Integration in Microsoft Intune erstellen, in denen Wartungstickets erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e6811-136">You can create tasks through the integration with Microsoft Intune where remediation tickets are created.</span></span>

<span data-ttu-id="e6811-137">Verringern Sie die Gefährdung Ihrer Organisation durch Sicherheitsrisiken, und erhöhen Sie Ihre Sicherheitskonfiguration, indem Sie die Sicherheitsempfehlungen korrigieren.</span><span class="sxs-lookup"><span data-stu-id="e6811-137">Lower your organization's exposure from vulnerabilities and increase your security configuration by remediating the security recommendations.</span></span>

## <a name="view-your-remediation-activities"></a><span data-ttu-id="e6811-138">Anzeigen Ihrer Korrekturaktivitäten</span><span class="sxs-lookup"><span data-stu-id="e6811-138">View your remediation activities</span></span>

<span data-ttu-id="e6811-139">Wenn Sie eine Korrekturanforderung von der Seite "Sicherheitsempfehlungen" übermitteln, wird eine Korrekturaktivität gestartet.</span><span class="sxs-lookup"><span data-stu-id="e6811-139">When you submit a remediation request from the Security recommendations page, it kicks-off a remediation activity.</span></span> <span data-ttu-id="e6811-140">Eine Sicherheitsaufgabe wird erstellt, die auf der Seite Bedrohungs- und Sicherheitsrisikomanagement **Korrektur** nachverfolgt werden kann, und ein Wartungsticket wird in Microsoft Intune erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6811-140">A security task is created that can be tracked in the threat and vulnerability management **Remediation** page, and a remediation ticket is created in Microsoft Intune.</span></span>

<span data-ttu-id="e6811-141">Wenn Sie die Korrekturoption "Aufmerksamkeit erforderlich" ausgewählt haben, gibt es keine Statusanzeige, keinen Ticketstatus oder kein Fälligkeitsdatum, da keine tatsächliche Aktion vorhanden ist, die wir überwachen können.</span><span class="sxs-lookup"><span data-stu-id="e6811-141">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there is no actual action we can monitor.</span></span>

<span data-ttu-id="e6811-142">Sobald Sie sich auf der Seite "Korrektur" befinden, wählen Sie die Korrekturaktivität aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="e6811-142">Once you are in the Remediation page, select the remediation activity that you want to view.</span></span> <span data-ttu-id="e6811-143">Sie können die Korrekturschritte ausführen, den Fortschritt nachverfolgen, die zugehörige Empfehlung anzeigen, in CSV exportieren oder als abgeschlossen markieren.</span><span class="sxs-lookup"><span data-stu-id="e6811-143">You can follow the remediation steps, track progress, view the related recommendation, export to CSV, or mark as complete.</span></span>
<span data-ttu-id="e6811-144">![Beispiel für die Seite "Korrektur" mit einer ausgewählten Korrekturaktivität und dem Flyout dieser Aktivität, in dem die Beschreibung, IT-Dienst- und Geräteverwaltungstools sowie der Fortschritt der Gerätebehebung aufgeführt sind.](images/remediation_flyouteolsw.png)</span><span class="sxs-lookup"><span data-stu-id="e6811-144">![Example of the Remediation page, with a selected remediation activity, and that activity's flyout listing the description, IT service and device management tools, and device remediation progress.](images/remediation_flyouteolsw.png)</span></span>

>[!NOTE]
> <span data-ttu-id="e6811-145">Es gibt einen Aufbewahrungszeitraum von 180 Tagen für abgeschlossene Korrekturaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="e6811-145">There is a 180 day retention period for completed remediation activities.</span></span> <span data-ttu-id="e6811-146">Damit die Seite "Korrektur" optimal ausgeführt wird, wird die Korrekturaktivität 6 Monate nach abschluss entfernt.</span><span class="sxs-lookup"><span data-stu-id="e6811-146">To keep the Remediation page performing optimally, the remediation activity will be removed 6 months after its completion.</span></span>

### <a name="completed-by-column"></a><span data-ttu-id="e6811-147">Abgeschlossen nach Spalte</span><span class="sxs-lookup"><span data-stu-id="e6811-147">Completed by column</span></span>

<span data-ttu-id="e6811-148">Verfolgen Sie, wer die Korrekturaktivität mit der Spalte "Abgeschlossen von" auf der Seite "Korrektur" geschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="e6811-148">Track who closed the remediation activity with the "Completed by" column on the Remediation page.</span></span>

- <span data-ttu-id="e6811-149">**E-Mail-Adresse:** Die E-Mail-Adresse der Person, die die Aufgabe manuell abgeschlossen hat</span><span class="sxs-lookup"><span data-stu-id="e6811-149">**Email address**: The email of the person who manually completed the task</span></span>
- <span data-ttu-id="e6811-150">**Systembestätigung:** Die Aufgabe wurde automatisch abgeschlossen (alle Geräte behoben)</span><span class="sxs-lookup"><span data-stu-id="e6811-150">**System confirmation**: The task was automatically completed (all devices remediated)</span></span>
- <span data-ttu-id="e6811-151">**Nicht** verfügbar: Informationen sind nicht verfügbar, da wir nicht wissen, wie diese ältere Aufgabe abgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="e6811-151">**N/A**: Information is not available because we don't know how this older task was completed</span></span>

![Wird von Spalten mit zwei Zeilen erstellt und abgeschlossen.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a><span data-ttu-id="e6811-154">Wichtigste Wartungsaktivitäten im Dashboard</span><span class="sxs-lookup"><span data-stu-id="e6811-154">Top remediation activities in the dashboard</span></span>

<span data-ttu-id="e6811-155">Zeigen Sie die **wichtigsten Wartungsaktivitäten** im [Bedrohungs- und Sicherheitsrisikomanagement-Dashboard](tvm-dashboard-insights.md)an.</span><span class="sxs-lookup"><span data-stu-id="e6811-155">View **Top remediation activities** in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span> <span data-ttu-id="e6811-156">Wählen Sie einen der Einträge aus, um zur Seite **"Korrektur"** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="e6811-156">Select any of the entries to go to the **Remediation** page.</span></span> <span data-ttu-id="e6811-157">Sie können die Korrekturaktivität als abgeschlossen markieren, nachdem das IT-Administratorteam die Aufgabe behoben hat.</span><span class="sxs-lookup"><span data-stu-id="e6811-157">You can mark the remediation activity as completed after the IT admin team remediates the task.</span></span>

![Beispiel für karte top remediation activities with a table that lists top activities that were generated from security recommendations.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a><span data-ttu-id="e6811-159">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="e6811-159">Related articles</span></span>

- [<span data-ttu-id="e6811-160">Übersicht über Bedrohungen und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="e6811-160">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e6811-161">Dashboard</span><span class="sxs-lookup"><span data-stu-id="e6811-161">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="e6811-162">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="e6811-162">Security recommendations</span></span>](tvm-security-recommendation.md)