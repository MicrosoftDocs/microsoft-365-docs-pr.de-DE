---
title: Erstellen einer Nutzlast für attack simulation training
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren erfahren, wie Sie benutzerdefinierte Nutzlasten für attack simulation training in Microsoft Defender for Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204072"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="fd24a-103">Erstellen einer benutzerdefinierten Nutzlast für Angriffssimulationsschulungen</span><span class="sxs-lookup"><span data-stu-id="fd24a-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="fd24a-104">Microsoft bietet einen robusten Nutzlastkatalog für verschiedene Social -Engineering-Techniken, die Sie mit Ihrem Training zur Angriffssimulation koppeln können.</span><span class="sxs-lookup"><span data-stu-id="fd24a-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="fd24a-105">Möglicherweise möchten Sie jedoch benutzerdefinierte Nutzlasten erstellen, die für Ihre Organisation besser funktionieren.</span><span class="sxs-lookup"><span data-stu-id="fd24a-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="fd24a-106">In diesem Artikel wird beschrieben, wie Sie eine Nutzlast in attack simulation training in Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="fd24a-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="fd24a-107">Sie können eine Nutzlast erstellen, indem Sie auf der Registerkarte Dedizierte Nutzlasten oder im Assistenten zum Erstellen der Simulation auf Nutzlast [erstellen klicken.](attack-simulation-training.md#selecting-a-payload) [  ](https://security.microsoft.com/attacksimulator?viewid=payload) </span><span class="sxs-lookup"><span data-stu-id="fd24a-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="fd24a-108">Im ersten Schritt des Assistenten müssen Sie einen Nutzlasttyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="fd24a-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="fd24a-109">**Derzeit ist nur E-Mail verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="fd24a-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="fd24a-110">Wählen Sie als Nächstes eine zugeordnete Technik aus.</span><span class="sxs-lookup"><span data-stu-id="fd24a-110">Next, select an associated technique.</span></span> <span data-ttu-id="fd24a-111">Weitere Informationen zu Techniken finden Sie unter [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span><span class="sxs-lookup"><span data-stu-id="fd24a-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="fd24a-112">Nennen Sie im nächsten Schritt Die Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="fd24a-112">In the next step name your payload.</span></span> <span data-ttu-id="fd24a-113">Optional können Sie ihm eine Beschreibung geben.</span><span class="sxs-lookup"><span data-stu-id="fd24a-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="fd24a-114">Konfigurieren der Nutzlast</span><span class="sxs-lookup"><span data-stu-id="fd24a-114">Configure payload</span></span>

<span data-ttu-id="fd24a-115">Jetzt ist es an der Zeit, Ihre Nutzlast zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fd24a-115">Now it's time to build your payload.</span></span> <span data-ttu-id="fd24a-116">Geben Sie den Namen des Absenders, die E-Mail-Adresse und den Betreff der E-Mail im Abschnitt **Absenderdetails** ein.</span><span class="sxs-lookup"><span data-stu-id="fd24a-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="fd24a-117">Wählen Sie eine Phishing-URL aus der bereitgestellten Liste aus.</span><span class="sxs-lookup"><span data-stu-id="fd24a-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="fd24a-118">Diese URL wird später in den Nachrichtentext eingebettet.</span><span class="sxs-lookup"><span data-stu-id="fd24a-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="fd24a-119">Sie können eine interne E-Mail für den Absender Ihrer Nutzlast auswählen, wodurch die Nutzlast als von einem anderen Mitarbeiter des Unternehmens stammt.</span><span class="sxs-lookup"><span data-stu-id="fd24a-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="fd24a-120">Dies erhöht die Anfälligkeit für die Nutzlast und hilft, Mitarbeiter über das Risiko interner Bedrohungen aufzuklären.</span><span class="sxs-lookup"><span data-stu-id="fd24a-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="fd24a-121">Zum Erstellen Ihrer Nutzlast steht ein Rich-Text-Editor zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fd24a-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="fd24a-122">Sie können auch eine E-Mail importieren, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="fd24a-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="fd24a-123">Wenn Sie den Textkörper der E-Mail erstellen, nutzen Sie die dynamischen Tags, um die E-Mail an Ihre Ziele zu personalisieren. </span><span class="sxs-lookup"><span data-stu-id="fd24a-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="fd24a-124">Klicken **Sie auf Phishinglink,** um die zuvor ausgewählte Phishing-URL dem Nachrichtentext hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fd24a-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Phishinglinks und dynamische Tags, die in der Nutzlasterstellung für Microsoft Defender for Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="fd24a-126">Um Zeit zu sparen, aktivieren Sie die Option, um alle Links in der E-Mail-Nachricht durch **den Phishinglink zu ersetzen.**</span><span class="sxs-lookup"><span data-stu-id="fd24a-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="fd24a-127">Nachdem Sie die Nutzlast nach Ihren Wünschen erstellen, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fd24a-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="fd24a-128">Hinzufügen von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="fd24a-128">Adding indicators</span></span>

<span data-ttu-id="fd24a-129">Mithilfe von Indikatoren können Mitarbeiter, die die Angriffssimulation durch führen, den Hinweis verstehen, nach dem sie bei zukünftigen Angriffen suchen können.</span><span class="sxs-lookup"><span data-stu-id="fd24a-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="fd24a-130">Klicken Sie zu Beginn auf **Indikator hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="fd24a-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="fd24a-131">Wählen Sie in der Dropdownliste einen Indikator aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="fd24a-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="fd24a-132">Diese Liste ist so gehärtet, dass sie die häufigsten Hinweise enthält, die in Phishing-E-Mail-Nachrichten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fd24a-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="fd24a-133">Stellen Sie nach der Auswahl sicher, dass die Anzeigeplatzierung auf **Vom Textkörper** der E-Mail festgelegt ist, und klicken Sie auf **Text auswählen.**</span><span class="sxs-lookup"><span data-stu-id="fd24a-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="fd24a-134">Markieren Sie den Teil Ihrer Nutzlast, in dem dieser Indikator angezeigt wird, und klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="fd24a-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Hervorgehobener Text im Nachrichtentext, der einem Indikator im Training zur Angriffssimulation hinzugefügt werden soll](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="fd24a-136">Fügen Sie eine benutzerdefinierte Beschreibung hinzu, um den Indikator zu beschreiben, und klicken Sie im Vorschaurahmen des Indikators, um eine Vorschau des Indikators anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fd24a-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="fd24a-137">Klicken Sie nach getaner Arbeit auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fd24a-137">Once done, click **Add**.</span></span> <span data-ttu-id="fd24a-138">Wiederholen Sie diese Schritte, bis Sie alle Indikatoren in Ihrer Nutzlast behandelt haben.</span><span class="sxs-lookup"><span data-stu-id="fd24a-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="fd24a-139">Überprüfen der Nutzlast</span><span class="sxs-lookup"><span data-stu-id="fd24a-139">Review payload</span></span>

<span data-ttu-id="fd24a-140">Sie sind damit fertig, Ihre Nutzlast zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fd24a-140">You're done building your payload.</span></span> <span data-ttu-id="fd24a-141">Jetzt ist es an der Zeit, die Details zu überprüfen und eine Vorschau ihrer Nutzlast anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fd24a-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="fd24a-142">Die Vorschau enthält alle von Ihnen erstellten Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="fd24a-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="fd24a-143">In diesem Schritt können Sie jeden Teil der Nutzlast bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="fd24a-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="fd24a-144">Sobald Sie zufrieden sind, können Sie **Ihre** Nutzlast übermitteln.</span><span class="sxs-lookup"><span data-stu-id="fd24a-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd24a-145">Nutzlasten, die Sie erstellt haben, haben **Mandanten** als Quelle.</span><span class="sxs-lookup"><span data-stu-id="fd24a-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="fd24a-146">Stellen Sie beim Auswählen von Nutzlasten sicher, dass Sie Mandanten nicht **herausfiltern.**</span><span class="sxs-lookup"><span data-stu-id="fd24a-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="fd24a-147">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="fd24a-147">Related links</span></span>

[<span data-ttu-id="fd24a-148">Erste Schritte mit dem Angriffssimulationstraining</span><span class="sxs-lookup"><span data-stu-id="fd24a-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="fd24a-149">Erstellen einer Phishingangriffssimulation</span><span class="sxs-lookup"><span data-stu-id="fd24a-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="fd24a-150">Gewinnen Sie Erkenntnisse durch Angriffssimulationsschulungen</span><span class="sxs-lookup"><span data-stu-id="fd24a-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
