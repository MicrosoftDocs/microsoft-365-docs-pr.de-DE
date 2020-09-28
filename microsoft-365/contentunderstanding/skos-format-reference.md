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
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SKOS-Format Referenz für die SharePoint-Taxonomie

Dieser Artikel enthält RDF-Vokabular, das zur Darstellung der [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) verwendet wird und auf [SKOS](https://www.w3.org/TR/skos-primer/)basiert. Für die Serialisierung dieser RDF-Syntax verwenden Sie RDF [Turtle](https://www.w3.org/TR/turtle/).

In der folgenden Tabelle sind die [SKOS](https://www.w3.org/TR/skos-primer/) -Entsprechungen für das [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) -Vokabular dargestellt. SharePoint unterstützt keine [SKOS](https://www.w3.org/TR/skos-primer/) -Werte, die keine SharePoint-Taxonomie-Entsprechung aufweisen.

|SharePoint-Taxonomie|SKOS-Äquivalent|
|:-----------------|:--------------|
|SharePoint-Taxonomie: Ausdruck|skos: Konzept|
|SharePoint-Taxonomie: TermSet|skos: ConceptScheme|
|SharePoint-Taxonomie: intermset|skos: inschema|
|SharePoint-Taxonomie: hasTopLevelTerm|skos: hasTopConcept|
|SharePoint-Taxonomie: topLevelTermOf|skos: topConceptOf|
|SharePoint-Taxonomie: defaultLabel|skos: prefLabel|
|SharePoint-Taxonomie: termSetName|skos: prefLabel|
|SharePoint-Taxonomie: PropertyName|skos: prefLabel|
|SharePoint-Taxonomie: otherLabel|skos: altLabel|
|SharePoint-Taxonomie: Beschreibung|skos: Definition|
|SharePoint-Taxonomie: Parent|skos: breiter|
|SharePoint-Taxonomie: Child|skos: schmaler|

In der folgenden Tabelle werden die Entitäten des von [Owl](https://www.w3.org/TR/owl2-primer/)abgeleiteten SharePoint-Taxonomie-Vokabulars angezeigt.

|SharePoint-Taxonomie-Vokabular|Abgeleitet von OWL|
|:-----------------------------|:----------------------|
|SharePoint-Taxonomie: isAvailableForTagging|Owl: datatypeproperty|
|SharePoint-Taxonomie: SharedCustomPropertyForTerm|Owl: OBJECTPROPERTY|
|SharePoint-Taxonomie: LocalCustomPropertyForTerm|Owl: OBJECTPROPERTY|
|SharePoint-Taxonomie: CustomPropertyForTermSet|Owl: OBJECTPROPERTY|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint-Taxonomie-Vokabular

Eine Taxonomie ist ein formales Klassifizierungssystem. Eine Taxonomie gruppiert die Wörter, Bezeichnungen und Begriffe, die etwas beschreiben, und ordnet die Gruppen dann in einer Hierarchie an.

**SharePoint-Taxonomie: Ausdruck**

Stellt einen Term oder ein Schlüsselwort in einer Hierarchie für verwaltete Metadaten dar.

Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ist die atomare Einheit einer SharePoint- [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Jeder [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) gehört zu einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) , das zu einer [termgroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)gehört. 

Die Syntax zum Definieren eines [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) lautet wie folgt:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ist innerhalb eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)-pflichtbereichs vorhanden. DefaultLabel ist der Name des [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , der in der visuellen Darstellung angezeigt wird. Die erforderlichen Felder zum Definieren eines [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) umfassen Folgendes:

- SharePoint-Taxonomie: defaultLabel
- SharePoint-Taxonomie: intermset

Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann:

- Sie müssen sich hierarchisch auf einen anderen [Begriff](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) beziehen, der sowohl die [Begriffe](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) gehören zum gleichen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)angegeben wird.
- Mehrere untergeordnete [Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), aber nur ein einzelner übergeordneter [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).
- Kein übergeordneter [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) definiert, wenn es sich um ein topLevelTermOf-Objekt eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)handelt.
- Haben Sie eine defaultLabel pro [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) Arbeitssprache.
- Nicht vorhanden, wenn weder ein übergeordneter [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)noch der topLevelTermOf ein [termsatz](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)enthält. 
- Sie haben nur eine eindeutige defaultLabel auf derselben hierarchischen Ebene.

**SharePoint-Taxonomie: TermSet**

Stellt eine hierarchische oder flache Gruppe von Term-Objekten dar, die als "TermSet" bezeichnet werden.

Wie der Name schon sagt, [ist TermSet eine Reihe von](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)Begriffen. Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in einem [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) muss einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)angehören. Kein [Begriff](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann unabhängig voneinander vorhanden sein. 

Die Syntax zum Definieren eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) lautet:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) sind in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)logisch zusammengefasst. Das erforderliche Feld zur Definition eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) lautet:

