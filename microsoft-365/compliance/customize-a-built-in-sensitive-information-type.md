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
description: Bei der Suche nach vertraulichen Informationen in Inhalten müssen Sie die in einer so genannten Regel enthaltenen Informationen beschreiben. DLP (Data Loss Prevention, Verhinderung von Datenverlust) umfasst Regeln für die gängigsten vertraulichen Informationstypen, das Sie sofort nutzen können. Um diese Regeln zu verwenden, müssen Sie sie in eine Richtlinie aufnehmen. Möglicherweise möchten Sie die integrierten Regeln an die spezifischen Anforderungen Ihrer Organisation anpassen. Zu diesem Zweck können Sie benutzerdefinierte vertrauliche Informationstypen erstellen. In diesem Thema erfahren Sie, wie Sie die XML-Datei anpassen, die die vorhandene Regelsammlung enthält, damit ein größerer Bereich potenzieller Kreditkarteninformationen erkannt wird.
ms.openlocfilehash: 4c61ab1a60b6259509d2928e22d31e447a996ec9
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595492"
---
# <a name="customize-a-built-in-sensitive-information-type"></a>Anpassen eines benutzerdefinierten vertraulichen Informationstyps

Bei der Suche nach vertraulichen Informationen in Inhalten müssen Sie die in einer so genannten *Regel* enthaltenen Informationen beschreiben. DLP (Data Loss Prevention, Verhinderung von Datenverlust) umfasst Regeln für die gängigsten vertraulichen Informationstypen, das Sie sofort nutzen können. Um diese Regeln zu verwenden, müssen Sie sie in eine Richtlinie aufnehmen. Möglicherweise möchten Sie die integrierten Regeln an die spezifischen Anforderungen Ihrer Organisation anpassen. Zu diesem Zweck können Sie benutzerdefinierte vertrauliche Informationstypen erstellen. In diesem Thema erfahren Sie, wie Sie die XML-Datei anpassen, die die vorhandene Regelsammlung enthält, damit ein größerer Bereich potenzieller Kreditkarteninformationen erkannt wird. 
  
Dieses Beispiel können Sie auf weitere integrierte vertrauliche Informationstypen anwenden. Eine Liste der standardmäßigen vertraulichen Informationstypen und XML-Definitionen finden Sie unter [Wonach die Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md). 
  
## <a name="export-the-xml-file-of-the-current-rules"></a>Exportieren der XML-Datei der aktuellen Regeln

Zum Exportieren der XML-Datei müssen Sie [eine Verbindung mit dem Security and Compliance Center über Remote-PowerShell herstellen](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).
  
1. Geben Sie in PowerShell Folgendes ein, um die Regeln Ihrer Organisation anzuzeigen. Falls Sie keine eigenen Regeln erstellt haben, werden nur die integrierten Standardregeln mit der Bezeichnung „Microsoft-Regelpaket“ angezeigt.

```powershell
Get-DlpSensitiveInformationTypeRulePackage
```    
2. Speichern Sie die Regeln Ihrer Organisation in einer Variablen, indem Sie Folgendes eingeben. Durch das Speichern in einer Variablen kann später problemlos auf die Daten in einem Format zugegriffen werden, das sich für Remote-PowerShell-Befehle eignet.

```powershell    
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
```
    
3. Erstellen Sie eine formatierte XML-Datei mit all diesen Daten, indem Sie Folgendes eingeben. (`Set-content` ist der Teil des Cmdlets, das die XML-Daten in die Datei schreibt.) 
    
```powershell
Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
```

