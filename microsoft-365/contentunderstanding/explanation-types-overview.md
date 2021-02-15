---
title: Erklärungstypen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Weitere Informationen über Erklärungstypen in Microsoft SharePoint Syntex
ms.openlocfilehash: caba92b635feaf8f87e2c487559f70be3fab6df9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242592"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="591c0-103">Einführung in Erklärungstypen</span><span class="sxs-lookup"><span data-stu-id="591c0-103">Introduction to explanation types</span></span>

<span data-ttu-id="591c0-104">Erklärungen werden verwendet, um die Informationen zu definieren, die Sie in Ihren Document Understanding-Modellen in Microsoft SharePoint Syntex bezeichnen und extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="591c0-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="591c0-105">Wenn Sie eine Erklärung erstellen, müssen Sie einen Erklärungstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="591c0-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="591c0-106">Dieser Artikel hilft Ihnen dabei, die verschiedenen Erklärungstypen und ihre Verwendung zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="591c0-106">This article helps you understand the different explanation types and how they are used.</span></span> 

   ![Erklärungstypen](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="591c0-108">Diese Erklärungstypen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="591c0-108">These explanation types are available:</span></span>

- <span data-ttu-id="591c0-109">**Begriffsliste**: Liste von Wörtern, Phrasen, Zahlen oder anderen Zeichen, die Sie in dem Dokument oder der Information, die Sie extrahieren, verwenden können.</span><span class="sxs-lookup"><span data-stu-id="591c0-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="591c0-110">Zum Beispiel ist die Textzeichenfolge **Überweisender Arzt** in allen Dokumenten "Ärztliche Überweisung" enthalten, die Sie identifizieren.</span><span class="sxs-lookup"><span data-stu-id="591c0-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="591c0-111">**Musterliste**: Auflisten von Mustern aus Zahlen, Buchstaben oder anderen Zeichen, die Sie zur Identifizierung der Informationen, die Sie extrahieren, verwenden können.</span><span class="sxs-lookup"><span data-stu-id="591c0-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="591c0-112">Sie können beispielsweise die **Telefonnummer** des überweisenden Arztes aus allen Dokumenten "Ärztliche Überweisung" extrahieren, die Sie identifizieren.</span><span class="sxs-lookup"><span data-stu-id="591c0-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="591c0-113">**Näherung**: Beschreibt, wie nahe die Erklärungen beieinander liegen.</span><span class="sxs-lookup"><span data-stu-id="591c0-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="591c0-114">Zum Beispiel geht eine Musterliste *Straßennummer* direkt vor die Begriffsliste *Straßenname*, ohne Token dazwischen (Sie werden später in diesem Artikel mehr über Token erfahren).</span><span class="sxs-lookup"><span data-stu-id="591c0-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="591c0-115">Die Verwendung des Näherungstyps erfordert, dass Sie mindestens zwei Erklärungen in Ihrem Modell haben, ansonsten die Option deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="591c0-115">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="591c0-116">Begriffsliste</span><span class="sxs-lookup"><span data-stu-id="591c0-116">Phrase list</span></span>

<span data-ttu-id="591c0-117">Der Erklärungstyp "Begriffsliste" wird normalerweise verwendet, um ein Dokument durch Ihr Modell zu identifizieren und zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="591c0-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="591c0-118">Wie im Beispiel der Bezeichnung *Überweisender Arzt* beschrieben, handelt es sich dabei um eine Kette von Wörtern, Phrasen, Zahlen oder Zeichen, die in den Dokumenten, die Sie identifizieren, konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="591c0-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="591c0-119">Auch wenn dies keine Voraussetzung ist, können Sie mit Ihrer Erklärung einen besseren Erfolg erzielen, wenn die Phrase, die Sie erfassen, sich an einer konsistenten Stelle in Ihrem Dokument befindet.</span><span class="sxs-lookup"><span data-stu-id="591c0-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="591c0-120">Beispielsweise kann sich die Bezeichnung *Überweisender Arzt* durchgängig im ersten Absatz des Dokuments befinden.</span><span class="sxs-lookup"><span data-stu-id="591c0-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="591c0-121">Wenn die Groß-/Kleinschreibung bei der Identifizierung Ihrer Bezeichnung beachtet werden muss, können Sie dies in Ihrer Erklärung mit dem Typ "Begriffsliste" angeben, indem Sie das Kontrollkästchen **Nur exakte Groß-/Kleinschreibung** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="591c0-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Unterscheidung nach Groß-/Kleinschreibung](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="591c0-123">Musterlisten</span><span class="sxs-lookup"><span data-stu-id="591c0-123">Pattern lists</span></span>

<span data-ttu-id="591c0-124">Ein Musterlistentyp ist besonders nützlich, wenn Sie eine Erklärung erstellen, die Informationen aus einem Dokument identifiziert und extrahiert.</span><span class="sxs-lookup"><span data-stu-id="591c0-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="591c0-125">Er wird in der Regel in verschiedenen Formaten dargestellt, wie z. B. Datum, Telefonnummern und Kreditkartennummern.</span><span class="sxs-lookup"><span data-stu-id="591c0-125">It is typically presented in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="591c0-126">Beispielsweise kann ein Datum in verschiedenen Formaten angezeigt werden (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1.1.2020 usw.).</span><span class="sxs-lookup"><span data-stu-id="591c0-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="591c0-127">Die Definition einer Musterliste macht Ihre Erklärung effizienter, indem sie alle möglichen Variationen in den Daten erfasst, die Sie zu identifizieren und zu extrahieren versuchen.</span><span class="sxs-lookup"><span data-stu-id="591c0-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="591c0-128">Für das Beispiel **Telefonnummer** extrahieren Sie die Telefonnummer für jeden überweisenden Arzt aus allen Dokumenten "Ärztliche Überweisung", die das Modell identifiziert.</span><span class="sxs-lookup"><span data-stu-id="591c0-128">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="591c0-129">Wenn Sie die Erklärung erstellen, wählen Sie den Musterlistentyp aus, um die verschiedenen Formate zuzulassen, von denen Sie erwarten können, dass sie zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="591c0-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Musterliste "Telefonnummer"](../media/content-understanding/pattern-list.png)

