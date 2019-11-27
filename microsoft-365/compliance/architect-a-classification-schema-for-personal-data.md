---
title: Entwerfen eines Klassifikationsschemas für personenbezogene Daten
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Ermitteln Sie, ob Ihre Organisation als Teil des DSGVO-Plans Bezeichnungen implementiert.
ms.openlocfilehash: 4470f766ad2f8fd2d914e0e45deac8604028ddb5
ms.sourcegitcommit: 7f26840a4330b0fd29807ec091c6915d283b3dd2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615645"
---
# <a name="architect-a-classification-schema-for-personal-data"></a><span data-ttu-id="10cc1-103">Entwerfen eines Klassifikationsschemas für personenbezogene Daten</span><span class="sxs-lookup"><span data-stu-id="10cc1-103">Architect a classification schema for personal data</span></span>

<span data-ttu-id="10cc1-p101">Vorherige Artikel dieser Reihe konzentrieren sich auf die Verwendung vertraulicher Informationstypen zum Identifizieren personenbezogener Daten, die der DSGVO unterliegen. Vertrauliche Informationstypen sind eine Form der Klassifizierung. Dies ist möglicherweise die einzige Klassifizierung, die Sie benötigen. Viele Organisationen implementieren jedoch mithilfe von Bezeichnungen eine umfassendere Strategie für die Datenkontrolle. Anhand dieses Themas können Sie entscheiden, ob Sie auch im Rahmen Ihres DSGVO-Plans Bezeichnungen implementieren möchten. Wenn Sie sich dazu entscheiden, beinhaltet dieses Thema einige Anleitungen und Beispiele hierzu.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p101">Previous articles in this series focus on using sensitive information types to identify personal data that is subject to GDPR. Sensitive information types are a form of classification. This might be all the classification you need. However, many organizations implement a broader data governance strategy using labels. Use this topic to decide if you also want to implement labels as part of your GDPR plan. If you do, this topic provides some guidance and examples.</span></span>

<span data-ttu-id="10cc1-p102">Hinweis: Die Definition eines Klassifikationsschemas für eine Organisation und die Konfiguration von Richtlinien, Bezeichnungen und Bedingungen erfordert sorgfältige Planung und Vorbereitung. Es ist wichtig zu erkennen, dass dies kein von der IT gesteuerter Prozess ist. Arbeiten Sie unbedingt mit Ihrer Rechts- und Complianceabteilung zusammen, um ein geeignetes Klassifikations- und Bezeichnungsschema für die Daten Ihrer Organisation zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p102">Note: Defining a classification schema for an organization and configuring policies, labels, and conditions requires careful planning and preparation. It is important to realize that this is not an IT driven process. Be sure to work with your legal and compliance team to develop an appropriate classification and labeling schema for your organization’s data.</span></span>

## <a name="decide-if-youre-using-labels-in-addition-to-sensitive-data-types"></a><span data-ttu-id="10cc1-113">Entscheiden, ob Bezeichnungen neben vertraulichen Informationstypen verwendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="10cc1-113">Decide if you are using labels in addition to sensitive data types</span></span>

<span data-ttu-id="10cc1-p103">Sie können einen der beiden Ansätze für die Klassifikation personenbezogener Informationen in Office 365 verwenden. Jeder Ansatz kann für Schutz für die DSGVO verwendet werden. Wenn Sie nur vertrauliche Informationstypen für die Klassifikation verwenden möchten, können Sie den Rest dieses Themas überspringen.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p103">You can take one of two approaches for classification in Office 365 for personal information. Either of these can be used for GDPR protection. If decide to use only sensitive information types for classification, you can skip the rest of this topic.</span></span>

<span data-ttu-id="10cc1-117">Wählen Sie eine der folgenden Optionen.</span><span class="sxs-lookup"><span data-stu-id="10cc1-117">Choose one of the following options.</span></span>

