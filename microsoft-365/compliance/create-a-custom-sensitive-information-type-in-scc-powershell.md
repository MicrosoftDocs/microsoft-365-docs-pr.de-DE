---
title: Erstellen eines benutzerdefinierten Typs für vertrauliche Informationen in Security & Compliance Center PowerShell
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
ms.openlocfilehash: ec5f61eec3e4f4f94fa955a936db0b245fc772eb
ms.sourcegitcommit: 27a7a373ca77375fdab0690a899135fad16c3cf5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435569"
---
# <a name="create-a-custom-sensitive-information-type-in-security--compliance-center-powershell"></a>Erstellen eines benutzerdefinierten Typs für vertrauliche Informationen in Security & Compliance Center PowerShell

Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) in Office 365 umfasst zahlreiche integrierte [Typen vertraulicher Informationen](what-the-sensitive-information-types-look-for.md), die Sie in DLP-Richtlinien verwenden können. Diese integrierten Typen unterstützen Sie beim Erkennen und Schützen von Kreditkartennummern, Bankkontonummern, Reisepassnummern und mehr. 
  
Wenn Sie jedoch verschiedene Typen vertraulicher Informationen identifizieren und schützen müssen, zum Beispiel eine Mitarbeiter-ID, die ein für Ihre Organisation spezifisches Format verwendet, können Sie einen benutzerdefinierten Typ für vertrauliche Informationen erstellen. Dieser wird in einer XML-Datei definiert, die als *Regelpaket* bezeichnet wird.
  
In diesem Thema wird gezeigt, wie Sie eine XML-Datei erstellen, die Ihren eigenen benutzerdefinierten vertraulichen Informationstyp definiert. Sie müssen wissen, wie Sie einen regulären Ausdruck erstellen. In diesem Thema wird beispielsweise ein benutzerdefinierter vertraulicher Informationstyp erstellt, der eine Mitarbeiter-ID identifiziert. Sie können dieses XML-Beispiel als Ausgangspunkt für Ihre eigene XML-Datei verwenden.
  
Nachdem Sie eine wohlgeformte XML-Datei erstellt haben, können Sie sie mit Office 365 PowerShell in Office 365 hochladen. Sie können dann den benutzerdefinierten vertraulichen Informationstyp in Ihren DLP-Richtlinien verwenden und testen, ob er die vertraulichen Informationen wie beabsichtigt erkennt.

> [!NOTE]
> Sie können auch weniger komplexe benutzerdefinierte Typen für vertrauliche Informationen in der Oberfläche des Security & Compliance Center erstellen. Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Typs für vertrauliche Informationen](create-a-custom-sensitive-information-type.md).

## <a name="important-disclaimer"></a>Wichtiger Haftungsausschluss
<!-- this is worded much better than the previous one is --> Aufgrund der Unterschiede in Kundenumgebungen und Anforderungen an die Inhaltsübereinstimmung kann Microsoft-Support keine Unterstützung bei der Bereitstellung benutzerdefinierter Definitionen für die Inhaltsübereinstimmung leisten – z. B. Definieren von benutzerdefinierten Klassifizierungen oder Mustern für reguläre Ausdrücke (auch als „RegEx“ bezeichnet). Für benutzerdefinierte Entwicklung, Tests und Debugging im Bereich Inhaltsübereinstimmung müssen Office 365-Kunden auf interne IT-Ressourcen zurückgreifen oder eine externe Beratungsressource wie z. B. Microsoft Consulting Services (MCS) nutzen. Supporttechniker können eingeschränkten Support für die Funktion bereitstellen, aber nicht garantieren, dass eine benutzerdefinierte Inhaltsübereinstimmungsentwicklung die Anforderungen oder Verpflichtungen des Kunden erfüllt. Als Beispiel für die Art von möglichem Support können Beispielmuster für reguläre Ausdrücke zu Testzwecken bereitgestellt werden. Außerdem kann der Support bei der Problembehandlung für ein vorhandenes RegEx-Muster, das nicht wie erwartet ausgelöst wird, mit einem einzelnen spezifischen Inhaltsbeispiel helfen.

 Weitere Informationen über die Boost.RegEx-Engine (ehemals RegEx++), die für die Verarbeitung des Textes verwendet wird, finden Sie unter [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).
    
## <a name="sample-xml-of-a-rule-package"></a>Beispiel-XML für ein Regelpaket

Unten sehen Sie die Beispiel-XML für das Regelpaket, das Sie in diesem Thema erstellen. Die Elemente und Attribute werden in den folgenden Abschnitten erläutert.
  
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

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a>Was sind die wichtigsten Anforderungen? [Elemente „Rule“, „Entity“ und „Pattern“]

Bevor Sie beginnen, ist es hilfreich, die grundlegende Struktur des XML-Schemas für eine Regel zu kennen, und wie Sie diese Struktur verwenden können, um den benutzerdefinierten vertraulichen Informationstyp zu definieren, damit die richtigen Inhalte erkannt werden.
  
