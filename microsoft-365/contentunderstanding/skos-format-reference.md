---
title: SKOS-Formatreferenz für SharePoint-Taxonomie
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: SKOS-Formatreferenz für SharePoint-Taxonomie
ms.openlocfilehash: 90c20ddb440e216941a5ea06f1aa815cb80102a9
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087279"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="4b71e-103">SKOS-Formatreferenz für SharePoint-Taxonomie</span><span class="sxs-lookup"><span data-stu-id="4b71e-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="4b71e-104">Dieser Artikel enthält RDF-Vokabular, das zur Darstellung der [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) verwendet wird, und basiert auf [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="4b71e-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="4b71e-105">Zur Serialisierung dieser RDF-Syntax verwenden Sie RDF [TURTLE](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="4b71e-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="4b71e-106">Die folgende Tabelle zeigt die [SKOS](https://www.w3.org/TR/skos-primer/)-Entsprechungen für das Vokabular der [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="4b71e-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="4b71e-107">SharePoint unterstützt keine [SKOS](https://www.w3.org/TR/skos-primer/)-Werte, die keine SharePoint-Entsprechung zur Taxonomie aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4b71e-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="4b71e-108">SharePoint-Taxonomie</span><span class="sxs-lookup"><span data-stu-id="4b71e-108">SharePoint taxonomy</span></span>|<span data-ttu-id="4b71e-109">SKOS-Entsprechung</span><span class="sxs-lookup"><span data-stu-id="4b71e-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="4b71e-110">sharepoint-taxonomy:Term</span><span class="sxs-lookup"><span data-stu-id="4b71e-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="4b71e-111">skos:Concept</span><span class="sxs-lookup"><span data-stu-id="4b71e-111">skos:Concept</span></span>|
|<span data-ttu-id="4b71e-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="4b71e-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="4b71e-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="4b71e-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="4b71e-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="4b71e-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="4b71e-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="4b71e-115">skos:inScheme</span></span>|
|<span data-ttu-id="4b71e-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="4b71e-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="4b71e-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="4b71e-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="4b71e-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="4b71e-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="4b71e-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="4b71e-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="4b71e-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="4b71e-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="4b71e-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="4b71e-121">skos:prefLabel</span></span>|
|<span data-ttu-id="4b71e-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="4b71e-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="4b71e-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="4b71e-123">skos:prefLabel</span></span>|
|<span data-ttu-id="4b71e-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="4b71e-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="4b71e-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="4b71e-125">skos:prefLabel</span></span>|
|<span data-ttu-id="4b71e-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="4b71e-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="4b71e-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="4b71e-127">skos:altLabel</span></span>|
|<span data-ttu-id="4b71e-128">sharepoint-taxonomy:description</span><span class="sxs-lookup"><span data-stu-id="4b71e-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="4b71e-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="4b71e-129">skos:definition</span></span>|
|<span data-ttu-id="4b71e-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="4b71e-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="4b71e-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="4b71e-131">skos:broader</span></span>|
|<span data-ttu-id="4b71e-132">sharepoint-taxonomy:child</span><span class="sxs-lookup"><span data-stu-id="4b71e-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="4b71e-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="4b71e-133">skos:narrower</span></span>|

<span data-ttu-id="4b71e-134">Die folgende Tabelle zeigt die Entitäten des aus [OWL](https://www.w3.org/TR/owl2-primer/) abgeleiteten Vokabulars der SharePoint-Taxonomie.</span><span class="sxs-lookup"><span data-stu-id="4b71e-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="4b71e-135">SharePoint-Taxonomie – Vokabular</span><span class="sxs-lookup"><span data-stu-id="4b71e-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="4b71e-136">Abgeleitet von OWL</span><span class="sxs-lookup"><span data-stu-id="4b71e-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="4b71e-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="4b71e-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="4b71e-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="4b71e-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="4b71e-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="4b71e-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="4b71e-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="4b71e-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="4b71e-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="4b71e-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="4b71e-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="4b71e-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="4b71e-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="4b71e-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="4b71e-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="4b71e-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="4b71e-145">SharePoint-Taxonomie – Vokabular</span><span class="sxs-lookup"><span data-stu-id="4b71e-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="4b71e-146">Bei einer Taxonomie handelt es sich um ein formales Klassifizierungssystem.</span><span class="sxs-lookup"><span data-stu-id="4b71e-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="4b71e-147">Eine Taxonomie gruppiert die Wörter, Bezeichnungen und Ausdrücke, die etwas beschreiben, und ordnet die Gruppen hierarchisch an.</span><span class="sxs-lookup"><span data-stu-id="4b71e-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="4b71e-148">**sharepoint-taxonomy:Term**</span><span class="sxs-lookup"><span data-stu-id="4b71e-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="4b71e-149">Stellt einen Ausdruck oder ein Schlüsselwort in einer verwalteten Metadatenhierarchie dar.</span><span class="sxs-lookup"><span data-stu-id="4b71e-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="4b71e-150">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ist die atomare Einheit eines SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="4b71e-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="4b71e-151">Jeder [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) gehört zu einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) der zu einer [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group) gehört.</span><span class="sxs-lookup"><span data-stu-id="4b71e-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="4b71e-152">Die Syntax zum Definieren eines [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4b71e-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="4b71e-153">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) existiert obligatorisch innerhalb eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="4b71e-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="4b71e-154">DefaultLabel ist der Name des [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) wie er in der visuellen Darstellung dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b71e-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="4b71e-155">Die erforderlichen Felder zum Definieren eines [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) enthalten:</span><span class="sxs-lookup"><span data-stu-id="4b71e-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="4b71e-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="4b71e-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="4b71e-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="4b71e-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="4b71e-158">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann:</span><span class="sxs-lookup"><span data-stu-id="4b71e-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="4b71e-159">Hierarchisch mit einem anderen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in Beziehung gesetzt werden, vorausgesetzt, beide [Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) gehören zum selben [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="4b71e-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="4b71e-160">Mehrere untergeordnete [Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) haben, aber nur einen einzigen übergeordneten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="4b71e-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="4b71e-161">Keinen übergeordneten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) definiert haben, wenn es sich um einen topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) handelt.</span><span class="sxs-lookup"><span data-stu-id="4b71e-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="4b71e-162">Ein defaultLabel pro [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-Arbeitssprache haben. </span><span class="sxs-lookup"><span data-stu-id="4b71e-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="4b71e-163">Nicht existieren, wenn es weder einen übergeordneten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) enthält, noch der TopLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) ist.</span><span class="sxs-lookup"><span data-stu-id="4b71e-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="4b71e-164">Nur ein eindeutiges defaultLabel in der gleichen hierarchischen Ebene haben.</span><span class="sxs-lookup"><span data-stu-id="4b71e-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="4b71e-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="4b71e-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="4b71e-166">Stellt einen hierarchischen oder unstrukturierten Satz von Term-Objekten dar, die als "Ausdruckssatz" bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="4b71e-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="4b71e-167">Wie der Name sagt, ist TermSet ein Satz von [Ausdrücken](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="4b71e-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="4b71e-168">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in einem [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) muss in einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) gehören.</span><span class="sxs-lookup"><span data-stu-id="4b71e-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="4b71e-169">Kein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann unabhängig voneinander vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4b71e-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="4b71e-170">Die Syntax zum Definieren eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="4b71e-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) werden logisch in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)gruppiert.</span><span class="sxs-lookup"><span data-stu-id="4b71e-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="4b71e-172">Das erforderliche Feld zum Definieren eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="4b71e-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="4b71e-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="4b71e-174">Wenn der angegebene termSetName innerhalb der [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group) nicht eindeutig ist, hängt SharePoint eine Nummer an das Ende des Namens an, um die Eindeutigkeit von termSetName(s) beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="4b71e-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="4b71e-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="4b71e-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="4b71e-176">SharePoint verwendet diese Eigenschaft zum Zuordnen des obersten [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) im [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), der den Einstiegspunkt zur Hierarchie der[Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) darstellt.</span><span class="sxs-lookup"><span data-stu-id="4b71e-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="4b71e-177">Hierbei handelt es sich um einen umgekehrten Bezug zu sharepoint-taxonomy:topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="4b71e-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="4b71e-178">Die Syntax, um dies zu definieren, lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="4b71e-179">Sie können den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) der obersten Ebene eines übergeordneten [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nicht definieren.</span><span class="sxs-lookup"><span data-stu-id="4b71e-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="4b71e-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="4b71e-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="4b71e-181">Sharepoint-taxonomy:topLevelTermOf ist die Umkehrung der sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="4b71e-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="4b71e-182">Die Syntax, um dies zu definieren, lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="4b71e-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="4b71e-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="4b71e-184">Hiermit ordnen Sie einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) zu.</span><span class="sxs-lookup"><span data-stu-id="4b71e-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="4b71e-185">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann nur in einem einzigen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4b71e-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="4b71e-186">SharePoint erfordert diese Eigenschaft beim [Definieren eines Ausdrucks](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="4b71e-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="4b71e-187">Erforderliche Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="4b71e-187">Required labels</span></span>

<span data-ttu-id="4b71e-188">Möglicherweise möchte Ihre Organisation eine sorgfältige Planung vornehmen, bevor Sie mit der Verwendung verwalteter Metadaten beginnen.</span><span class="sxs-lookup"><span data-stu-id="4b71e-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="4b71e-189">Der Umfang der Planung, die Sie vornehmen müssen, hängt davon ab, wie formal Ihre Taxonomie ist.</span><span class="sxs-lookup"><span data-stu-id="4b71e-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="4b71e-190">Es hängt auch davon ab, wie viel Kontrolle Sie den Metadaten auferlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="4b71e-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="4b71e-191">Auf jeder Ebene der Hierarchie müssen Sie die erforderlichen Bezeichnungen für einen Ausdruck oder ein TermSet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4b71e-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="4b71e-192">Ein Ausdruck kann eine oder mehrere Bezeichnungen in der Standardsprache haben, und keine oder mehrere Bezeichnungen in einer anderen als der Standardsprache.</span><span class="sxs-lookup"><span data-stu-id="4b71e-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="4b71e-193">Wenn der Ausdruck Bezeichnungen in einer Sprache hat, muss eine der Bezeichnungen die Standardbezeichnung sein.</span><span class="sxs-lookup"><span data-stu-id="4b71e-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="4b71e-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="4b71e-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="4b71e-195">Verwenden Sie diese standardmäßige lexikalische Bezeichnung für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), der ein erforderlicher Parameter für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ist.</span><span class="sxs-lookup"><span data-stu-id="4b71e-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="4b71e-196">Wird verwendet, um den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) darzustellen.</span><span class="sxs-lookup"><span data-stu-id="4b71e-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="4b71e-197">Die Syntax zum Definieren eines defaultLabel lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="4b71e-198">Der defaultLabel enthält zwei Teile: die Zeichenfolge und das Sprachentag.</span><span class="sxs-lookup"><span data-stu-id="4b71e-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="4b71e-199">Die Sprache muss eine der [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-Arbeitssprachen sein.</span><span class="sxs-lookup"><span data-stu-id="4b71e-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="4b71e-200">Der defaultLabel muss für alle [Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) desselben [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) auf derselben hierarchischen Ebene eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="4b71e-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="4b71e-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="4b71e-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="4b71e-202">Ruft den Namen für das aktuelle TermSet-Objekt ab und legt ihn fest.</span><span class="sxs-lookup"><span data-stu-id="4b71e-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="4b71e-203">Hierbei handelt es sich um die lexikalische Bezeichnung für einen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) in einer [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-Arbeitssprache.</span><span class="sxs-lookup"><span data-stu-id="4b71e-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="4b71e-204">Dieser Parameter ist für einen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) erforderlich..</span><span class="sxs-lookup"><span data-stu-id="4b71e-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="4b71e-205">Wird verwendet, um einen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) darzustellen.</span><span class="sxs-lookup"><span data-stu-id="4b71e-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="4b71e-206">Die Syntax zum Definieren eines termSetName lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="4b71e-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="4b71e-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="4b71e-208">Ruft den Eigenschaftennamen für das aktuelle TermSet-Objekt ab und legt ihn fest.</span><span class="sxs-lookup"><span data-stu-id="4b71e-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="4b71e-209">Dies ist die lexikalische Bezeichnung für eine sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm und sharepoint-taxonomy:CustomPropertyForTermSet in einer [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-Arbeitssprache.</span><span class="sxs-lookup"><span data-stu-id="4b71e-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="4b71e-210">Der sharepoint-taxonomy:propertyName wird als Schlüssel der CustomProperty behandelt.</span><span class="sxs-lookup"><span data-stu-id="4b71e-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="4b71e-211">Die Syntax zum Definieren eines propetyName lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="4b71e-212">Optionale Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="4b71e-212">Optional labels</span></span>

<span data-ttu-id="4b71e-213">Sie können Ihrer Taxonomie auch optionale Bezeichnungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4b71e-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="4b71e-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="4b71e-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="4b71e-215">Dies ist die Alternative lexikalische Bezeichnung für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="4b71e-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="4b71e-216">Die Syntax zum Definieren eines otherLabel lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="4b71e-217">Semantische Beziehungen</span><span class="sxs-lookup"><span data-stu-id="4b71e-217">Semantic relationships</span></span>

<span data-ttu-id="4b71e-218">Taxonomien haben hierarchische und manchmal eine einfache assoziative Beziehung zu einem " verwandten Ausdruck", aber einige haben "semantische Beziehungen" oder benutzerdefinierte Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="4b71e-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="4b71e-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="4b71e-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="4b71e-220">Damit wird ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) hierarchisch zu einem anderen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in Beziehung gesetzt.</span><span class="sxs-lookup"><span data-stu-id="4b71e-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="4b71e-221">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) könnte ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) der obersten Ebene eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) sein, aber falls dies nicht der Fall ist, muss es einen übergeordneten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4b71e-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="4b71e-222">Die Syntax zum Definieren eines übergeordneten Elements lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="4b71e-223">Dies bedeutet, dass TermA das übergeordnete Element und TermA das untergeordnete Element ist.</span><span class="sxs-lookup"><span data-stu-id="4b71e-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="4b71e-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="4b71e-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="4b71e-225">Das Objekt enthält eine oder mehrere untergeordnete TermSet-Instanzen, auf die über die TermSets-Eigenschaft zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4b71e-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="4b71e-226">Diese Klasse bietet auch Methoden zum Erstellen neuer untergeordneter TermSet-Objekte.</span><span class="sxs-lookup"><span data-stu-id="4b71e-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="4b71e-227">Die Berechtigungen zum Bearbeiten untergeordneter Ausdruck- und TermSet-Instanzen werden in der Gruppe angegeben.</span><span class="sxs-lookup"><span data-stu-id="4b71e-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="4b71e-228">Damit wird ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) hierarchisch zu einem anderen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in Beziehung gesetzt.</span><span class="sxs-lookup"><span data-stu-id="4b71e-228">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="4b71e-229">Die Syntax zum Definieren eines untergeordneten Elements lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="4b71e-230">Dies bedeutet, dass TermA das übergeordnete Element und TermA das untergeordnete Element ist.</span><span class="sxs-lookup"><span data-stu-id="4b71e-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="4b71e-231">Dokumentationsnotizen</span><span class="sxs-lookup"><span data-stu-id="4b71e-231">Documentation notes</span></span>

