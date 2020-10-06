---
title: Erklärungstypen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Weitere Informationen über Erklärungstypen in Microsoft SharePoint Syntex
ms.openlocfilehash: 43272504912451e4690cb8b7fe351462371bb252
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350303"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="20420-103">Einführung in Erklärungstypen</span><span class="sxs-lookup"><span data-stu-id="20420-103">Introduction to explanation types</span></span>

<span data-ttu-id="20420-104">Erklärungen werden verwendet, um die Informationen zu definieren, die Sie in Ihren Document Understanding-Modellen in Microsoft SharePoint Syntex bezeichnen und extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="20420-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="20420-105">Wenn Sie eine Erklärung erstellen, müssen Sie einen Erklärungstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="20420-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="20420-106">Dieser Artikel soll Ihnen helfen, die verschiedenen Erklärungstypen und ihre Verwendung besser zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="20420-106">This article will help you learn more to better understand the different explanation types and how they are used.</span></span> 

   ![Erklärungstypen](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="20420-108">Diese Erklärungstypen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="20420-108">These explanation types are available:</span></span>

- <span data-ttu-id="20420-109">**Begriffsliste**: Liste von Wörtern, Phrasen, Zahlen oder anderen Zeichen, die Sie in dem Dokument oder der Information, die Sie extrahieren, verwenden können.</span><span class="sxs-lookup"><span data-stu-id="20420-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="20420-110">Zum Beispiel ist die Textzeichenfolge **Überweisender Arzt** in allen Dokumenten "Ärztliche Überweisung" enthalten, die Sie identifizieren.</span><span class="sxs-lookup"><span data-stu-id="20420-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="20420-111">**Musterliste**: Auflisten von Mustern aus Zahlen, Buchstaben oder anderen Zeichen, die Sie zur Identifizierung der Informationen, die Sie extrahieren, verwenden können.</span><span class="sxs-lookup"><span data-stu-id="20420-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="20420-112">Sie können beispielsweise die **Telefonnummer** des überweisenden Arztes aus allen Dokumenten "Ärztliche Überweisung" extrahieren, die Sie identifizieren.</span><span class="sxs-lookup"><span data-stu-id="20420-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="20420-113">**Näherung**: Beschreibt, wie nahe die Erklärungen beieinander liegen.</span><span class="sxs-lookup"><span data-stu-id="20420-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="20420-114">Zum Beispiel geht eine Musterliste *Straßennummer* direkt vor die Begriffsliste *Straßenname*, ohne Token dazwischen (Sie werden später in diesem Artikel mehr über Token erfahren).</span><span class="sxs-lookup"><span data-stu-id="20420-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="20420-115">Die Verwendung des Näherungstyps erfordert, dass Sie mindestens zwei Erklärungen in Ihrem Modell haben, sonst wird die Option deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="20420-115">Using the proximity type requires you to have at least two explanations in your model, or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="20420-116">Begriffsliste</span><span class="sxs-lookup"><span data-stu-id="20420-116">Phrase list</span></span>

<span data-ttu-id="20420-117">Der Erklärungstyp "Begriffsliste" wird normalerweise verwendet, um ein Dokument durch Ihr Modell zu identifizieren und zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="20420-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="20420-118">Wie im Beispiel der Bezeichnung *Überweisender Arzt* beschrieben, handelt es sich dabei um eine Kette von Wörtern, Phrasen, Zahlen oder Zeichen, die in den Dokumenten, die Sie identifizieren, konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="20420-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="20420-119">Auch wenn dies keine Voraussetzung ist, können Sie mit Ihrer Erklärung einen besseren Erfolg erzielen, wenn die Phrase, die Sie erfassen, sich an einer konsistenten Stelle in Ihrem Dokument befindet.</span><span class="sxs-lookup"><span data-stu-id="20420-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="20420-120">Beispielsweise kann sich die Bezeichnung *Überweisender Arzt* durchgängig im ersten Absatz des Dokuments befinden.</span><span class="sxs-lookup"><span data-stu-id="20420-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="20420-121">Wenn die Groß-/Kleinschreibung bei der Identifizierung Ihrer Bezeichnung beachtet werden muss, können Sie dies in Ihrer Erklärung mit dem Typ "Begriffsliste" angeben, indem Sie das Kontrollkästchen **Nur exakte Groß-/Kleinschreibung** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="20420-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Unterscheidung nach Groß-/Kleinschreibung](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="20420-123">Musterlisten</span><span class="sxs-lookup"><span data-stu-id="20420-123">Pattern lists</span></span>

<span data-ttu-id="20420-124">Ein Musterlistentyp ist besonders nützlich, wenn Sie eine Erklärung erstellen, die Informationen aus einem Dokument identifiziert und extrahiert.</span><span class="sxs-lookup"><span data-stu-id="20420-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="20420-125">Sie wird in der Regel in verschiedenen Formaten dargestellt, wie z. B. Datum, Telefonnummern oder Kreditkartennummern.</span><span class="sxs-lookup"><span data-stu-id="20420-125">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="20420-126">Beispielsweise kann ein Datum in verschiedenen Formaten angezeigt werden (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1.1.2020 usw.).</span><span class="sxs-lookup"><span data-stu-id="20420-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="20420-127">Die Definition einer Musterliste macht Ihre Erklärung effizienter, indem sie alle möglichen Variationen in den Daten erfasst, die Sie zu identifizieren und zu extrahieren versuchen.</span><span class="sxs-lookup"><span data-stu-id="20420-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="20420-128">Für das Beispiel **Telefonnummer** extrahieren Sie die Telefonnummer für jeden überweisenden Arzt aus allen Dokumenten "Ärztliche Überweisung", die das Modell identifiziert.</span><span class="sxs-lookup"><span data-stu-id="20420-128">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="20420-129">Wenn Sie die Erklärung erstellen, wählen Sie den Musterlistentyp aus, um die verschiedenen Formate zuzulassen, von denen Sie erwarten können, dass sie zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="20420-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Musterliste "Telefonnummer"](../media/content-understanding/pattern-list.png)

