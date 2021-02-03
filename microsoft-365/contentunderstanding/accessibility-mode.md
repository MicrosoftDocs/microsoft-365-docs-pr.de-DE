---
title: 'SharePoint -Syntex-Barrierefreiheitsmodus '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Erfahren Sie, wie Sie den Barrierefreiheitsmodus verwenden, wenn Sie ein Modell in SharePoint Syntex trainieren.
ms.openlocfilehash: 32e5bd132a7a0145f03e4620545d65d1d92ff223
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50081007"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="51c5f-103">SharePoint -Syntex-Barrierefreiheitsmodus</span><span class="sxs-lookup"><span data-stu-id="51c5f-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="51c5f-104">In [SharePoint Syntex](index.md)können Benutzer den Barrierefreiheitsmodus in allen Phasen der Modellschulung (Bezeichnung, Schulung, Test) beim Arbeiten mit Beispieldokumenten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="51c5f-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="51c5f-105">Mithilfe des Barrierefreiheitsmodus können Benutzer mit geringer Anzeigezugriffshilfen leichter auf die Tastatur barrierefrei sein, wenn sie in der Dokumentanzeige navigieren und Elemente mit Bezeichnungen versehen.</span><span class="sxs-lookup"><span data-stu-id="51c5f-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="51c5f-106">Auf diese Weise können Benutzer mithilfe ihrer Tastaturen durch Text in der Dokumentanzeige navigieren und nicht nur die ausgewählten Werte, sondern auch Aktionen (z. B. Bezeichnungen oder Entfernen von Bezeichnungen aus markierten Texten) oder vorhergesagte Bezeichnungswerte hören, während Sie das Modell mit zusätzlichen Beispieldokumenten trainieren.</span><span class="sxs-lookup"><span data-stu-id="51c5f-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![Barrierefreiheitsmodus](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="51c5f-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51c5f-108">Requirements</span></span>

<span data-ttu-id="51c5f-109">Um die Audiowiedergabe der Sprachausgabe zu hören, müssen Sie die [Sprachausgabe-App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in den Sprachausgabeeinstellungen auf Ihrem Windows 10-System aktivieren.</span><span class="sxs-lookup"><span data-stu-id="51c5f-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![Sprachausgabe aktivieren](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="51c5f-111">Bezeichnung für Tastaturbenutzer</span><span class="sxs-lookup"><span data-stu-id="51c5f-111">Labeling for keyboard users</span></span>

<span data-ttu-id="51c5f-112">Für Tastaturbenutzer, die den Barrierefreiheitsmodus verwenden, können Sie die folgenden Tasten verwenden, wenn Sie Text in einem Beispieldokument im Viewer beschriften:</span><span class="sxs-lookup"><span data-stu-id="51c5f-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="51c5f-113">TAB: Verschiebt Sie vorwärts und wählt das nächste Wort aus.</span><span class="sxs-lookup"><span data-stu-id="51c5f-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="51c5f-114">TAB+ UMSCHALT: Verschiebt Sie nach hinten und wählt das vorherige Wort aus.</span><span class="sxs-lookup"><span data-stu-id="51c5f-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="51c5f-115">Enter: Label or removes a label from the selected word.</span><span class="sxs-lookup"><span data-stu-id="51c5f-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="51c5f-116">Vorwärtspfeil: Verschiebt Sie durch einzelne Zeichen in einem ausgewählten Wort vorwärts.</span><span class="sxs-lookup"><span data-stu-id="51c5f-116">Forward arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="51c5f-117">Abwärtspfeil: Verschiebt Sie in einem ausgewählten Wort rückwärts durch einzelne Zeichen.</span><span class="sxs-lookup"><span data-stu-id="51c5f-117">Backward arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="51c5f-118">Wenn Sie mehrere Wörter für eine einzelne Bezeichnung beschriften, müssen Sie jedes Wort beschriften.</span><span class="sxs-lookup"><span data-stu-id="51c5f-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="51c5f-119">Kommentar</span><span class="sxs-lookup"><span data-stu-id="51c5f-119">Narration</span></span>

<span data-ttu-id="51c5f-120">Verwenden Sie für Benutzer der Sprachausgabe, die den Barrierefreiheitsmodus verwenden, dieselbe Tastaturnavigation, die für Tastaturbenutzer beschrieben wird, um das Beispieldokument im Viewer zu durchgehen.</span><span class="sxs-lookup"><span data-stu-id="51c5f-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="51c5f-121">Während Sie durch die Beispieldokumente und Diebeschriftungswerte navigieren, gibt die Sprachausgabe dem Benutzer die folgenden Audioaufforderungen:</span><span class="sxs-lookup"><span data-stu-id="51c5f-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="51c5f-122">Wenn Sie die Tastatur verwenden, um durch die Dokumentanzeige zu navigieren, wird die ausgewählte Zeichenfolge von Sprachausgabeaudio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51c5f-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="51c5f-123">Innerhalb einer ausgewählten Zeichenfolge gibt die Sprachausgabe jedes Zeichen in der Zeichenfolge an, während Sie sie mithilfe des Vorwärts- oder Rückwärtspfeils auswählen.</span><span class="sxs-lookup"><span data-stu-id="51c5f-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the forward or backward arrow.</span></span>
- <span data-ttu-id="51c5f-124">Wenn Sie eine Zeichenfolge auswählen, die mit bezeichnungen versehen wurde, gibt die Sprachausgabe den Wert und dann "mit Bezeichnung" an.</span><span class="sxs-lookup"><span data-stu-id="51c5f-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="51c5f-125">Wenn der Bezeichnungswert beispielsweise "Contoso" ist, wird "Costoso mit Bezeichnung" angegeben.</span><span class="sxs-lookup"><span data-stu-id="51c5f-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="51c5f-126">Wenn Sie auf der Registerkarte "Schulung" eine Zeichenfolge in der Dokumentanzeige auswählen, die nur vorhergesagt wurde, gibt die Sprachausgabe den Wert und dann "vorhergesagt" an.</span><span class="sxs-lookup"><span data-stu-id="51c5f-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="51c5f-127">Dies tritt auf, wenn beim Training ein Wert in der Datei vorherzusagen ist, der nicht mit dem vom Benutzer bezeichneten Wert übereinstimmen kann.</span><span class="sxs-lookup"><span data-stu-id="51c5f-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="51c5f-128">Wenn Sie auf der Registerkarte "Schulung" eine Zeichenfolge in der Dokumentanzeige auswählen, die mit Bezeichnungen versehen und vorhergesagt wurde, gibt die Sprachausgabe den Wert und dann "mit Bezeichnungen und Vorhersagen" an.</span><span class="sxs-lookup"><span data-stu-id="51c5f-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="51c5f-129">Dies tritt auf, wenn die Schulung erfolgreich ist und eine Übereinstimmung zwischen einem vorhergesagten Wert und der Benutzerbezeichnung besteht.</span><span class="sxs-lookup"><span data-stu-id="51c5f-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="51c5f-130">Nachdem eine Zeichenfolge mit einer Bezeichnung versehen oder eine Bezeichnung im Viewer entfernt wurde, warnt die Sprachausgabe Sie, die Änderungen vor dem Beenden zu speichern.</span><span class="sxs-lookup"><span data-stu-id="51c5f-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="51c5f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51c5f-131">See Also</span></span>

[<span data-ttu-id="51c5f-132">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="51c5f-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="51c5f-133">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="51c5f-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



