---
title: Erstellen eines benutzerdefinierten Typs für vertrauliche Informationen in Security & Compliance Center PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie einen benutzerdefinierten Typ für vertrauliche Informationen für DLP im Security & Compliance Center erstellen und importieren.
ms.openlocfilehash: e0b2cbdad49c19e34237095b7825b4a3496fd570
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086622"
---
# <a name="create-a-custom-sensitive-information-type-in-security--compliance-center-powershell"></a><span data-ttu-id="bc0f6-103">Erstellen eines benutzerdefinierten Typs für vertrauliche Informationen in Security & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc0f6-103">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="bc0f6-104">Data loss prevention (DLP) in Microsoft 365 includes many built-in [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md) that are ready for you to use in your DLP policies.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-104">Data loss prevention (DLP) in Microsoft 365 includes many built-in [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md) that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="bc0f6-105">These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-105">These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span></span>
  
<span data-ttu-id="bc0f6-106">But what if you need to identify and protect a different type of sensitive information (for example, an employee ID that uses a format specific to your organization)?</span><span class="sxs-lookup"><span data-stu-id="bc0f6-106">But what if you need to identify and protect a different type of sensitive information (for example, an employee ID that uses a format specific to your organization)?</span></span> <span data-ttu-id="bc0f6-107">To do this, you can create a custom sensitive information type that is defined in an XML file called a *rule package*.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-107">To do this, you can create a custom sensitive information type that is defined in an XML file called a *rule package*.</span></span>
  
<span data-ttu-id="bc0f6-108">This topic shows you how to create an XML file that defines your own custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-108">This topic shows you how to create an XML file that defines your own custom sensitive information type.</span></span> <span data-ttu-id="bc0f6-109">You need to know how to create a regular expression.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-109">You need to know how to create a regular expression.</span></span> <span data-ttu-id="bc0f6-110">As an example, this topic creates a custom sensitive information type that identifies an employee ID.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-110">As an example, this topic creates a custom sensitive information type that identifies an employee ID.</span></span> <span data-ttu-id="bc0f6-111">You can use this example XML as a starting point for your own XML file.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-111">You can use this example XML as a starting point for your own XML file.</span></span>
  
<span data-ttu-id="bc0f6-112">After you've created a well-formed XML file, you can upload it to Microsoft 365 by using Microsoft 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-112">After you've created a well-formed XML file, you can upload it to Microsoft 365 by using Microsoft 365 PowerShell.</span></span> <span data-ttu-id="bc0f6-113">Then you're ready to use your custom sensitive information type in your DLP policies and test that it's detecting the sensitive information as you intended.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-113">Then you're ready to use your custom sensitive information type in your DLP policies and test that it's detecting the sensitive information as you intended.</span></span>

> [!NOTE]
> <span data-ttu-id="bc0f6-114">You can also create less complex custom sensitive information types in the Security & Compliance Center UI.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-114">You can also create less complex custom sensitive information types in the Security & Compliance Center UI.</span></span> <span data-ttu-id="bc0f6-115">For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-115">For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="important-disclaimer"></a><span data-ttu-id="bc0f6-116">Wichtiger Haftungsausschluss</span><span class="sxs-lookup"><span data-stu-id="bc0f6-116">Important disclaimer</span></span>
<!-- this is worded much better than the previous one is -->
<span data-ttu-id="bc0f6-117">Due to the variances in customer environments and content match requirements, Microsoft Support cannot assist in providing custom content-matching definitions; e.g., defining custom classifications or regular expression (also known as RegEx) patterns.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-117">Due to the variances in customer environments and content match requirements, Microsoft Support cannot assist in providing custom content-matching definitions; e.g., defining custom classifications or regular expression (also known as RegEx) patterns.</span></span> <span data-ttu-id="bc0f6-118">For custom content-matching development, testing, and debugging, Microsoft 365 customers will need to rely upon internal IT resources, or use an external consulting resource such as Microsoft Consulting Services (MCS).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-118">For custom content-matching development, testing, and debugging, Microsoft 365 customers will need to rely upon internal IT resources, or use an external consulting resource such as Microsoft Consulting Services (MCS).</span></span> <span data-ttu-id="bc0f6-119">Support engineers can provide limited support for the feature, but cannot provide assurances that any custom content-matching development will fulfill the customer's requirements or obligations.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-119">Support engineers can provide limited support for the feature, but cannot provide assurances that any custom content-matching development will fulfill the customer's requirements or obligations.</span></span>  <span data-ttu-id="bc0f6-120">As an example of the type of support that can be provided, sample regular expression patterns may be provided for testing purposes.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-120">As an example of the type of support that can be provided, sample regular expression patterns may be provided for testing purposes.</span></span> <span data-ttu-id="bc0f6-121">Or, support can assist with troubleshooting an existing RegEx pattern which is not triggering as expected with a single specific content example.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-121">Or, support can assist with troubleshooting an existing RegEx pattern which is not triggering as expected with a single specific content example.</span></span>

