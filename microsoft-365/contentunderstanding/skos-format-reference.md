---
title: SKOS-Format Referenz für die SharePoint-Taxonomie
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: SKOS-Format Referenz für die SharePoint-Taxonomie
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296084"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="6cc80-103">SKOS-Format Referenz für die SharePoint-Taxonomie</span><span class="sxs-lookup"><span data-stu-id="6cc80-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="6cc80-104">Dieser Artikel enthält RDF-Vokabular, das zur Darstellung der [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) verwendet wird und auf [SKOS](https://www.w3.org/TR/skos-primer/)basiert.</span><span class="sxs-lookup"><span data-stu-id="6cc80-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="6cc80-105">Für die Serialisierung dieser RDF-Syntax verwenden Sie RDF [Turtle](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="6cc80-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="6cc80-106">In der folgenden Tabelle sind die [SKOS](https://www.w3.org/TR/skos-primer/) -Entsprechungen für das [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) -Vokabular dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6cc80-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="6cc80-107">SharePoint unterstützt keine [SKOS](https://www.w3.org/TR/skos-primer/) -Werte, die keine SharePoint-Taxonomie-Entsprechung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6cc80-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="6cc80-108">SharePoint-Taxonomie</span><span class="sxs-lookup"><span data-stu-id="6cc80-108">SharePoint taxonomy</span></span>|<span data-ttu-id="6cc80-109">SKOS-Äquivalent</span><span class="sxs-lookup"><span data-stu-id="6cc80-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="6cc80-110">SharePoint-Taxonomie: Ausdruck</span><span class="sxs-lookup"><span data-stu-id="6cc80-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="6cc80-111">skos: Konzept</span><span class="sxs-lookup"><span data-stu-id="6cc80-111">skos:Concept</span></span>|
|<span data-ttu-id="6cc80-112">SharePoint-Taxonomie: TermSet</span><span class="sxs-lookup"><span data-stu-id="6cc80-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="6cc80-113">skos: ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="6cc80-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="6cc80-114">SharePoint-Taxonomie: intermset</span><span class="sxs-lookup"><span data-stu-id="6cc80-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="6cc80-115">skos: inschema</span><span class="sxs-lookup"><span data-stu-id="6cc80-115">skos:inScheme</span></span>|
|<span data-ttu-id="6cc80-116">SharePoint-Taxonomie: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="6cc80-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="6cc80-117">skos: hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="6cc80-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="6cc80-118">SharePoint-Taxonomie: topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="6cc80-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="6cc80-119">skos: topConceptOf</span><span class="sxs-lookup"><span data-stu-id="6cc80-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="6cc80-120">SharePoint-Taxonomie: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="6cc80-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="6cc80-121">skos: prefLabel</span><span class="sxs-lookup"><span data-stu-id="6cc80-121">skos:prefLabel</span></span>|
|<span data-ttu-id="6cc80-122">SharePoint-Taxonomie: termSetName</span><span class="sxs-lookup"><span data-stu-id="6cc80-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="6cc80-123">skos: prefLabel</span><span class="sxs-lookup"><span data-stu-id="6cc80-123">skos:prefLabel</span></span>|
|<span data-ttu-id="6cc80-124">SharePoint-Taxonomie: PropertyName</span><span class="sxs-lookup"><span data-stu-id="6cc80-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="6cc80-125">skos: prefLabel</span><span class="sxs-lookup"><span data-stu-id="6cc80-125">skos:prefLabel</span></span>|
|<span data-ttu-id="6cc80-126">SharePoint-Taxonomie: otherLabel</span><span class="sxs-lookup"><span data-stu-id="6cc80-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="6cc80-127">skos: altLabel</span><span class="sxs-lookup"><span data-stu-id="6cc80-127">skos:altLabel</span></span>|
|<span data-ttu-id="6cc80-128">SharePoint-Taxonomie: Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6cc80-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="6cc80-129">skos: Definition</span><span class="sxs-lookup"><span data-stu-id="6cc80-129">skos:definition</span></span>|
|<span data-ttu-id="6cc80-130">SharePoint-Taxonomie: Parent</span><span class="sxs-lookup"><span data-stu-id="6cc80-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="6cc80-131">skos: breiter</span><span class="sxs-lookup"><span data-stu-id="6cc80-131">skos:broader</span></span>|
|<span data-ttu-id="6cc80-132">SharePoint-Taxonomie: Child</span><span class="sxs-lookup"><span data-stu-id="6cc80-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="6cc80-133">skos: schmaler</span><span class="sxs-lookup"><span data-stu-id="6cc80-133">skos:narrower</span></span>|

<span data-ttu-id="6cc80-134">In der folgenden Tabelle werden die Entitäten des von [Owl](https://www.w3.org/TR/owl2-primer/)abgeleiteten SharePoint-Taxonomie-Vokabulars angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cc80-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="6cc80-135">SharePoint-Taxonomie-Vokabular</span><span class="sxs-lookup"><span data-stu-id="6cc80-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="6cc80-136">Abgeleitet von OWL</span><span class="sxs-lookup"><span data-stu-id="6cc80-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="6cc80-137">SharePoint-Taxonomie: isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="6cc80-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="6cc80-138">Owl: datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="6cc80-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="6cc80-139">SharePoint-Taxonomie: SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="6cc80-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="6cc80-140">Owl: OBJECTPROPERTY</span><span class="sxs-lookup"><span data-stu-id="6cc80-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="6cc80-141">SharePoint-Taxonomie: LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="6cc80-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="6cc80-142">Owl: OBJECTPROPERTY</span><span class="sxs-lookup"><span data-stu-id="6cc80-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="6cc80-143">SharePoint-Taxonomie: CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="6cc80-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="6cc80-144">Owl: OBJECTPROPERTY</span><span class="sxs-lookup"><span data-stu-id="6cc80-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="6cc80-145">SharePoint-Taxonomie-Vokabular</span><span class="sxs-lookup"><span data-stu-id="6cc80-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="6cc80-146">Eine Taxonomie ist ein formales Klassifizierungssystem.</span><span class="sxs-lookup"><span data-stu-id="6cc80-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="6cc80-147">Eine Taxonomie gruppiert die Wörter, Bezeichnungen und Begriffe, die etwas beschreiben, und ordnet die Gruppen dann in einer Hierarchie an.</span><span class="sxs-lookup"><span data-stu-id="6cc80-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="6cc80-148">**SharePoint-Taxonomie: Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="6cc80-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="6cc80-149">Stellt einen Term oder ein Schlüsselwort in einer Hierarchie für verwaltete Metadaten dar.</span><span class="sxs-lookup"><span data-stu-id="6cc80-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="6cc80-150">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ist die atomare Einheit einer SharePoint- [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="6cc80-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="6cc80-151">Jeder [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) gehört zu einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) , das zu einer [termgroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)gehört.</span><span class="sxs-lookup"><span data-stu-id="6cc80-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="6cc80-152">Die Syntax zum Definieren eines [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6cc80-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="6cc80-153">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ist innerhalb eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)-pflichtbereichs vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6cc80-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6cc80-154">DefaultLabel ist der Name des [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , der in der visuellen Darstellung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6cc80-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="6cc80-155">Die erforderlichen Felder zum Definieren eines [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6cc80-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="6cc80-156">SharePoint-Taxonomie: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="6cc80-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="6cc80-157">SharePoint-Taxonomie: intermset</span><span class="sxs-lookup"><span data-stu-id="6cc80-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="6cc80-158">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann:</span><span class="sxs-lookup"><span data-stu-id="6cc80-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="6cc80-159">Sie müssen sich hierarchisch auf einen anderen [Begriff](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) beziehen, der sowohl die [Begriffe](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) gehören zum gleichen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6cc80-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="6cc80-160">Mehrere untergeordnete [Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), aber nur ein einzelner übergeordneter [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="6cc80-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="6cc80-161">Kein übergeordneter [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) definiert, wenn es sich um ein topLevelTermOf-Objekt eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)handelt.</span><span class="sxs-lookup"><span data-stu-id="6cc80-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="6cc80-162">Haben Sie eine defaultLabel pro [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) Arbeitssprache.</span><span class="sxs-lookup"><span data-stu-id="6cc80-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="6cc80-163">Nicht vorhanden, wenn weder ein übergeordneter [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)noch der topLevelTermOf ein [termsatz](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)enthält.</span><span class="sxs-lookup"><span data-stu-id="6cc80-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="6cc80-164">Sie haben nur eine eindeutige defaultLabel auf derselben hierarchischen Ebene.</span><span class="sxs-lookup"><span data-stu-id="6cc80-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="6cc80-165">**SharePoint-Taxonomie: TermSet**</span><span class="sxs-lookup"><span data-stu-id="6cc80-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="6cc80-166">Stellt eine hierarchische oder flache Gruppe von Term-Objekten dar, die als "TermSet" bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="6cc80-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="6cc80-167">Wie der Name schon sagt, [ist TermSet eine Reihe von](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)Begriffen.</span><span class="sxs-lookup"><span data-stu-id="6cc80-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="6cc80-168">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in einem [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) muss einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)angehören.</span><span class="sxs-lookup"><span data-stu-id="6cc80-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6cc80-169">Kein [Begriff](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann unabhängig voneinander vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="6cc80-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="6cc80-170">Die Syntax zum Definieren eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) lautet:</span><span class="sxs-lookup"><span data-stu-id="6cc80-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="6cc80-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) sind in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)logisch zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="6cc80-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="6cc80-172">Das erforderliche Feld zur Definition eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) lautet:</span><span class="sxs-lookup"><span data-stu-id="6cc80-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="6cc80-173">SharePoint-Taxonomie: termSetName</span><span class="sxs-lookup"><span data-stu-id="6cc80-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="6cc80-174">Im Fall der bereitgestellten termSetName innerhalb der [termgroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)nicht eindeutig ist, fügt Topologiemodell eine Zahl am Ende des Namens an, um die Eindeutigkeit von termSetName (s) beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="6cc80-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharPoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="6cc80-175">**SharePoint-Taxonomie: hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="6cc80-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="6cc80-176">SharePoint verwendet diese Eigenschaft, um den obersten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) im [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), dem Einstiegspunkt für die Hierarchie von [Ausdrücken](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="6cc80-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6cc80-177">Dies ist eine umgekehrte Relation zur SharePoint-Taxonomie: topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="6cc80-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="6cc80-178">Die folgende Syntax definiert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6cc80-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="6cc80-179">Sie können den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) der obersten Ebene eines übergeordneten [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)nicht definieren.</span><span class="sxs-lookup"><span data-stu-id="6cc80-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="6cc80-180">**SharePoint-Taxonomie: topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="6cc80-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="6cc80-181">SharePoint-Taxonomie: topLevelTermOf ist die inverse SharePoint-Taxonomie: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="6cc80-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="6cc80-182">Die folgende Syntax definiert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6cc80-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="6cc80-183">**SharePoint-Taxonomie: intermset**</span><span class="sxs-lookup"><span data-stu-id="6cc80-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="6cc80-184">Verwenden Sie diese, um einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="6cc80-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6cc80-185">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann nur in einem einzelnen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="6cc80-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6cc80-186">SharePoint erfordert diese Eigenschaft, wenn [ein Ausdruck definiert](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)wird.</span><span class="sxs-lookup"><span data-stu-id="6cc80-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="6cc80-187">Erforderliche Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="6cc80-187">Required labels</span></span>

<span data-ttu-id="6cc80-188">Ihre Organisation möchte möglicherweise eine sorgfältige Planung durchführen, bevor Sie mit der Verwendung von verwalteten Metadaten beginnen.</span><span class="sxs-lookup"><span data-stu-id="6cc80-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="6cc80-189">Die Planungsmenge, die Sie ausführen müssen, hängt von der formalen Taxonomie ab.</span><span class="sxs-lookup"><span data-stu-id="6cc80-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="6cc80-190">Es hängt auch davon ab, wie viel Kontrolle Sie für Metadaten auferlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="6cc80-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="6cc80-191">Auf jeder Ebene der Hierarchie müssen Sie die erforderlichen Lables für einen Ausdruck oder ein TermSet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6cc80-191">At each level of the hierarchy, you need to configure required lables for a Term or TermSet.</span></span>

<span data-ttu-id="6cc80-192">Ein Ausdruck kann eine oder mehrere Bezeichnungen in der Standardsprache und NULL oder mehr Bezeichnungen in der nicht standardmäßigen Sprache aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6cc80-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="6cc80-193">Falls der Ausdruck Bezeichnungen in einer Sprache aufweist, muss eine der Bezeichnungen die Standardbezeichnung sein.</span><span class="sxs-lookup"><span data-stu-id="6cc80-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="6cc80-194">**SharePoint-Taxonomie: defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="6cc80-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="6cc80-195">Verwenden Sie diese standardmäßige lexikalische Bezeichnung für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , der ein erforderlicher Parameter für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)ist.</span><span class="sxs-lookup"><span data-stu-id="6cc80-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="6cc80-196">Wird verwendet, um den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)visuell darzustellen.</span><span class="sxs-lookup"><span data-stu-id="6cc80-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="6cc80-197">Die Syntax zum Definieren einer defaultLabel lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6cc80-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="6cc80-198">Das defaultLabel-Objekt enthält zwei Teile – die Zeichenfolge und das Sprachtag.</span><span class="sxs-lookup"><span data-stu-id="6cc80-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="6cc80-199">Die Sprache muss eine der [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) Arbeitssprachen sein.</span><span class="sxs-lookup"><span data-stu-id="6cc80-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="6cc80-200">Das defaultLabel muss für alle [Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) im gleichen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)auf derselben hierarchischen Ebene eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="6cc80-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="6cc80-201">**SharePoint-Taxonomie: termSetName**</span><span class="sxs-lookup"><span data-stu-id="6cc80-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="6cc80-202">Dient zum Abrufen und Festlegen des Namens für das aktuelle TermSet-Objekt.</span><span class="sxs-lookup"><span data-stu-id="6cc80-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="6cc80-203">Dies ist die lexikalische Bezeichnung für einen [termsatz](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)in einer [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) -Arbeitssprache.</span><span class="sxs-lookup"><span data-stu-id="6cc80-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="6cc80-204">Dies ist ein erforderlicher Parameter für einen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="6cc80-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6cc80-205">Wird verwendet, um einen [termsatz](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)visuell darzustellen.</span><span class="sxs-lookup"><span data-stu-id="6cc80-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="6cc80-206">Die Syntax zum Definieren einer termSetName lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6cc80-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="6cc80-207">**SharePoint-Taxonomie: PropertyName**</span><span class="sxs-lookup"><span data-stu-id="6cc80-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="6cc80-208">Ruft den Eigenschaftennamen für das aktuelle TermSet-Objekt ab und legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="6cc80-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="6cc80-209">Dies ist die lexikalische Bezeichnung für eine SharePoint-Taxonomie: SharedCustomPropertyForTerm, SharePoint-Taxonomie: LocalCustomPropertyForTerm und SharePoint-Taxonomie: CustomPropertyForTermSet in einer [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) Arbeitssprache.</span><span class="sxs-lookup"><span data-stu-id="6cc80-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="6cc80-210">Die SharePoint-Taxonomie: PropertyName wird als Schlüssel der CustomProperty behandelt.</span><span class="sxs-lookup"><span data-stu-id="6cc80-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="6cc80-211">Die Syntax zum Definieren einer propetyName lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6cc80-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="6cc80-212">Optionale Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="6cc80-212">Optional labels</span></span>