### <a name="option-1-use-only-office-365-sensitive-information-types"></a><span data-ttu-id="10cc1-118">Option 1: Ausschließliches Verwenden vertraulicher Informationstypen in Office 365</span><span class="sxs-lookup"><span data-stu-id="10cc1-118">Option 1: Use only Office 365 sensitive information types</span></span>

- <span data-ttu-id="10cc1-119">Vertrauliche Informationstypen sind gut zum Identifizieren und Schutz personenbezogener Daten geeignet, die der DSGVO und anderen Vorschriften unterliegen.</span><span class="sxs-lookup"><span data-stu-id="10cc1-119">Sensitive information types work well to identify and protect personal data subject to GDPR and other types of regulations.</span></span>

- <span data-ttu-id="10cc1-120">Diese sind einfacher zu verwenden, wenn Ihre Organisation nicht bereits einen umfassenden Plan für die Datenkontrolle mithilfe von Bezeichnungen hat bzw. plant.</span><span class="sxs-lookup"><span data-stu-id="10cc1-120">These are simpler to use if your organization doesn’t already have or plan to implement a broader data governance plan using labels.</span></span>

- <span data-ttu-id="10cc1-121">Sie können mit DLP-Regeln verwendet werden (genauso wie Aufbewahrungsbezeichnungen).</span><span class="sxs-lookup"><span data-stu-id="10cc1-121">These work with DLP rules (so do retention labels).</span></span>

- <span data-ttu-id="10cc1-122">Typen vertraulicher Informationen können auch mit Cloud App Security verwendet werden, sodass Sie vertrauliche Informationen in anderen SaaS-Apps erkennen können.</span><span class="sxs-lookup"><span data-stu-id="10cc1-122">Sensitive information types work with Cloud App Security so you can detect sensitive information in other SaaS apps.</span></span>

### <a name="option-2-use-sensitive-information-types--retention-labels"></a><span data-ttu-id="10cc1-123">Option 2: Verwenden von vertraulichen Informationstypen und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="10cc1-123">Option 2: Use sensitive information types + retention labels</span></span>

- <span data-ttu-id="10cc1-124">Sie benötigen vertrauliche Informationstypen, um Bezeichnungen automatisch auf personenbezogene Daten anzuwenden, die der DSGVO unterliegen, diese sind somit eine Voraussetzung.</span><span class="sxs-lookup"><span data-stu-id="10cc1-124">You’ll need sensitive information types to automatically apply labels to personal data that is subject to GDPR, so these are a prerequisite.</span></span>

- <span data-ttu-id="10cc1-125">Mit Aufbewahrungsbezeichnungen können Sie personenbezogene Daten, die der DSGVO unterliegen, in einen umfassenderen Plan für die Datenkontrolle für Ihre Organisation implementieren.</span><span class="sxs-lookup"><span data-stu-id="10cc1-125">Using retention labels allows you to include personal data that is subject to GDPR into a broader data governance plan for your organization.</span></span>

## <a name="develop-a-label-schema-that-includes-personal-data"></a><span data-ttu-id="10cc1-126">Entwickeln eines Bezeichnungsschemas, das personenbezogene Daten enthält</span><span class="sxs-lookup"><span data-stu-id="10cc1-126">Develop a label schema that includes personal data</span></span>

<span data-ttu-id="10cc1-p104">Bevor Sie die technischen Funktionen zum Anwenden von Bezeichnungen und des Schutzes verwenden können, müssen Sie ein Klassifikationsschema für Ihre Organisation definieren. Ihre Organisation verfügt möglicherweise bereits über ein Klassifikationsschema, was Ihnen das Hinzufügen personenbezogener Daten erleichtert. Dieses Thema enthält ein Beispiel für ein Klassifikationsschema. Sie können dieses Beispiel bei Bedarf als Ausgangspunkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p104">Before using technical capabilities to apply labels and protection, first work across your organization to define a classification schema. Your organization might already have a classification schema, which makes it easier to add personal data. This topic includes an example classification schema. You can use this as a starting point, if needed.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10cc1-131">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="10cc1-131">Getting started</span></span>