Eine Regel definiert eine oder mehrere Entitäten (vertrauliche Informationstypen), und jede Entität definiert ein oder mehrere Muster (Patterns). Die DLP such nach einem Muster, wenn sie Inhalte auswertet, wie z. B. E-Mails und Dokumente.   <!-- ok then this is going to be really confusing since the terminology changes.... --> (Ein kurzer Hinweis zur Terminologie: Wenn Sie mit DLP-Richtlinien vertraut sind, wissen Sie, dass eine Richtlinie eine oder mehrere Regeln enthält, die aus Bedingungen und Aktionen bestehen. In diesem Thema verwendet das XML-Markup jedoch den Begriff „Regel“, um Muster zu bezeichnen, die eine Entität definieren, die auch als Typ vertraulicher Informationen bezeichnet wird. Wenn Sie in diesem Thema als den Begriff „Regel“ sehen, denken Sie an eine Entität oder einen Typ vertraulicher Informationen, und nicht an Bedingungen und Aktionen.)
  
### <a name="simplest-scenario-entity-with-one-pattern"></a>Einfachstes Szenario: Entität mit einem Muster

Hier sehen Sie das das einfachste Szenario. Sie möchten, dass Ihre DLP-Richtlinie Inhalt identifiziert, der die Mitarbeiter-ID Ihrer Organisation enthält. Diese ist als neunstellige Zahl formatiert. Das Muster bezieht sich also auf einen regulären Ausdruck, der in der Regel enthalten ist, die neunstellige Zahlen erkennt. Jeder Inhalt, der eine neunstellige Zahl beinhaltet, entspricht dem Muster.
  