> [!IMPORTANT]
> Stellen Sie sicher, dass der Dateispeicherort verwendet wird, in dem das Regelpaket tatsächlich gespeichert ist. `C:\custompath\` ist ein Platzhalter. 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a>Suchen der Regel, die in der XML-Datei geändert werden soll

Mit den vorstehenden Cmdlets wurde die gesamte *Regelsammlung* exportiert, die die Standardregeln umfasst. Anschließend müssen Sie speziell nach der Regel für die Kreditkartennummer suchen, die Sie ändern möchten. 
  
1. Verwenden Sie einen Texteditor, um die im vorherigen Abschnitt exportierte XML-Datei zu öffnen.
    
2. Führen Sie einen Bildlauf bis zum Tag `<Rules>` durch, mit dem der Abschnitt beginnt, der die DLP-Regeln enthält. Da diese XML-Datei die Informationen für die gesamte Regelsammlung enthält, sind am Anfang weitere Informationen enthalten, über die Sie hinweg blättern müssen, um zu den Regeln zu gelangen.
    
3. Suchen Sie nach *Func_credit_card*, um die Regeldefinition für die Kreditkartennummer zu suchen. In der XML-Datei dürfen Regelnamen keine Leerzeichen enthalten, sodass die Leerzeichen üblicherweise durch Unterstriche ersetzt und die Regelnamen manchmal abgekürzt werden. Ein Beispiel hierfür ist die Regel für die US-Sozialversicherungsnummer, die als "SSN" abgekürzt wird. Die XML-Datei der Kreditkartennummer-Regel sollte wie das folgende Codebeispiel aussehen.
    
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

Nachdem Sie die Regeldefinition für die Kreditkartennummer in der XML-Datei ermittelt haben, können Sie die XML-Datei der Regel an Ihre Anforderungen anpassen. Eine Wiederholung zu den XML-Definitionen finden Sie am Ende dieses Themas unter [Glossar](#term-glossary).
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a>Ändern der XML-Datei und Erstellen eines neuen vertraulichen Informationstyps

Zuerst müssen Sie einen neuen vertraulichen Informationstyp erstellen, da Sie die Standardregeln nicht direkt ändern können. Sie können eine Vielzahl von Maßnahmen im Zusammenhang mit benutzerdefinierten vertraulichen Informationstypen ergreifen. Diese werden unter [Erstellen eines benutzerdefinierten vertraulichen Informationstyps in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) beschrieben. In diesem Beispiel machen wir es nicht kompliziert, sondern entfernen nur den bestätigenden Nachweis und fügen der Regel für die Kreditkartennummer Schlüsselwörter hinzu.
  
Alle XML-Regeldefinitionen werden anhand der folgenden allgemeinen Vorlage erstellt. Sie müssen die XML-Definition der Kreditkartennummer in der Vorlage kopieren und einfügen, einige Werte ändern (beachten Sie die Platzhalter ". . ." im folgenden Beispiel) und anschließend die geänderte XML-Datei als neue Regel hochladen, die in Richtlinien verwendet werden kann.
  
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

Sie verfügen nun über eine XML-Datei, die der Folgenden ähnelt. Da Regelpakete und Regeln anhand ihrer eindeutigen GUIDs identifiziert werden, müssen Sie zwei GUIDs generieren: eine für das Regelpaket und eine zum Ersetzen der GUID für die Kreditkartennummer-Regel. Die GUID für die Entitäts-ID im folgenden Codebeispiel ist die für unsere integrierte Regeldefinition, die Sie durch eine neue GUID ersetzen müssen. Es gibt verschiedene Wege zum Generieren von GUIDs. Sie können dies jedoch unkompliziert in PowerShell bewerkstelligen, indem Sie **[guid]::NewGuid()** eingeben. 
  
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

Sie möchten möglicherweise festlegen, dass der bestätigende Nachweis erforderlich ist, aber andere oder zusätzliche Schlüsselwörter angeben. Möglicherweise möchten Sie auch ändern, wo nach diesem Nachweis gesucht werden soll. Sie können das Attribut `patternsProximity` anpassen, um das Fenster für den bestätigenden Nachweis um die 16-stellige Zahl herum zu erweitern oder zu verkleinern. Um Ihre eigenen Schlüsselwörter hinzuzufügen, müssen Sie eine Schlüsselwortliste definieren und in Ihrer Regel darauf verweisen. Mit der folgenden XML-Datei werden die Schlüsselwörter "company card" (Firmenkarte) und "Contoso card" (Contoso-Karte) hinzugefügt, sodass jede Nachricht, die diese Phrasen im Umkreis von 150 Zeichen von einer Kreditkartennummer enthält, als Kreditkartennummer erkannt wird.
  
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
  
1. Speichern Sie sie als XML-Datei mit Unicode-Codierung. Dies ist wichtig, da die Regel nicht funktioniert, wenn die Datei mit einer anderen Codierung gespeichert wird.
    
2. [Herstellen einer Verbindung zum Security and Compliance Center mithilfe von Remote-PowerShell](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. Geben Sie PowerShell Folgendes ein.

```powershell    
New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte).
```
> [!IMPORTANT]
> Stellen Sie sicher, dass der Dateispeicherort verwendet wird, in dem das Regelpaket tatsächlich gespeichert ist. `C:\custompath\` ist ein Platzhalter. 
  
4. Geben Sie zur Bestätigung Y ein, und drücken Sie die **EINGABETASTE**. 
5. Überprüfen Sie, ob Ihre neue Regel hochgeladen wurde, sowie den Anzeigenamen, indem Sie Folgendes eingeben:

```powershell
Get-DlpSensitiveInformationType
```

Sie müssen die Regel einer DLP-Richtlinie hinzufügen, um damit zu beginnen, die Regel zum Erkennen vertraulicher Informationen zu verwenden. Informationen zum Hinzufügen einer Regel zu einer Richtlinie finden Sie unter [Erstellen einer DLP-Richtlinie aus einer Vorlage](create-a-dlp-policy-from-a-template.md).
  
## <a name="term-glossary"></a>Glossar

Nachfolgend finden Sie Definitionen der Begriffe, die in diesem Verfahren vorkommen.
  
|**Begriff**|**Definition**|
|:-----|:-----|
|Entität|Entitäten sind vertrauliche Informationstypen, wie beispielsweise Kreditkartennummern. Jede Entität verfügt über eine eindeutige GUID als ID. Wenn Sie eine GUID kopieren und in der XML-Datei danach suchen, finden Sie die XML-Regeldefinition und alle lokalisierten Übersetzungen dieser XML-Regel. Diese Definition können Sie auch finden, indem Sie die GUID für die Übersetzung ermitteln und dann nach dieser GUID suchen.|
|Funktionen|Die XML-Datei verweist auf `Func_credit_card`, eine Funktion im kompilierten Code. Funktionen dienen zur Ausführung komplexer regulärer Ausdrücke und prüfen, ob Prüfsummen mit den integrierten Regeln übereinstimmen. Da dies im Code geschieht, werden einige der Variablen nicht in der XML-Datei angezeigt.|
|IdMatch|Dies ist die Kennung, die das Muster abgleichen möchte – beispielsweise eine Kreditkartennummer.|
|Schlüsselwortliste|Die XML-Datei verweist außerdem auf `keyword_cc_verification` und `keyword_cc_name`. Dies sind Schlüsselwortlisten, anhand derer nach Übereinstimmungen mit dem Attribut `patternsProximity` für die Entität gesucht wird. Diese werden zurzeit nicht in der XML-Datei angezeigt.|
|Muster|Das Muster enthält die Liste der Informationen, anhand derer der vertrauliche Informationstyp sucht. Hierzu zählen Schlüsselwörter, reguläre Ausdrücke und interne Funktionen, die Aufgaben ausführen, wie beispielsweise die Überprüfung von Prüfsummen. Vertrauliche Informationstypen können mehrere Muster mit eindeutigen Angaben zur Vertrauenswürdigkeit aufweisen. Dies ist nützlich, wenn ein vertraulicher Informationstyp erstellt wird, der eine hohe Vertrauenswürdigkeit zurückgibt, falls ein bestätigender Nachweis gefunden wurde, und der eine niedrige Vertrauenswürdigkeit zurückgibt, wenn nur ein geringer oder gar kein bestätigender Nachweis gefunden wurde.|
|Pattern confidenceLevel|Dies ist die Vertrauensstufe, für die das DLP-Modul eine Übereinstimmung gefunden hat. Diese Vertrauensstufe wird einer Übereinstimmung für das Muster zugeordnet, wenn die Anforderungen des Musters erfüllt sind. Es handelt sich hierbei um das Maß an Vertrauenswürdigkeit, das Sie bei Verwendung von Exchange-E-Mail-Flussregeln (auch als Transportregeln bezeichnet) erwägen sollten.|
|patternsProximity|Wird etwas gefunden, das wie ein Kreditkartennummer-Muster aussieht, handelt es sich bei dem Attribut `patternsProximity` um die Umgebung der Nummer, in der nach einem bestätigenden Nachweis gesucht wird.|
|recommendedConfidence|Dies ist die Vertrauensstufe, die für diese Regel empfohlen wird. Die empfohlene Vertrauensstufe gilt für Entitäten und Affinitäten. Für Entitäten wird diese Zahl niemals anhand des Attributs `confidenceLevel` für das Muster ausgewertet. Es ist lediglich eine Empfehlung, die Ihnen bei der Auswahl einer Vertrauensstufe helfen soll, falls Sie eine solche zuweisen möchten. Für Affinitäten muss das Attribut `confidenceLevel` des Musters höher sein als die Zahl des Attributs `recommendedConfidence` für eine aufzurufende E-Mail-Flussregel-Aktion. Das Attribut `recommendedConfidence` ist die in E-Mail-Flussregeln verwendete Standardvertrauensstufe, die eine Aktion aufruft. Bei Bedarf können Sie stattdessen die aufzurufende E-Mail-Flussregel manuell basierend auf der Vertrauensstufe des Musters ändern.|
   
## <a name="for-more-information"></a>Weitere Informationen

- [Wonach die Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md)
    
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps](create-a-custom-sensitive-information-type.md)
    
- [Übersicht über die Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md)
