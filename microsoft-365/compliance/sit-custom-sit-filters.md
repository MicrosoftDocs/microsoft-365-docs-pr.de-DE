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
# <a name="custom-sensitive-information-type-filters-reference"></a><span data-ttu-id="e81dd-103">Benutzerdefinierter Verweis auf Filter für vertrauliche Informationstypen</span><span class="sxs-lookup"><span data-stu-id="e81dd-103">Custom sensitive information type filters reference</span></span>

<span data-ttu-id="e81dd-104">In Microsoft können Sie Filter oder zusätzliche Prüfungen definieren, während Sie benutzerdefinierte Typen vertraulicher Informationen (SIT) erstellen.</span><span class="sxs-lookup"><span data-stu-id="e81dd-104">In Microsoft you can define filters or additional checks while creating a custom sensitive information types (SIT).</span></span>

## <a name="list-of-supported-filters-and-use-cases"></a><span data-ttu-id="e81dd-105">Liste der unterstützten Filter und Anwendungsfälle</span><span class="sxs-lookup"><span data-stu-id="e81dd-105">List of supported filters and use cases</span></span>

### <a name="alldigitssame-exclude"></a><span data-ttu-id="e81dd-106">AllDigitsSame-Ausschluss</span><span class="sxs-lookup"><span data-stu-id="e81dd-106">AllDigitsSame Exclude</span></span>

<span data-ttu-id="e81dd-107">Beschreibung: Ermöglicht das Ausschließen von Übereinstimmungen, die alle Ziffern als doppelte Ziffern aufweisen, z. B. 1111111111 oder 111-111-111</span><span class="sxs-lookup"><span data-stu-id="e81dd-107">Description: Allows you to exclude matches which have all digits as duplicate digits, like 111111111 or 111-111-111</span></span>

<span data-ttu-id="e81dd-108">Definieren von Filtern</span><span class="sxs-lookup"><span data-stu-id="e81dd-108">Defining filters</span></span>
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

<span data-ttu-id="e81dd-109">Verwenden des Pakets im Regelpaket auf Entitätsebene</span><span class="sxs-lookup"><span data-stu-id="e81dd-109">Using it in rule package at the entity level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

<span data-ttu-id="e81dd-110">Verwenden des Pakets im Regelpaket auf Musterebene</span><span class="sxs-lookup"><span data-stu-id="e81dd-110">Using it in rule package at the pattern level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a><span data-ttu-id="e81dd-111">TextMatchFilter StartsWith</span><span class="sxs-lookup"><span data-stu-id="e81dd-111">TextMatchFilter StartsWith</span></span> 

<span data-ttu-id="e81dd-112">Beschreibung: Ermöglicht es Ihnen, die Anfangszeichen für die Entität zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e81dd-112">Description: Allows you to define the starting characters for the entity.</span></span> <span data-ttu-id="e81dd-113">Es weist zwei Varianten auf: "Einschließen" und "Ausschließen".</span><span class="sxs-lookup"><span data-stu-id="e81dd-113">It has two variants, include and exclude.</span></span>

<span data-ttu-id="e81dd-114">So schließen Sie beispielsweise die Zahlen aus, die mit 0500, 91, 091, 010 in einer Liste wie der folgenden beginnen:</span><span class="sxs-lookup"><span data-stu-id="e81dd-114">For example to exclude the numbers starting with 0500, 91, 091, 010 in a list like this:</span></span>

- <span data-ttu-id="e81dd-115">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="e81dd-115">0500-4500-027</span></span>
- <span data-ttu-id="e81dd-116">91564721450</span><span class="sxs-lookup"><span data-stu-id="e81dd-116">91564721450</span></span>
- <span data-ttu-id="e81dd-117">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="e81dd-117">91-8523697410</span></span>
- <span data-ttu-id="e81dd-118">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="e81dd-118">700-8956-7844</span></span>
- <span data-ttu-id="e81dd-119">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="e81dd-119">1000-3265-9874</span></span>
- <span data-ttu-id="e81dd-120">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="e81dd-120">0100-7892-3012</span></span>

<span data-ttu-id="e81dd-121">Sie können diese XML-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-121">you can use this xml</span></span>

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
<span data-ttu-id="e81dd-122">Um z. B. die Zahlen ab 0500, 91, 091 und 0100 in eine Liste wie die folgende einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="e81dd-122">For example, to include the numbers starting with 0500, 91, 091, 0100 in a list like this:</span></span> 