- SharePoint-Taxonomie: termSetName

Im Fall der bereitgestellten termSetName innerhalb der [termgroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)nicht eindeutig ist, fügt Topologiemodell eine Zahl am Ende des Namens an, um die Eindeutigkeit von termSetName (s) beizubehalten.

**SharePoint-Taxonomie: hasTopLevelTerm**

SharePoint verwendet diese Eigenschaft, um den obersten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) im [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), dem Einstiegspunkt für die Hierarchie von [Ausdrücken](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), zuzuordnen. Dies ist eine umgekehrte Relation zur SharePoint-Taxonomie: topLevelTermOf. 

Die folgende Syntax definiert Folgendes:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> Sie können den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) der obersten Ebene eines übergeordneten [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)nicht definieren.

**SharePoint-Taxonomie: topLevelTermOf**

SharePoint-Taxonomie: topLevelTermOf ist die inverse SharePoint-Taxonomie: hasTopLevelTerm

Die folgende Syntax definiert Folgendes:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**SharePoint-Taxonomie: intermset**

Verwenden Sie diese, um einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)zuzuordnen. Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann nur in einem einzelnen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)vorhanden sein. SharePoint erfordert diese Eigenschaft, wenn [ein Ausdruck definiert](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)wird.

## <a name="required-labels"></a>Erforderliche Bezeichnungen

Ihre Organisation möchte möglicherweise eine sorgfältige Planung durchführen, bevor Sie mit der Verwendung von verwalteten Metadaten beginnen. Die Planungsmenge, die Sie ausführen müssen, hängt von der formalen Taxonomie ab. Es hängt auch davon ab, wie viel Kontrolle Sie für Metadaten auferlegen möchten. Auf jeder Ebene der Hierarchie müssen Sie die erforderlichen Lables für einen Ausdruck oder ein TermSet konfigurieren.

Ein Ausdruck kann eine oder mehrere Bezeichnungen in der Standardsprache und NULL oder mehr Bezeichnungen in der nicht standardmäßigen Sprache aufweisen. Falls der Ausdruck Bezeichnungen in einer Sprache aufweist, muss eine der Bezeichnungen die Standardbezeichnung sein.

**SharePoint-Taxonomie: defaultLabel**

Verwenden Sie diese standardmäßige lexikalische Bezeichnung für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , der ein erforderlicher Parameter für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)ist. Wird verwendet, um den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)visuell darzustellen.

Die Syntax zum Definieren einer defaultLabel lautet wie folgt:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Das defaultLabel-Objekt enthält zwei Teile – die Zeichenfolge und das Sprachtag. Die Sprache muss eine der [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) Arbeitssprachen sein. Das defaultLabel muss für alle [Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) im gleichen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)auf derselben hierarchischen Ebene eindeutig sein.

**SharePoint-Taxonomie: termSetName**

Dient zum Abrufen und Festlegen des Namens für das aktuelle TermSet-Objekt.

Dies ist die lexikalische Bezeichnung für einen [termsatz](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)in einer [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) -Arbeitssprache. Dies ist ein erforderlicher Parameter für einen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Wird verwendet, um einen [termsatz](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)visuell darzustellen.

Die Syntax zum Definieren einer termSetName lautet wie folgt:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**SharePoint-Taxonomie: PropertyName**

Ruft den Eigenschaftennamen für das aktuelle TermSet-Objekt ab und legt diesen fest.