<span data-ttu-id="4b71e-232">Dieser Abschnitt behandelt die Taxonomie, die im Microsoft.SharePoint.Taxonomie "Namespace" detailliert beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="4b71e-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="4b71e-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="4b71e-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="4b71e-234">Dies ist eine detaillierte Erklärung jeder Entität des Vokabulars der [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="4b71e-234">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="4b71e-235">Die Syntax für das Hinzufügen einer Beschreibung lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="4b71e-236">Benutzerdefinierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4b71e-236">Custom properties</span></span>

<span data-ttu-id="4b71e-237">Ruft die Sammlung der benutzerdefinierten Eigenschaftsobjekte für das aktuelle Term-Objekt aus dem schreibgeschützten Schlüsselverzeichnis ab.</span><span class="sxs-lookup"><span data-stu-id="4b71e-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="4b71e-238">Benutzerdefinierte Eigenschaften sind Schlüssel-Werte-Paare, die für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder ein [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) definiert werden können, um die Beschreibung des [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="4b71e-238">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="4b71e-239">SharePoint gibt den Schlüssel der benutzerdefinierten Eigenschaft mit Hilfe von propertyName an.</span><span class="sxs-lookup"><span data-stu-id="4b71e-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="4b71e-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="4b71e-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="4b71e-241">Die Syntax, um dies zu definieren, lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="4b71e-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="4b71e-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="4b71e-243">Wenn die benutzerdefinierte Eigenschaft für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) mit dem [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) mitgeführt werden muss, wenn Sie den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) woanders wiederverwenden, müssen Sie ihn unter SharedCustomPropertyForTerm definieren.</span><span class="sxs-lookup"><span data-stu-id="4b71e-243">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="4b71e-244">Die Syntax, um dies zu definieren, lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="4b71e-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="4b71e-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="4b71e-246">Wenn die benutzerdefinierte Eigenschaft für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nicht mit dem [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) mitgeführt werden muss, wenn Sie den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) woanders wiederverwenden, dann müssen Sie ihn unter LocalCustomPropertyForTerm definieren.</span><span class="sxs-lookup"><span data-stu-id="4b71e-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="4b71e-247">Die Syntax, um dies zu definieren, lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="4b71e-248">Dateneigenschaften</span><span class="sxs-lookup"><span data-stu-id="4b71e-248">Data properties</span></span>

