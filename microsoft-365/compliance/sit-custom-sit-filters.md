---
title: Referenz zu benutzerdefinierten Filtern für vertrauliche Informationstypen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Dieser Artikel enthält eine Liste der Filter, die in benutzerdefinierte Typen vertraulicher Informationen codiert werden können.
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322702"
---
# <a name="custom-sensitive-information-type-filters-reference"></a>Benutzerdefinierter Verweis auf Filter für vertrauliche Informationstypen

In Microsoft können Sie Filter oder zusätzliche Prüfungen definieren, während Sie benutzerdefinierte Typen vertraulicher Informationen (SIT) erstellen.

## <a name="list-of-supported-filters-and-use-cases"></a>Liste der unterstützten Filter und Anwendungsfälle

### <a name="alldigitssame-exclude"></a>AllDigitsSame-Ausschluss

Beschreibung: Ermöglicht das Ausschließen von Übereinstimmungen, die alle Ziffern als doppelte Ziffern aufweisen, z. B. 1111111111 oder 111-111-111

Definieren von Filtern
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

Verwenden des Pakets im Regelpaket auf Entitätsebene
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

Verwenden des Pakets im Regelpaket auf Musterebene
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a>TextMatchFilter StartsWith 

Beschreibung: Ermöglicht es Ihnen, die Anfangszeichen für die Entität zu definieren. Es weist zwei Varianten auf: "Einschließen" und "Ausschließen".

So schließen Sie beispielsweise die Zahlen aus, die mit 0500, 91, 091, 010 in einer Liste wie der folgenden beginnen:

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

Sie können diese XML-Datei verwenden.

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
Um z. B. die Zahlen ab 0500, 91, 091 und 0100 in eine Liste wie die folgende einzuschließen: 

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

Sie können diese XML-Datei verwenden.

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a>TextMatchFilter EndsWith 

Beschreibung: Ermöglicht es Ihnen, die Endzeichen für die Entität zu definieren. 

Um beispielsweise die Zahlen auszuschließen, die mit 0500,91,091, 0100 enden, in einer Liste wie der folgenden:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

Sie können diese XML-Datei verwenden.

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

So fügen Sie beispielsweise die Zahlen, die mit 0500, 91, 091, 0100 enden, in eine Liste wie die folgende ein:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

Sie können diese XML-Datei verwenden.

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a>TextMatchFilter Full

Beschreibung: Ermöglicht es Ihnen, bestimmte Übereinstimmungen zu verbieten, um zu verhindern, dass sie die Regel auslösen. Schließen Sie beispielsweise 411111111111111111 aus der Liste gültiger Kreditkartenüberstimmungen aus.

Beispiel: Um Kreditkartennummern wie 41111111111111111111111 und 32418910311111 in einer Liste wie der folgenden auszuschließen:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

Sie können diese XML-Datei verwenden.

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

Beispiel: Um Kreditkartennummern wie 41111111111111111111111 und 32418910311111 in eine Liste wie die folgende einzuschließen:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

Sie können diese XML-Datei verwenden.

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a>TextMatchFilter-Präfix

Beschreibung: Ermöglicht es Ihnen, die vorherigen Zeichen zu definieren, die immer eingeschlossen oder ausgeschlossen werden sollen. Wenn z. B. der Kreditkartennummer "Bestell-ID:" vorangestellt ist, entfernen Sie die Übereinstimmung aus den gültigen Übereinstimmungen.

Um z. B. Vorkommen von Telefonnummern auszuschließen, die **Telefon Nummer** haben, und rufen Sie mich in einer Liste wie der folgenden in Zeichenfolgen vor der Telefonnummer **an:**

- Telefonnummer 091-8974-653278
- Telefon 45-124576532-123
- 45-124576532-123

Sie können diese XML-Datei verwenden.

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

Um beispielsweise Vorkommen mit **Kreditkarten-** und **Kartenzeichenfolgen vor** der Kreditkartennummer in eine Liste wie die folgende einzuschließen:

- Kreditkarte 45-124576532-123 
- 45-124576532-123 (die Telefonnummer sein könnte)

Sie können diese XML-Datei verwenden.

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a>TextMatchFilter-Suffix

Beschreibung: Ermöglicht es Ihnen, die folgenden Zeichen zu definieren, die immer eingeschlossen oder ausgeschlossen werden sollen. Wenn z. B. auf die Kreditkartennummer "/xuid" folgt, entfernen Sie die Übereinstimmung aus den gültigen Übereinstimmungen.

Beispiel: Häufigstes Ausschließen von Vorkommen, wenn in einer Liste wie dieser 5 weitere Instanzen von vier Ziffern als Suffix vorhanden sind:

- 1234-5678-9321 4500 9870 6321 48925566
- 1234-5678-9321

Sie können diese XML-Datei verwenden.

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
Um z. B. Vorkommen auszuschließen, wenn auf sie **/xuidsuffix** folgt, wie in dieser Liste:

- 1234-5678-9321 /xuid
- 1234-5678-9321

Sie können diese XML-Datei verwenden.

''xml <Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      <Term>/xuid</Term>
    </Group> </Keyword>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a>Verwenden von Filtern in Regelpaketen

Filter können für die gesamte SIT oder ein Muster definiert werden. Hier sind einige Codeausschnittbeispiele. 

### <a name="at-sensitive-information-type-level"></a>Auf Der Ebene der vertraulichen Informationstypen

Filter bei Entity – deckt alle untergeordneten Muster ab

Die Filter werden auf **alle** Instanzen angewendet, die von einem der Muster in diesem Entitäts-/vertraulichen Typ klassifiziert werden.

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a>Auf der Ebene der vertraulichen Informationstypen im individuellen Muster

Filtert nur auf Musterebene.

Der Filter wird auf die Instanzen angewendet, die mit dem Muster übereinstimmen.

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a>Auf Der Ebene der vertraulichen Informationstypen und einem zusätzlichen Filter nach einigen Mustern dieser Entität

Filter bei Entity + Pattern

Die Filter werden auf **alle** Instanzen angewendet, die von einem der Muster in diesem Entitäts-/vertraulichen Typ klassifiziert werden. Der Filter auf Musterebene filtert die Instanzen, die mit diesem Muster übereinstimmen.

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a>Weitere Informationen

- [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md)

- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)

- [Wonach die DLP-Funktionen suchen](what-the-dlp-functions-look-for.md)
