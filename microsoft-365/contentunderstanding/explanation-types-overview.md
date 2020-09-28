---
title: Erklärungs Typen
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Weitere Informationen zu Erklärungs Typen in Microsoft SharePoint Syntex
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295848"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="800ac-103">Einführung in Erklärungs Typen</span><span class="sxs-lookup"><span data-stu-id="800ac-103">Introduction to explanation types</span></span>

<span data-ttu-id="800ac-104">Verwenden Sie Erläuterungen, um die Informationen zu definieren, die Sie bezeichnen möchten, und extrahieren Sie in Ihrem Dokument die grundlegenden Modelle für Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="800ac-104">Use explanations to help to define the information that you want to label, and extract in your document the understanding models for Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="800ac-105">Wenn Sie eine Erklärung erstellen, müssen Sie einen Erklärungs auswählen.</span><span class="sxs-lookup"><span data-stu-id="800ac-105">When you create an explanation, be sure to select an explanation type.</span></span> 

<span data-ttu-id="800ac-106">Dieser Artikel hilft Ihnen, die verschiedenen Erklärungs Typen und deren Verwendung zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="800ac-106">This article helps you understand the different explanation types and how they are used.</span></span>

   ![Erklärungs Typen](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="800ac-108">Diese Erklärungs Typen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="800ac-108">These explanation types are available:</span></span>

- <span data-ttu-id="800ac-109">**Phrase List**: Liste der Wörter, Ausdrücke, Zahlen oder andere Zeichen, die Sie in dem Dokument oder den Informationen, die Sie extrahieren möchten, verwenden können.</span><span class="sxs-lookup"><span data-stu-id="800ac-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="800ac-110">Beispielsweise ist die Textzeichenfolge **verweisenden Arzt** in allen medizinischen Empfehlungs Dokumenten, die Sie identifizieren.</span><span class="sxs-lookup"><span data-stu-id="800ac-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="800ac-111">**Musterliste**: Listen Muster von Zahlen, Buchstaben oder anderen Zeichen, mit denen Sie die extrahierten Informationen identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="800ac-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="800ac-112">Sie können beispielsweise die **Telefonnummer** des überweisenden Arztes aus dem von Ihnen identifizierten medizinischen Empfehlungs Dokument extrahieren.</span><span class="sxs-lookup"><span data-stu-id="800ac-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="800ac-113">**Proximity**: Beschreibt, wie sich nahe Erläuterungen zueinander befinden.</span><span class="sxs-lookup"><span data-stu-id="800ac-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="800ac-114">Beispielsweise wird eine Liste mit *Straßennummern* Mustern direkt vor der Liste mit den *Straßennamen* Phrasen angezeigt, wobei keine Token dazwischen liegen (Sie erfahren mehr über Token später in diesem Artikel).</span><span class="sxs-lookup"><span data-stu-id="800ac-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="800ac-115">Phrasen Liste</span><span class="sxs-lookup"><span data-stu-id="800ac-115">Phrase list</span></span>

<span data-ttu-id="800ac-116">Ein Phrase List-Erklärungs wird normalerweise verwendet, um ein Dokument über das Modell zu identifizieren und zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="800ac-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="800ac-117">Wie im Beispiel zum *verweisenden Arzt* Etikett beschrieben, handelt es sich um eine Reihe von Wörtern, Ausdrücken, Zahlen oder Zeichen, die konsistent in den zu identifizierenden Dokumenten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="800ac-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="800ac-118">Obwohl dies nicht erforderlich ist, können Sie mit ihrer Erläuterung einen besseren Erfolg erzielen, wenn sich die von Ihnen erfasste Phrase an einem konsistenten Ort in Ihrem Dokument befindet.</span><span class="sxs-lookup"><span data-stu-id="800ac-118">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="800ac-119">Beispielsweise kann die Bezeichnung des *verweisenden Arztes* im ersten Absatz des Dokuments konsistent gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="800ac-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="800ac-120">Wenn die Groß-/Kleinschreibung bei der Identifizierung ihrer Bezeichnung erforderlich ist, können Sie Sie mithilfe des Listentyps Phrasen in ihrer Erklärung angeben, indem Sie das Kontrollkästchen **exakte Groß-/Kleinschreibung** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="800ac-120">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Groß-/Kleinschreibung](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="800ac-122">Muster Listen</span><span class="sxs-lookup"><span data-stu-id="800ac-122">Pattern lists</span></span>

<span data-ttu-id="800ac-123">Ein Muster Listentyp ist besonders nützlich, wenn Sie eine Erklärung erstellen, mit der Informationen aus einem Dokument identifiziert und extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="800ac-123">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="800ac-124">Sie wird in der Regel in unterschiedlichen Formaten wie Datumsangaben, Telefonnummern oder Kreditkartennummern dargestellt.</span><span class="sxs-lookup"><span data-stu-id="800ac-124">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="800ac-125">Beispielsweise kann ein Datum in einer Reihe von verschiedenen Formaten angezeigt werden (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1, 2020 usw.).</span><span class="sxs-lookup"><span data-stu-id="800ac-125">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="800ac-126">Durch das Definieren einer Musterliste wird Ihre Erklärung effizienter, indem alle möglichen Variationen in den Daten erfasst werden, die Sie identifizieren und extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="800ac-126">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="800ac-127">Extrahieren Sie für das **Telefonnummern** Beispiel die Telefonnummer für jeden verweisenden Arzt aus allen medizinischen Empfehlungs Dokumenten, die das Modell identifiziert.</span><span class="sxs-lookup"><span data-stu-id="800ac-127">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="800ac-128">Wenn Sie die Erläuterung erstellen, wählen Sie den Muster Listentyp aus, um zu ermöglichen, dass die verschiedenen Formate, die Sie möglicherweise erwarten, zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="800ac-128">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Liste der Telefonnummernmuster](../media/content-understanding/pattern-list.png)

