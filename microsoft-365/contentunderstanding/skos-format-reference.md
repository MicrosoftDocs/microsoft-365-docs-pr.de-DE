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
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SKOS-Formatreferenz für SharePoint-Taxonomie

Dieser Artikel enthält RDF-Vokabular, das zur Darstellung der [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) verwendet wird, und basiert auf [SKOS](https://www.w3.org/TR/skos-primer/). Zur Serialisierung dieser RDF-Syntax verwenden Sie RDF [TURTLE](https://www.w3.org/TR/turtle/).

Die folgende Tabelle zeigt die [SKOS](https://www.w3.org/TR/skos-primer/)-Entsprechungen für das Vokabular der [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy). SharePoint unterstützt keine [SKOS](https://www.w3.org/TR/skos-primer/)-Werte, die keine SharePoint-Entsprechung zur Taxonomie aufweisen.

|SharePoint-Taxonomie|SKOS-Entsprechung|
|:-----------------|:--------------|
|sharepoint-taxonomy:Term|skos:Concept|
|sharepoint-taxonomy:TermSet|skos:ConceptScheme|
|sharepoint-taxonomy:inTermSet|skos:inScheme|
|sharepoint-taxonomy:hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-taxonomy:topLevelTermOf|skos:topConceptOf|
|sharepoint-taxonomy:defaultLabel|skos:prefLabel|
|sharepoint-taxonomy:termSetName|skos:prefLabel|
|sharepoint-taxonomy:propertyName|skos:prefLabel|
|sharepoint-taxonomy:otherLabel|skos:altLabel|
|sharepoint-taxonomy:description|skos:definition|
|sharepoint-taxonomy:parent|skos:broader|
|sharepoint-taxonomy:child|skos:narrower|

Die folgende Tabelle zeigt die Entitäten des aus [OWL](https://www.w3.org/TR/owl2-primer/) abgeleiteten Vokabulars der SharePoint-Taxonomie.

|SharePoint-Taxonomie – Vokabular|Abgeleitet von OWL|
|:-----------------------------|:----------------------|
|sharepoint-taxonomy:isAvailableForTagging|owl:datatypeproperty|
|sharepoint-taxonomy:SharedCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:LocalCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint-Taxonomie – Vokabular

Bei einer Taxonomie handelt es sich um ein formales Klassifizierungssystem. Eine Taxonomie gruppiert die Wörter, Bezeichnungen und Ausdrücke, die etwas beschreiben, und ordnet die Gruppen hierarchisch an.

**sharepoint-taxonomy:Term**

Stellt einen Ausdruck oder ein Schlüsselwort in einer verwalteten Metadatenhierarchie dar.

Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ist die atomare Einheit eines SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Jeder [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) gehört zu einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) der zu einer [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group) gehört. 

Die Syntax zum Definieren eines [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) lautet wie folgt:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) existiert obligatorisch innerhalb eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). DefaultLabel ist der Name des [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) wie er in der visuellen Darstellung dargestellt wird. Die erforderlichen Felder zum Definieren eines [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) enthalten:

- sharepoint-taxonomy:defaultLabel
- sharepoint-taxonomy:inTermSet

Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann:

- Hierarchisch mit einem anderen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in Beziehung gesetzt werden, vorausgesetzt, beide [Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) gehören zum selben [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Mehrere untergeordnete [Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) haben, aber nur einen einzigen übergeordneten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).
- Keinen übergeordneten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) definiert haben, wenn es sich um einen topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) handelt.
- Ein defaultLabel pro [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-Arbeitssprache haben. 
- Nicht existieren, wenn es weder einen übergeordneten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) enthält, noch der TopLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) ist. 
- Nur ein eindeutiges defaultLabel in der gleichen hierarchischen Ebene haben.

**sharepoint-taxonomy:TermSet**

Stellt einen hierarchischen oder unstrukturierten Satz von Term-Objekten dar, die als "Ausdruckssatz" bezeichnet werden.

Wie der Name sagt, ist TermSet ein Satz von [Ausdrücken](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in einem [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) muss in einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) gehören. Kein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann unabhängig voneinander vorhanden sein. 

Die Syntax zum Definieren eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) lautet:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) werden logisch in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)gruppiert. Das erforderliche Feld zum Definieren eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) lautet:

- sharepoint-taxonomy:termSetName

Wenn der angegebene termSetName innerhalb der [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group) nicht eindeutig ist, hängt SharePoint eine Nummer an das Ende des Namens an, um die Eindeutigkeit von termSetName(s) beizubehalten.

**sharepoint-taxonomy:hasTopLevelTerm**

SharePoint verwendet diese Eigenschaft zum Zuordnen des obersten [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) im [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), der den Einstiegspunkt zur Hierarchie der[Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) darstellt. Hierbei handelt es sich um einen umgekehrten Bezug zu sharepoint-taxonomy:topLevelTermOf. 