<span data-ttu-id="591c0-131">Wählen Sie in diesem Beispiel das Kontrollkästchen **Beliebige Ziffer von 0-9** aus, um zu erkennen, dass es sich bei jedem in Ihrer Musterliste verwendeten „0“-Wert um eine beliebige Ziffer von 0 bis 9 handelt.</span><span class="sxs-lookup"><span data-stu-id="591c0-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Beliebige Ziffer von 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="591c0-133">Wenn Sie eine Musterliste erstellen, die Textzeichen enthält, wählen Sie in ähnlicher Weise das Kontrollkästchen **Beliebige Buchstaben von a-z** aus, um zu erkennen, dass es sich bei jedem in Ihrer Musterliste verwendeten "a" -Zeichen um ein beliebiges Zeichen zwischen "a" und "z" handelt.</span><span class="sxs-lookup"><span data-stu-id="591c0-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="591c0-134">Wenn Sie beispielsweise eine Musterliste **Datum** erstellen und sicherstellen möchten, dass ein Datumsformat wie z. B. *Jan 1, 2020* erkannt wird, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="591c0-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="591c0-135">Fügen Sie Ihrer Musterliste *aaa 0, 0000* und *aaa 00, 0000* hinzu.</span><span class="sxs-lookup"><span data-stu-id="591c0-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="591c0-136">Stellen Sie sicher, dass auch **Beliebiger Buchstabe von a-z** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="591c0-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Beliebiger Buchstabe von a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="591c0-138">Wenn Sie in Ihrer Musterliste Groß-/Kleinschreibungsanforderungen haben, haben Sie zusätzlich die Möglichkeit, das Kontrollkästchen **Nur genaue Groß-/Kleinschreibung** zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="591c0-138">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="591c0-139">Wenn Sie für das Beispiel "Datum" den ersten Buchstaben des Monats groß schreiben möchten, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="591c0-139">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="591c0-140">Fügen Sie Ihrer Musterliste *Aaa 0, 0000* und *Aaa 00, 0000* hinzu.</span><span class="sxs-lookup"><span data-stu-id="591c0-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="591c0-141">Stellen Sie sicher, dass auch **Nur genaue Groß-/Kleinschreibung** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="591c0-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Nur genaue Groß-/Kleinschreibung](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="591c0-143">Statt eine Musterlistenerklärung manuell zu erstellen, verwenden Sie die [Erklärungsbibliothek](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates), um Musterlistenvorlagen für allgemeine Musterlisten zu verwenden, wie z. B. *Datum*, *Telefonnummer*, *Kreditkartennummer* usw.</span><span class="sxs-lookup"><span data-stu-id="591c0-143">Instead of manually creating a pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="591c0-144">Näherung</span><span class="sxs-lookup"><span data-stu-id="591c0-144">Proximity</span></span> 