<span data-ttu-id="10cc1-p105">Entscheiden Sie zunächst über die Anzahl und die Namen von Bezeichnungen, die Sie implementieren möchten. Machen Sie sich zu diesem Zeitpunkt keine Gedanken darüber, welche Technologie verwendet und wie Bezeichnungen angewendet werden sollen. Wenden Sie dieses Schema universell innerhalb der gesamten Organisation an, darunter Daten, die lokal und in anderen Clouddiensten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p105">Begin by deciding on the number and names of labels to implement. Do this activity without worrying about which technology to use and how labels will be applied. Apply this schema universally throughout your organization, including data that resides on premises and in other cloud services.</span></span>

### <a name="recommendations"></a><span data-ttu-id="10cc1-135">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="10cc1-135">Recommendations</span></span> 

<span data-ttu-id="10cc1-136">Berücksichtigen Sie beim Entwerfen und Implementieren von Richtlinien, Bezeichnungen und Bedingungen die folgenden Empfehlungen:</span><span class="sxs-lookup"><span data-stu-id="10cc1-136">When designing and implementing policies, labels and conditions, consider following these recommendations:</span></span>

- <span data-ttu-id="10cc1-p106">Verwenden Sie ein vorhandenes Klassifikationsschema (sofern vorhanden) &ndash; Viele Organisationen verwenden bereits eine Datenklassifizierung in irgendeiner Form. Werten Sie sorgfältig das vorhandene Bezeichnungsschema aus, und verwenden Sie es nach Möglichkeit unverändert. Vertraute Bezeichnungen, die für den Endbenutzer erkennbar sind, sorgen für größere Akzeptanz.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p106">Use existing classification schema (if any) — Many organizations already are using data classification in some form. Carefully evaluate the existing label schema and if possible use it as is. Using familiar labels that are recognizable to the end-user will drive adoption.</span></span>

- <span data-ttu-id="10cc1-p107">Beginnen Sie mit Standardrichtlinien und -bezeichnungen &ndash; Alle Lösungen enthalten eine Reihe vordefinierter Richtlinien und Bezeichnungen. Werten Sie diese sorgfältig anhand der rechtlichen und geschäftlichen Anforderungen der Organisation aus, und ziehen Sie es in Erwägung, diese zu verwenden, anstatt neue zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p107">Start with default policies and labels — All solutions come with a set of predefined policies and labels. Carefully evaluate these against the organizations legal and business requirements and consider using them instead of creating new ones.</span></span>

- <span data-ttu-id="10cc1-p108">Beginnen Sie klein &ndash; Es gibt nahezu keine Beschränkung, was die Anzahl der Bezeichnungen angeht, die erstellt werden können. Viele Bezeichnungen und Unterbezeichnungen wirken sich jedoch negativ auf die Akzeptanz aus. Zu viele Auswahlmöglichkeiten bedeuten häufig überhaupt keine Auswahl.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p108">Start small — There is virtually no limit to the number of labels that can be created. However, large numbers of labels and sub-labels will negatively impact the adoption. Too many choices often means no choice at all.</span></span>

- <span data-ttu-id="10cc1-145">Verwenden Sie Szenarien und Anwendungsfälle &ndash; Identifizieren Sie allgemeine Anwendungsfälle innerhalb der Organisation, und verwenden Sie Szenarien, die von der DSGVO abgeleitet sind, um zu prüfen, ob die vorgesehene Bezeichnungs- und Klassifikationskonfiguration in der Praxis funktionieren.</span><span class="sxs-lookup"><span data-stu-id="10cc1-145">Use scenarios and use cases — Identify common use cases within the organization and use scenarios derived from the GDPR to verify if the envisioned label and classification configuration will work in practice.</span></span>

- <span data-ttu-id="10cc1-p109">Stellen Sie jede Anforderung für eine neue Bezeichnung in Frage &ndash; Ist für jedes Szenario oder jeden Anwendungsfall wirklich eine neue Bezeichnung erforderlich, oder kann hierfür eine bereits vorhandene Bezeichnung verwendet werden? Eine minimale Anzahl von Bezeichnungen verbessert die Akzeptanz.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p109">Question every request for a new label, does every scenario or use case really need a new label or can we use what we already have? Keeping the number of labels to a minimum improves adoption.</span></span>

