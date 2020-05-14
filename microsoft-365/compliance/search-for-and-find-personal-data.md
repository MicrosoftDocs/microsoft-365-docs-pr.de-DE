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
ms.openlocfilehash: e0d29697a28221b5ff998f5ce923c143bf7a0804
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214579"
---
# <a name="search-for-and-find-personal-data"></a><span data-ttu-id="f5601-103">Suchen und Finden personenbezogener Daten</span><span class="sxs-lookup"><span data-stu-id="f5601-103">Search for and find personal data</span></span>

<span data-ttu-id="f5601-104">Personenbezogene Daten sind unter der DSGVO allgemein als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen, die Einwohner der Europäischen Union (EU) ist.</span><span class="sxs-lookup"><span data-stu-id="f5601-104">Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="f5601-105">Artikel 4: Definitionen</span><span class="sxs-lookup"><span data-stu-id="f5601-105">Article 4 – Definitions</span></span>

> <span data-ttu-id="f5601-106">Als „personenbezogene Daten“ gelten alle Informationen über eine identifizierte oder identifizierbare natürliche Person („betroffene Person“). Eine identifizierbare natürliche Person ist eine Person, die direkt oder indirekt, insbesondere durch Zuordnung zu einer Kennung wie einem Namen, zu einer Kennnummer, zu Standortdaten, zu einer Online-Kennung oder zu einem oder mehreren besonderen Merkmalen identifiziert werden kann, die Ausdruck der physischen, physiologischen, genetischen, psychischen, wirtschaftlichen, kulturellen oder sozialen Identität dieser natürlichen Person sind.</span><span class="sxs-lookup"><span data-stu-id="f5601-106">'personal data' means any information relating to an identified or identifiable natural person ('data subject'); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="f5601-107">In diesem Artikel wird veranschaulicht, wie in SharePoint Online und OneDrive for Business (was die Websites für alle Microsoft 365-Gruppen und Microsoft Teams umfasst) gespeicherte personenbezogene Daten zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="f5601-107">This article demonstrates how to find personal data stored in SharePoint Online and OneDrive for Business (which includes the sites for all Microsoft 365 groups and Microsoft Teams).</span></span>

<span data-ttu-id="f5601-108">Das Suchen nach personenbezogenen Daten, das der DSGVO unterliegt, stützt sich auf die Verwendung von vertraulichen Informationstypen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="f5601-108">Finding personal data subject to GDPR relies on using sensitive information types in Office 365.</span></span> <span data-ttu-id="f5601-109">Sie legen fest, wie bestimmte Informationstypen (z. B. Krankenversicherungsnummern und Kreditkartennummern) von einem automatisierten Prozess erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="f5601-109">These define how the automated process recognizes specific information types such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="f5601-110">Sie können die Richtlinien zur Verhinderung von Datenverlust einsetzen, um personenbezogene Daten während der Übertragung zu finden.</span><span class="sxs-lookup"><span data-stu-id="f5601-110">You can use data loss prevention policies to find personal data in mail while in transit.</span></span> <span data-ttu-id="f5601-111">Sie können die vertraulichen Informationstypen, die Sie für GDPR zusammenstellen, verwenden, um personenbezogene Informationen zu finden und zu schützen, während sie per E-Mail versendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5601-111">You can use the sensitive information types you curate for GDPR to find and protect personal information as it is sent through email.</span></span> <span data-ttu-id="f5601-112">Siehe auch [Verwalten von Anträgen betroffener Personen nach der DSGVO mit dem Anfragetool für Anträge betroffener Personen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).</span><span class="sxs-lookup"><span data-stu-id="f5601-112">Also see [Managed GDPR data subject requests with the DSR case tool in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).</span></span>

## <a name="use-content-search-to-find-personal-data"></a><span data-ttu-id="f5601-113">Verwenden der Inhaltssuche zum Suchen nach personenbezogenen Daten</span><span class="sxs-lookup"><span data-stu-id="f5601-113">Use Content Search to find personal data</span></span>