![Diagramm einer Entität mit einem Muster](media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
Obwohl dieses Muster einfach ist, führt möglicherweise jedoch zu einer Menge falsch positiver Ergebnisse, indem es Inhalte mit einer neunstelligen Zahl erkennt, die nicht unbedingt eine Mitarbeiter-ID ist.
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a>Häufigeres Szenario: Entität mit mehreren Mustern

Aus diesem Grund wird eine Entität in der Regel mit mehr als einem Muster definiert, wobei die Muster unterstützende Hinweise (z. B. ein Schlüsselwort oder Datum) zusätzlich zur Entität (z. B. die neunstellige Zahl) identifizieren.
  
Um zum Beispiel die Wahrscheinlichkeit zu erhöhen, Inhalt zu erkennen, der eine Mitarbeiter-ID enthält, können Sie ein anderes Muster definieren, das z. B. auch ein Einstellungsdatum identifiziert. Sie können noch ein weiteres Muster definieren, das sowohl ein Einstellungsdatum als auch ein Stichwort (z. B. „Mitarbeiter-ID“) zusätzlich zur neunstelligen Zahl identifiziert.
  
![Diagramm einer Entität mit mehreren Mustern](media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
Beachten Sie einige wichtige Aspekte dieser Struktur:
  
- Muster, die mehr Nachweise erfordern, weisen ein höheres Konfidenzniveau auf. Dies ist nützlich, denn wenn Sie später diesen vertraulichen Informationstyp in einer DLP-Richtlinie verwenden, können Sie restriktivere Aktionen (z. B. Inhalt blockieren) nur für Übereinstimmungen mit höherem Konfidenzniveau und weniger restriktive Aktionen (z. B. Benachrichtigung senden) für Übereinstimmungen mit geringerem Konfidenzniveau verwenden.
    
- Die unterstützenden Elemente "IdMatch" und "Match" verweisen auf reguläre Ausdrücke und Schlüsselwörter, die tatsächlich untergeordnete Elemente des Elements "Rule" und nicht des Elements "Pattern" sind. Auf diese unterstützenden Elemente wird von "Pattern" Bezug genommen, sie sind aber in "Rule" enthalten. Das bedeutet, dass auf eine einzelne Definition eines unterstützenden Elements, z. B. einen regulären Ausdruck oder eine Schlüsselwortliste, von mehreren Entitäten und Mustern Bezug genommen werden kann.
    
## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a>Welche Entität muss erkannt werden? [Element "Entity", Attribut "id"]

Eine Entität ist ein vertraulicher Informationstyp (z. B. eine Kreditkartennummer), der ein klar definiertes Muster aufweist. Jede Entität hat eine eindeutige GUID als ID.
  
### <a name="name-the-entity-and-generate-its-guid"></a>Benennen der Entität und Generieren der GUID
<!-- why isn't the following in procedure format? --> Fügen Sie die Regel- und Entitätselemente hinzu. Fügen Sie dann einen Kommentar hinzu, der den Namen der benutzerdefinierten Entität enthält – in diesem Beispiel „Employee ID“. Später fügen Sie den Entitätsnamen zum Abschnitt mit den lokalisierten Zeichenfolgen hinzu, und dieser Name wird beim Erstellen einer DLP-Richtlinie in der Benutzeroberfläche angezeigt.
  
Als Nächstes generieren Sie eine GUID für die Entität. Es gibt mehrere Methoden zum Generieren von GUIDs, aber Sie können dies ganz einfach in PowerShell durch die Eingabe von „[guid]::NewGuid()“ durchführen. Später fügen Sie die Entitäts-GUID ebenfalls zum Abschnitt mit en lokalisierten Zeichenfolgen hinzu.
  
![XML-Markup mit Regel- und Entitätselementen](media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a>Welches Muster möchten Sie abgleichen? [Muster-Element, IdMatch-Element, Regex-Element]

Das Muster enthält die Liste der Dinge, nach denen der vertrauliche Informationstyp sucht. Dies kann reguläre Ausdrücke, Stichwörter und integrierte Funktionen (die Aufgaben wie das Ausführen von regulären Ausdrücken zum Suchen nach Datumsangaben oder Adressen ausführen) umfassen. Vertrauliche Informationstypen können mehrere Muster mit eindeutigen Zuverlässigkeitsgraden aufweisen.
  
Allen der folgenden Muster ist gemeinsam, dass sie sich alle auf denselben regulären Ausdruck beziehen, der nach einer neunstelligen Zahl sucht (\d{9}), die von Leerzeichen eingeschlossen ist (\s) ... (\s). Das Element "IdMatch" verweist auf diesen regulären Ausdruck, und er ist die allgemeine Anforderung für alle Muster, die nach der Mitarbeiter-ID-Entität suchen. „IdMatch“ ist der Bezeichner, für den das Muster eine Entsprechung sucht, wie z. B. die Mitarbeiter-ID, Kreditkartennummer oder Sozialversicherungsnummern. Ein Pattern-Element muss genau ein IdMatch-Element haben.
  
![XML-Markup mit mehreren Pattern-Elementen, die auf ein einzelnes Regex-Element verweisen](media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
Wenn eine Übereinstimmung gefunden wurde, gibt ein Muster eine Anzahl und einen Zuverlässigkeitsgrad zurück, die Sie in den Bedingungen Ihrer DLP-Richtlinie verwenden können. Wenn Sie eine Bedingung zum Erkennen eines Typs vertraulicher Informationen zu einer DLP-Richtlinie hinzufügen, können Sie die Anzahl und den Zuverlässigkeitsgrad wie hier gezeigt bearbeiten. Der Zuverlässigkeitsgrad (auch als „Übereinstimmungsgenauigkeit“ bezeichnet) wird weiter unten in diesem Thema erläutert.
  
![Instanzenanzahl und Optionen für die Übereinstimmungsgenauigkeit](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
Beim Erstellen des regulären Ausdrucks müssen Sie berücksichtigen, dass es potenzielle Probleme geben kann. Wenn Sie z. B. einen regulären Ausdruck schreiben und hochladen, der zu viel Inhalt erkennt, kann dies die Leistung beeinträchtigen. Weitere Informationen zu diesen potenziellen Problemen finden Sie im Abschnitt [Mögliche Überprüfungsprobleme, die Sie beachten müssen](#potential-validation-issues-to-be-aware-of).
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a>Sollen weitere Nachweise erforderlich sein? [Element "Match", Attribut "minCount"]

Zusätzlich zu "IdMatch" kann in einem Muster das Element "Match" verwendet werden, um zusätzliche unterstützende Nachweise anzufordern, z. B. ein Schlüsselwort, einen regulären Ausdruck, ein Datum oder eine Adresse.
  
Ein Muster kann mehrere "Match"-Elemente umfassen, die direkt im Element "Pattern" enthalten sein oder mithilfe des Elements "Any" kombiniert werden können. "Match"-Elemente werden mit einem impliziten AND-Operator verknüpft. Es müssen alle "Match"-Elemente erfüllt sein, damit eine Übereinstimmung mit dem Muster erkannt wird. Sie können das Element "Any" zum Einführen von AND- oder OR-Operatoren verwenden (weitere Informationen dazu sind in einem späteren Abschnitt enthalten).
  
Sie können das optionale minCount-Attribut verwenden, um anzugeben, wie viele Instanzen einer Übereinstimmung für jedes der Match-Elemente gefunden werden müssen. Sie können z. B. angeben, dass eine Übereinstimmung mit einem Muster nur dann vorliegt, wenn mindestens zwei Stichwörter aus einer Stichwortliste gefunden werden.
  
![XML-Markup mit Match-Element und minOccurs-Attribut](media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a>Stichwörter [Elemente „Keyword“, „Group“ und „Term“, matchStyle- und caseSensitive-Attribute]

Wenn Sie vertrauliche Informationen identifizieren möchten, wie z. B. eine Mitarbeiter-ID, dann sollen häufig Stichwörter als bestätigende Nachweise erforderlich sein. Möglicherweise möchten Sie beispielsweise zusätzlich zur Übereinstimmung mit einer neunstelligen Zahl auch nach Wörtern wie „Karte“, „Ausweis“ oder „ID“ suchen. Hierzu verwenden Sie das Keyword-Element. Das Keyword-Element verfügt über das Attribut „id“, auf das sich mehrere Match-Elemente in mehreren Mustern oder Entitäten beziehen können.
  
Stichwörter werden als eine Liste von Term-Elementen in ein Group-Element eingeschlossen. Das Group-Element verfügt über ein matchStyle-Attribut mit zwei möglichen Werten:
  
- **matchStyle = "word"** Der Wortabgleich identifiziert ganze Wörter, die von Leerzeichen oder anderen Trennzeichen umgeben sind. Sie sollten immer „word“ verwenden, es sei denn, Sie müssen nach Übereinstimmungen mit Teilen von Wörtern oder Wörtern in asiatischen Sprachen suchen. 
    
- **matchStyle = "string"** Der Zeichenfolgenabgleich identifiziert Zeichenfolgen unabhängig davon, von welchen Zeichen sie umgeben sind. So erkennt „id“ zum Beispiel auch „bid“ und „idea“. Verwenden Sie „string“ nur, wenn Sie Übereinstimmungen mit asiatischen Wörtern suchen oder wenn das Stichwort als Teil anderer Zeichenfolgen enthalten sein kann. 
    
Sie können auch das caseSensitive-Attribut des Term-Elements verwenden, um festzulegen, dass der Inhalt genau mit dem Stichwort übereinstimmen muss, einschließlich Groß- und Kleinschreibung.
  
![XML-Markup mit Match-Elementen, die auf Stichwörter verweisen](media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a>Reguläre Ausdrücke [Element „Regex“]

In diesem Beispiel verwendet die Entität „Employee ID“ bereits das IdMatch-Element, um auf einen regulären Ausdruck für das Muster zu verweisen – eine neunstellige Zahl, die von Leerzeichen umgeben ist. Darüber hinaus kann ein Muster ein Match-Element verwenden, um ein zusätzliches Regex-Element zum Identifizieren von bestätigenden Nachweisen, z. B. einer fünf- oder neunstellige Zahl im Format einer US-Postleitzahl, zu verwenden.
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a>Zusätzliche Muster wie Datumsangaben oder Adressen [integrierte Funktionen]

Zusätzlich zu den integrierten Typen für vertrauliche Informationen umfasst DLP auch integrierte Funktionen, mit denen bestätigende Nachweise wie ein US-Datum, ein EU-Datum, ein Ablaufdatum oder eine US-Adresse identifiziert werden können. DLP bietet keine Unterstützung für das Hochladen eigener benutzerdefinierter Funktionen. Wenn Sie jedoch einen benutzerdefinierten Typ für vertrauliche Informationen erstellen, kann die Entität auf die integrierten Funktionen verweisen.
  
Beispielsweise steht auf einem Mitarbeiterausweis außer der Mitarbeiter-ID auch ein Einstellungsdatum, sodass diese benutzerdefinierte Entität die integrierte Funktion `Func_us_date` verwenden kann, um ein Datum im US-typischen Format zu identifizieren. 
  
Weitere Informationen finden Sie unter [Wonach die DLP-Funktionen suchen](what-the-dlp-functions-look-for.md).
  
![XML-Markup mit Match-Element, das auf eine integrierte Funktion verweist](media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a>Verschiedene Kombinationen von Nachweisen [Element „Any“, minMatches- und maxMatches-Attribute]

In einem Pattern-Element werden alle IdMatch- und Match-Elemente durch einen impliziten AND-Operator verknüpft – es müssen alle Übereinstimmungen gegeben sein, bevor das Muster als erfüllt betrachtet wird. Sie können jedoch mithilfe des Elements „Any“ eine flexiblere Übereinstimmungslogik erstellen, um Match-Elemente zu gruppieren. Sie können das Any-Element beispielsweise verwenden, um alle, keine oder eine genaue Teilmenge der untergeordneten Match-Elemente abzugleichen.
  
Das Any-Element hat optionale minMatches- und maxMatches-Attribute, die Sie verwenden können, um zu definieren, wie viele der untergeordneten Match-Elemente erfüllt sein müssen, bevor das Muster als übereinstimmend angesehen wird. Beachten Sie, dass diese Attribute die Anzahl der Match-Elemente definiert, die erfüllt sein müssen, nicht die Anzahl der Instanzen gefundener Nachweise für die Übereinstimmungen. Zum Definieren einer Mindestanzahl von Instanzen für eine bestimmte Übereinstimmung, z. B. zwei Stichwörter aus einer Liste, verwenden Sie das minCount-Attribut für ein Match-Element (siehe oben).
  
### <a name="match-at-least-one-child-match-element"></a>Übereinstimmung mit mindestens einem untergeordneten "Match"-Element

Wenn Sie möchten, dass nur eine Mindestanzahl von Match-Elementen erfüllt sein muss, können Sie das minMatches-Attribut verwenden. Diese Match-Elemente werden eigentlich durch einen impliziten OR-Operator verknüpft. Dieses Any-Element wird erfüllt, wenn ein US-formatiertes Datum oder ein Stichwort aus einer Liste gefunden wird.

```
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
    
### <a name="match-an-exact-subset-of-any-children-match-elements"></a>Übereinstimmung mit einer genauen Untermenge beliebiger untergeordneter Match-Elemente

Wenn Sie möchten, dass eine genaue Anzahl von Match-Elementen gefunden werden soll, können Sie für „minMatches“ und „maxMatches“ den gleichen Wert festlegen. Dieses Any-Element ist nur dann erfüllt, wenn genau ein Datum oder Stichwort gefunden wird. Wenn mehr gefunden werden, gilt das Muster als nicht übereinstimmend.

```
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
  
### <a name="match-none-of-children-match-elements"></a>Übereinstimmung für keine untergeordneten Match-Elemente

Wenn Sie festlegen möchten, dass ein bestimmter Nachweis nicht vorhanden sein darf, damit die Übereinstimmung mit einem Muster gegeben ist, können Sie sowohl „minMatches“ als auch „maxMatches“ auf 0 festlegen. Dies kann hilfreich sein, wenn Sie eine Stichwortliste oder andere Nachweise haben, die wahrscheinlich zu einem falsch positiven Ergebnis führen.
  
Die Entität „Employee ID“ such zum Beispiel nach dem Stichwort „Card“, da es sich auf eine „ID Card“ beziehen kann. Wenn „card“ jedoch nur im Ausdruck „credit card“ vorkommt, bedeutet „card“ in diesem Inhalt wahrscheinlich nicht „ID card“. Sie können also „credit card“ als Stichwort zu einer Liste mit Begriffen hinzufügen, die Sie von der Übereinstimmung mit dem Muster ausschließen möchten.
  
```
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a>Übereinstimmung mit einer Reihe eindeutiger Begriffe

Wenn Entsprechungen für eine Reihe eindeutiger Begriffe gefunden werden sollen, verwenden Sie den *uniqueResults*-Parameter und legen Sie ihn wie im folgenden Beispiel auf *true* fest:

```
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

In diesem Beispiel ist ein Muster für die Gehaltsrevision mit mindestens drei eindeutigen Übereinstimmungen definiert. 
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a>Wie nah an der Entität muss der andere Nachweis sein? [patternsProximity-Attribut]

Der Typ für vertrauliche Informationen sucht nach einem Muster, das eine Mitarbeiter-ID darstellt, und als Teil dieses Musters sucht er auch nach bestätigenden Nachweisen, wie z. B. dem Stichwort „ID“. Daraus folgt: Je näher dieser Nachweis bei der Entität liegt, desto wahrscheinlicher ist das Muster eine tatsächliche Mitarbeiter-ID. Sie können festlegen, wie nah andere Nachweise bei der Entität im Muster liegen müssen, indem Sie das erforderliche patternsProximity-Attribut des Entity-Elements verwenden.
  
![XML-Markup mit patternsProximity-Attribut](media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
Der patternsProximity-Attributwert definiert für jedes Muster in der Entität den Abstand (in Unicode-Zeichen) von der IdMatch-Position für alle anderen Übereinstimmungen, die für dieses Muster angegeben wurden. Das Näherungsfenster wird von der IdMatch-Position verankert, wobei das Fenster links und rechts von „IdMatch“ erweitert wird.
  
![Diagramm des Näherungsfensters](media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
Im nachstehenden Beispiel wird gezeigt, in welcher Weise das Näherungsfenster den Musterabgleich beeinflusst, wobei das IdMatch-Element für die benutzerdefinierte Employee ID-Entität mindestens eine bestätigende Übereinstimmung von Stichwort oder Datum erfordert. Aufgrund von ID2 und ID3 gibt es nur eine Übereinstimmung für ID1, und im Näherungsfenster wird kein oder nur ein teilweise bestätigender Nachweis gefunden.
  
![Diagramm von bestätigenden Nachweisen und Näherungsfenster](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
Beachten Sie, dass bei E-Mails der Text und jede Anlage als separate Elemente behandelt werden. Dies bedeutet, dass sich das Näherungsfenster nicht über das Ende des jeweiligen Elements erstreckt. Für jedes Element (Anlage oder Text) muss sowohl idMatch als auch der bestätigende Nachweise vorhanden sein.
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a>Welches sind die richtigen Konfidenzniveaus für verschiedene Muster? [Attribut "confidenceLevel", Attribut "recommendedConfidence"]

Je mehr Nachweise für ein Muster erforderlich sind, desto höher ist der Zuverlässigkeitsgrad, dass eine tatsächliche Entität (z. B. Mitarbeiter-ID) beim Abgleich des Musters identifiziert wurde. So ist die Zuverlässigkeit beispielsweise größer bei einem Muster, für das eine neunstellige ID, das Einstellungsdatum und ein Stichwort in nächster Nähe erforderlich sind, als bei einem Muster, das nur eine neue neunstellige ID erfordert.
  
Das Pattern-Element hat ein erforderliches confidenceLevel-Attribut. Sie können sich den Wert für „confidenceLevel“ (eine ganze Zahl zwischen 1 und 100) als eine eindeutige ID für jedes Muster in einer Entität vorstellen – Sie müssen den Mustern in einer Entität unterschiedlichen Zuverlässigkeitsgrade zuweisen. Der genaue Wert der ganzen Zahl spielt keine Rolle – wählen Sie einfach Zahlen aus, die Ihrem Complianceteam sinnvoll erscheinen. Nachdem Sie den benutzerdefinierten Typ für vertrauliche Informationen hochgeladen und anschließend eine DLP-Richtlinie erstellt haben, können Sie in den Bedingungen der von Ihnen erstellten Regeln auf diese Zuverlässigkeitsgrade verweisen.
  
![XML-Markup mit Pattern-Elementen und verschiedenen Werten für das confidenceLevel-Attribut](media/301e0ba1-2deb-4add-977b-f6e9e18fba8b.png)
  
Zusätzlich zum confidenceLevel-Attribut für jedes Muster hat die Entität ein recommendedConfidence-Attribut. Das recommendedConfidence-Attribut kann als Standardzuverlässigkeitsgrad für die Regel angesehen werden. Wenn Sie beim Erstellen einer Regel in einer DLP-Richtlinie keinen Zuverlässigkeitsgrad angeben, nimmt die Regel die Übereinstimmung basierend auf dem empfohlenen Zuverlässigkeitsgrad für die Entität vor.
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-security-amp-compliance-center-localizedstrings-element"></a>Möchten Sie in der Benutzeroberfläche von Security &amp; Compliance Center andere Sprachen unterstützehn? [Element „LocalizedStrings“]

Wenn Ihr Complianceteam Office 365 Security &amp; Compliance Center zum Erstellen von DLP-Richtlinien in verschiedenen Gebietsschemas und in verschiedenen Sprachen verwendet, können Sie lokalisierte Versionen des Namens und der Beschreibung Ihres benutzerdefinierten Typs für vertrauliche Informationen bereitstellen. Wenn Ihr Complianceteam Office 365 in einer anderen, von Ihnen unterstützten Sprache verwendet, wird der lokalisierte Name in der Benutzeroberfläche angezeigt.
  
![Instanzenanzahl und Optionen für die Übereinstimmungsgenauigkeit](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
Das Rules-Element muss ein LocalizedStrings-Element enthalten, das ein Resource-Element enthält, das auf die GUID Ihrer benutzerdefinierten Entität verweist. Jedes Resource-Element enthält wiederum ein oder mehrere Name-Elemente und Description-Elemente, die jeweils das langcode-Attribut verwenden, um eine lokalisierte Zeichenfolge für eine bestimmte Sprache bereitzustellen.
  
![XML-Markup mit Inhalt des LocalizedStrings-Elements](media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
Beachten Sie, dass Sie lokalisierte Zeichenfolgen nur für die Anzeige Ihres benutzerdefinierten Typs für vertrauliche Informationen in der Benutzeroberfläche von Security &amp; Compliance Center verwenden. Sie können keine lokalisierte Zeichenfolgen verwenden, um verschiedene lokalisierte Versionen einer Stichwortliste oder eines regulären Ausdrucks bereitzustellen.
  
## <a name="other-rule-package-markup-rulepack-guid"></a>Sonstige Regelpaket-Markups [RulePack-GUID]

Der Anfang jedes Regelpakets enthält einige allgemeine Informationen, die Sie ausfüllen müssen. Sie können das folgende Markup als Vorlage verwenden und die Platzhalter ". . ." durch eigene Informationen ersetzen.
  
Am wichtigsten ist Folgendes: Sie müssen eine GUID für das RulePack generieren. Weiter oben haben Sie eine GUID für die Entität generiert. Dies ist eine zweite GUID für das RulePack. Es gibt mehrere Methoden zum Generieren von GUIDs, aber Sie können dies ganz einfach in PowerShell durch Eingabe von „[guid]::NewGuid()“ durchführen.
  
Das Version-Element ist ebenfalls wichtig. Wenn Sie das Regelpaket zum ersten Mal hochladen, merkt sich Office 365 die Versionsnummer. Wenn Sie das Regelpaket später aktualisieren und eine neue Version hochladen, stellen Sie sicher, dass Sie die Versionsnummer aktualisieren, da Office 365 das Regelpaket sonst nicht bereitstellt.
  
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

Wenn es fertig ist, sollte das RulePack-Element wie folgt aussehen.
  
![XML-Markup mit dem RulePack-Element](media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)
  
## <a name="changes-for-exchange-online"></a>Änderungen für Exchange Online

Sie haben bisher möglicherweise Exchange Online PowerShell verwendet, um Ihre benutzerdefinierten Typen für vertrauliche Informationen für DLP zu importieren. Nun können Ihre benutzerdefinierten vertraulichen Informationstypen sowohl im Exchange Admin Center als auch im Security &amp; Compliance Center verwendet werden. Als Teil dieser Verbesserung sollten Sie die Security &amp; Compliance Center-PowerShell verwenden, um Ihre benutzerdefinierten vertraulichen Informationstypen zu importieren. Sie können sie nicht mehr aus Exchange PowerShell importieren. Ihre benutzerdefinierten vertraulichen Informationstypen funktionieren weiterhin wie zuvor, es kann jedoch bis zu einer Stunde dauern, bis Änderungen, die Sie im Security &amp; Compliance Center an benutzerdefinierten vertraulichen Informationstypen vorgenommen haben, im Exchange Admin Center angezeigt werden.
  
Beachten Sie, dass Sie im Security &amp;Compliance Center das  Cmdlet **[New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpsensitiveinformationtyperulepackage?view=exchange-ps)** verwenden müssen, um ein Regelpaket hochzuladen. Im Exchange Admin Center wurde früher das Cmdlet **ClassificationRuleCollection** verwendet. 
  
## <a name="upload-your-rule-package"></a>Hochladen des Regelpakets

Gehen Sie zum Hochladen des Regelpakets wie folgt vor:
  
1. Speichern Sie es als XML-Datei mit Unicode-Codierung.
    
2. [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=799771)
    
3. Verwenden Sie die folgende Syntax:

    ```powershell
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte)
    ```

    Dieses Beispiel lädt die Unicode-XML-Datei mit dem Namen „MyNewRulePack.xml“ aus C:\Dokumente“ hoch.

    ```powershell
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte)
    ```

    Ausführliche Informationen zur Syntax und zu den Parametern finden Sie unter [New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpsensitiveinformationtyperulepackage).

5. Um sicherzustellen, dass Sie einen neuen Typ für vertrauliche Informationen erstellt haben, führen Sie einen der folgenden Schritte aus:

  - Führen Sie das Cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) aus, um zu überprüfen, ob das neue Regelpaket aufgeführt wird:

    ```
    Get-DlpSensitiveInformationTypeRulePackage
    ``` 

  - Führen Sie das Cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) aus, um zu überprüfen, ob der Typ für vertrauliche Informationen aufgeführt wird:

    ```
    Get-DlpSensitiveInformationType
    ``` 

    Bei benutzerdefinierten Typen für vertrauliche Informationen ist der Publisher-Eigenschaftswert ein anderer als „Microsoft Corporation“.

  - Ersetzen Sie \<Name\> durch den Namenswert des Typs für vertrauliche Informationen (z. B. die Mitarbeiter-ID), und führen Sie das Cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) aus:

    ```powershell
    Get-DlpSensitiveInformationType -Identity "<Name>"
    ```
    
## <a name="potential-validation-issues-to-be-aware-of"></a>Mögliche Überprüfungsprobleme, die Sie beachten müssen

Wenn Sie die XML-Datei des Regelpakets hochladen, überprüft das System den XML-Code und sucht nach bekannten fehlerhaften Mustern und offensichtlichen Leistungsproblemen. Hier sind einige bekannte Probleme aufgeführt, auf die eine Überprüfung erfolgt – ein regulärer Ausdruck:
  
- Darf nicht mit einem Alternator „|“ beginnen, das allem entspricht, da es als leere Übereinstimmung angesehen wird.
    
    Beispiel: „|a“ oder „|b“ besteht die Überprüfung nicht.
    
- Darf nicht mit einem „. {0, m}“-Muster beginnen oder enden, da dies keine Funktion hat und nur die Leistung beeinträchtigt.
    
    Beispiel: „.{0,50}ASDF“ oder „ASDF.{0,50}“ besteht die Überprüfung nicht.
    
- Darf „.{0,m}“ oder „.{1,m}“ nicht in Gruppen haben, und darf nicht „.\*“ oder „.+“ in Gruppen haben.
    
    Beispiel: „(.{0,50000})“ besteht die Überprüfung nicht.
    
- Darf keine Zeichen mit den Wiederholern „{0,m}“ oder „{1,m}“ haben.
    
    Beispiel: „(a\*)“ besteht die Überprüfung nicht.
    
- Darf nicht mit „.{1,m}“ beginnen oder enden; verwenden Sie stattdessen „.“
    
    Beispiel: „.{1,m}asdf“ besteht die Überprüfung nicht; verwenden Sie stattdessen „.asdf“.
    
- Darf keinen unbegrenzten Wiederholer in einer Grupe haben (wie z. B. „\*“ oder „+“).
    
    Beispiel: „(xx)\*“ und „(xx)+“ bestehen die Überprüfung nicht.
    
Wenn ein benutzerdefinierter Typ für vertrauliche Informationen ein Problem enthält, das die Leistung beeinträchtigen könnte, wird er nicht hochgeladen, und es wird möglicherweise eine der folgenden Fehlermeldungen angezeigt:
  
- **Generische Mengenangaben, die mit mehr Inhalten übereinstimmen als erwartet (z. B. „+“, „\*“)**
    
- **Lookaround-Assertionen**
    
- **Komplexe Gruppieren in Verbindung mit allgemeinen Mengenangaben**
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a>Neues Durchforsten des Inhalts, um die Typen für vertrauliche Informationen zu identifizieren

DLP verwendet den Suchcrawler zum Identifizieren und Klassifizieren von vertraulichen Informationen in Websiteinhalten. Inhalte in SharePoint Online- und OneDrive for Business-Websites werden bei jeder Aktualisierung automatisch erneut durchforstet. Damit der neue benutzerdefinierte Typ für vertrauliche Informationen im gesamten vorhandenen Inhalt identifiziert werden kann, muss der Inhalt erneut durchforstet werden.
  
In Office 365 können Sie das erneute Durchforsten des gesamten Mandanten nicht manuell anfordern, für eine Websitesammlung, Liste oder Bibliothek ist dies jedoch möglich. Weitere Informationen finden Sie unter [Manuelles Durchforsten und erneutes Indizieren einer Website, einer Bibliothek oder Liste](https://docs.microsoft.com/sharepoint/crawl-site-content).
  
## <a name="remove-a-custom-sensitive-information-type"></a>Entfernen eines benutzerdefinierten Typs für vertrauliche Informationen

> [!NOTE]
> Bevor Sie einen benutzerdefinierten Typ für vertrauliche Informationen entfernen, überprüfen Sie, dass keine DLP-Richtlinien oder Exchange-Nachrichtenflussregeln (auch bezeichnet als Transportregeln) mehr auf den Typ vertraulicher Informationen verweisen.

In Security & Compliance Center PowerShell gibt es zwei Methoden zum Entfernen eines benutzerdefinierten Typs für vertrauliche Informationen:

- **Entfernen einzelner benutzerdefinierten Typen für vertrauliche Informationen**: Verwenden Sie die unter [Ändern eines benutzerdefinierten Typs für vertrauliche Informationen](#modify-a-custom-sensitive-information-type) aufgeführte Methode. Sie exportieren das benutzerdefinierte Regelpaket, das den benutzerdefinierten Typ für vertrauliche Informationen enthält, entfernen den Typ für vertrauliche Informationen aus der XML-Datei und importieren die aktualisierte XML-Datei wieder in das vorhandene benutzerdefinierte Regelpaket.

- **Entfernen eines benutzerdefinierten Regelpakets und aller benutzerdefinierten Typen für vertrauliche Informationen, die darin enthalten sind**: Diese Methode ist in diesem Abschnitt aufgeführt.

1. [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=799771)

2. Wenn Sie ein benutzerdefiniertes Regelpaket entfernen möchten, verwenden Sie das Cmdlet [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/remove-dlpsensitiveinformationtyperulepackage?view=exchange-ps):

    ```
    Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
    ```

    Sie können den Wert „Name“ (für jede Sprache) oder den Wert `RulePack id` (GUID) verwenden, um das Regelpaket zu identifizieren.

    In diesem Beispiel wird das Regelpaket mit dem Namen „Employee ID Custom Rule Pack“ entfernt.

    ```
       Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
    ```

    Ausführliche Informationen zur Syntax und den Parametern finden Sie unter [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/remove-dlpsensitiveinformationtyperulepackage).

3. Um sicherzustellen, dass Sie einen benutzerdefinierten Typen für vertrauliche Informationen erfolgreich entfernt haben, führen Sie einen der folgenden Schritte aus:

  - Führen Sie das Cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) aus und vergewissern Sie sich, dass das Regelpaket nicht mehr aufgeführt wird:

    ```
    Get-DlpSensitiveInformationTypeRulePackage
    ``` 

  - Führen Sie das Cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) aus und stellen Sie sicher, dass die Typen für vertrauliche Informationen im entfernten Regelpaket nicht mehr aufgeführt werden:

    ```
    Get-DlpSensitiveInformationType
    ``` 

    Bei benutzerdefinierten Typen für vertrauliche Informationen ist der Publisher-Eigenschaftswert ein anderer als „Microsoft Corporation“.

  - Ersetzen Sie \<Name\> durch den Namenswert des Typs für vertrauliche Informationen (z. B. die Mitarbeiter-ID), und führen Sie das Cmdlet [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) aus, um sicherzustellen, dass der Typ für vertrauliche Informationen nicht mehr aufgeführt wird:

    ```
    Get-DlpSensitiveInformationType -Identity "<Name>"
    ```

## <a name="modify-a-custom-sensitive-information-type"></a>Ändern eines benutzerdefinierten Typs für vertrauliche Informationen

In Security & Compliance Center PowerShell müssen Sie zum Ändern eines Typs für vertrauliche Informationen wie folgt vorgehen:

1. Exportieren Sie das vorhandene Regelpaket, das den benutzerdefinierten Typ für vertrauliche Informationen enthält, in eine XML-Datei (oder verwenden Sie die vorhandene XML-Datei, wenn Sie darüber verfügen). 

2. Ändern Sie den benutzerdefinierten Typ für vertrauliche Informationen in der exportierten XML-Datei.

3. Importieren Sie die aktualisierte XML-Datei wieder in das vorhandene Regelpaket.

Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=799771).

#### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>Schritt 1: Exportieren des vorhandenen Regelpakets in eine XML-Datei

> [!NOTE]
> Wenn Sie eine Kopie der XML-Datei haben (z. B. eine soeben erstellte und importierte Datei), können Sie mit dem nächsten Schritt fortfahren, in dem Sie die XML-Datei ändern.

1. Sollten Sie ihn noch nicht kennen, führen Sie das Cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) aus, um den Namen des benutzerdefinierten Regelpakets zu ermitteln:

    ```
    Get-DlpSensitiveInformationTypeRulePackage
    ```

    **Hinweis**: Das integrierte Regelpaket, das die integrierten Typen für vertrauliche Informationen enthält, heißt „Microsoft Regelpaket“. Das Regelpaket, das die benutzerdefinierten Typen für vertrauliche Informationen enthält, die Sie in der Security & Compliance Center-Benutzeroberfläche erstellt haben, heißt „Microsoft.SCCManaged.CustomRulePack“.

2. Verwenden Sie das Cmdlet [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps), um das benutzerdefinierte Regelpaket in einer Variablen zu speichern:

    ```
    $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
    ```

   Wenn der Name für das Regelpaket beispielsweise „Employee ID Custom Rule Pack“ lautet, führen Sie das folgende Cmdlet aus:

    ```
    $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
    ```

3. Verwenden Sie das Cmdlet [Set-Content](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6) zum Exportieren des benutzerdefinierten Regelpakets in eine XML-Datei:

    ```
    Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
    ```

    In diesem Beispiel wird das Regelpaket in die Datei mit dem Namen „ExportedRulePackage.xml“ im Ordner „C:\Dokumente“ exportiert.

    ```
    Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
    ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>Schritt 2: Ändern Sie den benutzerdefinierten Typ für vertrauliche Informationen in der exportierten XML-Datei.

Typen für vertrauliche Informationen in der XML-Datei und andere Elemente in der Datei werden weiter oben in diesem Thema beschrieben.

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>Schritt 3: Importieren Sie die aktualisierte XML-Datei wieder in das vorhandene Regelpaket.

Verwenden Sie das Cmdlet [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpsensitiveinformationtyperulepackage?view=exchange-ps), um die aktualisierte XML-Datei wieder in das vorhandene Regelpaket zu importieren:

```
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

Ausführliche Informationen zur Syntax und zu den Parametern finden Sie unter [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpsensitiveinformationtyperulepackage).

## <a name="reference-rule-package-xml-schema-definition"></a>Referenz: XML-Schemadefinition für Regelpaket

Sie können dieses Markup kopieren, als eine XSD-Datei speichern und diese zum Überprüfen der XML-Datei für das Regelpaket verwenden.
  
```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="http://schemas.microsoft.com/office/2011/mce"
           targetNamespace="http://schemas.microsoft.com/office/2011/mce" 
           xmlns:xs="http://www.w3.org/2001/XMLSchema"
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

## <a name="more-information"></a>Weitere Informationen

- [Übersicht über die Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md)
    
- [Wonach die Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md)
    
- [Wonach die DLP-Funktionen suchen](what-the-dlp-functions-look-for.md)
    

