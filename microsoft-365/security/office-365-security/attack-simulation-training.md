---
title: Simulieren eines Phishingangriffs mit Microsoft Defender für Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können lernen, wie Sie Phishingangriffe simulieren und ihre Benutzer mithilfe von Attack simulation training in Microsoft Defender for Office 365.
ms.technology: mdo
ms.openlocfilehash: 27279f927a15ea94ae84112ffdc23d88ea42d2ff
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206224"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="8771e-103">Simulieren eines Phishingangriffs</span><span class="sxs-lookup"><span data-stu-id="8771e-103">Simulate a phishing attack</span></span>

<span data-ttu-id="8771e-104">Mit Dem Training zur Angriffssimulation in Microsoft Defender for Office 365 können Sie in Ihrer Organisation gutartige Cyberangriffssimulationen ausführen, um Ihre Sicherheitsrichtlinien und -methoden zu testen und Ihre Mitarbeiter zu schulen, um ihr Bewusstsein zu erhöhen und ihre Anfälligkeit für Angriffe zu verringern.</span><span class="sxs-lookup"><span data-stu-id="8771e-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="8771e-105">In diesem Artikel werden Sie durch das Erstellen eines simulierten Phishingangriffs mithilfe von Training zur Angriffssimulation erläutert.</span><span class="sxs-lookup"><span data-stu-id="8771e-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="8771e-106">Informationen zu den ersten Informationen zum Training zur Angriffssimulation finden Sie unter [Erste Schritte mit attack simulation training](attack-simulation-training-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="8771e-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="8771e-107">Öffnen Sie zum Starten eines simulierten Phishingangriffs das [Microsoft 365 Security Center,](https://security.microsoft.com/)wechseln Sie zu **E-Mail & Zusammenarbeit** Attack simulation training, und wechseln Sie zur Registerkarte \>  [**Simulationen.**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="8771e-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="8771e-108">Wählen **Sie unter Simulationen** **die Option + Simulation starten aus.**</span><span class="sxs-lookup"><span data-stu-id="8771e-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Starten einer Simulationsschaltfläche im Microsoft 365 Security Center](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="8771e-110">Sie können die Simulation jederzeit während der Simulationserstellung speichern und schließen, um die Konfiguration der Simulation zu einem späteren Zeitpunkt fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="8771e-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="8771e-111">Auswählen einer Social Engineering-Technik</span><span class="sxs-lookup"><span data-stu-id="8771e-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="8771e-112">Wählen Sie aus vier verschiedenen Techniken aus, die aus dem [MITRE ATT&CK® werden.](https://attack.mitre.org/techniques/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="8771e-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="8771e-113">Unterschiedliche Nutzlasten stehen für verschiedene Techniken zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="8771e-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="8771e-114">**Die Erfassung von** Anmeldeinformationen versucht, Anmeldeinformationen zu sammeln, indem Benutzer zu einer bekannten, aussehenden Website mit Eingabefeldern zum Übermitteln eines Benutzernamens und Kennworts aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="8771e-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="8771e-115">**Eine** Schadsoftwareanlage fügt einer Nachricht eine bösartige Anlage hinzu.</span><span class="sxs-lookup"><span data-stu-id="8771e-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="8771e-116">Wenn der Benutzer die Anlage öffnet, wird beliebiger Code ausgeführt, mit dem der Angreifer das Gerät des Ziels gefährdet.</span><span class="sxs-lookup"><span data-stu-id="8771e-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="8771e-117">**Link in attachment ist** eine Art hybrider Anmeldeinformationsernte.</span><span class="sxs-lookup"><span data-stu-id="8771e-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="8771e-118">Ein Angreifer fügt eine URL in eine E-Mail-Anlage ein.</span><span class="sxs-lookup"><span data-stu-id="8771e-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="8771e-119">Die URL in der Anlage folgt der gleichen Technik wie die Lese von Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="8771e-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="8771e-120">**Bei einem Link zu Schadsoftware** wird beliebiger Code aus einer Datei ausgeführt, die in einem bekannten Dateifreigabedienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="8771e-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="8771e-121">Die an den Benutzer gesendete Nachricht enthält einen Link zu dieser schädlichen Datei.</span><span class="sxs-lookup"><span data-stu-id="8771e-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="8771e-122">Öffnen Sie die Datei, und helfen Sie dem Angreifer, das Gerät des Ziels zu gefährdet.</span><span class="sxs-lookup"><span data-stu-id="8771e-122">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="8771e-123">**Die Drive-by-URL** führt den Benutzer mit der bösartigen URL in der Nachricht zu einer vertraut aussehenden Website, die im Hintergrund ausgeführt und/oder Codecode auf dem Gerät des Benutzers installiert.</span><span class="sxs-lookup"><span data-stu-id="8771e-123">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="8771e-124">Wenn Sie in **der Beschreibung der** einzelnen Techniken auf Details anzeigen klicken, werden weitere Informationen sowie die Simulationsschritte für die Technik angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8771e-124">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Simulationsschritte für die Auslese von Anmeldeinformationen innerhalb von Angriffssimulationsschulungen in Microsoft 365 Security Center](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="8771e-126">Nachdem Sie die Technik ausgewählt und auf **Weiter** geklickt haben, geben Sie Ihrer Simulation einen Namen und optional eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="8771e-126">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="8771e-127">Auswählen einer Nutzlast</span><span class="sxs-lookup"><span data-stu-id="8771e-127">Selecting a payload</span></span>

<span data-ttu-id="8771e-128">Als Nächstes müssen Sie entweder eine Nutzlast aus dem bereits vorhandenen Nutzlastkatalog auswählen.</span><span class="sxs-lookup"><span data-stu-id="8771e-128">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="8771e-129">Nutzlasten verfügen über eine Reihe von Datenpunkten, die Ihnen bei der Auswahl helfen:</span><span class="sxs-lookup"><span data-stu-id="8771e-129">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="8771e-130">**Die Klickrate** zählt, wie viele Personen auf diese Nutzlast geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="8771e-130">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="8771e-131">**Die vorhergesagte** Kompromissrate prognostizieren den Prozentsatz der Personen, die von dieser Nutzlast basierend auf historischen Daten für die Nutzlast in Microsoft Defender für Office 365 werden.</span><span class="sxs-lookup"><span data-stu-id="8771e-131">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="8771e-132">**Gestartete Simulationen** zählen, wie oft diese Nutzlast in anderen Simulationen verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8771e-132">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="8771e-133">**Die** Komplexität , die über **Filter** verfügbar ist, wird basierend auf der Anzahl der Indikatoren innerhalb der Nutzlast berechnet, in der der Hinweis darauf zielt, dass es sich um einen Angriff handelt.</span><span class="sxs-lookup"><span data-stu-id="8771e-133">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="8771e-134">Weitere Indikatoren führen zu einer geringeren Komplexität.</span><span class="sxs-lookup"><span data-stu-id="8771e-134">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="8771e-135">**Source**, die über **Filter** verfügbar ist, gibt an, ob die Nutzlast in Ihrem Mandanten erstellt wurde oder Teil des bereits vorhandenen Nutzlastkatalogs von Microsoft (global) ist.</span><span class="sxs-lookup"><span data-stu-id="8771e-135">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Ausgewählte Nutzlast im Training zur Angriffssimulation in Microsoft 365 Security Center](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="8771e-137">Wählen Sie eine Nutzlast aus der Liste aus, um eine Vorschau der Nutzlast mit zusätzlichen Informationen dazu anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8771e-137">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="8771e-138">Wenn Sie Eine eigene Nutzlast erstellen möchten, lesen Sie [Create a payload for attack simulation training](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="8771e-138">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="8771e-139">Zielgruppenadressierung</span><span class="sxs-lookup"><span data-stu-id="8771e-139">Audience targeting</span></span>

<span data-ttu-id="8771e-140">Jetzt ist es an der Zeit, die Zielgruppe dieser Simulation auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="8771e-140">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="8771e-141">Sie können festlegen, **dass alle Benutzer in Ihrer** Organisation oder nur bestimmte Benutzer und Gruppen enthalten **sind.**</span><span class="sxs-lookup"><span data-stu-id="8771e-141">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="8771e-142">Wenn Sie nur bestimmte Benutzer und Gruppen enthalten **möchten,** können Sie folgendes:</span><span class="sxs-lookup"><span data-stu-id="8771e-142">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="8771e-143">**Fügen Sie Benutzer** hinzu, mit denen Sie die Suche nach Ihrem Mandanten sowie erweiterte Such- und Filterfunktionen nutzen können, z. B. für Benutzer, die in den letzten 3 Monaten nicht auf eine Simulation ausgerichtet waren.</span><span class="sxs-lookup"><span data-stu-id="8771e-143">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="8771e-144">![Benutzerfilterung in Angriffssimulationsschulungen Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="8771e-144">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="8771e-145">**Mit dem Import** aus csv können Sie eine vordefinierte Gruppe von Benutzern für diese Simulation importieren.</span><span class="sxs-lookup"><span data-stu-id="8771e-145">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="8771e-146">Zuweisen von Schulungen</span><span class="sxs-lookup"><span data-stu-id="8771e-146">Assigning training</span></span>

<span data-ttu-id="8771e-147">Es wird empfohlen, für jede Simulation Schulungen zuzuordnen, da Mitarbeiter, die eine Schulung durchgehen, weniger anfällig für ähnliche Angriffe sind.</span><span class="sxs-lookup"><span data-stu-id="8771e-147">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="8771e-148">Sie können entweder festlegen, dass Ihnen Schulungen zugewiesen werden, oder Sie können selbst Schulungskurse und Module auswählen.</span><span class="sxs-lookup"><span data-stu-id="8771e-148">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="8771e-149">Wählen Sie **das Fälligkeitsdatum der** Schulung aus, um sicherzustellen, dass die Mitarbeiter ihre Schulung zeitnah beenden.</span><span class="sxs-lookup"><span data-stu-id="8771e-149">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="8771e-150">Wenn Sie Kurse und Module selbst auswählen, können Sie weiterhin die empfohlenen Inhalte sowie alle verfügbaren Kurse und Module anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8771e-150">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Hinzufügen empfohlener Schulungen in Angriffssimulationsschulungen in Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="8771e-152">In den nächsten Schritten müssen  Sie Schulungen hinzufügen, wenn Sie sich dafür entschieden haben, sie selbst auszuwählen, und Ihre Schulungslandeseite anpassen.</span><span class="sxs-lookup"><span data-stu-id="8771e-152">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="8771e-153">Sie können eine Vorschau der Schulungslandeseite anzeigen und die Kopfzeile und den Textkörper ändern.</span><span class="sxs-lookup"><span data-stu-id="8771e-153">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="8771e-154">Starten von Details und Überprüfen</span><span class="sxs-lookup"><span data-stu-id="8771e-154">Launch details and review</span></span>

<span data-ttu-id="8771e-155">Nachdem nun alles konfiguriert ist, können Sie diese Simulation sofort starten oder für einen späteren Zeitpunkt planen.</span><span class="sxs-lookup"><span data-stu-id="8771e-155">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="8771e-156">Sie müssen auch auswählen, wann diese Simulation beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8771e-156">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="8771e-157">Wir beenden die Erfassung der Interaktion mit dieser Simulation nach dem ausgewählten Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="8771e-157">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="8771e-158">**Aktivieren Sie die Bereitstellung von regionenbezogenen** Zeitzonen, um simulierte Angriffsnachrichten an Ihre Mitarbeiter während ihrer Arbeitszeit basierend auf ihrer Region zu senden.</span><span class="sxs-lookup"><span data-stu-id="8771e-158">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="8771e-159">Nachdem Sie fertig sind, klicken Sie auf **Weiter,** und überprüfen Sie die Details Ihrer Simulation.</span><span class="sxs-lookup"><span data-stu-id="8771e-159">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="8771e-160">Klicken Sie **auf Bearbeiten** für einen der Teile, um zurück zu wechseln und alle Details zu ändern, die geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8771e-160">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="8771e-161">Klicken Sie nach getaner Arbeit auf **Absenden**.</span><span class="sxs-lookup"><span data-stu-id="8771e-161">Once done, click **Submit**.</span></span>