<span data-ttu-id="800ac-130">Wählen Sie für dieses Beispiel das Kontrollkästchen **beliebige Ziffer von 0-9 aus** .</span><span class="sxs-lookup"><span data-stu-id="800ac-130">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="800ac-131">Durch Auswahl dieser Option wird jeder 0-Wert erkannt, der in ihrer Musterliste als beliebige Ziffer von 0 bis 9 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="800ac-131">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Beliebige Ziffer aus 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="800ac-133">Wenn Sie eine Musterliste erstellen, die Textzeichen enthält, wählen Sie die Option **beliebiger Buchstabe von a-z** (CheckBox) aus.</span><span class="sxs-lookup"><span data-stu-id="800ac-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="800ac-134">Durch Auswählen dieser Option wird jedes Zeichen "a" in der Musterliste als beliebiges Zeichen von "a" bis "z" erkannt.</span><span class="sxs-lookup"><span data-stu-id="800ac-134">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="800ac-135">Wenn Sie beispielsweise eine Liste mit **Datums** Mustern erstellen und sicherstellen möchten, dass ein Datumsformat wie *Jan 1, 2020* erkannt wird, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="800ac-135">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="800ac-136">Fügen Sie Ihrer Musterliste *AAA 0, 0000* und *AAA 00, 0000* hinzu.</span><span class="sxs-lookup"><span data-stu-id="800ac-136">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="800ac-137">Stellen Sie sicher, dass **alle Buchstaben von a-z** ebenfalls ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="800ac-137">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Jeder Buchstabe von a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="800ac-139">Außerdem haben Sie die Möglichkeit, das Kontrollkästchen **nur exakte Groß-/Kleinschreibung** auszuwählen, wenn Sie in ihrer Musterliste die Groß-/Kleinschreibung Voraussetzungen haben.</span><span class="sxs-lookup"><span data-stu-id="800ac-139">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="800ac-140">Wenn Sie für das Beispiel Datum den ersten Buchstaben des Monats benötigen, der groß geschrieben werden soll, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="800ac-140">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="800ac-141">Fügen Sie Ihrer Musterliste *AAA 0, 0000* und *AAA 00, 0000* hinzu.</span><span class="sxs-lookup"><span data-stu-id="800ac-141">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="800ac-142">Stellen Sie sicher, dass auch **nur exakte Großschreibung** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="800ac-142">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Nur exakte Großschreibung](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="800ac-144">Verwenden Sie die [Erklärungs Bibliothek]() , um vorgefertigte Muster Listenvorlagen für allgemeine Muster Listen wie *Datum*, *Telefonnummer*, *Kreditkartennummer*usw. zu verwenden, anstatt eine Erläuterung der Musterliste manuell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="800ac-144">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="800ac-145">Näherung</span><span class="sxs-lookup"><span data-stu-id="800ac-145">Proximity</span></span> 

