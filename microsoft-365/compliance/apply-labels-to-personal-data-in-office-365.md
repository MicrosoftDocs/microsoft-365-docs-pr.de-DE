---
title: Anwenden von Bezeichnungen auf personenbezogene Daten in Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
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
description: Erfahren Sie, wie Sie Office-Bezeichnungen im Rahmen Ihres DSGVO-Schutzplans verwenden können.
ms.openlocfilehash: 518e5352861242bfbf9220f876edcb4b616493df
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081144"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a><span data-ttu-id="a3054-103">Anwenden von Bezeichnungen auf personenbezogene Daten in Office 365</span><span class="sxs-lookup"><span data-stu-id="a3054-103">Apply labels to personal data in Office 365</span></span>

 <span data-ttu-id="a3054-104">Verwenden Sie dieses Thema, wenn Sie im Rahmen Ihres DSGVO-Schutzplans Klassifizierungsbezeichnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3054-104">Use this topic if you are using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="a3054-105">Wenn Sie Bezeichnungen zum Schutz persönlicher Daten in Office 365 verwenden, empfiehlt Microsoft, mit [Aufbewahrungsbezeichnungen](labels.md) zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="a3054-105">If you are using labels for protection of personal data in Office 365, Microsoft recommends you start with [retention labels](labels.md).</span></span> <span data-ttu-id="a3054-106">Mit Aufbewahrungsbezeichnungen können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="a3054-106">With retention labels, you can:</span></span>
- <span data-ttu-id="a3054-107">Verwenden Sie die Erweiterte Datenkontrolle, um Bezeichnungen automatisch auf vertrauliche Informationstypen oder andere Kriterien anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="a3054-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
- <span data-ttu-id="a3054-108">Verwenden Sie Aufbewahrungsbezeichnungen mit der Verhinderung von Datenverlust, um einen Schutz anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="a3054-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="a3054-109">Verwenden Sie Bezeichnungen mit eDiscovery und der Inhaltssuche.</span><span class="sxs-lookup"><span data-stu-id="a3054-109">Use labels with eDiscovery and Content Search.</span></span> 

<span data-ttu-id="a3054-110">Cloud App Security unterstützt derzeit keine Aufbewahrungsbezeichnungen, aber Sie können Office 365-Typen für vertrauliche Informationen mit Cloud App Security verwenden, um personenbezogene Daten zu überwachen, die in anderen SaaS-Apps gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a3054-110">Cloud App Security doesn't currently support retention labels, but you can use Office 365 sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="a3054-111">[Vertraulichkeitsbezeichnungen](sensitivity-labels.md) werden derzeit empfohlen, um Bezeichnungen auf lokale Dateien und Dateien in anderen Cloud-Diensten und bei anderen Anbietern anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="a3054-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="a3054-112">Sie werden ebenfalls empfohlen für Dateien in Office 365, die für den Datenschutz eine Azure Informationen Protection-Verschlüsselung benötigen, wie z. B. Dateien mit Betriebsgeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="a3054-112">These are also recommended for files in Office 365 that require Azure Information Protection encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="a3054-113">Zu diesem Zeitpunkt wird die Verwendung der Azure Information Protection-Verschlüsselung nicht für Dateien in Office 365 empfohlen, die der DSGVO unterliegen.</span><span class="sxs-lookup"><span data-stu-id="a3054-113">At this time, using Azure Information Protection to apply encryption is not recommended for files in Office 365 with data that is subject to the GDPR.</span></span> <span data-ttu-id="a3054-114">Office 365-Dienste können derzeit keine AIP-verschlüsselten Dateien lesen.</span><span class="sxs-lookup"><span data-stu-id="a3054-114">Office 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="a3054-115">Aus diesem Grund findet der Dienst keine vertraulichen Daten in diesen Dateien.</span><span class="sxs-lookup"><span data-stu-id="a3054-115">Therefore, the service can’t find sensitive data in these files.</span></span>

<span data-ttu-id="a3054-116">Aufbewahrungsbezeichnungen können in Exchange Online auf E-Mail-Nachrichten angewendet werden, und diese Bezeichnungen verwenden den Schutz vor Datenverlust von Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3054-116">Retention labels can be applied to mail in Exchange Online and these labels work with Office 365 data loss prevention.</span></span> 