<span data-ttu-id="6cc80-213">Sie können auch optionale Bezeichnungen zu ihrer Taxonomie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6cc80-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="6cc80-214">**SharePoint-Taxonomie: otherLabel**</span><span class="sxs-lookup"><span data-stu-id="6cc80-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="6cc80-215">Dies ist die Alternative lexikalische Bezeichnung für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="6cc80-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="6cc80-216">Die Syntax zum Definieren einer otherLabel lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6cc80-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="6cc80-217">Semantische Beziehungen</span><span class="sxs-lookup"><span data-stu-id="6cc80-217">Semantic relationships</span></span>

<span data-ttu-id="6cc80-218">Taxonomien weisen hierarchische und manchmal auch eine einfache "Verwandte Terminologie"-assoziative Beziehungen auf, einige weisen jedoch "semantische Beziehungen" oder benutzerdefinierte Beziehungen auf.</span><span class="sxs-lookup"><span data-stu-id="6cc80-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="6cc80-219">**SharePoint-Taxonomie: Parent**</span><span class="sxs-lookup"><span data-stu-id="6cc80-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="6cc80-220">Dadurch wird ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) hierarchisch mit einem anderen [Begriff](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)verknüpft.</span><span class="sxs-lookup"><span data-stu-id="6cc80-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="6cc80-221">Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann [ein Ausdruck auf oberster Ebene](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)sein, für den Fall jedoch nicht, dass er über einen übergeordneten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="6cc80-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="6cc80-222">Die Syntax zum Definieren eines übergeordneten Elements lautet:</span><span class="sxs-lookup"><span data-stu-id="6cc80-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="6cc80-223">Dies bedeutet, dass TermA1 über übergeordnete Terma verfügt.</span><span class="sxs-lookup"><span data-stu-id="6cc80-223">This means that TermA1 has parent TermA.</span></span> <span data-ttu-id="6cc80-224">Umgekehrt bedeutet dies auch, dass TermA1 das untergeordnete Element von Terma ist.</span><span class="sxs-lookup"><span data-stu-id="6cc80-224">Inversely it also means that TermA1 is the child of TermA.</span></span> <span data-ttu-id="6cc80-225">Parent-Child-Beziehung ist eine inversible-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="6cc80-225">Parent-child relationship is an inversible relationship.</span></span>

