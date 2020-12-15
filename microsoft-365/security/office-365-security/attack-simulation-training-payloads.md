---
title: Erstellen einer Nutzlast für die Angriffs Simulations Schulung
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Administratoren können erfahren, wie Sie benutzerdefinierte Nutzlasten für die Angriffs Simulations Schulung in Microsoft Defender für Office 365 erstellen.
ms.openlocfilehash: c42090634f6fa9500ae4c3e781b49b607ee928f5
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667504"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="8b729-103">Erstellen einer benutzerdefinierten Nutzlast für Angriffssimulationsschulungen</span><span class="sxs-lookup"><span data-stu-id="8b729-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="8b729-104">Microsoft bietet einen robusten Nutz Last Katalog für verschiedene Social Engineering-Techniken, um mit Ihrem Angriffs Simulationstraining zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="8b729-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="8b729-105">Möglicherweise möchten Sie jedoch benutzerdefinierte Nutzlasten erstellen, die für Ihre Organisation besser verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b729-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="8b729-106">In diesem Artikel wird beschrieben, wie Sie eine Nutzlast in Attack Simulation Training in Microsoft Defender für Office 365 erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b729-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8b729-107">Sie können eine Nutzlast erstellen, indem Sie auf der [Registerkarte dedizierte **Nutzlasten**](https://security.microsoft.com/attacksimulator?viewid=payload) oder im [Simulations Erstellungs-Assistenten](attack-simulation-training.md#selecting-a-payload)auf **Nutzlast erstellen** klicken.</span><span class="sxs-lookup"><span data-stu-id="8b729-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="8b729-108">Im ersten Schritt des Assistenten können Sie einen Payload-Typ auswählen.</span><span class="sxs-lookup"><span data-stu-id="8b729-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="8b729-109">**Derzeit ist nur e-Mail verfügbar**.</span><span class="sxs-lookup"><span data-stu-id="8b729-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="8b729-110">Wählen Sie als nächstes eine zugehörige Technik aus.</span><span class="sxs-lookup"><span data-stu-id="8b729-110">Next, select an associated technique.</span></span> <span data-ttu-id="8b729-111">Weitere Informationen finden Sie unter Techniken bei [der Auswahl einer Social Engineering-Technik](attack-simulation-training.md#selecting-a-social-engineering-technique).</span><span class="sxs-lookup"><span data-stu-id="8b729-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="8b729-112">Geben Sie im nächsten Schritt den Namen Ihrer Nutzlast ein.</span><span class="sxs-lookup"><span data-stu-id="8b729-112">In the next step name your payload.</span></span> <span data-ttu-id="8b729-113">Optional können Sie ihm eine Beschreibung geben.</span><span class="sxs-lookup"><span data-stu-id="8b729-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="8b729-114">Konfigurieren der Nutzlast</span><span class="sxs-lookup"><span data-stu-id="8b729-114">Configure payload</span></span>

<span data-ttu-id="8b729-115">Jetzt ist es an der Zeit, Ihre Nutzlast zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b729-115">Now it's time to build your payload.</span></span> <span data-ttu-id="8b729-116">Geben Sie den Namen des Absenders, die e-Mail-Adresse und den Betreff der e-Mail im Abschnitt **Absenderdetails** ein.</span><span class="sxs-lookup"><span data-stu-id="8b729-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="8b729-117">Wählen Sie eine Phishing-URL aus der bereitgestellten Liste aus.</span><span class="sxs-lookup"><span data-stu-id="8b729-117">Pick a phishing URL from the the provided list.</span></span> <span data-ttu-id="8b729-118">Diese URL wird später in den Text der Nachricht eingebettet.</span><span class="sxs-lookup"><span data-stu-id="8b729-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="8b729-119">Sie können eine interne e-Mail-Adresse für den Absender Ihrer Nutzlast auswählen, sodass die Nutzlast als von einem anderen Mitarbeiter des Unternehmens angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8b729-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="8b729-120">Dadurch wird die Anfälligkeit für die Nutzlast erhöht, und die Mitarbeiter werden bei der Gefahr interner Bedrohungen unterrichtet.</span><span class="sxs-lookup"><span data-stu-id="8b729-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="8b729-121">Ein Rich-Text-Editor steht zur Verfügung, um Ihre Nutzlast zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b729-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="8b729-122">Sie können auch eine e-Mail importieren, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="8b729-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="8b729-123">Wenn Sie den Textkörper der e-Mail erstellen, nutzen Sie die **dynamischen Tags** , um die e-Mail an Ihre Ziele zu personalisieren.</span><span class="sxs-lookup"><span data-stu-id="8b729-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="8b729-124">Klicken Sie auf **Phishing-Link** , um die zuvor ausgewählte Phishing-URL in den Textkörper der Nachricht einzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b729-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Phishing-Link und dynamische Tags, die in der Nutzlast-Erstellung für Microsoft Defender für Office 365 hervorgehoben wurden](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="8b729-126">Um Zeit zu sparen, schalten Sie die Option zum **Ersetzen aller Links in der e-Mail-Nachricht durch den Phishing-Link** ein.</span><span class="sxs-lookup"><span data-stu-id="8b729-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="8b729-127">Nachdem Sie die Nutzlast nach Ihren Wünschen gebaut haben, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="8b729-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="8b729-128">Hinzufügen von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="8b729-128">Adding indicators</span></span>

<span data-ttu-id="8b729-129">Mithilfe von Indikatoren können Mitarbeiter, die die Angriffssimulation durchlaufen, den Anhaltspunkt verstehen, nach dem Sie in zukünftigen Angriffen suchen können.</span><span class="sxs-lookup"><span data-stu-id="8b729-129">Indicators will help employees going through the attack simulation understand clue they can look for in future attacks.</span></span> <span data-ttu-id="8b729-130">Klicken Sie zum Starten auf **Indikator hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8b729-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="8b729-131">Wählen Sie in der Dropdownliste einen Indikator aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8b729-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="8b729-132">Diese Liste wird kuratiert, um die häufigsten Hinweise enthalten, die in Phishing-e-Mails angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8b729-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="8b729-133">Nachdem Sie ausgewählt haben, stellen Sie sicher, dass die Indikator Platzierung auf **aus dem Textkörper der e-Mail** festgelegt ist, und klicken Sie auf **Text auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8b729-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="8b729-134">Markieren Sie den Teil der Nutzlast, in dem dieses Symbol angezeigt wird, und klicken Sie auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8b729-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Hervorgehobener Text im Nachrichtentext, der einem Indikator in Angriffs Simulationstraining hinzugefügt werden soll](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="8b729-136">Fügen Sie eine benutzerdefinierte Beschreibung hinzu, um den Indikator zu beschreiben, und klicken Sie innerhalb des Indikator Vorschau Frames, um eine Vorschau des Indikators anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8b729-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="8b729-137">Klicken Sie nach Abschluss des Vorganges auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8b729-137">Once done, click **Add**.</span></span> <span data-ttu-id="8b729-138">Wiederholen Sie diese Schritte, bis Sie alle Indikatoren in ihrer Nutzlast abgedeckt haben.</span><span class="sxs-lookup"><span data-stu-id="8b729-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="8b729-139">Überprüfen der Nutzlast</span><span class="sxs-lookup"><span data-stu-id="8b729-139">Review payload</span></span>

<span data-ttu-id="8b729-140">Sie haben die Erstellung Ihrer Nutzlast abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8b729-140">You're done building your payload.</span></span> <span data-ttu-id="8b729-141">Jetzt ist es an der Zeit, die Details zu überprüfen und eine Vorschau Ihrer Nutzlast anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8b729-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="8b729-142">Die Vorschau enthält alle Indikatoren, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="8b729-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="8b729-143">Sie können die einzelnen Teile der Nutzlast in diesem Schritt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8b729-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="8b729-144">Sobald Sie zufrieden sind, **senden** Sie Ihre Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="8b729-144">Once satisfied, **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b729-145">Die von Ihnen erstellten Nutzdaten haben einen **Mandanten** als Quelle.</span><span class="sxs-lookup"><span data-stu-id="8b729-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="8b729-146">Stellen Sie beim Auswählen von Nutzdaten sicher, dass Sie den **Mandanten** nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="8b729-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>
