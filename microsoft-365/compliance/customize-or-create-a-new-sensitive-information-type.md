---
title: Anpassen oder Erstellen eines neuen vertraulichen Informationstyps
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Informationen zum Ändern oder Erstellen eines neuen vertraulichen Informationstyps in Office 365 für DSGVO.
ms.openlocfilehash: 006a3e7be35000513053321ebb500cbd627e8779
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595482"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a>Anpassen oder Erstellen eines neuen vertraulichen Informationstyps

Dieser Artikel enthält drei Beispiele, anhand derer gezeigt wird, wie neue vertrauliche Informationstypen in Office 365 für die DSGVO erstellt bzw. geändert werden können.

- Ändern eines vorhandenen vertraulichen Informationstyps – EU-Debitkartennummer

- Erstellen eines neuen vertraulichen Informationstyps – E-Mail-Adresse

- Erstellen eines neuen vertraulichen Informationstyps mit einer XML-Beispieldatei – Contoso-Kundennummer

Siehe auch:

- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps mit PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [Anpassen eines benutzerdefinierten vertraulichen Informationstyps](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a>Ändern eines vertraulichen Informationstyps für verbesserte Genauigkeit

Wenn Sie die Inhaltssuche für die Suche personenbezogener Daten mithilfe von vertraulichen Informationstypen verwenden und diese nicht die erwarteten Ergebnisse oder zu viele falsch positive Ergebnisse zurückgibt, sollten Sie den vertraulichen Informationstyp ändern, damit dieser besser mit Ihrer Umgebung funktioniert.

Eine bewährte Methode beim Erstellen oder Anpassen eines vertraulichen Informationstyps besteht darin, einen neuen vertraulichen Informationstyp basierend auf einem vorhandenen zu erstellen und für diesen einen eindeutigen Namen und Bezeichner festzulegen. Wenn Sie die Parameter des vertraulichen Informationstyps „EU-Debitkartennummer“ anpassen möchten, können Sie Ihre Kopie dieser Regel z. B. „EU-Debitkarte erweitert“ benennen, damit sie sich von der ursprünglichen Regel unterscheidet.

Ändern Sie in Ihrem neuen vertraulichen Informationstyp einfach die Werte, die Sie für bessere Genauigkeit ändern möchten. Wenn Sie dies abgeschlossen haben, laden Sie Ihren neuen vertraulichen Informationstyp hoch und erstellen Sie eine neue DLP-Regel (oder ändern Sie eine vorhandene Regel), um den hinzugefügten neuen vertraulichen Informationstyp zu verwenden. Beim Ändern der Genauigkeit vertraulicher Informationstypen sind möglicherweise einige Testversuche erforderlich, sodass Sie durch eine Kopie des ursprünglichen Typs darauf zurückgreifen können, wenn dies in der Zukunft erforderlich ist.

So passen Sie einen benutzerdefinierten vertraulichen Informationstyp an

1.  Exportieren Sie das vorhandene Microsoft-Regelpaket der integrierten vertraulichen Informationstypen in Office 365.

2.  Benennen Sie diese XML-Datei um, und öffnen Sie sie in einem beliebigen XML-Editor.

3.  Isolieren Sie den vertraulichen Informationstyp, und entfernen Sie alle anderen.

4.  Verwenden Sie PowerShell, um zwei neue GUIDs für den vertraulichen Informationstyp zu generieren, den Sie ändern möchten.

5.  Ändern Sie die ID und andere grundlegende Elemente, damit der vertrauliche Informationstyp eindeutig ist (Dies umfasst das Ersetzen der zwei GUIDs durch die neuen, die generiert wurden.).

6.  Optimieren Sie die Übereinstimmungsanforderungen für verbesserte Genauigkeit.

    1.  Änderungen der Näherung – Ändern Sie die Näherung der Zeichenmuster, um den Bereich zu vergrößern bzw. einzugrenzen, in dem Schlüsselwörter um den vertraulichen Informationstyp herum gefunden werden müssen.

    2.  Änderungen des Schlüsselworts – Fügen Sie Schlüsselwörter zu einem \<Keywords\>-Element hinzu, um für den vertraulichen Informationstyp einen genaueren bestätigenden Nachweis für die Suche bereitzustellen, um dieser Regel eine Übereinstimmung zu signalisieren. Sie können auch Schlüsselwörter entfernen, die für falsch positive Ergebnisse sorgen.

    3.  Änderungen der Konfidenz – Ändern Sie die Konfidenz, mit der der vertrauliche Informationstyp den in der Definition angegebenen Kriterien entsprechen muss, bevor eine Übereinstimmung signalisiert und gemeldet wird.

7.  Laden Sie den neuen vertraulichen Informationstyp hoch.

8.  Durchforsten Sie Ihre Inhalte erneut, um vertrauliche Informationen zu identifizieren. Weitere Informationen finden Sie unter [Manuelles Anfordern des Durchforstens und des erneuten Indizieren einer Website](https://support.office.com/article/Manually-request-crawling-and-re-indexing-of-a-site-a-library-or-a-list-9AFA977D-39DE-4321-B4CA-8C7C7E6D264E).

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a>Beispiel: Ändern des vertraulichen Informationstyps „EU-Debitkartennummer“

Zur Verbesserung der Genauigkeit von DLP-Regeln in einem System sind Tests anhand eines Beispieldatensatzes erforderlich und ggf. eine Optimierung durch sich wiederholende Änderungen und Tests. In diesem Beispiel werden Änderungen des vertraulichen Informationstyps „EU-Debitkartennummer“ zur Verbesserung der Genauigkeit veranschaulicht.

Bei der Suche nach einer EU-Debitkartennummer in unserem Beispiel ist die Definition dieser Zahl mithilfe eines komplexen Musters streng als 16 Ziffern definiert, die einer Überprüfung der Prüfsumme unterliegt. Wir können dieses Muster aufgrund der Zeichenfolgendefinition dieses vertraulichen Informationstyps nicht ändern. Wir können jedoch zur Verbesserung der Genauigkeit für die Suche dieses vertraulichen Informationstyps in Office 365 mit DLP von Office 365 folgende Änderungen vornehmen.

### <a name="proximity-modification"></a>Änderung der Näherung

Wir werden den Bereich eingrenzen, indem der patternProximity-Wert in unserem \<Entity\>-Element von 300 in 150 Zeichen geändert wird. Dies bedeutet, dass der bestätigende Nachweis oder unsere Stichwörter, sich näher an unserem vertraulichen Informationstyp befinden müssen, damit diese Regel eine Übereinstimmung signalisiert.

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

### <a name="keyword-modifications"></a>Änderungen des Schlüsselworts

Einige Schlüsselwörter können dazu führen, dass falsch positive Ergebnisse auftreten. Sie möchten daher möglicherweise einige Schlüsselwörter entfernen. Hier sind die Schlüsselwörter für dieses Beispiel:

\<Keyword id="Keyword\_card\_terms\_dict"\>

\<Group\>

\<Term\>corporate card\</Term\>

\<Term\>organization card\</Term\>

\<Term\>acct nbr\</Term\>

\<Term\>acct num\</Term\>

\<Term\>acct no\</Term\>

…

\</Group\>

\</Keyword\>

### <a name="confidence-modifications"></a>Änderungen der Konfidenz

Wenn Sie Schlüsselwörter aus der Definition entfernen, möchten Sie in der Regel auch die Konfidenz anpassen, mit der dieser vertraulicher Informationstyp durch Verringern dieses Werts gefunden wurde. Die Standardstufe für den Typ „EU-Debitkartennummer“ ist 85.

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

…

\</Pattern\>

\</Entity\>

## <a name="create-a-new-custom-sensitive-information-type"></a>Erstellen eines neuen benutzerdefinierten vertraulichen Informationstyps

Um einen neuen benutzerdefinierten vertraulichen Informationstyp zu erstellen, beginnen Sie mit der Verwendung der Inhaltssuche für folgende Aufgaben:

-   Optimieren einer KQL-Abfrage

-   Erfahren, welche Schlüsselwörter besonders hilfreich sind

Verwenden Sie diese Ergebnisse, um einen neuen vertraulichen Informationstyp zu erstellen. Optimieren Sie dann den neuen vertraulichen Informationstyp für Ihre Umgebung.

Hinweis: In Kürze stehen viele neue vertrauliche Informationstypen für personenbezogene Daten in EU-Ländern zur Verfügung. Wenn Sie neue vertrauliche Informationstypen erstellen müssen, legen Sie zunächst die Daten als Ziel fest, die in Ihrer Umgebung benutzerdefiniert sind.

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a>Schritt 1 – Verwenden von KQL-Abfragen und Stichwörtern für die Suche nach zusätzlichen Daten in Ihrer Umgebung

Sie müssen möglicherweise zusätzliche Abfragen erstellen, um nach personenbezogenen Daten zu suchen, die der DSGVO unterliegen. Die Inhaltssuche verwendet KQL (Keyword Query Language) für die Suche von Daten. Die meisten vertraulichen Daten können nicht ausschließlich mithilfe von KQL ohne vertrauliche Informationstypen ordnungsgemäß erkannt werden. Ziel ist es daher, KQL-Zeichenfolgen mithilfe der Inhaltssuche zu testen und zu optimieren und sie dann für das Erstellen und Optimieren neuer vertraulicher Informationstypen für verbesserte Genauigkeit zu verwenden.

Verwenden Sie die folgenden Ressourcen, um Abfragen mithilfe von KQL zu formulieren und zu optimieren:

- [Syntaxreferenz für die Keyword Query Language (KQL) (DMC)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

- [Ausführen einer Inhaltssuche](content-search.md)

Die Inhaltssuche bietet eine weitere Ressource, die Sie beim Entwickeln von KQL-Abfragen und vertraulichen Informationstypen unterstützt – Schlüsselwörter. Gründe für die Verwendung der Schlüsselwortliste? Sie können Statistiken abrufen, die zeigen, wie viele Elemente den einzelnen Schlüsselwörtern entsprechen. Dadurch können Sie schnell erkennen, welche Schlüsselwörter am effektivsten (und am wenigsten effektiv) sind. Weitere Informationen zu Suchstatistiken finden Sie unter [Anzeigen der Schlüsselwortstatistik für Inhaltssuchergebnisse](https://support.office.com/article/View-keyword-statistics-for-Content-Search-results-9701a024-c52e-43f0-b545-9a53478aec04).

Schlüsselwörter in einer Zeile werden durch den OR-Operator in der Suchabfrage verknüpft, die erstellt wird. Sie können auch einen Stichwortausdruck (in Klammern) in einer Zeile verwenden.

Weitere Informationen finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](https://support.office.com/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3).

### <a name="exampleusing-content-search-to-identify-email-addresses"></a>Beispiel – Verwenden der Inhaltssuche für die Identifizierung von E-Mail-Adressen

E-Mail-Adressen werden als vertrauliche Informationen behandelt, die Personen betreffen. Dies ist ein einfaches Beispiel, das veranschaulicht, wie hilfreich die Inhaltssuche sein kann.

KQL und Schlüsselwörter können nicht zusammen verwendet werden. Verwenden Sie diese Tools separat, um Ihre Abfrage zu verfeinern und Schlüsselwörter zu ermitteln, die bei vertraulichen Informationstypen nützlich sein können.

### <a name="kql-query"></a>KQL-Abfrage

(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)

Hinweise:

-   Sie können NEAR und ONEAR für Näherungssuchen verwenden.

-   Leider unterstützt KQL keine Abfragen mit der Regex-Klasse (Beispiel: IdRef="Regex\_email\_address")

### <a name="keywords"></a>Schlüsselwörter

Geben Sie jedes Schlüsselwort in einer separaten Zeile ein. Beispielschlüsselwörter:

-   email address

-   mail

-   contact

-   sender

-   recipient

-   cc

-   bcc

In diesem Beispiel erfahren Sie möglicherweise, dass Schlüsselwörter nicht erforderlich sind und viele falsch positive Ergebnisse erzielen.

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a>Schritt 2 – Erstellen eines neuen benutzerdefinierten vertraulichen Informationstyps

Nachdem Sie KQL-Abfragen und Schlüsselwörter zum Identifizieren vertraulicher Informationstypen verwendet haben, verwenden Sie diese zum Erstellen von neuen benutzerdefinierten vertraulichen Informationstypen. In vielen Fällen benötigen Sie die Komplexität der vertraulichen Informationstypen, um eine geeignete Genauigkeitsebene zu erzielen. Sie können dann diese benutzerdefinierten vertraulichen Informationstypen mit der Inhaltssuche, in DLP-Richtlinien und anderen Tools und in anderen KQL-Abfragen verwenden.

Die bewährte Methode besteht darin, einen neuen vertraulichen Informationstyp basierend auf einem vorhandenen zu erstellen. Verwenden Sie das gleiche Verfahren, wie oben in diesem Artikel beschrieben.

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a>Beispiel – Erstellen eines neuen vertraulichen Informationstyps für E-Mail-Adressen 

Wir werden mit der E-Mail-Adresse als Beispiel fortfahren, weil es einfach ist. In der folgende Tabelle sind die Änderungen enthalten, die für einen neuen vertraulichen Informationstyp „E-Mail-Adresse“ empfohlen sind.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Schritt</strong></th>
<th align="left"><strong>Änderung</strong></th>
<th align="left"><strong>Beispiel-XML-Syntax</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Legen Sie die IdRef-Eigenschaft fest.
<p>Ändern Sie in dem &lt;Entity&gt;-Element das &lt;IdMatch&gt;-Element so, dass seine idRef-Eigenschaft einem eindeutigen Wert entspricht. Dieser Wert verweist auf ein Element, das unseren regulären Ausdruck für die Suche von E-Mail-Adressen definiert.</p></td>
<td align="left">IdRef=&quot;Regex_email_address&quot;</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left"><p>Näherungsattribut</p>
<p>Wir beginnen mit einem patternProximity-Wert von 300 in unserem &lt;Entity&gt;-Element.</p></td>
<td align="left">patternsProximity=&quot;300&quot;</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left"><p>Zuverlässigkeitsstufe</p>
<p>Legen Sie die recommendedConfidence-Eigenschaft auf einen Wert fest, der der Zuverlässigkeit entspricht, mit der eine genaue Übereinstimmung gefunden wird. Dies erfordert wahrscheinlich einige Tests anhand eines repräsentativen Datensatzes, um ein genaues Ergebnis zu erhalten. Legen Sie diesen Wert zunächst auf 75 fest.</p></td>
<td align="left"><p>recommendedConfidence=&quot;75&quot;&gt;</p>
<p>Der resultierende XML-Code für diese ersten drei Elemente sieht wie folgt aus:</p>
<p>&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</p>
<p>&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</p>
<p>&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</p>
<p>&lt;Any minMatches=&quot;1&quot;&gt;</p>
<p>&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</p>
<p>&lt;/Any&gt;</p>
<p>&lt;/Pattern&gt;</p>
<p>&lt;/Entity&gt;</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left"><p>Regex-Element</p>
<p>Fügen Sie ein neues &lt;Regex&gt;-Element unmittelbar unterhalb der &lt;Entity&gt;-Elemente hinzu, die den zum Identifizieren von E-Mail-Adressen verwendeten regulären Ausdruck definieren.</p></td>
<td align="left">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left"><p>Schlüsselwörter</p>
<p>Fügen Sie ein neues &lt;Keyword&gt;-Element unterhalb des &lt;Regex&gt;-Elements hinzu, das die Liste von E-Mail-Adressen definiert, die mit Schlüsselwörtern verknüpft sind. Stellen Sie sicher, dass der ID-Wert für das &lt;Keyword&gt;-Element dem &lt;Match idRef&gt;-Wert in dem &lt;Entity&gt;&lt;Pattern&gt;-Element entspricht. Sie können weiterhin eigene Schlüsselwörter hinzufügen, falls erforderlich.</p>
<p>Schlüsselwörter müssen nicht zwingend in einem vertraulichen Informationstyp „E-Mail-Adresse“ enthalten sein. Sie dienen lediglich als Beispiel.</p></td>
<td align="left"><p>&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</p>
<p>&lt;Group&gt;</p>
<p>&lt;Term&gt;email&lt;/Term&gt;</p>
<p>&lt;Term&gt;email address&lt;/Term&gt;</p>
<p>&lt;Term&gt;contact&lt;/Term&gt;</p>
<p>&lt;/Group&gt;</p>
<p>&lt;/Keyword&gt;</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left"><p>LocalizedStrings-Element</p>
<p>Stellen Sie in dem &lt;LocalizedStrings&gt;&lt;Resource&gt;-Element sicher, dass Sie einen eindeutigen Namen verwenden, der den vertraulichen Informationstyp angibt.</p></td>
<td align="left"><p>&lt;LocalizedStrings&gt;</p>
<p>&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</p>
<p>&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</p>
<p>&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</p>
<p>&lt;/Resource&gt;</p>
<p>&lt;/LocalizedStrings&gt;</p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a>Erstellen eines neuen vertraulichen Informationstyps mit einer PowerShell- und XML-Beispieldatei – Contoso-Kundennummer

Contoso verwendet eine Contoso-Kundennummer, um jeden Kunden in der Kundendatenbank zu identifizieren. Eine Contoso-Kundennummer weist die folgende Taxonomie auf:

-   Zwei Ziffern, die für das Jahr stehen, in dem der Datensatz erstellt wurde. Contoso wurde im Jahr 2002 gegründet. Daher wäre der früheste mögliche Wert 02.

-   Drei Ziffern, die für die Partneragentur stehen, die den Datensatz erstellt hat. Mögliche Agenturwerte liegen zwischen 000 bis 999.

-   Ein alphanumerisches Zeichen zur Darstellung der Branche. Mögliche Werte sind a-z. Groß- und Kleinschreibung sollte dabei nicht berücksichtigt werden.

-   Eine vierstellige fortlaufende Seriennummer. Mögliche Werte liegen zwischen 0000 und 9999.

Beispiele für Contoso-Kundennummern:

> 15080P9562
>
> 14040O1119
>
> 15020J8317
>
> 14050E2330
>
> 16050E2166
>
> 17040O1118

Contoso verwendet immer eine Contoso-Kundennummer beim Verweisen auf Kunden in der internen Korrespondenz, externen Korrespondenz, in Dokumenten usw. Das Unternehmen möchte einen benutzerdefinierten vertraulichen Informationstyp erstellen, um die Verwendung von Contoso-Kundennummern in Office 365 zu ermitteln, um einen möglichen Schutz für die Verwendung dieser personenbezogenen Daten anzuwenden.

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a>Erstellen eines neuen vertraulichen Informationstyps für Contoso-Kundennummer

<table>
<thead>
<tr class="header">
<th align="left"><strong>Schritt</strong></th>
<th align="left"><strong>Aktion </strong></th>
<th align="left"><strong>Ergebnis</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Contoso verwendet PowerShell und die Inhaltssuche, um nach Dokumenten zu suchen, die einem beispielhaften Satz an Contoso-Kundennummern entsprechen.</td>
<td align="left">

<p>#Verbinden mit Office 365 Security &amp; Compliance Center</p>
<p>$adminUser = &quot;alland@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#Erstellen &amp; Starten der Suche für Beispieldaten</p>
<p>$searchName = &quot;Sample Customer Information Search&quot;</p>
<p>$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</p>
<p>New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</p>
<p>Start-ComplianceSearch -Identity $searchName</p>
</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">Contoso analysiert die Ergebnisse. Jedes Mal, wenn die Contoso-Kundennummer verwendet wurde, wurde ein Datum im EU-Format verwendet sowie eines der folgenden Schlüsselwörter innerhalb eines Näherungsbereichs von 300 Zeichen.</td>
<td align="left">customer number, customer no, customer #, customer#, Contoso customer</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">Contoso hat das folgende RegEx-Muster zum Identifizieren von Contoso-Kundennummern entwickelt.</td>
<td align="left">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">Contoso hat das folgende RegEx-Muster zum Identifizieren von EU-Datumsangaben in den von ihren verschiedenen Filialen verwendeten Formaten entwickelt.</td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">Contoso verwendet PowerShell, um drei eindeutige GUIDs zu generieren.</td>
<td align="left"><p>#Generieren einer eindeutigen GUID für RulePack-ID, Publisher-ID und Entitäts-ID</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left">Contoso definiert die folgenden Parameter für die Regel für vertrauliche Elemente.</td>
<td align="left"><p>Name: Contoso-Kundennummer</p>
<p>Beschreibung: Contoso-Kundennummer, die nach zusätzlichen Stichwörtern und EU-Datumsangaben sucht.</p></td>
</tr>
<tr class="odd">
<td align="left">7</td>
<td align="left">Contoso erstellt eine XML-Datei für einen neuen vertraulichen Informationstyp zum Erkennen einer Contoso-Kundennummer und speichert diese in einem lokalen Dateisystem als C:\Scripts\ContosoCCN.xml mit UTF-8-Codierung.</td>
<td align="left">Siehe XML-Datei unter dieser Tabelle.</td>
</tr>
<tr class="even">
<td align="left">8</td>
<td align="left">Contoso erstellt den benutzerdefinierten vertraulichen Informationstyp mit PowerShell.</td>
<td align="left"><p>#Verbinden mit Office 365 Security &amp; Compliance Center</p>
<p>$adminUser = &quot;alland@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#Erstellen eines neuen vertraulichen Informationstyps</p>
<p>New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a>XML-Beispieldatei für den neuen vertraulichen Informationstyp (Schritt 7)
```xml
\<?xml version="1.0" encoding="utf-8"?\>

\<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"\>

\<RulePack id="130ae63b-a91e-4a12-9e02-a90e36a83d7f"\>

\<Version major="1" minor="0" build="0" revision="0" /\>

\<Publisher id="47148982-defd-42a1-890a-7b9472099f1f" /\>

\<Details defaultLangCode="en"\>

\<LocalizedDetails langcode="en"\>

\<PublisherName\>Contoso Ltd.\</PublisherName\>

\<Name\>Contoso Rule Package\</Name\>

\<Description\>Defines Contoso's custom set of classification rules\</Description\>

\</LocalizedDetails\>

\</Details\>

\</RulePack\>

\<Rules\>

\<!-- Contoso Customer Number (CCN) --\>

\<Entity id="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b" patternsProximity="300" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

\<IdMatch idRef="Regex\_contoso\_ccn" /\>

\<Match idRef="Keyword\_contoso\_ccn" /\>

\<Match idRef="Regex\_eu\_date" /\>

\</Pattern\>

\</Entity\>

\<Regex id="Regex\_contoso\_ccn"\>[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}\</Regex\>

\<Keyword id="Keyword\_contoso\_ccn"\>

\<Group matchStyle="word"\>

\<Term caseSensitive="false"\>customer number\</Term\>

\<Term caseSensitive="false"\>customer no\</Term\>

\<Term caseSensitive="false"\>customer \#\</Term\>

\<Term caseSensitive="false"\>customer\#\</Term\>

\<Term caseSensitive="false"\>Contoso customer\</Term\>

\</Group\>

\</Keyword\>

\<Regex id="Regex\_eu\_date"\> (0?[1-9]|[12][0-9]|3[0-1])[\\/-](0?[1-9]|1[0-2]|j\\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?‌ |feb(ruary|ruari|rero|braio|ruar|br)?|f\\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\\x00e4rz|maart‌|apr(ile|il)?|abr(il)?|avril‌ |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?‌ |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\\x00e9c(embre)?)[ \\/-](19|20)?[0-9]{2}\</Regex\>

\<LocalizedStrings\>

\<Resource idRef="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b"\>

\<Name default="true" langcode="en-us"\>Contoso Customer Number (CCN)\</Name\>

\<Description default="true" langcode="en-us"\>Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date\</Description\>

\</Resource\>

\</LocalizedStrings\>

\</Rules\>

\</RulePackage\>
```