<span data-ttu-id="4b71e-249">Auf jeder Ebene der Hierarchie können Sie bestimmte Dateneigenschaften für einen Ausdruck oder TermSet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4b71e-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="4b71e-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="4b71e-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="4b71e-251">Verwenden Sie dies, um anzugeben, ob ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder ein [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) in SharePoint-Listen und -Bibliotheken verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4b71e-251">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="4b71e-252">Die Syntax dafür lautet:</span><span class="sxs-lookup"><span data-stu-id="4b71e-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="4b71e-253">Domäne und Bereich</span><span class="sxs-lookup"><span data-stu-id="4b71e-253">Domain and range</span></span>

<span data-ttu-id="4b71e-254">Die folgende Tabelle beschreibt die Domäne und den Bereich des Vokabulars der SharePoint-Taxonomie.</span><span class="sxs-lookup"><span data-stu-id="4b71e-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="4b71e-255">Prädikate/Verb</span><span class="sxs-lookup"><span data-stu-id="4b71e-255">Predicates/verb</span></span>|<span data-ttu-id="4b71e-256">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="4b71e-256">Meaning</span></span>|<span data-ttu-id="4b71e-257">Domäne</span><span class="sxs-lookup"><span data-stu-id="4b71e-257">Domain</span></span>|<span data-ttu-id="4b71e-258">Bereich</span><span class="sxs-lookup"><span data-stu-id="4b71e-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="4b71e-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="4b71e-259">inTermSet</span></span>|<span data-ttu-id="4b71e-260">Im Ausdruckssatz</span><span class="sxs-lookup"><span data-stu-id="4b71e-260">In term set</span></span>|<span data-ttu-id="4b71e-261">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-261">Term</span></span>|<span data-ttu-id="4b71e-262">Ausdruckssatz</span><span class="sxs-lookup"><span data-stu-id="4b71e-262">Term Set</span></span>|
<span data-ttu-id="4b71e-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="4b71e-263">inTermGroup</span></span>|<span data-ttu-id="4b71e-264">In Ausdrucksgruppe</span><span class="sxs-lookup"><span data-stu-id="4b71e-264">In term group</span></span>|<span data-ttu-id="4b71e-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="4b71e-265">TermSet</span></span>|<span data-ttu-id="4b71e-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="4b71e-266">TermGroup</span></span>|
<span data-ttu-id="4b71e-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="4b71e-267">topLevelTermOf</span></span>|<span data-ttu-id="4b71e-268">Ist Ausdruck der obersten Ebene von</span><span class="sxs-lookup"><span data-stu-id="4b71e-268">Is Top Level Term Of</span></span>|<span data-ttu-id="4b71e-269">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-269">Term</span></span>|<span data-ttu-id="4b71e-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="4b71e-270">TermSet</span></span>|
<span data-ttu-id="4b71e-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="4b71e-271">hasTopLevelTerm</span></span>|<span data-ttu-id="4b71e-272">Hat Ausdruck der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="4b71e-272">Has top level term</span></span>|<span data-ttu-id="4b71e-273">Ausdruckssatz</span><span class="sxs-lookup"><span data-stu-id="4b71e-273">Term Set</span></span>|<span data-ttu-id="4b71e-274">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-274">Term</span></span>|
<span data-ttu-id="4b71e-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="4b71e-275">termSetName</span></span>|<span data-ttu-id="4b71e-276">Ausdruckssatz hat Namen</span><span class="sxs-lookup"><span data-stu-id="4b71e-276">Term set has Name</span></span>|<span data-ttu-id="4b71e-277">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-277">Term</span></span>|<span data-ttu-id="4b71e-278">Einfaches Literal</span><span class="sxs-lookup"><span data-stu-id="4b71e-278">Plain literal</span></span>|
<span data-ttu-id="4b71e-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="4b71e-279">defaultLabel</span></span>|<span data-ttu-id="4b71e-280">Ausdruck hat Standardbezeichnung</span><span class="sxs-lookup"><span data-stu-id="4b71e-280">Term has default label</span></span>|<span data-ttu-id="4b71e-281">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-281">Term</span></span>|<span data-ttu-id="4b71e-282">Einfaches Literal</span><span class="sxs-lookup"><span data-stu-id="4b71e-282">Plain literal</span></span>|
<span data-ttu-id="4b71e-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="4b71e-283">otherLabel</span></span>|<span data-ttu-id="4b71e-284">Ausdruck hat andere Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="4b71e-284">Term has other label</span></span>|<span data-ttu-id="4b71e-285">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-285">Term</span></span>|<span data-ttu-id="4b71e-286">Einfaches Literal</span><span class="sxs-lookup"><span data-stu-id="4b71e-286">Plain literal</span></span>|
<span data-ttu-id="4b71e-287">propertyName</span><span class="sxs-lookup"><span data-stu-id="4b71e-287">propertyName</span></span>|<span data-ttu-id="4b71e-288">Hat Eigenschaftenbezeichnung</span><span class="sxs-lookup"><span data-stu-id="4b71e-288">Has Property Label</span></span>|<span data-ttu-id="4b71e-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="4b71e-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="4b71e-290">Boolesch, Zeichenfolge, Ganze Zahl, Dezimal, Duplikat</span><span class="sxs-lookup"><span data-stu-id="4b71e-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="4b71e-291">description</span><span class="sxs-lookup"><span data-stu-id="4b71e-291">description</span></span>|<span data-ttu-id="4b71e-292">Hat Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b71e-292">Has Description</span></span>|<span data-ttu-id="4b71e-293">Alle</span><span class="sxs-lookup"><span data-stu-id="4b71e-293">All</span></span>|<span data-ttu-id="4b71e-294">Einfaches Literal</span><span class="sxs-lookup"><span data-stu-id="4b71e-294">Plain literal</span></span>|
|<span data-ttu-id="4b71e-295">parent</span><span class="sxs-lookup"><span data-stu-id="4b71e-295">parent</span></span>|<span data-ttu-id="4b71e-296">Hat ein übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="4b71e-296">Has parent</span></span>|<span data-ttu-id="4b71e-297">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-297">Term</span></span>|<span data-ttu-id="4b71e-298">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-298">Term</span></span>|
|<span data-ttu-id="4b71e-299">child</span><span class="sxs-lookup"><span data-stu-id="4b71e-299">child</span></span>|<span data-ttu-id="4b71e-300">Hat untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="4b71e-300">Has Child</span></span>|<span data-ttu-id="4b71e-301">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-301">Term</span></span>|<span data-ttu-id="4b71e-302">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-302">Term</span></span>|
|<span data-ttu-id="4b71e-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="4b71e-303">isAvailableForTagging</span></span>|<span data-ttu-id="4b71e-304">Ist für Tagging verfügbar</span><span class="sxs-lookup"><span data-stu-id="4b71e-304">Is available for tagging</span></span>|<span data-ttu-id="4b71e-305">Term, Ausdruckssatz</span><span class="sxs-lookup"><span data-stu-id="4b71e-305">Term, Term Set</span></span>|<span data-ttu-id="4b71e-306">Boolesch</span><span class="sxs-lookup"><span data-stu-id="4b71e-306">Boolean</span></span>|
|<span data-ttu-id="4b71e-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="4b71e-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="4b71e-308">Hat gemeinsame benutzerdefinierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4b71e-308">Has shared custom property</span></span>|<span data-ttu-id="4b71e-309">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-309">Term</span></span>|<span data-ttu-id="4b71e-310">Boolesch, Zeichenfolge, Ganze Zahl, Dezimal, Duplikat</span><span class="sxs-lookup"><span data-stu-id="4b71e-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="4b71e-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="4b71e-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="4b71e-312">Hat lokale benutzerdefinierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4b71e-312">Has local custom property</span></span>|<span data-ttu-id="4b71e-313">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4b71e-313">Term</span></span>|<span data-ttu-id="4b71e-314">Boolesch, Zeichenfolge, Ganze Zahl, Dezimal, Duplikat</span><span class="sxs-lookup"><span data-stu-id="4b71e-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="4b71e-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="4b71e-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="4b71e-316">Hat benutzerdefinierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4b71e-316">Has Custom Property</span></span>|<span data-ttu-id="4b71e-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="4b71e-317">TermSet</span></span>|<span data-ttu-id="4b71e-318">Boolesch, Zeichenfolge, Ganze Zahl, Dezimal, Duplikat</span><span class="sxs-lookup"><span data-stu-id="4b71e-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="4b71e-319">[SKOS](https://www.w3.org/TR/skos-primer/) gültige Szenarien, die [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) nicht zulassen:</span><span class="sxs-lookup"><span data-stu-id="4b71e-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="4b71e-320">Hierarchische Redundanz – Ein [SKOS](https://www.w3.org/TR/skos-primer/)-Konzept kann gleichzeitig an mehrere breitere Konzepte angehängt werden, aber ein sharepoint-taxonomy:Term kann nur ein sharepoint-taxonomy:parent aufweisen, daher ist auch eine zyklische Abhängigkeit von Ausdrücken nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="4b71e-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="4b71e-321">Verwaiste Ausdrücke sind in der SharePoint-Taxonomie nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="4b71e-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="4b71e-322">Jeder sharepoint-taxonomy:Term sollte entweder einen sharepoint-taxonomy:parent haben oder es sollte der sharepoint-taxonomy:topLevelTermOf eines TermSets sein.</span><span class="sxs-lookup"><span data-stu-id="4b71e-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="4b71e-323">Die SharePoint-Taxonomie unterstützt keine assoziativen Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="4b71e-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="4b71e-324">Die SharePoint-Taxonomie erlaubt nur 2 Arten von hierarchischen Beziehungen: sharepoint-taxonomy:parent und sharepoint-taxonomy:child.</span><span class="sxs-lookup"><span data-stu-id="4b71e-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="4b71e-325">Im Gegensatz zu [SKOS](https://www.w3.org/TR/skos-primer/) kann die hierarchische Beziehung im Vokabular der SharePoint-Taxonomie nur mit Ausdrücken innerhalb desselben TermSets hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4b71e-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b71e-326">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="4b71e-326">See also</span></span>

[<span data-ttu-id="4b71e-327">Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats</span><span class="sxs-lookup"><span data-stu-id="4b71e-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

