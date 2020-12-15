---
title: Simulieren eines Phishing-Angriffs mit Microsoft Defender für Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Administratoren können erfahren, wie Sie Phishing-Angriffe simulieren und Ihre Benutzer auf Phishing-Verhinderung mithilfe von Angriffs Simulations Schulungen in Microsoft Defender für Office 365 Schulen.
ms.openlocfilehash: 3707041067fd76ee9535d0dccf5cdfcb9d74fbd7
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667555"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="25925-103">Simulieren eines Phishing-Angriffs</span><span class="sxs-lookup"><span data-stu-id="25925-103">Simulate a phishing attack</span></span>

<span data-ttu-id="25925-104">Angriffs Simulator-Schulung in Microsoft Defender für Office 365 können Sie gutartige Cyberangriff-Simulationen in Ihrer Organisation ausführen, um Ihre Sicherheitsrichtlinien und-Methoden zu testen und Ihre Mitarbeiter auszubilden, um Ihr Bewusstsein zu schärfen und ihre Anfälligkeit für Angriffe zu verringern.</span><span class="sxs-lookup"><span data-stu-id="25925-104">Attack simulator training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="25925-105">Dieser Artikel führt Sie durch das Erstellen eines simulierten Phishing-Angriffs mithilfe von Attack Simulator Training.</span><span class="sxs-lookup"><span data-stu-id="25925-105">This article walks you through creating  a simulated phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="25925-106">Um einen simulierten Phishing-Angriff zu starten, öffnen Sie das [Microsoft 365 Security Center](https://security.microsoft.com/), wechseln Sie zu **e-Mail & Zusammenarbeits-** \> **Angriffs Simulator**, und wechseln Sie zur Registerkarte [**Simulationen**](https://security.microsoft.com/attacksimulator?viewid=simulations) .</span><span class="sxs-lookup"><span data-stu-id="25925-106">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulator**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="25925-107">Wählen Sie unter **Simulationen** **die Option + Simulation starten** aus.</span><span class="sxs-lookup"><span data-stu-id="25925-107">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Starten einer Schaltfläche "Simulation" im Microsoft 365 Security Center](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="25925-109">Sie können während der Simulationserstellung jederzeit speichern und schließen, um die Konfiguration der Simulation zu einem späteren Zeitpunkt fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="25925-109">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="25925-110">Auswählen einer Social Engineering-Technik</span><span class="sxs-lookup"><span data-stu-id="25925-110">Selecting a social engineering technique</span></span>

<span data-ttu-id="25925-111">Wählen Sie aus vier verschiedenen Techniken aus, die von der [Mitra ATT&ck® Framework](https://attack.mitre.org/techniques/enterprise/)kuratiert wurden.</span><span class="sxs-lookup"><span data-stu-id="25925-111">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="25925-112">Für verschiedene Techniken stehen unterschiedliche Nutzlasten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="25925-112">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="25925-113">Die Erfassung von **Anmelde** Informationen versucht, Anmeldeinformationen zu sammeln, indem Benutzer zu einer bekannten Website mit Eingabefeldern übertragen werden, um einen Benutzernamen und ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="25925-113">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="25925-114">**Schadsoftware** fügt eine böswillige Anlage zu einer Nachricht hinzu.</span><span class="sxs-lookup"><span data-stu-id="25925-114">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="25925-115">Wenn der Benutzer die Anlage öffnet, wird willkürlicher Code ausgeführt, mit dem der Angreifer das Gerät des Ziels kompromittieren kann.</span><span class="sxs-lookup"><span data-stu-id="25925-115">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="25925-116">**Link in Attachment** ist eine Art der Hybriden Anmeldeinformationen-Ernte.</span><span class="sxs-lookup"><span data-stu-id="25925-116">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="25925-117">Ein Angreifer fügt eine URL in eine e-Mail-Anlage ein.</span><span class="sxs-lookup"><span data-stu-id="25925-117">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="25925-118">Die URL innerhalb der Anlage folgt dem gleichen Verfahren wie das Sammeln von Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="25925-118">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="25925-119">**Mit Link zu Schadsoftware** wird ein beliebiger Code aus einer Datei ausgeführt, die auf einem bekannten Dateifreigabedienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="25925-119">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="25925-120">Die Nachricht, die an den Benutzer gesendet wird, enthält einen Link zu dieser schädlichen Datei.</span><span class="sxs-lookup"><span data-stu-id="25925-120">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="25925-121">Öffnen der Datei und unterstützen des Angreifers, das Gerät des Ziels zu gefährden.</span><span class="sxs-lookup"><span data-stu-id="25925-121">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="25925-122">Durch Klicken auf **Details anzeigen** in der Beschreibung jeder Technik werden weitere Informationen und die Simulationsschritte für die Technik angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25925-122">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Simulationsschritte für das Sammeln von Anmeldeinformationen im Angriffs Simulationstraining im Microsoft 365 Security Center](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="25925-124">Nachdem Sie die Technik ausgewählt und auf **weiter** geklickt haben, geben Sie Ihrer Simulation einen Namen und optional eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="25925-124">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="25925-125">Auswählen einer Nutzlast</span><span class="sxs-lookup"><span data-stu-id="25925-125">Selecting a payload</span></span>

<span data-ttu-id="25925-126">Als nächstes müssen Sie entweder eine Nutzlast aus dem bereits vorhandenen Nutz Last Katalog auswählen.</span><span class="sxs-lookup"><span data-stu-id="25925-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="25925-127">Bei der Auswahl von Nutzlasten stehen Ihnen mehrere Datenpunkte zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="25925-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="25925-128">**Klickrate** zählt, wie viele Personen auf diese Nutzlast geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="25925-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="25925-129">**Prognostizierte Kompromiss Rate** prognostiziert, dass der Prozentsatz der Personen, die von dieser Nutzlast betroffen werden, basierend auf den Verlaufsdaten für die Nutzlast in Microsoft Defender für Office 365 Kunden beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="25925-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="25925-130">**Gestartete Simulationen** zählt die Häufigkeit, mit der diese Nutzlast in anderen Simulationen verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="25925-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="25925-131">Die **Komplexität**, die über **Filter** verfügbar ist, wird basierend auf der Anzahl der Indikatoren innerhalb der Nutzlast berechnet, die der Hinweis darauf abzielt, dass es sich um einen Angriff handelt.</span><span class="sxs-lookup"><span data-stu-id="25925-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="25925-132">Mehr Indikatoren führen zu einer geringeren Komplexität.</span><span class="sxs-lookup"><span data-stu-id="25925-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="25925-133">**Source**, verfügbar über **Filter**, gibt an, ob die Nutzlast auf Ihrem Mandanten erstellt wurde oder ein Bestandteil des bereits vorhandenen Payload-Katalogs (Global) von Microsoft ist.</span><span class="sxs-lookup"><span data-stu-id="25925-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Ausgewählte Nutzlast innerhalb der Angriffs Simulations Schulung im Microsoft 365 Security Center](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="25925-135">Wählen Sie in der Liste eine Nutzlast aus, um eine Vorschau der Nutzlast mit zusätzlichen Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="25925-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="25925-136">Wenn Sie eine eigene Nutzlast erstellen möchten, lesen Sie [Erstellen einer Nutzlast für die Angriffs Simulations Schulung](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="25925-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="25925-137">Zielgruppenadressierung</span><span class="sxs-lookup"><span data-stu-id="25925-137">Audience targeting</span></span>

<span data-ttu-id="25925-138">Jetzt ist es an der Zeit, die Zielgruppe dieser Simulation auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="25925-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="25925-139">Sie können auswählen, dass **alle Benutzer in Ihrer Organisation eingeschlossen** oder **nur bestimmte Benutzer und Gruppen eingeschlossen** werden sollen.</span><span class="sxs-lookup"><span data-stu-id="25925-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="25925-140">Wenn Sie **nur bestimmte Benutzer und Gruppen einbeziehen** möchten, können Sie entweder Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="25925-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="25925-141">**Fügen Sie Benutzer hinzu**, mit denen Sie die Suche für Ihren Mandanten sowie erweiterte Such-und Filterfunktionen nutzen können, beispielsweise für Benutzer, die in den letzten drei Monaten nicht auf eine Simulation ausgerichtet waren.</span><span class="sxs-lookup"><span data-stu-id="25925-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="25925-142">![Benutzer Filterung beim Angriffs Simulationstraining im Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="25925-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="25925-143">Mit dem **Import aus CSV** können Sie eine vordefinierte Gruppe von Benutzern für diese Simulation importieren.</span><span class="sxs-lookup"><span data-stu-id="25925-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="25925-144">Zuweisen von Schulungen</span><span class="sxs-lookup"><span data-stu-id="25925-144">Assigning training</span></span>

<span data-ttu-id="25925-145">Es wird empfohlen, eine Schulung für jede Simulation zuzuweisen, da Mitarbeiter, die die Schulung durchlaufen, für ähnliche Angriffe unempfindlicher sind.</span><span class="sxs-lookup"><span data-stu-id="25925-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="25925-146">Sie können entweder eine Schulung für Sie festlegen oder selbst Schulungskurse und Module auswählen.</span><span class="sxs-lookup"><span data-stu-id="25925-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="25925-147">Wählen Sie das **Fälligkeitsdatum für Schulungen** aus, um sicherzustellen, dass Mitarbeiter die Schulung rechtzeitig abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="25925-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="25925-148">Wenn Sie Kurse und Module selbst auswählen, können Sie weiterhin den empfohlenen Inhalt sowie alle verfügbaren Kurse und Module anzeigen.</span><span class="sxs-lookup"><span data-stu-id="25925-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Hinzufügen einer empfohlenen Schulung in der Schulung zur Angriffssimulation im Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="25925-150">In den nächsten Schritten müssen Sie **Schulungen hinzufügen** , wenn Sie sich für die Auswahl entschieden haben, und passen Sie Ihre Schulungsziel Seite an.</span><span class="sxs-lookup"><span data-stu-id="25925-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="25925-151">Sie können die Startseite der Schulung in einer Vorschau anzeigen und die Kopfzeile und den Textkörper ändern.</span><span class="sxs-lookup"><span data-stu-id="25925-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="25925-152">Starten von Details und überprüfen</span><span class="sxs-lookup"><span data-stu-id="25925-152">Launch details and review</span></span>

<span data-ttu-id="25925-153">Nachdem alles konfiguriert wurde, können Sie diese Simulation sofort starten oder zu einem späteren Zeitpunkt planen.</span><span class="sxs-lookup"><span data-stu-id="25925-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="25925-154">Sie müssen auch auswählen, wann diese Simulation beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="25925-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="25925-155">Die Aufzeichnung der Interaktion mit dieser Simulation wird nach der ausgewählten Zeit angehalten.</span><span class="sxs-lookup"><span data-stu-id="25925-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="25925-156">**Aktivieren Sie die regionsbezogene Zustellungs Zeitzonen** , um simulierte Angriffsmeldungen an Ihre Mitarbeiter während der Arbeitszeit basierend auf Ihrer Region zu liefern.</span><span class="sxs-lookup"><span data-stu-id="25925-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="25925-157">Wenn Sie fertig sind, klicken Sie auf **weiter** , und überprüfen Sie die Details der Simulation.</span><span class="sxs-lookup"><span data-stu-id="25925-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="25925-158">Klicken Sie auf **Bearbeiten** auf einem der Teile, um zurückzugehen, und ändern Sie alle Details, die geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="25925-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="25925-159">Klicken Sie nach Abschluss des Vorganges auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="25925-159">Once done, click **Submit**.</span></span>