<span data-ttu-id="20420-131">Für dieses Beispiel aktivieren Sie das Kontrollkästchen **Beliebige Ziffer von 0-9**.</span><span class="sxs-lookup"><span data-stu-id="20420-131">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="20420-132">Wenn Sie dies aktivieren, wird jeder "0"-Wert, der in Ihrer Musterliste verwendet wird, als eine beliebige Ziffer von 0 bis 9 erkannt.</span><span class="sxs-lookup"><span data-stu-id="20420-132">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Beliebige Ziffer von 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="20420-134">Wenn Sie eine Musterliste erstellen, die Textzeichen enthält, aktivieren Sie in ähnlicher Weise das Kontrollkästchen **Jeder Buchstabe von a-z**.</span><span class="sxs-lookup"><span data-stu-id="20420-134">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="20420-135">Wenn Sie dies aktivieren, wird jedes "a"-Zeichen, das in der Musterliste verwendet wird, als ein beliebiges Zeichen von "a" bis "z" erkannt.</span><span class="sxs-lookup"><span data-stu-id="20420-135">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="20420-136">Wenn Sie beispielsweise eine Musterliste **Datum** erstellen und sicherstellen möchten, dass ein Datumsformat wie z. B. *Jan 1, 2020* erkannt wird, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="20420-136">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="20420-137">Fügen Sie Ihrer Musterliste *aaa 0, 0000* und *aaa 00, 0000* hinzu.</span><span class="sxs-lookup"><span data-stu-id="20420-137">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="20420-138">Stellen Sie sicher, dass auch **Beliebiger Buchstabe von a-z** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="20420-138">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Beliebiger Buchstabe von a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="20420-140">Wenn Sie in Ihrer Musterliste Groß-/Kleinschreibungsanforderungen haben, haben Sie zusätzlich die Möglichkeit, das Kontrollkästchen **Nur genaue Groß-/Kleinschreibung** zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="20420-140">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="20420-141">Wenn Sie für das Beispiel "Datum" den ersten Buchstaben des Monats groß schreiben möchten, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="20420-141">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="20420-142">Fügen Sie Ihrer Musterliste *Aaa 0, 0000* und *Aaa 00, 0000* hinzu.</span><span class="sxs-lookup"><span data-stu-id="20420-142">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="20420-143">Stellen Sie sicher, dass auch **Nur genaue Groß-/Kleinschreibung** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="20420-143">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Nur genaue Groß-/Kleinschreibung](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="20420-145">Statt die Erklärung der Musterliste manuell zu erstellen, verwenden Sie die [Erklärungsbibliothek](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates), um vorgefertigte Musterlistenvorlagen für allgemeine Musterlisten zu verwenden, wie z. B. *Datum*, *Telefonnummer*, *Kreditkartennummer* usw.</span><span class="sxs-lookup"><span data-stu-id="20420-145">Instead of manually creating pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="20420-146">Näherung</span><span class="sxs-lookup"><span data-stu-id="20420-146">Proximity</span></span> 

<span data-ttu-id="20420-147">Der Erklärungstyp "Näherung" hilft Ihrem Modell bei der Identifizierung von Daten, indem er definiert, wie nahe ein anderer Datenbestand an ihm liegt.</span><span class="sxs-lookup"><span data-stu-id="20420-147">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="20420-148">Beispielsweise haben Sie in Ihrem Modell zwei Erklärungen definiert, die sowohl die *Straßennummer* als auch die *Telefonnummer* des Kunden bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="20420-148">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="20420-149">Außerdem stellen Sie fest, dass die Telefonnummern des Kunden immer vor der Straßennummer erscheinen.</span><span class="sxs-lookup"><span data-stu-id="20420-149">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="20420-150">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="20420-150">Alex Wilburn</span></span><br>
<span data-ttu-id="20420-151">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="20420-151">555-555-5555</span></span><br>
<span data-ttu-id="20420-152">Langgasse 18</span><span class="sxs-lookup"><span data-stu-id="20420-152">One Microsoft Way</span></span><br>
<span data-ttu-id="20420-153">54123 Münchfeld</span><span class="sxs-lookup"><span data-stu-id="20420-153">Redmond, WA 98034</span></span><br>

<span data-ttu-id="20420-154">Verwenden Sie die Näherungserklärung, um festzulegen, wie weit die Erklärung "Telefonnummer" entfernt ist, um die Straßennummer in Ihren Dokumenten besser identifizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="20420-154">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Näherungserklärung](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="20420-156">Was sind Token?</span><span class="sxs-lookup"><span data-stu-id="20420-156">What are tokens?</span></span>

<span data-ttu-id="20420-157">Um den Erklärungstyp "Näherung" verwenden zu können, müssen Sie verstehen, was ein Token ist, da die Anzahl der Token angibt, wie die Näherungserklärung den Abstand von einer Erklärung zur anderen misst.</span><span class="sxs-lookup"><span data-stu-id="20420-157">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="20420-158">Ein Token ist eine kontinuierliche Spanne (keine Leerzeichen oder Interpunktion) von Buchstaben und Zahlen.</span><span class="sxs-lookup"><span data-stu-id="20420-158">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="20420-159">Ein Leerzeichen ist KEIN Token.</span><span class="sxs-lookup"><span data-stu-id="20420-159">A space is NOT a token.</span></span> <span data-ttu-id="20420-160">Jedes Interpunktionszeichen ist ein Token.</span><span class="sxs-lookup"><span data-stu-id="20420-160">Each punctuation character is a token.</span></span> <span data-ttu-id="20420-161">Die folgende Tabelle zeigt einige Beispiele für das Ermitteln der Anzahl von Token in einer Phrase.</span><span class="sxs-lookup"><span data-stu-id="20420-161">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="20420-162">Phrase</span><span class="sxs-lookup"><span data-stu-id="20420-162">Phrase</span></span>|<span data-ttu-id="20420-163">Anzahl von Token</span><span class="sxs-lookup"><span data-stu-id="20420-163">Number of tokens</span></span>|<span data-ttu-id="20420-164">Erklärung</span><span class="sxs-lookup"><span data-stu-id="20420-164">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="20420-165">1</span><span class="sxs-lookup"><span data-stu-id="20420-165">1</span></span>|<span data-ttu-id="20420-166">Ein einzelnes Wort ohne Interpunktionszeichen oder Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="20420-166">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="20420-167">1</span><span class="sxs-lookup"><span data-stu-id="20420-167">1</span></span>|<span data-ttu-id="20420-168">Eine Datensatz-Locator-Nummer.</span><span class="sxs-lookup"><span data-stu-id="20420-168">A record locator number.</span></span> <span data-ttu-id="20420-169">Sie kann Zahlen und Buchstaben enthalten, hat aber keine Interpunktion.</span><span class="sxs-lookup"><span data-stu-id="20420-169">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="20420-170">5</span><span class="sxs-lookup"><span data-stu-id="20420-170">5</span></span>|<span data-ttu-id="20420-171">Eine Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="20420-171">A phone number.</span></span> <span data-ttu-id="20420-172">Jedes Interpunktionszeichen ist ein einzelnes Token, sodass  `425-555-5555` 5 Tokens wären:</span><span class="sxs-lookup"><span data-stu-id="20420-172">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="20420-173">7</span><span class="sxs-lookup"><span data-stu-id="20420-173">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="20420-174">Konfigurieren des Erklärungstyps "Näherung"</span><span class="sxs-lookup"><span data-stu-id="20420-174">Configure the proximity explanation type</span></span>

<span data-ttu-id="20420-175">Konfigurieren Sie für das Beispiel die Einstellung für die Näherung so, dass wir den Bereich der Anzahl der Token definieren können, die die Erklärung *Telefonnummer* aus der Erklärung *Straßennummer* enthält.</span><span class="sxs-lookup"><span data-stu-id="20420-175">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="20420-176">Sie sollten sehen, dass der Mindestbereich "0" ist, da es keine Token zwischen der Telefonnummer und der Straßennummer gibt.</span><span class="sxs-lookup"><span data-stu-id="20420-176">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="20420-177">Einige Telefonnummern in den Beispieldokumenten sind jedoch mit *(Mobil)* angehängt.</span><span class="sxs-lookup"><span data-stu-id="20420-177">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="20420-178">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="20420-178">Nestor Wilke</span></span><br>
<span data-ttu-id="20420-179">111-111-1111 (Mobil)</span><span class="sxs-lookup"><span data-stu-id="20420-179">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="20420-180">Langgasse 18</span><span class="sxs-lookup"><span data-stu-id="20420-180">One Microsoft Way</span></span><br>
<span data-ttu-id="20420-181">54123 Münchfeld</span><span class="sxs-lookup"><span data-stu-id="20420-181">Redmond, WA 98034</span></span><br>

<span data-ttu-id="20420-182">Es gibt drei Token in *(Mobil)*:</span><span class="sxs-lookup"><span data-stu-id="20420-182">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="20420-183">Phrase</span><span class="sxs-lookup"><span data-stu-id="20420-183">Phrase</span></span>|<span data-ttu-id="20420-184">Tokenzahl</span><span class="sxs-lookup"><span data-stu-id="20420-184">Token count</span></span>|
|--|--|
|<span data-ttu-id="20420-185">(</span><span class="sxs-lookup"><span data-stu-id="20420-185">(</span></span>|<span data-ttu-id="20420-186">1</span><span class="sxs-lookup"><span data-stu-id="20420-186">1</span></span>|
|<span data-ttu-id="20420-187">Mobil</span><span class="sxs-lookup"><span data-stu-id="20420-187">mobile</span></span>|<span data-ttu-id="20420-188">2</span><span class="sxs-lookup"><span data-stu-id="20420-188">2</span></span>|
|<span data-ttu-id="20420-189">)</span><span class="sxs-lookup"><span data-stu-id="20420-189">)</span></span>|<span data-ttu-id="20420-190">3</span><span class="sxs-lookup"><span data-stu-id="20420-190">3</span></span>|

<span data-ttu-id="20420-191">Konfigurieren Sie die Einstellung für die Näherung so, dass sie einen Wert von 0 bis 3 aufweist.</span><span class="sxs-lookup"><span data-stu-id="20420-191">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Beispiel einer Näherung](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="20420-193">Verwenden von Erklärungsvorlagen</span><span class="sxs-lookup"><span data-stu-id="20420-193">Use explanation templates</span></span>

<span data-ttu-id="20420-194">Sie können zwar manuell verschiedene Musterlistenwerte für Ihre Erklärung hinzufügen, es kann jedoch viel einfacher sein, die vorgefertigten Vorlagen zu verwenden, die Ihnen in der Erklärungsbibliothek zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="20420-194">While you can manually add various pattern list values for your explanation, it can be much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="20420-195">Statt z. B. alle Varianten für *Datum* manuell hinzuzufügen, können Sie die Musterlistenvorlage für\* Datum\* verwenden, die bereits eine Reihe von Musterlistenwerten enthält:</span><span class="sxs-lookup"><span data-stu-id="20420-195">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Erklärungsbibliothek](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="20420-197">Die Erklärungsbibliothek enthält eine Reihe von häufig verwendeten Musterlistenerklärungen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="20420-197">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="20420-198">Datum</span><span class="sxs-lookup"><span data-stu-id="20420-198">Date</span></span></br>
- <span data-ttu-id="20420-199">Datum (numerisch)</span><span class="sxs-lookup"><span data-stu-id="20420-199">Date (numeric)</span></span></br>
- <span data-ttu-id="20420-200">Zeit</span><span class="sxs-lookup"><span data-stu-id="20420-200">Time</span></span></br>
- <span data-ttu-id="20420-201">Zahl</span><span class="sxs-lookup"><span data-stu-id="20420-201">Number</span></span></br>
- <span data-ttu-id="20420-202">Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="20420-202">Phone number</span></span></br>
- <span data-ttu-id="20420-203">PLZ</span><span class="sxs-lookup"><span data-stu-id="20420-203">Zip code</span></span></br>
- <span data-ttu-id="20420-204">Erstes Wort des Satzes</span><span class="sxs-lookup"><span data-stu-id="20420-204">First word of sentence</span></span></br>
- <span data-ttu-id="20420-205">Kreditkarte</span><span class="sxs-lookup"><span data-stu-id="20420-205">Credit card</span></span></br>
- <span data-ttu-id="20420-206">Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="20420-206">Social security number</span></span></br>

<span data-ttu-id="20420-207">Beachten Sie, dass die Erklärungsbibliothek auch Vorlagen für Begriffslistenerklärungen enthält, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="20420-207">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="20420-208">Ende des Satzes</span><span class="sxs-lookup"><span data-stu-id="20420-208">End of sentence</span></span>
- <span data-ttu-id="20420-209">Währung</span><span class="sxs-lookup"><span data-stu-id="20420-209">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="20420-210">Verwenden einer Vorlage aus der Erklärungsbibliothek</span><span class="sxs-lookup"><span data-stu-id="20420-210">To use a template from the explanation library</span></span>

1. <span data-ttu-id="20420-211">Wählen Sie im Abschnitt **Erklärungen** auf der Seite **Trainieren** Ihres Modells **Neu** aus und dann **Aus einer Vorlage**.</span><span class="sxs-lookup"><span data-stu-id="20420-211">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Aus Vorlage erstellen](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="20420-213">Wählen Sie auf der Seite **Erklärungsvorlagen** die Erklärung aus, die Sie verwenden möchten, und wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="20420-213">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Auswählen einer Vorlage](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="20420-215">Die Informationen für die von Ihnen ausgewählte Vorlage werden auf der Seite **Erklärung erstellen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20420-215">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="20420-216">Bearbeiten Sie bei Bedarf den Namen der Erklärung und fügen Sie Elemente zur Musterliste hinzu oder entfernen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="20420-216">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Vorlage bearbeiten](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="20420-218">Wählen Sie anschließend **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="20420-218">When finished, select **Save**.</span></span>