<span data-ttu-id="591c0-145">Der Erklärungstyp "Näherung" hilft Ihrem Modell bei der Identifizierung von Daten, indem er definiert, wie nahe ein anderes Datenelement an ihm liegt.</span><span class="sxs-lookup"><span data-stu-id="591c0-145">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="591c0-146">Beispielsweise haben Sie in Ihrem Modell zwei Erklärungen definiert, die sowohl die *Straßennummer* als auch die *Telefonnummer* des Kunden bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="591c0-146">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="591c0-147">Beachten Sie, dass die Telefonnummern des Kunden immer vor der Straßennummer steht.</span><span class="sxs-lookup"><span data-stu-id="591c0-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="591c0-148">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="591c0-148">Alex Wilburn</span></span><br>
<span data-ttu-id="591c0-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="591c0-149">555-555-5555</span></span><br>
<span data-ttu-id="591c0-150">Langgasse 18</span><span class="sxs-lookup"><span data-stu-id="591c0-150">One Microsoft Way</span></span><br>
<span data-ttu-id="591c0-151">54123 Münchfeld</span><span class="sxs-lookup"><span data-stu-id="591c0-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="591c0-152">Verwenden Sie die Näherungserklärung, um festzulegen, wie weit die Erklärung "Telefonnummer" entfernt ist, um die Straßennummer in Ihren Dokumenten besser identifizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="591c0-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Näherungserklärung](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="591c0-154">Was sind Token?</span><span class="sxs-lookup"><span data-stu-id="591c0-154">What are tokens?</span></span>

<span data-ttu-id="591c0-155">Um den Erklärungstyp "Näherung" verwenden zu können, müssen Sie verstehen, was ein Token ist, da die Anzahl der Token angibt, wie die Näherungserklärung den Abstand von einer Erklärung zur anderen misst.</span><span class="sxs-lookup"><span data-stu-id="591c0-155">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="591c0-156">Ein Token ist eine kontinuierliche Reihe (ohne Leerzeichen oder Interpunktionen) von Buchstaben und Zahlen.</span><span class="sxs-lookup"><span data-stu-id="591c0-156">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="591c0-157">Die folgende Tabelle zeigt Beispiele, wie die Anzahl der Token in einer Phrase ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="591c0-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="591c0-158">Phrase</span><span class="sxs-lookup"><span data-stu-id="591c0-158">Phrase</span></span>|<span data-ttu-id="591c0-159">Anzahl von Token</span><span class="sxs-lookup"><span data-stu-id="591c0-159">Number of tokens</span></span>|<span data-ttu-id="591c0-160">Erklärung</span><span class="sxs-lookup"><span data-stu-id="591c0-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="591c0-161">1</span><span class="sxs-lookup"><span data-stu-id="591c0-161">1</span></span>|<span data-ttu-id="591c0-162">Ein einzelnes Wort ohne Interpunktionszeichen oder Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="591c0-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="591c0-163">1</span><span class="sxs-lookup"><span data-stu-id="591c0-163">1</span></span>|<span data-ttu-id="591c0-164">Eine Datensatz-Locator-Nummer.</span><span class="sxs-lookup"><span data-stu-id="591c0-164">A record locator number.</span></span> <span data-ttu-id="591c0-165">Sie kann Zahlen und Buchstaben beinhalten, hat aber keine Interpunktion.</span><span class="sxs-lookup"><span data-stu-id="591c0-165">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="591c0-166">5</span><span class="sxs-lookup"><span data-stu-id="591c0-166">5</span></span>|<span data-ttu-id="591c0-167">Eine Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="591c0-167">A phone number.</span></span> <span data-ttu-id="591c0-168">Jedes Interpunktionszeichen ist ein einzelnes Token, also ist `425-555-5555` 5 Tokens:</span><span class="sxs-lookup"><span data-stu-id="591c0-168">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="591c0-169">7</span><span class="sxs-lookup"><span data-stu-id="591c0-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="591c0-170">Konfigurieren des Erklärungstyps "Näherung"</span><span class="sxs-lookup"><span data-stu-id="591c0-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="591c0-171">Konfigurieren Sie für das Beispiel die Näherungseinstellung, um den Bereich der Anzahl der Token in der *Telefonnummer*-Erklärung aus der *Straßenadressnummer*-Erklärung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="591c0-171">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="591c0-172">Beachten sie, dass der Mindestbereich „0“ ist, da es keine Token zwischen der Telefonnummer und der Straßenadressnummer gibt.</span><span class="sxs-lookup"><span data-stu-id="591c0-172">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="591c0-173">Einige Telefonnummern in den Beispieldokumenten sind jedoch mit *(Mobil)* ergänzt.</span><span class="sxs-lookup"><span data-stu-id="591c0-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="591c0-174">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="591c0-174">Nestor Wilke</span></span><br>
<span data-ttu-id="591c0-175">111-111-1111 (Mobil)</span><span class="sxs-lookup"><span data-stu-id="591c0-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="591c0-176">Langgasse 18</span><span class="sxs-lookup"><span data-stu-id="591c0-176">One Microsoft Way</span></span><br>
<span data-ttu-id="591c0-177">54123 Münchfeld</span><span class="sxs-lookup"><span data-stu-id="591c0-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="591c0-178">Es gibt drei Token in *(Mobil)*:</span><span class="sxs-lookup"><span data-stu-id="591c0-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="591c0-179">Phrase</span><span class="sxs-lookup"><span data-stu-id="591c0-179">Phrase</span></span>|<span data-ttu-id="591c0-180">Tokenzahl</span><span class="sxs-lookup"><span data-stu-id="591c0-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="591c0-181">(</span><span class="sxs-lookup"><span data-stu-id="591c0-181">(</span></span>|<span data-ttu-id="591c0-182">1</span><span class="sxs-lookup"><span data-stu-id="591c0-182">1</span></span>|
|<span data-ttu-id="591c0-183">Mobil</span><span class="sxs-lookup"><span data-stu-id="591c0-183">mobile</span></span>|<span data-ttu-id="591c0-184">2</span><span class="sxs-lookup"><span data-stu-id="591c0-184">2</span></span>|
|<span data-ttu-id="591c0-185">)</span><span class="sxs-lookup"><span data-stu-id="591c0-185">)</span></span>|<span data-ttu-id="591c0-186">3</span><span class="sxs-lookup"><span data-stu-id="591c0-186">3</span></span>|

