---
title: Verwalten von Microsoft Defender for Endpoint-Warnungen
description: Ändern Sie den Status von Warnungen, erstellen Sie Unterdrückungsregeln, um Warnungen auszublenden, Kommentare zu übermitteln und den Änderungsverlauf für einzelne Warnungen im Menü Warnung verwalten zu überprüfen.
keywords: Verwalten von Warnungen, Verwalten, Warnungen, Status, neu, in Bearbeitung, aufgelöst, Warnungen auflösen, Unterdrücken, Unterdrückung, Regeln, Kontext, Verlauf, Kommentare, Änderungen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5acec4e9b43c8af7f85fadd31caefbb15e227029
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062215"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a><span data-ttu-id="0c728-104">Verwalten von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="0c728-104">Manage Microsoft Defender for Endpoint alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0c728-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0c728-105">**Applies to:**</span></span>
- [<span data-ttu-id="0c728-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0c728-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="0c728-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c728-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="0c728-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0c728-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0c728-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0c728-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="0c728-110">Defender for Endpoint benachrichtigt Sie über Warnungen über mögliche bösartige Ereignisse, Attribute und Kontextinformationen.</span><span class="sxs-lookup"><span data-stu-id="0c728-110">Defender for Endpoint notifies you of possible malicious events, attributes, and contextual information through alerts.</span></span> <span data-ttu-id="0c728-111">Eine Zusammenfassung der neuen Warnungen wird im Dashboard für Sicherheitsvorgänge **angezeigt,** und Sie können auf alle Warnungen in der Benachrichtigungswarteschlange **zugreifen.**</span><span class="sxs-lookup"><span data-stu-id="0c728-111">A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue**.</span></span>

<span data-ttu-id="0c728-112">Sie können Warnungen verwalten, indem Sie eine  Warnung in der Warnungswarteschlange oder auf der Registerkarte Warnungen auf der Seite Gerät für ein einzelnes Gerät auswählen.</span><span class="sxs-lookup"><span data-stu-id="0c728-112">You can manage alerts by selecting an alert in the **Alerts queue**, or the **Alerts** tab of the Device page for an individual device.</span></span>

<span data-ttu-id="0c728-113">Wenn Sie eine Warnung an einem dieser Orte auswählen, wird der **Bereich Warnungsverwaltung geöffnet.**</span><span class="sxs-lookup"><span data-stu-id="0c728-113">Selecting an alert in either of those places brings up the **Alert management pane**.</span></span>

![Abbildung des Warnungsverwaltungsbereichs und der Warnungswarteschlange](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a><span data-ttu-id="0c728-115">Link zu einem anderen Vorfall</span><span class="sxs-lookup"><span data-stu-id="0c728-115">Link to another incident</span></span>
<span data-ttu-id="0c728-116">Sie können einen neuen Vorfall aus der Warnung oder einem Link zu einem vorhandenen Vorfall erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c728-116">You can create a new incident from the alert or link to an existing incident.</span></span> 

## <a name="assign-alerts"></a><span data-ttu-id="0c728-117">Zuweisen von Warnungen</span><span class="sxs-lookup"><span data-stu-id="0c728-117">Assign alerts</span></span>
<span data-ttu-id="0c728-118">Wenn eine Warnung noch nicht zugewiesen ist, können Sie **Zuweisen** für mich auswählen, um die Warnung selbst zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="0c728-118">If an alert is not yet assigned, you can select **Assign to me** to assign the alert to yourself.</span></span>


## <a name="suppress-alerts"></a><span data-ttu-id="0c728-119">Unterdrücken von Warnungen</span><span class="sxs-lookup"><span data-stu-id="0c728-119">Suppress alerts</span></span>
<span data-ttu-id="0c728-120">Es kann Szenarien gibt, in denen Sie das Anzeigen von Warnungen im Microsoft Defender Security Center unterdrücken müssen.</span><span class="sxs-lookup"><span data-stu-id="0c728-120">There might be scenarios where you need to suppress alerts from appearing in Microsoft Defender Security Center.</span></span> <span data-ttu-id="0c728-121">Mit Defender for Endpoint können Sie Unterdrückungsregeln für bestimmte Warnungen erstellen, die als harmlos bekannt sind, z. B. bekannte Tools oder Prozesse in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="0c728-121">Defender for Endpoint lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span>

<span data-ttu-id="0c728-122">Unterdrückungsregeln können aus einer vorhandenen Warnung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0c728-122">Suppression rules can be created from an existing alert.</span></span> <span data-ttu-id="0c728-123">Sie können bei Bedarf deaktiviert und erneut aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0c728-123">They can be disabled and reenabled if needed.</span></span>

<span data-ttu-id="0c728-124">Wenn eine Unterdrückungsregel erstellt wird, wird sie ab dem Zeitpunkt wirksam, an dem die Regel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0c728-124">When a suppression rule is created, it will take effect from the point when the rule is created.</span></span> <span data-ttu-id="0c728-125">Die Regel wirkt sich nicht auf vorhandene Warnungen aus, die sich bereits in der Warteschlange befinden, vor der Regelerstellung.</span><span class="sxs-lookup"><span data-stu-id="0c728-125">The rule will not affect existing alerts already in the queue, prior to the rule creation.</span></span> <span data-ttu-id="0c728-126">Die Regel wird nur auf Warnungen angewendet, die die bedingungen erfüllen, die nach dem Erstellen der Regel festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c728-126">The rule will only be applied on alerts that satisfy the conditions set after the rule is created.</span></span>

<span data-ttu-id="0c728-127">Es gibt zwei Kontexte für eine Unterdrückungsregel, aus der Sie auswählen können:</span><span class="sxs-lookup"><span data-stu-id="0c728-127">There are two contexts for a suppression rule that you can choose from:</span></span>

- <span data-ttu-id="0c728-128">**Unterdrücken von Warnungen auf diesem Gerät**</span><span class="sxs-lookup"><span data-stu-id="0c728-128">**Suppress alert on this device**</span></span>
- <span data-ttu-id="0c728-129">**Unterdrücken von Warnungen in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="0c728-129">**Suppress alert in my organization**</span></span>

<span data-ttu-id="0c728-130">Mit dem Kontext der Regel können Sie anpassen, was im Portal angezeigt wird, und sicherstellen, dass nur echte Sicherheitswarnungen im Portal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0c728-130">The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.</span></span>

<span data-ttu-id="0c728-131">Anhand der Beispiele in der folgenden Tabelle können Sie den Kontext für eine Unterdrückungsregel auswählen:</span><span class="sxs-lookup"><span data-stu-id="0c728-131">You can use the examples in the following table to help you choose the context for a suppression rule:</span></span>

| <span data-ttu-id="0c728-132">**Context**</span><span class="sxs-lookup"><span data-stu-id="0c728-132">**Context**</span></span>                           | <span data-ttu-id="0c728-133">**Definition**</span><span class="sxs-lookup"><span data-stu-id="0c728-133">**Definition**</span></span>                                                                                                                                              | <span data-ttu-id="0c728-134">**Beispielszenarien**</span><span class="sxs-lookup"><span data-stu-id="0c728-134">**Example scenarios**</span></span>                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0c728-135">**Unterdrücken von Warnungen auf diesem Gerät**</span><span class="sxs-lookup"><span data-stu-id="0c728-135">**Suppress alert on this device**</span></span>    | <span data-ttu-id="0c728-136">Warnungen mit dem gleichen Warnungstitel und nur auf diesem bestimmten Gerät werden unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="0c728-136">Alerts with the same alert title and on that specific device only will be suppressed.</span></span> <br /><br /><span data-ttu-id="0c728-137">Alle anderen Warnungen auf diesem Gerät werden nicht unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="0c728-137">All other alerts on that device will not be suppressed.</span></span> | <ul><li><span data-ttu-id="0c728-138">Ein Sicherheitsforscher untersucht ein bösartiges Skript, das zum Angriff auf andere Geräte in Ihrer Organisation verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="0c728-138">A security researcher is investigating a malicious script that has been used to attack other devices in your organization.</span></span></li><li><span data-ttu-id="0c728-139">Ein Entwickler erstellt regelmäßig PowerShell-Skripts für sein Team.</span><span class="sxs-lookup"><span data-stu-id="0c728-139">A developer regularly creates PowerShell scripts for their team.</span></span></li></ul> |
| <span data-ttu-id="0c728-140">**Unterdrücken von Warnungen in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="0c728-140">**Suppress alert in my organization**</span></span> | <span data-ttu-id="0c728-141">Warnungen mit dem gleichen Warnungstitel auf jedem Gerät werden unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="0c728-141">Alerts with the same alert title on any device will be suppressed.</span></span>                                                                                         | <ul><li><span data-ttu-id="0c728-142">Ein gutartiges Verwaltungstool wird von allen in Ihrer Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c728-142">A benign administrative tool is used by everyone in your organization.</span></span></li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a><span data-ttu-id="0c728-143">Unterdrücken Sie eine Warnung, und erstellen Sie eine neue Unterdrückungsregel:</span><span class="sxs-lookup"><span data-stu-id="0c728-143">Suppress an alert and create a new suppression rule:</span></span>
<span data-ttu-id="0c728-144">Erstellen Sie benutzerdefinierte Regeln, um zu steuern, wann Warnungen unterdrückt oder aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0c728-144">Create custom rules to control when alerts are suppressed, or resolved.</span></span> <span data-ttu-id="0c728-145">Sie können den Kontext steuern, für den eine Warnung unterdrückt wird, indem Sie den Warnungstitel, den Kompromissindikator und die Bedingungen angeben.</span><span class="sxs-lookup"><span data-stu-id="0c728-145">You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions.</span></span> <span data-ttu-id="0c728-146">Nachdem Sie den Kontext angegeben haben, können Sie die Aktion und den Bereich für die Warnung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0c728-146">After specifying the context, you’ll be able to configure the action and scope on the alert.</span></span> 

1. <span data-ttu-id="0c728-147">Wählen Sie die Warnung aus, die Sie unterdrücken möchten.</span><span class="sxs-lookup"><span data-stu-id="0c728-147">Select the alert you'd like to suppress.</span></span> <span data-ttu-id="0c728-148">Dadurch wird der Bereich **Warnungsverwaltung** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0c728-148">This brings up the **Alert management** pane.</span></span>

2.  <span data-ttu-id="0c728-149">Wählen **Sie Unterdrückungsregel erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="0c728-149">Select **Create a suppression rule**.</span></span>

    <span data-ttu-id="0c728-150">Mit diesen Attributen können Sie eine Unterdrückungsbedingung erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c728-150">You can create a suppression condition using these attributes.</span></span> <span data-ttu-id="0c728-151">Zwischen jeder Bedingung wird ein AND-Operator angewendet, sodass die Unterdrückung nur erfolgt, wenn alle Bedingungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="0c728-151">An AND operator is applied between each condition, so suppression occurs only if all conditions are met.</span></span>
    
    * <span data-ttu-id="0c728-152">Datei SHA1</span><span class="sxs-lookup"><span data-stu-id="0c728-152">File SHA1</span></span>
    * <span data-ttu-id="0c728-153">Dateiname – Platzhalter wird unterstützt</span><span class="sxs-lookup"><span data-stu-id="0c728-153">File name - wildcard supported</span></span>
    * <span data-ttu-id="0c728-154">Ordnerpfad – Platzhalter unterstützt</span><span class="sxs-lookup"><span data-stu-id="0c728-154">Folder path - wildcard supported</span></span>
    * <span data-ttu-id="0c728-155">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="0c728-155">IP address</span></span>
    * <span data-ttu-id="0c728-156">URL – Platzhalter unterstützt</span><span class="sxs-lookup"><span data-stu-id="0c728-156">URL - wildcard supported</span></span>
    * <span data-ttu-id="0c728-157">Befehlszeile – Platzhalter unterstützt</span><span class="sxs-lookup"><span data-stu-id="0c728-157">Command line - wildcard supported</span></span>

3. <span data-ttu-id="0c728-158">Wählen Sie **das Auslösende IOC aus.**</span><span class="sxs-lookup"><span data-stu-id="0c728-158">Select the **Triggering IOC**.</span></span>
    
4. <span data-ttu-id="0c728-159">Geben Sie die Aktion und den Bereich für die Warnung an.</span><span class="sxs-lookup"><span data-stu-id="0c728-159">Specify the action and scope on the alert.</span></span> <br>
   <span data-ttu-id="0c728-160">Sie können eine Warnung automatisch auflösen oder im Portal ausblenden.</span><span class="sxs-lookup"><span data-stu-id="0c728-160">You can automatically resolve an alert or hide it from the portal.</span></span> <span data-ttu-id="0c728-161">Warnungen, die automatisch aufgelöst werden, werden im Abschnitt "Aufgelöst" der Warnungswarteschlange, der Warnungsseite und der Gerätezeitachse angezeigt und werden als in Defender for Endpoint-APIs aufgelöst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c728-161">Alerts that are automatically resolved will appear in the resolved section of the alerts queue, alert page, and device timeline and will appear as resolved across Defender for Endpoint APIs.</span></span> <br><br> <span data-ttu-id="0c728-162">Warnungen, die als ausgeblendet markiert sind, werden sowohl für die zugeordneten Warnungen des Geräts als auch über das Dashboard aus dem gesamten System unterdrückt und nicht über Defender for Endpoint-APIs gestreamt.</span><span class="sxs-lookup"><span data-stu-id="0c728-162">Alerts that are marked as hidden will be suppressed from the entire system, both on the device's associated alerts and from the dashboard and will not be streamed across Defender for Endpoint APIs.</span></span>


5. <span data-ttu-id="0c728-163">Geben Sie einen Regelnamen und einen Kommentar ein.</span><span class="sxs-lookup"><span data-stu-id="0c728-163">Enter a rule name and a comment.</span></span>

6. <span data-ttu-id="0c728-164">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0c728-164">Click **Save**.</span></span>

#### <a name="view-the-list-of-suppression-rules"></a><span data-ttu-id="0c728-165">Anzeigen der Liste der Unterdrückungsregeln</span><span class="sxs-lookup"><span data-stu-id="0c728-165">View the list of suppression rules</span></span>

1. <span data-ttu-id="0c728-166">Wählen Sie im Navigationsbereich  >  Einstellungsbenachrichtigungsunterdrückung **aus.**</span><span class="sxs-lookup"><span data-stu-id="0c728-166">In the navigation pane, select **Settings** > **Alert suppression**.</span></span>

2. <span data-ttu-id="0c728-167">Die Liste der Unterdrückungsregeln zeigt alle Regeln an, die Benutzer in Ihrer Organisation erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0c728-167">The list of suppression rules shows all the rules that users in your organization have created.</span></span>

<span data-ttu-id="0c728-168">Weitere Informationen zum Verwalten von Unterdrückungsregeln finden Sie unter [Manage suppression rules](manage-suppression-rules.md)</span><span class="sxs-lookup"><span data-stu-id="0c728-168">For more information on managing suppression rules, see [Manage suppression rules](manage-suppression-rules.md)</span></span>

## <a name="change-the-status-of-an-alert"></a><span data-ttu-id="0c728-169">Ändern des Status einer Warnung</span><span class="sxs-lookup"><span data-stu-id="0c728-169">Change the status of an alert</span></span>

<span data-ttu-id="0c728-170">Sie können Warnungen (als **Neu,** **In Bearbeitung** oder **Aufgelöst**) kategorisieren, indem Sie ihren Status im Verlauf der Untersuchung ändern.</span><span class="sxs-lookup"><span data-stu-id="0c728-170">You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="0c728-171">Auf diese Weise können Sie organisieren und verwalten, wie Ihr Team auf Warnungen reagieren kann.</span><span class="sxs-lookup"><span data-stu-id="0c728-171">This helps you organize and manage how your team can respond to alerts.</span></span>

<span data-ttu-id="0c728-172">Beispielsweise kann ein Teamleiter  alle neuen Warnungen überprüfen und diese zur weiteren Analyse der **Warteschlange In Bearbeitung** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0c728-172">For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.</span></span>

<span data-ttu-id="0c728-173">Alternativ kann der Teamleiter die  Warnung der Aufgelösten Warteschlange zuweisen, wenn er weiß, dass die Warnung gutartig ist, von einem gerät kommt, das irrelevant ist (z. B. eines, das einem Sicherheitsadministrator gehört) oder über eine frühere Warnung behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="0c728-173">Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a device that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.</span></span>



## <a name="alert-classification"></a><span data-ttu-id="0c728-174">Warnungsklassifizierung</span><span class="sxs-lookup"><span data-stu-id="0c728-174">Alert classification</span></span>
<span data-ttu-id="0c728-175">Sie können keine Klassifizierung festlegen oder angeben, ob es sich bei einer Warnung um eine echte warnung oder um eine falsche Warnung handelt.</span><span class="sxs-lookup"><span data-stu-id="0c728-175">You can choose not to set a classification, or specify whether an alert is a true alert or a false alert.</span></span> <span data-ttu-id="0c728-176">Es ist wichtig, die Klassifizierung des echten positiven/falsch positiven Werts zu liefern.</span><span class="sxs-lookup"><span data-stu-id="0c728-176">It's important to provide the classification of true positive/false positive.</span></span> <span data-ttu-id="0c728-177">Diese Klassifizierung wird verwendet, um die Warnungsqualität zu überwachen und Warnungen genauer zu machen.</span><span class="sxs-lookup"><span data-stu-id="0c728-177">This classification is used to monitor alert quality, and make alerts more accurate.</span></span> <span data-ttu-id="0c728-178">Das Feld "Bestimmung" definiert zusätzliche Genauigkeit für eine "true positive" Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="0c728-178">The "determination" field defines additional fidelity for a "true positive" classification.</span></span> 

## <a name="add-comments-and-view-the-history-of-an-alert"></a><span data-ttu-id="0c728-179">Hinzufügen von Kommentaren und Anzeigen des Verlaufs einer Warnung</span><span class="sxs-lookup"><span data-stu-id="0c728-179">Add comments and view the history of an alert</span></span>
<span data-ttu-id="0c728-180">Sie können Kommentare hinzufügen und verlaufshistorische Ereignisse zu einer Warnung anzeigen, um frühere Änderungen an der Warnung zu sehen.</span><span class="sxs-lookup"><span data-stu-id="0c728-180">You can add comments and view historical events about an alert to see previous changes made to the alert.</span></span>

<span data-ttu-id="0c728-181">Wann immer eine Änderung oder ein Kommentar an einer Warnung vorgenommen wird, wird sie im Abschnitt **Kommentare und Verlauf** aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0c728-181">Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.</span></span>

<span data-ttu-id="0c728-182">Hinzugefügte Kommentare werden sofort in diesem Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c728-182">Added comments instantly appear on the pane.</span></span>


## <a name="related-topics"></a><span data-ttu-id="0c728-183">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0c728-183">Related topics</span></span>
- [<span data-ttu-id="0c728-184">Verwalten von Unterdrückungsregeln</span><span class="sxs-lookup"><span data-stu-id="0c728-184">Manage suppression rules</span></span>](manage-suppression-rules.md)
- [<span data-ttu-id="0c728-185">Anzeigen und Organisieren der Microsoft Defender for Endpoint Alerts-Warteschlange</span><span class="sxs-lookup"><span data-stu-id="0c728-185">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="0c728-186">Untersuchen von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="0c728-186">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="0c728-187">Untersuchen einer Datei, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="0c728-187">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="0c728-188">Untersuchen von Geräten in der Microsoft Defender for Endpoint Devices-Liste</span><span class="sxs-lookup"><span data-stu-id="0c728-188">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="0c728-189">Untersuchen einer einer Microsoft Defender for Endpoint-Warnung zugeordneten IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="0c728-189">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="0c728-190">Untersuchen einer Domäne, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="0c728-190">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="0c728-191">Untersuchen eines Benutzerkontos in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0c728-191">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
