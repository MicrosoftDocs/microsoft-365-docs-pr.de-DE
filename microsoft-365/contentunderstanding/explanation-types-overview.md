---
title: Erklärungstypen in Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Weitere Informationen zur Begriffsliste, regulärem Ausdruck und Arten der Näherungserklärung in Microsoft SharePoint Syntex.
ms.openlocfilehash: 8748b2fd33e20cf7e402d499db05f1f6722e735a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770865"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="2d7e9-103">Erklärungstypen in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="2d7e9-103">Explanation types in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="2d7e9-104">Erklärungen werden verwendet, um die Informationen zu definieren, die Sie in Ihren Document Understanding-Modellen in Microsoft SharePoint Syntex bezeichnen und extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="2d7e9-105">Wenn Sie eine Erklärung erstellen, müssen Sie einen Erklärungstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-105">When you create an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="2d7e9-106">Dieser Artikel hilft Ihnen dabei, die verschiedenen Erklärungstypen zu verstehen, und wie sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-106">This article helps you understand the different explanation types and how they're used.</span></span>

![Screenshot des Bereichs „Erstellen einer Erklärung“, der die drei Erklärungstypen zeigt.](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="2d7e9-108">Diese Erklärungstypen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-108">These explanation types are available:</span></span>

- <span data-ttu-id="2d7e9-109">[**Begriffsliste**](#phrase-list): Liste von Wörtern, Phrasen, Zahlen oder anderen Zeichen, die Sie im Dokument oder in der Information, die Sie extrahieren, verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-109">[**Phrase list**](#phrase-list): List of words, phrases, numbers, or other characters you can use in the document or information that you're extracting.</span></span> <span data-ttu-id="2d7e9-110">Zum Beispiel ist die Textzeichenfolge *Überweisender Arzt* in allen Dokumenten „Ärztliche Überweisung“ enthalten, die Sie identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-110">For example, the text string *referring doctor* is in all Medical Referral documents you're identifying.</span></span> <span data-ttu-id="2d7e9-111">Oder die *Telefonnummer* des überweisenden Arztes aus allen von Ihnen identifizierten Dokumenten „Ärztliche Überweisung“.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-111">Or the *phone number* of the referring doctor from all Medical Referral documents that you're identifying.</span></span>

- <span data-ttu-id="2d7e9-112">[**Regulärer Ausdruck**](#regular-expression): Verwendet eine Notation für den Mustervergleich, um bestimmte Zeichenmuster zu finden.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-112">[**Regular expression**](#regular-expression): Uses a pattern-matching notation to find specific character patterns.</span></span> <span data-ttu-id="2d7e9-113">Beispielsweise können Sie einen regulären Ausdruck verwenden, um alle Instanzen eines *E-Mail-Adressen*-Musters in einer Gruppe von Dokumenten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-113">For example, you can use a regular expression to find all instances of an *email address* pattern in a set of documents.</span></span>

- <span data-ttu-id="2d7e9-114">[**Näherung**](#proximity): Beschreibt, wie nahe die Erklärungen beieinander liegen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-114">[**Proximity**](#proximity): Describes how close explanations are to each other.</span></span> <span data-ttu-id="2d7e9-115">Eine *Straßennummern*-Begriffsliste wird beispielsweise direkt vor der *Straßennamen*-Begriffsliste ohne dazwischen liegende Token angezeigt (Informationen zu Token finden Sie weiter unten in diesem Artikel).</span><span class="sxs-lookup"><span data-stu-id="2d7e9-115">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="2d7e9-116">Die Verwendung des Näherungstyps erfordert, dass Sie mindestens zwei Erklärungen in Ihrem Modell haben, ansonsten die Option deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-116">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 

## <a name="phrase-list"></a><span data-ttu-id="2d7e9-117">Begriffsliste</span><span class="sxs-lookup"><span data-stu-id="2d7e9-117">Phrase list</span></span>

<span data-ttu-id="2d7e9-118">Der Erklärungstyp "Begriffsliste" wird normalerweise verwendet, um ein Dokument durch Ihr Modell zu identifizieren und zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-118">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="2d7e9-119">Wie im Beispiel der Bezeichnung *Überweisender Arzt* beschrieben, handelt es sich dabei um eine Kette von Wörtern, Phrasen, Zahlen oder Zeichen, die in den Dokumenten, die Sie identifizieren, konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-119">As described in the *referring doctor* label example, it's a string of words, phrases, numbers, or characters that is consistently in the documents that you're identifying.</span></span>

<span data-ttu-id="2d7e9-120">Auch wenn dies keine Voraussetzung ist, können Sie mit Ihrer Erklärung einen besseren Erfolg erzielen, wenn die Phrase, die Sie erfassen, sich an einer konsistenten Stelle in Ihrem Dokument befindet.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-120">While not a requirement, you can achieve better success with your explanation if the phrase you're capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="2d7e9-121">Beispielsweise könnte sich die Bezeichnung *Überweisender Arzt* durchgängig im ersten Absatz des Dokuments befinden.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-121">For example, the *referring doctor* label might be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="2d7e9-122">Sie können auch die Option **[Konfigurieren, wo Begriffe im Dokument vorkommen](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** in den erweiterten Einstellung verwenden, um bestimmte Bereiche auszuwählen, in denen sich der Begriff befindet, insbesondere wenn die Möglichkeit besteht, dass der Begriff an mehreren Stellen in Ihrem Dokument vorkommt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-122">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there's a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="2d7e9-123">Wenn die Groß-/Kleinschreibung bei der Identifizierung Ihrer Bezeichnung beachtet werden muss, können Sie dies in Ihrer Erklärung mit dem Typ "Begriffsliste" angeben, indem Sie das Kontrollkästchen **Nur exakte Groß-/Kleinschreibung** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-123">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![Unterscheidung nach Groß-/Kleinschreibung](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="2d7e9-125">Ein Begriffstyp ist besonders nützlich, wenn Sie eine Erklärung erstellen, die Informationen in verschiedenen Formaten wie Datum, Telefonnummer und Kreditkartennummer identifiziert und extrahiert.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-125">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="2d7e9-126">Ein Datum kann beispielsweise in vielen verschiedenen Formaten angezeigt werden (1/1/2020, 1-1-2020, 01/01/20, 01.01.2020 oder 1. Jan. 2020).</span><span class="sxs-lookup"><span data-stu-id="2d7e9-126">For example, a date can be displayed in many different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, or Jan 1,2020).</span></span> <span data-ttu-id="2d7e9-127">Durch das Definieren einer Begriffsliste wird Ihre Erklärung effizienter, indem mögliche Abweichungen in den Daten, die Sie identifizieren und extrahieren möchten, erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-127">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you're trying to identify and extract.</span></span> 

<span data-ttu-id="2d7e9-128">Für das Beispiel *Telefonnummer* extrahieren Sie die Telefonnummer für jeden überweisenden Arzt aus allen Dokumenten „Ärztliche Überweisung“, die das Modell identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-128">For the *phone number* example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="2d7e9-129">Geben Sie beim Erstellen der Erklärung die verschiedenen Formate ein, in denen eine Telefonnummer möglicherweise in Ihrem Dokument angezeigt wird, damit Sie mögliche Abweichungen erfassen können.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-129">When you create the explanation, type the different formats a phone number might display in your document so that you're able to capture possible variations.</span></span> 

![Begriffsmuster von Telefonnummern](../media/content-understanding/pattern-list.png)

<span data-ttu-id="2d7e9-131">In diesem Beispiel aktivieren Sie unter **Erweiterte Einstellungen** das Kontrollkästchen **Beliebige Ziffer von 0-9**, um zu erkennen, dass jeder in Ihrer Begriffsliste verwendete "0" -Wert eine beliebige Ziffer von 0 bis 9 ist.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-131">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![Beliebige Ziffer von 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="2d7e9-133">Wenn Sie eine Begriffsliste erstellen, die Textzeichen enthält, aktivieren Sie das Kontrollkästchen **Beliebiger Buchstabe von a-z**, um zu erkennen, dass jedes in der Begriffsliste verwendete "a" -Zeichen ein beliebiges Zeichen von "a" bis "z" ist.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-133">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="2d7e9-134">Wenn Sie beispielsweise eine **Datum**-Begriffsliste erstellen und sicherstellen möchten, dass ein Datumsformat wie der *1. Januar 2020* erkannt wird, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-134">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>

- <span data-ttu-id="2d7e9-135">Fügen Sie Ihrer Begriffsliste *aaa 0, 0000* und *aaa 00, 0000* hinzu.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="2d7e9-136">Stellen Sie sicher, dass auch **Beliebiger Buchstabe von a-z** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-136">Make sure that **Any letter from a-z** is also selected.</span></span>

![Beliebiger Buchstabe von a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="2d7e9-138">Wenn Ihre Begriffsliste Anforderungen an die Groß-/Kleinschreibung hat, können Sie das Kontrollkästchen **Nur genaue Groß-/Kleinschreibung** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-138">If you have capitalization requirements in your phrase list, you can select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="2d7e9-139">Wenn für das Beispiel „Datum“ der erste Buchstabe des Monats groß geschrieben werden muss, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-139">For the date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="2d7e9-140">Fügen Sie Ihrer Begriffsliste *Aaa 0, 0000* und *Aaa 00, 0000* hinzu.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="2d7e9-141">Stellen Sie sicher, dass auch **Nur genaue Groß-/Kleinschreibung** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-141">Make sure that **Only exact capitalization** is also selected.</span></span>

![Nur genaue Groß-/Kleinschreibung](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="2d7e9-143">Anstatt manuell eine Erklärung für die Begriffsliste zu erstellen, verwenden Sie die [Erklärungsbibliothek](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates), um Begriffslistenvorlagen für eine allgemeine Begriffsliste wie *Datum*, *Telefonnummer* oder *Kreditkartennummer* zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-143">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, or *credit card number*.</span></span>

## <a name="regular-expression"></a><span data-ttu-id="2d7e9-144">Regulärer Ausdruck</span><span class="sxs-lookup"><span data-stu-id="2d7e9-144">Regular expression</span></span>

<span data-ttu-id="2d7e9-145">Ein Erklärungstyp für einen regulären Ausdruck erlaubt Ihnen das Erstellen von Mustern, die Ihnen beim Suchen und Identifizieren bestimmter Textzeichenfolgen in Dokumenten helfen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-145">A regular expression explanation type allows you to create patterns that help find and identify certain text strings in documents.</span></span> <span data-ttu-id="2d7e9-146">Sie können reguläre Ausdrücke verwenden, um große Textmengen schnell zu analysieren zum:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-146">You can use regular expressions to quickly parse large amounts of text to:</span></span>

- <span data-ttu-id="2d7e9-147">Suchen bestimmter Zeichenmuster.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-147">Find specific character patterns.</span></span>
- <span data-ttu-id="2d7e9-148">Validieren von Text, um sicherzustellen, dass er mit einem vordefinierten Muster übereinstimmt (beispielsweise eine E-Mail-Adresse).</span><span class="sxs-lookup"><span data-stu-id="2d7e9-148">Validate text to ensure that it matches a predefined pattern (such as an email address).</span></span>
- <span data-ttu-id="2d7e9-149">Extrahieren, bearbeiten, ersetzen oder löschen von Teilen der Textzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-149">Extract, edit, replace, or delete text substrings.</span></span>

<span data-ttu-id="2d7e9-150">Ein regulärer Ausdruckstyp ist besonders nützlich, wenn Sie eine Erklärung erstellen, die Informationen mit ähnlichen Formaten wie E-Mail-Adressen, Bankkontonummern oder URLs identifiziert und extrahiert.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-150">A regular expression type is especially useful when you create an explanation that identifies and extracts information in similar formats, such as email addresses, bank account numbers, or URLs.</span></span> <span data-ttu-id="2d7e9-151">Zum Beispiel wird eine E-Mail-Adresse, wie megan@contoso.com, in einem bestimmten Muster angezeigt („megan“ ist der erste Teil und „com“ ist der letzte Teil).</span><span class="sxs-lookup"><span data-stu-id="2d7e9-151">For example, an email address, such as megan@contoso.com, is displayed in a certain pattern ("megan" is the first part, and "com" is the last part).</span></span> 

<span data-ttu-id="2d7e9-152">Der reguläre Ausdruck für eine E-Mail-Adresse ist: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-152">The regular expression for an email address is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span></span>

<span data-ttu-id="2d7e9-153">Der Ausdruck besteht aus fünf Teilen in dieser Reihenfolge:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-153">This expression consists of five parts, in this order:</span></span>

1. <span data-ttu-id="2d7e9-154">Eine beliebige Anzahl der folgenden Sonderzeichen: </span><span class="sxs-lookup"><span data-stu-id="2d7e9-154">Any amount of the following characters:</span></span>

   <span data-ttu-id="2d7e9-p112">a. Buchstaben von a bis z</span><span class="sxs-lookup"><span data-stu-id="2d7e9-p112">a. Letters from a to z</span></span>

   <span data-ttu-id="2d7e9-p113">b. Zahlen von 0–9</span><span class="sxs-lookup"><span data-stu-id="2d7e9-p113">b. Numbers from 0-9</span></span>

   <span data-ttu-id="2d7e9-p114">c. Punkt, Unterstrich, Prozent oder Gedankenstrich</span><span class="sxs-lookup"><span data-stu-id="2d7e9-p114">c. Period, underscore, percent, or dash</span></span>

2. <span data-ttu-id="2d7e9-161">Das Symbol „@“</span><span class="sxs-lookup"><span data-stu-id="2d7e9-161">The @ symbol</span></span>

3. <span data-ttu-id="2d7e9-162">Eine beliebige Anzahl der gleichen Zeichen wie im ersten Teil der E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="2d7e9-162">Any amount of the same characters as the first part of the email address</span></span>

4. <span data-ttu-id="2d7e9-163">Ein Punkt</span><span class="sxs-lookup"><span data-stu-id="2d7e9-163">A period</span></span>

5. <span data-ttu-id="2d7e9-164">Zwei bis sechs Buchstaben</span><span class="sxs-lookup"><span data-stu-id="2d7e9-164">Two to six letters</span></span>

<span data-ttu-id="2d7e9-165">So fügen Sie einen Erklärungstyp für einen regulären Ausdruck hinzu:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-165">To add a regular expression explanation type:</span></span>

1. <span data-ttu-id="2d7e9-166">Wählen Sie aus dem Bereich **Erstellen einer Erklärung** unter **Erklärungstyp** die Option **Regulärer Ausdruck** aus.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-166">From the **Create an explanation** panel, under **Explanation type**, select **Regular expression**.</span></span>

   ![Screenshot zeigt den Bereich „Erstellen einer Erklärung“ mit der Option „Regulärer Ausdruck“ ausgewählt.](../media/content-understanding/create-regular-expression.png)

2. <span data-ttu-id="2d7e9-168">Sie können entweder einen Ausdruck im Textfeld **Regulärer Ausdruck** eingeben, oder **Hinzufügen eines regulären Ausdrucks aus einer Vorlage** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-168">You can either type an expression in the **Regular expression** text box or select **Add a regular expression from a template**.</span></span>

   <span data-ttu-id="2d7e9-169">Wenn Sie einen regulären Ausdruck mittels einer Vorlage hinzufügen, wird der Name und der reguläre Ausdruck automatisch dem Textfeld hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-169">When you add a regular expression by using a template, it automatically adds the name and the regular expression to the text box.</span></span> <span data-ttu-id="2d7e9-170">Wenn Sie beispielsweise die Vorlage **E-Mail-Adresse** auswählen, wird der Bereich **Erstellen einer Erklärung** ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-170">For example, if you choose the **Email address** template, the **Create an explanation** panel will be populated.</span></span>

   ![Screenshot zeigt den Bereich „Erstellen einer Erklärung“ mit der Vorlage „E-Mail-Adresse“ angewendet.](../media/content-understanding/create-regular-expression-email.png)

### <a name="limitations"></a><span data-ttu-id="2d7e9-172">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2d7e9-172">Limitations</span></span>

<span data-ttu-id="2d7e9-173">Die nachfolgende Tabelle zeigt Inline-Zeichenoptionen, die derzeit für Muster eines regulären Ausdrucks nicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-173">The following table shows inline character options that currently are not available for use in regular expression patterns.</span></span> 

|<span data-ttu-id="2d7e9-174">Option</span><span class="sxs-lookup"><span data-stu-id="2d7e9-174">Option</span></span>  |<span data-ttu-id="2d7e9-175">Status</span><span class="sxs-lookup"><span data-stu-id="2d7e9-175">State</span></span>  |<span data-ttu-id="2d7e9-176">Aktuelle Funktionalität</span><span class="sxs-lookup"><span data-stu-id="2d7e9-176">Current functionality</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2d7e9-177">Unterscheidung nach Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="2d7e9-177">Case sensitivity</span></span> | <span data-ttu-id="2d7e9-178">Derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-178">Currently not supported.</span></span> | <span data-ttu-id="2d7e9-179">Bei allen durchgeführten Aktionen wird nicht nach Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-179">All matches performed are case-insensitive.</span></span>  |
|<span data-ttu-id="2d7e9-180">Zeilenanker</span><span class="sxs-lookup"><span data-stu-id="2d7e9-180">Line anchors</span></span>     | <span data-ttu-id="2d7e9-181">Derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-181">Currently not supported.</span></span> | <span data-ttu-id="2d7e9-182">Es konnte keine spezifische Position in einer Zeichenfolge bestimmt werden, an der eine Übereinstimmung erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-182">Unable to specify a specific position in a string where a match must occur.</span></span>   |

## <a name="proximity"></a><span data-ttu-id="2d7e9-183">Näherung</span><span class="sxs-lookup"><span data-stu-id="2d7e9-183">Proximity</span></span> 

<span data-ttu-id="2d7e9-184">Der Erklärungstyp "Näherung" hilft Ihrem Modell bei der Identifizierung von Daten, indem er definiert, wie nahe ein anderes Datenelement an ihm liegt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-184">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="2d7e9-185">Beispielsweise haben Sie in Ihrem Modell zwei Erklärungen definiert, die sowohl die *Straßennummer* als auch die *Telefonnummer* des Kunden bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-185">For example, in your model say you have defined two explanations that label both the customer *street address number* and *phone number*.</span></span> 

<span data-ttu-id="2d7e9-186">Beachten Sie, dass die Telefonnummern des Kunden immer vor der Straßennummer steht.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-186">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="2d7e9-187">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="2d7e9-187">Alex Wilburn</span></span><br>
<span data-ttu-id="2d7e9-188">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="2d7e9-188">555-555-5555</span></span><br>
<span data-ttu-id="2d7e9-189">Langgasse 18</span><span class="sxs-lookup"><span data-stu-id="2d7e9-189">One Microsoft Way</span></span><br>
<span data-ttu-id="2d7e9-190">54123 Münchfeld</span><span class="sxs-lookup"><span data-stu-id="2d7e9-190">Redmond, WA 98034</span></span><br>

<span data-ttu-id="2d7e9-191">Verwenden Sie die Näherungserklärung, um festzulegen, wie weit die Erklärung "Telefonnummer" entfernt ist, um die Straßennummer in Ihren Dokumenten besser identifizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-191">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![Näherungserklärung](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="2d7e9-193">Was sind Token?</span><span class="sxs-lookup"><span data-stu-id="2d7e9-193">What are tokens?</span></span>

<span data-ttu-id="2d7e9-194">Um den Erklärungstyp „Näherung“ verwenden zu können, müssen Sie verstehen, was ein Token ist.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-194">To use the proximity explanation type, you need to understand what a token is.</span></span> <span data-ttu-id="2d7e9-195">Die Anzahl der Token gibt an, wie die Näherungserklärung den Abstand von einer Erklärung zur anderen misst.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-195">The number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="2d7e9-196">Ein Token ist eine kontinuierliche Reihe (ohne Leerzeichen oder Interpunktionen) von Buchstaben und Zahlen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-196">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="2d7e9-197">Die folgende Tabelle zeigt Beispiele, wie die Anzahl der Token in einer Phrase ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-197">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="2d7e9-198">Phrase</span><span class="sxs-lookup"><span data-stu-id="2d7e9-198">Phrase</span></span>|<span data-ttu-id="2d7e9-199">Anzahl von Token</span><span class="sxs-lookup"><span data-stu-id="2d7e9-199">Number of tokens</span></span>|<span data-ttu-id="2d7e9-200">Erklärung</span><span class="sxs-lookup"><span data-stu-id="2d7e9-200">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="2d7e9-201">1</span><span class="sxs-lookup"><span data-stu-id="2d7e9-201">1</span></span>|<span data-ttu-id="2d7e9-202">Ein einzelnes Wort ohne Interpunktionszeichen oder Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-202">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="2d7e9-203">1</span><span class="sxs-lookup"><span data-stu-id="2d7e9-203">1</span></span>|<span data-ttu-id="2d7e9-p118">Eine Datensatz-Locator-Nummer. Diese kann Zahlen und Buchstaben beinhalten, hat jedoch keine Interpunktion.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-p118">A record locator number. It might include numbers and letters, but doesn't have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="2d7e9-206">5</span><span class="sxs-lookup"><span data-stu-id="2d7e9-206">5</span></span>|<span data-ttu-id="2d7e9-207">Eine Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-207">A phone number.</span></span> <span data-ttu-id="2d7e9-208">Jedes Interpunktionszeichen ist ein einzelnes Token, also ist `425-555-5555` 5 Tokens:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-208">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="2d7e9-209">7</span><span class="sxs-lookup"><span data-stu-id="2d7e9-209">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="2d7e9-210">Konfigurieren des Erklärungstyps "Näherung"</span><span class="sxs-lookup"><span data-stu-id="2d7e9-210">Configure the proximity explanation type</span></span>

<span data-ttu-id="2d7e9-211">Konfigurieren Sie für das Beispiel die Näherungseinstellung, um den Bereich der Anzahl der Token in der *Telefonnummer*-Erklärung aus der *Straßennummer*-Erklärung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-211">For the example, configure the proximity setting to define the range of the number of tokens in the *phone number* explanation from the *street address number* explanation.</span></span> <span data-ttu-id="2d7e9-212">Beachten sie, dass der Mindestbereich „0“ ist, da es keine Token zwischen der Telefonnummer und der Straßenadressnummer gibt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-212">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="2d7e9-213">Einige Telefonnummern in den Beispieldokumenten sind jedoch mit *(Mobil)* ergänzt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-213">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="2d7e9-214">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="2d7e9-214">Nestor Wilke</span></span><br>
<span data-ttu-id="2d7e9-215">111-111-1111 (Mobil)</span><span class="sxs-lookup"><span data-stu-id="2d7e9-215">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="2d7e9-216">Langgasse 18</span><span class="sxs-lookup"><span data-stu-id="2d7e9-216">One Microsoft Way</span></span><br>
<span data-ttu-id="2d7e9-217">54123 Münchfeld</span><span class="sxs-lookup"><span data-stu-id="2d7e9-217">Redmond, WA 98034</span></span><br>

<span data-ttu-id="2d7e9-218">Es gibt drei Token in *(Mobil)*:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-218">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="2d7e9-219">Phrase</span><span class="sxs-lookup"><span data-stu-id="2d7e9-219">Phrase</span></span>|<span data-ttu-id="2d7e9-220">Tokenzahl</span><span class="sxs-lookup"><span data-stu-id="2d7e9-220">Token count</span></span>|
|--|--|
|<span data-ttu-id="2d7e9-221">(</span><span class="sxs-lookup"><span data-stu-id="2d7e9-221">(</span></span>|<span data-ttu-id="2d7e9-222">1</span><span class="sxs-lookup"><span data-stu-id="2d7e9-222">1</span></span>|
|<span data-ttu-id="2d7e9-223">Mobil</span><span class="sxs-lookup"><span data-stu-id="2d7e9-223">mobile</span></span>|<span data-ttu-id="2d7e9-224">2</span><span class="sxs-lookup"><span data-stu-id="2d7e9-224">2</span></span>|
|<span data-ttu-id="2d7e9-225">)</span><span class="sxs-lookup"><span data-stu-id="2d7e9-225">)</span></span>|<span data-ttu-id="2d7e9-226">3</span><span class="sxs-lookup"><span data-stu-id="2d7e9-226">3</span></span>|

<span data-ttu-id="2d7e9-227">Konfigurieren Sie die Einstellung für die Näherung so, dass sie einen Wert von 0 bis 3 aufweist.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-227">Configure the proximity setting to have a range of 0 through 3.</span></span>

![Beispiel einer Näherung](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="2d7e9-229">Konfigurieren Sie, wo Ausdrücke im Dokument vorkommen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-229">Configure where phrases occur in the document</span></span>

<span data-ttu-id="2d7e9-230">Wenn Sie eine Erklärung erstellen, wird standardmäßig das gesamte Dokument nach dem Ausdruck durchsucht, den Sie extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-230">When you create an explanation, by default the entire document is searched for the phrase you're trying to extract.</span></span> <span data-ttu-id="2d7e9-231">Sie können jedoch die erweiterte Einstellung **Wo diese Ausdrücke vorkommen** verwenden, um eine bestimmte Stelle im Dokument zu isolieren, an der ein Ausdruck vorkommt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-231">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="2d7e9-232">Diese Einstellung ist in Situationen hilfreich, in denen ähnliche Instanzen eines Ausdrucks möglicherweise an einer anderen Stelle im Dokument auftreten und Sie sicherstellen möchten, dass der richtige Ausdruck ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-232">This setting is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span>

<span data-ttu-id="2d7e9-233">In unserem Beispiel für das Dokument „Ärztliche Überweisung“ wird der *überweisende Arzt* immer im ersten Absatz des Dokuments erwähnt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-233">Referring to our Medical Referral document example, the *referring doctor* is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="2d7e9-234">Mit der Einstellung **Wo diese Ausdrücke vorkommen** können Sie in diesem Beispiel Ihre Erklärung so konfigurieren, dass nach dieser Bezeichnung nur im Anfangsabschnitt des Dokuments oder an einer anderen Stelle gesucht wird, an der sie möglicherweise vorkommt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-234">With the **Where these phrases occur** setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![Einstellung „Wo diese Ausdrücke vorkommen“](../media/content-understanding/phrase-location.png)

<span data-ttu-id="2d7e9-236">Sie können für diese Einstellung die folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-236">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="2d7e9-237">An beliebiger Stelle in der Datei: Es wird das gesamte Dokument nach dem Ausdruck durchsucht.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-237">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="2d7e9-238">Anfang der Datei: Das Dokument wird vom Anfang bis zur Position des Ausdrucks durchsucht.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-238">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![Anfang der Datei](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="2d7e9-240">Im Viewer können Sie das Auswahlfeld manuell anpassen, um die Position einzugeben, an der die Phase erscheint.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-240">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="2d7e9-241">Der Wert **Endposition** wird aktualisiert und zeigt die Anzahl der Token an, die im ausgewählten Bereich enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-241">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="2d7e9-242">Sie können den Wert der **Endposition** auch aktualisieren, um den ausgewählten Bereich anzupassen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-242">You can update the **End position** value as well to adjust the selected area.</span></span>

   ![Anfang des Dateipositionsfelds](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="2d7e9-244">Ende der Datei: Das Dokument wird vom Ende bis zur Position des Ausdrucks durchsucht.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-244">End of the file: The document is searched from the end to the phrase location.</span></span>

   ![Ende der Datei](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="2d7e9-246">Im Viewer können Sie das Auswahlfeld manuell anpassen, um die Position einzugeben, an der die Phase erscheint.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-246">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="2d7e9-247">Der Wert **Startposition** wird aktualisiert und zeigt die Anzahl der Token an, die im ausgewählten Bereich enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-247">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="2d7e9-248">Sie können den Wert der Startposition auch aktualisieren, um den ausgewählten Bereich anzupassen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-248">You can update the Starting position value as well to adjust the selected area.</span></span>

   ![Ende des Dateipositionsfelds](../media/content-understanding/end-box.png)

- <span data-ttu-id="2d7e9-250">Benutzerdefiniert: Das Dokument wird innerhalb eines bestimmten Bereichs nach der Position des Ausdrucks durchsucht.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-250">Custom range: The document is searched within a specified range for the phrase location.</span></span>

   ![Benutzerdefinierter Bereich](../media/content-understanding/custom-file.png)

    <span data-ttu-id="2d7e9-252">Im Viewer können Sie das Auswahlfeld manuell anpassen, um die Position einzugeben, an der die Phase erscheint.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-252">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="2d7e9-253">Für diese Einstellung müssen Sie je eine Position **Start** und **Ende** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-253">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="2d7e9-254">Diese Werte stellen die Anzahl der Token ab dem Anfang des Dokuments dar.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-254">These values represent the number of tokens from the beginning of the document.</span></span> <span data-ttu-id="2d7e9-255">Sie können diese Werte zwar manuell eingeben, doch ist es einfacher, das Auswahlfeld im Viewer manuell anzupassen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-255">While you can manually enter in these values, it's easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="2d7e9-256">Verwenden von Erklärungsvorlagen</span><span class="sxs-lookup"><span data-stu-id="2d7e9-256">Use explanation templates</span></span>

<span data-ttu-id="2d7e9-257">Während Sie manuell verschiedene Begriffslistenwerte für Ihre Erklärung hinzufügen können, kann es einfacher sein, die Vorlagen zu verwenden, die Ihnen in der Erklärungsbibliothek zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-257">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="2d7e9-258">Statt beispielsweise alle Varianten für *Datum* manuell hinzuzufügen, können Sie die Begriffslistenvorlage für *Datum* verwenden, weil diese bereits viele Begriffslistenwerte enthält:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-258">For example, instead of manually adding all the variations for *date*, you can use the phrase list template for *date* because it already includes many phrase lists values:</span></span>

![Erklärungsbibliothek](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="2d7e9-260">Die Erklärungsbibliothek enthält häufig verwendete Erklärungen für *Begriffslisten*, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-260">The explanation library includes commonly used *phrase list* explanations, including:</span></span>

- <span data-ttu-id="2d7e9-261">Datum: Kalenderdaten, alle Formate.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-261">Date: Calendar dates, all formats.</span></span> <span data-ttu-id="2d7e9-262">Enthält Text und Zahlen (z. B. „Dec 9, 2020“).</span><span class="sxs-lookup"><span data-stu-id="2d7e9-262">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="2d7e9-263">Datum (numerisch): Kalenderdaten, alle Formate.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-263">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="2d7e9-264">Beinhaltet Zahlen (zum Beispiel 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="2d7e9-264">Includes numbers (for example, 1-11-2020).</span></span>
- <span data-ttu-id="2d7e9-265">Zeit: 12- und 24-Stunden-Format.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-265">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="2d7e9-266">Zahl: Positive und negative Zahlen bis zu zwei Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-266">Number: Positive and negative numbers up to two decimals.</span></span> 
- <span data-ttu-id="2d7e9-267">Prozentsatz: Eine Liste von Mustern, die einen Prozentsatz darstellen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-267">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="2d7e9-268">Beispielsweise 1 %, 11 %, 100 % oder 11.11 %.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-268">For example, 1%, 11%, 100%, or 11.11%.</span></span>
- <span data-ttu-id="2d7e9-269">Rufnummer: Gängige amerikanische und internationale Formate.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-269">Phone number: Common US and International formats.</span></span> <span data-ttu-id="2d7e9-270">Beispielsweise 000 000 0000, 000-000-0000, (000)000-0000 oder (000) 000-0000.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-270">For example, 000 000 0000, 000-000-0000, (000)000-0000, or (000) 000-0000.</span></span>
- <span data-ttu-id="2d7e9-271">Postleitzahl: Vereinigte Staaten-Postleitzahlenformate.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-271">Zip code: US Zip code formats.</span></span> <span data-ttu-id="2d7e9-272">Zum Beispiel, 11111, 11111-1111.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-272">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="2d7e9-273">Erstes Wort des Satzes: Gemeinsame Muster für Wörter mit bis zu neun Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-273">First word of sentence: Common patterns for words up to nine characters.</span></span> 
- <span data-ttu-id="2d7e9-274">Ende des Satzes: Gängige Interpunktion für das Ende eines Satzes.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-274">End of sentence: Common punctuation for end of a sentence.</span></span>
- <span data-ttu-id="2d7e9-275">Kreditkarte: Gängige Formate für Kreditkartennummern.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-275">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="2d7e9-276">Zum Beispiel: 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-276">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="2d7e9-p132">Sozialversicherungsnummer: Format der Sozialversicherungsnummer der Vereinigte Staaten. Beispielsweise 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-p132">Social security number: US Social Security Number format. For example, 111-11-1111.</span></span> 
- <span data-ttu-id="2d7e9-279">Kontrollkästchen: Eine Begriffsliste, die Variationen für ein ausgefülltes Kontrollkästchen darstellt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-279">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="2d7e9-280">Beispielsweise _X_, _ _X_.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-280">For example, _X_, _ _X_.</span></span>
- <span data-ttu-id="2d7e9-281">Währung: Wichtige internationale Symbole.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-281">Currency: Major international symbols.</span></span> <span data-ttu-id="2d7e9-282">Zum Beispiel: $.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-282">For example, $.</span></span> 
- <span data-ttu-id="2d7e9-283">E-Mail-CC: Eine Begriffsliste mit dem Begriff „CC:“, die oft in der Nähe der Namen oder E-Mail-Adressen von anderen Personen oder Gruppen zu finden ist, an welche die Nachricht gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-283">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of other people or groups the message was sent to.</span></span>
- <span data-ttu-id="2d7e9-284">E-Mail-Datum: Eine Begriffsliste mit dem Begriff „Gesendet am:“, die oft in der Nähe des Datums zu finden ist, an dem die E-Mail gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-284">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="2d7e9-285">E-Mail-Begrüßung: Gängige Anfangszeilen für E-Mails.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-285">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="2d7e9-286">E-Mail-Empfänger: Eine Begriffsliste mit dem Begriff „An:“, die oft in der Nähe der Namen oder E-Mail-Adressen von Personen oder Gruppen zu finden ist, an die die Nachricht gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-286">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="2d7e9-287">E-Mail-Absender: Eine Begriffsliste mit dem Begriff „Von:“, die oft in der Nähe des Namens oder der E-Mail-Adresse des Absenders zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-287">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="2d7e9-288">E-Mail-Betreff: Eine Begriffsliste mit dem Begriff „Betreff:“, die oft in der Nähe des Betreffs der E-Mail zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-288">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span>

<span data-ttu-id="2d7e9-289">Die Erklärungsbibliothek enthält ebenfalls häufig verwendete Erklärungen für *reguläre Ausdrücke*, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-289">The explanation library also includes commonly used *regular expression* explanations, including:</span></span>

- <span data-ttu-id="2d7e9-290">6- bis 17-stellige Zahlen: Entspricht einer beliebigen Zahl von 6 bis 17 Ziffern Länge.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-290">6 to 17 digit numbers: Matches any number from 6 to 17 digits long.</span></span> <span data-ttu-id="2d7e9-291">Bankkontonummern der Vereinigten Staaten passen in dieses Muster.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-291">US bank account numbers fit this pattern.</span></span>
- <span data-ttu-id="2d7e9-292">E-Mail-Adresse: Entspricht einem gemeinsamen Typ der E-Mail-Adresse wie meganb@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-292">Email address: Matches a common type of email address like meganb@contoso.com.</span></span>
- <span data-ttu-id="2d7e9-293">Steuernummer der Vereinigten Staaten: Entspricht einer 3-stelligen Zahl, die mit 9 beginnt, gefolgt von einer 6-stelligen Zahl, die mit 7 oder 8 beginnt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-293">US taxpayer ID number: Matches a three-digit number starting with 9 followed by a 6 digit number starting with 7 or 8.</span></span> 
- <span data-ttu-id="2d7e9-294">Webadresse (URL): Entspricht dem Format einer Webadresse ab, beginnend mit http:// oder https://.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-294">Web address (URL): Matches the format of a web address, starting with http:// or https://.</span></span>

<span data-ttu-id="2d7e9-295">Zusätzlich beinhaltet die Erklärungsbibliothek drei automatische Vorlagentypen, die mit den von Ihnen in Ihren Beispieldateien bezeichneten Daten funktionieren:</span><span class="sxs-lookup"><span data-stu-id="2d7e9-295">In addition, the explanation library includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="2d7e9-296">Nach der Bezeichnung: Die Wörter oder Zeichen, die nach den Bezeichnungen in den Beispieldateien aufscheinen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-296">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="2d7e9-297">Vor der Bezeichnung: Die Wörter oder Zeichen, die vor den Bezeichnungen in den Beispieldateien aufscheinen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-297">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="2d7e9-298">Bezeichnungen: Bis zu den ersten 10 Bezeichnungen der Beispieldateien.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-298">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="2d7e9-299">Als Beispiel dafür, wie automatische Vorlagen funktionieren, verwenden wir in der folgenden Beispieldatei die Erklärungsvorlage „Vor der Bezeichnung“, die dazu beiträgt, dem Modell weitere Informationen zur Verfügung zu stellen, um eine genauere Übereinstimmung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-299">To give you an example of how automatic templates work, in the following example file, we'll use the Before label explanation template to help give the model more information to get a more accurate match.</span></span>

![Beispieldatei](../media/content-understanding/before-label.png)

<span data-ttu-id="2d7e9-301">Wenn Sie die Erklärungsvorlage „Vor der Bezeichnung“ auswählen, sucht diese nach der ersten Gruppe von Wörtern, die vor der Bezeichnung in Ihren Beispieldateien vorkommen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-301">When you select the Before label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="2d7e9-302">In dem Beispiel lauten die in der ersten Beispieldatei identifizierten Wörter „Ab dem“.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-302">In the example, the words that are identified in the first example file is "As of".</span></span>

![Vorlage für „Vor der Bezeichnung“](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="2d7e9-304">Sie können **Hinzufügen** wählen, um aus der Vorlage eine Erläuterung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-304">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="2d7e9-305">Sobald Sie weitere Beispieldateien hinzufügen, werden zusätzliche Wörter identifiziert und zur Begriffsliste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-305">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![Die Bezeichnung hinzufügen](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="2d7e9-307">Verwenden einer Vorlage aus der Erklärungsbibliothek</span><span class="sxs-lookup"><span data-stu-id="2d7e9-307">To use a template from the explanation library</span></span>

1. <span data-ttu-id="2d7e9-308">Wählen Sie im Abschnitt **Erklärungen** auf der Seite **Trainieren** Ihres Modells **Neu** aus und dann **Aus einer Vorlage**.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-308">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![„Vor der Bezeichnung „hinzufügen](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="2d7e9-310">Wählen Sie auf der Seite **Erklärungsvorlagen** die Erklärung aus, die Sie verwenden möchten, dann wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-310">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![Auswählen einer Vorlage](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="2d7e9-312">Die Informationen für die von Ihnen ausgewählte Vorlage sind auf der Seite **Erklärung erstellen** dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-312">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="2d7e9-313">Bearbeiten Sie bei Bedarf den Namen der Erläuterung und fügen Sie Elemente zur Begriffsliste hinzu oder entfernen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-313">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![Vorlage bearbeiten](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="2d7e9-315">Wählen Sie anschließend **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2d7e9-315">When finished, select **Save**.</span></span>