<span data-ttu-id="6cc80-226">**SharePoint-Taxonomie: Child**</span><span class="sxs-lookup"><span data-stu-id="6cc80-226">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="6cc80-227">Das-Objekt enthält mindestens eine untergeordnete TermSet-Instanz, auf die über die TermSets-Eigenschaft zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="6cc80-227">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="6cc80-228">Diese Klasse stellt auch Methoden zum Erstellen neuer untergeordneter TermSet-Objekte bereit.</span><span class="sxs-lookup"><span data-stu-id="6cc80-228">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="6cc80-229">Berechtigungen zum Bearbeiten von untergeordneten Term-und TermSet-Instanzen werden in der Gruppe angegeben.</span><span class="sxs-lookup"><span data-stu-id="6cc80-229">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="6cc80-230">Dadurch wird ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) hierarchisch mit einem anderen [Begriff](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)verknüpft.</span><span class="sxs-lookup"><span data-stu-id="6cc80-230">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="6cc80-231">Die Syntax zum Definieren eines untergeordneten Elements lautet:</span><span class="sxs-lookup"><span data-stu-id="6cc80-231">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="6cc80-232">Dies bedeutet, dass Terma über untergeordnete TermA1 verfügt.</span><span class="sxs-lookup"><span data-stu-id="6cc80-232">This means that TermA has child TermA1.</span></span> <span data-ttu-id="6cc80-233">Umgekehrt bedeutet dies auch, dass Terma das übergeordnete Element der TermA1 Parent-Child-Beziehung eine inversible Beziehung ist.</span><span class="sxs-lookup"><span data-stu-id="6cc80-233">Inversely it also means that TermA is the parent of TermA1 parent-child relationship is an inversible relationship.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="6cc80-234">Dokumentations Hinweise</span><span class="sxs-lookup"><span data-stu-id="6cc80-234">Documentation notes</span></span>

