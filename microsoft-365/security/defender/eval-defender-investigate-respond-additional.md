---
title: Testen Sie Microsoft 365 Defender Vorfallreaktionsfunktionen in einer Pilotumgebung, um Vorfälle zu priorisieren und zu verwalten, eine automatisierte Untersuchung und Reaktion zu konfigurieren und die erweiterte Suche zu verwenden.
description: Testen Sie die Funktionen zur Reaktion auf Vorfälle in Microsoft 365 Defender, um Vorfälle zu priorisieren und zu verwalten, Untersuchungen zu automatisieren und die erweiterte Suche bei der Bedrohungserkennung zu verwenden.
keywords: Microsoft 365 Defender Testversion, testen Sie Microsoft 365 Defender, bewerten Sie Microsoft 365 Defender, Microsoft 365 Defender Evaluierungslabor, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c554f7bcedbdb64118639f5a455fd6f6e55daaa6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458113"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a><span data-ttu-id="cf161-104">Testen Microsoft 365 Defender Vorfallreaktionsfunktionen in einer Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="cf161-104">Try Microsoft 365 Defender incident response capabilities in a pilot environment</span></span>

<span data-ttu-id="cf161-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cf161-105">**Applies to:**</span></span>
- <span data-ttu-id="cf161-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf161-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cf161-107">Dieser Artikel ist [Schritt 2 von 2,](eval-defender-investigate-respond.md) um eine Untersuchung und Reaktion auf einen Vorfall in Microsoft 365 Defender mithilfe einer Pilotumgebung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="cf161-107">This article is [Step 2 of 2](eval-defender-investigate-respond.md) in the process of performing an investigation and response of an incident in Microsoft 365 Defender using a pilot environment.</span></span> <span data-ttu-id="cf161-108">Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-investigate-respond.md)</span><span class="sxs-lookup"><span data-stu-id="cf161-108">For more information about this process, see the [overview](eval-defender-investigate-respond.md) article.</span></span>

<span data-ttu-id="cf161-109">Nachdem Sie eine [Vorfallreaktion für einen simulierten Angriff](eval-defender-investigate-respond-simulate-attack.md)ausgeführt haben, können Sie hier einige Microsoft 365 Defender Funktionen erkunden:</span><span class="sxs-lookup"><span data-stu-id="cf161-109">Once you have performed an [incident response for a simulated attack](eval-defender-investigate-respond-simulate-attack.md), here are some Microsoft 365 Defender capabilities to explore:</span></span>