Die Syntax, um dies zu definieren, lautet:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> Sie können den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) der obersten Ebene eines übergeordneten [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nicht definieren.

**sharepoint-taxonomy:topLevelTermOf**

Sharepoint-taxonomy:topLevelTermOf ist die Umkehrung der sharepoint-taxonomy:hasTopLevelTerm

Die Syntax, um dies zu definieren, lautet:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

Hiermit ordnen Sie einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) einem [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) zu. Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kann nur in einem einzigen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) vorhanden sein. SharePoint erfordert diese Eigenschaft beim [Definieren eines Ausdrucks](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Erforderliche Bezeichnungen

Möglicherweise möchte Ihre Organisation eine sorgfältige Planung vornehmen, bevor Sie mit der Verwendung verwalteter Metadaten beginnen. Der Umfang der Planung, die Sie vornehmen müssen, hängt davon ab, wie formal Ihre Taxonomie ist. Es hängt auch davon ab, wie viel Kontrolle Sie den Metadaten auferlegen möchten. Auf jeder Ebene der Hierarchie müssen Sie die erforderlichen Bezeichnungen für einen Ausdruck oder ein TermSet konfigurieren.

Ein Ausdruck kann eine oder mehrere Bezeichnungen in der Standardsprache haben, und keine oder mehrere Bezeichnungen in einer anderen als der Standardsprache. Wenn der Ausdruck Bezeichnungen in einer Sprache hat, muss eine der Bezeichnungen die Standardbezeichnung sein.

**sharepoint-taxonomy:defaultLabel**

Verwenden Sie diese standardmäßige lexikalische Bezeichnung für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), der ein erforderlicher Parameter für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ist. Wird verwendet, um den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) darzustellen.

Die Syntax zum Definieren eines defaultLabel lautet:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Der defaultLabel enthält zwei Teile: die Zeichenfolge und das Sprachentag. Die Sprache muss eine der [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-Arbeitssprachen sein. Der defaultLabel muss für alle [Ausdrücke](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) desselben [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) auf derselben hierarchischen Ebene eindeutig sein.

**sharepoint-taxonomy:termSetName**

Ruft den Namen für das aktuelle TermSet-Objekt ab und legt ihn fest.

Hierbei handelt es sich um die lexikalische Bezeichnung für einen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) in einer [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-Arbeitssprache. Dieser Parameter ist für einen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) erforderlich.. Wird verwendet, um einen [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) darzustellen.

Die Syntax zum Definieren eines termSetName lautet:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

Ruft den Eigenschaftennamen für das aktuelle TermSet-Objekt ab und legt ihn fest.

Dies ist die lexikalische Bezeichnung für eine sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm und sharepoint-taxonomy:CustomPropertyForTermSet in einer [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-Arbeitssprache.

Der sharepoint-taxonomy:propertyName wird als Schlüssel der CustomProperty behandelt.

Die Syntax zum Definieren eines propetyName lautet:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Optionale Bezeichnungen

Sie können Ihrer Taxonomie auch optionale Bezeichnungen hinzufügen.

**sharepoint-taxonomy:otherLabel**

Dies ist die Alternative lexikalische Bezeichnung für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

Die Syntax zum Definieren eines otherLabel lautet:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Semantische Beziehungen

Taxonomien haben hierarchische und manchmal eine einfache assoziative Beziehung zu einem " verwandten Ausdruck", aber einige haben "semantische Beziehungen" oder benutzerdefinierte Beziehungen. 

**sharepoint-taxonomy:parent**

Damit wird ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) hierarchisch zu einem anderen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in Beziehung gesetzt. Ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) könnte ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) der obersten Ebene eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) sein, aber falls dies nicht der Fall ist, muss es einen übergeordneten [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) aufweisen. 

Die Syntax zum Definieren eines übergeordneten Elements lautet:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Dies bedeutet, dass TermA das übergeordnete Element und TermA das untergeordnete Element ist.

**sharepoint-taxonomy:child**

Das Objekt enthält eine oder mehrere untergeordnete TermSet-Instanzen, auf die über die TermSets-Eigenschaft zugegriffen werden kann. Diese Klasse bietet auch Methoden zum Erstellen neuer untergeordneter TermSet-Objekte. Die Berechtigungen zum Bearbeiten untergeordneter Ausdruck- und TermSet-Instanzen werden in der Gruppe angegeben. 

Damit wird ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) hierarchisch zu einem anderen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in Beziehung gesetzt.

Die Syntax zum Definieren eines untergeordneten Elements lautet:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Dies bedeutet, dass TermA das übergeordnete Element und TermA das untergeordnete Element ist.

## <a name="documentation-notes"></a>Dokumentationsnotizen

Dieser Abschnitt behandelt die Taxonomie, die im Microsoft.SharePoint.Taxonomie "Namespace" detailliert beschrieben wird.

**sharepoint-taxonomy:description**

Dies ist eine detaillierte Erklärung jeder Entität des Vokabulars der [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy). 

Die Syntax für das Hinzufügen einer Beschreibung lautet:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Benutzerdefinierte Eigenschaften

Ruft die Sammlung der benutzerdefinierten Eigenschaftsobjekte für das aktuelle Term-Objekt aus dem schreibgeschützten Schlüsselverzeichnis ab.