<span data-ttu-id="f5601-p102">Microsoft empfiehlt einen dreistufigen Ansatz zum Suchen nach personenbezogenen Daten in Office 365. Der Rest des Themas bietet Hilfestellung für jede dieser Stufen.</span><span class="sxs-lookup"><span data-stu-id="f5601-p102">Microsoft recommends a three-stage approach to finding personal data in Office 365. The rest of this topic provides guidance for each of these stages.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f5601-116"><strong>Schritt</strong></span><span class="sxs-lookup"><span data-stu-id="f5601-116"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="f5601-117"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="f5601-117"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5601-118">1. Suchen nach Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="f5601-118">1. Search for sensitive information types</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5601-p103">Verwenden Sie als Erstes Typen vertraulicher Informationen, um personenbezogene Daten zu finden. Erstellen Sie eine Abfrage der Inhaltssuche für jeden Typ vertraulicher Informationen. Führen Sie die Abfrage aus, und analysieren Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="f5601-p103">Start by using sensitive information types to find personal data. Create a Content Search query for each sensitive information type. Run the query and analyze the results.</span></span></p>
<span data-ttu-id="f5601-122">Fügen Sie der Abfrage ggf. Parameter hinzu, um die falsch positiven Ergebnisse zu verringern:</span><span class="sxs-lookup"><span data-stu-id="f5601-122">If needed, add parameters to the query to reduce false positives:</span></span> <li><span data-ttu-id="f5601-123">Anzahlbereich</span><span class="sxs-lookup"><span data-stu-id="f5601-123">Count range</span></span></li>
    <li><span data-ttu-id="f5601-124">Konfidenzbereich</span><span class="sxs-lookup"><span data-stu-id="f5601-124">Confidence range</span></span></li>
    <li><span data-ttu-id="f5601-125">Andere Eigenschaften oder Operatoren für komplexere Abfragen</span><span class="sxs-lookup"><span data-stu-id="f5601-125">Other properties or operators for more complex queries</span></span></li>
<p><span data-ttu-id="f5601-126">Ändern Sie ggf. einen Typ vertraulicher Informationen, um die Genauigkeit für Ihre Organisation zu verbessern:</span><span class="sxs-lookup"><span data-stu-id="f5601-126">If necessary, modify a sensitive information type to improve accuracy for your organization:</span></span></p>
<p><li><span data-ttu-id="f5601-127">Passen Sie den Zuverlässigkeitsgrad direkt in den XML-Daten an.</span><span class="sxs-lookup"><span data-stu-id="f5601-127">Adjust the confidence level directly in the XML.</span></span></li></p>
<p><li><span data-ttu-id="f5601-128">Fügen Sie Schlüsselwörter hinzu.</span><span class="sxs-lookup"><span data-stu-id="f5601-128">Add key words.</span></span></li></p>
<p><li><span data-ttu-id="f5601-129">Passen Sie die Näherungsanforderungen für Schlüsselwörter an.</span><span class="sxs-lookup"><span data-stu-id="f5601-129">Adjust the proximity requirements for keywords.</span></span></li></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5601-130">2. Verwenden von Keyword Query Language (KQL), um zusätzliche personenbezogene Daten in Ihrer Umgebung zu finden</span><span class="sxs-lookup"><span data-stu-id="f5601-130">2. Use Keyword Query Language (KQL) to find additional personal data in your environment</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5601-131">Für die Suche nach Daten, die nicht in Typen vertraulicher Informationen enthalten sind, erstellen Sie benutzerdefinierte Abfragen mit der Abfragesprache KQL.</span><span class="sxs-lookup"><span data-stu-id="f5601-131">To find data not included in sensitive information types, use the KQL query language to develop custom queries.</span></span></p>
<p><span data-ttu-id="f5601-132">Testen Sie die Ergebnisse dieser Suchvorgänge, und passen Sie die KQL-Abfragezeichenfolge an, bis Sie das erwartete Ergebnis erzielen.</span><span class="sxs-lookup"><span data-stu-id="f5601-132">Test the results of these searches and adjust the KQL query string until you achieve the expected result.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5601-133">3. Erstellen neuer benutzerdefinierter Typen vertraulicher Informationen mithilfe der KQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="f5601-133">3. Create new custom sensitive information types using the KQL queries</span></span></p></td>
<td align="left"><span data-ttu-id="f5601-p104">Nachdem Sie die KQL-Abfragen zum Suchen nach Zieldaten optimiert haben, erstellen Sie neue benutzerdefinierte Typen vertraulicher Informationen mit diesen Abfragen. Sie können diese benutzerdefinierten Typen vertraulicher Informationen dann mit der Inhaltssuche, in DLP-Richtlinien und anderen Tools sowie in anderen KQL-Abfragen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5601-p104">After optimizing KQL queries to find target data, create new custom sensitive information types using these queries. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span></td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a><span data-ttu-id="f5601-136">Suchen nach Typen vertraulicher Informationen mit der Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="f5601-136">Search for sensitive information types using Content Search</span></span>