![Bezeichnungen in Office 365 und Azure Information Protection](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="a3054-118">In der Darstellung sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a3054-118">In the illustration:</span></span>

-   <span data-ttu-id="a3054-119">Verwenden von Aufbewahrungsbezeichnungen für personenbezogene Daten und streng geregelte Dateien sowie Dateien mit Betriebsgeheimnissen in SharePoint Online und OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="a3054-119">Use retention labels for personal data and for highly regulated & trade secret files in SharePoint Online and OneDrive for Business.</span></span>
-   <span data-ttu-id="a3054-120">Sie können Office 365-Typen für vertrauliche Informationen in Office 365 und mit Cloud App Security verwenden, um personenbezogene Daten zu überwachen, die in anderen SaaS-Apps gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a3054-120">Office 365 sensitive information types can be used within Office 365 and with Cloud App Security to monintor personal data that resides in other SaaS apps.</span></span>
-   <span data-ttu-id="a3054-121">Verwenden von Vertraulichkeitsbezeichnungen für streng geregelte Dateien sowie Dateien mit Betriebsgeheimnissen, Exchange Online-E-Mails, Dateien in anderen SaaS-Diensten, Dateien in lokalen Rechenzentren und Dateien in anderen Cloudanbietern.</span><span class="sxs-lookup"><span data-stu-id="a3054-121">Use sensitivity labels for highly regulated & trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="a3054-122">Verwenden von Aufbewahrungsbezeichnungen und vertraulichen Informationstypen in Microsoft 365 zum Schutz von Informationen</span><span class="sxs-lookup"><span data-stu-id="a3054-122">Use retention labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="a3054-123">Die folgende Abbildung zeigt, wie Aufbewahrungsbezeichnungen und vertrauliche Informationstypen in Bezeichnungsrichtlinien, DLP-Richtlinien und mit Cloud App Security-Richtlinien verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a3054-123">The following illustration shows how retention labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Office-Bezeichnungen und vertrauliche Informationstypen](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="a3054-125">Für Zwecke der Barrierefreiheit enthält die folgende Tabelle die gleichen Beispiele wie die Abbildung.</span><span class="sxs-lookup"><span data-stu-id="a3054-125">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table><span data-ttu-id="a3054-126">
<thead>
<tr class="header">
<th align="left"><strong>Klassifikationselemente</strong></span><span class="sxs-lookup"><span data-stu-id="a3054-126">Classification elements</span></span></th>
<th align="left"><span data-ttu-id="a3054-127"><strong>Bezeichnungsrichtlinien – 2 Beispiele</strong></span><span class="sxs-lookup"><span data-stu-id="a3054-127"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="a3054-128"><strong>DLP-Richtlinien – 2 Beispiele</strong></span><span class="sxs-lookup"><span data-stu-id="a3054-128"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="a3054-129"><strong>Cloud App Security-Richtlinien für alle SaaS-Apps – 1 Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="a3054-129"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr><span data-ttu-id="a3054-130">
</thead>
<tbody>
<tr class="odd">
<td align="left">Aufbewahrungsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="a3054-130">Retention labels.</span></span> <span data-ttu-id="a3054-131">Beispiele: „Privat“, „Öffentlich“, „Kundendaten“, „Personaldaten“, „Vertraulich“, „Streng vertraulich“</span><span class="sxs-lookup"><span data-stu-id="a3054-131">Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="a3054-p105">Diese Bezeichnung automatisch anwenden...</span><span class="sxs-lookup"><span data-stu-id="a3054-p105">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="a3054-135">Kundendaten</span><span class="sxs-lookup"><span data-stu-id="a3054-135">Customer data</span></span></p>
<p><span data-ttu-id="a3054-p106">... auf Dokumente, die folgenden vertraulichen Informationstypen entsprechen...</span><span class="sxs-lookup"><span data-stu-id="a3054-p106">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="a3054-142">&lt;Liste der Beispiele für vertrauliche Informationstypen&gt;</span><span class="sxs-lookup"><span data-stu-id="a3054-142">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3054-p107">Diesen Schutz anwenden...</span><span class="sxs-lookup"><span data-stu-id="a3054-p107">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="a3054-146">&lt;Schutz definieren&gt;</span><span class="sxs-lookup"><span data-stu-id="a3054-146">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="a3054-p108">... auf Dokumente mit dieser Bezeichnung...</span><span class="sxs-lookup"><span data-stu-id="a3054-p108">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="a3054-153">Kundendaten</span><span class="sxs-lookup"><span data-stu-id="a3054-153">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3054-p109">Warnung, wenn Dateien mit diesen Attributen...</span><span class="sxs-lookup"><span data-stu-id="a3054-p109">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="a3054-157">Wählen Sie ein oder mehrere Attribute aus: vordefiniertes PII-Attribut, Office 365-Typ für vertrauliche Informationen, Vertraulichkeitsbezeichnung (AIP), benutzerdefinierter Ausdruck</span><span class="sxs-lookup"><span data-stu-id="a3054-157">Choose one or more attribute: predefined PII attribute, Office 365 sensitive information type, sensitivity label (AIP), custom expression</span></span></p>
<p><span data-ttu-id="a3054-158">.</span><span class="sxs-lookup"><span data-stu-id="a3054-158">.</span></span> <span data-ttu-id="a3054-159">.</span><span class="sxs-lookup"><span data-stu-id="a3054-159">.</span></span> <span data-ttu-id="a3054-160">.</span><span class="sxs-lookup"><span data-stu-id="a3054-160">.</span></span> <span data-ttu-id="a3054-161">in einer beliebigen genehmigten SaaS-App außerhalb der Organisation freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="a3054-161">in any sanctioned SaaS app are shared outside the organization</span></span></p><p><span data-ttu-id="a3054-162">Hinweis: Aufbewahrungsbezeichnungen werden derzeit in Cloud App Security nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3054-162">Note: Retention labels are currently not supported in Cloud App Security.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="a3054-p111">Vertrauliche Informationstypen. Beispiele: Nationale belgische Nummer, Kreditkartennummer, Kroatische ID-Kartennummer, nationale finnische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="a3054-p111">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="a3054-p112">Diese Bezeichnungen für Benutzer zum manuellen Anwenden veröffentlichen...</span><span class="sxs-lookup"><span data-stu-id="a3054-p112">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="a3054-168">&lt;Bezeichnungen wählen&gt;</span><span class="sxs-lookup"><span data-stu-id="a3054-168">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="a3054-p113">... für diese Speicherorte...</span><span class="sxs-lookup"><span data-stu-id="a3054-p113">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="a3054-175">&lt;alle Speicherorte oder bestimmte Speicherorte wählen&gt;</span><span class="sxs-lookup"><span data-stu-id="a3054-175">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3054-p114">Diesen Schutz anwenden...</span><span class="sxs-lookup"><span data-stu-id="a3054-p114">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="a3054-179">&lt;Schutz definieren&gt;</span><span class="sxs-lookup"><span data-stu-id="a3054-179">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="a3054-p115">... auf Dokumente, die folgenden vertraulichen Informationstypen entsprechen&gt;</span><span class="sxs-lookup"><span data-stu-id="a3054-p115">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="a3054-184">Priorisieren automatisch angewendeter Bezeichnungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a3054-184">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="a3054-p116">Für personenbezogene Daten, die der DSGVO unterliegen, wird empfohlen, Bezeichnungen automatisch anzuwenden, indem vertrauliche Informationstypen verwendet werden, die Sie für Ihre Umgebung bereitgestellt haben. Es ist wichtig, dass Richtlinien für das automatische Anwenden von Bezeichnungen gut konzipiert und getestet wurden, damit ein beabsichtigtes Verhalten auftritt.</span><span class="sxs-lookup"><span data-stu-id="a3054-p116">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="a3054-p117">Die Reihenfolge, in der automatisch anzuwendende Richtlinien erstellt werden, sowie, ob Benutzer diese Bezeichnungen auch anwenden, wirkt sich auf das Ergebnis aus. Es ist als wichtig, die Einführung sorgfältig zu planen. Folgendes müssen Sie dazu wissen.</span><span class="sxs-lookup"><span data-stu-id="a3054-p117">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it is important to carefully plan the roll-out. Here’s what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="a3054-189">Jeweils nur eine Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="a3054-189">One label at a time</span></span>

<span data-ttu-id="a3054-190">Sie können einem Dokument jeweils nur eine Bezeichnung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a3054-190">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="a3054-191">Ältere automatisch anzuwendende Richtlinien gelten zuerst</span><span class="sxs-lookup"><span data-stu-id="a3054-191">Older auto-apply policies win</span></span>

<span data-ttu-id="a3054-p118">Wenn es mehrere Regeln gibt, die eine automatisch anzuwendende Bezeichnung zuweisen, und der Inhalt die Bedingungen für mehrere Regeln erfüllt, wird die Bezeichnung für die älteste Regel zugewiesen. Aus diesem Grund ist es wichtig, die Richtlinien für Bezeichnungen sorgfältig zu planen, bevor Sie diese konfigurieren. Wenn für eine Organisation eine Änderung der Priorität der Richtlinien für Bezeichnungen erforderlich ist, müssen die Richtlinien gelöscht und erneut erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a3054-p118">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it is important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they will need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="a3054-195">Manuell von Benutzern angewendete Bezeichnungen sind wichtiger als automatisch angewendete Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="a3054-195">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="a3054-p119">Manuell von Benutzern angewendete Bezeichnungen sind wichtiger als automatisch angewendete Bezeichnungen. Richtlinien für automatisches Anwenden können keine Bezeichnung ersetzen, die bereits von einem Benutzer angewendet wurde. Benutzer können Bezeichnungen ersetzen, die automatisch angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="a3054-p119">Manual user applied labels trump auto-applied labels. Auto-apply policies cannot replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="a3054-199">Automatisch zugewiesene Bezeichnungen können aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="a3054-199">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="a3054-200">Automatisch zugewiesene Bezeichnungen können entweder durch neuere Bezeichnungsrichtlinien oder durch Aktualisierungen vorhandener Richtlinien aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3054-200">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="a3054-201">Achten Sie darauf, dass Ihr Plan für die Implementierung von Bezeichnungen Folgendes umfasst:</span><span class="sxs-lookup"><span data-stu-id="a3054-201">Be sure your plan for implementing labels includes:</span></span>

-   <span data-ttu-id="a3054-202">Priorisieren der Reihenfolge, in der automatisch angewendete Richtlinien erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a3054-202">Prioritizing the order that auto-apply policies are created.</span></span>

-   <span data-ttu-id="a3054-p120">Ausreichend Zeit für das automatische Anwenden von Bezeichnungen, bevor diese für das manuelle Anwenden für Benutzer bereitgestellt werden. Es kann bis zu sieben Tage dauern, bis die Bezeichnungen auf alle Inhalte angewendet werden, die die Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a3054-p120">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="a3054-205">Beispiel für Priorität für das Erstellen von automatisch angewendeten Richtlinien</span><span class="sxs-lookup"><span data-stu-id="a3054-205">Example priority for creating the auto-apply policies</span></span>

<table><span data-ttu-id="a3054-206">
<thead>
<tr class="header">
<th align="left"><strong>Bezeichnungen</strong></span><span class="sxs-lookup"><span data-stu-id="a3054-206">Labels</span></span></th>
<th align="left"><span data-ttu-id="a3054-207"><strong>Prioritätsreihenfolge beim Erstellen von automatisch angewendeten Richtlinien</strong></span><span class="sxs-lookup"><span data-stu-id="a3054-207"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr><span data-ttu-id="a3054-208">
</thead>
<tbody>
<tr class="odd">
<td align="left">Personaldaten – Mitarbeiterdaten</span><span class="sxs-lookup"><span data-stu-id="a3054-208">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="a3054-209">1</span><span class="sxs-lookup"><span data-stu-id="a3054-209">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="a3054-210">Kundendaten</span><span class="sxs-lookup"><span data-stu-id="a3054-210">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="a3054-211">2</span><span class="sxs-lookup"><span data-stu-id="a3054-211">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="a3054-212">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="a3054-212">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="a3054-213">3</span><span class="sxs-lookup"><span data-stu-id="a3054-213">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="a3054-214">Personaldaten – Gehaltsdaten</span><span class="sxs-lookup"><span data-stu-id="a3054-214">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="a3054-215">4</span><span class="sxs-lookup"><span data-stu-id="a3054-215">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="a3054-216">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="a3054-216">Confidential</span></span></td>
<td align="left"><span data-ttu-id="a3054-217">5</span><span class="sxs-lookup"><span data-stu-id="a3054-217">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="a3054-218">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="a3054-218">Public</span></span></td>
<td align="left"><span data-ttu-id="a3054-219">6</span><span class="sxs-lookup"><span data-stu-id="a3054-219">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="a3054-220">Privat</span><span class="sxs-lookup"><span data-stu-id="a3054-220">Personal</span></span></td>
<td align="left"><span data-ttu-id="a3054-221">Keine automatisch angewendete Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a3054-221">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="a3054-222">Erstellen von Bezeichnungen und automatisch angewendeten Bezeichnungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a3054-222">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="a3054-223">Erstellen Sie Bezeichnungen und Richtlinien im Security Center or Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="a3054-223">Create labels and policies in the scurity center or the compliance center.</span></span>

<table><span data-ttu-id="a3054-224">
<thead>
<tr class="header">
<th align="left"><strong>Schritt</strong></span><span class="sxs-lookup"><span data-stu-id="a3054-224">Step</span></span></th>
<th align="left"><span data-ttu-id="a3054-225"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a3054-225"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3054-226">Gewähren von Berechtigungen für Mitglieder Ihres Complianceteams</span><span class="sxs-lookup"><span data-stu-id="a3054-226">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3054-227">Die Mitglieder Ihres Complianceteams, die Bezeichnungen erstellen sollen, benötigen Berechtigungen für das Security Center und/oder das Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="a3054-227">Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center.</span></span> <span data-ttu-id="a3054-228">Gehen Sie im Security Center oder im Compliance Center zu „Berechtigungen“ und ändern Sie die Mitglieder der Gruppe „Complianceadministrator“.</span><span class="sxs-lookup"><span data-stu-id="a3054-228">Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="a3054-229">Einzelheiten hierzu finden Sie unter <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Gewähren des Zugriffs auf das Security Center und/oder Compliance Center</a>.</span><span class="sxs-lookup"><span data-stu-id="a3054-229">See <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Give users access to the security center and/or the compliance center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3054-230">Erstellen Sie Aufbewahrungsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="a3054-230">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="a3054-231">Wechseln Sie im Security Center oder Compliance Center zu „Klassifizierungen“, wählen Sie „Aufbewahrungsbezeichnungen“, und erstellen Sie die Bezeichnungen für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="a3054-231">Go to Classifications in the Security center or the Compliance center, choose Retention labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3054-232">Erstellen automatisch angewendeter Richtlinien für Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="a3054-232">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="a3054-233">Wechseln Sie im Security Center oder Compliance Center zu „Klassifizierungen“, wählen Sie „Bezeichnungsrichtlinien“, und erstellen Sie die Richtlinien für das automatische Anwenden von Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="a3054-233">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels.</span></span> <span data-ttu-id="a3054-234">Achten Sie darauf, diese Richtlinien in der priorisierten Reihenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a3054-234">Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3054-235">Die folgende Abbildung zeigt, wie Sie eine automatisch angewendete Bezeichnung für die Bezeichnung „Kundendaten“ erstellen können.</span><span class="sxs-lookup"><span data-stu-id="a3054-235">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![Erstellen und Anwenden einer Bezeichnung für Kundendaten](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="a3054-237">In der Abbildung sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a3054-237">In the illustration:</span></span>

-   <span data-ttu-id="a3054-238">Die Bezeichnung „Kundendaten“ wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="a3054-238">The “Customer data” label is created.</span></span>

-   <span data-ttu-id="a3054-239">Die gewünschten vertraulichen Informationstypen für die DSGVO werden aufgeführt: Nationale belgische Nummer, Kreditkartennummer, Kroatische ID-Kartennummer, nationale finnische ID-Nummer.</span><span class="sxs-lookup"><span data-stu-id="a3054-239">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

-   <span data-ttu-id="a3054-240">Erstellen einer automatisch angewendeten Richtlinie, die die Bezeichnung „Kundendaten“ jeder Datei zuweist, die einen der vertraulichen Informationstypen enthält, die der Richtlinie hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="a3054-240">Create an auto-apply policy assigns the label “Customer data” to any file that includes one of the sensitive information types that you add to the policy.</span></span>
