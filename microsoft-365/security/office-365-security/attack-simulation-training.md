---
title: Simulieren eines Phishingangriffs mit Microsoft Defender für Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können lernen, wie Sie Phishingangriffe simulieren und ihre Benutzer mithilfe von Angriffssimulationsschulungen in Microsoft Defender für Office 365 zur Phishingverhütung schulen.
ms.openlocfilehash: dfdd3c93afb1b0fb30cc5b5affc040a369c29447
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870967"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="6ebc0-103">Simulieren eines Phishingangriffs</span><span class="sxs-lookup"><span data-stu-id="6ebc0-103">Simulate a phishing attack</span></span>

<span data-ttu-id="6ebc0-104">Mit dem Training zur Angriffssimulation in Microsoft Defender für Office 365 können Sie gutartige Cyberangriffssimulationen in Ihrer Organisation ausführen, um Ihre Sicherheitsrichtlinien und -praktiken zu testen und Ihre Mitarbeiter zu schulen, um ihr Bewusstsein zu erhöhen und ihre Anfälligkeit für Angriffe zu verringern.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="6ebc0-105">Dieser Artikel führt Sie durch die Erstellung eines simulierten Phishingangriffs mithilfe von Angriffssimulationsschulungen.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="6ebc0-106">Informationen zu den ersten Schritte zum Training zur Angriffssimulation finden Sie unter ["Erste Schritte mit dem Attack Simulation Training".](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="6ebc0-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="6ebc0-107">Um einen simulierten Phishingangriff zu starten, öffnen Sie das [Microsoft 365 Security Center,](https://security.microsoft.com/)wechseln Sie zu **"E-Mail &** Collaboration Attack Simulation Training", und wechseln Sie zur Registerkarte \>  [**"Simulationen".**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="6ebc0-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="6ebc0-108">Wählen **Sie unter Simulationen** die Option **+ Starten einer Simulation aus.**</span><span class="sxs-lookup"><span data-stu-id="6ebc0-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Starten einer Simulationsschaltfläche im Microsoft 365 Security Center](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="6ebc0-110">Zu jedem Zeitpunkt während der Simulationserstellung können Sie speichern und sich nähern, um die Konfiguration der Simulation zu einem späteren Zeitpunkt fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="6ebc0-111">Auswählen einer Social -Engineering-Technik</span><span class="sxs-lookup"><span data-stu-id="6ebc0-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="6ebc0-112">Wählen Sie aus vier verschiedenen Techniken aus, die aus dem [MITRE ATT&CK® werden.](https://attack.mitre.org/techniques/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="6ebc0-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="6ebc0-113">Für unterschiedliche Techniken stehen unterschiedliche Nutzlasten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="6ebc0-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="6ebc0-114">**Die Erfassung von** Anmeldeinformationen versucht, Anmeldeinformationen zu sammeln, indem Benutzer zu einer bekannten Website mit Eingabefeldern zum Übermitteln eines Benutzernamens und Kennworts aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="6ebc0-115">**Eine Anlage mit** Schadsoftware fügt einer Nachricht eine bösartige Anlage hinzu.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="6ebc0-116">Wenn der Benutzer die Anlage öffnet, wird beliebiger Code ausgeführt, der dem Angreifer dabei hilft, das Gerät des Ziels zu greife.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="6ebc0-117">**Der Link in der Anlage** ist ein Hybridtyp für die Anmeldeinformationsernte.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="6ebc0-118">Ein Angreifer fügt eine URL in eine E-Mail-Anlage ein.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="6ebc0-119">Die URL in der Anlage folgt demselben Verfahren wie die Anmeldeinformationsernte.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="6ebc0-120">**Bei einem Link zu Schadsoftware** wird beliebiger Code aus einer Datei ausgeführt, die auf einem bekannten Dateifreigabedienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="6ebc0-121">Die an den Benutzer gesendete Nachricht enthält einen Link zu dieser schädlichen Datei.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="6ebc0-122">Öffnen sie die Datei, und helfen Sie dem Angreifer, das Gerät des Ziels zu greife.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-122">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="6ebc0-123">Wenn Sie in **der Beschreibung der** einzelnen Techniken auf Details anzeigen klicken, werden weitere Informationen und die Simulationsschritte für die Technik angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-123">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Simulationsschritte für die Verwendung von Anmeldeinformationen im Rahmen des Angriffssimulationstrainings im Microsoft 365 Security Center](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="6ebc0-125">Nachdem Sie das Verfahren ausgewählt und auf **"Weiter"** geklickt haben, geben Sie ihrer Simulation einen Namen und optional eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-125">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="6ebc0-126">Auswählen einer Nutzlast</span><span class="sxs-lookup"><span data-stu-id="6ebc0-126">Selecting a payload</span></span>

<span data-ttu-id="6ebc0-127">Als Nächstes müssen Sie entweder eine Nutzlast aus dem bereits vorhandenen Nutzlastkatalog auswählen.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-127">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="6ebc0-128">Nutzlasten verfügen über eine Reihe von Datenpunkten, die Ihnen bei der Auswahl helfen:</span><span class="sxs-lookup"><span data-stu-id="6ebc0-128">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="6ebc0-129">**Die Klickrate** zählt, wie viele Personen auf diese Nutzlast geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-129">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="6ebc0-130">**Die vorhergesagte Kompromissrate** prognostizieren den Prozentsatz der Personen, die von dieser Nutzlast basierend auf historischen Daten für die Nutzlast von Microsoft Defender für Office 365-Kunden gefährdet werden.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-130">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="6ebc0-131">**Bei gestarteten Simulationen** wird ermittelt, wie oft diese Nutzlast in anderen Simulationen verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-131">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="6ebc0-132">**Die** Komplexität , die über **Filter** verfügbar ist, wird basierend auf der Anzahl der Indikatoren innerhalb der Nutzlast berechnet, die darauf hinweisen, dass es sich um einen Angriff handelt.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-132">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="6ebc0-133">Mehr Indikatoren führen zu einer geringeren Komplexität.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-133">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="6ebc0-134">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span><span class="sxs-lookup"><span data-stu-id="6ebc0-134">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Ausgewählte Nutzlast im Training zur Angriffssimulation im Microsoft 365 Security Center](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="6ebc0-136">Wählen Sie eine Nutzlast aus der Liste aus, um eine Vorschau der Nutzlast mit zusätzlichen Informationen dazu anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-136">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="6ebc0-137">Wenn Sie Ihre eigene Nutzlast erstellen möchten, lesen Sie die Informationen zum Erstellen einer Nutzlast [für das Training zur Angriffssimulation.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="6ebc0-137">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="6ebc0-138">Zielgruppenadressierung</span><span class="sxs-lookup"><span data-stu-id="6ebc0-138">Audience targeting</span></span>

<span data-ttu-id="6ebc0-139">Jetzt ist es an der Zeit, die Zielgruppe dieser Simulation auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-139">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="6ebc0-140">Sie können festlegen, **dass alle Benutzer in Ihrer** Organisation oder nur bestimmte Benutzer und Gruppen enthalten **sind.**</span><span class="sxs-lookup"><span data-stu-id="6ebc0-140">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="6ebc0-141">Wenn Sie festlegen, **dass nur bestimmte Benutzer und Gruppen enthalten sind,** haben Sie folgende Möglichkeit:</span><span class="sxs-lookup"><span data-stu-id="6ebc0-141">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="6ebc0-142">**Fügen Sie** Benutzer hinzu, mit denen Sie die Suche nach Ihrem Mandanten sowie erweiterte Such- und Filterfunktionen nutzen können, z. B. für Benutzer, die in den letzten drei Monaten nicht zielgerichtet auf eine Simulation ausgerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-142">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="6ebc0-143">![Benutzerfilterung in Angriffssimulationsschulungen im Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="6ebc0-143">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="6ebc0-144">**Mit dem Import** aus csv können Sie eine vordefinierte Gruppe von Benutzern für diese Simulation importieren.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-144">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="6ebc0-145">Zuweisen von Schulungen</span><span class="sxs-lookup"><span data-stu-id="6ebc0-145">Assigning training</span></span>

<span data-ttu-id="6ebc0-146">Es wird empfohlen, dass Sie für jede Simulation Schulungen zuweisen, da Mitarbeiter, die Schulungen durchgehen, weniger anfällig für ähnliche Angriffe sind.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-146">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="6ebc0-147">Sie können entweder eine Schulung für Sie zugewiesen haben oder selbst Schulungskurse und Module auswählen.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-147">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="6ebc0-148">Wählen Sie das **Fälligkeitsdatum der** Schulung aus, um sicherzustellen, dass die Mitarbeiter ihre Schulung rechtzeitig beenden.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-148">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="6ebc0-149">Wenn Sie kurse und Module selbst auswählen, können Sie weiterhin die empfohlenen Inhalte sowie alle verfügbaren Kurse und Module anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-149">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Hinzufügen empfohlener Schulungen zur Angriffssimulation im Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="6ebc0-151">In den nächsten Schritten müssen  Sie Schulungen hinzufügen, wenn Sie sich dafür entschieden haben, sie selbst auszuwählen, und Ihre Angebotsseite für Schulungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-151">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="6ebc0-152">Sie können eine Vorschau der Angebotsseite für Schulungen anzeigen und den Header und textkörper ändern.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-152">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="6ebc0-153">Startdetails und Überprüfung</span><span class="sxs-lookup"><span data-stu-id="6ebc0-153">Launch details and review</span></span>

<span data-ttu-id="6ebc0-154">Nachdem nun alles konfiguriert ist, können Sie diese Simulation sofort starten oder für einen späteren Termin planen.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-154">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="6ebc0-155">Sie müssen auch auswählen, wann diese Simulation beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-155">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="6ebc0-156">Wir beenden die Erfassung von Interaktionen mit dieser Simulation nach dem ausgewählten Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-156">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="6ebc0-157">**Aktivieren Sie die Regionen-bezogene Zeitzonenzustellung,** um ihren Mitarbeitern während der Arbeitszeiten basierend auf ihrer Region simulierte Angriffsnachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-157">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="6ebc0-158">Wenn Sie fertig sind, klicken Sie auf **"Weiter",** und überprüfen Sie die Details ihrer Simulation.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-158">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="6ebc0-159">Klicken Sie **auf "Bearbeiten"** auf einen der Teile, um zurück zu gehen und alle Details zu ändern, die geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6ebc0-159">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="6ebc0-160">Klicken Sie anschließend auf **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="6ebc0-160">Once done, click **Submit**.</span></span>
