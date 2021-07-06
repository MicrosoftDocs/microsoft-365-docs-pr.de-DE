---
title: Weitere Informationen zu Typen vertraulicher Informationen
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: 3f64b981b60db9f9089af0555e4bf734864913b9
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300381"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="2dfc8-102">Weitere Informationen zu Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="2dfc8-102">Learn about sensitive information types</span></span>

<span data-ttu-id="2dfc8-103">Das Identifizieren und Klassifizieren vertraulicher Elemente, die der Kontrolle Ihrer Organisation unterliegen, ist der erste Schritt in der [Informationsschutz-Abteilung.](./information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="2dfc8-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](./information-protection.md).</span></span>  <span data-ttu-id="2dfc8-104">Microsoft 365 bietet drei Möglichkeiten zum Identifizieren von Elementen, sodass sie klassifiziert werden können:</span><span class="sxs-lookup"><span data-stu-id="2dfc8-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="2dfc8-105">manuell von Benutzern</span><span class="sxs-lookup"><span data-stu-id="2dfc8-105">manually by users</span></span>
- <span data-ttu-id="2dfc8-106">automatische Mustererkennung, z. B. Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="2dfc8-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="2dfc8-107">Maschinelles Lernen</span><span class="sxs-lookup"><span data-stu-id="2dfc8-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="2dfc8-108">Typen vertraulicher Informationen sind musterbasierte Klassifizierer.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="2dfc8-109">Sie erkennen vertrauliche Informationen wie Sozialversicherungs-, Kreditkarten- oder Bankkontonummern, um vertrauliche Elemente zu identifizieren. Siehe [Entitätsdefinitionen für Typen vertraulicher Informationen.](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="2dfc8-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="2dfc8-110">Typen vertraulicher Informationen werden in</span><span class="sxs-lookup"><span data-stu-id="2dfc8-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="2dfc8-111">Richtlinien zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="2dfc8-111">Data loss prevention policies</span></span>](dlp-learn-about-dlp.md) 
- [<span data-ttu-id="2dfc8-112">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="2dfc8-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="2dfc8-113">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="2dfc8-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="2dfc8-114">Insider-Risikomanagement</span><span class="sxs-lookup"><span data-stu-id="2dfc8-114">Insider risk management</span></span>](insider-risk-management.md)
- [<span data-ttu-id="2dfc8-115">Kommunikationscompliance</span><span class="sxs-lookup"><span data-stu-id="2dfc8-115">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="2dfc8-116">Richtlinien für die automatische Kennzeichnung</span><span class="sxs-lookup"><span data-stu-id="2dfc8-116">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="2dfc8-117">Grundlegende Teile eines vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="2dfc8-117">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="2dfc8-118">Jede Entität des Vertraulichen Informationstyps wird durch die folgenden Felder definiert:</span><span class="sxs-lookup"><span data-stu-id="2dfc8-118">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="2dfc8-119">Name: Wie auf den Vertraulichen Informationstyp verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="2dfc8-119">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="2dfc8-120">description: beschreibt, wonach der Typ vertraulicher Informationen sucht</span><span class="sxs-lookup"><span data-stu-id="2dfc8-120">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="2dfc8-121">Muster: Ein Muster definiert, was ein vertraulicher Informationstyp erkennt.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-121">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="2dfc8-122">Es besteht aus den folgenden Komponenten</span><span class="sxs-lookup"><span data-stu-id="2dfc8-122">It consists of the following components</span></span>
    - <span data-ttu-id="2dfc8-123">Primäres Element – das Hauptelement, nach dem der Typ vertraulicher Informationen sucht.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-123">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="2dfc8-124">Es kann sich um einen **regulären Ausdruck** mit oder ohne Prüfsummenüberprüfung, eine **Schlüsselwortliste,** ein **Schlüsselwortwörterbuch** oder eine **Funktion sein.**</span><span class="sxs-lookup"><span data-stu-id="2dfc8-124">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="2dfc8-125">Unterstützendes Element – Elemente, die als unterstützende Nachweise dienen und dazu beitragen, das Vertrauen der Übereinstimmung zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-125">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="2dfc8-126">Beispiel: Schlüsselwort "SSN" in der Nähe einer SSN-Nummer.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-126">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="2dfc8-127">Es kann sich um einen regulären Ausdruck mit oder ohne Prüfsummenüberprüfung, Schlüsselwortliste, Schlüsselwortwörterbuch oder Wörterbuch sein.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-127">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="2dfc8-128">Konfidenzniveau – Konfidenzniveau (hoch, mittel, niedrig) gibt an, wie viele unterstützende Nachweise zusammen mit dem primären Element gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-128">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="2dfc8-129">Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Wahrscheinlichkeit, dass ein übereinstimmendes Element die vertraulichen Informationen enthält, nach denen Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-129">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="2dfc8-130">Näherung – Anzahl der Zeichen zwischen primärem und unterstützendem Element</span><span class="sxs-lookup"><span data-stu-id="2dfc8-130">Proximity – Number of characters between primary and supporting element</span></span>

![Diagramm von bestätigenden Nachweisen und Näherungsfenster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="2dfc8-132">Weitere Informationen zu Vertrauensstufen finden Sie in diesem Video.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-132">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="2dfc8-133">Beispiel für vertraulichen Informationstyp</span><span class="sxs-lookup"><span data-stu-id="2dfc8-133">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="2dfc8-134">Nationale Identität (DNI) für Argentinien</span><span class="sxs-lookup"><span data-stu-id="2dfc8-134">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="2dfc8-135">Format</span><span class="sxs-lookup"><span data-stu-id="2dfc8-135">Format</span></span>

<span data-ttu-id="2dfc8-136">Acht Ziffern, durch Punkte getrennt</span><span class="sxs-lookup"><span data-stu-id="2dfc8-136">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="2dfc8-137">Muster</span><span class="sxs-lookup"><span data-stu-id="2dfc8-137">Pattern</span></span>

<span data-ttu-id="2dfc8-138">Acht Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2dfc8-138">Eight digits:</span></span>
- <span data-ttu-id="2dfc8-139">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2dfc8-139">two digits</span></span>
- <span data-ttu-id="2dfc8-140">ein Punkt</span><span class="sxs-lookup"><span data-stu-id="2dfc8-140">a period</span></span>
- <span data-ttu-id="2dfc8-141">drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2dfc8-141">three digits</span></span>
- <span data-ttu-id="2dfc8-142">ein Punkt</span><span class="sxs-lookup"><span data-stu-id="2dfc8-142">a period</span></span>
- <span data-ttu-id="2dfc8-143">drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2dfc8-143">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2dfc8-144">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2dfc8-144">Checksum</span></span>

<span data-ttu-id="2dfc8-145">Nein</span><span class="sxs-lookup"><span data-stu-id="2dfc8-145">No</span></span>

### <a name="definition"></a><span data-ttu-id="2dfc8-146">Definition</span><span class="sxs-lookup"><span data-stu-id="2dfc8-146">Definition</span></span>

<span data-ttu-id="2dfc8-147">Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:</span><span class="sxs-lookup"><span data-stu-id="2dfc8-147">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2dfc8-148">Der reguläre Ausdruck Regex_argentina_national_id nach Inhalten sucht, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-148">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2dfc8-149">Es wird ein Schlüsselwort aus Keyword_argentina_national_id gefunden.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-149">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2dfc8-150">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2dfc8-150">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="2dfc8-151">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="2dfc8-151">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="2dfc8-152">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="2dfc8-152">Argentina National Identity number</span></span> 
- <span data-ttu-id="2dfc8-153">Identität</span><span class="sxs-lookup"><span data-stu-id="2dfc8-153">Identity</span></span> 
- <span data-ttu-id="2dfc8-154">Nationale Identifikationskarte</span><span class="sxs-lookup"><span data-stu-id="2dfc8-154">Identification National Identity Card</span></span> 
- <span data-ttu-id="2dfc8-155">Dni</span><span class="sxs-lookup"><span data-stu-id="2dfc8-155">DNI</span></span> 
- <span data-ttu-id="2dfc8-156">Nationale NIC-Registrierung von Personen</span><span class="sxs-lookup"><span data-stu-id="2dfc8-156">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="2dfc8-157">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="2dfc8-157">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="2dfc8-158">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="2dfc8-158">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="2dfc8-159">Identidad</span><span class="sxs-lookup"><span data-stu-id="2dfc8-159">Identidad</span></span> 
- <span data-ttu-id="2dfc8-160">Identificación</span><span class="sxs-lookup"><span data-stu-id="2dfc8-160">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="2dfc8-161">Weitere Informationen zu Konfidenzniveaus</span><span class="sxs-lookup"><span data-stu-id="2dfc8-161">More on confidence levels</span></span>

<span data-ttu-id="2dfc8-162">In einer Entitätsdefinition des Vertraulichen Informationstyps gibt die **Konfidenzstufe** an, wie viel unterstützende Nachweise zusätzlich zum primären Element erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-162">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="2dfc8-163">Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Wahrscheinlichkeit, dass ein übereinstimmendes Element die vertraulichen Informationen enthält, nach denen Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-163">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="2dfc8-164">Übereinstimmungen mit einem hohen Konfidenzniveau enthalten beispielsweise mehr unterstützende Nachweise in direkter Nähe des primären Elements, während Übereinstimmungen mit einem niedrigen Konfidenzniveau wenig bis gar keine unterstützenden Nachweise in der nähe enthalten würden.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-164">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="2dfc8-165">Eine hohe Konfidenzstufe gibt die wenigsten falsch positiven Ergebnisse zurück, kann aber zu mehr falsch negativen Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-165">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="2dfc8-166">Niedrige oder mittlere Konfidenzniveaus geben mehr falsch positive Ergebnisse zurück, aber nur wenige bis null falsch negative Werte.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-166">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="2dfc8-167">**niedrige Konfidenz:** Der Wert von 65, übereinstimmende Elemente enthalten die wenigsten falsch negativen, aber die falsch positiven Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-167">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="2dfc8-168">Niedrige Konfidenz gibt alle Übereinstimmungen mit niedriger, mittlerer und hoher Konfidenz zurück.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-168">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="2dfc8-169">**mittlere Konfidenz:** Der Wert von 75, übereinstimmende Elemente enthalten eine durchschnittliche Menge falsch positiver und falsch negativer Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-169">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="2dfc8-170">Mittlere Konfidenz gibt alle mittleren und hohen Konfidenzüberstimmungen zurück.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-170">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="2dfc8-171">**Hohe Konfidenz:** Der Wert von 85, übereinstimmende Elemente enthalten die wenigsten falsch positiven, aber die falsch negativen Werte.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-171">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="2dfc8-172">Hohe Konfidenz gibt nur Übereinstimmungen mit hoher Konfidenz zurück.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-172">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="2dfc8-173">Sie sollten Muster mit hoher Konfidenzstufe mit niedrigen Zählungen verwenden, z. B. fünf bis zehn, und Muster mit niedriger Konfidenz mit höheren Zählungen, z. B. 20 oder mehr.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-173">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="2dfc8-174">Wenn Sie vorhandene Richtlinien oder benutzerdefinierte Typen vertraulicher Informationen (SITs) mithilfe von nummernbasierten Konfidenzniveaus definiert haben (auch als Genauigkeit bekannt), werden sie automatisch den drei diskreten Konfidenzniveaus zugeordnet. Geringes Vertrauen, mittleres Vertrauen und hohe Vertrauenswürdigkeit in der Benutzeroberfläche des Security @ Compliance Centers.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-174">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="2dfc8-175">Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierte SIT-Muster mit Konfidenzniveaus zwischen 76 und 100 werden einer hohen Zuverlässigkeit zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-175">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="2dfc8-176">Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierte SIT-Muster mit Konfidenzniveaus zwischen 66 und 75 werden mittleren Konfidenzwerten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-176">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="2dfc8-177">Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierte SIT-Muster mit Konfidenzniveaus, die kleiner oder gleich 65 sind, werden einem niedrigen Konfidenzniveau zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-177">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="2dfc8-178">Benutzerdefinierte Typen vertraulicher Informationen erstellen</span><span class="sxs-lookup"><span data-stu-id="2dfc8-178">Creating custom sensitive information types</span></span>

<span data-ttu-id="2dfc8-179">Zum Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center stehen Ihnen mehrere Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="2dfc8-179">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="2dfc8-180">**Verwenden der Benutzeroberfläche** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit der Benutzeroberfläche des Security & Compliance Centers.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-180">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="2dfc8-181">Mit dieser Methode können Sie reguläre Ausdrücke, Schlüsselwörter und Schlüsselwörterbücher verwenden.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-181">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="2dfc8-182">Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="2dfc8-182">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="2dfc8-183">**EDM verwenden** Sie können benutzerdefinierte Typen vertraulicher Informationen mit Hilfe der Exact Data Match (EDM)-basierten Klassifizierung einrichten.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-183">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="2dfc8-184">Mit dieser Methode können Sie anhand einer sicheren Datenbank, die sie regelmäßig aktualisieren können, einen dynamischen Typ vertraulicher Informationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-184">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="2dfc8-185">Mehr Informationen unter[Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="2dfc8-185">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="2dfc8-186">**Verwenden von PowerShell** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-186">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="2dfc8-187">Diese Methode ist zwar komplexer als die Verwendung der Benutzeroberfläche, Sie haben aber mehr Konfigurationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-187">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="2dfc8-188">Mehr Informationen unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="2dfc8-188">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="2dfc8-189">Verbesserte Konfidenzniveaus sind für die sofortige Verwendung innerhalb der Verhinderung von Datenverlust für Microsoft 365 Dienste, Microsoft Information Protection für Microsoft 365 Dienste, Kommunikationscompliance, Informationsgovernance und Datensatzverwaltung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-189">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>
> <span data-ttu-id="2dfc8-190">Microsoft 365 Information Protection unterstützt jetzt Doppelbyte-Zeichensatzsprachen für:</span><span class="sxs-lookup"><span data-stu-id="2dfc8-190">Microsoft 365 Information Protection now  supports double byte character set languages for:</span></span>
> - <span data-ttu-id="2dfc8-191">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="2dfc8-191">Chinese (simplified)</span></span>
> - <span data-ttu-id="2dfc8-192">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="2dfc8-192">Chinese (traditional)</span></span>
> - <span data-ttu-id="2dfc8-193">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="2dfc8-193">Korean</span></span>
> - <span data-ttu-id="2dfc8-194">Japanisch</span><span class="sxs-lookup"><span data-stu-id="2dfc8-194">Japanese</span></span>
> 
> <span data-ttu-id="2dfc8-195">Diese Unterstützung ist für vertrauliche Informationstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-195">This support is available for sensitive information types.</span></span> <span data-ttu-id="2dfc8-196">Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="2dfc8-196">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="2dfc8-197">Um Muster zu erkennen, die chinesische/japanische Zeichen und einzelne Bytezeichen enthalten, oder um Muster zu erkennen, die Chinesisch/Japanisch und Englisch enthalten, definieren Sie zwei Varianten des Schlüsselworts oder regulären Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-197">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span>
> 
> <span data-ttu-id="2dfc8-198">Verwenden Sie z. B. zwei Varianten des Schlüsselworts, um ein Schlüsselwort wie „机密的document“ zu erkennen; eine mit einem Leerzeichen zwischen dem japanischen und dem englischen Text und eine andere ohne Leerzeichen zwischen dem japanischen und dem englischen Text.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-198">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="2dfc8-199">Daher sollten die Schlüsselwörter, die in SIT hinzugefügt werden sollen, „机密的 document“ und „机密的document“ lauten.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-199">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="2dfc8-200">Ebenso sollten zwei Varianten verwendet werden, um den Ausdruck „東京オリンピック2020“ zu erkennen; „東京オリンピック 2020“ und „東京オリンピック2020“.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-200">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> 
> <span data-ttu-id="2dfc8-201">Achten Sie beim Erstellen eines regulären Ausdrucks mit einem Doppeltbyte-Bindestrich oder einem Doppeltbyte-Punkt darauf, beide Zeichen mit Escapezeichen zu versehen, so wie man einen Bindestrich oder einen Punkt in einem regulären Ausdruck mit Escapezeichen versehen würde.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-201">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex.</span></span> <span data-ttu-id="2dfc8-202">Hier sehen Sie ein Beispiel für einen regulären Ausdruck als Referenz:</span><span class="sxs-lookup"><span data-stu-id="2dfc8-202">Here is a sample regex for reference:</span></span>
>    - <span data-ttu-id="2dfc8-203">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="2dfc8-203">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
>
> <span data-ttu-id="2dfc8-204">Es wird empfohlen, die Zeichenfolgenüberstimmung anstelle der Wortüberstimmung in einer Schlüsselwortliste zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2dfc8-204">We recommend using string match instead of word match in a keyword list.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="2dfc8-205">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2dfc8-205">For further information</span></span>
- [<span data-ttu-id="2dfc8-206">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="2dfc8-206">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="2dfc8-207">Erstellen eines benutzerdefinierten vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="2dfc8-207">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="2dfc8-208">Erstellen eines benutzerdefinierten vertraulichen Informationstyps in PowerShell</span><span class="sxs-lookup"><span data-stu-id="2dfc8-208">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<span data-ttu-id="2dfc8-209">Informationen zur Verwendung vertraulicher Informationstypen zur Einhaltung von Datenschutzbestimmungen finden Sie unter [Bereitstellen des Informationsschutzes für Datenschutzbestimmungen mit Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span><span class="sxs-lookup"><span data-stu-id="2dfc8-209">To learn how to use sensitive information types to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