<span data-ttu-id="591c0-187">Konfigurieren Sie die Einstellung für die Näherung so, dass sie einen Wert von 0 bis 3 aufweist.</span><span class="sxs-lookup"><span data-stu-id="591c0-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Beispiel einer Näherung](../media/content-understanding/proximity-example.png)</br>


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="591c0-189">Konfigurieren Sie, wo Ausdrücke im Dokument vorkommen.</span><span class="sxs-lookup"><span data-stu-id="591c0-189">Configure where phrases occur in the document</span></span>

<span data-ttu-id="591c0-190">Wenn Sie eine Erklärung erstellen, wird standardmäßig im gesamten Dokument nach dem Ausdruck gesucht, den Sie extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="591c0-190">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="591c0-191">Sie können jedoch die erweiterte Einstellung <b>Wo diese Ausdrücke vorkommen</b> verwenden, um eine bestimmte Stelle im Dokument zu isolieren, an der ein Ausdruck vorkommt.</span><span class="sxs-lookup"><span data-stu-id="591c0-191">However, you can use the <b>Where these phrases occur</b> advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="591c0-192">Dies ist in Situationen hilfreich, in denen ähnliche Instanzen eines Ausdrucks möglicherweise an einer anderen Stelle im Dokument auftreten und Sie sicherstellen möchten, dass der richtige Ausdruck ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="591c0-192">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="591c0-193">Unter Bezugnahme auf unser Dokument mit medizinischen Empfehlungen wird der **überweisende Arzt** immer im ersten Absatz des Dokuments erwähnt.</span><span class="sxs-lookup"><span data-stu-id="591c0-193">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="591c0-194">Mit der Einstellung <b>Wo diese Ausdrücke vorkommen</b> können Sie in diesem Beispiel Ihre Erklärung so konfigurieren, dass nach dieser Bezeichnung nur im Anfangsabschnitt des Dokuments oder an einer anderen Stelle gesucht wird, an der sie möglicherweise vorkommt.</span><span class="sxs-lookup"><span data-stu-id="591c0-194">With the <b>Where these phrases occur</b> setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

   ![Einstellung „Wo diese Ausdrücke vorkommen“](../media/content-understanding/phrase-location.png)</br>