- <span data-ttu-id="e81dd-123">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="e81dd-123">0500-4500-027</span></span>
- <span data-ttu-id="e81dd-124">91564721450</span><span class="sxs-lookup"><span data-stu-id="e81dd-124">91564721450</span></span>
- <span data-ttu-id="e81dd-125">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="e81dd-125">91-8523697410</span></span>
- <span data-ttu-id="e81dd-126">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="e81dd-126">700-8956-7844</span></span>
- <span data-ttu-id="e81dd-127">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="e81dd-127">1000-3265-9874</span></span>
- <span data-ttu-id="e81dd-128">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="e81dd-128">0100-7892-3012</span></span>

<span data-ttu-id="e81dd-129">Sie können diese XML-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-129">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a><span data-ttu-id="e81dd-130">TextMatchFilter EndsWith</span><span class="sxs-lookup"><span data-stu-id="e81dd-130">TextMatchFilter EndsWith</span></span> 

<span data-ttu-id="e81dd-131">Beschreibung: Ermöglicht es Ihnen, die Endzeichen für die Entität zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e81dd-131">Description: Allows you to define the ending characters for the entity.</span></span> 

<span data-ttu-id="e81dd-132">Um beispielsweise die Zahlen auszuschließen, die mit 0500,91,091, 0100 enden, in einer Liste wie der folgenden:</span><span class="sxs-lookup"><span data-stu-id="e81dd-132">For example, to exclude the numbers ending with 0500,91,091, 0100 in a list like this:</span></span>

- <span data-ttu-id="e81dd-133">1234567891</span><span class="sxs-lookup"><span data-stu-id="e81dd-133">1234567891</span></span>
- <span data-ttu-id="e81dd-134">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="e81dd-134">1234-5678-0091</span></span>
- <span data-ttu-id="e81dd-135">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="e81dd-135">1234.4567.7091</span></span>
- <span data-ttu-id="e81dd-136">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="e81dd-136">1234-8091-4564</span></span>

<span data-ttu-id="e81dd-137">Sie können diese XML-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-137">you can use this xml</span></span>

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

<span data-ttu-id="e81dd-138">So fügen Sie beispielsweise die Zahlen, die mit 0500, 91, 091, 0100 enden, in eine Liste wie die folgende ein:</span><span class="sxs-lookup"><span data-stu-id="e81dd-138">For example, to include the numbers ending with 0500, 91, 091, 0100, in a list like this:</span></span>

- <span data-ttu-id="e81dd-139">1234567891</span><span class="sxs-lookup"><span data-stu-id="e81dd-139">1234567891</span></span>
- <span data-ttu-id="e81dd-140">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="e81dd-140">1234-5678-0091</span></span>
- <span data-ttu-id="e81dd-141">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="e81dd-141">1234.4567.7091</span></span>
- <span data-ttu-id="e81dd-142">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="e81dd-142">1234-8091-4564</span></span>

<span data-ttu-id="e81dd-143">Sie können diese XML-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-143">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a><span data-ttu-id="e81dd-144">TextMatchFilter Full</span><span class="sxs-lookup"><span data-stu-id="e81dd-144">TextMatchFilter Full</span></span>

<span data-ttu-id="e81dd-145">Beschreibung: Ermöglicht es Ihnen, bestimmte Übereinstimmungen zu verbieten, um zu verhindern, dass sie die Regel auslösen.</span><span class="sxs-lookup"><span data-stu-id="e81dd-145">Description: Allows you to prohibit certain matches to prevent them from triggering the rule.</span></span> <span data-ttu-id="e81dd-146">Schließen Sie beispielsweise 411111111111111111 aus der Liste gültiger Kreditkartenüberstimmungen aus.</span><span class="sxs-lookup"><span data-stu-id="e81dd-146">For example, exclude 4111111111111111 from the list of valid credit card matches.</span></span>

<span data-ttu-id="e81dd-147">Beispiel: Um Kreditkartennummern wie 41111111111111111111111 und 32418910311111 in einer Liste wie der folgenden auszuschließen:</span><span class="sxs-lookup"><span data-stu-id="e81dd-147">For example, to exclude credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="e81dd-148">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="e81dd-148">4485 3647 3952 7352</span></span>
- <span data-ttu-id="e81dd-149">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="e81dd-149">4111111111111111</span></span>
- <span data-ttu-id="e81dd-150">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="e81dd-150">3241891031113111</span></span>

<span data-ttu-id="e81dd-151">Sie können diese XML-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-151">you can use this xml</span></span>

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

