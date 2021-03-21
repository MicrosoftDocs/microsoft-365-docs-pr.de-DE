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
ms.openlocfilehash: 12a4e8873cb7212bfa7dde12bba9e98528cd859a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919671"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="d9293-102">Weitere Informationen zu Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="d9293-102">Learn about sensitive information types</span></span>

<span data-ttu-id="d9293-103">Das Identifizieren und Klassifizieren vertraulicher Elemente, die sich unter der Kontrolle Ihrer Organisation befinden, ist der erste Schritt in der [Information Protection-Disziplin.](./information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="d9293-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](./information-protection.md).</span></span>  <span data-ttu-id="d9293-104">Microsoft 365 bietet drei Möglichkeiten zum Identifizieren von Elementen, sodass sie klassifiziert werden können:</span><span class="sxs-lookup"><span data-stu-id="d9293-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="d9293-105">manuell von Benutzern</span><span class="sxs-lookup"><span data-stu-id="d9293-105">manually by users</span></span>
- <span data-ttu-id="d9293-106">Automatische Mustererkennung, wie vertrauliche Informationstypen</span><span class="sxs-lookup"><span data-stu-id="d9293-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="d9293-107">maschinelles Lernen</span><span class="sxs-lookup"><span data-stu-id="d9293-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="d9293-108">Typen vertraulicher Informationen sind musterbasierte Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="d9293-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="d9293-109">Sie erkennen vertrauliche Informationen wie soziale Sicherheit, Kreditkarten- oder Bankkontonummern, um vertrauliche Elemente zu identifizieren. Weitere Informationen finden Sie unter [Entitätsdefinitionen](sensitive-information-type-entity-definitions.md) für Typen vertraulicher Informationen.</span><span class="sxs-lookup"><span data-stu-id="d9293-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="d9293-110">Typen vertraulicher Informationen werden in</span><span class="sxs-lookup"><span data-stu-id="d9293-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="d9293-111">Richtlinien zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="d9293-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="d9293-112">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="d9293-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="d9293-113">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="d9293-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="d9293-114">Kommunikationscompliance</span><span class="sxs-lookup"><span data-stu-id="d9293-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="d9293-115">Richtlinien für die automatische Kennzeichnung</span><span class="sxs-lookup"><span data-stu-id="d9293-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="d9293-116">Grundlegende Teile eines vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="d9293-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="d9293-117">Jede Entität vom Typ vertraulicher Informationen wird durch die folgenden Felder definiert:</span><span class="sxs-lookup"><span data-stu-id="d9293-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="d9293-118">Name: So wird auf den Typ vertraulicher Informationen verwiesen</span><span class="sxs-lookup"><span data-stu-id="d9293-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="d9293-119">description: beschreibt, wofür der Typ vertraulicher Informationen gesucht wird</span><span class="sxs-lookup"><span data-stu-id="d9293-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="d9293-120">pattern: Ein Muster definiert, was ein vertraulicher Informationstyp erkennt.</span><span class="sxs-lookup"><span data-stu-id="d9293-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="d9293-121">Es besteht aus den folgenden Komponenten</span><span class="sxs-lookup"><span data-stu-id="d9293-121">It consists of the following components</span></span>
    - <span data-ttu-id="d9293-122">Primäres Element – das Hauptelement, nach dem der Typ vertraulicher Informationen sucht.</span><span class="sxs-lookup"><span data-stu-id="d9293-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="d9293-123">Es kann sich um einen **regulären Ausdruck** mit oder ohne Prüfsummenüberprüfung, eine Schlüsselwortliste, ein  **Schlüsselwortwörterbuch** oder eine Funktion **sein.**</span><span class="sxs-lookup"><span data-stu-id="d9293-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="d9293-124">Unterstützendes Element – Elemente, die als unterstützende Nachweise fungieren, die dazu beitragen, das Vertrauen der Übereinstimmung zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="d9293-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="d9293-125">Beispiel: Schlüsselwort "SSN" in der Nähe einer SSN-Nummer.</span><span class="sxs-lookup"><span data-stu-id="d9293-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="d9293-126">Es kann ein regulärer Ausdruck mit oder ohne Prüfsummenüberprüfung, Stichwortliste, Schlüsselwortwörterbuch sein.</span><span class="sxs-lookup"><span data-stu-id="d9293-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="d9293-127">Konfidenzstufe – Konfidenzstufen (hoch, mittel, niedrig) spiegeln wider, wie viele unterstützende Nachweise zusammen mit dem primären Element erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="d9293-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="d9293-128">Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Sicherheit, dass ein übereinstimmendes Element die von Ihnen gesuchten vertraulichen Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="d9293-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="d9293-129">Näherung – Anzahl der Zeichen zwischen primärem und unterstützendem Element</span><span class="sxs-lookup"><span data-stu-id="d9293-129">Proximity – Number of characters between primary and supporting element</span></span>

![Diagramm von bestätigenden Nachweisen und Näherungsfenster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="d9293-131">Weitere Informationen zu Vertrauensebenen finden Sie in diesem Video.</span><span class="sxs-lookup"><span data-stu-id="d9293-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="d9293-132">Beispieltyp für vertrauliche Informationen</span><span class="sxs-lookup"><span data-stu-id="d9293-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="d9293-133">Nationale Identität (DNI) (Argentina National Identity)</span><span class="sxs-lookup"><span data-stu-id="d9293-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="d9293-134">Format</span><span class="sxs-lookup"><span data-stu-id="d9293-134">Format</span></span>

<span data-ttu-id="d9293-135">Acht Ziffern, durch Punkte getrennt</span><span class="sxs-lookup"><span data-stu-id="d9293-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="d9293-136">Muster</span><span class="sxs-lookup"><span data-stu-id="d9293-136">Pattern</span></span>

<span data-ttu-id="d9293-137">Acht Ziffern:</span><span class="sxs-lookup"><span data-stu-id="d9293-137">Eight digits:</span></span>
- <span data-ttu-id="d9293-138">zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="d9293-138">two digits</span></span>
- <span data-ttu-id="d9293-139">ein Zeitraum</span><span class="sxs-lookup"><span data-stu-id="d9293-139">a period</span></span>
- <span data-ttu-id="d9293-140">drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="d9293-140">three digits</span></span>
- <span data-ttu-id="d9293-141">ein Zeitraum</span><span class="sxs-lookup"><span data-stu-id="d9293-141">a period</span></span>
- <span data-ttu-id="d9293-142">drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="d9293-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d9293-143">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d9293-143">Checksum</span></span>

<span data-ttu-id="d9293-144">Nein</span><span class="sxs-lookup"><span data-stu-id="d9293-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="d9293-145">Definition</span><span class="sxs-lookup"><span data-stu-id="d9293-145">Definition</span></span>

<span data-ttu-id="d9293-146">Eine DLP-Richtlinie hat mittlere Sicherheit, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb einer Nähe von 300 Zeichen:</span><span class="sxs-lookup"><span data-stu-id="d9293-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d9293-147">Der reguläre Ausdruck Regex_argentina_national_id findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d9293-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d9293-148">Ein Schlüsselwort aus Keyword_argentina_national_id gefunden.</span><span class="sxs-lookup"><span data-stu-id="d9293-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9293-149">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d9293-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="d9293-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="d9293-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="d9293-151">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="d9293-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="d9293-152">Identität</span><span class="sxs-lookup"><span data-stu-id="d9293-152">Identity</span></span> 
- <span data-ttu-id="d9293-153">Identifikation der nationalen Identitätskarte</span><span class="sxs-lookup"><span data-stu-id="d9293-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="d9293-154">DNI</span><span class="sxs-lookup"><span data-stu-id="d9293-154">DNI</span></span> 
- <span data-ttu-id="d9293-155">Nationales NIC-Personenregister</span><span class="sxs-lookup"><span data-stu-id="d9293-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="d9293-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="d9293-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="d9293-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="d9293-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="d9293-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="d9293-158">Identidad</span></span> 
- <span data-ttu-id="d9293-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="d9293-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="d9293-160">Weitere Informationen zu Konfidenzstufen</span><span class="sxs-lookup"><span data-stu-id="d9293-160">More on confidence levels</span></span>

<span data-ttu-id="d9293-161">In einer Entitätsdefinition für vertrauliche **Informationstypen** gibt die Konfidenzstufe an, wie viele unterstützende Nachweise zusätzlich zum primären Element erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="d9293-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="d9293-162">Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Sicherheit, dass ein übereinstimmendes Element die von Ihnen gesuchten vertraulichen Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="d9293-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="d9293-163">Beispielsweise enthalten Übereinstimmungen mit einem hohen Konfidenzniveau mehr nachweisende Nachweise in unmittelbarer Nähe des primären Elements, während Übereinstimmungen mit einem niedrigen Konfidenzniveau nur wenig bis keine Nachweise in unmittelbarer Nähe enthalten würden.</span><span class="sxs-lookup"><span data-stu-id="d9293-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="d9293-164">Ein hohes Konfidenzniveau gibt die wenigsten falsch positiven Ergebnisse zurück, kann jedoch zu weiteren falsch negativen Folgen führen.</span><span class="sxs-lookup"><span data-stu-id="d9293-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="d9293-165">Niedrige oder mittlere Konfidenzstufen geben mehr falsch positive Werte zurück, aber nur wenige bis null falsch negative Werte.</span><span class="sxs-lookup"><span data-stu-id="d9293-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="d9293-166">**niedrige Konfidenz**: Der Wert von 65, übereinstimmende Elemente enthalten die wenigsten falsch negativen, aber die meisten falsch positiven Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="d9293-166">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="d9293-167">Niedrige Konfidenz gibt alle Übereinstimmungen mit niedriger, mittlerer und hoher Konfidenz zurück.</span><span class="sxs-lookup"><span data-stu-id="d9293-167">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="d9293-168">**mittlere Konfidenz**: Der Wert von 75, übereinstimmende Elemente enthalten eine durchschnittliche Menge falsch positiver und falsch negativer Werte.</span><span class="sxs-lookup"><span data-stu-id="d9293-168">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="d9293-169">Mittlere Konfidenz gibt alle übereinstimmungen mit mittlerer und hoher Vertrauenssicherheit zurück.</span><span class="sxs-lookup"><span data-stu-id="d9293-169">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="d9293-170">**hohe Konfidenz**: Der Wert von 85, übereinstimmende Elemente enthalten die wenigsten falsch positiven, aber die meisten falsch negativen.</span><span class="sxs-lookup"><span data-stu-id="d9293-170">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="d9293-171">Hohe Vertrauenssicherheit gibt nur Übereinstimmungen mit hoher Vertrauenssicherheit zurück.</span><span class="sxs-lookup"><span data-stu-id="d9293-171">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="d9293-172">Sie sollten Muster mit hoher Konfidenzstufe mit niedrigen Zählungen(z. B. fünf bis zehn) und niedrigen Konfidenzmustern mit höheren Zählungen (z. B. 20 oder mehr) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9293-172">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="d9293-173">Wenn Sie vorhandene Richtlinien oder benutzerdefinierte Typen vertraulicher Informationen (SITs) mithilfe von zahlenbasierten Konfidenzstufen (auch als Genauigkeit bekannt) definiert haben, werden sie automatisch den drei diskreten Zuverlässigkeitsstufen zugeordnet. geringes Vertrauen, mittleres Vertrauen und hohe Vertrauenssicherheit auf der Benutzeroberfläche des Security @ Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="d9293-173">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="d9293-174">Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierten SIT-Mustern mit Konfidenzstufen zwischen 76 und 100 werden einer hohen Zuverlässigkeit zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d9293-174">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="d9293-175">Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierten SIT-Mustern mit Konfidenzstufen zwischen 66 und 75 werden mittlerer Zuverlässigkeit zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d9293-175">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="d9293-176">Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierten SIT-Mustern mit Konfidenzstufen kleiner oder gleich 65 werden einer niedrigen Zuverlässigkeit zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d9293-176">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="d9293-177">Benutzerdefinierte Typen vertraulicher Informationen erstellen</span><span class="sxs-lookup"><span data-stu-id="d9293-177">Creating custom sensitive information types</span></span>

<span data-ttu-id="d9293-178">Zum Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center stehen Ihnen mehrere Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="d9293-178">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="d9293-179">**Verwenden der Benutzeroberfläche** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit der Benutzeroberfläche des Security & Compliance Centers.</span><span class="sxs-lookup"><span data-stu-id="d9293-179">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="d9293-180">Mit dieser Methode können Sie reguläre Ausdrücke, Schlüsselwörter und Schlüsselwörterbücher verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9293-180">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="d9293-181">Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="d9293-181">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="d9293-182">**EDM verwenden** Sie können benutzerdefinierte Typen vertraulicher Informationen mit Hilfe der Exact Data Match (EDM)-basierten Klassifizierung einrichten.</span><span class="sxs-lookup"><span data-stu-id="d9293-182">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="d9293-183">Mit dieser Methode können Sie anhand einer sicheren Datenbank, die sie regelmäßig aktualisieren können, einen dynamischen Typ vertraulicher Informationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d9293-183">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="d9293-184">Mehr Informationen unter[Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="d9293-184">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="d9293-185">**Verwenden von PowerShell** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9293-185">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="d9293-186">Diese Methode ist zwar komplexer als die Verwendung der Benutzeroberfläche, Sie haben aber mehr Konfigurationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="d9293-186">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="d9293-187">Mehr Informationen unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d9293-187">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="d9293-188">Verbesserte Vertrauensebenen stehen für die sofortige Verwendung in der Verhinderung von Datenverlust für Microsoft 365-Dienste, Microsoft Information Protection für Microsoft 365-Dienste, Kommunikationskonformität, Informations-Governance und Datensatzverwaltung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d9293-188">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="d9293-189">Microsoft 365 Information Protection unterstützt jetzt in der Vorschau Doppelbyte-Zeichensatz-Sprachen für:</span><span class="sxs-lookup"><span data-stu-id="d9293-189">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="d9293-190">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="d9293-190">Chinese (simplified)</span></span>
> - <span data-ttu-id="d9293-191">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="d9293-191">Chinese (traditional)</span></span>
> - <span data-ttu-id="d9293-192">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="d9293-192">Korean</span></span>
> - <span data-ttu-id="d9293-193">Japanisch</span><span class="sxs-lookup"><span data-stu-id="d9293-193">Japanese</span></span>

><span data-ttu-id="d9293-194">Diese Unterstützung ist für vertrauliche Informationstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d9293-194">This support is available for sensitive information types.</span></span> <span data-ttu-id="d9293-195">Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="d9293-195">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="d9293-196">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9293-196">For further information</span></span>
- [<span data-ttu-id="d9293-197">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="d9293-197">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="d9293-198">Erstellen eines benutzerdefinierten vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="d9293-198">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="d9293-199">Erstellen eines benutzerdefinierten vertraulichen Informationstyps in PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9293-199">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->