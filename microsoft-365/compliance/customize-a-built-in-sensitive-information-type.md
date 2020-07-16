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
ms.openlocfilehash: 6e9fb0295f8958584878921c1fac362dc511be8f
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086612"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="f2405-103">Anpassen eines benutzerdefinierten vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="f2405-103">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="f2405-p101">Bei der Suche nach vertraulichen Informationen in Inhalten müssen Sie die in einer so genannten *Regel* enthaltenen Informationen beschreiben. DLP (Data Loss Prevention, Verhinderung von Datenverlust) umfasst Regeln für die gängigsten vertraulichen Informationstypen, das Sie sofort nutzen können. Um diese Regeln zu verwenden, müssen Sie sie in eine Richtlinie aufnehmen. Möglicherweise möchten Sie die integrierten Regeln an die spezifischen Anforderungen Ihrer Organisation anpassen. Zu diesem Zweck können Sie benutzerdefinierte vertrauliche Informationstypen erstellen. In diesem Thema erfahren Sie, wie Sie die XML-Datei anpassen, die die vorhandene Regelsammlung enthält, damit ein größerer Bereich potenzieller Kreditkarteninformationen erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="f2405-p101">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  . Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away. To use these rules, you have to include them in a policy. You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type. This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span> 
  
<span data-ttu-id="f2405-p102">Dieses Beispiel können Sie auf weitere integrierte vertrauliche Informationstypen anwenden. Eine Liste der standardmäßigen vertraulichen Informationstypen und XML-Definitionen finden Sie unter [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="f2405-p102">You can take this example and apply it to other built-in sensitive information types. For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span> 
  
## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="f2405-111">Exportieren der XML-Datei der aktuellen Regeln</span><span class="sxs-lookup"><span data-stu-id="f2405-111">Export the XML file of the current rules</span></span>

<span data-ttu-id="f2405-112">Zum Exportieren der XML-Datei müssen Sie [eine Verbindung mit dem Security and Compliance Center über Remote-PowerShell herstellen](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="f2405-112">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="f2405-p103">Geben Sie in PowerShell Folgendes ein, um die Regeln Ihrer Organisation anzuzeigen. Falls Sie keine eigenen Regeln erstellt haben, werden nur die integrierten Standardregeln mit der Bezeichnung „Microsoft-Regelpaket“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2405-p103">In the PowerShell, type the following to display your organization's rules on screen. If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

2. <span data-ttu-id="f2405-p104">Speichern Sie die Regeln Ihrer Organisation in einer Variablen, indem Sie Folgendes eingeben. Durch das Speichern in einer Variablen kann später problemlos auf die Daten in einem Format zugegriffen werden, das sich für Remote-PowerShell-Befehle eignet.</span><span class="sxs-lookup"><span data-stu-id="f2405-p104">Store your organization's rules in a variable by typing the following. Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>

   ```powershell    
   $ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
   ```
    
3. <span data-ttu-id="f2405-p105">Erstellen Sie eine formatierte XML-Datei mit all diesen Daten, indem Sie Folgendes eingeben. (`Set-content` ist der Teil des Cmdlets, das die XML-Daten in die Datei schreibt.)</span><span class="sxs-lookup"><span data-stu-id="f2405-p105">Make a formatted XML file with all that data by typing the following. ( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span> 

   ```powershell
   Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="f2405-p106">Stellen Sie sicher, dass der Dateispeicherort verwendet wird, in dem das Regelpaket tatsächlich gespeichert ist. `C:\custompath\` ist ein Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="f2405-p106">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="f2405-121">Suchen der Regel, die in der XML-Datei geändert werden soll</span><span class="sxs-lookup"><span data-stu-id="f2405-121">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="f2405-p107">Mit den vorstehenden Cmdlets wurde die gesamte *Regelsammlung* exportiert, die die Standardregeln umfasst. Anschließend müssen Sie speziell nach der Regel für die Kreditkartennummer suchen, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f2405-p107">The cmdlets above exported the entire *rule collection*, which includes the default rules we provide. Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span> 
  
1. <span data-ttu-id="f2405-124">Verwenden Sie einen Texteditor, um die im vorherigen Abschnitt exportierte XML-Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f2405-124">Use a text editor to open the XML file that you exported in the previous section.</span></span>
    
2. <span data-ttu-id="f2405-p108">Führen Sie einen Bildlauf bis zum Tag `<Rules>` durch, mit dem der Abschnitt beginnt, der die DLP-Regeln enthält. Da diese XML-Datei die Informationen für die gesamte Regelsammlung enthält, sind am Anfang weitere Informationen enthalten, über die Sie hinweg blättern müssen, um zu den Regeln zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="f2405-p108">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules. Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.</span></span>
    
3. <span data-ttu-id="f2405-p109">Suchen Sie nach *Func_credit_card*, um die Regeldefinition für die Kreditkartennummer zu suchen. In der XML-Datei dürfen Regelnamen keine Leerzeichen enthalten, sodass die Leerzeichen üblicherweise durch Unterstriche ersetzt und die Regelnamen manchmal abgekürzt werden. Ein Beispiel hierfür ist die Regel für die US-Sozialversicherungsnummer, die als _SSN_ abgekürzt wird. Die XML-Datei der Kreditkartennummer-Regel sollte wie das folgende Codebeispiel aussehen.</span><span class="sxs-lookup"><span data-stu-id="f2405-p109">Look for *Func_credit_card* to find the Credit Card Number rule definition. In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated. An example of this is the U.S. Social Security number rule, which is abbreviated _SSN_. The Credit Card Number rule XML should look like the following code sample.</span></span>
    
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

<span data-ttu-id="f2405-p110">Nachdem Sie die Regeldefinition für die Kreditkartennummer in der XML-Datei ermittelt haben, können Sie die XML-Datei der Regel an Ihre Anforderungen anpassen. Eine Wiederholung zu den XML-Definitionen finden Sie am Ende dieses Themas unter [Glossar](#term-glossary).</span><span class="sxs-lookup"><span data-stu-id="f2405-p110">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs. For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.</span></span>
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="f2405-133">Ändern der XML-Datei und Erstellen eines neuen vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="f2405-133">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="f2405-p111">Zuerst müssen Sie einen neuen vertraulichen Informationstyp erstellen, da Sie die Standardregeln nicht direkt ändern können. Sie können eine Vielzahl von Maßnahmen im Zusammenhang mit benutzerdefinierten vertraulichen Informationstypen ergreifen. Diese werden unter [Erstellen eines benutzerdefinierten vertraulichen Informationstyps in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) beschrieben. In diesem Beispiel machen wir es nicht kompliziert, sondern entfernen nur den bestätigenden Nachweis und fügen der Regel für die Kreditkartennummer Schlüsselwörter hinzu.</span><span class="sxs-lookup"><span data-stu-id="f2405-p111">First, you need to create a new sensitive information type because you can't directly modify the default rules. You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>
  
<span data-ttu-id="f2405-p112">Alle XML-Regeldefinitionen werden anhand der folgenden allgemeinen Vorlage erstellt. Sie müssen die XML-Definition der Kreditkartennummer in der Vorlage kopieren und einfügen, einige Werte ändern (beachten Sie die Platzhalter ". . ." im folgenden Beispiel) und anschließend die geänderte XML-Datei als neue Regel hochladen, die in Richtlinien verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f2405-p112">All XML rule definitions are built on the following general template. You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ". . ." placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>
  
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

<span data-ttu-id="f2405-p113">Sie verfügen nun über eine XML-Datei, die der Folgenden ähnelt. Da Regelpakete und Regeln anhand ihrer eindeutigen GUIDs identifiziert werden, müssen Sie zwei GUIDs generieren: eine für das Regelpaket und eine zum Ersetzen der GUID für die Kreditkartennummer-Regel. Die GUID für die Entitäts-ID im folgenden Codebeispiel ist die für unsere integrierte Regeldefinition, die Sie durch eine neue GUID ersetzen müssen. Es gibt verschiedene Wege zum Generieren von GUIDs. Sie können dies jedoch unkompliziert in PowerShell bewerkstelligen, indem Sie **[guid]::NewGuid()** eingeben.</span><span class="sxs-lookup"><span data-stu-id="f2405-p113">Now, you have something that looks similar to the following XML. Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule. The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> 
  
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

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="f2405-146">Entfernen der Anforderung für einen bestätigenden Nachweis von einem vertraulichen Informationstyp</span><span class="sxs-lookup"><span data-stu-id="f2405-146">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="f2405-147">Nachdem Sie einen neuen vertraulichen Informationstyp erstellt haben, den Sie in das Security &amp; Compliance Center hochladen können, besteht der nächste Schritte darin, spezifischere Angaben für die Regel festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f2405-147">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific.</span></span> <span data-ttu-id="f2405-148">Ändern Sie die Regel so, dass sie nur nach einer 16-stelligen Zahl sucht, die die Prüfsummenprüfung besteht, für die aber kein weiterer (bestätigender) Nachweis erforderlich ist, beispielsweise Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="f2405-148">Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence, like keywords.</span></span> <span data-ttu-id="f2405-149">Hierfür müssen Sie den Teil der XML-Datei entfernen, der nach dem bestätigenden Nachweis sucht.</span><span class="sxs-lookup"><span data-stu-id="f2405-149">To do this, you need to remove the part of the XML that looks for corroborative evidence.</span></span> <span data-ttu-id="f2405-150">Der bestätigende Nachweis ist sehr hilfreich bei der Verringerung falsch positiver Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="f2405-150">Corroborative evidence is very helpful in reducing false positives.</span></span> <span data-ttu-id="f2405-151">In diesem Falle befinden sich üblicherweise bestimmte Schlüsselwörter oder ein Ablaufdatum in der Nähe der Kreditkartennummer.</span><span class="sxs-lookup"><span data-stu-id="f2405-151">In this case there are usually certain keywords or an expiration date near the credit card number.</span></span> <span data-ttu-id="f2405-152">Wenn Sie den Nachweis entfernen, sollten Sie auch anpassen, wie sicher Sie sind, dass Sie eine Kreditkartennummer gefunden haben, indem Sie den `confidenceLevel`-Wert senken (in dem Beispiel ist dies 85).</span><span class="sxs-lookup"><span data-stu-id="f2405-152">If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="f2405-153">Suchen nach Schlüsselwörtern speziell für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="f2405-153">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="f2405-p115">Sie möchten möglicherweise festlegen, dass der bestätigende Nachweis erforderlich ist, aber andere oder zusätzliche Schlüsselwörter angeben. Möglicherweise möchten Sie auch ändern, wo nach diesem Nachweis gesucht werden soll. Sie können das Attribut `patternsProximity` anpassen, um das Fenster für den bestätigenden Nachweis um die 16-stellige Zahl herum zu erweitern oder zu verkleinern. Um Ihre eigenen Schlüsselwörter hinzuzufügen, müssen Sie eine Schlüsselwortliste definieren und in Ihrer Regel darauf verweisen. Mit der folgenden XML-Datei werden die Schlüsselwörter "company card" (Firmenkarte) und "Contoso card" (Contoso-Karte) hinzugefügt, sodass jede Nachricht, die diese Phrasen im Umkreis von 150 Zeichen von einer Kreditkartennummer enthält, als Kreditkartennummer erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="f2405-p115">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence. You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number. To add your own keywords, you need to define a keyword list and reference it within your rule. The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span>
  
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

## <a name="upload-your-rule"></a><span data-ttu-id="f2405-158">Hochladen der Regel</span><span class="sxs-lookup"><span data-stu-id="f2405-158">Upload your rule</span></span>

<span data-ttu-id="f2405-159">Zum Hochladen der Regel müssen Sie wie folgt vorgehen.</span><span class="sxs-lookup"><span data-stu-id="f2405-159">To upload your rule, you need to do the following.</span></span>
  
1. <span data-ttu-id="f2405-p116">Speichern Sie sie als XML-Datei mit Unicode-Codierung. Dies ist wichtig, da die Regel nicht funktioniert, wenn die Datei mit einer anderen Codierung gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f2405-p116">Save it as an .xml file with Unicode encoding. This is important because the rule won't work if the file is saved with a different encoding.</span></span>
    
2. [<span data-ttu-id="f2405-162">Herstellen einer Verbindung zum Security and Compliance Center mithilfe von Remote-PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2405-162">Connect to the Security and Compliance Center via Remote PowerShell.</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. <span data-ttu-id="f2405-163">Geben Sie PowerShell Folgendes ein.</span><span class="sxs-lookup"><span data-stu-id="f2405-163">In the PowerShell, type the following.</span></span>

   ```powershell    
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)
   ```
   
   > [!IMPORTANT]
   > <span data-ttu-id="f2405-p117">Stellen Sie sicher, dass der Dateispeicherort verwendet wird, in dem das Regelpaket tatsächlich gespeichert ist. `C:\custompath\` ist ein Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="f2405-p117">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
4. <span data-ttu-id="f2405-166">Geben Sie zur Bestätigung Y ein, und drücken Sie die **EINGABETASTE**. </span><span class="sxs-lookup"><span data-stu-id="f2405-166">To confirm, type Y, and then press **Enter**.</span></span>

5. <span data-ttu-id="f2405-167">Überprüfen Sie, ob Ihre neue Regel hochgeladen wurde, sowie den Anzeigenamen, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="f2405-167">Verify that your new rule was uploaded and its display name by typing:</span></span>

   ```powershell
   Get-DlpSensitiveInformationType
   ```

<span data-ttu-id="f2405-p118">Sie müssen die Regel einer DLP-Richtlinie hinzufügen, um damit zu beginnen, die Regel zum Erkennen vertraulicher Informationen zu verwenden. Informationen zum Hinzufügen einer Regel zu einer Richtlinie finden Sie unter [Erstellen einer DLP-Richtlinie aus einer Vorlage](create-a-dlp-policy-from-a-template.md).</span><span class="sxs-lookup"><span data-stu-id="f2405-p118">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy. To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>
  
## <a name="term-glossary"></a><span data-ttu-id="f2405-170">Glossar</span><span class="sxs-lookup"><span data-stu-id="f2405-170">Term glossary</span></span>

<span data-ttu-id="f2405-171">Nachfolgend finden Sie Definitionen der Begriffe, die in diesem Verfahren vorkommen.</span><span class="sxs-lookup"><span data-stu-id="f2405-171">These are the definitions for the terms you encountered during this procedure.</span></span>
  
|<span data-ttu-id="f2405-172">**Begriff**</span><span class="sxs-lookup"><span data-stu-id="f2405-172">**Term**</span></span>|<span data-ttu-id="f2405-173">**Definition**</span><span class="sxs-lookup"><span data-stu-id="f2405-173">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f2405-174">Entität</span><span class="sxs-lookup"><span data-stu-id="f2405-174">Entity</span></span>|<span data-ttu-id="f2405-p119">Entitäten sind vertrauliche Informationstypen, wie beispielsweise Kreditkartennummern. Jede Entität verfügt über eine eindeutige GUID als ID. Wenn Sie eine GUID kopieren und in der XML-Datei danach suchen, finden Sie die XML-Regeldefinition und alle lokalisierten Übersetzungen dieser XML-Regel. Diese Definition können Sie auch finden, indem Sie die GUID für die Übersetzung ermitteln und dann nach dieser GUID suchen.</span><span class="sxs-lookup"><span data-stu-id="f2405-p119">Entities are what we call sensitive information types, such as credit card numbers. Each entity has a unique GUID as its ID. If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule. You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="f2405-179">Funktionen</span><span class="sxs-lookup"><span data-stu-id="f2405-179">Functions</span></span>|<span data-ttu-id="f2405-p120">Die XML-Datei verweist auf `Func_credit_card`, eine Funktion im kompilierten Code. Funktionen dienen zur Ausführung komplexer regulärer Ausdrücke und prüfen, ob Prüfsummen mit den integrierten Regeln übereinstimmen. Da dies im Code geschieht, werden einige der Variablen nicht in der XML-Datei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2405-p120">The XML file references  `Func_credit_card`, which is a function in compiled code. Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="f2405-182">IdMatch</span><span class="sxs-lookup"><span data-stu-id="f2405-182">IdMatch</span></span>|<span data-ttu-id="f2405-183">Dies ist die Kennung, die das Muster abgleichen möchte – beispielsweise eine Kreditkartennummer.</span><span class="sxs-lookup"><span data-stu-id="f2405-183">This is the identifier that the pattern is to trying to match—for example, a credit card number.</span></span>|
|<span data-ttu-id="f2405-184">Schlüsselwortliste</span><span class="sxs-lookup"><span data-stu-id="f2405-184">Keyword lists</span></span>|<span data-ttu-id="f2405-p121">Die XML-Datei verweist außerdem auf `keyword_cc_verification` und `keyword_cc_name`. Dies sind Schlüsselwortlisten, anhand derer nach Übereinstimmungen mit dem Attribut `patternsProximity` für die Entität gesucht wird. Diese werden zurzeit nicht in der XML-Datei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2405-p121">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity. These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="f2405-187">Muster</span><span class="sxs-lookup"><span data-stu-id="f2405-187">Pattern</span></span>|<span data-ttu-id="f2405-188">Das Muster enthält die Liste der Informationen, anhand derer der vertrauliche Informationstyp sucht.</span><span class="sxs-lookup"><span data-stu-id="f2405-188">The pattern contains the list of what the sensitive type is looking for.</span></span> <span data-ttu-id="f2405-189">Hierzu zählen Schlüsselwörter, reguläre Ausdrücke und interne Funktionen, die Aufgaben ausführen, wie beispielsweise die Überprüfung von Prüfsummen.</span><span class="sxs-lookup"><span data-stu-id="f2405-189">This includes keywords, regexes, and internal functions, which perform tasks like verifying checksums.</span></span> <span data-ttu-id="f2405-190">Vertrauliche Informationstypen können mehrere Muster mit eindeutigen Angaben zur Vertrauenswürdigkeit aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f2405-190">Sensitive information types can have multiple patterns with unique confidences.</span></span> <span data-ttu-id="f2405-191">Dies ist nützlich, wenn ein vertraulicher Informationstyp erstellt wird, der eine hohe Vertrauenswürdigkeit zurückgibt, falls ein bestätigender Nachweis gefunden wurde, und der eine niedrige Vertrauenswürdigkeit zurückgibt, wenn nur ein geringer oder gar kein bestätigender Nachweis gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="f2405-191">This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="f2405-192">Pattern confidenceLevel</span><span class="sxs-lookup"><span data-stu-id="f2405-192">Pattern confidenceLevel</span></span>|<span data-ttu-id="f2405-p123">Dies ist die Vertrauensstufe, für die das DLP-Modul eine Übereinstimmung gefunden hat. Diese Vertrauensstufe wird einer Übereinstimmung für das Muster zugeordnet, wenn die Anforderungen des Musters erfüllt sind. Es handelt sich hierbei um das Maß an Vertrauenswürdigkeit, das Sie bei Verwendung von Exchange-E-Mail-Flussregeln (auch als Transportregeln bezeichnet) erwägen sollten.</span><span class="sxs-lookup"><span data-stu-id="f2405-p123">This is the level of confidence that the DLP engine found a match. This level of confidence is associated with a match for the pattern if the pattern's requirements are met. This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="f2405-196">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="f2405-196">patternsProximity</span></span>|<span data-ttu-id="f2405-197">Wird etwas gefunden, das wie ein Kreditkartennummer-Muster aussieht, handelt es sich bei dem Attribut `patternsProximity` um die Umgebung der Nummer, in der nach einem bestätigenden Nachweis gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="f2405-197">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="f2405-198">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="f2405-198">recommendedConfidence</span></span>|<span data-ttu-id="f2405-p124">Dies ist die Vertrauensstufe, die für diese Regel empfohlen wird. Die empfohlene Vertrauensstufe gilt für Entitäten und Affinitäten. Für Entitäten wird diese Zahl niemals anhand des Attributs `confidenceLevel` für das Muster ausgewertet. Es ist lediglich eine Empfehlung, die Ihnen bei der Auswahl einer Vertrauensstufe helfen soll, falls Sie eine solche zuweisen möchten. Für Affinitäten muss das Attribut `confidenceLevel` des Musters höher sein als die Zahl des Attributs `recommendedConfidence` für eine aufzurufende E-Mail-Flussregel-Aktion. Das Attribut `recommendedConfidence` ist die in E-Mail-Flussregeln verwendete Standardvertrauensstufe, die eine Aktion aufruft. Bei Bedarf können Sie stattdessen die aufzurufende E-Mail-Flussregel manuell basierend auf der Vertrauensstufe des Musters ändern.</span><span class="sxs-lookup"><span data-stu-id="f2405-p124">This is the confidence level we recommend for this rule. The recommended confidence applies to entities and affinities. For entities, this number is never evaluated against the  `confidenceLevel` for the pattern. It's merely a suggestion to help you choose a confidence level if you want to apply one. For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked. The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action. If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|
   
## <a name="for-more-information"></a><span data-ttu-id="f2405-206">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2405-206">For more information</span></span>

- [<span data-ttu-id="f2405-207">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="f2405-207">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="f2405-208">Erstellen eines benutzerdefinierten vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="f2405-208">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    
- [<span data-ttu-id="f2405-209">Übersicht über die Richtlinien zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="f2405-209">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
