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
description: Administratoren können lernen, wie Sie Phishingangriffe simulieren und ihre Benutzer mithilfe von Angriffssimulationsschulungen in Microsoft Defender für Office 365 zur Phishing-Verhinderung schulen.
ms.technology: mdo
ms.openlocfilehash: d82e7544e6795e4514cf1949645107c53fc69c61
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878364"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="341f9-103">Simulieren eines Phishingangriffs</span><span class="sxs-lookup"><span data-stu-id="341f9-103">Simulate a phishing attack</span></span>

<span data-ttu-id="341f9-104">**Gilt** [für Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="341f9-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="341f9-105">Mit der Angriffssimulationsschulung in Microsoft Defender für Office 365 können Sie gutartig Cyberangriffssimulationen in Ihrer Organisation ausführen, um Ihre Sicherheitsrichtlinien und -praktiken zu testen, sowie Ihre Mitarbeiter schulen, um ihr Bewusstsein zu erhöhen und ihre Anfälligkeit für Angriffe zu verringern.</span><span class="sxs-lookup"><span data-stu-id="341f9-105">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="341f9-106">Dieser Artikel führt Sie durch die Erstellung eines simulierten Phishingangriffs mithilfe von Angriffssimulationsschulungen.</span><span class="sxs-lookup"><span data-stu-id="341f9-106">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="341f9-107">Informationen zu den ersten Schritten zum Angriffssimulationstraining finden Sie unter ["Erste Schritte mit dem Angriffssimulationstraining".](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="341f9-107">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="341f9-108">Um einen simulierten Phishingangriff zu starten, öffnen Sie das Microsoft 365 Defender-Portal ( <https://security.microsoft.com/> ), wechseln Sie zu **E-Mail &** \> **Angriffssimulationstraining** für die Zusammenarbeit, und wechseln Sie zur Registerkarte **["Simulationen".](https://security.microsoft.com/attacksimulator?viewid=simulations)**</span><span class="sxs-lookup"><span data-stu-id="341f9-108">To launch a simulated phishing attack, open the Microsoft 365 Defender portal (<https://security.microsoft.com/>), go to **Email & collaboration** \> **Attack simulation training**, and switch to the **[Simulations](https://security.microsoft.com/attacksimulator?viewid=simulations)** tab.</span></span>

<span data-ttu-id="341f9-109">Wählen Sie unter **"Simulationen"** die Option **+Simulation starten** aus.</span><span class="sxs-lookup"><span data-stu-id="341f9-109">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Starten einer Simulationsschaltfläche im Microsoft 365 Defender-Portal](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="341f9-111">Zu jedem Zeitpunkt während der Simulationserstellung können Sie speichern und die Konfiguration der Simulation zu einem späteren Zeitpunkt fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="341f9-111">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="341f9-112">Auswählen eines Social Engineering-Verfahrens</span><span class="sxs-lookup"><span data-stu-id="341f9-112">Selecting a social engineering technique</span></span>

<span data-ttu-id="341f9-113">Wählen Sie aus vier verschiedenen Techniken aus, die aus dem [MITRE ATT&CK® Framework](https://attack.mitre.org/techniques/enterprise/)zusammengestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="341f9-113">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="341f9-114">Für unterschiedliche Techniken stehen unterschiedliche Nutzlasten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="341f9-114">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="341f9-115">Die Erfassung von **Anmeldeinformationen** versucht, Anmeldeinformationen zu sammeln, indem Benutzer zu einer bekannten Website mit Eingabefeldern weitergeleitet werden, um einen Benutzernamen und ein Kennwort zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="341f9-115">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="341f9-116">**Eine Antischadsoftwareanlage** fügt einer Nachricht eine schädliche Anlage hinzu.</span><span class="sxs-lookup"><span data-stu-id="341f9-116">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="341f9-117">Wenn der Benutzer die Anlage öffnet, wird beliebiger Code ausgeführt, der dem Angreifer hilft, das Zielgerät zu kompromittieren.</span><span class="sxs-lookup"><span data-stu-id="341f9-117">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="341f9-118">**Der Link in der Anlage** ist eine Art von Hybridlösung für die Nutzung von Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="341f9-118">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="341f9-119">Ein Angreifer fügt eine URL in eine E-Mail-Anlage ein.</span><span class="sxs-lookup"><span data-stu-id="341f9-119">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="341f9-120">Die URL in der Anlage folgt derselben Technik wie die Anmeldeinformationsernte.</span><span class="sxs-lookup"><span data-stu-id="341f9-120">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="341f9-121">**Links zu Schadsoftware** führen beliebigen Code aus einer Datei aus, die in einem bekannten Dateifreigabedienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="341f9-121">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="341f9-122">Die an den Benutzer gesendete Nachricht enthält einen Link zu dieser schädlichen Datei.</span><span class="sxs-lookup"><span data-stu-id="341f9-122">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="341f9-123">Öffnen Sie die Datei, und helfen Sie dem Angreifer, das Zielgerät zu kompromittiv zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="341f9-123">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="341f9-124">**Drive-by-URL** ist der Ort, an dem die schädliche URL in der Nachricht den Benutzer zu einer vertraut aussehenden Website führt, die automatisch Code auf dem Gerät des Benutzers ausführt und/oder installiert.</span><span class="sxs-lookup"><span data-stu-id="341f9-124">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="341f9-125">Wenn Sie in der Beschreibung der einzelnen Techniken auf **"Details anzeigen"** klicken, werden weitere Informationen und die Simulationsschritte für die Technik angezeigt.</span><span class="sxs-lookup"><span data-stu-id="341f9-125">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Simulationsschritte zum Sammeln von Anmeldeinformationen innerhalb des Angriffssimulationstrainings im Microsoft 365 Defender-Portal](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="341f9-127">Nachdem Sie die Technik ausgewählt und auf **"Weiter"** geklickt haben, geben Sie Ihrer Simulation einen Namen und optional eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="341f9-127">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="341f9-128">Auswählen einer Nutzlast</span><span class="sxs-lookup"><span data-stu-id="341f9-128">Selecting a payload</span></span>

<span data-ttu-id="341f9-129">Als Nächstes müssen Sie entweder eine Nutzlast aus dem bereits vorhandenen Nutzlastkatalog auswählen.</span><span class="sxs-lookup"><span data-stu-id="341f9-129">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="341f9-130">Nutzlasten haben eine Reihe von Datenpunkten, die Ihnen bei der Auswahl helfen:</span><span class="sxs-lookup"><span data-stu-id="341f9-130">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="341f9-131">**Die Klickrate** zählt, wie viele Personen auf diese Nutzlast geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="341f9-131">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="341f9-132">**Die prognostizierte Kompromittierungsrate** prognostiziert den Prozentsatz der Personen, die durch diese Nutzlast kompromittiert werden, basierend auf verlaufsbasierten Daten für die Nutzlast in Microsoft Defender für Office 365 Kunden.</span><span class="sxs-lookup"><span data-stu-id="341f9-132">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="341f9-133">**Gestartete Simulationen** zählen, wie oft diese Nutzlast in anderen Simulationen verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="341f9-133">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="341f9-134">**Die Komplexität,** die über **Filter** verfügbar ist, wird basierend auf der Anzahl der Indikatoren innerhalb der Nutzlast berechnet, die darauf hinweisen, dass es sich um einen Angriff handelt.</span><span class="sxs-lookup"><span data-stu-id="341f9-134">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="341f9-135">Mehr Indikatoren führen zu einer geringeren Komplexität.</span><span class="sxs-lookup"><span data-stu-id="341f9-135">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="341f9-136">**Quelle,** die über **Filter** verfügbar ist, gibt an, ob die Nutzlast auf Ihrem Mandanten erstellt wurde oder Teil des bereits vorhandenen Nutzlastkatalogs (global) von Microsoft ist.</span><span class="sxs-lookup"><span data-stu-id="341f9-136">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Ausgewählte Nutzlast im Angriffssimulationstraining im Microsoft 365 Defender-Portal](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="341f9-138">Wählen Sie eine Nutzlast aus der Liste aus, um eine Vorschau der Nutzlast mit zusätzlichen Informationen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="341f9-138">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="341f9-139">Wenn Sie Ihre eigene Nutzlast erstellen möchten, lesen Sie ["Erstellen einer Nutzlast für Angriffssimulationsschulungen".](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="341f9-139">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="341f9-140">Zielgruppenadressierung</span><span class="sxs-lookup"><span data-stu-id="341f9-140">Audience targeting</span></span>

<span data-ttu-id="341f9-141">Jetzt ist es an der Zeit, die Zielgruppe dieser Simulation auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="341f9-141">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="341f9-142">Sie können **alle Benutzer in Ihrer Organisation oder** nur bestimmte Benutzer und Gruppen **einschließen.**</span><span class="sxs-lookup"><span data-stu-id="341f9-142">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="341f9-143">Wenn Sie sich dafür entscheiden, **nur bestimmte Benutzer und Gruppen einzuschließen,** können Sie die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="341f9-143">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="341f9-144">**Fügen Sie Benutzer hinzu,** mit denen Sie die Suche nach Ihrem Mandanten sowie erweiterte Such- und Filterfunktionen nutzen können, z. B. für Benutzer, die in den letzten 3 Monaten nicht für eine Simulation vorgesehen waren.</span><span class="sxs-lookup"><span data-stu-id="341f9-144">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>

  ![Benutzerfilterung in Angriffssimulationsschulungen im Microsoft 365 Defender-Portal](../../media/attack-sim-preview-user-targeting.png)

- <span data-ttu-id="341f9-146">**Mit dem Import aus CSV** können Sie eine vordefinierte Gruppe von Benutzern für diese Simulation importieren.</span><span class="sxs-lookup"><span data-stu-id="341f9-146">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="341f9-147">Zuweisen von Schulungen</span><span class="sxs-lookup"><span data-stu-id="341f9-147">Assigning training</span></span>

<span data-ttu-id="341f9-148">Es wird empfohlen, für jede Simulation Schulungen zuzuweisen, da Mitarbeiter, die eine Schulung durchlaufen, weniger anfällig für ähnliche Angriffe sind.</span><span class="sxs-lookup"><span data-stu-id="341f9-148">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="341f9-149">Sie können entweder auswählen, ob Ihnen Schulungen zugewiesen wurden, oder selbst Schulungskurse und Module auswählen.</span><span class="sxs-lookup"><span data-stu-id="341f9-149">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="341f9-150">Wählen Sie das **Fälligkeitsdatum** der Schulung aus, um sicherzustellen, dass die Mitarbeiter ihre Schulung zeitnah abschließen.</span><span class="sxs-lookup"><span data-stu-id="341f9-150">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="341f9-151">Wenn Sie selbst Kurse und Module auswählen möchten, können Sie weiterhin die empfohlenen Inhalte sowie alle verfügbaren Kurse und Module anzeigen.</span><span class="sxs-lookup"><span data-stu-id="341f9-151">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Hinzufügen empfohlener Schulungen innerhalb der Angriffssimulationsschulung im Microsoft 365 Defender-Portal](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="341f9-153">In den nächsten Schritten müssen Sie **Schulungen hinzufügen,** wenn Sie sich dafür entschieden haben, sie selbst auszuwählen, und Ihre Schulungszielseite anpassen.</span><span class="sxs-lookup"><span data-stu-id="341f9-153">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="341f9-154">Sie können eine Vorschau der Schulungszielseite anzeigen und die Kopfzeile und den Textkörper ändern.</span><span class="sxs-lookup"><span data-stu-id="341f9-154">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="341f9-155">Details zum Starten und Überprüfen</span><span class="sxs-lookup"><span data-stu-id="341f9-155">Launch details and review</span></span>

<span data-ttu-id="341f9-156">Nachdem alles konfiguriert ist, können Sie diese Simulation sofort starten oder für einen späteren Zeitpunkt planen.</span><span class="sxs-lookup"><span data-stu-id="341f9-156">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="341f9-157">Sie müssen auch auswählen, wann diese Simulation beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="341f9-157">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="341f9-158">Wir werden die Aufzeichnung der Interaktion mit dieser Simulation nach der ausgewählten Zeit beenden.</span><span class="sxs-lookup"><span data-stu-id="341f9-158">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="341f9-159">Aktivieren Sie die **Region unterstützende Zeitzonenzustellung,** um simulierte Angriffsmeldungen an Ihre Mitarbeiter während ihrer Arbeitszeiten basierend auf ihrer Region zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="341f9-159">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="341f9-160">Wenn Sie fertig sind, klicken Sie auf **"Weiter",** und überprüfen Sie die Details Ihrer Simulation.</span><span class="sxs-lookup"><span data-stu-id="341f9-160">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="341f9-161">Klicken Sie auf **"Bearbeiten"** auf einen der Teile, um zurückzugehen und alle Details zu ändern, die geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="341f9-161">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="341f9-162">Nachdem Sie fertig sind, klicken Sie auf **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="341f9-162">Once done, click **Submit**.</span></span>