- <span data-ttu-id="10cc1-p110">Verwenden Sie Unterbezeichnungen für wichtige Abteilungen &ndash; Für einige Abteilungen sind spezielle Bezeichnungen erforderlich. Definieren Sie diese Bezeichnungen als Unterbezeichnungen für vorhandene Bezeichnungen, und ziehen Sie es in Erwägung, bereichsbezogene Richtlinien zu verwenden, die einer Benutzergruppe zugewiesen sind, anstelle von globalen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p110">Use sub-labels for key departments, some departments will have specific needs that require specific labels. Define these labels as sub-labels to an existing label and consider using scoped policies that are assigned to user groups instead of globally.</span></span>

- <span data-ttu-id="10cc1-p111">Ziehen Sie die Verwendung von bereichsbezogenen Richtlinien in Erwägung &ndash; Richtlinien, die auf eine Teilmenge von Benutzern abzielen, verhindern zu viele Bezeichnungen. Mit einer bereichsbezogenen Richtlinie können Sie rollen- oder abteilungsspezifische (Unter-)Bezeichnungen nur Mitarbeitern zuweisen, die für diese Abteilung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p111">Consider scoped policies, polices targeted at subsets of users will prevent "label overload". A scoped policy enables assigning role or department specific (sub-)labels to just employees that work for that specific department.</span></span>

- <span data-ttu-id="10cc1-p112">Verwenden Sie aussagekräftige Namen &ndash; Es wird empfohlen, Jargon, Standards oder Akronyme nicht als Bezeichnungsnamen zu verwenden. Verwenden Sie Namen, die hohe Akzeptanz bei Endbenutzern finden. Verwenden Sie statt Bezeichnungen wie PII, PCI, HIPAA, LBI, MBI und HBI Namen wie „Privat“, „Öffentlich“, „Allgemein“, „Vertraulich“ und „Streng vertraulich“.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p112">Use meaningful label names, it is recommended not to use jargon, standards or acronyms as label names. Try to use names that resonate with the end user to improve adoption. Instead of using labels like PII, PCI, HIPAA, LBI, MBI and HBI consider names like Non-Business, Public, General, Confidential and Highly Confidential.</span></span>

