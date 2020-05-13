---
title: Suchen und Finden personenbezogener Daten
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
description: Hier erfahren Sie, wie Sie personenbezogene Daten suchen und finden, die den allgemeinen Datenschutzbestimmungen (DSGVO) in Office 365 unterliegen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 50c8db59cfd5e9a7de3da0dc696227e85dab1cee
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208089"
---
# <a name="search-for-and-find-personal-data"></a>Suchen und Finden personenbezogener Daten

Personenbezogene Daten sind unter der DSGVO allgemein als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen, die Einwohner der Europäischen Union (EU) ist.

Artikel 4: Definitionen

> Als „personenbezogene Daten“ gelten alle Informationen über eine identifizierte oder identifizierbare natürliche Person („betroffene Person“). Eine identifizierbare natürliche Person ist eine Person, die direkt oder indirekt, insbesondere durch Zuordnung zu einer Kennung wie einem Namen, zu einer Kennnummer, zu Standortdaten, zu einer Online-Kennung oder zu einem oder mehreren besonderen Merkmalen identifiziert werden kann, die Ausdruck der physischen, physiologischen, genetischen, psychischen, wirtschaftlichen, kulturellen oder sozialen Identität dieser natürlichen Person sind.

In diesem Artikel wird veranschaulicht, wie in SharePoint Online und OneDrive for Business (was die Websites für alle Microsoft 365-Gruppen und Microsoft Teams umfasst) gespeicherte personenbezogene Daten zu finden sind.

Das Suchen nach personenbezogenen Daten, das der DSGVO unterliegt, stützt sich auf die Verwendung von vertraulichen Informationstypen in Office 365. Sie legen fest, wie bestimmte Informationstypen (z. B. Krankenversicherungsnummern und Kreditkartennummern) von einem automatisierten Prozess erkannt werden. Sie können die Richtlinien zur Verhinderung von Datenverlust einsetzen, um personenbezogene Daten während der Übertragung zu finden. Sie können die vertraulichen Informationstypen, die Sie für GDPR zusammenstellen, verwenden, um personenbezogene Informationen zu finden und zu schützen, während sie per E-Mail versendet werden. Siehe auch [Verwalten von Anträgen betroffener Personen nach der DSGVO mit dem Anfragetool für Anträge betroffener Personen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).

## <a name="use-content-search-to-find-personal-data"></a>Verwenden der Inhaltssuche zum Suchen nach personenbezogenen Daten

Microsoft empfiehlt einen dreistufigen Ansatz zum Suchen nach personenbezogenen Daten in Office 365. Der Rest des Themas bietet Hilfestellung für jede dieser Stufen.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Schritt</strong></th>
<th align="left"><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>1. Suchen nach Typen vertraulicher Informationen</p></td>
<td align="left"><p>Verwenden Sie als Erstes Typen vertraulicher Informationen, um personenbezogene Daten zu finden. Erstellen Sie eine Abfrage der Inhaltssuche für jeden Typ vertraulicher Informationen. Führen Sie die Abfrage aus, und analysieren Sie die Ergebnisse.</p>
Fügen Sie der Abfrage ggf. Parameter hinzu, um die falsch positiven Ergebnisse zu verringern: <li>Anzahlbereich</li>
    <li>Konfidenzbereich</li>
    <li>Andere Eigenschaften oder Operatoren für komplexere Abfragen</li>