<span data-ttu-id="e81dd-152">Beispiel: Um Kreditkartennummern wie 41111111111111111111111 und 32418910311111 in eine Liste wie die folgende einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="e81dd-152">For example, to include credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="e81dd-153">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="e81dd-153">4485 3647 3952 7352</span></span>
- <span data-ttu-id="e81dd-154">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="e81dd-154">4111111111111111</span></span>
- <span data-ttu-id="e81dd-155">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="e81dd-155">3241891031113111</span></span>

<span data-ttu-id="e81dd-156">Sie können diese XML-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-156">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a><span data-ttu-id="e81dd-157">TextMatchFilter-Präfix</span><span class="sxs-lookup"><span data-stu-id="e81dd-157">TextMatchFilter Prefix</span></span>

<span data-ttu-id="e81dd-158">Beschreibung: Ermöglicht es Ihnen, die vorherigen Zeichen zu definieren, die immer eingeschlossen oder ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e81dd-158">Description: Allows you to define the preceding characters that should be always included or excluded.</span></span> <span data-ttu-id="e81dd-159">Wenn z. B. der Kreditkartennummer "Bestell-ID:" vorangestellt ist, entfernen Sie die Übereinstimmung aus den gültigen Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="e81dd-159">For example, if Credit card number is preceded by ‘Order ID:’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="e81dd-160">Um z. B. Vorkommen von Telefonnummern auszuschließen, die **Telefon Nummer** haben, und rufen Sie mich in einer Liste wie der folgenden in Zeichenfolgen vor der Telefonnummer **an:**</span><span class="sxs-lookup"><span data-stu-id="e81dd-160">For example, to exclude occurrences of phone numbers which have **Phone number** and **call me at** strings before the phone number, in a list like this:</span></span>

- <span data-ttu-id="e81dd-161">Telefonnummer 091-8974-653278</span><span class="sxs-lookup"><span data-stu-id="e81dd-161">phone number 091-8974-653278</span></span>
- <span data-ttu-id="e81dd-162">Telefon 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="e81dd-162">Phone 45-124576532-123</span></span>
- <span data-ttu-id="e81dd-163">45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="e81dd-163">45-124576532-123</span></span>

<span data-ttu-id="e81dd-164">Sie können diese XML-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-164">you can use this xml</span></span>

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

<span data-ttu-id="e81dd-165">Um beispielsweise Vorkommen mit **Kreditkarten-** und **Kartenzeichenfolgen vor** der Kreditkartennummer in eine Liste wie die folgende einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="e81dd-165">For example, to include occurrences that have **credit card** and **card #** strings before the credit card number, in a list like this:</span></span>

- <span data-ttu-id="e81dd-166">Kreditkarte 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="e81dd-166">Credit card 45-124576532-123</span></span> 
- <span data-ttu-id="e81dd-167">45-124576532-123 (die Telefonnummer sein könnte)</span><span class="sxs-lookup"><span data-stu-id="e81dd-167">45-124576532-123  (which could be phone number)</span></span>

<span data-ttu-id="e81dd-168">Sie können diese XML-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-168">you can use this xml</span></span>

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

### <a name="textmatchfilter-suffix"></a><span data-ttu-id="e81dd-169">TextMatchFilter-Suffix</span><span class="sxs-lookup"><span data-stu-id="e81dd-169">TextMatchFilter Suffix</span></span>

<span data-ttu-id="e81dd-170">Beschreibung: Ermöglicht es Ihnen, die folgenden Zeichen zu definieren, die immer eingeschlossen oder ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e81dd-170">Description: Allows you to define the following characters that should be always included or excluded.</span></span> <span data-ttu-id="e81dd-171">Wenn z. B. auf die Kreditkartennummer "/xuid" folgt, entfernen Sie die Übereinstimmung aus den gültigen Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="e81dd-171">For example, if Credit card number is followed by ‘/xuid’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="e81dd-172">Beispiel: Häufigstes Ausschließen von Vorkommen, wenn in einer Liste wie dieser 5 weitere Instanzen von vier Ziffern als Suffix vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="e81dd-172">For example, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span></span>

- <span data-ttu-id="e81dd-173">1234-5678-9321 4500 9870 6321 48925566</span><span class="sxs-lookup"><span data-stu-id="e81dd-173">1234-5678-9321 4500 9870 6321 48925566</span></span>
- <span data-ttu-id="e81dd-174">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="e81dd-174">1234-5678-9321</span></span>

<span data-ttu-id="e81dd-175">Sie können diese XML-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-175">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
<span data-ttu-id="e81dd-176">Um z. B. Vorkommen auszuschließen, wenn auf sie **/xuidsuffix** folgt, wie in dieser Liste:</span><span class="sxs-lookup"><span data-stu-id="e81dd-176">For example, to exclude occurrences if they are followed by **/xuidsuffix**, like one in this list:</span></span>

