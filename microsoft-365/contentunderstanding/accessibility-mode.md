---
title: 'Barrierefreiheitsmodus für SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Erfahren Sie, wie Sie den Barrierefreiheitsmodus verwenden, wenn Sie ein Modell in SharePoint Syntex trainieren.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515148"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="cad88-103">Barrierefreiheitsmodus für SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="cad88-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="cad88-104">In [SharePoint Syntex](index.md)können Benutzer den Barrierefreiheitsmodus in allen Phasen der Modellschulung (Bezeichnung, Schulung, Test) beim Arbeiten mit Beispieldokumenten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cad88-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="cad88-105">Die Verwendung des Barrierefreiheitsmodus kann Benutzern mit niedriger Sicht bei der Navigation und Beschriftung von Elementen in der Dokumentanzeige helfen, die Barrierefreiheit auf der Tastatur zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="cad88-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="cad88-106">Auf diese Weise können Benutzer ihre Tastaturen verwenden, um durch Text in der Dokumentanzeige zu navigieren und eine Erzählung nicht nur der ausgewählten Werte, sondern auch von Aktionen (z. B. Beschriftung oder Entfernen von Bezeichnungen aus markierten Texten) oder vorhergesagte Beschriftungswerte zu hören, während Sie das Modell mit zusätzlichen Beispieldokumenten trainieren.</span><span class="sxs-lookup"><span data-stu-id="cad88-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![Barrierefreiheitsmodus](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="cad88-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cad88-108">Requirements</span></span>

<span data-ttu-id="cad88-109">Um die Audiodaten der Sprachausgabe zu hören, müssen Sie die [Sprachausgabe-App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in Ihren Sprachausgabe auf Ihrem Windows 10 aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cad88-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![Aktivieren Sprachausgabe](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="cad88-111">Bezeichnung für Tastaturbenutzer</span><span class="sxs-lookup"><span data-stu-id="cad88-111">Labeling for keyboard users</span></span>

<span data-ttu-id="cad88-112">Bei Tastaturbenutzern, die den Barrierefreiheitsmodus verwenden, können Sie die folgenden Tasten verwenden, wenn Sie Text in einem Beispieldokument im Viewer beschriften:</span><span class="sxs-lookup"><span data-stu-id="cad88-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="cad88-113">Tab: Verschiebt Sie vorwärts und wählt das nächste Wort aus.</span><span class="sxs-lookup"><span data-stu-id="cad88-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="cad88-114">Tabulator + Umschalt: Verschiebt Sie nach hinten und wählt das vorherige Wort aus.</span><span class="sxs-lookup"><span data-stu-id="cad88-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="cad88-115">Enter: Label or removes a label from the selected word.</span><span class="sxs-lookup"><span data-stu-id="cad88-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="cad88-116">Pfeil nach rechts: Verschiebt Sie durch einzelne Zeichen in einem ausgewählten Wort.</span><span class="sxs-lookup"><span data-stu-id="cad88-116">Right arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="cad88-117">Pfeil nach links: Verschiebt Sie rückwärts durch einzelne Zeichen in einem ausgewählten Wort.</span><span class="sxs-lookup"><span data-stu-id="cad88-117">Left arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="cad88-118">Wenn Sie mehrere Wörter für eine einzelne Bezeichnung beschriften, müssen Sie jedes Wort beschriften.</span><span class="sxs-lookup"><span data-stu-id="cad88-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="cad88-119">Erzählung</span><span class="sxs-lookup"><span data-stu-id="cad88-119">Narration</span></span>

<span data-ttu-id="cad88-120">Wenn Sprachausgabe Barrierefreiheitsmodus verwenden, verwenden Sie dieselbe Tastaturnavigation, die für Tastaturbenutzer beschrieben wird, um das Beispieldokument im Viewer zu durchgehen.</span><span class="sxs-lookup"><span data-stu-id="cad88-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="cad88-121">Wenn Sie durch die Beispieldokumente und Beschriftungszeichenfolgenwerte navigieren, Sprachausgabe Benutzer die folgenden Audioaufforderungen erhalten:</span><span class="sxs-lookup"><span data-stu-id="cad88-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="cad88-122">Wenn Sie die Tastatur verwenden, um durch die Dokumentanzeige zu navigieren, Sprachausgabe audio die ausgewählte Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="cad88-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="cad88-123">Innerhalb einer ausgewählten Zeichenfolge Sprachausgabe audio jedes Zeichen in der Zeichenfolge angeben, während Sie sie mithilfe der PFEILTASTEn nach links oder rechts auswählen.</span><span class="sxs-lookup"><span data-stu-id="cad88-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the left or right arrow keys.</span></span>
- <span data-ttu-id="cad88-124">Wenn Sie eine Zeichenfolge auswählen, die beschriftet wurde, Sprachausgabe den Wert und dann "beschriftet" an.</span><span class="sxs-lookup"><span data-stu-id="cad88-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="cad88-125">Wenn der Bezeichnungswert beispielsweise "Contoso" ist, wird "Costoso labeled" angegeben.</span><span class="sxs-lookup"><span data-stu-id="cad88-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="cad88-126">Wenn Sie auf der Registerkarte Schulung eine Zeichenfolge in der Dokumentanzeige auswählen, die nur vorhergesagt wurde, Sprachausgabe audio den Wert und dann "vorhergesagt".</span><span class="sxs-lookup"><span data-stu-id="cad88-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="cad88-127">Dies tritt auf, wenn die Schulung einen Wert in der Datei vorhersagt, der nicht mit dem vom Benutzer bezeichneten Wert übereinstimmen kann.</span><span class="sxs-lookup"><span data-stu-id="cad88-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="cad88-128">Wenn Sie auf der Registerkarte Schulung eine Zeichenfolge in der Dokumentanzeige auswählen, die beschriftet und vorhergesagt wurde, gibt Sprachausgabe audio den Wert an, und dann "beschriftet und vorhergesagt".</span><span class="sxs-lookup"><span data-stu-id="cad88-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="cad88-129">Dies tritt auf, wenn die Schulung erfolgreich ist und eine Übereinstimmung zwischen einem vorhergesagten Wert und der Benutzerbezeichnung besteht.</span><span class="sxs-lookup"><span data-stu-id="cad88-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="cad88-130">Nachdem eine Zeichenfolge beschriftet oder eine Bezeichnung im Viewer entfernt wurde, warnt Sprachausgabe Audio, ihre Änderungen vor dem Beenden zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cad88-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="cad88-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cad88-131">See Also</span></span>

[<span data-ttu-id="cad88-132">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="cad88-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="cad88-133">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="cad88-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