### <a name="example-classification-schema"></a><span data-ttu-id="10cc1-155">Beispiel für ein Klassifikationsschema</span><span class="sxs-lookup"><span data-stu-id="10cc1-155">Example classification schema</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="10cc1-156"><strong>Bezeichnungsname</strong></span><span class="sxs-lookup"><span data-stu-id="10cc1-156"><strong>Label name</strong></span></span></th>
<th align="left"><span data-ttu-id="10cc1-157"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="10cc1-157"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="10cc1-158">Privat</span><span class="sxs-lookup"><span data-stu-id="10cc1-158">Personal</span></span></td>
<td align="left"><span data-ttu-id="10cc1-159">Nicht geschäftliche Daten, nur für private Verwendung.</span><span class="sxs-lookup"><span data-stu-id="10cc1-159">Non-business data, for personal use only.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="10cc1-160">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="10cc1-160">Public</span></span></td>
<td align="left"><span data-ttu-id="10cc1-161">Geschäftsdaten, die speziell für die öffentliche Nutzung vorbereitet und genehmigt sind.</span><span class="sxs-lookup"><span data-stu-id="10cc1-161">Business data that is specifically prepared and approved for public consumption.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="10cc1-162">Kundendaten</span><span class="sxs-lookup"><span data-stu-id="10cc1-162">Customer data</span></span></td>
<td align="left"><span data-ttu-id="10cc1-p113">Geschäftsdaten, die personenbezogene Informationen enthalten. Beispiele sind Kreditkartennummern, Bankkontonummern und Sozialversicherungsnummern.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p113">Business data that contains personal identifiable information. Examples are credit card numbers, bank account numbers, and social security numbers.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="10cc1-165">Personaldaten</span><span class="sxs-lookup"><span data-stu-id="10cc1-165">HR data</span></span></td>
<td align="left"><span data-ttu-id="10cc1-166">Personaldaten über Contoso-Mitarbeiter, z. B. Mitarbeiternummer und Gehalt.</span><span class="sxs-lookup"><span data-stu-id="10cc1-166">Human Resource data about Contoso employees, such as employee number and salary data.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="10cc1-167">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="10cc1-167">Confidential</span></span></td>
<td align="left"><span data-ttu-id="10cc1-p114">Vertrauliche Geschäftsdaten, die dem Unternehmen schaden können, wenn sie an nicht autorisierte Personen weitergegeben werden. Beispiele hierfür sind Verträge, Sicherheitsberichte, Prognosen und Vertriebsdaten.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p114">Sensitive business data that could cause damage to the business if shared with unauthorized people. Examples include contracts, security reports, forecast summaries, and sales account data.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="10cc1-170">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="10cc1-170">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="10cc1-p115">Streng vertrauliche Geschäftsdaten, die dem Unternehmen schaden, wenn sie an nicht autorisierte Personen weitergegeben werden. Beispiele hierfür sind Mitarbeiter- und Kundeninformationen, Kennwörter, Quellcode und vorangekündigte Finanzberichte.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p115">Very sensitive business data that would cause damage to the business if it was shared with unauthorized people. Examples include employee and customer information, passwords, source code, and pre-announced financial reports.</span></span></td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a><span data-ttu-id="10cc1-173">Definieren von Taxonomie und Suchkriterien für jede Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="10cc1-173">Define a taxonomy and search criteria for each label</span></span>

<span data-ttu-id="10cc1-p116">Nachdem Sie ein Klassifikationsschema für Ihre Organisation entwickelt haben, besteht der nächste Schritt darin, die Taxonomie und Suchkriterien für die Suche nach diesen Daten zu entwickeln. Für personenbezogene Daten haben Sie diese Arbeit durch das Identifizieren von vertraulichen Informationstypen sowie durch Anpassen oder Erstellen neuer vertraulicher Informationstypen für Ihre Umgebung bereits abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p116">After developing a classification schema for your organization, the next step is to develop the taxonomy and search criteria for finding this data. For personal data, you’ve already completed this work by identifying sensitive information types and also by customizing or creating new sensitive information types for your environment.</span></span>

<span data-ttu-id="10cc1-p117">Die folgende Tabelle enthält Beispiele für Schema, Taxonomie und Suchkriterien für eine Organisation. Die Bezeichnungen sind nach Vertraulichkeitsstufe von am wenigsten vertraulich bis streng vertraulich sortiert, um sicherzustellen, dass Daten, die mehreren Bezeichnungsbedingungen entsprechen, der entsprechenden Bezeichnung zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="10cc1-p117">The following table provides an example schema, taxonomy, and search criteria for an organization. The labels are ordered by sensitivity level from least sensitive to most sensitive to ensure that data that matches multiple label conditions is assigned the appropriate label.</span></span>

<span data-ttu-id="10cc1-178">Hinweis: Das Konfigurationsbeispiel dient nur der Veranschaulichung und stellt keine Bereitstellungsanleitung oder Referenz dar.</span><span class="sxs-lookup"><span data-stu-id="10cc1-178">Note: The configuration example is provided for illustration only and is not intended as deployment guidance or reference.</span></span>

<span data-ttu-id="10cc1-179">Die wichtige Schlussfolgerung besteht darin, sicherzustellen, dass die Arbeit, die Sie in die Klassifizierung personenbezogener Daten für die Einhaltung der DSGVO stecken, zu den Zielen für Ihre gesamte Organisation passt.</span><span class="sxs-lookup"><span data-stu-id="10cc1-179">The important takeaway is to ensure that the work you invest to classify personal data for GDPR compliance fits together with the objectives for your entire organization.</span></span>