<span data-ttu-id="6cc80-235">In diesem Abschnitt wird die Taxonomie beschrieben, die im Microsoft. SharePoint. Taxonomy-Namespace beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="6cc80-235">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="6cc80-236">**SharePoint-Taxonomie: Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6cc80-236">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="6cc80-237">Dies ist eine ausführliche Erläuterung einer beliebigen [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) -Vokabular-Entität.</span><span class="sxs-lookup"><span data-stu-id="6cc80-237">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="6cc80-238">Die Syntax zum Hinzufügen einer Beschreibung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6cc80-238">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="6cc80-239">Benutzerdefinierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6cc80-239">Custom properties</span></span>

<span data-ttu-id="6cc80-240">Ruft die Auflistung der benutzerdefinierten Property-Objekte für das aktuelle Term-Objekt aus dem schreibgeschützten Wörterbuch ab.</span><span class="sxs-lookup"><span data-stu-id="6cc80-240">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="6cc80-241">Benutzerdefinierte Eigenschaften sind Schlüssel-Werte-Paare, die für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder einen [termsatz](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)definiert werden können, um die Beschreibung des [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder eines [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)sätzes zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="6cc80-241">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6cc80-242">SharePoint gibt den Schlüssel der benutzerdefinierten Eigenschaft mit der Hilfe von PropertyName an.</span><span class="sxs-lookup"><span data-stu-id="6cc80-242">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="6cc80-243">**SharePoint-Taxonomie: CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="6cc80-243">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="6cc80-244">Die folgende Syntax definiert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6cc80-244">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="6cc80-245">**SharePoint-Taxonomie: SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="6cc80-245">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="6cc80-246">Wenn die benutzerdefinierte Eigenschaft für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) zusammen mit dem Ausdruck mitgetragen werden muss, wenn Sie den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) an anderer Stelle wieder [verwenden, müssen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)Sie ihn unter SharedCustomPropertyForTerm definieren.</span><span class="sxs-lookup"><span data-stu-id="6cc80-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="6cc80-247">Die folgende Syntax definiert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6cc80-247">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="6cc80-248">**SharePoint-Taxonomie: LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="6cc80-248">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="6cc80-249">Wenn die benutzerdefinierte Eigenschaft für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nicht zusammen mit dem [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)mitgetragen werden muss, wenn Sie den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) an anderer Stelle wieder verwenden, müssen Sie ihn unter LocalCustomPropertyForTerm definieren.</span><span class="sxs-lookup"><span data-stu-id="6cc80-249">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="6cc80-250">Die folgende Syntax definiert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6cc80-250">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="6cc80-251">Dateneigenschaften</span><span class="sxs-lookup"><span data-stu-id="6cc80-251">Data properties</span></span>