<p>Ändern Sie ggf. einen Typ vertraulicher Informationen, um die Genauigkeit für Ihre Organisation zu verbessern:</p>
<p><li>Passen Sie den Zuverlässigkeitsgrad direkt in den XML-Daten an.</li></p>
<p><li>Fügen Sie Schlüsselwörter hinzu.</li></p>
<p><li>Passen Sie die Näherungsanforderungen für Schlüsselwörter an.</li></p></td>
</tr>
<tr class="even">
<td align="left"><p>2. Verwenden von Keyword Query Language (KQL), um zusätzliche personenbezogene Daten in Ihrer Umgebung zu finden</p></td>
<td align="left"><p>Für die Suche nach Daten, die nicht in Typen vertraulicher Informationen enthalten sind, erstellen Sie benutzerdefinierte Abfragen mit der Abfragesprache KQL.</p>
<p>Testen Sie die Ergebnisse dieser Suchvorgänge, und passen Sie die KQL-Abfragezeichenfolge an, bis Sie das erwartete Ergebnis erzielen.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3. Erstellen neuer benutzerdefinierter Typen vertraulicher Informationen mithilfe der KQL-Abfragen</p></td>
<td align="left">Nachdem Sie die KQL-Abfragen zum Suchen nach Zieldaten optimiert haben, erstellen Sie neue benutzerdefinierte Typen vertraulicher Informationen mit diesen Abfragen. Sie können diese benutzerdefinierten Typen vertraulicher Informationen dann mit der Inhaltssuche, in DLP-Richtlinien und anderen Tools sowie in anderen KQL-Abfragen verwenden.</td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a>Suchen nach Typen vertraulicher Informationen mit der Inhaltssuche

Beginnen Sie mit der Suche nach personenbezogenen Daten, indem Sie vertrauliche Informationstypen verwenden, die in Office 365 enthalten sind. Diese sind unter „Klassifizierung“ im Security Center und Compliance Center aufgeführt.

Dieses Thema enthält eine Liste einiger vertraulicher Informationstypen, die für Bürger in der Europäischen Union gelten. Gehen Sie zum Security Center oder Compliance Center, um sich über neue Ergänzungen zu informieren, die bei der DSGVO-Compliance hilfreich sind.