<span data-ttu-id="591c0-196">Sie können für diese Einstellung die folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="591c0-196">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="591c0-197">An beliebiger Stelle in der Datei: Es wird das gesamte Dokument nach dem Ausdruck durchsucht.</span><span class="sxs-lookup"><span data-stu-id="591c0-197">Anywhere in the file: The entire document is searched for the phrase.</span></span>
- <span data-ttu-id="591c0-198">Anfang der Datei: Das Dokument wird vom Anfang bis zur Position des Ausdrucks durchsucht.</span><span class="sxs-lookup"><span data-stu-id="591c0-198">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span></br> 
   <span data-ttu-id="591c0-199">![Anfang der Datei](../media/content-understanding/beginning-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="591c0-199">![Beginning of file](../media/content-understanding/beginning-of-file.png)</span></span></br>
<span data-ttu-id="591c0-200">Im Viewer können Sie das Auswahlfeld manuell anpassen, um die Position einzugeben, an der die Phase erscheint.</span><span class="sxs-lookup"><span data-stu-id="591c0-200">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="591c0-201">Der Wert <b>Endposition</b> wird aktualisiert und zeigt die Anzahl der Token an, die im ausgewählten Bereich enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="591c0-201">The <b>End position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="591c0-202">Beachten Sie, dass Sie auch den Endpositionswert aktualisieren können, um den ausgewählten Bereich anzupassen.</span><span class="sxs-lookup"><span data-stu-id="591c0-202">Note that you can update the End position value as well to adjust the selected area.</span></span></br>
   <span data-ttu-id="591c0-203">![Positionsfeld „Anfang der Datei“](../media/content-understanding/beginning-box.png)</span><span class="sxs-lookup"><span data-stu-id="591c0-203">![Beginning of file position box](../media/content-understanding/beginning-box.png)</span></span></br>

- <span data-ttu-id="591c0-204">Ende der Datei: Das Dokument wird vom Ende bis zur Position des Ausdrucks durchsucht.</span><span class="sxs-lookup"><span data-stu-id="591c0-204">End of the file:  The document is searched from the end to the phrase location.</span></span></br> 
   <span data-ttu-id="591c0-205">![Ende der Datei](../media/content-understanding/end-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="591c0-205">![End of file](../media/content-understanding/end-of-file.png)</span></span></br>
<span data-ttu-id="591c0-206">Im Viewer können Sie das Auswahlfeld manuell anpassen, um die Position einzugeben, an der die Phase erscheint.</span><span class="sxs-lookup"><span data-stu-id="591c0-206">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="591c0-207">Der Wert <b>Startposition</b> wird aktualisiert und zeigt die Anzahl der Token an, die im ausgewählten Bereich enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="591c0-207">The <b>Starting position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="591c0-208">Beachten Sie, dass Sie auch den Startpositionswert aktualisieren können, um den ausgewählten Bereich anzupassen.</span><span class="sxs-lookup"><span data-stu-id="591c0-208">Note that you can update the Starting position value as well to adjust the selected area.</span></span></br> 
   <span data-ttu-id="591c0-209">![Positionsfeld „Ende der Datei“](../media/content-understanding/end-box.png)</span><span class="sxs-lookup"><span data-stu-id="591c0-209">![End of file end box](../media/content-understanding/end-box.png)</span></span></br>
- <span data-ttu-id="591c0-210">Benutzerdefiniert: Das Dokument wird in einem bestimmten Bereich innerhalb des Dokuments nach der Position des Ausdrucks durchsucht.</span><span class="sxs-lookup"><span data-stu-id="591c0-210">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span></br> 
   <span data-ttu-id="591c0-211">![Benutzerdefinierter Bereich](../media/content-understanding/custom-file.png)</span><span class="sxs-lookup"><span data-stu-id="591c0-211">![Custom range](../media/content-understanding/custom-file.png)</span></span></br>
<span data-ttu-id="591c0-212">Im Viewer können Sie das Auswahlfeld manuell anpassen, um die Position einzugeben, an der die Phase erscheint.</span><span class="sxs-lookup"><span data-stu-id="591c0-212">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="591c0-213">Für diese Einstellung müssen Sie je eine Position <b>Start</b> und <b>Ende</b> auswählen.</span><span class="sxs-lookup"><span data-stu-id="591c0-213">For this setting, you need to select a <b>Start</b> and an <b>End</b> position.</span></span> <span data-ttu-id="591c0-214">Diese Werte stellen die Anzahl der Token ab dem Anfang des Dokuments dar.</span><span class="sxs-lookup"><span data-stu-id="591c0-214">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="591c0-215">Sie können diese Werte zwar manuell eingeben, doch ist es einfacher, das Auswahlfeld im Viewer manuell anzupassen.</span><span class="sxs-lookup"><span data-stu-id="591c0-215">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span></br> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="591c0-216">Verwenden von Erklärungsvorlagen</span><span class="sxs-lookup"><span data-stu-id="591c0-216">Use explanation templates</span></span>

<span data-ttu-id="591c0-217">Während Sie manuell verschiedene Begriffslistenwerte für Ihre Erklärung hinzufügen können, kann es einfacher sein, die Vorlagen zu verwenden, die Ihnen in der Erklärungsbibliothek zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="591c0-217">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="591c0-218">Statt beispielsweise alle Varianten für *Datum* manuell hinzuzufügen, können Sie die Begriffslistenvorlage für *Datum* verwenden, da diese bereits eine Reihe von Begriffslistenwerten enthält:</span><span class="sxs-lookup"><span data-stu-id="591c0-218">For example, instead of manually adding all the variations for *Date*, you can use the phrase list template for *Date* as it already includes a number of phrase lists values:</span></span></br>

   ![Erklärungsbibliothek](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="591c0-220">Die Erklärungsbibliothek enthält häufig verwendeten Begriffslistenerklärungen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="591c0-220">The explanation library includes commonly used phrase list explanations, including:</span></span></br>

- <span data-ttu-id="591c0-221">Datum</span><span class="sxs-lookup"><span data-stu-id="591c0-221">Date</span></span></br>
- <span data-ttu-id="591c0-222">Datum (numerisch)</span><span class="sxs-lookup"><span data-stu-id="591c0-222">Date (numeric)</span></span></br>
- <span data-ttu-id="591c0-223">Zeit</span><span class="sxs-lookup"><span data-stu-id="591c0-223">Time</span></span></br>
- <span data-ttu-id="591c0-224">Zahl</span><span class="sxs-lookup"><span data-stu-id="591c0-224">Number</span></span></br>
- <span data-ttu-id="591c0-225">Prozentsatz</span><span class="sxs-lookup"><span data-stu-id="591c0-225">Percentage</span></span></br>
- <span data-ttu-id="591c0-226">Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="591c0-226">Phone number</span></span></br>
- <span data-ttu-id="591c0-227">PLZ</span><span class="sxs-lookup"><span data-stu-id="591c0-227">Zip code</span></span></br>
- <span data-ttu-id="591c0-228">Erstes Wort des Satzes</span><span class="sxs-lookup"><span data-stu-id="591c0-228">First word of sentence</span></span></br>
- <span data-ttu-id="591c0-229">Satzende</span><span class="sxs-lookup"><span data-stu-id="591c0-229">End of sentence</span></span></br>
- <span data-ttu-id="591c0-230">Kreditkarte</span><span class="sxs-lookup"><span data-stu-id="591c0-230">Credit card</span></span></br>
- <span data-ttu-id="591c0-231">Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="591c0-231">Social security number</span></span></br>
- <span data-ttu-id="591c0-232">Kontrollkästchen</span><span class="sxs-lookup"><span data-stu-id="591c0-232">Checkbox</span></span></br>
- <span data-ttu-id="591c0-233">Währung</span><span class="sxs-lookup"><span data-stu-id="591c0-233">Currency</span></span></br>
- <span data-ttu-id="591c0-234">E-Mail CC</span><span class="sxs-lookup"><span data-stu-id="591c0-234">Email CC</span></span></br>
- <span data-ttu-id="591c0-235">E-Mail-Datum</span><span class="sxs-lookup"><span data-stu-id="591c0-235">Email date</span></span></br>
- <span data-ttu-id="591c0-236">E-Mail-Begrüßung</span><span class="sxs-lookup"><span data-stu-id="591c0-236">Email greeting</span></span></br>
- <span data-ttu-id="591c0-237">E-Mail-Empfänger</span><span class="sxs-lookup"><span data-stu-id="591c0-237">Email recipient</span></span></br>
- <span data-ttu-id="591c0-238">E-Mail-Absender</span><span class="sxs-lookup"><span data-stu-id="591c0-238">Email sender</span></span></br>
- <span data-ttu-id="591c0-239">E-Mail-Betreff</span><span class="sxs-lookup"><span data-stu-id="591c0-239">Email subject</span></span></br>

<span data-ttu-id="591c0-240">Die Erläuterungsbibliothek beinhaltet auch drei automatische Vorlagentypen, die mit den von Ihnen in Ihren Beispieldateien bezeichneten Daten funktionieren:</span><span class="sxs-lookup"><span data-stu-id="591c0-240">The explanation library also includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="591c0-241">Nach der Bezeichnung: Die Wörter oder Zeichen, die nach den Bezeichnungen in den Beispieldateien aufscheinen.</span><span class="sxs-lookup"><span data-stu-id="591c0-241">After label: The words or characters that occur after the labels in the example files.</span></span></br>
- <span data-ttu-id="591c0-242">Vor der Bezeichnung: Die Wörter oder Zeichen, die vor den Bezeichnungen in den Beispieldateien aufscheinen.</span><span class="sxs-lookup"><span data-stu-id="591c0-242">Before label: The words or characters that occur before the labels in the example files.</span></span></br>
- <span data-ttu-id="591c0-243">Bezeichnungen: Bis zu den ersten 10 Bezeichnungen der Beispieldateien.</span><span class="sxs-lookup"><span data-stu-id="591c0-243">Labels: Up to the first 10 labels from the example files.</span></span></br>

<span data-ttu-id="591c0-244">Als Beispiel dafür, wie automatische Vorlagen funktionieren, verwenden wir in der folgenden Beispieldatei die Erläuterungsvorlage „Vor der Bezeichnung“, die dazu beiträgt, dem Modell weitere Informationen zur Verfügung zu stellen, um eine genauere Übereinstimmung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="591c0-244">To give you an example of how automatic templates work, in the following example file, we will use the Before Label explanation template to help give the model more information to get a more accurate match.</span></span>

   ![Beispieldatei](../media/content-understanding/before-label.png)</br>

<span data-ttu-id="591c0-246">Wenn Sie die Erläuterungsvorlage „Vor der Bezeichnung“ auswählen, sucht diese zunächst nach der Gruppe an Wörtern, die vor der Bezeichnung in Ihren Beispieldateien aufscheinen.</span><span class="sxs-lookup"><span data-stu-id="591c0-246">When you select the Before Label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="591c0-247">In dem Beispiel lauten die in der ersten Beispieldatei identifizierten Wörter „Ab dem“.</span><span class="sxs-lookup"><span data-stu-id="591c0-247">In the example, the words that are identified in the first example file is "As of".</span></span>

   ![Vorlage für „Vor der Bezeichnung“](../media/content-understanding/before-label-explanation.png)</br>

<span data-ttu-id="591c0-249">Sie können <b>Hinzufügen</b> wählen, um aus der Vorlage eine Erläuterung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="591c0-249">You can select <b>Add</b> to create an explanation from the template.</span></span>  <span data-ttu-id="591c0-250">Sobald Sie weitere Beispieldateien hinzufügen, werden zusätzliche Wörter identifiziert und zur Begriffsliste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="591c0-250">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

   ![Die Bezeichnung hinzufügen](../media/content-understanding/before-label-add.png)</br>
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="591c0-252">Verwenden einer Vorlage aus der Erklärungsbibliothek</span><span class="sxs-lookup"><span data-stu-id="591c0-252">To use a template from the explanation library</span></span>

1. <span data-ttu-id="591c0-253">Wählen Sie im Abschnitt **Erklärungen** auf der Seite **Trainieren** Ihres Modells **Neu** aus und dann **Aus einer Vorlage**.</span><span class="sxs-lookup"><span data-stu-id="591c0-253">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![„Vor der Bezeichnung „hinzufügen](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="591c0-255">Wählen Sie auf der Seite **Erklärungsvorlagen** die Erklärung aus, die Sie verwenden möchten, dann wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="591c0-255">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![Auswählen einer Vorlage](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="591c0-257">Die Informationen für die von Ihnen ausgewählte Vorlage sind auf der Seite **Erklärung erstellen** dargestellt.</span><span class="sxs-lookup"><span data-stu-id="591c0-257">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="591c0-258">Bearbeiten Sie bei Bedarf den Namen der Erläuterung und fügen Sie Elemente zur Begriffsliste hinzu oder entfernen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="591c0-258">If needed, edit the explanation name and add or remove items from the phrase list.</span></span> </br> 

   ![Vorlage bearbeiten](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="591c0-260">Wählen Sie anschließend **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="591c0-260">When finished, select **Save**.</span></span>