### <a name="example-schema-taxonomy-and-search-criteria"></a><span data-ttu-id="10cc1-180">Beispiele für Schema, Taxonomie und Suchkriterien</span><span class="sxs-lookup"><span data-stu-id="10cc1-180">Example schema, taxonomy, and search criteria</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="10cc1-181"><strong>Bezeichnung</strong></span><span class="sxs-lookup"><span data-stu-id="10cc1-181"><strong>Label</strong></span></span></th>
<th align="left"><span data-ttu-id="10cc1-182"><strong>Taxonomie</strong></span><span class="sxs-lookup"><span data-stu-id="10cc1-182"><strong>Taxonomy</strong></span></span></th>
<th align="left"><span data-ttu-id="10cc1-183"><strong>Methode</strong></span><span class="sxs-lookup"><span data-stu-id="10cc1-183"><strong>Method</strong></span></span></th>
<th align="left"><span data-ttu-id="10cc1-184"><strong>Suchsyntax</strong></span><span class="sxs-lookup"><span data-stu-id="10cc1-184"><strong>Search syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="10cc1-185">Privat</span><span class="sxs-lookup"><span data-stu-id="10cc1-185">Personal</span></span></td>
<td align="left"><span data-ttu-id="10cc1-186">Manuell vom Endbenutzer als „Privat“ gekennzeichnete Dokumente.</span><span class="sxs-lookup"><span data-stu-id="10cc1-186">Documents manually labelled personal by the end user.</span></span></td>
<td align="left"><span data-ttu-id="10cc1-187">Manuell</span><span class="sxs-lookup"><span data-stu-id="10cc1-187">Manual</span></span></td>
<td align="left"><span data-ttu-id="10cc1-188">Manuell vom Endbenutzer als „Privat“ gekennzeichnete Dokumente.</span><span class="sxs-lookup"><span data-stu-id="10cc1-188">Documents manually labelled personal by the end user.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="10cc1-189">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="10cc1-189">Public</span></span></td>
<td align="left"><span data-ttu-id="10cc1-190">Dokumente, die den Ausdruck „Approved for Public Release  ##/###“ (Genehmigt für öffentliche Freigabe ##/###) enthalten, wobei # eine beliebige Ziffer darstellt. Dabei wird Groß- und Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="10cc1-190">Documents containing the case insensitive phrase Approved for Public Release ##/#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="10cc1-191">KQL</span><span class="sxs-lookup"><span data-stu-id="10cc1-191">KQL</span></span></p>
<p><span data-ttu-id="10cc1-192">RegEx</span><span class="sxs-lookup"><span data-stu-id="10cc1-192">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="10cc1-193">KQL — Approved for Public Release\*</span><span class="sxs-lookup"><span data-stu-id="10cc1-193">KQL — Approved for Public Release\*</span></span></p>
<p><span data-ttu-id="10cc1-194">RegEx – (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="10cc1-194">RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="10cc1-195">Kundendaten</span><span class="sxs-lookup"><span data-stu-id="10cc1-195">Customer data</span></span></td>
<td align="left"><span data-ttu-id="10cc1-196">Typen vertraulicher Informationen für Daten von EU-Bürgern.</span><span class="sxs-lookup"><span data-stu-id="10cc1-196">Sensitive information types for EU citizen data.</span></span></td>
<td align="left"><span data-ttu-id="10cc1-197">Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="10cc1-197">Sensitive information types</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="10cc1-198">Personaldaten – Mitarbeiterdaten</span><span class="sxs-lookup"><span data-stu-id="10cc1-198">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="10cc1-199">Dokumente, die die Mitarbeiter-ID, ohne Berücksichtigung der Kleinschreibung, im Format CONTOSO-9##### enthalten, wobei # eine beliebige Ziffer darstellt.</span><span class="sxs-lookup"><span data-stu-id="10cc1-199">Documents that include the case sensitive employee id in the format CONTOSO-9##### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="10cc1-200">KQL</span><span class="sxs-lookup"><span data-stu-id="10cc1-200">KQL</span></span></p>
<p><span data-ttu-id="10cc1-201">RegEx</span><span class="sxs-lookup"><span data-stu-id="10cc1-201">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="10cc1-202">KQL — CONTOSO-9\*</span><span class="sxs-lookup"><span data-stu-id="10cc1-202">KQL — CONTOSO-9\*</span></span></p>
<p><span data-ttu-id="10cc1-203">RegEx – (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="10cc1-203">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="10cc1-204">Personaldaten – Gehaltsdaten</span><span class="sxs-lookup"><span data-stu-id="10cc1-204">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="10cc1-205">Dokumente, die das Schlüsselwort (ohne Berücksichtigung der Groß-und Kleinschreibung) Contoso UND entweder das Schlüsselwort „Salary“ (Gehalt) (ohne Berücksichtigung der Groß-und Kleinschreibung) ODER „Compensation“ (Entgelt) enthalten</span><span class="sxs-lookup"><span data-stu-id="10cc1-205">Documents that include the keyword (not case sensitive) Contoso AND either keyword (not case sensitive) Salary OR Compensation</span></span></td>
<td align="left"><p><span data-ttu-id="10cc1-206">KQL</span><span class="sxs-lookup"><span data-stu-id="10cc1-206">KQL</span></span></p>
<p><span data-ttu-id="10cc1-207">RegEx</span><span class="sxs-lookup"><span data-stu-id="10cc1-207">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="10cc1-208">KQL — Contoso AND (Salary OR Compensation)</span><span class="sxs-lookup"><span data-stu-id="10cc1-208">KQL — Contoso AND (Salary OR Compensation)</span></span></p>
<p><span data-ttu-id="10cc1-209">RegEx – (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="10cc1-209">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="10cc1-210">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="10cc1-210">Confidential</span></span></td>
<td align="left"><span data-ttu-id="10cc1-211">Dokumente, die den Ausdruck „Contoso Confidential“ (Contoso Vertraulich) (ohne Berücksichtigung der Groß-und Kleinschreibung) enthalten.</span><span class="sxs-lookup"><span data-stu-id="10cc1-211">Documents containing the phrase (not case sensitive) Contoso Confidential.</span></span></td>
<td align="left"><p><span data-ttu-id="10cc1-212">KQL</span><span class="sxs-lookup"><span data-stu-id="10cc1-212">KQL</span></span></p>
<p><span data-ttu-id="10cc1-213">RegEx</span><span class="sxs-lookup"><span data-stu-id="10cc1-213">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="10cc1-214">KQL — Contoso Confidential</span><span class="sxs-lookup"><span data-stu-id="10cc1-214">KQL — Contoso Confidential</span></span></p>
<p><span data-ttu-id="10cc1-215">RegEx — (?i)(\bContoso Confidential\b)</span><span class="sxs-lookup"><span data-stu-id="10cc1-215">RegEx — (?i)(\bContoso Confidential\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="10cc1-216">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="10cc1-216">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="10cc1-217">Dokumente, die entweder den Ausdruck „Contoso Secret“ (Contoso Geheimnis) oder „Secret-C####“ (Geheimnis-C####) (ohne Berücksichtigung der Groß-/Kleinschreibung) enthalten, wobei # eine beliebige Ziffer darstellt.</span><span class="sxs-lookup"><span data-stu-id="10cc1-217">Documents that include either pharase (case sensitive) Contoso Secret or Secret-C#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="10cc1-218">KQL</span><span class="sxs-lookup"><span data-stu-id="10cc1-218">KQL</span></span></p>
<p><span data-ttu-id="10cc1-219">RegEx</span><span class="sxs-lookup"><span data-stu-id="10cc1-219">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="10cc1-220">KQL — Contoso Secret OR Secret-C\*</span><span class="sxs-lookup"><span data-stu-id="10cc1-220">KQL — Contoso Secret OR Secret-C\*</span></span></p>
<p><span data-ttu-id="10cc1-221">RegEx – (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="10cc1-221">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span></span></p></td>
</tr>
</tbody>
</table>