Weitere Informationen finden Sie im Artikel: [Liste der Typen vertraulicher Informationen und wonach sie suchen](https://support.office.com/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).

Typen vertraulicher Informationen definieren, wie der automatisierte Prozess bestimmte Informationstypen wie Kreditkartennummern und Bankkontonummern erkennt. Typen vertraulicher Informationen werden auch als Bedingungen bezeichnet. Ein Typ vertraulicher Informationen wird durch ein Muster definiert, das durch einen regulären Ausdruck oder eine Funktion identifiziert werden kann. Darüber hinaus können auch belegende Hinweise wie Schlüsselwörter oder Prüfsummen zum Identifizieren eines Typs vertraulicher Informationen verwendet werden. Zuverlässigkeitsgrad und Näherung werden ebenfalls bei der Auswertung verwendet.

Zu diesem Zeitpunkt können Typen vertraulicher Informationen nicht zur Suche nach Daten in ruhenden Postfächern verwendet werden.

### <a name="using-content-search-with-sensitive-information-types"></a>Verwenden der Inhaltssuche mit Typen vertraulicher Informationen

<table>
<thead>
<tr class="header">
<th align="left"><strong>Schritt</strong></th>
<th align="left"><strong>Weitere Informationen</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p>Wechseln zur Inhaltssuche im Security & Compliance Center</p></td>
<td align="left"><p>Klicken Sie im linken Bereich des Security &amp; Compliance Centers auf **Suche &amp; Untersuchung** &gt; **Inhaltssuche**.</p>
<p>Siehe <a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Ausführen einer Inhaltssuche im Security &amp; Compliance Center</a>.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Erstellen eines neuen Suchelements für jeden Typ vertraulicher Informationen</p></td>
<td align="left"><p>Verwenden Sie die folgende Syntax:</p>
<blockquote>
<p>SensitiveType: "&lt;Typ&gt;"</p>
</blockquote>
<p>Beispiel:</p>
<blockquote>
<p>SensitiveType:&quot;Französische Reisepassnummer&quot;</p>
</blockquote>
<p>Beschränken Sie die Suche auf SharePoint (schließt OneDrive for Business ein). Stellen Sie sicher, dass die Syntax genau stimmt und keine zusätzlichen Leerzeichen oder Tippfehler enthalten sind.</p>
<p>Siehe <a href="https://support.office.com/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Erstellen einer Abfrage zum Auffinden auf Websites gespeicherter vertraulicher Daten</a>.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Überprüfen der Ergebnisse für jede Suche</p></td>
<td align="left"><p>Suchen Sie nach dieser Art von Problemen, um zu ermitteln, ob die Abfragegenauigkeit eingehalten wird:</p>
<p><li>Viele falsch positive Ergebnisse</li></p>
<p><li>Fehlende bekannte Instanzen von Daten</li></p>
<p>Siehe <a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">Exportieren der Inhaltssuchergebnisse aus dem Security &amp; Compliance Center</a>.</p>
<p>Hinweis: Wenn Sie Mozilla Firefox oder Chrome verwenden, müssen Sie möglicherweise zuerst Berichte mithilfe von Internet Explorer oder Edge herunterladen, um das erforderliche Add-In installieren zu können.</p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a>Typen vertraulicher Informationen für Daten von EU-Bürgern

Beginnen Sie mit diesen Typen vertraulicher Informationen. In Kürze werden zahlreiche weitere Typen vertraulicher Informationen für personenbezogene Daten in EU-Ländern verfügbar sein.

> Nationale belgische Nummer
>
> Kreditkartennummer
>
> Kroatische ID-Kartennummer
>
> Kroatische persönliche ID-Nummer (OIB)
>
> Nationale tschechische ID-Kartennummer
>
> Dänische persönliche ID-Nummer
>
> EU-Debitkartennummern
>
> Nationale finnische ID-Nummer
>
> Finnische Reisepassnummer
>
> Französische Führerscheinnummer
>
> Französischer Personalausweis (Carte Nationale d'Identité, CNI)
>
> Französische Reisepassnummer
>
> Französische Sozialversicherungsnummer (INSEE)
>
> Deutsche Führerscheinnummer
>
> Deutsche Personalausweisnummer
>
> Deutsche Reisepassnummer
>
> Nationale griechische ID-Karte
>
> International Banking Account Number (IBAN)
>
> IP-Adresse
>
> Irische PPS-Nummer (Personal Public Service)
>
> Italienische Führerscheinnummer
>
> Nummer des niederländischen Citizen's Service (BSN)
>
> Norwegische ID-Nummer
>
> Polnische Identitätskarte
>
> Nationale polnische ID-Nummer (PESEL)
>
> Polnische Reisepassnummer
>
> Portugiesische ID-Kartennummer (Citizen Card)
>
> Spanische Sozialversicherungsnummer (SSN)
>
> Nationale schwedische ID-Nummer
>
> Schwedische Reisepassnummer
>
> Vereinigtes Königreich – Führerscheinnummer
>
> Vereinigtes Königreich – Wählerverzeichnisnummer
>
> UK-Gesundheitsdienstnummer
>
> UK-Sozialversicherungsnummer (National Insurance Number, NINO)
>
> US-/UK-Reisepassnummer

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a>Hinzufügen von Parametern zu einer Abfrage für Typen vertraulicher Informationen, um die Ergebnisse zu verfeinern

Sie können die folgenden Parameter zu einer Abfrage für Typen vertraulicher Informationen hinzufügen:

-   Anzahlbereich – Die Anzahl von Vorkommen vertraulicher Informationen, die ein Dokument aufweisen muss, damit es in die Abfrageergebnisse einbezogen wird.

-   Konfidenzbereich – Der Grad an Konfidenz, zu dem der erkannte Typ vertraulicher Informationen ein Treffer ist. Beispiel: 85 (85%).

Syntax:

-   SensitiveType:"\<Typ\>|\<Anzahlbereich\>|\<Konfidenzbereich\>"

Beispiele:

-   SensitiveType:"Kreditkartennummer|5" (nur Dokumente zurückgeben, die genau fünf Kreditkartennummern enthalten)

-   SensitiveType:"Kreditkartennummer|\*|85.." (Konfidenzbereich ist 85 % oder höher)

Hinweis: Bei "SensitiveType" wird die Groß-/Kleinschreibung beachtet, im Rest der Abfrage jedoch nicht.

Sie können auch Eigenschaften und Operatoren verwenden, um zu veranschaulichen, wie Sie Abfragen optimieren können. Weitere Informationen und Beispiele finden Sie unter [Erstellen einer Abfrage zum Auffinden auf Websites gespeicherter vertraulicher Daten](https://support.office.com/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).