Benutzerdefinierte Eigenschaften sind Schlüssel-Werte-Paare, die für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder ein [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) definiert werden können, um die Beschreibung des [Ausdrucks](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder eines [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) zu erweitern. SharePoint gibt den Schlüssel der benutzerdefinierten Eigenschaft mit Hilfe von propertyName an.

**sharepoint-taxonomy:CustomPropertyForTermSet**

Die Syntax, um dies zu definieren, lautet:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

Wenn die benutzerdefinierte Eigenschaft für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) mit dem [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) mitgeführt werden muss, wenn Sie den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) woanders wiederverwenden, müssen Sie ihn unter SharedCustomPropertyForTerm definieren.

Die Syntax, um dies zu definieren, lautet:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

Wenn die benutzerdefinierte Eigenschaft für einen [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nicht mit dem [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) mitgeführt werden muss, wenn Sie den [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) woanders wiederverwenden, dann müssen Sie ihn unter LocalCustomPropertyForTerm definieren.

Die Syntax, um dies zu definieren, lautet:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Dateneigenschaften

Auf jeder Ebene der Hierarchie können Sie bestimmte Dateneigenschaften für einen Ausdruck oder TermSet konfigurieren.

**sharepoint-taxonomy:isAvailableForTagging**

Verwenden Sie dies, um anzugeben, ob ein [Ausdruck](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) oder ein [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) in SharePoint-Listen und -Bibliotheken verfügbar ist.  

Die Syntax dafür lautet:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Domäne und Bereich

Die folgende Tabelle beschreibt die Domäne und den Bereich des Vokabulars der SharePoint-Taxonomie.

|Prädikate/Verb|Bedeutung|Domäne|Bereich|
|:--------------|:------|:-----|:----|
inTermSet|Im Ausdruckssatz|Ausdruck|Ausdruckssatz|
inTermGroup|In Ausdrucksgruppe|TermSet|TermGroup|
topLevelTermOf|Ist Ausdruck der obersten Ebene von|Ausdruck|TermSet|
hasTopLevelTerm|Hat Ausdruck der obersten Ebene|Ausdruckssatz|Ausdruck|
termSetName|Ausdruckssatz hat Namen|Ausdruck|Einfaches Literal|
defaultLabel|Ausdruck hat Standardbezeichnung|Ausdruck|Einfaches Literal|
otherLabel|Ausdruck hat andere Bezeichnung|Ausdruck|Einfaches Literal|
propertyName|Hat Eigenschaftenbezeichnung|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolesch, Zeichenfolge, Ganze Zahl, Dezimal, Duplikat|
|description|Hat Beschreibung|Alle|Einfaches Literal|
|parent|Hat ein übergeordnetes Element|Ausdruck|Ausdruck|
|child|Hat untergeordnetes Element|Ausdruck|Ausdruck|
|isAvailableForTagging|Ist für Tagging verfügbar|Term, Ausdruckssatz|Boolesch|
|SharedCustomPropertyForTerm|Hat gemeinsame benutzerdefinierte Eigenschaft|Ausdruck|Boolesch, Zeichenfolge, Ganze Zahl, Dezimal, Duplikat|
|LocalCustomPropertyForTerm|Hat lokale benutzerdefinierte Eigenschaft|Ausdruck|Boolesch, Zeichenfolge, Ganze Zahl, Dezimal, Duplikat|
|CustomPropertyForTermSet|Hat benutzerdefinierte Eigenschaft|TermSet|Boolesch, Zeichenfolge, Ganze Zahl, Dezimal, Duplikat|

[SKOS](https://www.w3.org/TR/skos-primer/) gültige Szenarien, die [SharePoint-Taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) nicht zulassen:

- Hierarchische Redundanz – Ein [SKOS](https://www.w3.org/TR/skos-primer/)-Konzept kann gleichzeitig an mehrere breitere Konzepte angehängt werden, aber ein sharepoint-taxonomy:Term kann nur ein sharepoint-taxonomy:parent aufweisen, daher ist auch eine zyklische Abhängigkeit von Ausdrücken nicht zulässig.
- Verwaiste Ausdrücke sind in der SharePoint-Taxonomie nicht zulässig. Jeder sharepoint-taxonomy:Term sollte entweder einen sharepoint-taxonomy:parent haben oder es sollte der sharepoint-taxonomy:topLevelTermOf eines TermSets sein.
- Die SharePoint-Taxonomie unterstützt keine assoziativen Beziehungen.
- Die SharePoint-Taxonomie erlaubt nur 2 Arten von hierarchischen Beziehungen: sharepoint-taxonomy:parent und sharepoint-taxonomy:child. 
- Im Gegensatz zu [SKOS](https://www.w3.org/TR/skos-primer/) kann die hierarchische Beziehung im Vokabular der SharePoint-Taxonomie nur mit Ausdrücken innerhalb desselben TermSets hergestellt werden.

## <a name="see-also"></a>Weitere Informationen:

[Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats](import-term-set-skos.md)