|<span data-ttu-id="cf161-110">Funktion</span><span class="sxs-lookup"><span data-stu-id="cf161-110">Capability</span></span> |<span data-ttu-id="cf161-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf161-111">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="cf161-112">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="cf161-112">Prioritize incidents</span></span>](#prioritize-incidents) | <span data-ttu-id="cf161-113">Verwenden Sie filtering and sorting of the incidents queue to determine which incidents to address next.</span><span class="sxs-lookup"><span data-stu-id="cf161-113">Use filtering and sorting of the incidents queue to determine which incidents to address next.</span></span> |
| [<span data-ttu-id="cf161-114">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="cf161-114">Manage incidents</span></span>](#manage-incidents) | <span data-ttu-id="cf161-115">Ändern Sie Vorfalleigenschaften, um die korrekte Zuweisung sicherzustellen, Tags und Kommentare hinzuzufügen und einen Vorfall zu beheben.</span><span class="sxs-lookup"><span data-stu-id="cf161-115">Modify incident properties to ensure correct assignment, add tags and comments, and to resolve an incident.</span></span> |
| [<span data-ttu-id="cf161-116">Automatische Untersuchung und Reaktion</span><span class="sxs-lookup"><span data-stu-id="cf161-116">Automated investigation and response</span></span>](#examine-automated-investigation-and-response-with-the-action-center) | <span data-ttu-id="cf161-117">Air-Funktionen (Automated Investigation and Response), die Ihrem Sicherheitsteam helfen können, Bedrohungen effizienter und effektiver zu bewältigen.</span><span class="sxs-lookup"><span data-stu-id="cf161-117">Automated investigation and response (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span> <span data-ttu-id="cf161-118">Das Info-Center ist ein "einzelner Bereich" für Vorfall- und Warnungsaufgaben wie das Genehmigen ausstehender Abhilfemaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="cf161-118">The Action center is a "single pane of glass" experience for incident and alert tasks such as approving pending remediation actions.</span></span> |
| [<span data-ttu-id="cf161-119">Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="cf161-119">Advanced hunting</span></span>](#advanced-hunting) | <span data-ttu-id="cf161-120">Ein abfragebasiertes Tool zur Bedrohungssuche, mit dem Sie Ereignisse in Ihrem Netzwerk proaktiv untersuchen und Bedrohungsindikatoren und Entitäten suchen können.</span><span class="sxs-lookup"><span data-stu-id="cf161-120">A query-based threat-hunting tool that lets you proactively inspect events in your network and locate threat indicators and entities.</span></span> <span data-ttu-id="cf161-121">Sie verwenden auch die erweiterte Suche während der Untersuchung und Behebung eines Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="cf161-121">You also use advanced hunting during the investigation and remediation of an incident.</span></span> |
||||

## <a name="prioritize-incidents"></a><span data-ttu-id="cf161-122">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="cf161-122">Prioritize incidents</span></span>

<span data-ttu-id="cf161-123">Sie gelangen in der Schnellstartleiste des Microsoft 365 Defender-Portals ( security.microsoft.com ) von **Vorfällen & Warnungen > Vorfällen** in die Vorfallswarteschlange.[](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="cf161-123">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="cf161-124">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cf161-124">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Beispiel für die Vorfallwarteschlange":::

<span data-ttu-id="cf161-126">Der Abschnitt **"Letzte Vorfälle und Warnungen"** zeigt ein Diagramm der Anzahl der empfangenen Warnungen und vorfälle, die in den letzten 24 Stunden erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="cf161-126">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="cf161-127">Um die Liste der Vorfälle zu untersuchen und deren Wichtigkeit für die Zuweisung und Untersuchung zu priorisieren, können Sie:</span><span class="sxs-lookup"><span data-stu-id="cf161-127">To examine the list of incidents and prioritize their importance for assignment and investigation, you can:</span></span> 

- <span data-ttu-id="cf161-128">Konfigurieren Sie anpassbare Spalten (wählen **Sie Spalten auswählen)** aus, um Einblicke in die verschiedenen Merkmale des Vorfalls oder der betroffenen Entitäten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cf161-128">Configure customizable columns (select **Choose columns**) to give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="cf161-129">Auf diese Weise können Sie eine fundierte Entscheidung hinsichtlich der Priorisierung von Vorfällen für die Analyse treffen.</span><span class="sxs-lookup"><span data-stu-id="cf161-129">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

- <span data-ttu-id="cf161-130">Verwenden Sie die Filterung, um sich auf ein bestimmtes Szenario oder eine bestimmte Bedrohung zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="cf161-130">Use filtering to focus on a specific scenario or threat.</span></span> <span data-ttu-id="cf161-131">Das Anwenden von Filtern auf die Vorfallswarteschlange kann helfen, zu bestimmen, welche Vorfälle sofortige Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="cf161-131">Applying filters on the incident queue can help determine which incidents require immediate attention.</span></span> 

<span data-ttu-id="cf161-132">Wählen Sie in der Standardvorfallswarteschlange **Filter** aus, um einen **Filterbereich** anzuzeigen, aus dem Sie eine bestimmte Gruppe von Vorfällen angeben können.</span><span class="sxs-lookup"><span data-stu-id="cf161-132">From the default incident queue, select **Filters** to see a **Filters** pane, from which you can specify a specific set of incidents.</span></span> <span data-ttu-id="cf161-133">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cf161-133">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Beispiel für den Filterbereich für die Vorfallwarteschlange":::

<span data-ttu-id="cf161-135">Weitere Informationen finden Sie unter [Priorisieren von Vorfällen.](incident-queue.md)</span><span class="sxs-lookup"><span data-stu-id="cf161-135">For more information, see [Prioritize incidents](incident-queue.md).</span></span>

## <a name="manage-incidents"></a><span data-ttu-id="cf161-136">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="cf161-136">Manage incidents</span></span>

<span data-ttu-id="cf161-137">Sie können Vorfälle aus dem **Bereich "Vorfall verwalten"** für einen Vorfall verwalten.</span><span class="sxs-lookup"><span data-stu-id="cf161-137">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="cf161-138">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cf161-138">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Beispiel für den Bereich &quot;Vorfall verwalten&quot; eines Vorfalls":::

<span data-ttu-id="cf161-140">Sie können diesen Bereich über den Link **"Vorfall verwalten"** auf folgendem Link anzeigen:</span><span class="sxs-lookup"><span data-stu-id="cf161-140">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="cf161-141">Eigenschaftenbereich eines Vorfalls in der Vorfallwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="cf161-141">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="cf161-142">**Zusammenfassungsseite** eines Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="cf161-142">**Summary** page of an incident.</span></span>

<span data-ttu-id="cf161-143">Hier sind die Möglichkeiten, wie Sie Ihre Vorfälle verwalten können:</span><span class="sxs-lookup"><span data-stu-id="cf161-143">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="cf161-144">Bearbeiten des Vorfallnamens</span><span class="sxs-lookup"><span data-stu-id="cf161-144">Edit the incident name</span></span>

  <span data-ttu-id="cf161-145">Ändern Sie den utomanisch zugewiesenen Namen basierend auf den bewährten Methoden Ihres Sicherheitsteams.</span><span class="sxs-lookup"><span data-stu-id="cf161-145">Change the utomatically assigned name based on your security team best practices.</span></span>
  
- <span data-ttu-id="cf161-146">Hinzufügen von Ereigniskategorien</span><span class="sxs-lookup"><span data-stu-id="cf161-146">Add incident tags</span></span>

  <span data-ttu-id="cf161-147">Fügen Sie Tags hinzu, die Ihr Sicherheitsteam zum Klassifizieren von Vorfällen verwendet, die später gefiltert werden können.</span><span class="sxs-lookup"><span data-stu-id="cf161-147">Add tags that your security team uses to classify incidents, which can be later filtered.</span></span>
  
- <span data-ttu-id="cf161-148">Zuweisen des Vorfalls zu sich selbst</span><span class="sxs-lookup"><span data-stu-id="cf161-148">Assign the incident to yourself</span></span>

  <span data-ttu-id="cf161-149">Weisen Sie ihn Ihrem Benutzerkontonamen zu, der später gefiltert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cf161-149">Assign it to your user account name, which can be later filtered.</span></span>
  
- <span data-ttu-id="cf161-150">Beheben eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="cf161-150">Resolve an incident</span></span>

  <span data-ttu-id="cf161-151">Schließen Sie den Vorfall, nachdem er behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="cf161-151">Close the incident after it has been remediated.</span></span>
  
- <span data-ttu-id="cf161-152">Festlegen der Klassifizierung und Bestimmung</span><span class="sxs-lookup"><span data-stu-id="cf161-152">Set its classification and determination</span></span>

  <span data-ttu-id="cf161-153">Klassifizieren und wählen Sie den Bedrohungstyp aus, wenn Sie einen Vorfall beheben.</span><span class="sxs-lookup"><span data-stu-id="cf161-153">Classify and select the threat type when you resolve an incident.</span></span>
  
- <span data-ttu-id="cf161-154">Kommentare hinzufügen</span><span class="sxs-lookup"><span data-stu-id="cf161-154">Add comments</span></span>

  <span data-ttu-id="cf161-155">Verwenden Sie Kommentare für Fortschritt, Notizen oder andere Informationen, die auf den bewährten Methoden Ihres Sicherheitsteams basieren.</span><span class="sxs-lookup"><span data-stu-id="cf161-155">Use comments for progress, notes, or other information based on your security team best practices.</span></span> <span data-ttu-id="cf161-156">Der vollständige Kommentarverlauf ist über die Option **"Kommentare und Verlauf"** auf der Detailseite eines Vorfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cf161-156">The full comment history is available from the **Comments and history** option in the details page of an incident.</span></span>

<span data-ttu-id="cf161-157">Weitere Informationen finden Sie unter [Verwalten von Vorfällen.](manage-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="cf161-157">For more information, see [Manage incidents](manage-incidents.md).</span></span>

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a><span data-ttu-id="cf161-158">Untersuchen der automatisierten Untersuchung und Reaktion mit dem Info-Center</span><span class="sxs-lookup"><span data-stu-id="cf161-158">Examine automated investigation and response with the Action center</span></span>

<span data-ttu-id="cf161-159">Je nachdem, wie automatisierte Untersuchungs- und Reaktionsfunktionen für Ihre Organisation konfiguriert sind, werden Korrekturmaßnahmen automatisch oder nur nach Genehmigung durch Ihr Sicherheitsteam ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cf161-159">Depending on how automated investigation and response capabilities are configured for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="cf161-160">Alle Aktionen, ob ausstehend oder abgeschlossen, werden im [Info-Center](m365d-action-center.md)aufgelistet, in dem ausstehende und abgeschlossene Korrekturaktionen für Ihre Geräte, E-Mails & Inhalte für die Zusammenarbeit und Identitäten an einem Ort aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="cf161-160">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md), which lists pending and completed remediation actions for your devices, email & collaboration content, and identities in one location.</span></span>

<span data-ttu-id="cf161-161">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cf161-161">Here's an example.</span></span>

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Einheitliches Info-Center in Microsoft 365 Defender":::

<span data-ttu-id="cf161-163">Im Info-Center können Sie ausstehende Aktionen auswählen und diese dann im Flyoutbereich genehmigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="cf161-163">From the Action center, you can select pending actions and then approve or reject them in the flyout pane.</span></span> <span data-ttu-id="cf161-164">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cf161-164">Here's an example.</span></span>

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="Genehmigen oder Ablehnen einer Aktion":::

<span data-ttu-id="cf161-166">Genehmigen (oder ablehnen) Sie ausstehende Aktionen so bald wie möglich, damit Ihre automatisierten Untersuchungen zeitnah fortgesetzt und abgeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="cf161-166">Approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span>

<span data-ttu-id="cf161-167">Weitere Informationen finden Sie im [Info-Center](m365d-action-center.md)für [automatisierte Untersuchung und Reaktion.](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="cf161-167">For more information, see [Automated investigation and response](m365d-autoir.md) and [Action center](m365d-action-center.md).</span></span>

## <a name="advanced-hunting"></a><span data-ttu-id="cf161-168">Erweiterte Bedrohungssuche</span><span class="sxs-lookup"><span data-stu-id="cf161-168">Advanced hunting</span></span>

> [!NOTE]
> <span data-ttu-id="cf161-169">Bevor wir Sie durch die Simulation der erweiterten Suche führen, sehen Sie sich das folgende Video an, um erweiterte Suchkonzepte zu verstehen, zu sehen, wo Sie sie im Portal finden und wissen, wie sie Ihnen bei Ihren Sicherheitsvorgängen helfen kann.</span><span class="sxs-lookup"><span data-stu-id="cf161-169">Before we walk you through the advanced hunting simulation, watch the following video to understand advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


<span data-ttu-id="cf161-170">Wenn es sich bei der [optionalen dateilosen PowerShell-Angriffssimulation](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) um einen echten Angriff handelte, der bereits die Anmeldeinformationszugriffsphase erreicht hat, können Sie die erweiterte Suche jederzeit in der Untersuchung verwenden, um proaktiv Ereignisse und Datensätze im Netzwerk mithilfe der Informationen zu durchsuchen, die Sie bereits aus den generierten Warnungen und betroffenen Entitäten kennen.</span><span class="sxs-lookup"><span data-stu-id="cf161-170">If the [optional fileless PowerShell attack simulation](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) were a real attack that had already reached the credential access stage, you can use advanced hunting at any point in the investigation to proactively search through events and records in the network using what you already know from the generated alerts and affected entities.</span></span> <span data-ttu-id="cf161-171">Sie können beispielsweise in den letzten 30 Tagen alle Verbindungen mit der externen IP-Adresse abfragen.</span><span class="sxs-lookup"><span data-stu-id="cf161-171">For instance, you can query for any connections to the external IP address in the past 30 days.</span></span>

### <a name="hunting-environment-requirements"></a><span data-ttu-id="cf161-172">Anforderungen an die Umgebungssuche</span><span class="sxs-lookup"><span data-stu-id="cf161-172">Hunting environment requirements</span></span>

<span data-ttu-id="cf161-173">Für diese Simulation ist ein einzelnes internes Postfach und Gerät erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cf161-173">There's a single internal mailbox and device required for this simulation.</span></span> <span data-ttu-id="cf161-174">Sie benötigen auch ein externes E-Mail-Konto, um die Testnachricht zu senden.</span><span class="sxs-lookup"><span data-stu-id="cf161-174">You'll also need an external email account to send the test message.</span></span>

1. <span data-ttu-id="cf161-175">Stellen Sie sicher, dass Ihr Mandant [Microsoft 365 Defender aktiviert](m365d-enable.md#confirm-that-the-service-is-on)hat.</span><span class="sxs-lookup"><span data-stu-id="cf161-175">Verify that your tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>
2. <span data-ttu-id="cf161-176">Identifizieren Sie ein Zielpostfach, das für den Empfang von E-Mails verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cf161-176">Identify a target mailbox to be used for receiving email.</span></span>

   - <span data-ttu-id="cf161-177">Dieses Postfach muss von Microsoft Defender auf Office 365 überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="cf161-177">This mailbox must be monitored by Microsoft Defender for Office 365</span></span>

   - <span data-ttu-id="cf161-178">Das Gerät aus Anforderung 3 muss auf dieses Postfach zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cf161-178">The device from requirement 3 needs to access this mailbox</span></span>

3. <span data-ttu-id="cf161-179">Konfigurieren eines Testgeräts:</span><span class="sxs-lookup"><span data-stu-id="cf161-179">Configure a test device:</span></span>

    <span data-ttu-id="cf161-180">a.</span><span class="sxs-lookup"><span data-stu-id="cf161-180">a.</span></span> <span data-ttu-id="cf161-181">Stellen Sie sicher, dass Sie Windows 10 Version 1903 oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf161-181">Make sure you are using Windows 10 version 1903 or later version.</span></span>

    <span data-ttu-id="cf161-182">b.</span><span class="sxs-lookup"><span data-stu-id="cf161-182">b.</span></span> <span data-ttu-id="cf161-183">Verknüpfen Sie das Testgerät mit der Testdomäne.</span><span class="sxs-lookup"><span data-stu-id="cf161-183">Join the test device to the test domain.</span></span>

    <span data-ttu-id="cf161-184">c.</span><span class="sxs-lookup"><span data-stu-id="cf161-184">c.</span></span> <span data-ttu-id="cf161-185">[Aktivieren Sie Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span><span class="sxs-lookup"><span data-stu-id="cf161-185">[Turn on Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="cf161-186">Wenn Sie Probleme beim Aktivieren von Windows Defender Antivirus haben, lesen Sie [dieses Problembehandlungsthema.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="cf161-186">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

    <span data-ttu-id="cf161-187">d.</span><span class="sxs-lookup"><span data-stu-id="cf161-187">d.</span></span> <span data-ttu-id="cf161-188">[Onboarding in Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="cf161-188">[Onboard to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="cf161-189">Ausführen der Simulation</span><span class="sxs-lookup"><span data-stu-id="cf161-189">Run the simulation</span></span>

1. <span data-ttu-id="cf161-190">Senden Sie von einem externen E-Mail-Konto aus eine E-Mail an das Postfach, das in Schritt 2 des Abschnitts mit den Anforderungen für die Suchumgebung identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="cf161-190">From an external email account, send an email to the mailbox identified in step 2 of the hunting environment requirements section.</span></span> <span data-ttu-id="cf161-191">Fügen Sie eine Anlage hinzu, die über alle vorhandenen E-Mail-Filterrichtlinien zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="cf161-191">Include an attachment that will be allowed through any existing email filter policies.</span></span> <span data-ttu-id="cf161-192">Diese Datei muss nicht bösartig oder eine ausführbare Datei sein.</span><span class="sxs-lookup"><span data-stu-id="cf161-192">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="cf161-193">Vorgeschlagene Dateitypen sind <i>.pdf, </i> <i>.exe</i> (sofern zulässig) oder ein Office Dokumenttyp, z. B. eine Word-Datei.</span><span class="sxs-lookup"><span data-stu-id="cf161-193">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or an Office document type such as a Word file.</span></span>

2. <span data-ttu-id="cf161-194">Öffnen Sie die gesendete E-Mail von dem Gerät, das gemäß der Definition in Schritt 3 des Abschnitts mit den Anforderungen an die Umgebung für die Suche konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="cf161-194">Open the sent email from the device configured as defined in step 3 of the hunting environment requirements section.</span></span> <span data-ttu-id="cf161-195">Öffnen Sie die Anlage, oder speichern Sie die Datei auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="cf161-195">Either open the attachment or save the file to the device.</span></span>

#### <a name="go-hunting"></a><span data-ttu-id="cf161-196">Suche gehen</span><span class="sxs-lookup"><span data-stu-id="cf161-196">Go hunting</span></span>

1. <span data-ttu-id="cf161-197">Öffnen Sie das [Microsoft 365 Defender Portal.](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="cf161-197">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="cf161-198">Wählen Sie im Navigationsbereich **"Suche > Erweiterte Suche"** aus.</span><span class="sxs-lookup"><span data-stu-id="cf161-198">From the navigation pane, select **Hunting > Advanced hunting**.</span></span>

3. <span data-ttu-id="cf161-199">Erstellen Sie eine Abfrage, die mit dem Sammeln von E-Mail-Ereignissen beginnt.</span><span class="sxs-lookup"><span data-stu-id="cf161-199">Build a query that starts by gathering email events.</span></span>

   1. <span data-ttu-id="cf161-200">Select **Query > New**.</span><span class="sxs-lookup"><span data-stu-id="cf161-200">Select **Query > New**.</span></span>

   1. <span data-ttu-id="cf161-201">Doppelklicken Sie in den **E-Mail-Gruppen** unter **"Erweiterte Suche"** auf **"EmailEvents".**</span><span class="sxs-lookup"><span data-stu-id="cf161-201">In the **Email** groups under **Advanced hunting**, double-click **EmailEvents**.</span></span> <span data-ttu-id="cf161-202">Dies sollte im Abfragefenster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cf161-202">You should see this in the query window.</span></span>

      ```console
      EmailEvents
      ```

   1. <span data-ttu-id="cf161-203">Ändern Sie den Zeitrahmen der Abfrage in die letzten 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="cf161-203">Change the time frame of the query to the last 24 hours.</span></span> <span data-ttu-id="cf161-204">Angenommen, die E-Mail, die Sie beim Ausführen der oben genannten Simulation gesendet haben, lag in den letzten 24 Stunden, andernfalls ändern Sie den Zeitrahmen nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="cf161-204">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame as needed.</span></span>

   1. <span data-ttu-id="cf161-205">Wählen Sie **Abfrage ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="cf161-205">Select **Run query**.</span></span> <span data-ttu-id="cf161-206">Je nach Pilotumgebung haben Sie möglicherweise unterschiedliche Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="cf161-206">You may have differing results depending on your pilot environment.</span></span>

      > [!NOTE]
      > <span data-ttu-id="cf161-207">Weitere Informationen zum Filtern von Optionen zum Einschränken der Datenrückgabe finden Sie im nächsten Schritt.</span><span class="sxs-lookup"><span data-stu-id="cf161-207">See the next step for filtering options to limit data return.</span></span>

      ![Beispiel für die Abfrageergebnisse der erweiterten Suche](../../media/mtp/fig19.png)

        > [!NOTE]
        > <span data-ttu-id="cf161-209">Bei der erweiterten Suche werden Abfrageergebnisse als tabellarische Daten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cf161-209">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="cf161-210">Sie können die Daten auch in anderen Formattypen wie Diagrammen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cf161-210">You can also opt to view the data in other format types such as charts.</span></span>

   1. <span data-ttu-id="cf161-211">Sehen Sie sich die Ergebnisse an, und überprüfen Sie, ob Sie die geöffnete E-Mail identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="cf161-211">Look at the results and see if you can identify the email you opened.</span></span> <span data-ttu-id="cf161-212">Es kann bis zu zwei Stunden dauern, bis die Nachricht in der erweiterten Suche angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cf161-212">It may take up to two hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="cf161-213">Um die Ergebnisse einzugrenzen, können Sie der Abfrage die Bedingung hinzufügen, **dass** nur nach E-Mails mit "yahoo.com" als SenderMailFromDomain gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="cf161-213">To narrow down the results, you can add the **where** condition to your query to only look for emails that have "yahoo.com" as their SenderMailFromDomain.</span></span> <span data-ttu-id="cf161-214">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cf161-214">Here is an example.</span></span>

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. <span data-ttu-id="cf161-215">Klicken Sie auf die resultierenden Zeilen aus der Abfrage, damit Sie den Datensatz überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="cf161-215">Click the resulting rows from the query so you can inspect the record.</span></span>

      ![Beispiel für den Seitenbereich "Datensatz untersuchen", der geöffnet wird, wenn ein Erweitertes Suchergebnis ausgewählt wird](../../media/mtp/fig21.png)

4. <span data-ttu-id="cf161-217">Nachdem Sie sich vergewissert haben, dass die E-Mail angezeigt wird, fügen Sie einen Filter für die Anlagen hinzu.</span><span class="sxs-lookup"><span data-stu-id="cf161-217">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="cf161-218">Konzentrieren Sie sich auf alle E-Mails mit Anlagen in der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="cf161-218">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="cf161-219">Konzentrieren Sie sich für diese Simulation auf eingehende E-Mails, nicht auf E-Mails, die aus Ihrer Umgebung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf161-219">For this simulation, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="cf161-220">Entfernen Sie alle Filter, die Sie hinzugefügt haben, um Ihre Nachricht zu suchen und "| wobei **AttachmentCount > 0** und **EmailDirection**  ==  **"Eingehend"**</span><span class="sxs-lookup"><span data-stu-id="cf161-220">Remove any filters you have added to locate your message and add "| where **AttachmentCount > 0** and **EmailDirection** == **"Inbound""**</span></span>

   <span data-ttu-id="cf161-221">In der folgenden Abfrage wird das Ergebnis mit einer kürzeren Liste angezeigt als die ursprüngliche Abfrage für alle E-Mail-Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="cf161-221">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. <span data-ttu-id="cf161-222">Fügen Sie als Nächstes die Informationen zur Anlage (z. B. Dateiname, Hashes) in das Resultset ein.</span><span class="sxs-lookup"><span data-stu-id="cf161-222">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="cf161-223">Fügen Sie dazu der **Tabelle EmailAttachmentInfo** bei.</span><span class="sxs-lookup"><span data-stu-id="cf161-223">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="cf161-224">Die allgemeinen Felder, die für die Verknüpfung verwendet werden sollen, in diesem Fall sind **NetworkMessageId** und **RecipientObjectId**.</span><span class="sxs-lookup"><span data-stu-id="cf161-224">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

   <span data-ttu-id="cf161-225">Die folgende Abfrage enthält auch eine zusätzliche Zeile "| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span><span class="sxs-lookup"><span data-stu-id="cf161-225">The following query also includes an additional line "| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. <span data-ttu-id="cf161-226">Verwenden Sie als Nächstes den **SHA256-Wert** aus der **EmailAttachmentInfo-Tabelle,** um **DeviceFileEvents** (Dateiaktionen, die auf dem Endpunkt aufgetreten sind) für diesen Hash zu suchen.</span><span class="sxs-lookup"><span data-stu-id="cf161-226">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span> <span data-ttu-id="cf161-227">Das allgemeine Feld hier ist der SHA256-Hash für die Anlage.</span><span class="sxs-lookup"><span data-stu-id="cf161-227">The common field here will be the SHA256 hash for the attachment.</span></span>

   <span data-ttu-id="cf161-228">Die resultierende Tabelle enthält nun Details vom Endpunkt (Microsoft Defender für Endpunkt), z. B. den Gerätenamen, welche Aktion ausgeführt wurde (in diesem Fall gefiltert, um nur FileCreated-Ereignisse einzuschließen), und wo die Datei gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="cf161-228">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="cf161-229">Der dem Prozess zugeordnete Kontoname wird ebenfalls eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cf161-229">The account name associated with the process will also be included.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   <span data-ttu-id="cf161-230">Sie haben nun eine Abfrage erstellt, die alle eingehenden E-Mails identifiziert, in denen der Benutzer die Anlage geöffnet oder gespeichert hat.</span><span class="sxs-lookup"><span data-stu-id="cf161-230">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="cf161-231">Sie können diese Abfrage auch verfeinern, um nach bestimmten Absenderdomänen, Dateigrößen, Dateitypen usw. zu filtern.</span><span class="sxs-lookup"><span data-stu-id="cf161-231">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7. <span data-ttu-id="cf161-232">Funktionen sind eine besondere Art von Verknüpfung, mit der Sie mehr TI-Daten zu einer Datei wie Verbreitung, Signaturgeber- und Ausstellerinformationen usw. abrufen können. Um weitere Details zur Datei zu erhalten, verwenden Sie die **FileProfile()-Funktionserweiterung:**</span><span class="sxs-lookup"><span data-stu-id="cf161-232">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc. To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a><span data-ttu-id="cf161-233">Erstellen einer Erkennung</span><span class="sxs-lookup"><span data-stu-id="cf161-233">Create a detection</span></span>

<span data-ttu-id="cf161-234">Nachdem Sie eine Abfrage erstellt haben, die Informationen identifiziert, über die Sie **benachrichtigt werden** möchten, ob sie in der Zukunft auftreten, können Sie eine benutzerdefinierte Erkennung aus der Abfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="cf161-234">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span>

<span data-ttu-id="cf161-235">Benutzerdefinierte Erkennungen führen die Abfrage entsprechend der von Ihnen festgelegten Häufigkeit aus, und die Ergebnisse der Abfragen erstellen Sicherheitswarnungen, basierend auf den betroffenen Ressourcen, die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="cf161-235">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="cf161-236">Diese Warnungen werden mit Vorfällen korreliert und können als jede andere Sicherheitswarnung, die von einem der Produkte generiert wird, triagediert werden.</span><span class="sxs-lookup"><span data-stu-id="cf161-236">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1. <span data-ttu-id="cf161-237">Entfernen Sie auf der Abfrageseite die Zeilen 7 und 8, die in Schritt 7 der Go-Suchanweisungen hinzugefügt wurden, und klicken Sie auf **Erkennungsregel erstellen.**</span><span class="sxs-lookup"><span data-stu-id="cf161-237">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span>

   ![Beispiel dafür, wo Sie auf der Seite "Erweiterte Suche" auf "Erkennungsregel erstellen" klicken können](../../media/mtp/fig22.png)

   > [!NOTE]
   > <span data-ttu-id="cf161-239">Wenn Sie auf **"Erkennungsregel erstellen"** klicken und in Ihrer Abfrage Syntaxfehler vorhanden sind, wird die Erkennungsregel nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cf161-239">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won't be saved.</span></span> <span data-ttu-id="cf161-240">Überprüfen Sie Ihre Abfrage, um sicherzustellen, dass keine Fehler vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cf161-240">Double-check your query to ensure there's no errors.</span></span>

2. <span data-ttu-id="cf161-241">Füllen Sie die erforderlichen Felder mit den Informationen aus, die es dem Sicherheitsteam ermöglichen, die Warnung zu verstehen, warum sie generiert wurde und welche Aktionen sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="cf161-241">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span>

   ![Beispiel für die Seite "Erkennungsregel erstellen", auf der Sie die Warnungsdetails definieren können](../../media/mtp/fig23.png)

   <span data-ttu-id="cf161-243">Stellen Sie sicher, dass Sie die Felder mit Klarheit ausfüllen, um dem nächsten Benutzer eine fundierte Entscheidung über diese Warnung zur Erkennungsregel zu geben.</span><span class="sxs-lookup"><span data-stu-id="cf161-243">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span>

3. <span data-ttu-id="cf161-244">Wählen Sie aus, welche Entitäten in dieser Warnung betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="cf161-244">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="cf161-245">Wählen Sie in diesem Fall **"Gerät** und **Postfach"** aus.</span><span class="sxs-lookup"><span data-stu-id="cf161-245">In this case, select **Device** and **Mailbox**.</span></span>

   ![Beispiel für die Seite "Erkennungsregel erstellen", auf der Sie die Parameter der betroffenen Entitäten auswählen können](../../media/mtp/fig24.png)

4. <span data-ttu-id="cf161-247">Bestimmen Sie, welche Aktionen ausgeführt werden sollen, wenn die Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="cf161-247">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="cf161-248">Führen Sie in diesem Fall eine Antivirenüberprüfung aus, obwohl andere Aktionen ausgeführt werden konnten.</span><span class="sxs-lookup"><span data-stu-id="cf161-248">In this case, run an antivirus scan, though other actions could be taken.</span></span>

   ![Beispiel für die Seite "Erkennungsregel erstellen", auf der Sie eine Antivirenüberprüfung ausführen können, wenn eine Warnung ausgelöst wird, um Bedrohungen zu begegnen](../../media/mtp/fig25.png)

5. <span data-ttu-id="cf161-250">Wählen Sie den Bereich für die Warnungsregel aus.</span><span class="sxs-lookup"><span data-stu-id="cf161-250">Select the scope for the alert rule.</span></span> <span data-ttu-id="cf161-251">Da diese Abfrage Geräte umfasst, sind die Gerätegruppen in dieser benutzerdefinierten Erkennung gemäß dem Kontext von Microsoft Defender für Endpunkt relevant.</span><span class="sxs-lookup"><span data-stu-id="cf161-251">Since this query involves devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="cf161-252">Beim Erstellen einer benutzerdefinierten Erkennung, die keine Geräte als betroffene Entitäten enthält, gilt der Bereich nicht.</span><span class="sxs-lookup"><span data-stu-id="cf161-252">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>

   ![Beispiel für die Seite "Erkennungsregel erstellen", auf der Sie den Bereich für die Warnungsregel festlegen können, verwaltet Ihre Erwartungen an die Ergebnisse, die Angezeigt werden.](../../media/mtp/fig26.png)

   <span data-ttu-id="cf161-254">Bei diesem Pilotprojekt sollten Sie diese Regel auf eine Teilmenge der Testgeräte in Ihrer Produktionsumgebung beschränken.</span><span class="sxs-lookup"><span data-stu-id="cf161-254">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6. <span data-ttu-id="cf161-255">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="cf161-255">Select **Create**.</span></span> <span data-ttu-id="cf161-256">Wählen Sie dann im Navigationsbereich **benutzerdefinierte Erkennungsregeln** aus.</span><span class="sxs-lookup"><span data-stu-id="cf161-256">Then, select **Custom detection rules** from the navigation panel.</span></span>

   ![Beispiel für die Option "Benutzerdefinierte Erkennungsregeln" im Menü](../../media/mtp/fig27a.png)

   ![Beispiel für die Seite "Erkennungsregeln", auf der die Regel- und Ausführungsdetails angezeigt werden](../../media/mtp/fig27b.png)

   <span data-ttu-id="cf161-259">Auf dieser Seite können Sie die Erkennungsregel auswählen, die eine Detailseite öffnet.</span><span class="sxs-lookup"><span data-stu-id="cf161-259">From this page, you can select the detection rule, which will open a details page.</span></span>

   ![Beispiel für die Seite "E-Mail-Anlagen", auf der Sie den Status der Regelausführung, ausgelöste Warnungen und Aktionen, die Erkennung bearbeiten usw.](../../media/mtp/fig28.png)

<!--

### Advanced hunting walk-through exercises

To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities, and create custom detections and remediation actions.

> [!NOTE]
> Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.

|Title|Description|Download MP4|Watch on YouTube|CSL file to use|
|---|---|---|---|---|
|Episode 1: KQL fundamentals|We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender. Learn about available advanced hunting data and basic KQL syntax and operators.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episode 1: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episode 2: Joins|We'll continue learning about data in advanced hunting and how to join tables together. Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episode 2: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episode 3: Summarizing, pivoting, and visualizing data|Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing. In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema. We turn our datasets into charts that can help improve analysis.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episode 3: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episode 4: Let's hunt! Applying KQL to incident tracking|Time to track some attacker activity! In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack. Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episode 4: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

--> 

### <a name="expert-training-on-advanced-hunting"></a><span data-ttu-id="cf161-261">Expertenschulung zur erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="cf161-261">Expert training on advanced hunting</span></span>

<span data-ttu-id="cf161-262">**Das Nachverfolgen des Angreifers** ist eine Webcast-Serie für neue Sicherheitsanalysten und erfahrene Bedrohungsexperten.</span><span class="sxs-lookup"><span data-stu-id="cf161-262">**Tracking the adversary** is a webcast series for new security analysts and seasoned threat hunters.</span></span> <span data-ttu-id="cf161-263">Es führt Sie durch die Grundlagen der erweiterten Suche bis hin zum Erstellen Eigener anspruchsvoller Abfragen.</span><span class="sxs-lookup"><span data-stu-id="cf161-263">It guides you through the basics of advanced hunting all the way to creating your own sophisticated queries.</span></span> 

<span data-ttu-id="cf161-264">Informationen zu den ersten Schritten finden Sie unter ["Expertenschulungen](advanced-hunting-expert-training.md) zur erweiterten Suche".</span><span class="sxs-lookup"><span data-stu-id="cf161-264">See [Get expert training on advanced hunting](advanced-hunting-expert-training.md) to get started.</span></span>

### <a name="navigation-you-may-need"></a><span data-ttu-id="cf161-265">Navigation, die Sie möglicherweise benötigen</span><span class="sxs-lookup"><span data-stu-id="cf161-265">Navigation you may need</span></span>

[<span data-ttu-id="cf161-266">Erstellen der Microsoft 365 Defender-Evaluierungsumgebung</span><span class="sxs-lookup"><span data-stu-id="cf161-266">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
