---
title: Anpassen oder Erstellen eines neuen vertraulichen Informationstyps
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: ''
description: Informationen zum Ändern oder Erstellen eines neuen vertraulichen Informationstyps in Office 365 für die Datenschutz-Grundverordnung (DSGVO).
ms.openlocfilehash: 70ce61f582cbc952811d01cccc7b958bf1b52dbb
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224632"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a><span data-ttu-id="ab63e-103">Anpassen oder Erstellen eines neuen vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="ab63e-103">Customize or create a new sensitive information type</span></span>

<span data-ttu-id="ab63e-104">Dieser Artikel enthält drei Beispiele, anhand derer gezeigt wird, wie neue vertrauliche Informationstypen für die DSGVO erstellt oder geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="ab63e-104">This article provides three examples to demonstrate how to modify or create new sensitive information types for GDPR.</span></span>

- <span data-ttu-id="ab63e-105">Ändern eines vorhandenen vertraulichen Informationstyps – EU-Debitkartennummer</span><span class="sxs-lookup"><span data-stu-id="ab63e-105">Modify an existing sensitive information type — EU Debit Card Number</span></span>

- <span data-ttu-id="ab63e-106">Erstellen eines neuen vertraulichen Informationstyps – E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="ab63e-106">Create a new sensitive information type — email address</span></span>

- <span data-ttu-id="ab63e-107">Erstellen eines neuen vertraulichen Informationstyps mit einer XML-Beispieldatei – Contoso-Kundennummer</span><span class="sxs-lookup"><span data-stu-id="ab63e-107">Create a new sensitive information type with example XML file — Contoso customer number</span></span>

<span data-ttu-id="ab63e-108">Siehe auch:</span><span class="sxs-lookup"><span data-stu-id="ab63e-108">Also see:</span></span>