Dies ist die lexikalische Bezeichnung für eine SharePoint-Taxonomie: SharedCustomPropertyForTerm, SharePoint-Taxonomie: LocalCustomPropertyForTerm und SharePoint-Taxonomie: CustomPropertyForTermSet in einer [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) Arbeitssprache.

Die SharePoint-Taxonomie: PropertyName wird als Schlüssel der CustomProperty behandelt.

Die Syntax zum Definieren einer propetyName lautet wie folgt:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Optionale Bezeichnungen

Sie können auch optionale Bezeichnungen zu ihrer Taxonomie hinzufügen.

**SharePoint-Taxonomie: otherLabel**

Dies ist die Alternative lexikalische Bezeichnung für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

Die Syntax zum Definieren einer otherLabel lautet wie folgt:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Semantische Beziehungen

Taxonomien weisen hierarchische und manchmal auch eine einfache "Verwandte Terminologie"-assoziative Beziehungen auf, einige weisen jedoch "semantische Beziehungen" oder benutzerdefinierte Beziehungen auf. 

**SharePoint-Taxonomie: Parent**

Dadurch wird ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) hierarchisch mit einem anderen [Begriff](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)verknüpft. Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann [ein Ausdruck auf oberster Ebene](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)sein, für den Fall jedoch nicht, dass er über einen übergeordneten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)verfügen muss. 

Die Syntax zum Definieren eines übergeordneten Elements lautet:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Dies bedeutet, dass TermA1 über übergeordnete Terma verfügt. Umgekehrt bedeutet dies auch, dass TermA1 das untergeordnete Element von Terma ist. Parent-Child-Beziehung ist eine inversible-Beziehung.

**SharePoint-Taxonomie: Child**

Das-Objekt enthält mindestens eine untergeordnete TermSet-Instanz, auf die über die TermSets-Eigenschaft zugegriffen werden kann. Diese Klasse stellt auch Methoden zum Erstellen neuer untergeordneter TermSet-Objekte bereit. Berechtigungen zum Bearbeiten von untergeordneten Term-und TermSet-Instanzen werden in der Gruppe angegeben. 

Dadurch wird ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) hierarchisch mit einem anderen [Begriff](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)verknüpft.

Die Syntax zum Definieren eines untergeordneten Elements lautet:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Dies bedeutet, dass Terma über untergeordnete TermA1 verfügt. Umgekehrt bedeutet dies auch, dass Terma das übergeordnete Element der TermA1 Parent-Child-Beziehung eine inversible Beziehung ist.

## <a name="documentation-notes"></a>Dokumentations Hinweise

In diesem Abschnitt wird die Taxonomie beschrieben, die im Microsoft. SharePoint. Taxonomy-Namespace beschrieben wird.

**SharePoint-Taxonomie: Beschreibung**

Dies ist eine ausführliche Erläuterung einer beliebigen [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) -Vokabular-Entität. 

Die Syntax zum Hinzufügen einer Beschreibung lautet wie folgt:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Benutzerdefinierte Eigenschaften

Ruft die Auflistung der benutzerdefinierten Property-Objekte für das aktuelle Term-Objekt aus dem schreibgeschützten Wörterbuch ab.

Benutzerdefinierte Eigenschaften sind Schlüssel-Werte-Paare, die für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder einen [termsatz](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)definiert werden können, um die Beschreibung des [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder eines [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)sätzes zu erweitern. SharePoint gibt den Schlüssel der benutzerdefinierten Eigenschaft mit der Hilfe von PropertyName an.

**SharePoint-Taxonomie: CustomPropertyForTermSet**

Die folgende Syntax definiert Folgendes:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**SharePoint-Taxonomie: SharedCustomPropertyForTerm**

Wenn die benutzerdefinierte Eigenschaft für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) zusammen mit dem Ausdruck mitgetragen werden muss, wenn Sie den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) an anderer Stelle wieder [verwenden, müssen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)Sie ihn unter SharedCustomPropertyForTerm definieren.

Die folgende Syntax definiert Folgendes:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**SharePoint-Taxonomie: LocalCustomPropertyForTerm**