<span data-ttu-id="bc0f6-122">Lesen Sie auch [Mögliche Überprüfungsprobleme, die zu beachten sind](#potential-validation-issues-to-be-aware-of) in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-122">See [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of) in this topic.</span></span>

<span data-ttu-id="bc0f6-123">Weitere Informationen über die Boost.RegEx-Engine (ehemals RegEx++), die für die Verarbeitung des Textes verwendet wird, finden Sie unter [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-123">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

## <a name="sample-xml-of-a-rule-package"></a><span data-ttu-id="bc0f6-124">Beispiel-XML für ein Regelpaket</span><span class="sxs-lookup"><span data-stu-id="bc0f6-124">Sample XML of a rule package</span></span>

<span data-ttu-id="bc0f6-125">Here's the sample XML of the rule package that we'll create in this topic.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-125">Here's the sample XML of the rule package that we'll create in this topic.</span></span> <span data-ttu-id="bc0f6-126">Elements and attributes are explained in the sections below.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-126">Elements and attributes are explained in the sections below.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
<RulePack id="DAD86A92-AB18-43BB-AB35-96F7C594ADAA">
    <Version build="0" major="1" minor="0" revision="0"/>
    <Publisher id="619DD8C3-7B80-4998-A312-4DF0402BAC04"/>
    <Details defaultLangCode="en-us">
        <LocalizedDetails langcode="en-us">
            <PublisherName>Contoso</PublisherName>
            <Name>Employee ID Custom Rule Pack</Name>
            <Description>
            This rule package contains the custom Employee ID entity.
            </Description>
        </LocalizedDetails>
    </Details>
</RulePack>
<Rules>
<!-- Employee ID -->
    <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="70">
        <Pattern confidenceLevel="60">
            <IdMatch idRef="Regex_employee_id"/>
        </Pattern>
        <Pattern confidenceLevel="70">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
        </Pattern>
        <Pattern confidenceLevel="80">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
            <Any minMatches="1">
                <Match idRef="Keyword_badge" minCount="2"/>
                <Match idRef="Keyword_employee"/>
            </Any>
            <Any minMatches="0" maxMatches="0">
                <Match idRef="Keyword_false_positives_local"/>
                <Match idRef="Keyword_false_positives_intl"/>
            </Any>
        </Pattern>
    </Entity>
    <Regex id="Regex_employee_id">(\s)(\d{9})(\s)</Regex>
    <Keyword id="Keyword_employee">
        <Group matchStyle="word">
            <Term>Identification</Term>
            <Term>Contoso Employee</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_badge">
        <Group matchStyle="string">
            <Term>card</Term>
            <Term>badge</Term>
            <Term caseSensitive="true">ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_local">
        <Group matchStyle="word">
            <Term>credit card</Term>
            <Term>national ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_intl">
        <Group matchStyle="word">
            <Term>identity card</Term>
            <Term>national ID</Term>
            <Term>EU debit card</Term>
        </Group>
    </Keyword>
    <LocalizedStrings>
        <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB378">
            <Name default="true" langcode="en-us">Employee ID</Name>
            <Description default="true" langcode="en-us">
            A custom classification for detecting Employee IDs.
            </Description>
            <Description default="false" langcode="de-de">
            Description for German locale.
            </Description>
        </Resource>
    </LocalizedStrings>
</Rules>
</RulePackage>
```

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a><span data-ttu-id="bc0f6-127">What are your key requirements?</span><span class="sxs-lookup"><span data-stu-id="bc0f6-127">What are your key requirements?</span></span> <span data-ttu-id="bc0f6-128">[Rule, Entity, Pattern elements]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-128">[Rule, Entity, Pattern elements]</span></span>

<span data-ttu-id="bc0f6-129">Bevor Sie beginnen, ist es hilfreich, die grundlegende Struktur des XML-Schemas für eine Regel zu kennen, und wie Sie diese Struktur verwenden können, um den benutzerdefinierten vertraulichen Informationstyp zu definieren, damit die richtigen Inhalte erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-129">Before you get started, it's helpful to understand the basic structure of the XML schema for a rule, and how you can use this structure to define your custom sensitive information type so that it will identify the right content.</span></span>
  
<span data-ttu-id="bc0f6-130">A rule defines one or more entities (sensitive information types), and each entity defines one or more patterns.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-130">A rule defines one or more entities (sensitive information types), and each entity defines one or more patterns.</span></span> <span data-ttu-id="bc0f6-131">A pattern is what DLP looks for when it evaluates content such as email and documents.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-131">A pattern is what DLP looks for when it evaluates content such as email and documents.</span></span>
  <!-- ok then this is going to be really confusing since the terminology changes.... -->
<span data-ttu-id="bc0f6-132">(A quick note on terminology - if you're familiar with DLP policies, you know that a policy contains one or more rules comprised of conditions and actions.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-132">(A quick note on terminology - if you're familiar with DLP policies, you know that a policy contains one or more rules comprised of conditions and actions.</span></span> <span data-ttu-id="bc0f6-133">However, in this topic, the XML markup uses rule to mean the patterns that define an entity, also known as a sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-133">However, in this topic, the XML markup uses rule to mean the patterns that define an entity, also known as a sensitive information type.</span></span> <span data-ttu-id="bc0f6-134">So in this topic, when you see rule, think entity or sensitive information type, not conditions and actions.)</span><span class="sxs-lookup"><span data-stu-id="bc0f6-134">So in this topic, when you see rule, think entity or sensitive information type, not conditions and actions.)</span></span>
  
### <a name="simplest-scenario-entity-with-one-pattern"></a><span data-ttu-id="bc0f6-135">Einfachstes Szenario: Entität mit einem Muster</span><span class="sxs-lookup"><span data-stu-id="bc0f6-135">Simplest scenario: entity with one pattern</span></span>

<span data-ttu-id="bc0f6-136">Here's the simplest scenario.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-136">Here's the simplest scenario.</span></span> <span data-ttu-id="bc0f6-137">You want your DLP policy to identify content that contains your organization's employee ID, which is formatted as a nine-digit number.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-137">You want your DLP policy to identify content that contains your organization's employee ID, which is formatted as a nine-digit number.</span></span> <span data-ttu-id="bc0f6-138">So the pattern refers to a regular expression contained in the rule that identifies nine-digit numbers.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-138">So the pattern refers to a regular expression contained in the rule that identifies nine-digit numbers.</span></span> <span data-ttu-id="bc0f6-139">Any content containing a nine-digit number satisfies the pattern.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-139">Any content containing a nine-digit number satisfies the pattern.</span></span>
  
![Diagramm einer Entität mit einem Muster](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
<span data-ttu-id="bc0f6-141">Obwohl dieses Muster einfach ist, führt möglicherweise jedoch zu einer Menge falsch positiver Ergebnisse, indem es Inhalte mit einer neunstelligen Zahl erkennt, die nicht unbedingt eine Mitarbeiter-ID ist.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-141">However, while simple, this pattern may identify many false positives by matching content that contains any nine-digit number that is not necessarily an employee ID.</span></span>
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a><span data-ttu-id="bc0f6-142">Häufigeres Szenario: Entität mit mehreren Mustern</span><span class="sxs-lookup"><span data-stu-id="bc0f6-142">More common scenario: entity with multiple patterns</span></span>

<span data-ttu-id="bc0f6-143">Aus diesem Grund wird eine Entität in der Regel mit mehr als einem Muster definiert, wobei die Muster unterstützende Hinweise (z. B. ein Schlüsselwort oder Datum) zusätzlich zur Entität (z. B. die neunstellige Zahl) identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-143">For this reason, it's more common to define an entity by using more than one pattern, where the patterns identify supporting evidence (such as a keyword or date) in addition to the entity (such as a nine-digit number).</span></span>
  
<span data-ttu-id="bc0f6-144">Um zum Beispiel die Wahrscheinlichkeit zu erhöhen, Inhalt zu erkennen, der eine Mitarbeiter-ID enthält, können Sie ein anderes Muster definieren, das z. B. auch ein Einstellungsdatum identifiziert. Sie können noch ein weiteres Muster definieren, das sowohl ein Einstellungsdatum als auch ein Stichwort (z. B. „Mitarbeiter-ID“) zusätzlich zur neunstelligen Zahl identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-144">For example, to increase the likelihood of identifying content that contains an employee ID, you can define another pattern that also identifies a hire date, and define yet another pattern that identifies both a hire date and a keyword (such as "employee ID"), in addition to the nine-digit number.</span></span>
  
![Diagramm einer Entität mit mehreren Mustern](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
<span data-ttu-id="bc0f6-146">Beachten Sie einige wichtige Aspekte dieser Struktur:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-146">Note a couple of important aspects of this structure:</span></span>
  
- <span data-ttu-id="bc0f6-147">Patterns that require more evidence have a higher confidence level.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-147">Patterns that require more evidence have a higher confidence level.</span></span> <span data-ttu-id="bc0f6-148">This is useful because when you later use this sensitive information type in a DLP policy, you can use more restrictive actions (such as block content) with only the higher-confidence matches, and you can use less restrictive actions (such as send notification) with the lower-confidence matches.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-148">This is useful because when you later use this sensitive information type in a DLP policy, you can use more restrictive actions (such as block content) with only the higher-confidence matches, and you can use less restrictive actions (such as send notification) with the lower-confidence matches.</span></span>

- <span data-ttu-id="bc0f6-149">The supporting IdMatch and Match elements reference regexes and keywords that are actually children of the Rule element, not the Pattern.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-149">The supporting IdMatch and Match elements reference regexes and keywords that are actually children of the Rule element, not the Pattern.</span></span> <span data-ttu-id="bc0f6-150">These supporting elements are referenced by the Pattern but included in the Rule.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-150">These supporting elements are referenced by the Pattern but included in the Rule.</span></span> <span data-ttu-id="bc0f6-151">This means that a single definition of a supporting element, like a regular expression or a keyword list, can be referenced by multiple entities and patterns.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-151">This means that a single definition of a supporting element, like a regular expression or a keyword list, can be referenced by multiple entities and patterns.</span></span>

## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a><span data-ttu-id="bc0f6-152">What entity do you need to identify?</span><span class="sxs-lookup"><span data-stu-id="bc0f6-152">What entity do you need to identify?</span></span> <span data-ttu-id="bc0f6-153">[Entity element, id attribute]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-153">[Entity element, id attribute]</span></span>

<span data-ttu-id="bc0f6-154">An entity is a sensitive information type, such as a credit card number, that has a well-defined pattern.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-154">An entity is a sensitive information type, such as a credit card number, that has a well-defined pattern.</span></span> <span data-ttu-id="bc0f6-155">Each entity has a unique GUID as its ID.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-155">Each entity has a unique GUID as its ID.</span></span>
  
### <a name="name-the-entity-and-generate-its-guid"></a><span data-ttu-id="bc0f6-156">Benennen der Entität und Generieren der GUID</span><span class="sxs-lookup"><span data-stu-id="bc0f6-156">Name the entity and generate its GUID</span></span>
<!-- why isn't the following in procedure format? -->
<span data-ttu-id="bc0f6-157">Add the Rules and Entity elements.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-157">Add the Rules and Entity elements.</span></span> <span data-ttu-id="bc0f6-158">Then add a comment that contains the name of your custom entity - in this example, Employee ID.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-158">Then add a comment that contains the name of your custom entity - in this example, Employee ID.</span></span> <span data-ttu-id="bc0f6-159">Later, you'll add the entity name to the localized strings section, and that name is what appears in the UI when you create a DLP policy.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-159">Later, you'll add the entity name to the localized strings section, and that name is what appears in the UI when you create a DLP policy.</span></span>
  
<span data-ttu-id="bc0f6-160">Als Nächstes generieren Sie eine GUID für die Entität.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-160">Next, generate a GUID for your entity.</span></span> <span data-ttu-id="bc0f6-161">GUIDs können auf verschiedene Arten generiert werden, besonders einfach ist es aber in PowerShell. Dort müssen Sie nur **[guid]::NewGuid()** eingeben.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-161">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> <span data-ttu-id="bc0f6-162">Später fügen Sie auch die Entitäts-GUID zum Abschnitt mit den lokalisierten Zeichenfolgen hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-162">Later, you'll also add the entity GUID to the localized strings section.</span></span>
  
![XML-Markup mit den Elementen "Regeln" und "Entität"](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a><span data-ttu-id="bc0f6-164">What pattern do you want to match?</span><span class="sxs-lookup"><span data-stu-id="bc0f6-164">What pattern do you want to match?</span></span> <span data-ttu-id="bc0f6-165">[Pattern element, IdMatch element, Regex element]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-165">[Pattern element, IdMatch element, Regex element]</span></span>

<span data-ttu-id="bc0f6-166">The pattern contains the list of what the sensitive information type is looking for.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-166">The pattern contains the list of what the sensitive information type is looking for.</span></span> <span data-ttu-id="bc0f6-167">This can include regexes, keywords, and built-in functions (which perform tasks like running regexes to find dates or addresses).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-167">This can include regexes, keywords, and built-in functions (which perform tasks like running regexes to find dates or addresses).</span></span> <span data-ttu-id="bc0f6-168">Sensitive information types can have multiple patterns with unique confidences.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-168">Sensitive information types can have multiple patterns with unique confidences.</span></span>
  
<span data-ttu-id="bc0f6-169">What all of the below patterns have in common is that they all reference the same regular expression, which looks for a nine-digit number (\d{9}) surrounded by white space (\s) …</span><span class="sxs-lookup"><span data-stu-id="bc0f6-169">What all of the below patterns have in common is that they all reference the same regular expression, which looks for a nine-digit number (\d{9}) surrounded by white space (\s) …</span></span> <span data-ttu-id="bc0f6-170">(\s).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-170">(\s).</span></span> <span data-ttu-id="bc0f6-171">This regular expression is referenced by the IdMatch element and is the common requirement for all patterns that look for the Employee ID entity.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-171">This regular expression is referenced by the IdMatch element and is the common requirement for all patterns that look for the Employee ID entity.</span></span> <span data-ttu-id="bc0f6-172">IdMatch is the identifier that the pattern is to trying to match, such as Employee ID or credit card number or social security number.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-172">IdMatch is the identifier that the pattern is to trying to match, such as Employee ID or credit card number or social security number.</span></span> <span data-ttu-id="bc0f6-173">A Pattern element must have exactly one IdMatch element.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-173">A Pattern element must have exactly one IdMatch element.</span></span>
  
![XML-Markup mit mehreren Pattern-Elementen, die auf ein einzelnes Regex-Element verweisen](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
<span data-ttu-id="bc0f6-175">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policy.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-175">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policy.</span></span> <span data-ttu-id="bc0f6-176">When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown here.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-176">When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown here.</span></span> <span data-ttu-id="bc0f6-177">Confidence level (also called match accuracy) is explained later in this topic.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-177">Confidence level (also called match accuracy) is explained later in this topic.</span></span>
  
![Instanzenanzahl und Optionen für die Übereinstimmungsgenauigkeit](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="bc0f6-179">When you create your regular expression, keep in mind that there are potential issues to be aware of.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-179">When you create your regular expression, keep in mind that there are potential issues to be aware of.</span></span> <span data-ttu-id="bc0f6-180">For example, if you write and upload a regex that identifies too much content, this can impact performance.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-180">For example, if you write and upload a regex that identifies too much content, this can impact performance.</span></span> <span data-ttu-id="bc0f6-181">To learn more about these potential issues, see the later section [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-181">To learn more about these potential issues, see the later section [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of).</span></span>
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a><span data-ttu-id="bc0f6-182">Do you want to require additional evidence?</span><span class="sxs-lookup"><span data-stu-id="bc0f6-182">Do you want to require additional evidence?</span></span> <span data-ttu-id="bc0f6-183">[Match element, minCount attribute]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-183">[Match element, minCount attribute]</span></span>

<span data-ttu-id="bc0f6-184">Zusätzlich zu "IdMatch" kann in einem Muster das Element "Match" verwendet werden, um zusätzliche unterstützende Nachweise anzufordern, z. B. ein Schlüsselwort, einen regulären Ausdruck, ein Datum oder eine Adresse.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-184">In addition to the IdMatch, a pattern can use the Match element to require additional supporting evidence, such as a keyword, regex, date, or address.</span></span>
  
<span data-ttu-id="bc0f6-185">A Pattern can include multiple Match elements; they can be included directly in the Pattern element or combined by using the Any element.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-185">A Pattern can include multiple Match elements; they can be included directly in the Pattern element or combined by using the Any element.</span></span> <span data-ttu-id="bc0f6-186">Match elements are joined by an implicit AND operator; all Match elements must be satisfied for the pattern to be matched.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-186">Match elements are joined by an implicit AND operator; all Match elements must be satisfied for the pattern to be matched.</span></span> <span data-ttu-id="bc0f6-187">You can use the Any element to introduce AND or OR operators (more on that in a later section).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-187">You can use the Any element to introduce AND or OR operators (more on that in a later section).</span></span>
  
<span data-ttu-id="bc0f6-188">You can use the optional minCount attribute to specify how many instances of a match need to be found for each of the Match elements.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-188">You can use the optional minCount attribute to specify how many instances of a match need to be found for each of the Match elements.</span></span> <span data-ttu-id="bc0f6-189">For example, you can specify that a pattern is satisfied only when at least two keywords from a keyword list are found.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-189">For example, you can specify that a pattern is satisfied only when at least two keywords from a keyword list are found.</span></span>
  
![XML-Markup mit Match-Element und minOccurs-Attribut](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a><span data-ttu-id="bc0f6-191">Stichwörter [Elemente „Keyword“, „Group“ und „Term“, matchStyle- und caseSensitive-Attribute]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-191">Keywords [Keyword, Group, and Term elements, matchStyle and caseSensitive attributes]</span></span>

<span data-ttu-id="bc0f6-192">When you identify sensitive information, like an employee ID, you often want to require keywords as corroborative evidence.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-192">When you identify sensitive information, like an employee ID, you often want to require keywords as corroborative evidence.</span></span> <span data-ttu-id="bc0f6-193">For example, in addition to matching a nine-digit number, you may want to look for words like "card", "badge", or "ID".</span><span class="sxs-lookup"><span data-stu-id="bc0f6-193">For example, in addition to matching a nine-digit number, you may want to look for words like "card", "badge", or "ID".</span></span> <span data-ttu-id="bc0f6-194">To do this, you use the Keyword element.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-194">To do this, you use the Keyword element.</span></span> <span data-ttu-id="bc0f6-195">The Keyword element has an id attribute that can be referenced by multiple Match elements in multiple patterns or entities.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-195">The Keyword element has an id attribute that can be referenced by multiple Match elements in multiple patterns or entities.</span></span>
  
<span data-ttu-id="bc0f6-196">Keywords are included as a list of Term elements in a Group element.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-196">Keywords are included as a list of Term elements in a Group element.</span></span> <span data-ttu-id="bc0f6-197">The Group element has a matchStyle attribute with two possible values:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-197">The Group element has a matchStyle attribute with two possible values:</span></span>
  
- <span data-ttu-id="bc0f6-198">**matchStyle="word"** Word match identifies whole words surrounded by white space or other delimiters.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-198">**matchStyle="word"** Word match identifies whole words surrounded by white space or other delimiters.</span></span> <span data-ttu-id="bc0f6-199">You should always use word unless you need to match parts of words or match words in Asian languages.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-199">You should always use word unless you need to match parts of words or match words in Asian languages.</span></span> 
    
- <span data-ttu-id="bc0f6-200">**matchStyle="string"** String match identifies strings no matter what they're surrounded by.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-200">**matchStyle="string"** String match identifies strings no matter what they're surrounded by.</span></span> <span data-ttu-id="bc0f6-201">For example, "id" will match "bid" and "idea".</span><span class="sxs-lookup"><span data-stu-id="bc0f6-201">For example, "id" will match "bid" and "idea".</span></span> <span data-ttu-id="bc0f6-202">Use string only when you need to match Asian words or if your keyword may be included as part of other strings.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-202">Use string only when you need to match Asian words or if your keyword may be included as part of other strings.</span></span> 
    
<span data-ttu-id="bc0f6-203">Sie können auch das caseSensitive-Attribut des Term-Elements verwenden, um festzulegen, dass der Inhalt genau mit dem Stichwort übereinstimmen muss, einschließlich Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-203">Finally, you can use the caseSensitive attribute of the Term element to specify that the content must match the keyword exactly, including lower- and upper-case letters.</span></span>
  
![XML-Markup mit Match-Elementen, die auf Stichwörter verweisen](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a><span data-ttu-id="bc0f6-205">Reguläre Ausdrücke [Element „Regex“]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-205">Regular expressions [Regex element]</span></span>

<span data-ttu-id="bc0f6-206">In this example, the employee ID entity already uses the IdMatch element to reference a regex for the pattern - a nine-digit number surrounded by whitespace.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-206">In this example, the employee ID entity already uses the IdMatch element to reference a regex for the pattern - a nine-digit number surrounded by whitespace.</span></span> <span data-ttu-id="bc0f6-207">In addition, a pattern can use a Match element to reference an additional Regex element to identify corroborative evidence, such as a five- or nine-digit number in the format of a US zip code.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-207">In addition, a pattern can use a Match element to reference an additional Regex element to identify corroborative evidence, such as a five- or nine-digit number in the format of a US zip code.</span></span>
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a><span data-ttu-id="bc0f6-208">Zusätzliche Muster wie Datumsangaben oder Adressen [integrierte Funktionen]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-208">Additional patterns such as dates or addresses [built-in functions]</span></span>

<span data-ttu-id="bc0f6-209">In addition to the built-in sensitive information types, DLP also includes built-in functions that can identify corroborative evidence such as a US date, EU date, expiration date, or US address.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-209">In addition to the built-in sensitive information types, DLP also includes built-in functions that can identify corroborative evidence such as a US date, EU date, expiration date, or US address.</span></span> <span data-ttu-id="bc0f6-210">DLP does not support uploading your own custom functions, but when you create a custom sensitive information type, your entity can reference the built-in functions.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-210">DLP does not support uploading your own custom functions, but when you create a custom sensitive information type, your entity can reference the built-in functions.</span></span>
  
<span data-ttu-id="bc0f6-211">Beispielsweise steht auf einem Mitarbeiterausweis außer der Mitarbeiter-ID auch ein Einstellungsdatum, sodass diese benutzerdefinierte Entität die integrierte Funktion `Func_us_date` verwenden kann, um ein Datum im US-typischen Format zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-211">For example, an employee ID badge has a hire date on it, so this custom entity can use the built-in function  `Func_us_date` to identify a date in the format commonly used in the US.</span></span> 
  
<span data-ttu-id="bc0f6-212">Weitere Informationen finden Sie unter [Wonach die DLP-Funktionen suchen](what-the-dlp-functions-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-212">For more information, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
  
![XML-Markup mit Match-Element, das auf eine integrierte Funktion verweist](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a><span data-ttu-id="bc0f6-214">Verschiedene Kombinationen von Nachweisen [Element „Any“, minMatches- und maxMatches-Attribute]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-214">Different combinations of evidence [Any element, minMatches and maxMatches attributes]</span></span>

<span data-ttu-id="bc0f6-215">In a Pattern element, all IdMatch and Match elements are joined by an implicit AND operator - all of the matches must be satisfied before the pattern can be satisfied.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-215">In a Pattern element, all IdMatch and Match elements are joined by an implicit AND operator - all of the matches must be satisfied before the pattern can be satisfied.</span></span> <span data-ttu-id="bc0f6-216">However, you can create more flexible matching logic by using the Any element to group Match elements.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-216">However, you can create more flexible matching logic by using the Any element to group Match elements.</span></span> <span data-ttu-id="bc0f6-217">For example, you can use the Any element to match all, none, or an exact subset of its children Match elements.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-217">For example, you can use the Any element to match all, none, or an exact subset of its children Match elements.</span></span>
  
<span data-ttu-id="bc0f6-218">The Any element has optional minMatches and maxMatches attributes that you can use to define how many of the children Match elements must be satisfied before the pattern is matched.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-218">The Any element has optional minMatches and maxMatches attributes that you can use to define how many of the children Match elements must be satisfied before the pattern is matched.</span></span> <span data-ttu-id="bc0f6-219">Note that these attributes define the number of Match elements that must be satisfied, not the number of instances of evidence found for the matches.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-219">Note that these attributes define the number of Match elements that must be satisfied, not the number of instances of evidence found for the matches.</span></span> <span data-ttu-id="bc0f6-220">To define a minimum number of instances for a specific match, such as two keywords from a list, use the minCount attribute for a Match element (see above).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-220">To define a minimum number of instances for a specific match, such as two keywords from a list, use the minCount attribute for a Match element (see above).</span></span>
  
### <a name="match-at-least-one-child-match-element"></a><span data-ttu-id="bc0f6-221">Übereinstimmung mit mindestens einem untergeordneten "Match"-Element</span><span class="sxs-lookup"><span data-stu-id="bc0f6-221">Match at least one child Match element</span></span>

<span data-ttu-id="bc0f6-222">If you want to require that only a minimum number of Match elements must be met, you can use the minMatches attribute.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-222">If you want to require that only a minimum number of Match elements must be met, you can use the minMatches attribute.</span></span> <span data-ttu-id="bc0f6-223">In effect, these Match elements are joined by an implicit OR operator.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-223">In effect, these Match elements are joined by an implicit OR operator.</span></span> <span data-ttu-id="bc0f6-224">This Any element is satisfied if a US-formatted date or a keyword from either list is found.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-224">This Any element is satisfied if a US-formatted date or a keyword from either list is found.</span></span>

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
    
### <a name="match-an-exact-subset-of-any-children-match-elements"></a><span data-ttu-id="bc0f6-225">Übereinstimmung mit einer genauen Untermenge beliebiger untergeordneter Match-Elemente</span><span class="sxs-lookup"><span data-stu-id="bc0f6-225">Match an exact subset of any children Match elements</span></span>

<span data-ttu-id="bc0f6-226">If you want to require that an exact number of Match elements must be met, you can set minMatches and maxMatches to the same value.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-226">If you want to require that an exact number of Match elements must be met, you can set minMatches and maxMatches to the same value.</span></span> <span data-ttu-id="bc0f6-227">This Any element is satisfied only if exactly one date or keyword is found - any more than that, and the pattern won't be matched.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-227">This Any element is satisfied only if exactly one date or keyword is found - any more than that, and the pattern won't be matched.</span></span>

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
  
### <a name="match-none-of-children-match-elements"></a><span data-ttu-id="bc0f6-228">Übereinstimmung für keine untergeordneten Match-Elemente</span><span class="sxs-lookup"><span data-stu-id="bc0f6-228">Match none of children Match elements</span></span>

<span data-ttu-id="bc0f6-229">If you want to require the absence of specific evidence for a pattern to be satisfied, you can set both minMatches and maxMatches to 0.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-229">If you want to require the absence of specific evidence for a pattern to be satisfied, you can set both minMatches and maxMatches to 0.</span></span> <span data-ttu-id="bc0f6-230">This can be useful if you have a keyword list or other evidence that are likely to indicate a false positive.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-230">This can be useful if you have a keyword list or other evidence that are likely to indicate a false positive.</span></span>
  
<span data-ttu-id="bc0f6-231">For example, the employee ID entity looks for the keyword "card" because it might refer to an "ID card".</span><span class="sxs-lookup"><span data-stu-id="bc0f6-231">For example, the employee ID entity looks for the keyword "card" because it might refer to an "ID card".</span></span> <span data-ttu-id="bc0f6-232">However, if card appears only in the phrase "credit card", "card" in this content is unlikely to mean "ID card".</span><span class="sxs-lookup"><span data-stu-id="bc0f6-232">However, if card appears only in the phrase "credit card", "card" in this content is unlikely to mean "ID card".</span></span> <span data-ttu-id="bc0f6-233">So you can add "credit card" as a keyword to a list of terms that you want to exclude from satisfying the pattern.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-233">So you can add "credit card" as a keyword to a list of terms that you want to exclude from satisfying the pattern.</span></span>
  
```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a><span data-ttu-id="bc0f6-234">Übereinstimmung mit einer Reihe eindeutiger Begriffe</span><span class="sxs-lookup"><span data-stu-id="bc0f6-234">Match a number of unique terms</span></span>

<span data-ttu-id="bc0f6-235">Wenn Entsprechungen für eine Reihe eindeutiger Begriffe gefunden werden sollen, verwenden Sie den *uniqueResults*-Parameter und legen Sie ihn wie im folgenden Beispiel auf *true* fest:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-235">If you want to match a number of unique terms, use the *uniqueResults* parameter, set to *true*, as shown in the following example:</span></span>

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

<span data-ttu-id="bc0f6-236">In diesem Beispiel ist ein Muster für die Gehaltsrevision mit mindestens drei eindeutigen Übereinstimmungen definiert.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-236">In this example, a pattern is defined for salary revision using at least three unique matches.</span></span> 
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a><span data-ttu-id="bc0f6-237">How close to the entity must the other evidence be?</span><span class="sxs-lookup"><span data-stu-id="bc0f6-237">How close to the entity must the other evidence be?</span></span> <span data-ttu-id="bc0f6-238">[patternsProximity attribute]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-238">[patternsProximity attribute]</span></span>

<span data-ttu-id="bc0f6-239">Your sensitive information type is looking for a pattern that represents an employee ID, and as part of that pattern it's also looking for corroborative evidence like a keyword such as "ID".</span><span class="sxs-lookup"><span data-stu-id="bc0f6-239">Your sensitive information type is looking for a pattern that represents an employee ID, and as part of that pattern it's also looking for corroborative evidence like a keyword such as "ID".</span></span> <span data-ttu-id="bc0f6-240">It makes sense that the closer together this evidence is, the more likely the pattern is to be an actual employee ID.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-240">It makes sense that the closer together this evidence is, the more likely the pattern is to be an actual employee ID.</span></span> <span data-ttu-id="bc0f6-241">You can determine how close other evidence in the pattern must be to the entity by using the required patternsProximity attribute of the Entity element.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-241">You can determine how close other evidence in the pattern must be to the entity by using the required patternsProximity attribute of the Entity element.</span></span>
  
![XML-Markup mit patternsProximity-Attribut](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
<span data-ttu-id="bc0f6-243">For each pattern in the entity, the patternsProximity attribute value defines the distance (in Unicode characters) from the IdMatch location for all other Matches specified for that Pattern.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-243">For each pattern in the entity, the patternsProximity attribute value defines the distance (in Unicode characters) from the IdMatch location for all other Matches specified for that Pattern.</span></span> <span data-ttu-id="bc0f6-244">The proximity window is anchored by the IdMatch location, with the window extending to the left and right of the IdMatch.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-244">The proximity window is anchored by the IdMatch location, with the window extending to the left and right of the IdMatch.</span></span>
  
![Diagramm des Näherungsfensters](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
<span data-ttu-id="bc0f6-246">The example below illustrates how the proximity window affects the pattern matching where IdMatch element for the employee ID custom entity requires at least one corroborating match of keyword or date.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-246">The example below illustrates how the proximity window affects the pattern matching where IdMatch element for the employee ID custom entity requires at least one corroborating match of keyword or date.</span></span> <span data-ttu-id="bc0f6-247">Only ID1 matches because for ID2 and ID3, either no or only partial corroborating evidence is found within the proximity window.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-247">Only ID1 matches because for ID2 and ID3, either no or only partial corroborating evidence is found within the proximity window.</span></span>
  
![Diagramm von bestätigenden Nachweisen und Näherungsfenster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
<span data-ttu-id="bc0f6-249">Note that for email, the message body and each attachment are treated as separate items.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-249">Note that for email, the message body and each attachment are treated as separate items.</span></span> <span data-ttu-id="bc0f6-250">This means that the proximity window does not extend beyond the end of each of these items.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-250">This means that the proximity window does not extend beyond the end of each of these items.</span></span> <span data-ttu-id="bc0f6-251">For each item (attachment or body), both the idMatch and corroborative evidence needs to reside in that item.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-251">For each item (attachment or body), both the idMatch and corroborative evidence needs to reside in that item.</span></span>
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a><span data-ttu-id="bc0f6-252">What are the right confidence levels for different patterns?</span><span class="sxs-lookup"><span data-stu-id="bc0f6-252">What are the right confidence levels for different patterns?</span></span> <span data-ttu-id="bc0f6-253">[confidenceLevel attribute, recommendedConfidence attribute]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-253">[confidenceLevel attribute, recommendedConfidence attribute]</span></span>

<span data-ttu-id="bc0f6-254">The more evidence that a pattern requires, the more confidence you have that an actual entity (such as employee ID) has been identified when the pattern is matched.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-254">The more evidence that a pattern requires, the more confidence you have that an actual entity (such as employee ID) has been identified when the pattern is matched.</span></span> <span data-ttu-id="bc0f6-255">For example, you have more confidence in a pattern that requires a nine-digit ID number, hire date, and keyword in close proximity, than you do in a pattern that requires only a nine-digit ID number.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-255">For example, you have more confidence in a pattern that requires a nine-digit ID number, hire date, and keyword in close proximity, than you do in a pattern that requires only a nine-digit ID number.</span></span>
  
<span data-ttu-id="bc0f6-256">The Pattern element has a required confidenceLevel attribute.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-256">The Pattern element has a required confidenceLevel attribute.</span></span> <span data-ttu-id="bc0f6-257">You can think of the value of confidenceLevel (an integer between 1 and 100) as a unique ID for each pattern in an entity - the patterns in an entity must have different confidence levels that you assign.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-257">You can think of the value of confidenceLevel (an integer between 1 and 100) as a unique ID for each pattern in an entity - the patterns in an entity must have different confidence levels that you assign.</span></span> <span data-ttu-id="bc0f6-258">The precise value of the integer doesn't matter - simply pick numbers that make sense to your compliance team.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-258">The precise value of the integer doesn't matter - simply pick numbers that make sense to your compliance team.</span></span> <span data-ttu-id="bc0f6-259">After you upload your custom sensitive information type and then create a DLP policy, you can reference these confidence levels in the conditions of the rules that you create.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-259">After you upload your custom sensitive information type and then create a DLP policy, you can reference these confidence levels in the conditions of the rules that you create.</span></span>
  
![XML-Markup mit "Muster"-Elementen und verschiedenen Werten für das Attribut "Konfidenzniveau"](../media/301e0ba1-2deb-4add-977b-f6e9e18fba8b.png)
  
<span data-ttu-id="bc0f6-261">Zusätzlich zu "confidenceLevel" für jedes Muster weist "Entity" ein Attribut "recommendedConfidence" auf.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-261">In addition to confidenceLevel for each Pattern, the Entity has a recommendedConfidence attribute.</span></span> <span data-ttu-id="bc0f6-262">Dieses Attribut für die empfohlene Konfidenz kann man sich als das Standardkonfidenzniveau für die Regel vorstellen.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-262">The recommended confidence attribute can be thought of as the default confidence level for the rule.</span></span> <span data-ttu-id="bc0f6-263">Wenn Sie beim Erstellen einer Regel in einer DLP-Richtlinie kein zu verwendendes Konfidenzniveau für die Regel angeben, erfolgt der Abgleich für diese Regel basierend auf dem empfohlenen Konfidenzniveau für die Entität.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-263">When you create a rule in a DLP policy, if you don't specify a confidence level for the rule to use, that rule will match based on the recommended confidence level for the entity.</span></span> <span data-ttu-id="bc0f6-264">Bitte beachten Sie, dass das recommendedConfidence-Attribut für jede Entitäts-ID im Regelpaket zwingend erforderlich ist. Wenn es nicht vorhanden ist, können Sie keine Richtlinien speichern, die den Typ „vertrauliche Informationen“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-264">Please note that the recommendedConfidence attribute is mandatory for each Entity ID in the Rule Package, if missing you won't be able to save policies that use the Sensitive Information Type.</span></span> 
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-security-amp-compliance-center-localizedstrings-element"></a><span data-ttu-id="bc0f6-265">Do you want to support other languages in the UI of the Security &amp; Compliance Center?</span><span class="sxs-lookup"><span data-stu-id="bc0f6-265">Do you want to support other languages in the UI of the Security &amp; Compliance Center?</span></span> <span data-ttu-id="bc0f6-266">[LocalizedStrings element]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-266">[LocalizedStrings element]</span></span>

<span data-ttu-id="bc0f6-267">If your compliance team uses the Microsoft 365 Security &amp; Compliance Center to create DLP policies in different locales and in different languages, you can provide localized versions of the name and description of your custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-267">If your compliance team uses the Microsoft 365 Security &amp; Compliance Center to create DLP policies in different locales and in different languages, you can provide localized versions of the name and description of your custom sensitive information type.</span></span> <span data-ttu-id="bc0f6-268">When your compliance team uses Microsoft 365 in a language that you support, they'll see the localized name in the UI.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-268">When your compliance team uses Microsoft 365 in a language that you support, they'll see the localized name in the UI.</span></span>
  
![Instanzenanzahl und Optionen für die Übereinstimmungsgenauigkeit](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="bc0f6-270">The Rules element must contain a LocalizedStrings element, which contains a Resource element that references the GUID of your custom entity.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-270">The Rules element must contain a LocalizedStrings element, which contains a Resource element that references the GUID of your custom entity.</span></span> <span data-ttu-id="bc0f6-271">In turn, each Resource element contains one or more Name and Description elements that each use the langcode attribute to provide a localized string for a specific language.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-271">In turn, each Resource element contains one or more Name and Description elements that each use the langcode attribute to provide a localized string for a specific language.</span></span>
  
![XML-Markup mit Inhalt des LocalizedStrings-Elements](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
<span data-ttu-id="bc0f6-273">Note that you use localized strings only for how your custom sensitive information type appears in the UI of the Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-273">Note that you use localized strings only for how your custom sensitive information type appears in the UI of the Security &amp; Compliance Center.</span></span> <span data-ttu-id="bc0f6-274">You can't use localized strings to provide different localized versions of a keyword list or regular expression.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-274">You can't use localized strings to provide different localized versions of a keyword list or regular expression.</span></span>
  
## <a name="other-rule-package-markup-rulepack-guid"></a><span data-ttu-id="bc0f6-275">Sonstige Regelpaket-Markups [RulePack-GUID]</span><span class="sxs-lookup"><span data-stu-id="bc0f6-275">Other rule package markup [RulePack GUID]</span></span>

<span data-ttu-id="bc0f6-276">Finally, the beginning of each RulePackage contains some general information that you need to fill in.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-276">Finally, the beginning of each RulePackage contains some general information that you need to fill in.</span></span> <span data-ttu-id="bc0f6-277">You can use the following markup as a template and replace the ".</span><span class="sxs-lookup"><span data-stu-id="bc0f6-277">You can use the following markup as a template and replace the ".</span></span> <span data-ttu-id="bc0f6-278">.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-278">.</span></span> <span data-ttu-id="bc0f6-279">."</span><span class="sxs-lookup"><span data-stu-id="bc0f6-279">."</span></span> <span data-ttu-id="bc0f6-280">placeholders with your own info.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-280">placeholders with your own info.</span></span>
  
<span data-ttu-id="bc0f6-281">Most importantly, you'll need to generate a GUID for the RulePack.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-281">Most importantly, you'll need to generate a GUID for the RulePack.</span></span> <span data-ttu-id="bc0f6-282">Above, you generated a GUID for the entity; this is a second GUID for the RulePack.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-282">Above, you generated a GUID for the entity; this is a second GUID for the RulePack.</span></span> <span data-ttu-id="bc0f6-283">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span><span class="sxs-lookup"><span data-stu-id="bc0f6-283">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span></span>
  
<span data-ttu-id="bc0f6-284">The Version element is also important.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-284">The Version element is also important.</span></span> <span data-ttu-id="bc0f6-285">When you upload your rule package for the first time, Microsoft 365 notes the version number.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-285">When you upload your rule package for the first time, Microsoft 365 notes the version number.</span></span> <span data-ttu-id="bc0f6-286">Later, if you update the rule package and upload a new version, make sure to update the version number or Microsoft 365 won't deploy the rule package.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-286">Later, if you update the rule package and upload a new version, make sure to update the version number or Microsoft 365 won't deploy the rule package.</span></span>
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    . . .
 </Rules>
</RulePackage>

```

<span data-ttu-id="bc0f6-287">Wenn es fertig ist, sollte das RulePack-Element wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-287">When complete, your RulePack element should look like this.</span></span>
  
![XML-Markup mit dem RulePack-Element](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)
  
## <a name="changes-for-exchange-online"></a><span data-ttu-id="bc0f6-289">Änderungen für Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bc0f6-289">Changes for Exchange Online</span></span>

<span data-ttu-id="bc0f6-290">Previously, you might have used Exchange Online PowerShell to import your custom sensitive information types for DLP.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-290">Previously, you might have used Exchange Online PowerShell to import your custom sensitive information types for DLP.</span></span> <span data-ttu-id="bc0f6-291">Now your custom sensitive information types can be used in both the Exchange admin center and the Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-291">Now your custom sensitive information types can be used in both the Exchange admin center and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="bc0f6-292">As part of this improvement, you should use Security &amp; Compliance Center PowerShell to import your custom sensitive information types - you can't import them from the Exchange PowerShell anymore.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-292">As part of this improvement, you should use Security &amp; Compliance Center PowerShell to import your custom sensitive information types - you can't import them from the Exchange PowerShell anymore.</span></span> <span data-ttu-id="bc0f6-293">Your custom sensitive information types will continue to work just like before; however, it may take up to one hour for changes made to custom sensitive information types in the Security &amp; Compliance Center to appear in the Exchange admin center.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-293">Your custom sensitive information types will continue to work just like before; however, it may take up to one hour for changes made to custom sensitive information types in the Security &amp; Compliance Center to appear in the Exchange admin center.</span></span>
  
<span data-ttu-id="bc0f6-294">Note that in the Security &amp; Compliance Center, you use the **[New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage?view=exchange-ps)** cmdlet to upload a rule package.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-294">Note that in the Security &amp; Compliance Center, you use the **[New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage?view=exchange-ps)** cmdlet to upload a rule package.</span></span> <span data-ttu-id="bc0f6-295">(Previously, in the Exchange admin center, you used the  **ClassificationRuleCollection**\` cmdlet.)</span><span class="sxs-lookup"><span data-stu-id="bc0f6-295">(Previously, in the Exchange admin center, you used the  **ClassificationRuleCollection**\` cmdlet.)</span></span> 
  
## <a name="upload-your-rule-package"></a><span data-ttu-id="bc0f6-296">Hochladen des Regelpakets</span><span class="sxs-lookup"><span data-stu-id="bc0f6-296">Upload your rule package</span></span>



<span data-ttu-id="bc0f6-297">Gehen Sie zum Hochladen des Regelpakets wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-297">To upload your rule package, do the following steps:</span></span>
  
1. <span data-ttu-id="bc0f6-298">Speichern Sie es als XML-Datei mit Unicode-Codierung.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-298">Save it as an .xml file with Unicode encoding.</span></span>
    
2. [<span data-ttu-id="bc0f6-299">Herstellen einer Verbindung mit Security & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc0f6-299">Connect to Security & Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=799771)
    
3. <span data-ttu-id="bc0f6-300">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-300">Use the following syntax:</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="bc0f6-301">Dieses Beispiel lädt die Unicode-XML-Datei mit dem Namen „MyNewRulePack.xml“ aus C:\Dokumente“ hoch.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-301">This example uploads the Unicode XML file named MyNewRulePack.xml from C:\My Documents.</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="bc0f6-302">Ausführliche Informationen zur Syntax und zu den Parametern finden Sie unter [New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-302">For detailed syntax and parameter information, see [New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage).</span></span>

   > [!NOTE]
   > <span data-ttu-id="bc0f6-303">Die Grenze für benutzerdefinierte Sammlungen sensibler Informationstypen liegt bei 10.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-303">The limit for custom sensitive information type collections is 10.</span></span>

4. <span data-ttu-id="bc0f6-304">Um sicherzustellen, dass Sie einen neuen Typ für vertrauliche Informationen erstellt haben, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-304">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="bc0f6-305">Führen Sie das Cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) aus, um zu überprüfen, ob das neue Regelpaket aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-305">Run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet to verify the new rule package is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ``` 

   - <span data-ttu-id="bc0f6-306">Führen Sie das Cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) aus, um zu überprüfen, ob der Typ für vertrauliche Informationen aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-306">Run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to verify the sensitive information type is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ``` 

     <span data-ttu-id="bc0f6-307">Bei benutzerdefinierten Typen für vertrauliche Informationen ist der Publisher-Eigenschaftswert ein anderer als „Microsoft Corporation“.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-307">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="bc0f6-308">Ersetzen Sie \<Name\> durch den Namenswert des Typs für vertrauliche Informationen (z. B. die Mitarbeiter-ID), und führen Sie das Cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) aus:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-308">Replace \<Name\> with the Name value of the sensitive information type (example: Employee ID) and run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```
    
## <a name="potential-validation-issues-to-be-aware-of"></a><span data-ttu-id="bc0f6-309">Mögliche Überprüfungsprobleme, die zu beachten sind</span><span class="sxs-lookup"><span data-stu-id="bc0f6-309">Potential validation issues to be aware of</span></span>

<span data-ttu-id="bc0f6-310">When you upload your rule package XML file, the system validates the XML and checks for known bad patterns and obvious performance issues.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-310">When you upload your rule package XML file, the system validates the XML and checks for known bad patterns and obvious performance issues.</span></span> <span data-ttu-id="bc0f6-311">Here are some known issues that the validation checks for — a regular expression:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-311">Here are some known issues that the validation checks for — a regular expression:</span></span>
  
- <span data-ttu-id="bc0f6-312">Darf nicht mit einem Alternator „|“ beginnen, das allem entspricht, da es als leere Übereinstimmung angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-312">Cannot begin or end with alternator "|", which matches everything because it's considered an empty match.</span></span>
    
  <span data-ttu-id="bc0f6-313">Beispiel: „|a“ oder „|b“ besteht die Überprüfung nicht.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-313">For example, "|a" or "b|" will not pass validation.</span></span>
    
- <span data-ttu-id="bc0f6-314">Darf nicht mit einem „. {0, m}“-Muster beginnen oder enden, da dies keine Funktion hat und nur die Leistung beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-314">Cannot begin or end with a ".{0,m}" pattern, which has no functional purpose and only impairs performance.</span></span>
    
  <span data-ttu-id="bc0f6-315">Beispiel: „.{0,50}ASDF“ oder „ASDF.{0,50}“ besteht die Überprüfung nicht.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-315">For example, ".{0,50}ASDF" or "ASDF.{0,50}" will not pass validation.</span></span>
    
- <span data-ttu-id="bc0f6-316">Darf „.{0,m}“ oder „.{1,m}“ nicht in Gruppen haben, und darf nicht „.\*“ oder „.+“ in Gruppen haben.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-316">Cannot have ".{0,m}" or ".{1,m}" in groups, and cannot have ".\*" or ".+" in groups.</span></span>
    
  <span data-ttu-id="bc0f6-317">Beispiel: „(.{0,50000})“ besteht die Überprüfung nicht.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-317">For example, "(.{0,50000})" will not pass validation.</span></span>
    
- <span data-ttu-id="bc0f6-318">Darf keine Zeichen mit den Wiederholern „{0,m}“ oder „{1,m}“ haben.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-318">Cannot have any character with "{0,m}" or "{1,m}" repeaters in groups.</span></span>
    
  <span data-ttu-id="bc0f6-319">Beispiel: „(a\*)“ besteht die Überprüfung nicht.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-319">For example, "(a\*)" will not pass validation.</span></span>
    
- <span data-ttu-id="bc0f6-320">Darf nicht mit „.{1,m}“ beginnen oder enden; verwenden Sie stattdessen „.“</span><span class="sxs-lookup"><span data-stu-id="bc0f6-320">Cannot begin or end with ".{1,m}"; instead, use just "."</span></span>
    
  <span data-ttu-id="bc0f6-321">Beispiel: „.{1,m}asdf“ besteht die Überprüfung nicht; verwenden Sie stattdessen „.asdf“.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-321">For example, ".{1,m}asdf" will not pass validation; instead, use just ".asdf".</span></span>
    
- <span data-ttu-id="bc0f6-322">Darf keinen unbegrenzten Wiederholer in einer Grupe haben (wie z. B. „\*“ oder „+“).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-322">Cannot have an unbounded repeater (such as "\*" or "+") on a group.</span></span>
    
  <span data-ttu-id="bc0f6-323">Beispiel: „(xx)\*“ und „(xx)+“ bestehen die Überprüfung nicht.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-323">For example, "(xx)\*" and "(xx)+" will not pass validation.</span></span>
    
<span data-ttu-id="bc0f6-324">Wenn ein benutzerdefinierter Typ für vertrauliche Informationen ein Problem enthält, das die Leistung beeinträchtigen könnte, wird er nicht hochgeladen, und es wird möglicherweise eine der folgenden Fehlermeldungen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-324">If a custom sensitive information type contains an issue that may affect performance, it won't be uploaded and you may see one of these error messages:</span></span>
  
- <span data-ttu-id="bc0f6-325">**Generische Mengenangaben, die mit mehr Inhalten übereinstimmen als erwartet (z. B. „+“, „\*“)**</span><span class="sxs-lookup"><span data-stu-id="bc0f6-325">**Generic quantifiers which match more content than expected (e.g., '+', '\*')**</span></span>
    
- <span data-ttu-id="bc0f6-326">**Lookaround-Assertionen**</span><span class="sxs-lookup"><span data-stu-id="bc0f6-326">**Lookaround assertions**</span></span>
    
- <span data-ttu-id="bc0f6-327">**Komplexe Gruppieren in Verbindung mit allgemeinen Mengenangaben**</span><span class="sxs-lookup"><span data-stu-id="bc0f6-327">**Complex grouping in conjunction with general quantifiers**</span></span>
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a><span data-ttu-id="bc0f6-328">Neues Durchforsten des Inhalts, um die Typen für vertrauliche Informationen zu identifizieren</span><span class="sxs-lookup"><span data-stu-id="bc0f6-328">Recrawl your content to identify the sensitive information</span></span>

<span data-ttu-id="bc0f6-329">DLP uses the search crawler to identify and classify sensitive information in site content.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-329">DLP uses the search crawler to identify and classify sensitive information in site content.</span></span> <span data-ttu-id="bc0f6-330">Content in SharePoint Online and OneDrive for Business sites is recrawled automatically whenever it's updated.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-330">Content in SharePoint Online and OneDrive for Business sites is recrawled automatically whenever it's updated.</span></span> <span data-ttu-id="bc0f6-331">But to identify your new custom type of sensitive information in all existing content, that content must be recrawled.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-331">But to identify your new custom type of sensitive information in all existing content, that content must be recrawled.</span></span>
  
<span data-ttu-id="bc0f6-332">In Microsoft 365 können Sie das erneute Durchforsten des gesamten Mandanten nicht manuell anfordern, für eine Websitesammlung, Liste oder Bibliothek ist dies jedoch möglich. Weitere Informationen finden Sie unter [Manuelles Durchforsten und erneutes Indizieren einer Website, einer Bibliothek oder Liste](https://docs.microsoft.com/sharepoint/crawl-site-content).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-332">In Microsoft 365, you can't manually request a recrawl of an entire tenant, but you can do this for a site collection, list, or library - see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>
  
## <a name="remove-a-custom-sensitive-information-type"></a><span data-ttu-id="bc0f6-333">Entfernen eines benutzerdefinierten Typs für vertrauliche Informationen</span><span class="sxs-lookup"><span data-stu-id="bc0f6-333">Remove a custom sensitive information type</span></span>

> [!NOTE]
> <span data-ttu-id="bc0f6-334">Bevor Sie einen benutzerdefinierten Typ für vertrauliche Informationen entfernen, überprüfen Sie, dass keine DLP-Richtlinien oder Exchange-Nachrichtenflussregeln (auch bezeichnet als Transportregeln) mehr auf den Typ vertraulicher Informationen verweisen.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-334">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

<span data-ttu-id="bc0f6-335">In Security & Compliance Center PowerShell gibt es zwei Methoden zum Entfernen eines benutzerdefinierten Typs für vertrauliche Informationen:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-335">In Security & Compliance Center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="bc0f6-336">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type](#modify-a-custom-sensitive-information-type).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-336">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type](#modify-a-custom-sensitive-information-type).</span></span> <span data-ttu-id="bc0f6-337">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-337">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="bc0f6-338">**Entfernen eines benutzerdefinierten Regelpakets und aller benutzerdefinierten Typen für vertrauliche Informationen, die darin enthalten sind**: Diese Methode ist in diesem Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-338">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

1. [<span data-ttu-id="bc0f6-339">Herstellen einer Verbindung mit Security & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc0f6-339">Connect to Security & Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=799771)

2. <span data-ttu-id="bc0f6-340">Wenn Sie ein benutzerdefiniertes Regelpaket entfernen möchten, verwenden Sie das Cmdlet [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage?view=exchange-ps):</span><span class="sxs-lookup"><span data-stu-id="bc0f6-340">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="bc0f6-341">Sie können den Wert „Name“ (für jede Sprache) oder den Wert `RulePack id` (GUID) verwenden, um das Regelpaket zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-341">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="bc0f6-342">In diesem Beispiel wird das Regelpaket mit dem Namen „Employee ID Custom Rule Pack“ entfernt.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-342">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="bc0f6-343">Ausführliche Informationen zur Syntax und den Parametern finden Sie unter [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-343">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="bc0f6-344">Um sicherzustellen, dass Sie einen benutzerdefinierten Typen für vertrauliche Informationen erfolgreich entfernt haben, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-344">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="bc0f6-345">Führen Sie das Cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) aus und vergewissern Sie sich, dass das Regelpaket nicht mehr aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-345">Run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="bc0f6-346">Führen Sie das Cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) aus und stellen Sie sicher, dass die Typen für vertrauliche Informationen im entfernten Regelpaket nicht mehr aufgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-346">Run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="bc0f6-347">Bei benutzerdefinierten Typen für vertrauliche Informationen ist der Publisher-Eigenschaftswert ein anderer als „Microsoft Corporation“.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-347">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="bc0f6-348">Ersetzen Sie \<Name\> durch den Namenswert des Typs für vertrauliche Informationen (z. B. die Mitarbeiter-ID), und führen Sie das Cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) aus, um sicherzustellen, dass der Typ für vertrauliche Informationen nicht mehr aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-348">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="modify-a-custom-sensitive-information-type"></a><span data-ttu-id="bc0f6-349">Ändern eines benutzerdefinierten Typs für vertrauliche Informationen</span><span class="sxs-lookup"><span data-stu-id="bc0f6-349">Modify a custom sensitive information type</span></span>

<span data-ttu-id="bc0f6-350">In Security & Compliance Center PowerShell müssen Sie zum Ändern eines Typs für vertrauliche Informationen wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-350">In Security & Compliance Center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="bc0f6-351">Exportieren Sie das vorhandene Regelpaket, das den benutzerdefinierten Typ für vertrauliche Informationen enthält, in eine XML-Datei (oder verwenden Sie die vorhandene XML-Datei, wenn Sie darüber verfügen).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-351">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="bc0f6-352">Ändern Sie den benutzerdefinierten Typ für vertrauliche Informationen in der exportierten XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-352">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="bc0f6-353">Importieren Sie die aktualisierte XML-Datei wieder in das vorhandene Regelpaket.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-353">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="bc0f6-354">Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=799771).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-354">To connect to Security & Compliance Center PowerShell, see [Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=799771).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="bc0f6-355">Schritt 1: Exportieren des vorhandenen Regelpakets in eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="bc0f6-355">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="bc0f6-356">Wenn Sie eine Kopie der XML-Datei haben (z. B. eine soeben erstellte und importierte Datei), können Sie mit dem nächsten Schritt fortfahren, in dem Sie die XML-Datei ändern.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-356">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="bc0f6-357">Sollten Sie ihn noch nicht kennen, führen Sie das Cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) aus, um den Namen des benutzerdefinierten Regelpakets zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-357">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="bc0f6-358">Das integrierte Regelpaket mit den integrierten vertraulichen Informationstypen trägt den Namen Microsoft-Regelpaket.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-358">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package.</span></span> <span data-ttu-id="bc0f6-359">Das Regelpaket, das die benutzerdefinierten vertraulichen Informationstypen enthält, die Sie in der Benutzeroberfläche des Security & Compliance Centers erstellt haben, trägt den Namen "Microsoft. SCCManaged.CustomRulePack".</span><span class="sxs-lookup"><span data-stu-id="bc0f6-359">The rule package that contains the custom sensitive information types that you created in the Security & Compliance Center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="bc0f6-360">Verwenden Sie das Cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps), um das benutzerdefinierte Regelpaket in einer Variablen zu speichern:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-360">Use the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="bc0f6-361">Wenn der Name für das Regelpaket beispielsweise „Employee ID Custom Rule Pack“ lautet, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-361">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="bc0f6-362">Verwenden Sie das Cmdlet [Set-Content](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6) zum Exportieren des benutzerdefinierten Regelpakets in eine XML-Datei:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-362">Use the [Set-Content](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="bc0f6-363">In diesem Beispiel wird das Regelpaket in die Datei mit dem Namen „ExportedRulePackage.xml“ im Ordner „C:\Dokumente“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-363">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="bc0f6-364">Schritt 2: Ändern Sie den benutzerdefinierten Typ für vertrauliche Informationen in der exportierten XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-364">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="bc0f6-365">Typen für vertrauliche Informationen in der XML-Datei und andere Elemente in der Datei werden weiter oben in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-365">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="bc0f6-366">Schritt 3: Importieren Sie die aktualisierte XML-Datei wieder in das vorhandene Regelpaket.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-366">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="bc0f6-367">Verwenden Sie das Cmdlet [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage?view=exchange-ps), um die aktualisierte XML-Datei wieder in das vorhandene Regelpaket zu importieren:</span><span class="sxs-lookup"><span data-stu-id="bc0f6-367">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="bc0f6-368">Ausführliche Informationen zur Syntax und zu den Parametern finden Sie unter [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="bc0f6-368">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>

## <a name="reference-rule-package-xml-schema-definition"></a><span data-ttu-id="bc0f6-369">Referenz: XML-Schemadefinition für Regelpaket</span><span class="sxs-lookup"><span data-stu-id="bc0f6-369">Reference: Rule package XML schema definition</span></span>

<span data-ttu-id="bc0f6-370">Sie können dieses Markup kopieren, als eine XSD-Datei speichern und diese zum Überprüfen der XML-Datei für das Regelpaket verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc0f6-370">You can copy this markup, save it as an XSD file, and use it to validate your rule package XML file.</span></span>
  
```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="http://schemas.microsoft.com/office/2011/mce"
           targetNamespace="http://schemas.microsoft.com/office/2011/mce"
           xmlns:xs="https://www.w3.org/2001/XMLSchema"
           elementFormDefault="qualified"
           attributeFormDefault="unqualified"
           id="RulePackageSchema">
  <!-- Use include if this schema has the same target namespace as the schema being referenced, otherwise use import -->
  <xs:element name="RulePackage" type="mce:RulePackageType"/>
  <xs:simpleType name="LangType">
    <xs:union memberTypes="xs:language">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value=""/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="GuidType" final="#all">
    <xs:restriction base="xs:token">
      <xs:pattern value="[0-9a-fA-F]{8}\-([0-9a-fA-F]{4}\-){3}[0-9a-fA-F]{12}"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulePackageType">
    <xs:sequence>
      <xs:element name="RulePack" type="mce:RulePackType"/>
      <xs:element name="Rules" type="mce:RulesType">
        <xs:key name="UniqueRuleId">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueProcessorId">
          <xs:selector xpath="mce:Regex|mce:Keyword|mce:Fingerprint"></xs:selector>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueResourceIdRef">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:key>
        <xs:keyref name="ReferencedRuleMustExist" refer="mce:UniqueRuleId">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:keyref>
        <xs:keyref name="RuleMustHaveResource" refer="mce:UniqueResourceIdRef">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:keyref>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="RulePackType">
    <xs:sequence>
      <xs:element name="Version" type="mce:VersionType"/>
      <xs:element name="Publisher" type="mce:PublisherType"/>
      <xs:element name="Details" type="mce:DetailsType">
        <xs:key name="UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="mce:LocalizedDetails"/>
          <xs:field xpath="@langcode"/>
        </xs:key>
        <xs:keyref name="DefaultLangCodeMustExist" refer="mce:UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="."/>
          <xs:field xpath="@defaultLangCode"/>
        </xs:keyref>
      </xs:element>
      <xs:element name="Encryption" type="mce:EncryptionType" minOccurs="0" maxOccurs="1"/>
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="VersionType">
    <xs:attribute name="major" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="minor" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="build" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="revision" type="xs:unsignedShort" use="required"/>
  </xs:complexType>
  <xs:complexType name="PublisherType">
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="LocalizedDetailsType">
    <xs:sequence>
      <xs:element name="PublisherName" type="mce:NameType"/>
      <xs:element name="Name" type="mce:RulePackNameType"/>
      <xs:element name="Description" type="mce:OptionalNameType"/>
    </xs:sequence>
    <xs:attribute name="langcode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="DetailsType">
    <xs:sequence>
      <xs:element name="LocalizedDetails" type="mce:LocalizedDetailsType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="defaultLangCode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="EncryptionType">
    <xs:sequence>
      <xs:element name="Key" type="xs:normalizedString"/>
      <xs:element name="IV" type="xs:normalizedString"/>
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="RulePackNameType">
    <xs:restriction base="xs:token">
      <xs:minLength value="1"/>
      <xs:maxLength value="64"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="NameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="1"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="OptionalNameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="0"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="RestrictedTermType">
    <xs:restriction base="xs:string">
      <xs:minLength value="1"/>
      <xs:maxLength value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulesType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Entity" type="mce:EntityType"/>
        <xs:element name="Affinity" type="mce:AffinityType"/>
        <xs:element name="Version" type="mce:VersionedRuleType"/>
      </xs:choice>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Regex" type="mce:RegexType"/>
        <xs:element name="Keyword" type="mce:KeywordType"/>
        <xs:element name="Fingerprint" type="mce:FingerprintType"/>
        <xs:element name="ExtendedKeyword" type="mce:ExtendedKeywordType"/>
      </xs:choice>
      <xs:element name="LocalizedStrings" type="mce:LocalizedStringsType"/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="EntityType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedPatternType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="patternsProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="recommendedConfidence" type="mce:ProbabilityType"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="PatternType">
    <xs:sequence>
      <xs:element name="IdMatch" type="mce:IdMatchType"/>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="AffinityType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedEvidenceType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="evidencesProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="thresholdConfidenceLevel" type="mce:ProbabilityType" use="required"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="EvidenceType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="IdMatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
  </xs:complexType>
  <xs:complexType name="MatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
    <xs:attribute name="minCount" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="uniqueResults" type="xs:boolean" use="optional"/>
  </xs:complexType>
  <xs:complexType name="AnyType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="minMatches" type="xs:nonNegativeInteger" default="1"/>
    <xs:attribute name="maxMatches" type="xs:nonNegativeInteger" use="optional"/>
  </xs:complexType>
  <xs:simpleType name="ProximityType">
    <xs:union>
      <xs:simpleType>
        <xs:restriction base='xs:string'>
          <xs:enumeration value="unlimited"/>
        </xs:restriction>
      </xs:simpleType>
      <xs:simpleType>
        <xs:restriction base="xs:positiveInteger">
          <xs:minInclusive value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="ProbabilityType">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="WorkloadType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Exchange"/>
      <xs:enumeration value="Outlook"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="EngineVersionType">
    <xs:restriction base="xs:token">
      <xs:pattern value="^\d{2}\.01?\.\d{3,4}\.\d{1,3}$"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="VersionedRuleType">
    <xs:choice maxOccurs="unbounded">
      <xs:element name="Entity" type="mce:EntityType"/>
      <xs:element name="Affinity" type="mce:AffinityType"/>
    </xs:choice>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedPatternType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedEvidenceType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:simpleType name="FingerprintValueType">
    <xs:restriction base="xs:string">
      <xs:minLength value="2732"/>
      <xs:maxLength value="2732"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FingerprintType">
    <xs:simpleContent>
      <xs:extension base="mce:FingerprintValueType">
        <xs:attribute name="id" type="xs:token" use="required"/>
        <xs:attribute name="threshold" type="mce:ProbabilityType" use="required"/>
        <xs:attribute name="shingleCount" type="xs:positiveInteger" use="required"/>
        <xs:attribute name="description" type="xs:string" use="optional"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="RegexType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="KeywordType">
    <xs:sequence>
      <xs:element name="Group" type="mce:GroupType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="id" type="xs:token" use="required"/>
  </xs:complexType>
  <xs:complexType name="GroupType">
    <xs:sequence>
      <xs:choice>
        <xs:element name="Term" type="mce:TermType" maxOccurs="unbounded"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="matchStyle" default="word">
      <xs:simpleType>
        <xs:restriction base="xs:NMTOKEN">
          <xs:enumeration value="word"/>
          <xs:enumeration value="string"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
  <xs:complexType name="TermType">
    <xs:simpleContent>
      <xs:extension base="mce:RestrictedTermType">
        <xs:attribute name="caseSensitive" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="ExtendedKeywordType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="LocalizedStringsType">
    <xs:sequence>
      <xs:element name="Resource" type="mce:ResourceType" maxOccurs="unbounded">
      <xs:key name="UniqueLangCodeUsedInNamePerResource">
        <xs:selector xpath="mce:Name"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
      <xs:key name="UniqueLangCodeUsedInDescriptionPerResource">
        <xs:selector xpath="mce:Description"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
    </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ResourceType">
    <xs:sequence>
      <xs:element name="Name" type="mce:ResourceNameType" maxOccurs="unbounded"/>
      <xs:element name="Description" type="mce:DescriptionType" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="idRef" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="ResourceNameType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="DescriptionType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
</xs:schema>
```

## <a name="more-information"></a><span data-ttu-id="bc0f6-371">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc0f6-371">More information</span></span>

- [<span data-ttu-id="bc0f6-372">Übersicht über die Richtlinien zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="bc0f6-372">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)

- [<span data-ttu-id="bc0f6-373">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="bc0f6-373">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="bc0f6-374">Wonach die DLP-Funktionen suchen</span><span class="sxs-lookup"><span data-stu-id="bc0f6-374">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
