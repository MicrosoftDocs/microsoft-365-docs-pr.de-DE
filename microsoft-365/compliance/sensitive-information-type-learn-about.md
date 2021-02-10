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
ms.openlocfilehash: 91366e8f255d277d4d40de4c4cd3330283da718c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166450"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="ccb4a-102">Weitere Informationen zu Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="ccb4a-102">Learn about sensitive information types</span></span>

<span data-ttu-id="ccb4a-103">Das Identifizieren und Klassifizieren vertraulicher Elemente, die von Ihren Organisationen kontrolliert werden, ist der erste Schritt in der Information [Protection-Teilung.](protect-information.md)</span><span class="sxs-lookup"><span data-stu-id="ccb4a-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="ccb4a-104">Microsoft 365 bietet drei Möglichkeiten zum Identifizieren von Elementen, sodass sie klassifiziert werden können:</span><span class="sxs-lookup"><span data-stu-id="ccb4a-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="ccb4a-105">manuell von Benutzern</span><span class="sxs-lookup"><span data-stu-id="ccb4a-105">manually by users</span></span>
- <span data-ttu-id="ccb4a-106">Automatisierte Mustererkennung, wie vertrauliche Informationstypen</span><span class="sxs-lookup"><span data-stu-id="ccb4a-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="ccb4a-107">Machine Learning</span><span class="sxs-lookup"><span data-stu-id="ccb4a-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="ccb4a-108">Vertrauliche Informationstypen sind musterbasierte Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="ccb4a-109">Sie erkennen vertrauliche Informationen wie Sozialversicherungs-, Kreditkarten- oder Bankkontonummern, um vertrauliche Elemente zu identifizieren. Weitere Informationen finden Sie unter Entitätsdefinitionen für Typen [vertraulicher Informationen.](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="ccb4a-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="ccb4a-110">Typen vertraulicher Informationen werden in</span><span class="sxs-lookup"><span data-stu-id="ccb4a-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="ccb4a-111">Richtlinien zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="ccb4a-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="ccb4a-112">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ccb4a-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="ccb4a-113">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ccb4a-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="ccb4a-114">Kommunikationscompliance</span><span class="sxs-lookup"><span data-stu-id="ccb4a-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="ccb4a-115">Richtlinien für die automatische Kennzeichnung</span><span class="sxs-lookup"><span data-stu-id="ccb4a-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="ccb4a-116">Grundlegende Teile eines vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="ccb4a-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="ccb4a-117">Jede Entität für vertrauliche Informationstypen wird durch die folgenden Felder definiert:</span><span class="sxs-lookup"><span data-stu-id="ccb4a-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="ccb4a-118">name: how the sensitive information type isreferred to</span><span class="sxs-lookup"><span data-stu-id="ccb4a-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="ccb4a-119">description: beschreibt, wo nach dem Typ vertraulicher Informationen gesucht wird</span><span class="sxs-lookup"><span data-stu-id="ccb4a-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="ccb4a-120">muster: Ein Muster definiert, was ein vertraulicher Informationstyp erkennt.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="ccb4a-121">Sie besteht aus den folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="ccb4a-121">It consists of the following components</span></span>
    - <span data-ttu-id="ccb4a-122">Primäres Element – das Hauptelement, nach dem der Typ vertraulicher Informationen sucht.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="ccb4a-123">Es kann sich um einen regulären **Ausdruck** mit oder ohne Prüfsummenüberprüfung, eine **Schlüsselwortliste,** ein **Schlüsselwortwörterbuch** oder eine Funktion **sein.**</span><span class="sxs-lookup"><span data-stu-id="ccb4a-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="ccb4a-124">Unterstützendes Element – Elemente, die als unterstützende Nachweise fungieren, die dazu beitragen, die Konfidenz der Übereinstimmung zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="ccb4a-125">Beispiel: Schlüsselwort "SSN" in der Nähe einer SSN-Nummer.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="ccb4a-126">Dabei kann es sich um einen regulären Ausdruck mit oder ohne Prüfsummenüberprüfung, Stichwortliste und Schlüsselwortverzeichnis sein.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="ccb4a-127">Konfidenzniveau – Die Konfidenzniveaus (hoch, mittel, niedrig) spiegeln wider, wie viele unterstützende Nachweise zusammen mit dem primären Element erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="ccb4a-128">Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Konfidenz, dass ein übereinstimmende Element die vertraulichen Informationen enthält, die Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="ccb4a-129">Näherung – Anzahl der Zeichen zwischen primärem und unterstützendem Element</span><span class="sxs-lookup"><span data-stu-id="ccb4a-129">Proximity – Number of characters between primary and supporting element</span></span>

![Diagramm von bestätigenden Nachweisen und Näherungsfenster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="ccb4a-131">Weitere Informationen zu Vertrauensebenen finden Sie in diesem Video.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="ccb4a-132">Beispiel für vertraulichen Informationstyp</span><span class="sxs-lookup"><span data-stu-id="ccb4a-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="ccb4a-133">Argentinien – Nationale Identitätsnummer (DNI)</span><span class="sxs-lookup"><span data-stu-id="ccb4a-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="ccb4a-134">Format</span><span class="sxs-lookup"><span data-stu-id="ccb4a-134">Format</span></span>

<span data-ttu-id="ccb4a-135">Acht Ziffern, durch Punkte getrennt</span><span class="sxs-lookup"><span data-stu-id="ccb4a-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="ccb4a-136">Muster</span><span class="sxs-lookup"><span data-stu-id="ccb4a-136">Pattern</span></span>

<span data-ttu-id="ccb4a-137">Acht Ziffern:</span><span class="sxs-lookup"><span data-stu-id="ccb4a-137">Eight digits:</span></span>
- <span data-ttu-id="ccb4a-138">zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="ccb4a-138">two digits</span></span>
- <span data-ttu-id="ccb4a-139">ein Zeitraum</span><span class="sxs-lookup"><span data-stu-id="ccb4a-139">a period</span></span>
- <span data-ttu-id="ccb4a-140">drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="ccb4a-140">three digits</span></span>
- <span data-ttu-id="ccb4a-141">ein Zeitraum</span><span class="sxs-lookup"><span data-stu-id="ccb4a-141">a period</span></span>
- <span data-ttu-id="ccb4a-142">drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="ccb4a-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ccb4a-143">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="ccb4a-143">Checksum</span></span>

<span data-ttu-id="ccb4a-144">Nein</span><span class="sxs-lookup"><span data-stu-id="ccb4a-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="ccb4a-145">Definition</span><span class="sxs-lookup"><span data-stu-id="ccb4a-145">Definition</span></span>

<span data-ttu-id="ccb4a-146">Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:</span><span class="sxs-lookup"><span data-stu-id="ccb4a-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ccb4a-147">Der reguläre Ausdruck Regex_argentina_national_id findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ccb4a-148">Ein Schlüsselwort aus Keyword_argentina_national_id gefunden.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ccb4a-149">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ccb4a-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="ccb4a-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="ccb4a-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="ccb4a-151">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="ccb4a-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="ccb4a-152">Identität</span><span class="sxs-lookup"><span data-stu-id="ccb4a-152">Identity</span></span> 
- <span data-ttu-id="ccb4a-153">Identification National Identity Card</span><span class="sxs-lookup"><span data-stu-id="ccb4a-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="ccb4a-154">DNI</span><span class="sxs-lookup"><span data-stu-id="ccb4a-154">DNI</span></span> 
- <span data-ttu-id="ccb4a-155">Nationales NIC-Registrierungsregister von Personen</span><span class="sxs-lookup"><span data-stu-id="ccb4a-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="ccb4a-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="ccb4a-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="ccb4a-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="ccb4a-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="ccb4a-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="ccb4a-158">Identidad</span></span> 
- <span data-ttu-id="ccb4a-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="ccb4a-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="ccb4a-160">Weitere Informationen zu Vertrauensebenen</span><span class="sxs-lookup"><span data-stu-id="ccb4a-160">More on confidence levels</span></span>

<span data-ttu-id="ccb4a-161">In einer Entitätsdefinition für vertrauliche Informationstypen spiegelt die Konfidenzstufe **wider,** wie viele unterstützende Nachweise zusätzlich zum primären Element erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="ccb4a-162">Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Konfidenz, dass ein übereinstimmende Element die vertraulichen Informationen enthält, die Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="ccb4a-163">Übereinstimmungen mit einem hohen Konfidenzniveau enthalten beispielsweise mehr unterstützende Nachweise in der Nähe des primären Elements, während Übereinstimmungen mit einem niedrigen Konfidenzniveau nur wenig bis keine unterstützenden Nachweise in unmittelbarer Nähe enthalten würden.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="ccb4a-164">Ein hoher Konfidenzniveau gibt die wenigsten falsch positiven Ergebnisse zurück, kann jedoch zu mehr falsch negativen Ergebnisse führen.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="ccb4a-165">Niedrige oder mittlere Konfidenzstufen geben mehr falsch positive Ergebnisse zurück, aber nur wenige bis null falsch negative Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="ccb4a-166">**niedrige Konfidenz:** Wert 65, übereinstimmende Elemente enthalten die wenigsten falsch negativen Ergebnisse, aber die meisten falsch positiven Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-166">**low confidence**: value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span>  
- <span data-ttu-id="ccb4a-167">**mittlere Konfidenz:** Wert 75, übereinstimmende Elemente enthalten eine durchschnittliche Menge falsch positiver und falsch negativer Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-167">**medium confidence**: value of 75, matched items will contain an average amount of false positives and false negatives.</span></span>  
- <span data-ttu-id="ccb4a-168">**hohe Konfidenz:** Wert 85, übereinstimmende Elemente enthalten die wenigsten falsch positiven Ergebnisse, aber die meisten falsch negativen Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-168">**high confidence**: value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span>  

<span data-ttu-id="ccb4a-169">Sie sollten Muster mit hoher Vertrauensebene mit geringer Anzahl verwenden, z. B. 5 bis 10, und Muster mit niedriger Konfidenz mit höherer Anzahl, z. B. 20 oder mehr.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-169">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="ccb4a-170">Benutzerdefinierte Typen vertraulicher Informationen erstellen</span><span class="sxs-lookup"><span data-stu-id="ccb4a-170">Creating custom sensitive information types</span></span>

<span data-ttu-id="ccb4a-171">Zum Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center stehen Ihnen mehrere Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="ccb4a-171">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="ccb4a-172">**Verwenden der Benutzeroberfläche** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit der Benutzeroberfläche des Security & Compliance Centers.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-172">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="ccb4a-173">Mit dieser Methode können Sie reguläre Ausdrücke, Schlüsselwörter und Schlüsselwörterbücher verwenden.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-173">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="ccb4a-174">Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="ccb4a-174">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="ccb4a-175">**EDM verwenden** Sie können benutzerdefinierte Typen vertraulicher Informationen mit Hilfe der Exact Data Match (EDM)-basierten Klassifizierung einrichten.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-175">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="ccb4a-176">Mit dieser Methode können Sie anhand einer sicheren Datenbank, die sie regelmäßig aktualisieren können, einen dynamischen Typ vertraulicher Informationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-176">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="ccb4a-177">Mehr Informationen unter[Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="ccb4a-177">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="ccb4a-178">**Verwenden von PowerShell** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-178">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="ccb4a-179">Diese Methode ist zwar komplexer als die Verwendung der Benutzeroberfläche, Sie haben aber mehr Konfigurationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-179">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="ccb4a-180">Mehr Informationen unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ccb4a-180">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="ccb4a-181">Verbesserte Vertrauensebenen sind für die sofortige Verwendung in der Verhinderung von Datenverlust für Microsoft 365-Dienste, Microsoft Information Protection für Microsoft 365-Dienste, Kommunikationskonformität, Informationssteuerung und Datensatzverwaltung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-181">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="ccb4a-182">Microsoft 365 Information Protection unterstützt jetzt in der Vorschau Doppelbyte-Zeichensatz-Sprachen für:</span><span class="sxs-lookup"><span data-stu-id="ccb4a-182">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="ccb4a-183">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="ccb4a-183">Chinese (simplified)</span></span>
> - <span data-ttu-id="ccb4a-184">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="ccb4a-184">Chinese (traditional)</span></span>
> - <span data-ttu-id="ccb4a-185">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="ccb4a-185">Korean</span></span>
> - <span data-ttu-id="ccb4a-186">Japanisch</span><span class="sxs-lookup"><span data-stu-id="ccb4a-186">Japanese</span></span>

><span data-ttu-id="ccb4a-187">Diese Unterstützung ist für vertrauliche Informationstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-187">This support is available for sensitive information types.</span></span> <span data-ttu-id="ccb4a-188">Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="ccb4a-188">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="ccb4a-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccb4a-189">For further information</span></span>
- [<span data-ttu-id="ccb4a-190">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="ccb4a-190">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="ccb4a-191">Erstellen eines benutzerdefinierten vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="ccb4a-191">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="ccb4a-192">Erstellen eines benutzerdefinierten vertraulichen Informationstyps in PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccb4a-192">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