<span data-ttu-id="6cc80-252">Auf jeder Ebene der Hierarchiekönnen Sie bestimmte Dateneigenschaften für einen Ausdruck oder ein TermSet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6cc80-252">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="6cc80-253">**SharePoint-Taxonomie: isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="6cc80-253">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="6cc80-254">Verwenden Sie diese, um anzugeben, ob ein [Begriff](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder ein [ausdrucksset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) in SharePoint-Listen und-Bibliotheken verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6cc80-254">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="6cc80-255">Die Syntax hierfür lautet:</span><span class="sxs-lookup"><span data-stu-id="6cc80-255">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="6cc80-256">Domäne und Bereich</span><span class="sxs-lookup"><span data-stu-id="6cc80-256">Domain and range</span></span>

<span data-ttu-id="6cc80-257">Die folgende Tabelle beschreibt die Domäne und den Bereich des SharePoint-Taxonomie-Vokabulars.</span><span class="sxs-lookup"><span data-stu-id="6cc80-257">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="6cc80-258">Prädikate/Verb</span><span class="sxs-lookup"><span data-stu-id="6cc80-258">Predicates/verb</span></span>|<span data-ttu-id="6cc80-259">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="6cc80-259">Meaning</span></span>|<span data-ttu-id="6cc80-260">Domäne</span><span class="sxs-lookup"><span data-stu-id="6cc80-260">Domain</span></span>|<span data-ttu-id="6cc80-261">Bereich</span><span class="sxs-lookup"><span data-stu-id="6cc80-261">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="6cc80-262">intermset</span><span class="sxs-lookup"><span data-stu-id="6cc80-262">inTermSet</span></span>|<span data-ttu-id="6cc80-263">Im Ausdruckssätze</span><span class="sxs-lookup"><span data-stu-id="6cc80-263">In term set</span></span>|<span data-ttu-id="6cc80-264">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-264">Term</span></span>|<span data-ttu-id="6cc80-265">Ausdruckssatz</span><span class="sxs-lookup"><span data-stu-id="6cc80-265">Term Set</span></span>|
<span data-ttu-id="6cc80-266">intermgroup</span><span class="sxs-lookup"><span data-stu-id="6cc80-266">inTermGroup</span></span>|<span data-ttu-id="6cc80-267">In Ausdrucksgruppe</span><span class="sxs-lookup"><span data-stu-id="6cc80-267">In term group</span></span>|<span data-ttu-id="6cc80-268">TermSet</span><span class="sxs-lookup"><span data-stu-id="6cc80-268">TermSet</span></span>|<span data-ttu-id="6cc80-269">Termgroup</span><span class="sxs-lookup"><span data-stu-id="6cc80-269">TermGroup</span></span>|
<span data-ttu-id="6cc80-270">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="6cc80-270">topLevelTermOf</span></span>|<span data-ttu-id="6cc80-271">Ist auf oberster Ebene der Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-271">Is Top Level Term Of</span></span>|<span data-ttu-id="6cc80-272">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-272">Term</span></span>|<span data-ttu-id="6cc80-273">TermSet</span><span class="sxs-lookup"><span data-stu-id="6cc80-273">TermSet</span></span>|
<span data-ttu-id="6cc80-274">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="6cc80-274">hasTopLevelTerm</span></span>|<span data-ttu-id="6cc80-275">Hat Ausdruck auf oberster Ebene</span><span class="sxs-lookup"><span data-stu-id="6cc80-275">Has top level term</span></span>|<span data-ttu-id="6cc80-276">Ausdruckssatz</span><span class="sxs-lookup"><span data-stu-id="6cc80-276">Term Set</span></span>|<span data-ttu-id="6cc80-277">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-277">Term</span></span>|
<span data-ttu-id="6cc80-278">termSetName</span><span class="sxs-lookup"><span data-stu-id="6cc80-278">termSetName</span></span>|<span data-ttu-id="6cc80-279">Ausdrucksgruppe hat Namen</span><span class="sxs-lookup"><span data-stu-id="6cc80-279">Term set has Name</span></span>|<span data-ttu-id="6cc80-280">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-280">Term</span></span>|<span data-ttu-id="6cc80-281">Einfaches Literal</span><span class="sxs-lookup"><span data-stu-id="6cc80-281">Plain literal</span></span>|
<span data-ttu-id="6cc80-282">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="6cc80-282">defaultLabel</span></span>|<span data-ttu-id="6cc80-283">Ausdruck hat Standardbezeichnung</span><span class="sxs-lookup"><span data-stu-id="6cc80-283">Term has default label</span></span>|<span data-ttu-id="6cc80-284">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-284">Term</span></span>|<span data-ttu-id="6cc80-285">Einfaches Literal</span><span class="sxs-lookup"><span data-stu-id="6cc80-285">Plain literal</span></span>|
<span data-ttu-id="6cc80-286">otherLabel</span><span class="sxs-lookup"><span data-stu-id="6cc80-286">otherLabel</span></span>|<span data-ttu-id="6cc80-287">Ausdruck hat andere Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="6cc80-287">Term has other label</span></span>|<span data-ttu-id="6cc80-288">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-288">Term</span></span>|<span data-ttu-id="6cc80-289">Einfaches Literal</span><span class="sxs-lookup"><span data-stu-id="6cc80-289">Plain literal</span></span>|
<span data-ttu-id="6cc80-290">PropertyName</span><span class="sxs-lookup"><span data-stu-id="6cc80-290">propertyName</span></span>|<span data-ttu-id="6cc80-291">Besitzt Eigenschaftenbezeichnung</span><span class="sxs-lookup"><span data-stu-id="6cc80-291">Has Property Label</span></span>|<span data-ttu-id="6cc80-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="6cc80-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="6cc80-293">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="6cc80-293">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="6cc80-294">description</span><span class="sxs-lookup"><span data-stu-id="6cc80-294">description</span></span>|<span data-ttu-id="6cc80-295">Beschreibung enthält</span><span class="sxs-lookup"><span data-stu-id="6cc80-295">Has Description</span></span>|<span data-ttu-id="6cc80-296">Alle</span><span class="sxs-lookup"><span data-stu-id="6cc80-296">All</span></span>|<span data-ttu-id="6cc80-297">Einfaches Literal</span><span class="sxs-lookup"><span data-stu-id="6cc80-297">Plain literal</span></span>|
|<span data-ttu-id="6cc80-298">übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="6cc80-298">parent</span></span>|<span data-ttu-id="6cc80-299">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="6cc80-299">Has parent</span></span>|<span data-ttu-id="6cc80-300">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-300">Term</span></span>|<span data-ttu-id="6cc80-301">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-301">Term</span></span>|
|<span data-ttu-id="6cc80-302">untergeordneten</span><span class="sxs-lookup"><span data-stu-id="6cc80-302">child</span></span>|<span data-ttu-id="6cc80-303">Untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="6cc80-303">Has Child</span></span>|<span data-ttu-id="6cc80-304">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-304">Term</span></span>|<span data-ttu-id="6cc80-305">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-305">Term</span></span>|
|<span data-ttu-id="6cc80-306">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="6cc80-306">isAvailableForTagging</span></span>|<span data-ttu-id="6cc80-307">Steht für Tagging zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="6cc80-307">Is available for tagging</span></span>|<span data-ttu-id="6cc80-308">Ausdruck, Ausdruckssätze</span><span class="sxs-lookup"><span data-stu-id="6cc80-308">Term, Term Set</span></span>|<span data-ttu-id="6cc80-309">Boolesch</span><span class="sxs-lookup"><span data-stu-id="6cc80-309">Boolean</span></span>|
|<span data-ttu-id="6cc80-310">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="6cc80-310">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="6cc80-311">Verfügt über freigegebene benutzerdefinierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6cc80-311">Has shared custom property</span></span>|<span data-ttu-id="6cc80-312">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-312">Term</span></span>|<span data-ttu-id="6cc80-313">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="6cc80-313">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="6cc80-314">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="6cc80-314">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="6cc80-315">Verfügt über eine lokale benutzerdefinierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6cc80-315">Has local custom property</span></span>|<span data-ttu-id="6cc80-316">Begriff</span><span class="sxs-lookup"><span data-stu-id="6cc80-316">Term</span></span>|<span data-ttu-id="6cc80-317">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="6cc80-317">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="6cc80-318">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="6cc80-318">CustomPropertyForTermSet</span></span>|<span data-ttu-id="6cc80-319">Verfügt über eine benutzerdefinierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6cc80-319">Has Custom Property</span></span>|<span data-ttu-id="6cc80-320">TermSet</span><span class="sxs-lookup"><span data-stu-id="6cc80-320">TermSet</span></span>|<span data-ttu-id="6cc80-321">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="6cc80-321">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="6cc80-322">[SKOS](https://www.w3.org/TR/skos-primer/) gültige Szenarien, die von der [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) nicht zugelassen werden:</span><span class="sxs-lookup"><span data-stu-id="6cc80-322">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="6cc80-323">Hierarchische Redundanz – ein [SKOS](https://www.w3.org/TR/skos-primer/) -Konzept kann gleichzeitig an mehrere umfassendere Konzepte angehängt werden, aber eine SharePoint-Taxonomie: Term kann nur eine SharePoint-Taxonomie haben: Parent, daher zyklische Abhängigkeit von Begriffen ist ebenfalls nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="6cc80-323">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="6cc80-324">Verwaiste Ausdrücke sind in der SharePoint-Taxonomie nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="6cc80-324">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="6cc80-325">Jede SharePoint-Taxonomie: Term sollte entweder eine SharePoint-Taxonomie haben: Parent oder sollte die SharePoint-Taxonomie sein: topLevelTermOf ein TermSet.</span><span class="sxs-lookup"><span data-stu-id="6cc80-325">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="6cc80-326">Die SharePoint-Taxonomie unterstützt keine assoziativen Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="6cc80-326">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="6cc80-327">Die SharePoint-Taxonomie erlaubt nur 2 Arten hierarchischer Beziehungen – SharePoint-Taxonomie: Parent und SharePoint-Taxonomie: Child.</span><span class="sxs-lookup"><span data-stu-id="6cc80-327">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="6cc80-328">Im Gegensatz zu [SKOS](https://www.w3.org/TR/skos-primer/) kann die hierarchische Beziehung in SharePoint-Taxonomie-Vokabular nur mit Ausdrücken innerhalb desselben ausdrucksset festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="6cc80-328">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cc80-329">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6cc80-329">See also</span></span>

[<span data-ttu-id="6cc80-330">Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats</span><span class="sxs-lookup"><span data-stu-id="6cc80-330">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