- [<span data-ttu-id="ab63e-109">Erstellen eines benutzerdefinierten vertraulichen Informationstyps mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab63e-109">Create a custom sensitive information type using PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [<span data-ttu-id="ab63e-110">Anpassen eines benutzerdefinierten vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="ab63e-110">Customize a built-in sensitive information type</span></span>](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a><span data-ttu-id="ab63e-111">Ändern eines vertraulichen Informationstyps für verbesserte Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="ab63e-111">Modify a sensitive information type to improve accuracy</span></span>

<span data-ttu-id="ab63e-112">Wenn Sie die Inhaltssuche für die Suche nach personenbezogenen Daten mithilfe von vertraulichen Informationstypen verwenden und diese nicht die erwarteten Ergebnisse oder zu viele falsch positive Ergebnisse zurückgibt, sollten Sie den vertraulichen Informationstyp ändern, damit er bei Ihrer Umgebung besser funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ab63e-112">If you're using Content Search to search for personal data using sensitive information types and you're not returning the expected results, or the query returns too many false positives, consider modifying the sensitive information type to work better with your environment.</span></span>

<span data-ttu-id="ab63e-p101">Eine bewährte Methode beim Erstellen oder Anpassen eines vertraulichen Informationstyps besteht darin, einen neuen vertraulichen Informationstyp basierend auf einem vorhandenen zu erstellen und dafür einen eindeutigen Namen und Bezeichner festzulegen. Wenn Sie beispielsweise die Parameter des vertraulichen Informationstyps „EU-Debitkartennummer“ anpassen möchten, könnten Sie Ihre Kopie dieser Regel „EU-Debitkarte erweitert“ nennen, damit sie sich von der ursprünglichen Regel unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p101">The best practice when creating or customizing a sensitive information type is to create a new sensitive information type based on an existing one, giving it a unique name and identifiers. For example, if you wish to adjust the parameters of the "EU Debit Card Number" sensitive information type, you could name your copy of that rule "EU Debit Card Enhanced" to distinguish it from the original.</span></span>

<span data-ttu-id="ab63e-p102">Ändern Sie in Ihrem neuen vertraulichen Informationstyp einfach die Werte, die Sie für bessere Genauigkeit ändern möchten. Wenn Sie dies abgeschlossen haben, laden Sie Ihren neuen vertraulichen Informationstyp hoch und erstellen Sie eine neue DLP-Regel (oder ändern Sie eine vorhandene Regel), um den hinzugefügten neuen vertraulichen Informationstyp zu verwenden. Beim Ändern der Genauigkeit vertraulicher Informationstypen sind möglicherweise einige Testversuche erforderlich, sodass Sie durch eine Kopie des ursprünglichen Typs darauf zurückgreifen können, wenn dies in der Zukunft erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p102">In your new sensitive information type, simply modify the values you wish to change to improve its accuracy. Once complete, upload your new sensitive information type and create a new DLP rule (or modify an existing one) to use the new sensitive information type you just added. Modifying the accuracy of sensitive information types might require some trial and error, so maintaining a copy of the original type allows you to fall back to it if required in the future.</span></span>

<span data-ttu-id="ab63e-118">So passen Sie einen benutzerdefinierten vertraulichen Informationstyp an</span><span class="sxs-lookup"><span data-stu-id="ab63e-118">To customize a sensitive information type:</span></span>

1.  <span data-ttu-id="ab63e-119">Exportieren Sie das vorhandene Microsoft-Regelpaket der integrierten vertraulichen Informationstypen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ab63e-119">Export the existing Microsoft Rule Package of built in sensitive information types in Office 365.</span></span>

2.  <span data-ttu-id="ab63e-120">Benennen Sie diese XML-Datei um, und öffnen Sie sie in einem beliebigen XML-Editor.</span><span class="sxs-lookup"><span data-stu-id="ab63e-120">Rename this XML file and open it in your favorite XML editor.</span></span>

3.  <span data-ttu-id="ab63e-121">Isolieren Sie den vertraulichen Informationstyp, und entfernen Sie alle anderen.</span><span class="sxs-lookup"><span data-stu-id="ab63e-121">Isolate the sensitive information type and remove all others.</span></span>

4.  <span data-ttu-id="ab63e-122">Verwenden Sie PowerShell, um zwei neue GUIDs für den vertraulichen Informationstyp zu generieren, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="ab63e-122">Use PowerShell to generate two new GUIDs for the sensitive information type you are modifying.</span></span>

5.  <span data-ttu-id="ab63e-123">Ändern Sie die ID und andere grundlegende Elemente, damit der vertrauliche Informationstyp eindeutig ist (Dies umfasst das Ersetzen der zwei GUIDs durch die neuen, die generiert wurden.).</span><span class="sxs-lookup"><span data-stu-id="ab63e-123">Modify the ID and other basic elements so the sensitive information type is unique (this includes replacing two GUIDs with the new ones you generated).</span></span>

6.  <span data-ttu-id="ab63e-124">Optimieren Sie die Übereinstimmungsanforderungen für verbesserte Genauigkeit.</span><span class="sxs-lookup"><span data-stu-id="ab63e-124">Tune the match requirements to improve accuracy.</span></span>

    1.  <span data-ttu-id="ab63e-125">Änderungen der Näherung – Ändern Sie die Näherung der Zeichenmuster, um den Bereich zu vergrößern bzw. einzugrenzen, in dem Schlüsselwörter um den vertraulichen Informationstyp herum gefunden werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ab63e-125">Proximity modifications — Modify the character pattern proximity to expand or shrink the window in which keywords must be found around the sensitive information type.</span></span>

    2.  <span data-ttu-id="ab63e-p103">Änderungen des Schlüsselworts – Fügen Sie Schlüsselwörter zu einem \<Keywords\>-Element hinzu, um für den vertraulichen Informationstyp einen genaueren bestätigenden Nachweis für die Suche bereitzustellen, um dieser Regel eine Übereinstimmung zu signalisieren. Sie können auch Schlüsselwörter entfernen, die für falsch positive Ergebnisse sorgen.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p103">Keyword modifications — Add keywords to one of the \<Keywords\> element in order to provide our sensitive information type more specific corroborative evidence to search for in order to signal a match on this rule. Or remove keywords that are causing false positives.</span></span>

    3.  <span data-ttu-id="ab63e-128">Änderungen der Konfidenz – Ändern Sie die Konfidenz, mit der der vertrauliche Informationstyp den in der Definition angegebenen Kriterien entsprechen muss, bevor eine Übereinstimmung signalisiert und gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="ab63e-128">Confidence modifications — Modify the confidence with which the sensitive information type must match the criteria specified in its definition before a match is signaled and reported.</span></span>

7.  <span data-ttu-id="ab63e-129">Laden Sie den neuen vertraulichen Informationstyp hoch.</span><span class="sxs-lookup"><span data-stu-id="ab63e-129">Upload the new sensitive information type.</span></span>

8.  <span data-ttu-id="ab63e-p104">Durchforsten Sie Ihre Inhalte erneut, um vertrauliche Informationen zu identifizieren. Weitere Informationen finden Sie unter [Manuelles Anfordern des Durchforstens und des erneuten Indizieren einer Website](https://docs.microsoft.com/sharepoint/crawl-site-content).</span><span class="sxs-lookup"><span data-stu-id="ab63e-p104">Recrawl your content to identify the sensitive information. See [Manually request crawling and re-indexing of a site](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a><span data-ttu-id="ab63e-132">Beispiel: Ändern des vertraulichen Informationstyps „EU-Debitkartennummer“</span><span class="sxs-lookup"><span data-stu-id="ab63e-132">Example: modify the 'EU Debit Card Number' sensitive information type</span></span>

<span data-ttu-id="ab63e-p105">Zur Verbesserung der Genauigkeit von DLP-Regeln in einem System sind Tests anhand eines Beispieldatensatzes erforderlich, und ggf. muss eine Optimierung durch sich wiederholende Änderungen und Tests vorgenommen werden. In diesem Beispiel werden Änderungen des vertraulichen Informationstyps „EU-Debitkartennummer“ zur Verbesserung der Genauigkeit gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p105">Improving the accuracy of DLP rules in any system requires testing against a sample data set, and may require fine tuning through repetitive modifications and tests. This example demonstrates modifications to the 'EU Debit Card Number' sensitive information type to improve its accuracy.</span></span>

<span data-ttu-id="ab63e-p106">Bei der Suche nach einer EU-Debitkartennummer in unserem Beispiel ist die Definition dieser Zahl mithilfe eines komplexen Musters streng als 16 Ziffern definiert und unterliegt einer Überprüfung der Prüfsumme. Wir können dieses Muster aufgrund der Zeichenfolgendefinition dieses vertraulichen Informationstyps nicht ändern, zur Verbesserung der Genauigkeit für die Suche dieses vertraulichen Informationstyps mit DLP in Office 365 aber die folgenden Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p106">When searching for an EU Debit Card Number in our example, the definition of that number is strictly defined as 16 digits using a complex pattern, and being subject to the validation of a checksum. We cannot alter this pattern due to the string definition of this sensitive information type. However, we can make the following adjustments to improve the accuracy of how DLP finds this sensitive information type within Office 365.</span></span>

### <a name="proximity-modification"></a><span data-ttu-id="ab63e-138">Änderung der Näherung</span><span class="sxs-lookup"><span data-stu-id="ab63e-138">Proximity modification</span></span>

<span data-ttu-id="ab63e-p107">Wir werden den Bereich eingrenzen, indem der patternProximity-Wert in unserem \<Entity\>-Element von 300 in 150 Zeichen geändert wird. Dies bedeutet, dass der bestätigende Nachweis oder unsere Stichwörter, sich näher an unserem vertraulichen Informationstyp befinden müssen, damit diese Regel eine Übereinstimmung signalisiert.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p107">We'll shrink the window by modifying the patternProximity value in our \<Entity\> element from 300 to 150 characters. This means that our corroborative evidence, or our keywords, must be closer to our sensitive information type in order to signal a match on this rule.</span></span>

<span data-ttu-id="ab63e-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="ab63e-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

### <a name="keyword-modifications"></a><span data-ttu-id="ab63e-142">Änderungen des Schlüsselworts</span><span class="sxs-lookup"><span data-stu-id="ab63e-142">Keyword modifications</span></span>

<span data-ttu-id="ab63e-p108">Einige Schlüsselwörter können dazu führen, dass falsch positive Ergebnisse auftreten. Sie möchten daher möglicherweise einige Schlüsselwörter entfernen. Hier sind die Schlüsselwörter für dieses Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ab63e-p108">Some keywords might cause false positives to occur. As a result you might want to remove keywords. Here are the keywords for this example::</span></span>

<span data-ttu-id="ab63e-146">\<Keyword id="Keyword\_card\_terms\_dict"\></span><span class="sxs-lookup"><span data-stu-id="ab63e-146">\<Keyword id="Keyword\_card\_terms\_dict"\></span></span>

<span data-ttu-id="ab63e-147">\<Group\></span><span class="sxs-lookup"><span data-stu-id="ab63e-147">\<Group\></span></span>

<span data-ttu-id="ab63e-148">\<Term\>corporate card\</Term\></span><span class="sxs-lookup"><span data-stu-id="ab63e-148">\<Term\>corporate card\</Term\></span></span>

<span data-ttu-id="ab63e-149">\<Term\>organization card\</Term\></span><span class="sxs-lookup"><span data-stu-id="ab63e-149">\<Term\>organization card\</Term\></span></span>

<span data-ttu-id="ab63e-150">\<Term\>acct nbr\</Term\></span><span class="sxs-lookup"><span data-stu-id="ab63e-150">\<Term\>acct nbr\</Term\></span></span>

<span data-ttu-id="ab63e-151">\<Term\>acct num\</Term\></span><span class="sxs-lookup"><span data-stu-id="ab63e-151">\<Term\>acct num\</Term\></span></span>

<span data-ttu-id="ab63e-152">\<Term\>acct no\</Term\></span><span class="sxs-lookup"><span data-stu-id="ab63e-152">\<Term\>acct no\</Term\></span></span>

<span data-ttu-id="ab63e-153">…</span><span class="sxs-lookup"><span data-stu-id="ab63e-153">…</span></span>

<span data-ttu-id="ab63e-154">\</Group\></span><span class="sxs-lookup"><span data-stu-id="ab63e-154">\</Group\></span></span>

<span data-ttu-id="ab63e-155">\</Keyword\></span><span class="sxs-lookup"><span data-stu-id="ab63e-155">\</Keyword\></span></span>

### <a name="confidence-modifications"></a><span data-ttu-id="ab63e-156">Änderungen der Konfidenz</span><span class="sxs-lookup"><span data-stu-id="ab63e-156">Confidence modifications</span></span>

<span data-ttu-id="ab63e-p109">Wenn Sie Schlüsselwörter aus der Definition entfernen, möchten Sie in der Regel auch die Konfidenz anpassen, mit der dieser vertraulicher Informationstyp durch Verringern dieses Werts gefunden wurde. Die Standardstufe für den Typ „EU-Debitkartennummer“ ist 85.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p109">If you remove keywords from the definition, you would typically want to adjust how confident you are that this sensitive information type was found by lowering this value. The default level for EU Debit Card Number type is 85.</span></span>

<span data-ttu-id="ab63e-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="ab63e-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

<span data-ttu-id="ab63e-160">\<Pattern confidenceLevel="85"\></span><span class="sxs-lookup"><span data-stu-id="ab63e-160">\<Pattern confidenceLevel="85"\></span></span>

<span data-ttu-id="ab63e-161">…</span><span class="sxs-lookup"><span data-stu-id="ab63e-161">…</span></span>

<span data-ttu-id="ab63e-162">\</Pattern\></span><span class="sxs-lookup"><span data-stu-id="ab63e-162">\</Pattern\></span></span>

<span data-ttu-id="ab63e-163">\</Entity\></span><span class="sxs-lookup"><span data-stu-id="ab63e-163">\</Entity\></span></span>

## <a name="create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="ab63e-164">Erstellen eines neuen benutzerdefinierten vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="ab63e-164">Create a new custom sensitive information type</span></span>

<span data-ttu-id="ab63e-165">Um einen neuen benutzerdefinierten vertraulichen Informationstyp zu erstellen, beginnen Sie mit der Verwendung der Inhaltssuche für folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="ab63e-165">To create a new custom sensitive information type, start by using Content Search to:</span></span>

-   <span data-ttu-id="ab63e-166">Optimieren einer KQL-Abfrage</span><span class="sxs-lookup"><span data-stu-id="ab63e-166">Optimize a KQL query</span></span>

-   <span data-ttu-id="ab63e-167">Erfahren, welche Schlüsselwörter besonders hilfreich sind</span><span class="sxs-lookup"><span data-stu-id="ab63e-167">See which keywords are most useful</span></span>

<span data-ttu-id="ab63e-p110">Verwenden Sie diese Ergebnisse, um einen neuen vertraulichen Informationstyp zu erstellen. Optimieren Sie dann den neuen vertraulichen Informationstyp für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p110">Use these results to create a new sensitive information type. Then optimize the new sensitive information type for your environment.</span></span>

<span data-ttu-id="ab63e-p111">Hinweis: In Kürze stehen viele neue vertrauliche Informationstypen für personenbezogene Daten in EU-Ländern zur Verfügung. Wenn Sie neue vertrauliche Informationstypen erstellen müssen, legen Sie zunächst die Daten als Ziel fest, die in Ihrer Umgebung benutzerdefiniert sind.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p111">Note: Many new sensitive information types are coming soon for personal data in EU countries. If you need to create new sensitive information types, begin by targeting data that is custom to your environment.</span></span>

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a><span data-ttu-id="ab63e-172">Schritt 1 – Verwenden von KQL-Abfragen und Stichwörtern für die Suche nach zusätzlichen Daten in Ihrer Umgebung</span><span class="sxs-lookup"><span data-stu-id="ab63e-172">Step 1 — Use KQL queries and key words to find additional data in your environment</span></span>

<span data-ttu-id="ab63e-p112">Sie müssen möglicherweise zusätzliche Abfragen erstellen, um nach personenbezogenen Daten zu suchen, die der DSGVO unterliegen. Die Inhaltssuche verwendet KQL (Keyword Query Language, Schlüsselwortabfragesprache) für die Suche von Daten. Die meisten vertraulichen Daten können nicht ausschließlich mithilfe von KQL ohne vertrauliche Informationstypen ordnungsgemäß erkannt werden. Ziel ist es daher, KQL-Zeichenfolgen mithilfe der Inhaltssuche zu testen, zu optimieren und dann für das Erstellen und Optimieren neuer vertraulicher Informationstypen zur Erzielung sogar einer größeren Genauigkeit zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p112">You might need to create additional queries to find personal data that is subject to GDPR. Content Search uses Keyword Query Language (KQL) to find data. Most sensitive data can't be accurately detected using just KQL without sensitive information types. So the goal is to test and optimize KQL strings using Content Search and then use these to create and tune new sensitive information types where you can achieve even greater accuracy.</span></span>

<span data-ttu-id="ab63e-177">Verwenden Sie die folgenden Ressourcen, um Abfragen mithilfe von KQL zu formulieren und zu optimieren:</span><span class="sxs-lookup"><span data-stu-id="ab63e-177">Use these resources to formulate and optimize queries using KQL:</span></span>

- [<span data-ttu-id="ab63e-178">Syntaxreferenz für die Keyword Query Language (KQL) (DMC)</span><span class="sxs-lookup"><span data-stu-id="ab63e-178">Keyword Query Language (KQL) syntax reference (DMC)</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

- [<span data-ttu-id="ab63e-179">Ausführen einer Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="ab63e-179">Run a Content Search</span></span>](content-search.md)

<span data-ttu-id="ab63e-p113">Die Inhaltssuche bietet eine weitere Ressource, die Sie beim Entwickeln von KQL-Abfragen und vertraulichen Informationstypen unterstützt – Schlüsselwörter. Gründe für die Verwendung der Schlüsselwortliste? Sie können Statistiken abrufen, die zeigen, wie viele Elemente den einzelnen Schlüsselwörtern entsprechen. Dadurch können Sie schnell erkennen, welche Schlüsselwörter am effektivsten (und am wenigsten effektiv) sind. Weitere Informationen zu Suchstatistiken finden Sie unter [Anzeigen der Schlüsselwortstatistik für Inhaltssuchergebnisse](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).</span><span class="sxs-lookup"><span data-stu-id="ab63e-p113">Content Search provides another resource to help you develop KQL queries and sensitive information types — keywords. Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. For more information about search statistics, see [View keyword statistics for Content Search results](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).</span></span>

<span data-ttu-id="ab63e-p114">Schlüsselwörter in einer Zeile werden durch den OR-Operator in der Suchabfrage verknüpft, die erstellt wird. Sie können auch einen Stichwortausdruck (in Klammern) in einer Zeile verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p114">Keywords on each row are connected by the OR operator in the search query that's created. You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span>

<span data-ttu-id="ab63e-187">Weitere Informationen finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions).</span><span class="sxs-lookup"><span data-stu-id="ab63e-187">For more information, see [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions).</span></span>

### <a name="exampleusing-content-search-to-identify-email-addresses"></a><span data-ttu-id="ab63e-188">Beispiel – Verwenden der Inhaltssuche für die Identifizierung von E-Mail-Adressen</span><span class="sxs-lookup"><span data-stu-id="ab63e-188">Example—Using Content Search to identify email addresses</span></span>

<span data-ttu-id="ab63e-p115">E-Mail-Adressen werden als vertrauliche Informationen behandelt, die Personen betreffen. Dies ist ein einfaches Beispiel, das veranschaulicht, wie hilfreich die Inhaltssuche sein kann.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p115">Email addresses are considered sensitive information related to data subjects. This is a simple example to demonstrate how Content Search can help.</span></span>

<span data-ttu-id="ab63e-p116">KQL und Schlüsselwörter können nicht zusammen verwendet werden. Verwenden Sie diese Tools separat, um Ihre Abfrage zu verfeinern und Schlüsselwörter zu ermitteln, die bei vertraulichen Informationstypen nützlich sein könnten.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p116">KQL and keywords can't be used together. Use these tools separately to hone your query and determine keywords that might be useful in sensitive information types.</span></span>

### <a name="kql-query"></a><span data-ttu-id="ab63e-193">KQL-Abfrage</span><span class="sxs-lookup"><span data-stu-id="ab63e-193">KQL query</span></span>

<span data-ttu-id="ab63e-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span><span class="sxs-lookup"><span data-stu-id="ab63e-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span></span>

<span data-ttu-id="ab63e-195">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="ab63e-195">Notes:</span></span>

-   <span data-ttu-id="ab63e-196">Sie können NEAR für Näherungssuchen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab63e-196">You can use NEAR for proximity searches.</span></span>

-   <span data-ttu-id="ab63e-197">Leider unterstützt KQL keine Abfragen mit der Regex-Klasse (Beispiel: IdRef="Regex\_email\_address")</span><span class="sxs-lookup"><span data-stu-id="ab63e-197">Unfortunately, KQL doesn't support queries with the Regex Class (ex: IdRef="Regex\_email\_address")</span></span>

### <a name="keywords"></a><span data-ttu-id="ab63e-198">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ab63e-198">Keywords</span></span>

<span data-ttu-id="ab63e-p117">Geben Sie jedes Schlüsselwort in einer separaten Zeile ein. Beispielschlüsselwörter:</span><span class="sxs-lookup"><span data-stu-id="ab63e-p117">Enter each keyword on a separate line. Example keywords:</span></span>

-   <span data-ttu-id="ab63e-201">email address</span><span class="sxs-lookup"><span data-stu-id="ab63e-201">email address</span></span>

-   <span data-ttu-id="ab63e-202">mail</span><span class="sxs-lookup"><span data-stu-id="ab63e-202">mail</span></span>

-   <span data-ttu-id="ab63e-203">contact</span><span class="sxs-lookup"><span data-stu-id="ab63e-203">contact</span></span>

-   <span data-ttu-id="ab63e-204">sender</span><span class="sxs-lookup"><span data-stu-id="ab63e-204">sender</span></span>

-   <span data-ttu-id="ab63e-205">recipient</span><span class="sxs-lookup"><span data-stu-id="ab63e-205">recipient</span></span>

-   <span data-ttu-id="ab63e-206">cc</span><span class="sxs-lookup"><span data-stu-id="ab63e-206">cc</span></span>

-   <span data-ttu-id="ab63e-207">bcc</span><span class="sxs-lookup"><span data-stu-id="ab63e-207">bcc</span></span>

<span data-ttu-id="ab63e-208">In diesem Beispiel erfahren Sie möglicherweise, dass Schlüsselwörter nicht erforderlich sind und viele falsch positive Ergebnisse erzielen.</span><span class="sxs-lookup"><span data-stu-id="ab63e-208">In this example, you might learn the keywords are not necessary and produce a lot of false positive results.</span></span>

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="ab63e-209">Schritt 2 – Erstellen eines neuen benutzerdefinierten vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="ab63e-209">Step 2 — Create a new custom sensitive information type</span></span>

<span data-ttu-id="ab63e-p118">Nachdem Sie KQL-Abfragen und Schlüsselwörter zum Identifizieren vertraulicher Informationen verwendet haben, verwenden Sie sie zum Erstellen von neuen benutzerdefinierten vertraulichen Informationstypen. In vielen Fällen benötigen Sie die Komplexität von vertraulichen Informationstypen, um eine geeignete Genauigkeitsebene zu erzielen. Sie können dann diese benutzerdefinierten vertraulichen Informationstypen bei der Inhaltssuche, in DLP-Richtlinien und anderen Tools sowie in anderen KQL-Abfragen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p118">After using KQL queries and keywords to identify sensitive information, use these to create new custom sensitive information types. In many cases, you'll require the sophistication of sensitive information types to achieve the right level of accuracy. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span>

<span data-ttu-id="ab63e-p119">Die bewährte Methode besteht darin, einen neuen vertraulichen Informationstyp basierend auf einem vorhandenen zu erstellen. Verwenden Sie das gleiche Verfahren, wie oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p119">The best practice is to create a new sensitive information type based on an existing one. Use the same process described earlier in this article.</span></span>

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a><span data-ttu-id="ab63e-215">Beispiel – Erstellen eines neuen vertraulichen Informationstyps für E-Mail-Adressen</span><span class="sxs-lookup"><span data-stu-id="ab63e-215">Example — Create a new sensitive information for email addresses</span></span> 

<span data-ttu-id="ab63e-p120">Wir werden mit der E-Mail-Adresse als Beispiel fortfahren, weil es einfach ist. In der folgenden Tabelle sind die Änderungen enthalten, die für einen neuen vertraulichen Informationstyp „E-Mail-Adresse“ empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p120">We'll continue with the email address as an example because it's simple. The following table details the modifications recommended for a new email sensitive information type.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ab63e-218"><strong>Schritt</strong></span><span class="sxs-lookup"><span data-stu-id="ab63e-218"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="ab63e-219"><strong>Änderung</strong></span><span class="sxs-lookup"><span data-stu-id="ab63e-219"><strong>Modification </strong></span></span></th>
<th align="left"><span data-ttu-id="ab63e-220"><strong>Beispiel-XML-Syntax</strong></span><span class="sxs-lookup"><span data-stu-id="ab63e-220"><strong>Example XML syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ab63e-221">1</span><span class="sxs-lookup"><span data-stu-id="ab63e-221">1</span></span></td>
<td align="left"><span data-ttu-id="ab63e-222">Legen Sie die IdRef-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="ab63e-222">Set the IdRef property</span></span>
<p><span data-ttu-id="ab63e-p121">Ändern Sie in dem &lt;Entity&gt;-Element das &lt;IdMatch&gt;-Element so, dass seine idRef-Eigenschaft einem eindeutigen Wert entspricht. Dieser Wert verweist auf ein Element, das unseren regulären Ausdruck für die Suche von E-Mail-Adressen definiert.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p121">Within the &lt;Entity&gt; element, modify the &lt;IdMatch&gt; element so that its idRef property is = to a unique value. This value will point to an element that defines our regular expression to find email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="ab63e-225">IdRef=&quot;Regex_email_address&quot;</span><span class="sxs-lookup"><span data-stu-id="ab63e-225">IdRef=&quot;Regex_email_address&quot;</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ab63e-226">2</span><span class="sxs-lookup"><span data-stu-id="ab63e-226">2</span></span></td>
<td align="left"><p><span data-ttu-id="ab63e-227">Näherungsattribut</span><span class="sxs-lookup"><span data-stu-id="ab63e-227">Proximity attribute</span></span></p>
<p><span data-ttu-id="ab63e-228">Wir beginnen mit einem patternProximity-Wert von 300 in unserem &lt;Entity&gt;-Element.</span><span class="sxs-lookup"><span data-stu-id="ab63e-228">We'll start with a patternProximity value in our &lt;Entity&gt; element of 300.</span></span></p></td>
<td align="left"><span data-ttu-id="ab63e-229">patternsProximity=&quot;300&quot;</span><span class="sxs-lookup"><span data-stu-id="ab63e-229">patternsProximity=&quot;300&quot;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ab63e-230">3</span><span class="sxs-lookup"><span data-stu-id="ab63e-230">3</span></span></td>
<td align="left"><p><span data-ttu-id="ab63e-231">Zuverlässigkeitsstufe</span><span class="sxs-lookup"><span data-stu-id="ab63e-231">Confidence level</span></span></p>
<p><span data-ttu-id="ab63e-p122">Legen Sie die recommendedConfidence-Eigenschaft auf einen Wert fest, der der Zuverlässigkeit entspricht, mit der eine genaue Übereinstimmung gefunden wird. Dies erfordert wahrscheinlich einige Tests anhand eines repräsentativen Datensatzes, um ein genaues Ergebnis zu erhalten. Legen Sie diesen Wert zunächst auf 75 fest.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p122">Set the recommendedConfidence property to a value you feel will represent the confidence of finding an accurate match. This will likely require testing with a representative data set to get an accurate result. As an initial setting, set this value to 75.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ab63e-235">recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-235">recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="ab63e-236">Der resultierende XML-Code für diese ersten drei Elemente sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ab63e-236">The resulting XML for these first three elements combined looks like this:</span></span></p>
<p><span data-ttu-id="ab63e-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="ab63e-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="ab63e-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span></span></p>
<p><span data-ttu-id="ab63e-240">&lt;Any minMatches=&quot;1&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-240">&lt;Any minMatches=&quot;1&quot;&gt;</span></span></p>
<p><span data-ttu-id="ab63e-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span></span></p>
<p><span data-ttu-id="ab63e-242">&lt;/Any&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-242">&lt;/Any&gt;</span></span></p>
<p><span data-ttu-id="ab63e-243">&lt;/Pattern&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-243">&lt;/Pattern&gt;</span></span></p>
<p><span data-ttu-id="ab63e-244">&lt;/Entity&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-244">&lt;/Entity&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ab63e-245">4</span><span class="sxs-lookup"><span data-stu-id="ab63e-245">4</span></span></td>
<td align="left"><p><span data-ttu-id="ab63e-246">Regex-Element</span><span class="sxs-lookup"><span data-stu-id="ab63e-246">Regex element</span></span></p>
<p><span data-ttu-id="ab63e-247">Fügen Sie ein neues &lt;Regex&gt;-Element unmittelbar unterhalb der &lt;Entity&gt;-Elemente hinzu, die den zum Identifizieren von E-Mail-Adressen verwendeten regulären Ausdruck definieren.</span><span class="sxs-lookup"><span data-stu-id="ab63e-247">Add a new &lt;Regex&gt; element immediately be below the &lt;Entity&gt; elements that defines the regular expression used to identify email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="ab63e-248">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-248">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ab63e-249">5</span><span class="sxs-lookup"><span data-stu-id="ab63e-249">5</span></span></td>
<td align="left"><p><span data-ttu-id="ab63e-250">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ab63e-250">Keywords</span></span></p>
<p><span data-ttu-id="ab63e-p123">Fügen Sie ein neues &lt;Keyword&gt;-Element unterhalb des &lt;Regex&gt;-Elements hinzu, das die Liste von E-Mail-Adressen definiert, die mit Schlüsselwörtern verknüpft sind. Stellen Sie sicher, dass der ID-Wert für das &lt;Keyword&gt;-Element dem &lt;Match idRef&gt;-Wert in dem &lt;Entity&gt;&lt;Pattern&gt;-Element entspricht. Sie können weiterhin eigene Schlüsselwörter hinzufügen, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p123">Add a new &lt;Keyword&gt; element below the &lt;Regex&gt; element that defines list of email address related keywords. Ensure that the id value for the &lt;Keyword&gt; element matches the &lt;Match idRef&gt; value in the &lt;Entity&gt;&lt;Pattern&gt; element. You may continue to add your own keywords if needed.</span></span></p>
<p><span data-ttu-id="ab63e-p124">Schlüsselwörter müssen nicht zwingend in einem vertraulichen Informationstyp „E-Mail-Adresse“ enthalten sein. Sie dienen lediglich als Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p124">Keywords are likely not necessary to include in an email sensitive information type. These are provided as an example.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ab63e-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span></span></p>
<p><span data-ttu-id="ab63e-257">&lt;Group&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-257">&lt;Group&gt;</span></span></p>
<p><span data-ttu-id="ab63e-258">&lt;Term&gt;email&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-258">&lt;Term&gt;email&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="ab63e-259">&lt;Term&gt;email address&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-259">&lt;Term&gt;email address&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="ab63e-260">&lt;Term&gt;contact&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-260">&lt;Term&gt;contact&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="ab63e-261">&lt;/Group&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-261">&lt;/Group&gt;</span></span></p>
<p><span data-ttu-id="ab63e-262">&lt;/Keyword&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-262">&lt;/Keyword&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ab63e-263">6</span><span class="sxs-lookup"><span data-stu-id="ab63e-263">6</span></span></td>
<td align="left"><p><span data-ttu-id="ab63e-264">LocalizedStrings-Element</span><span class="sxs-lookup"><span data-stu-id="ab63e-264">LocalizedStrings element</span></span></p>
<p><span data-ttu-id="ab63e-265">Stellen Sie in dem &lt;LocalizedStrings&gt;&lt;Resource&gt;-Element sicher, dass Sie einen eindeutigen Namen verwenden, der den vertraulichen Informationstyp angibt.</span><span class="sxs-lookup"><span data-stu-id="ab63e-265">In the &lt;LocalizedStrings&gt;&lt;Resource&gt; element ensure that you have a unique name that identifies your sensitive information type.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ab63e-266">&lt;LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-266">&lt;LocalizedStrings&gt;</span></span></p>
<p><span data-ttu-id="ab63e-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span></span></p>
<p><span data-ttu-id="ab63e-268">&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-268">&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</span></span></p>
<p><span data-ttu-id="ab63e-269">&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-269">&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</span></span></p>
<p><span data-ttu-id="ab63e-270">&lt;/Resource&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-270">&lt;/Resource&gt;</span></span></p>
<p><span data-ttu-id="ab63e-271">&lt;/LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="ab63e-271">&lt;/LocalizedStrings&gt;</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a><span data-ttu-id="ab63e-272">Erstellen eines neuen vertraulichen Informationstyps mit einer PowerShell- und XML-Beispieldatei – Contoso-Kundennummer</span><span class="sxs-lookup"><span data-stu-id="ab63e-272">Create a new sensitive information type with example PowerShell and XML file — Contoso customer number</span></span>

<span data-ttu-id="ab63e-p125">Contoso verwendet eine Contoso-Kundennummer, um jeden Kunden in der Kundendatenbank zu identifizieren. Eine Contoso-Kundennummer weist die folgende Taxonomie auf:</span><span class="sxs-lookup"><span data-stu-id="ab63e-p125">Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following taxonomy:</span></span>

-   <span data-ttu-id="ab63e-p126">Zwei Ziffern, die für das Jahr stehen, in dem der Datensatz erstellt wurde. Contoso wurde im Jahr 2002 gegründet. Daher wäre der früheste mögliche Wert 02.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p126">Two digits to represent the year that the record was created. Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span>

-   <span data-ttu-id="ab63e-p127">Drei Ziffern, die für die Partneragentur stehen, die den Datensatz erstellt hat. Mögliche Agenturwerte liegen zwischen 000 bis 999.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p127">Three digits to represent the partner agency that created the record. Possible agency values range from 000 to 999.</span></span>

-   <span data-ttu-id="ab63e-p128">Ein alphanumerisches Zeichen zur Darstellung der Branche. Mögliche Werte sind a-z. Groß- und Kleinschreibung sollte dabei nicht berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p128">An alpha character to represent the line of business. Possible values are a-z and should be case insensitive.</span></span>

-   <span data-ttu-id="ab63e-p129">Eine vierstellige fortlaufende Seriennummer. Mögliche Werte liegen zwischen 0000 und 9999.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p129">A four-digit serial number. Possible serial number values range from 0000 to 9999.</span></span>

<span data-ttu-id="ab63e-283">Beispiele für Contoso-Kundennummern:</span><span class="sxs-lookup"><span data-stu-id="ab63e-283">Example CCNs:</span></span>

> <span data-ttu-id="ab63e-284">15080P9562</span><span class="sxs-lookup"><span data-stu-id="ab63e-284">15080P9562</span></span>
>
> <span data-ttu-id="ab63e-285">14040O1119</span><span class="sxs-lookup"><span data-stu-id="ab63e-285">14040O1119</span></span>
>
> <span data-ttu-id="ab63e-286">15020J8317</span><span class="sxs-lookup"><span data-stu-id="ab63e-286">15020J8317</span></span>
>
> <span data-ttu-id="ab63e-287">14050E2330</span><span class="sxs-lookup"><span data-stu-id="ab63e-287">14050E2330</span></span>
>
> <span data-ttu-id="ab63e-288">16050E2166</span><span class="sxs-lookup"><span data-stu-id="ab63e-288">16050E2166</span></span>
>
> <span data-ttu-id="ab63e-289">17040O1118</span><span class="sxs-lookup"><span data-stu-id="ab63e-289">17040O1118</span></span>

<span data-ttu-id="ab63e-290">Contoso verwendet immer eine Contoso-Kundennummer zum Verweisen auf Kunden in der internen Korrespondenz, externen Korrespondenz, in Dokumenten usw. Das Unternehmen möchte einen benutzerdefinierten vertraulichen Informationstyp erstellen, um die Verwendung von Contoso-Kundennummern zu ermitteln, damit es einen Schutz für die Verwendung dieser personenbezogenen Daten anwenden kann.</span><span class="sxs-lookup"><span data-stu-id="ab63e-290">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, etc. They would like to create a custom sensitive information type to detect the use of CCN so that they may apply protection to the use of this form of personal data.</span></span>

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a><span data-ttu-id="ab63e-291">Erstellen eines neuen vertraulichen Informationstyps für Contoso-Kundennummer</span><span class="sxs-lookup"><span data-stu-id="ab63e-291">Create a new sensitive information type for Contoso customer number</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ab63e-292"><strong>Schritt</strong></span><span class="sxs-lookup"><span data-stu-id="ab63e-292"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="ab63e-293"><strong>Aktion </strong></span><span class="sxs-lookup"><span data-stu-id="ab63e-293"><strong>Action </strong></span></span></th>
<th align="left"><span data-ttu-id="ab63e-294"><strong>Ergebnis</strong></span><span class="sxs-lookup"><span data-stu-id="ab63e-294"><strong>Result</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ab63e-295">1</span><span class="sxs-lookup"><span data-stu-id="ab63e-295">1</span></span></td>
<td align="left"><span data-ttu-id="ab63e-296">Contoso verwendet PowerShell und die Inhaltssuche, um nach Dokumenten zu suchen, die einem beispielhaften Satz an Contoso-Kundennummern entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ab63e-296">Contoso uses PowerShell and Content Search to find documents that match an example set of CCNs.</span></span></td>
<td align="left">

<p><span data-ttu-id="ab63e-297">#Herstellen einer Verbindung mit dem Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ab63e-297">#Connect to Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="ab63e-298">$adminUser = &quot;alland@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="ab63e-298">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="ab63e-299">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="ab63e-299">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="ab63e-300">#Erstellen &amp; Starten der Suche für Beispieldaten</span><span class="sxs-lookup"><span data-stu-id="ab63e-300">#Create &amp; start search for sample data</span></span></p>
<p><span data-ttu-id="ab63e-301">$searchName = &quot;Sample Customer Information Search&quot;</span><span class="sxs-lookup"><span data-stu-id="ab63e-301">$searchName = &quot;Sample Customer Information Search&quot;</span></span></p>
<p><span data-ttu-id="ab63e-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span><span class="sxs-lookup"><span data-stu-id="ab63e-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span></span></p>
<p><span data-ttu-id="ab63e-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span><span class="sxs-lookup"><span data-stu-id="ab63e-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span></span></p>
<p><span data-ttu-id="ab63e-304">Start-ComplianceSearch -Identity $searchName</span><span class="sxs-lookup"><span data-stu-id="ab63e-304">Start-ComplianceSearch -Identity $searchName</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ab63e-305">2</span><span class="sxs-lookup"><span data-stu-id="ab63e-305">2</span></span></td>
<td align="left"><span data-ttu-id="ab63e-p130">Contoso analysiert die Ergebnisse. Jedes Mal, wenn die Contoso-Kundennummer verwendet wurde, wurde ein Datum im EU-Format verwendet sowie eines der folgenden Schlüsselwörter innerhalb eines Näherungsbereichs von 300 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ab63e-p130">Contoso analyzes the results. Every time the CCN was used, an EU formatted date was used and one of these keywords were also used within a proximity of 300 characters.</span></span></td>
<td align="left"><span data-ttu-id="ab63e-308">customer number, customer no, customer #, customer#, Contoso customer</span><span class="sxs-lookup"><span data-stu-id="ab63e-308">customer number, customer no, customer #, customer#, Contoso customer</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ab63e-309">3</span><span class="sxs-lookup"><span data-stu-id="ab63e-309">3</span></span></td>
<td align="left"><span data-ttu-id="ab63e-310">Contoso hat das folgende RegEx-Muster zum Identifizieren von Contoso-Kundennummern entwickelt.</span><span class="sxs-lookup"><span data-stu-id="ab63e-310">Contoso developed the following Regular Expression (RegEx) pattern to identify their CCN.</span></span></td>
<td align="left"><span data-ttu-id="ab63e-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span><span class="sxs-lookup"><span data-stu-id="ab63e-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ab63e-312">4</span><span class="sxs-lookup"><span data-stu-id="ab63e-312">4</span></span></td>
<td align="left"><span data-ttu-id="ab63e-313">Contoso hat das folgende RegEx-Muster zum Identifizieren von EU-Datumsangaben in den von ihren verschiedenen Filialen verwendeten Formaten entwickelt.</span><span class="sxs-lookup"><span data-stu-id="ab63e-313">Contoso developed the following Regular Expression (RegEx) pattern to identify EU dates in the formats used by their various subsidiaries.</span></span></td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ab63e-314">5</span><span class="sxs-lookup"><span data-stu-id="ab63e-314">5</span></span></td>
<td align="left"><span data-ttu-id="ab63e-315">Contoso verwendet PowerShell, um drei eindeutige GUIDs zu generieren.</span><span class="sxs-lookup"><span data-stu-id="ab63e-315">Contoso uses PowerShell to generate three unique GUIDs.</span></span></td>
<td align="left"><p><span data-ttu-id="ab63e-316">#Generieren einer eindeutigen GUID für RulePack-ID, Publisher-ID und Entitäts-ID</span><span class="sxs-lookup"><span data-stu-id="ab63e-316">#Generate a unique GUID for RulePack Id, Publisher Id, and Entity Id</span></span></p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ab63e-317">6</span><span class="sxs-lookup"><span data-stu-id="ab63e-317">6</span></span></td>
<td align="left"><span data-ttu-id="ab63e-318">Contoso definiert die folgenden Parameter für die Regel für vertrauliche Elemente.</span><span class="sxs-lookup"><span data-stu-id="ab63e-318">Contoso defines the following parameters for their sensitive item type rule.</span></span></td>
<td align="left"><p><span data-ttu-id="ab63e-319">Name: Contoso-Kundennummer</span><span class="sxs-lookup"><span data-stu-id="ab63e-319">Name: Contoso Customer Number (CCN)</span></span></p>
<p><span data-ttu-id="ab63e-320">Beschreibung: Contoso-Kundennummer, die nach zusätzlichen Stichwörtern und EU-Datumsangaben sucht.</span><span class="sxs-lookup"><span data-stu-id="ab63e-320">Description: Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ab63e-321">7</span><span class="sxs-lookup"><span data-stu-id="ab63e-321">7</span></span></td>
<td align="left"><span data-ttu-id="ab63e-322">Contoso erstellt eine XML-Datei für einen neuen vertraulichen Informationstyp zum Erkennen einer Contoso-Kundennummer und speichert diese in einem lokalen Dateisystem als C:\Scripts\ContosoCCN.xml mit UTF-8-Codierung.</span><span class="sxs-lookup"><span data-stu-id="ab63e-322">Contoso creates an XML file for a new sensitive information type to detect a Contoso Customer Number (CCN) and saves this to a local file system as C:\Scripts\ContosoCCN.xml in with UTF-8 encoding.</span></span></td>
<td align="left"><span data-ttu-id="ab63e-323">Siehe XML-Datei unter dieser Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ab63e-323">See the XML file below this table.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ab63e-324">8</span><span class="sxs-lookup"><span data-stu-id="ab63e-324">8</span></span></td>
<td align="left"><span data-ttu-id="ab63e-325">Contoso erstellt den benutzerdefinierten vertraulichen Informationstyp mit PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab63e-325">Contoso creates the custom sensitive information type with the following PowerShell.</span></span></td>
<td align="left"><p><span data-ttu-id="ab63e-326">#Herstellen einer Verbindung mit dem Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ab63e-326">#Connect to Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="ab63e-327">$adminUser = &quot;alland@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="ab63e-327">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="ab63e-328">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="ab63e-328">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="ab63e-329">#Erstellen eines neuen vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="ab63e-329">#Create new Sensitive Information Type</span></span></p>
<p><span data-ttu-id="ab63e-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span><span class="sxs-lookup"><span data-stu-id="ab63e-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a><span data-ttu-id="ab63e-331">XML-Beispieldatei für den neuen vertraulichen Informationstyp (Schritt 7)</span><span class="sxs-lookup"><span data-stu-id="ab63e-331">Example XML file for the new sensitive information type (step 7)</span></span>
```xml
\<?xml version="1.0" encoding="utf-8"?\>

\<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"\>

\<RulePack id="130ae63b-a91e-4a12-9e02-a90e36a83d7f"\>

\<Version major="1" minor="0" build="0" revision="0" /\>

\<Publisher id="47148982-defd-42a1-890a-7b9472099f1f" /\>

\<Details defaultLangCode="en"\>

\<LocalizedDetails langcode="en"\>

\<PublisherName\>Contoso Ltd.\</PublisherName\>

\<Name\>Contoso Rule Package\</Name\>

\<Description\>Defines Contoso's custom set of classification rules\</Description\>

\</LocalizedDetails\>

\</Details\>

\</RulePack\>

\<Rules\>

\<!-- Contoso Customer Number (CCN) --\>

\<Entity id="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b" patternsProximity="300" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

\<IdMatch idRef="Regex\_contoso\_ccn" /\>

\<Match idRef="Keyword\_contoso\_ccn" /\>

\<Match idRef="Regex\_eu\_date" /\>

\</Pattern\>

\</Entity\>

\<Regex id="Regex\_contoso\_ccn"\>[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}\</Regex\>

\<Keyword id="Keyword\_contoso\_ccn"\>

\<Group matchStyle="word"\>

\<Term caseSensitive="false"\>customer number\</Term\>

\<Term caseSensitive="false"\>customer no\</Term\>

\<Term caseSensitive="false"\>customer \#\</Term\>

\<Term caseSensitive="false"\>customer\#\</Term\>

\<Term caseSensitive="false"\>Contoso customer\</Term\>

\</Group\>

\</Keyword\>

\<Regex id="Regex\_eu\_date"\> (0?[1-9]|[12][0-9]|3[0-1])[\\/-](0?[1-9]|1[0-2]|j\\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?‌ |feb(ruary|ruari|rero|braio|ruar|br)?|f\\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\\x00e4rz|maart‌|apr(ile|il)?|abr(il)?|avril‌ |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?‌ |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\\x00e9c(embre)?)[ \\/-](19|20)?[0-9]{2}\</Regex\>

\<LocalizedStrings\>

\<Resource idRef="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b"\>

\<Name default="true" langcode="en-us"\>Contoso Customer Number (CCN)\</Name\>

\<Description default="true" langcode="en-us"\>Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date\</Description\>

\</Resource\>

\</LocalizedStrings\>

\</Rules\>

\</RulePackage\>
```