Wenn die benutzerdefinierte Eigenschaft für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nicht zusammen mit dem [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)mitgetragen werden muss, wenn Sie den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) an anderer Stelle wieder verwenden, müssen Sie ihn unter LocalCustomPropertyForTerm definieren.

Die folgende Syntax definiert Folgendes:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Dateneigenschaften

Auf jeder Ebene der Hierarchiekönnen Sie bestimmte Dateneigenschaften für einen Ausdruck oder ein TermSet konfigurieren.

**SharePoint-Taxonomie: isAvailableForTagging**

Verwenden Sie diese, um anzugeben, ob ein [Begriff](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder ein [ausdrucksset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) in SharePoint-Listen und-Bibliotheken verfügbar ist.  

Die Syntax hierfür lautet:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Domäne und Bereich

Die folgende Tabelle beschreibt die Domäne und den Bereich des SharePoint-Taxonomie-Vokabulars.

|Prädikate/Verb|Bedeutung|Domäne|Bereich|
|:--------------|:------|:-----|:----|
intermset|Im Ausdruckssätze|Begriff|Ausdruckssatz|
intermgroup|In Ausdrucksgruppe|TermSet|Termgroup|
topLevelTermOf|Ist auf oberster Ebene der Begriff|Begriff|TermSet|
hasTopLevelTerm|Hat Ausdruck auf oberster Ebene|Ausdruckssatz|Begriff|
termSetName|Ausdrucksgruppe hat Namen|Begriff|Einfaches Literal|
defaultLabel|Ausdruck hat Standardbezeichnung|Begriff|Einfaches Literal|
otherLabel|Ausdruck hat andere Bezeichnung|Begriff|Einfaches Literal|
PropertyName|Besitzt Eigenschaftenbezeichnung|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolean, String, Integer, Decimal, Double|
|description|Beschreibung enthält|Alle|Einfaches Literal|
|übergeordnetes Element|Übergeordnetes Element|Begriff|Begriff|
|untergeordneten|Untergeordnetes Element|Begriff|Begriff|
|isAvailableForTagging|Steht für Tagging zur Verfügung|Ausdruck, Ausdruckssätze|Boolesch|
|SharedCustomPropertyForTerm|Verfügt über freigegebene benutzerdefinierte Eigenschaft|Begriff|Boolean, String, Integer, Decimal, Double|
|LocalCustomPropertyForTerm|Verfügt über eine lokale benutzerdefinierte Eigenschaft|Begriff|Boolean, String, Integer, Decimal, Double|
|CustomPropertyForTermSet|Verfügt über eine benutzerdefinierte Eigenschaft|TermSet|Boolean, String, Integer, Decimal, Double|

[SKOS](https://www.w3.org/TR/skos-primer/) gültige Szenarien, die von der [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) nicht zugelassen werden:

- Hierarchische Redundanz – ein [SKOS](https://www.w3.org/TR/skos-primer/) -Konzept kann gleichzeitig an mehrere umfassendere Konzepte angehängt werden, aber eine SharePoint-Taxonomie: Term kann nur eine SharePoint-Taxonomie haben: Parent, daher zyklische Abhängigkeit von Begriffen ist ebenfalls nicht zulässig.
- Verwaiste Ausdrücke sind in der SharePoint-Taxonomie nicht zulässig. Jede SharePoint-Taxonomie: Term sollte entweder eine SharePoint-Taxonomie haben: Parent oder sollte die SharePoint-Taxonomie sein: topLevelTermOf ein TermSet.
- Die SharePoint-Taxonomie unterstützt keine assoziativen Beziehungen.
- Die SharePoint-Taxonomie erlaubt nur 2 Arten hierarchischer Beziehungen – SharePoint-Taxonomie: Parent und SharePoint-Taxonomie: Child. 
- Im Gegensatz zu [SKOS](https://www.w3.org/TR/skos-primer/) kann die hierarchische Beziehung in SharePoint-Taxonomie-Vokabular nur mit Ausdrücken innerhalb desselben ausdrucksset festgelegt werden.

## <a name="see-also"></a>Siehe auch

[Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats](import-term-set-skos.md)