<span data-ttu-id="f5601-137">Beginnen Sie mit der Suche nach personenbezogenen Daten, indem Sie vertrauliche Informationstypen verwenden, die in Office 365 enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f5601-137">Begin searching for personal data by using the sensitive information types that are included with Office 365.</span></span> <span data-ttu-id="f5601-138">Diese sind unter „Klassifizierung“ im Security Center und Compliance Center aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f5601-138">These are listed under Classification in the security center and compliance center.</span></span>

<span data-ttu-id="f5601-139">Dieses Thema enthält eine Liste einiger vertraulicher Informationstypen, die für Bürger in der Europäischen Union gelten.</span><span class="sxs-lookup"><span data-stu-id="f5601-139">This topic includes a list of some sensitive information types that apply to citizens in the European Union.</span></span> <span data-ttu-id="f5601-140">Gehen Sie zum Security Center oder Compliance Center, um sich über neue Ergänzungen zu informieren, die bei der DSGVO-Compliance hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="f5601-140">Check the security center or the compliance center for new additions that can help with GDPR compliance.</span></span>

<span data-ttu-id="f5601-141">Weitere Informationen finden Sie im Artikel: [Liste der Typen vertraulicher Informationen und wonach sie suchen](https://docs.microsoft.com/microsoft-365/compliance/content-search).</span><span class="sxs-lookup"><span data-stu-id="f5601-141">Also see this article: [List of sensitive information types and what each one looks for](https://docs.microsoft.com/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="f5601-p107">Typen vertraulicher Informationen definieren, wie der automatisierte Prozess bestimmte Informationstypen wie Kreditkartennummern und Bankkontonummern erkennt. Typen vertraulicher Informationen werden auch als Bedingungen bezeichnet. Ein Typ vertraulicher Informationen wird durch ein Muster definiert, das durch einen regulären Ausdruck oder eine Funktion identifiziert werden kann. Darüber hinaus können auch belegende Hinweise wie Schlüsselwörter oder Prüfsummen zum Identifizieren eines Typs vertraulicher Informationen verwendet werden. Zuverlässigkeitsgrad und Näherung werden ebenfalls bei der Auswertung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5601-p107">Sensitive information types define how the automated process recognizes specific information types such as bank account numbers, health service numbers, and credit card numbers. Sensitive information types are also referred to as conditions. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>

<span data-ttu-id="f5601-147">Zu diesem Zeitpunkt können Typen vertraulicher Informationen nicht zur Suche nach Daten in ruhenden Postfächern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5601-147">At this time sensitive information types cannot be used to find data at rest in mailboxes.</span></span>

### <a name="using-content-search-with-sensitive-information-types"></a><span data-ttu-id="f5601-148">Verwenden der Inhaltssuche mit Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="f5601-148">Using Content Search with sensitive information types</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f5601-149"><strong>Schritt</strong></span><span class="sxs-lookup"><span data-stu-id="f5601-149"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="f5601-150"><strong>Weitere Informationen</strong></span><span class="sxs-lookup"><span data-stu-id="f5601-150"><strong>More information</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p><span data-ttu-id="f5601-151">Wechseln zur Inhaltssuche im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f5601-151">Go to Content Search in the Security and Compliance Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5601-152">Klicken Sie im linken Bereich des Security &amp; Compliance Centers auf **Suche &amp; Untersuchung** &gt; **Inhaltssuche**.</span><span class="sxs-lookup"><span data-stu-id="f5601-152">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** &gt; **Content search**.</span></span></p>
<p><span data-ttu-id="f5601-153">Siehe <a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Ausführen einer Inhaltssuche im Security &amp; Compliance Center</a>.</span><span class="sxs-lookup"><span data-stu-id="f5601-153">See <a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Run a Content Search in the Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5601-154">Erstellen eines neuen Suchelements für jeden Typ vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="f5601-154">Create a new search item for each sensitive information type</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5601-155">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="f5601-155">Use the following syntax:</span></span></p>
<blockquote>
<p><span data-ttu-id="f5601-156">SensitiveType: "&lt;Typ&gt;"</span><span class="sxs-lookup"><span data-stu-id="f5601-156">SensitiveType:"&lt;type&gt;"</span></span></p>
</blockquote>
<p><span data-ttu-id="f5601-157">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f5601-157">For example:</span></span></p>
<blockquote>
<p><span data-ttu-id="f5601-158">SensitiveType:&quot;Französische Reisepassnummer&quot;</span><span class="sxs-lookup"><span data-stu-id="f5601-158">SensitiveType:&quot;France Passport Number&quot;</span></span></p>
</blockquote>
<p><span data-ttu-id="f5601-p108">Beschränken Sie die Suche auf SharePoint (schließt OneDrive for Business ein). Stellen Sie sicher, dass die Syntax genau stimmt und keine zusätzlichen Leerzeichen oder Tippfehler enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f5601-p108">Scope the search to SharePoint (includes OneDrive for Business). Make sure the syntax is exact and there are no extra spaces or typos.</span></span></p>
<p><span data-ttu-id="f5601-161">Siehe <a href="https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites">Erstellen einer Abfrage zum Auffinden auf Websites gespeicherter vertraulicher Daten</a>.</span><span class="sxs-lookup"><span data-stu-id="f5601-161">See <a href="https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites">Form a query to find sensitive data stored on sites</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5601-162">Überprüfen der Ergebnisse für jede Suche</span><span class="sxs-lookup"><span data-stu-id="f5601-162">Review the results for each search</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5601-163">Suchen Sie nach dieser Art von Problemen, um zu ermitteln, ob die Abfragegenauigkeit eingehalten wird:</span><span class="sxs-lookup"><span data-stu-id="f5601-163">Look for these types of issues to determine if the query accuracy is on target:</span></span></p>
<p><li><span data-ttu-id="f5601-164">Viele falsch positive Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="f5601-164">Many false positives</span></span></li></p>
<p><li><span data-ttu-id="f5601-165">Fehlende bekannte Instanzen von Daten</span><span class="sxs-lookup"><span data-stu-id="f5601-165">Missing known instances of data</span></span></li></p>
<p><span data-ttu-id="f5601-166">Siehe <a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">Exportieren der Inhaltssuchergebnisse aus dem Security &amp; Compliance Center</a>.</span><span class="sxs-lookup"><span data-stu-id="f5601-166">See <a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">Export Content Search results from the Security &amp; Compliance Center</a>.</span></span></p>
<p><span data-ttu-id="f5601-167">Hinweis: Wenn Sie Mozilla Firefox oder Chrome verwenden, müssen Sie möglicherweise zuerst Berichte mithilfe von Internet Explorer oder Edge herunterladen, um das erforderliche Add-In installieren zu können.</span><span class="sxs-lookup"><span data-stu-id="f5601-167">Note: if you're using Mozilla Firefox or Chrome, you might need to first download reports using Internet Explorer or Edge in order to install the required add-in.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a><span data-ttu-id="f5601-168">Typen vertraulicher Informationen für Daten von EU-Bürgern</span><span class="sxs-lookup"><span data-stu-id="f5601-168">Sensitive information types for EU citizen data</span></span>

<span data-ttu-id="f5601-p109">Beginnen Sie mit diesen Typen vertraulicher Informationen. In Kürze werden zahlreiche weitere Typen vertraulicher Informationen für personenbezogene Daten in EU-Ländern verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="f5601-p109">Start with these sensitive information types. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

> <span data-ttu-id="f5601-171">Nationale belgische Nummer</span><span class="sxs-lookup"><span data-stu-id="f5601-171">Belgium National Number</span></span>
>
> <span data-ttu-id="f5601-172">Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="f5601-172">Credit Card Number</span></span>
>
> <span data-ttu-id="f5601-173">Kroatische ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="f5601-173">Croatia Identity Card Number</span></span>
>
> <span data-ttu-id="f5601-174">Kroatische persönliche ID-Nummer (OIB)</span><span class="sxs-lookup"><span data-stu-id="f5601-174">Croatia Personal Identification (OIB) Number</span></span>
>
> <span data-ttu-id="f5601-175">Nationale tschechische ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="f5601-175">Czech National Identity Card Number</span></span>
>
> <span data-ttu-id="f5601-176">Dänische persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="f5601-176">Denmark Personal Identification Number</span></span>
>
> <span data-ttu-id="f5601-177">EU-Debitkartennummern</span><span class="sxs-lookup"><span data-stu-id="f5601-177">EU Debit Card Number</span></span>
>
> <span data-ttu-id="f5601-178">Nationale finnische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="f5601-178">Finland National ID</span></span>
>
> <span data-ttu-id="f5601-179">Finnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-179">Finland Passport Number</span></span>
>
> <span data-ttu-id="f5601-180">Französische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-180">France Driver's License Number</span></span>
>
> <span data-ttu-id="f5601-181">Französischer Personalausweis (Carte Nationale d'Identité, CNI)</span><span class="sxs-lookup"><span data-stu-id="f5601-181">France National ID Card (CNI)</span></span>
>
> <span data-ttu-id="f5601-182">Französische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-182">France Passport Number</span></span>
>
> <span data-ttu-id="f5601-183">Französische Sozialversicherungsnummer (INSEE)</span><span class="sxs-lookup"><span data-stu-id="f5601-183">France Social Security Number (INSEE)</span></span>
>
> <span data-ttu-id="f5601-184">Deutsche Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-184">German Driver's License Number</span></span>
>
> <span data-ttu-id="f5601-185">Deutsche Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-185">Germany Identity Card Number</span></span>
>
> <span data-ttu-id="f5601-186">Deutsche Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-186">German Passport Number</span></span>
>
> <span data-ttu-id="f5601-187">Nationale griechische ID-Karte</span><span class="sxs-lookup"><span data-stu-id="f5601-187">Greece National ID Card</span></span>
>
> <span data-ttu-id="f5601-188">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="f5601-188">International Banking Account Number (IBAN)</span></span>
>
> <span data-ttu-id="f5601-189">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="f5601-189">IP Address</span></span>
>
> <span data-ttu-id="f5601-190">Irische PPS-Nummer (Personal Public Service)</span><span class="sxs-lookup"><span data-stu-id="f5601-190">Ireland Personal Public Service (PPS) Number</span></span>
>
> <span data-ttu-id="f5601-191">Italienische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-191">Italy's Driver's License Number</span></span>
>
> <span data-ttu-id="f5601-192">Nummer des niederländischen Citizen's Service (BSN)</span><span class="sxs-lookup"><span data-stu-id="f5601-192">Netherlands Citizen's Service (BSN) Number</span></span>
>
> <span data-ttu-id="f5601-193">Norwegische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="f5601-193">Norway Identity Number</span></span>
>
> <span data-ttu-id="f5601-194">Polnische Identitätskarte</span><span class="sxs-lookup"><span data-stu-id="f5601-194">Poland Identity Card</span></span>
>
> <span data-ttu-id="f5601-195">Nationale polnische ID-Nummer (PESEL)</span><span class="sxs-lookup"><span data-stu-id="f5601-195">Poland National ID (PESEL)</span></span>
>
> <span data-ttu-id="f5601-196">Polnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-196">Poland Passport</span></span>
>
> <span data-ttu-id="f5601-197">Portugiesische ID-Kartennummer (Citizen Card)</span><span class="sxs-lookup"><span data-stu-id="f5601-197">Portugal Citizen Card Number</span></span>
>
> <span data-ttu-id="f5601-198">Spanische Sozialversicherungsnummer (SSN)</span><span class="sxs-lookup"><span data-stu-id="f5601-198">Spain Social Security Number (SSN)</span></span>
>
> <span data-ttu-id="f5601-199">Nationale schwedische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="f5601-199">Sweden National ID</span></span>
>
> <span data-ttu-id="f5601-200">Schwedische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-200">Sweden Passport Number</span></span>
>
> <span data-ttu-id="f5601-p110">Vereinigtes Königreich – Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-p110">U.K. Driver's License Number</span></span>
>
> <span data-ttu-id="f5601-p111">Vereinigtes Königreich – Wählerverzeichnisnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-p111">U.K. Electoral Roll Number</span></span>
>
> <span data-ttu-id="f5601-p112">UK-Gesundheitsdienstnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-p112">U.K. National Health Service Number</span></span>
>
> <span data-ttu-id="f5601-p113">UK-Sozialversicherungsnummer (National Insurance Number, NINO)</span><span class="sxs-lookup"><span data-stu-id="f5601-p113">U.K. National Insurance Number (NINO)</span></span>
>
> <span data-ttu-id="f5601-p114">US-/UK-Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="f5601-p114">U.S./U.K. Passport Number</span></span>

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a><span data-ttu-id="f5601-211">Hinzufügen von Parametern zu einer Abfrage für Typen vertraulicher Informationen, um die Ergebnisse zu verfeinern</span><span class="sxs-lookup"><span data-stu-id="f5601-211">Add parameters to a sensitive information type query to hone the results</span></span>

<span data-ttu-id="f5601-212">Sie können die folgenden Parameter zu einer Abfrage für Typen vertraulicher Informationen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f5601-212">You can add these parameters to a sensitive information type query:</span></span>

-   <span data-ttu-id="f5601-213">Anzahlbereich – Die Anzahl von Vorkommen vertraulicher Informationen, die ein Dokument aufweisen muss, damit es in die Abfrageergebnisse einbezogen wird.</span><span class="sxs-lookup"><span data-stu-id="f5601-213">Count range — define the number of occurrences of sensitive information a document needs to contain before it's included in the query results.</span></span>

-   <span data-ttu-id="f5601-214">Konfidenzbereich – Der Grad an Konfidenz, zu dem der erkannte Typ vertraulicher Informationen ein Treffer ist. Beispiel: 85 (85%).</span><span class="sxs-lookup"><span data-stu-id="f5601-214">Confidence range — the level of confidence that the detected sensitive type is actually a match, such as 85 (85%).</span></span>

<span data-ttu-id="f5601-215">Syntax:</span><span class="sxs-lookup"><span data-stu-id="f5601-215">Syntax:</span></span>

-   <span data-ttu-id="f5601-216">SensitiveType:"\<Typ\>|\<Anzahlbereich\>|\<Konfidenzbereich\>"</span><span class="sxs-lookup"><span data-stu-id="f5601-216">SensitiveType:"\<type\>|\<count range\>|\<confidence range\>"</span></span>

<span data-ttu-id="f5601-217">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="f5601-217">Examples:</span></span>

-   <span data-ttu-id="f5601-218">SensitiveType:"Kreditkartennummer|5" (nur Dokumente zurückgeben, die genau fünf Kreditkartennummern enthalten)</span><span class="sxs-lookup"><span data-stu-id="f5601-218">SensitiveType:"Credit Card Number|5" (return only documents that contain exactly five credit card numbers)</span></span>

-   <span data-ttu-id="f5601-219">SensitiveType:"Kreditkartennummer|\*|85.." (Konfidenzbereich ist 85 % oder höher)</span><span class="sxs-lookup"><span data-stu-id="f5601-219">SensitiveType:"Credit Card Number|\*|85.." (confidence range is 85 percent or higher)</span></span>

<span data-ttu-id="f5601-220">Hinweis: Bei "SensitiveType" wird die Groß-/Kleinschreibung beachtet, im Rest der Abfrage jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="f5601-220">Note: "SensitiveType" is case sensitive, but the rest of the query is not.</span></span>

<span data-ttu-id="f5601-p115">Sie können auch Eigenschaften und Operatoren verwenden, um zu veranschaulichen, wie Sie Abfragen optimieren können. Weitere Informationen und Beispiele finden Sie unter [Erstellen einer Abfrage zum Auffinden auf Websites gespeicherter vertraulicher Daten](https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites).</span><span class="sxs-lookup"><span data-stu-id="f5601-p115">You can also use properties, and operators to illustrate how you can refine your queries. For more information and examples, see [Form a query to find sensitive data stored on sites](https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites).</span></span>
