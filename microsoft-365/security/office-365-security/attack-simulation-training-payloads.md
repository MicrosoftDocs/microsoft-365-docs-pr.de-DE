---
title: Erstellen einer Nutzlast für Angriffssimulationsschulungen
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
description: Administratoren können erfahren, wie Sie benutzerdefinierte Nutzlasten für Angriffssimulationsschulungen in Microsoft Defender für Office 365 erstellen.
ms.technology: mdo
ms.openlocfilehash: ac7963b71c466e8dfdc513a2563776cd4e10af95
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878760"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="3fe5a-103">Erstellen einer benutzerdefinierten Nutzlast für Angriffssimulationsschulungen</span><span class="sxs-lookup"><span data-stu-id="3fe5a-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="3fe5a-104">**Gilt** [für Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="3fe5a-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="3fe5a-105">Microsoft bietet einen robusten Nutzlastkatalog für verschiedene Social Engineering-Techniken, die sie mit Ihrem Angriffssimulationstraining kombinieren können.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-105">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="3fe5a-106">Möglicherweise möchten Sie jedoch benutzerdefinierte Nutzlasten erstellen, die für Ihre Organisation besser funktionieren.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-106">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="3fe5a-107">In diesem Artikel wird beschrieben, wie Sie eine Nutzlast im Angriffssimulationstraining in Microsoft Defender für Office 365 erstellen.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-107">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="3fe5a-108">Sie können eine Nutzlast erstellen, indem Sie auf der [Registerkarte "Dedizierte **Nutzlasten"**](https://security.microsoft.com/attacksimulator?viewid=payload) oder im [Simulationserstellungs-Assistenten](attack-simulation-training.md#selecting-a-payload)auf **"Nutzlast** erstellen" klicken.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-108">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="3fe5a-109">Im ersten Schritt des Assistenten müssen Sie einen Nutzlasttyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-109">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="3fe5a-110">**Derzeit ist nur E-Mail verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="3fe5a-110">**Currently, only email is available**.</span></span>

<span data-ttu-id="3fe5a-111">Wählen Sie als Nächstes eine zugeordnete Technik aus.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-111">Next, select an associated technique.</span></span> <span data-ttu-id="3fe5a-112">Weitere Informationen zu Techniken finden Sie unter ["Auswählen einer Technik für Social Engineering".](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="3fe5a-112">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="3fe5a-113">Benennen Sie im nächsten Schritt Ihre Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-113">In the next step name your payload.</span></span> <span data-ttu-id="3fe5a-114">Optional können Sie ihr eine Beschreibung geben.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-114">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="3fe5a-115">Konfigurieren der Nutzlast</span><span class="sxs-lookup"><span data-stu-id="3fe5a-115">Configure payload</span></span>

<span data-ttu-id="3fe5a-116">Jetzt ist es an der Zeit, Ihre Nutzlast zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-116">Now it's time to build your payload.</span></span> <span data-ttu-id="3fe5a-117">Geben Sie im Abschnitt **"Absenderdetails"** den Namen, die E-Mail-Adresse und den Betreff der E-Mail ein.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-117">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="3fe5a-118">Wählen Sie eine Phishing-URL aus der bereitgestellten Liste aus.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-118">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="3fe5a-119">Diese URL wird später in den Textkörper der Nachricht eingebettet.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-119">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="3fe5a-120">Sie können eine interne E-Mail für den Absender Ihrer Nutzlast auswählen, wodurch die Nutzlast so angezeigt wird, dass sie von einem anderen Mitarbeiter des Unternehmens stammt.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-120">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="3fe5a-121">Dies erhöht die Anfälligkeit für die Nutzlast und hilft mitarbeitern, das Risiko interner Bedrohungen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-121">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="3fe5a-122">Zum Erstellen Ihrer Nutzlast steht ein Rich-Text-Editor zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-122">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="3fe5a-123">Sie können auch eine E-Mail importieren, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-123">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="3fe5a-124">Wenn Sie den Textkörper der E-Mail erstellen, nutzen Sie die **dynamischen Tags,** um die E-Mail an Ihre Ziele zu personalisieren.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-124">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="3fe5a-125">Klicken Sie auf den **Phishing-Link,** um die zuvor ausgewählte Phishing-URL zum Nachrichtentext hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-125">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Phishing-Link und dynamische Tags, die in der Nutzlasterstellung für Microsoft Defender für Office 365 hervorgehoben sind](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="3fe5a-127">Um Zeit zu sparen, aktivieren Sie die Option, **alle Links in der E-Mail-Nachricht durch den Phishinglink** zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-127">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="3fe5a-128">Nachdem Sie die Nutzlast nach Ihren Wünschen erstellt haben, klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="3fe5a-128">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="3fe5a-129">Hinzufügen von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="3fe5a-129">Adding indicators</span></span>

<span data-ttu-id="3fe5a-130">Indikatoren helfen Mitarbeitern, die die Angriffssimulation durchlaufen, die Hinweise zu verstehen, nach denen sie bei zukünftigen Angriffen suchen können.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-130">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="3fe5a-131">Klicken Sie zunächst auf **"Indikator hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="3fe5a-131">To start, click **Add indicator**.</span></span>

<span data-ttu-id="3fe5a-132">Wählen Sie in der Dropdownliste einen Indikator aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-132">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="3fe5a-133">Diese Liste wird so zusammengestellt, dass sie die häufigsten Hinweise enthält, die in Phishing-E-Mail-Nachrichten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-133">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="3fe5a-134">Stellen Sie nach der Auswahl sicher, dass die Platzierung des Indikators auf **"Vom Textkörper" der E-Mail** festgelegt ist, und klicken Sie auf **"Text auswählen".**</span><span class="sxs-lookup"><span data-stu-id="3fe5a-134">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="3fe5a-135">Markieren Sie den Teil Ihrer Nutzlast, in dem dieser Indikator angezeigt wird, und klicken Sie auf **"Auswählen".**</span><span class="sxs-lookup"><span data-stu-id="3fe5a-135">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Hervorgehobener Text im Nachrichtentext, der einem Indikator im Angriffssimulationstraining hinzugefügt werden soll](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="3fe5a-137">Fügen Sie eine benutzerdefinierte Beschreibung hinzu, um den Indikator zu beschreiben, und klicken Sie auf den Vorschauframe des Indikators, um eine Vorschau des Indikators anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-137">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="3fe5a-138">Klicken Sie anschließend auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="3fe5a-138">Once done, click **Add**.</span></span> <span data-ttu-id="3fe5a-139">Wiederholen Sie diese Schritte, bis Sie alle Indikatoren in Ihrer Nutzlast abgedeckt haben.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-139">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="3fe5a-140">Überprüfen der Nutzlast</span><span class="sxs-lookup"><span data-stu-id="3fe5a-140">Review payload</span></span>

<span data-ttu-id="3fe5a-141">Sie haben die Erstellung Ihrer Nutzlast abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-141">You're done building your payload.</span></span> <span data-ttu-id="3fe5a-142">Jetzt ist es an der Zeit, die Details zu überprüfen und eine Vorschau Ihrer Nutzlast anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-142">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="3fe5a-143">Die Vorschau enthält alle Indikatoren, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-143">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="3fe5a-144">Sie können jeden Teil der Nutzlast in diesem Schritt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-144">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="3fe5a-145">Sobald Sie zufrieden sind, können Sie Ihre Nutzlast **übermitteln.**</span><span class="sxs-lookup"><span data-stu-id="3fe5a-145">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fe5a-146">Nutzlasten, die Sie erstellt haben, verfügen über **"Mandant"** als Quelle.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-146">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="3fe5a-147">Stellen Sie beim Auswählen von Nutzlasten sicher, dass Sie den **Mandanten** nicht herausfiltern.</span><span class="sxs-lookup"><span data-stu-id="3fe5a-147">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="3fe5a-148">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="3fe5a-148">Related links</span></span>

[<span data-ttu-id="3fe5a-149">Erste Schritte mit dem Angriffssimulationstraining</span><span class="sxs-lookup"><span data-stu-id="3fe5a-149">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="3fe5a-150">Erstellen einer Phishingangriffssimulation</span><span class="sxs-lookup"><span data-stu-id="3fe5a-150">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="3fe5a-151">Gewinnen Sie Erkenntnisse durch Angriffssimulationsschulungen</span><span class="sxs-lookup"><span data-stu-id="3fe5a-151">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