<span data-ttu-id="800ac-146">Der Näherungs Erklärungs unterstützt Ihr Modell beim Identifizieren von Daten, indem es definiert, wie nah ein anderes Datenelement ist.</span><span class="sxs-lookup"><span data-stu-id="800ac-146">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="800ac-147">In Ihrem Modell haben Sie beispielsweise zwei Erläuterungen definiert, die sowohl die *Adresse* des Kunden als auch die *Telefonnummer*bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="800ac-147">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="800ac-148">Außerdem wird feststellen, dass Kundentelefon Nummern immer vor der Nummer der Straße angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="800ac-148">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="800ac-149">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="800ac-149">Alex Wilburn</span></span><br>
<span data-ttu-id="800ac-150">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="800ac-150">555-555-5555</span></span><br>
<span data-ttu-id="800ac-151">Langgasse 18</span><span class="sxs-lookup"><span data-stu-id="800ac-151">One Microsoft Way</span></span><br>
<span data-ttu-id="800ac-152">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="800ac-152">Redmond, WA 98034</span></span><br>

<span data-ttu-id="800ac-153">Verwenden Sie die Näherungs Erklärung, um festzulegen, wie weit entfernt die Telefonnummern Erklärung darin besteht, die Nummer der Straße in Ihren Dokumenten besser zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="800ac-153">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Näherungs Erklärung](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="800ac-155">Was sind Token?</span><span class="sxs-lookup"><span data-stu-id="800ac-155">What are tokens?</span></span>

<span data-ttu-id="800ac-156">Um den Näherungs Erklärungs zu verwenden, verstehen Sie, was ein Token ist, da die Anzahl der Token ist, wie die Annäherungs Erklärung misst Abstand von einer Erklärung zur anderen.</span><span class="sxs-lookup"><span data-stu-id="800ac-156">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="800ac-157">Ein Token ist eine kontinuierliche Spanne (keine Leerzeichen oder Interpunktion) von Buchstaben und Zahlen.</span><span class="sxs-lookup"><span data-stu-id="800ac-157">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="800ac-158">Ein Leerzeichen ist kein Token.</span><span class="sxs-lookup"><span data-stu-id="800ac-158">A space is NOT a token.</span></span> <span data-ttu-id="800ac-159">Jedes Interpunktionszeichen ist ein Token.</span><span class="sxs-lookup"><span data-stu-id="800ac-159">Each punctuation character is a token.</span></span> <span data-ttu-id="800ac-160">In der folgenden Tabelle sind einige Beispiele für die Ermittlung der Anzahl von Token in einem Ausdruck aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="800ac-160">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="800ac-161">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="800ac-161">Phrase</span></span>|<span data-ttu-id="800ac-162">Anzahl von Token</span><span class="sxs-lookup"><span data-stu-id="800ac-162">Number of tokens</span></span>|<span data-ttu-id="800ac-163">Erklärung</span><span class="sxs-lookup"><span data-stu-id="800ac-163">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="800ac-164">1 </span><span class="sxs-lookup"><span data-stu-id="800ac-164">1</span></span>|<span data-ttu-id="800ac-165">Ein einzelnes Wort ohne Interpunktion oder Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="800ac-165">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="800ac-166">1 </span><span class="sxs-lookup"><span data-stu-id="800ac-166">1</span></span>|<span data-ttu-id="800ac-167">Eine Record Locator-Nummer.</span><span class="sxs-lookup"><span data-stu-id="800ac-167">A record locator number.</span></span> <span data-ttu-id="800ac-168">Es gibt möglicherweise Zahlen und Buchstaben, aber keine Interpunktion.</span><span class="sxs-lookup"><span data-stu-id="800ac-168">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="800ac-169">5 </span><span class="sxs-lookup"><span data-stu-id="800ac-169">5</span></span>|<span data-ttu-id="800ac-170">Eine Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="800ac-170">A phone number.</span></span> <span data-ttu-id="800ac-171">Jedes Interpunktionszeichen ist ein einzelnes Token  `425-555-5555` , es wären also 5 Token:</span><span class="sxs-lookup"><span data-stu-id="800ac-171">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="800ac-172">7 </span><span class="sxs-lookup"><span data-stu-id="800ac-172">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="800ac-173">Konfigurieren des Näherungs Erklärungs Typs</span><span class="sxs-lookup"><span data-stu-id="800ac-173">Configure the proximity explanation type</span></span>

<span data-ttu-id="800ac-174">Konfigurieren Sie für das Beispiel die Näherungs Einstellung, sodass der Bereich der Anzahl von Token definiert werden kann, die für die *Telefonnummern* Erklärung aus der Beschreibung der *Adresse der Straße angegeben* werden.</span><span class="sxs-lookup"><span data-stu-id="800ac-174">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="800ac-175">Sie sollten sehen, dass der Mindestbereich "0" ist, da es keine Token zwischen der Telefonnummer und der Adressnummer gibt.</span><span class="sxs-lookup"><span data-stu-id="800ac-175">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="800ac-176">Einige Telefonnummern in den Beispiel Dokumenten werden jedoch mit *(Mobile)* angehängt.</span><span class="sxs-lookup"><span data-stu-id="800ac-176">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="800ac-177">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="800ac-177">Nestor Wilke</span></span><br>
<span data-ttu-id="800ac-178">111-111-1111 (mobil)</span><span class="sxs-lookup"><span data-stu-id="800ac-178">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="800ac-179">Langgasse 18</span><span class="sxs-lookup"><span data-stu-id="800ac-179">One Microsoft Way</span></span><br>
<span data-ttu-id="800ac-180">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="800ac-180">Redmond, WA 98034</span></span><br>

<span data-ttu-id="800ac-181">Es gibt drei Token in *(Mobile)*:</span><span class="sxs-lookup"><span data-stu-id="800ac-181">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="800ac-182">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="800ac-182">Phrase</span></span>|<span data-ttu-id="800ac-183">Anzahl von Token</span><span class="sxs-lookup"><span data-stu-id="800ac-183">Token count</span></span>|
|--|--|
|<span data-ttu-id="800ac-184">(</span><span class="sxs-lookup"><span data-stu-id="800ac-184">(</span></span>|<span data-ttu-id="800ac-185">1 </span><span class="sxs-lookup"><span data-stu-id="800ac-185">1</span></span>|
|<span data-ttu-id="800ac-186">Mobile</span><span class="sxs-lookup"><span data-stu-id="800ac-186">mobile</span></span>|<span data-ttu-id="800ac-187">2 </span><span class="sxs-lookup"><span data-stu-id="800ac-187">2</span></span>|
|<span data-ttu-id="800ac-188">)</span><span class="sxs-lookup"><span data-stu-id="800ac-188">)</span></span>|<span data-ttu-id="800ac-189">3 </span><span class="sxs-lookup"><span data-stu-id="800ac-189">3</span></span>|

<span data-ttu-id="800ac-190">Konfigurieren Sie die Näherungs Einstellung für einen Bereich von 0 bis 3.</span><span class="sxs-lookup"><span data-stu-id="800ac-190">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Näherungs Beispiel](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a><span data-ttu-id="800ac-192">Verwenden der Erklärungs Bibliothek</span><span class="sxs-lookup"><span data-stu-id="800ac-192">Use the explanation library</span></span>

<span data-ttu-id="800ac-193">Sie können zwar manuell verschiedene Muster Listenwerte für Ihre Erklärung hinzufügen, aber es ist viel einfacher, die vordefinierten Vorlagen zu verwenden, die Ihnen in der Erklärungs Bibliothek zur Verfügung gestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="800ac-193">While you can manually add various pattern list values for your explanation, it's much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="800ac-194">Verwenden Sie beispielsweise anstelle des manuellen Hinzufügens aller Variationen für *Date*die Muster Listenvorlage für *Date*, die bereits eine Reihe von Muster Listenwerten enthält:</span><span class="sxs-lookup"><span data-stu-id="800ac-194">For example, instead of manually adding all the variations for *Date*, use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Erklärungs Bibliothek](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="800ac-196">Die Erklärungs Bibliothek enthält eine Reihe häufig verwendeter Muster Listen Erläuterungen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="800ac-196">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="800ac-197">Datum</span><span class="sxs-lookup"><span data-stu-id="800ac-197">Date</span></span></br>
- <span data-ttu-id="800ac-198">Datum (numerisch)</span><span class="sxs-lookup"><span data-stu-id="800ac-198">Date (numeric)</span></span></br>
- <span data-ttu-id="800ac-199">Zeit</span><span class="sxs-lookup"><span data-stu-id="800ac-199">Time</span></span></br>
- <span data-ttu-id="800ac-200">Zahl</span><span class="sxs-lookup"><span data-stu-id="800ac-200">Number</span></span></br>
- <span data-ttu-id="800ac-201">Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="800ac-201">Phone number</span></span></br>
- <span data-ttu-id="800ac-202">PLZ</span><span class="sxs-lookup"><span data-stu-id="800ac-202">Zip code</span></span></br>
- <span data-ttu-id="800ac-203">Erstes Wort des Satzes</span><span class="sxs-lookup"><span data-stu-id="800ac-203">First word of sentence</span></span></br>
- <span data-ttu-id="800ac-204">Kreditkarte</span><span class="sxs-lookup"><span data-stu-id="800ac-204">Credit card</span></span></br>
- <span data-ttu-id="800ac-205">Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="800ac-205">Social security number</span></span></br>

<span data-ttu-id="800ac-206">Beachten Sie, dass die Erklärungs Bibliothek auch Vorlagen für Phrase List-Erläuterungen enthält, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="800ac-206">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="800ac-207">Ende des Satzes</span><span class="sxs-lookup"><span data-stu-id="800ac-207">End of sentence</span></span>
- <span data-ttu-id="800ac-208">Währung</span><span class="sxs-lookup"><span data-stu-id="800ac-208">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="800ac-209">So verwenden Sie eine Vorlage aus der Erklärungs Bibliothek</span><span class="sxs-lookup"><span data-stu-id="800ac-209">To use a template from the explanation library</span></span>

1. <span data-ttu-id="800ac-210">Wählen Sie im Abschnitt **Erläuterungen** des **Zuges** Ihres Modells die Option **neu**aus, und wählen Sie dann **aus einer Vorlage aus**.</span><span class="sxs-lookup"><span data-stu-id="800ac-210">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Aus Vorlage erstellen](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="800ac-212">Wählen Sie auf der Seite **Erklärungs Vorlagen** die Erklärung aus, die Sie verwenden möchten, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="800ac-212">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Auswählen einer Vorlage](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="800ac-214">Die Informationen für die ausgewählte Vorlage werden auf der Seite **Erklärung erstellen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="800ac-214">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="800ac-215">Bearbeiten Sie bei Bedarf den Namen der Erklärung, und fügen Sie Elemente aus der Liste Muster hinzu oder entfernen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="800ac-215">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Vorlage bearbeiten](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="800ac-217">Wenn Sie fertig sind, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="800ac-217">When finished, select **Save**.</span></span>
