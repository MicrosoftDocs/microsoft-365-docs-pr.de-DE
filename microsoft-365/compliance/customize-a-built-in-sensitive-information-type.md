---
title: Anpassen eines benutzerdefinierten vertraulichen Informationstyps
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie einen benutzerdefinierten vertraulichen Informationstyp erstellen, der es Ihnen ermöglicht, Regeln zu verwenden, die den Anforderungen Ihrer Organisation entsprechen.
ms.openlocfilehash: 7c9be91de796ed06ca2bdd71e9e4de0462a92358
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817934"
---
# <a name="customize-a-built-in-sensitive-information-type"></a>Anpassen eines benutzerdefinierten vertraulichen Informationstyps

When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  . Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away. To use these rules, you have to include them in a policy. You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type. This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information. 
  
You can take this example and apply it to other built-in sensitive information types. For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md). 
  
## <a name="export-the-xml-file-of-the-current-rules"></a>Exportieren der XML-Datei der aktuellen Regeln

Zum Exportieren der XML-Datei müssen Sie [eine Verbindung mit dem Security and Compliance Center über Remote-PowerShell herstellen](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).
  
1. In the PowerShell, type the following to display your organization's rules on screen. If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."

```powershell
Get-DlpSensitiveInformationTypeRulePackage
```    
2. Store your organization's rules in a variable by typing the following. Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.

```powershell    
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
```
    
3. Make a formatted XML file with all that data by typing the following. ( `Set-content` is the part of the cmdlet that writes the XML to the file.) 
    
```powershell
Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
```

> [!IMPORTANT]
> Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder. 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a>Suchen der Regel, die in der XML-Datei geändert werden soll

The cmdlets above exported the entire *rule collection*, which includes the default rules we provide. Next you'll need to look specifically for the Credit Card Number rule that you want to modify. 
  
1. Verwenden Sie einen Texteditor, um die im vorherigen Abschnitt exportierte XML-Datei zu öffnen.
    
2. Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules. Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.
    
3. Look for *Func_credit_card* to find the Credit Card Number rule definition. In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated. An example of this is the U.S. Social Security number rule, which is abbreviated "SSN." The Credit Card Number rule XML should look like the following code sample.
    
  ```xml
  <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
         patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
         <IdMatch idRef="Func_credit_card" />
          <Any minMatches="1">
            <Match idRef="Keyword_cc_verification" />
            <Match idRef="Keyword_cc_name" />
            <Match idRef="Func_expiration_date" />
          </Any>
        </Pattern>
      </Entity>
  ```

Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs. For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a>Ändern der XML-Datei und Erstellen eines neuen vertraulichen Informationstyps

First, you need to create a new sensitive information type because you can't directly modify the default rules. You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.
  
All XML rule definitions are built on the following general template. You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ". . ." placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
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
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

Now, you have something that looks similar to the following XML. Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule. The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**. 
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a>Entfernen der Anforderung für einen bestätigenden Nachweis von einem vertraulichen Informationstyp

Nachdem Sie einen neuen vertraulichen Informationstyp erstellt haben, den Sie in das Security &amp; Compliance Center hochladen können, besteht der nächste Schritte darin, spezifischere Angaben für die Regel festzulegen. Ändern Sie die Regel so, dass sie nur nach einer 16-stelligen Zahl sucht, die die Prüfsummenprüfung besteht, für die aber kein weiterer (bestätigender) Nachweis erforderlich ist, beispielsweise Schlüsselwörter. Hierfür müssen Sie den Teil der XML-Datei entfernen, der nach dem bestätigenden Nachweis sucht. Der bestätigende Nachweis ist sehr hilfreich bei der Verringerung falsch positiver Ergebnisse. In diesem Falle befinden sich üblicherweise bestimmte Schlüsselwörter oder ein Ablaufdatum in der Nähe der Kreditkartennummer. Wenn Sie den Nachweis entfernen, sollten Sie auch anpassen, wie sicher Sie sind, dass Sie eine Kreditkartennummer gefunden haben, indem Sie den `confidenceLevel`-Wert senken (in dem Beispiel ist dies 85).
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a>Suchen nach Schlüsselwörtern speziell für Ihre Organisation

You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence. You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number. To add your own keywords, you need to define a keyword list and reference it within your rule. The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.
  
```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a>Hochladen der Regel

Zum Hochladen der Regel müssen Sie wie folgt vorgehen.
  
1. Save it as an .xml file with Unicode encoding. This is important because the rule won't work if the file is saved with a different encoding.
    
2. [Herstellen einer Verbindung zum Security and Compliance Center mithilfe von Remote-PowerShell](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. Geben Sie PowerShell Folgendes ein.

```powershell    
New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte).
```
> [!IMPORTANT]
> Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder. 
  
4. Geben Sie zur Bestätigung Y ein, und drücken Sie die **EINGABETASTE**. 
5. Überprüfen Sie, ob Ihre neue Regel hochgeladen wurde, sowie den Anzeigenamen, indem Sie Folgendes eingeben:

```powershell
Get-DlpSensitiveInformationType
```

To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy. To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).
  
## <a name="term-glossary"></a>Glossar

Nachfolgend finden Sie Definitionen der Begriffe, die in diesem Verfahren vorkommen.
  
|**Begriff**|**Definition**|
|:-----|:-----|
|Entität|Entities are what we call sensitive information types, such as credit card numbers. Each entity has a unique GUID as its ID. If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule. You can also find this definition by locating the GUID for the translation and then searching for that GUID.|
|Funktionen|The XML file references  `Func_credit_card`, which is a function in compiled code. Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.|
|IdMatch|Dies ist die Kennung, die das Muster abgleichen möchte – beispielsweise eine Kreditkartennummer.|
|Schlüsselwortliste|The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity. These aren't currently displayed in the XML.|
|Muster|Das Muster enthält die Liste der Informationen, anhand derer der vertrauliche Informationstyp sucht. Hierzu zählen Schlüsselwörter, reguläre Ausdrücke und interne Funktionen, die Aufgaben ausführen, wie beispielsweise die Überprüfung von Prüfsummen. Vertrauliche Informationstypen können mehrere Muster mit eindeutigen Angaben zur Vertrauenswürdigkeit aufweisen. Dies ist nützlich, wenn ein vertraulicher Informationstyp erstellt wird, der eine hohe Vertrauenswürdigkeit zurückgibt, falls ein bestätigender Nachweis gefunden wurde, und der eine niedrige Vertrauenswürdigkeit zurückgibt, wenn nur ein geringer oder gar kein bestätigender Nachweis gefunden wurde.|
|Pattern confidenceLevel|This is the level of confidence that the DLP engine found a match. This level of confidence is associated with a match for the pattern if the pattern's requirements are met. This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).|
|patternsProximity|Wird etwas gefunden, das wie ein Kreditkartennummer-Muster aussieht, handelt es sich bei dem Attribut `patternsProximity` um die Umgebung der Nummer, in der nach einem bestätigenden Nachweis gesucht wird.|
|recommendedConfidence|This is the confidence level we recommend for this rule. The recommended confidence applies to entities and affinities. For entities, this number is never evaluated against the  `confidenceLevel` for the pattern. It's merely a suggestion to help you choose a confidence level if you want to apply one. For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked. The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action. If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.|
   
## <a name="for-more-information"></a>Weitere Informationen

- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
    
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps](create-a-custom-sensitive-information-type.md)
    
- [Übersicht über die Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md)