- <span data-ttu-id="e81dd-177">1234-5678-9321 /xuid</span><span class="sxs-lookup"><span data-stu-id="e81dd-177">1234-5678-9321 /xuid</span></span>
- <span data-ttu-id="e81dd-178">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="e81dd-178">1234-5678-9321</span></span>

<span data-ttu-id="e81dd-179">Sie können diese XML-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-179">you can use this xml</span></span>

<span data-ttu-id="e81dd-180">''xml <Filters id="cc_number_filters_exc"></span><span class="sxs-lookup"><span data-stu-id="e81dd-180">\`\`xml <Filters id="cc_number_filters_exc"></span></span>
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <span data-ttu-id="e81dd-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span><span class="sxs-lookup"><span data-stu-id="e81dd-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span></span><Term><span data-ttu-id="e81dd-182">/xuid</span><span class="sxs-lookup"><span data-stu-id="e81dd-182">/xuid</span></span></Term>
    <span data-ttu-id="e81dd-183"></Group> </Keyword></span><span class="sxs-lookup"><span data-stu-id="e81dd-183"></Group> </Keyword></span></span>
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

## <a name="using-filters-in-rule-packages"></a><span data-ttu-id="e81dd-184">Verwenden von Filtern in Regelpaketen</span><span class="sxs-lookup"><span data-stu-id="e81dd-184">Using filters in rule packages</span></span>

<span data-ttu-id="e81dd-185">Filter können für die gesamte SIT oder ein Muster definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-185">Filters can be defined on the entire SIT or on a pattern.</span></span> <span data-ttu-id="e81dd-186">Hier sind einige Codeausschnittbeispiele.</span><span class="sxs-lookup"><span data-stu-id="e81dd-186">Here are some code snippets examples.</span></span> 

### <a name="at-sensitive-information-type-level"></a><span data-ttu-id="e81dd-187">Auf Der Ebene der vertraulichen Informationstypen</span><span class="sxs-lookup"><span data-stu-id="e81dd-187">At sensitive information type level</span></span>

<span data-ttu-id="e81dd-188">Filter bei Entity – deckt alle untergeordneten Muster ab</span><span class="sxs-lookup"><span data-stu-id="e81dd-188">Filters at Entity - will cover all child patterns</span></span>

<span data-ttu-id="e81dd-189">Die Filter werden auf **alle** Instanzen angewendet, die von einem der Muster in diesem Entitäts-/vertraulichen Typ klassifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-189">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a><span data-ttu-id="e81dd-190">Auf der Ebene der vertraulichen Informationstypen im individuellen Muster</span><span class="sxs-lookup"><span data-stu-id="e81dd-190">At the individual pattern of the sensitive information type level</span></span>

<span data-ttu-id="e81dd-191">Filtert nur auf Musterebene.</span><span class="sxs-lookup"><span data-stu-id="e81dd-191">Filters only at the pattern level.</span></span>

<span data-ttu-id="e81dd-192">Der Filter wird auf die Instanzen angewendet, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e81dd-192">The filter will be applied on the instances matched by the pattern.</span></span>

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a><span data-ttu-id="e81dd-193">Auf Der Ebene der vertraulichen Informationstypen und einem zusätzlichen Filter nach einigen Mustern dieser Entität</span><span class="sxs-lookup"><span data-stu-id="e81dd-193">At sensitive information type level and an additional filter on some of the patterns of that entity</span></span>

<span data-ttu-id="e81dd-194">Filter bei Entity + Pattern</span><span class="sxs-lookup"><span data-stu-id="e81dd-194">Filters at Entity + pattern</span></span>

<span data-ttu-id="e81dd-195">Die Filter werden auf **alle** Instanzen angewendet, die von einem der Muster in diesem Entitäts-/vertraulichen Typ klassifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="e81dd-195">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type.</span></span> <span data-ttu-id="e81dd-196">Der Filter auf Musterebene filtert die Instanzen, die mit diesem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e81dd-196">The pattern level filter will filter the instances matched by that pattern.</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a><span data-ttu-id="e81dd-197">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e81dd-197">More information</span></span>

- [<span data-ttu-id="e81dd-198">Informationen zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="e81dd-198">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="e81dd-199">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="e81dd-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="e81dd-200">Wonach die DLP-Funktionen suchen</span><span class="sxs-lookup"><span data-stu-id="e81dd-200">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
