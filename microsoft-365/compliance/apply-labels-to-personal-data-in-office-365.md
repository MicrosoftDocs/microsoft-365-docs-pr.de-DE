---
title: Anwenden von Bezeichnungen auf personenbezogene Daten
f1.keywords:
- NOCSH
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
description: Erfahren Sie, wie Sie Office-Bezeichnungen im Rahmen Ihres DSGVO- (Datenschutz-Grundverordnung) Schutzplans verwenden können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7bea2abeaec7a858b3cfc693603c46c0f2a416a
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126816"
---
# <a name="apply-labels-to-personal-data"></a><span data-ttu-id="e6c7e-103">Anwenden von Bezeichnungen auf personenbezogene Daten</span><span class="sxs-lookup"><span data-stu-id="e6c7e-103">Apply labels to personal data</span></span>

 <span data-ttu-id="e6c7e-104">Verwenden Sie dieses Thema, wenn Sie im Rahmen Ihres DSGVO-Schutzplans Klassifizierungsbezeichnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-104">Use this topic if you're using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="e6c7e-105">Wenn Sie Bezeichnungen zum Schutz persönlicher Daten in Microsoft 365 verwenden, empfiehlt Microsoft, mit [Aufbewahrungsbezeichnungen](retention.md#retention-labels) zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-105">If you're using labels for protection of personal data in Microsoft 365, Microsoft recommends you start with [retention labels](retention.md#retention-labels).</span></span> <span data-ttu-id="e6c7e-106">Mit Aufbewahrungsbezeichnungen können Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e6c7e-106">With retention labels, you can:</span></span>
- <span data-ttu-id="e6c7e-107">Verwenden Sie die Erweiterte Datenkontrolle, um Bezeichnungen automatisch auf vertrauliche Informationstypen oder andere Kriterien anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
- <span data-ttu-id="e6c7e-108">Verwenden Sie Aufbewahrungsbezeichnungen mit der Verhinderung von Datenverlust, um einen Schutz anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="e6c7e-109">Verwenden Sie Bezeichnungen mit eDiscovery und der Inhaltssuche.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-109">Use labels with eDiscovery and Content Search.</span></span> 

<span data-ttu-id="e6c7e-110">Cloud App Security unterstützt derzeit keine Aufbewahrungsbezeichnungen, aber Sie können Microsoft 365-Typen für vertrauliche Informationen mit Cloud App Security verwenden, um personenbezogene Daten zu überwachen, die in anderen SaaS-Apps gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-110">Cloud App Security doesn't currently support retention labels, but you can use Microsoft 365 sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="e6c7e-111">[Vertraulichkeitsbezeichnungen](sensitivity-labels.md) werden derzeit empfohlen, um Bezeichnungen auf lokale Dateien und Dateien in anderen Cloud-Diensten und bei anderen Anbietern anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="e6c7e-112">Sie werden ebenfalls empfohlen für Dateien in Microsoft 365, die für den Datenschutz eine Azure Informationen Protection-Verschlüsselung benötigen, wie z. B. Dateien mit Betriebsgeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-112">These are also recommended for files in Microsoft 365 that require Azure Information Protection encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="e6c7e-113">Zu diesem Zeitpunkt wird die Verwendung der Azure Information Protection-Verschlüsselung nicht für Dateien in Microsoft 365 empfohlen, die der DSGVO unterliegen.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-113">At this time, using Azure Information Protection to apply encryption is not recommended for files in Microsoft 365 with data that is subject to the GDPR.</span></span> <span data-ttu-id="e6c7e-114">Microsoft 365-Dienste können derzeit keine AIP-verschlüsselten Dateien lesen.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-114">Microsoft 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="e6c7e-115">Aus diesem Grund findet der Dienst keine vertraulichen Daten in diesen Dateien.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-115">Therefore, the service can't find sensitive data in these files.</span></span>

<span data-ttu-id="e6c7e-116">Aufbewahrungsbezeichnungen können in Exchange Online auf E-Mail-Nachrichten angewendet werden, und diese Bezeichnungen verwenden den Schutz vor Datenverlust von Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-116">Retention labels can be applied to mail in Exchange Online and these labels work with Microsoft 365 data loss prevention.</span></span> 

![Bezeichnungen in Microsoft 365 und Azure Information Protection](../media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="e6c7e-118">In der Abbildung sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e6c7e-118">In the illustration:</span></span>

-   <span data-ttu-id="e6c7e-119">Verwenden von Aufbewahrungsbezeichnungen für personenbezogene Daten und streng geregelte Dateien sowie Dateien mit Betriebsgeheimnissen in SharePoint Online und OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-119">Use retention labels for personal data and for highly regulated and trade secret files in SharePoint Online and OneDrive for Business.</span></span>
-   <span data-ttu-id="e6c7e-120">Sie können Microsoft 365-Typen für vertrauliche Informationen in Microsoft 365 und mit Cloud App Security verwenden, um personenbezogene Daten zu überwachen, die in anderen SaaS-Apps gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-120">Microsoft 365 sensitive information types can be used within Microsoft 365 and with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>
-   <span data-ttu-id="e6c7e-121">Verwenden von Vertraulichkeitsbezeichnungen für streng geregelte Dateien sowie Dateien mit Betriebsgeheimnissen, Exchange Online-E-Mails, Dateien in anderen SaaS-Diensten, Dateien in lokalen Rechenzentren und Dateien in anderen Cloudanbietern.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-121">Use sensitivity labels for highly regulated and trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="e6c7e-122">Verwenden von Aufbewahrungsbezeichnungen und vertraulichen Informationstypen in Microsoft 365 zum Schutz von Informationen</span><span class="sxs-lookup"><span data-stu-id="e6c7e-122">Use retention labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="e6c7e-123">Die folgende Abbildung zeigt, wie Aufbewahrungsbezeichnungen und vertrauliche Informationstypen in Bezeichnungsrichtlinien, DLP-Richtlinien und mit Cloud App Security-Richtlinien verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-123">The following illustration shows how retention labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Office-Bezeichnungen und vertrauliche Informationstypen](../media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="e6c7e-125">Für Zwecke der Barrierefreiheit enthält die folgende Tabelle die gleichen Beispiele wie die Abbildung.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-125">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e6c7e-126"><strong>Klassifikationselemente</strong></span><span class="sxs-lookup"><span data-stu-id="e6c7e-126"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="e6c7e-127"><strong>Bezeichnungsrichtlinien – 2 Beispiele</strong></span><span class="sxs-lookup"><span data-stu-id="e6c7e-127"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="e6c7e-128"><strong>DLP-Richtlinien – 2 Beispiele</strong></span><span class="sxs-lookup"><span data-stu-id="e6c7e-128"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="e6c7e-129"><strong>Cloud App Security-Richtlinien für alle SaaS-Apps – 1 Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="e6c7e-129"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e6c7e-130">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e6c7e-130">Retention labels.</span></span> <span data-ttu-id="e6c7e-131">Beispiele: „Privat“, „Öffentlich“, „Kundendaten“, „Personaldaten“, „Vertraulich“, „Streng vertraulich“</span><span class="sxs-lookup"><span data-stu-id="e6c7e-131">Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="e6c7e-132">Auto apply this label .</span><span class="sxs-lookup"><span data-stu-id="e6c7e-132">Auto apply this label .</span></span> <span data-ttu-id="e6c7e-133">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-133">.</span></span> <span data-ttu-id="e6c7e-134">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-134">.</span></span></p>
<p><span data-ttu-id="e6c7e-135">Kundendaten</span><span class="sxs-lookup"><span data-stu-id="e6c7e-135">Customer data</span></span></p>
<p><span data-ttu-id="e6c7e-136">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-136">.</span></span> <span data-ttu-id="e6c7e-137">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-137">.</span></span> <span data-ttu-id="e6c7e-138">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-138">.</span></span> <span data-ttu-id="e6c7e-139">to documents that match these sensitive information types .</span><span class="sxs-lookup"><span data-stu-id="e6c7e-139">to documents that match these sensitive information types .</span></span> <span data-ttu-id="e6c7e-140">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-140">.</span></span> <span data-ttu-id="e6c7e-141">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-141">.</span></span></p>
<p><span data-ttu-id="e6c7e-142">&lt;Liste der Beispiele für vertrauliche Informationstypen&gt;</span><span class="sxs-lookup"><span data-stu-id="e6c7e-142">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6c7e-143">Apply this protection .</span><span class="sxs-lookup"><span data-stu-id="e6c7e-143">Apply this protection .</span></span> <span data-ttu-id="e6c7e-144">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-144">.</span></span> <span data-ttu-id="e6c7e-145">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-145">.</span></span></p>
<p><span data-ttu-id="e6c7e-146">&lt;Schutz definieren&gt;</span><span class="sxs-lookup"><span data-stu-id="e6c7e-146">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="e6c7e-147">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-147">.</span></span> <span data-ttu-id="e6c7e-148">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-148">.</span></span> <span data-ttu-id="e6c7e-149">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-149">.</span></span> <span data-ttu-id="e6c7e-150">to documents with this label .</span><span class="sxs-lookup"><span data-stu-id="e6c7e-150">to documents with this label .</span></span> <span data-ttu-id="e6c7e-151">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-151">.</span></span> <span data-ttu-id="e6c7e-152">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-152">.</span></span></p>
<p><span data-ttu-id="e6c7e-153">Kundendaten</span><span class="sxs-lookup"><span data-stu-id="e6c7e-153">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6c7e-154">Alert when files with these attributes .</span><span class="sxs-lookup"><span data-stu-id="e6c7e-154">Alert when files with these attributes .</span></span> <span data-ttu-id="e6c7e-155">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-155">.</span></span> <span data-ttu-id="e6c7e-156">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-156">.</span></span></p>
<p><span data-ttu-id="e6c7e-157">Wählen Sie ein oder mehrere Attribute aus: vordefiniertes PII-Attribut, Microsoft 365-Typ für vertrauliche Informationen, Vertraulichkeitsbezeichnung (AIP), benutzerdefinierter Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e6c7e-157">Choose one or more attributes: predefined PII attribute, Microsoft 365 sensitive information type, sensitivity label (AIP), custom expression</span></span></p>
<p><span data-ttu-id="e6c7e-158">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-158">.</span></span> <span data-ttu-id="e6c7e-159">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-159">.</span></span> <span data-ttu-id="e6c7e-160">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-160">.</span></span> <span data-ttu-id="e6c7e-161">in einer beliebigen genehmigten SaaS-App außerhalb der Organisation freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="e6c7e-161">in any sanctioned SaaS app are shared outside the organization</span></span></p><p><span data-ttu-id="e6c7e-162">Hinweis: Aufbewahrungsbezeichnungen werden derzeit in Cloud App Security nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-162">Note: Retention labels are currently not supported in Cloud App Security.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e6c7e-163">Sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-163">Sensitive information types.</span></span> <span data-ttu-id="e6c7e-164">Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span><span class="sxs-lookup"><span data-stu-id="e6c7e-164">Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="e6c7e-165">Publish these labels for users to manually apply .</span><span class="sxs-lookup"><span data-stu-id="e6c7e-165">Publish these labels for users to manually apply .</span></span> <span data-ttu-id="e6c7e-166">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-166">.</span></span> <span data-ttu-id="e6c7e-167">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-167">.</span></span></p>
<p><span data-ttu-id="e6c7e-168">&lt;Bezeichnungen wählen&gt;</span><span class="sxs-lookup"><span data-stu-id="e6c7e-168">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="e6c7e-169">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-169">.</span></span> <span data-ttu-id="e6c7e-170">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-170">.</span></span> <span data-ttu-id="e6c7e-171">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-171">.</span></span> <span data-ttu-id="e6c7e-172">to these locations .</span><span class="sxs-lookup"><span data-stu-id="e6c7e-172">to these locations .</span></span> <span data-ttu-id="e6c7e-173">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-173">.</span></span> <span data-ttu-id="e6c7e-174">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-174">.</span></span></p>
<p><span data-ttu-id="e6c7e-175">&lt;alle Speicherorte oder bestimmte Speicherorte wählen&gt;</span><span class="sxs-lookup"><span data-stu-id="e6c7e-175">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6c7e-176">Apply this protection .</span><span class="sxs-lookup"><span data-stu-id="e6c7e-176">Apply this protection .</span></span> <span data-ttu-id="e6c7e-177">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-177">.</span></span> <span data-ttu-id="e6c7e-178">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-178">.</span></span></p>
<p><span data-ttu-id="e6c7e-179">&lt;Schutz definieren&gt;</span><span class="sxs-lookup"><span data-stu-id="e6c7e-179">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="e6c7e-180">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-180">.</span></span> <span data-ttu-id="e6c7e-181">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-181">.</span></span> <span data-ttu-id="e6c7e-182">.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-182">.</span></span> <span data-ttu-id="e6c7e-183">to documents that match these sensitive information types&gt;</span><span class="sxs-lookup"><span data-stu-id="e6c7e-183">to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="e6c7e-184">Priorisieren automatisch angewendeter Bezeichnungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="e6c7e-184">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="e6c7e-185">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-185">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment.</span></span> <span data-ttu-id="e6c7e-186">It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-186">It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="e6c7e-187">The order that auto-apply policies are created and whether users are also applying these labels affect the result.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-187">The order that auto-apply policies are created and whether users are also applying these labels affect the result.</span></span> <span data-ttu-id="e6c7e-188">So, it's important to carefully plan the roll-out. Here's what you need to know.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-188">So, it's important to carefully plan the roll-out. Here's what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="e6c7e-189">Jeweils nur eine Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="e6c7e-189">One label at a time</span></span>

<span data-ttu-id="e6c7e-190">Sie können einem Dokument jeweils nur eine Bezeichnung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-190">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="e6c7e-191">Ältere automatisch anzuwendende Richtlinien gelten zuerst</span><span class="sxs-lookup"><span data-stu-id="e6c7e-191">Older auto-apply policies win</span></span>

<span data-ttu-id="e6c7e-192">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-192">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned.</span></span> <span data-ttu-id="e6c7e-193">For this reason, it's important to plan the label policies carefully before configuring them.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-193">For this reason, it's important to plan the label policies carefully before configuring them.</span></span> <span data-ttu-id="e6c7e-194">If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-194">If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="e6c7e-195">Manuell von Benutzern angewendete Bezeichnungen sind wichtiger als automatisch angewendete Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e6c7e-195">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="e6c7e-196">Manual user applied labels trump auto-applied labels.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-196">Manual user applied labels trump auto-applied labels.</span></span> <span data-ttu-id="e6c7e-197">Auto-apply policies can't replace a label that is already applied by a user.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-197">Auto-apply policies can't replace a label that is already applied by a user.</span></span> <span data-ttu-id="e6c7e-198">Users can replace labels that are auto-applied.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-198">Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="e6c7e-199">Automatisch zugewiesene Bezeichnungen können aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="e6c7e-199">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="e6c7e-200">Automatisch zugewiesene Bezeichnungen können entweder durch neuere Bezeichnungsrichtlinien oder durch Aktualisierungen vorhandener Richtlinien aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-200">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="e6c7e-201">Achten Sie darauf, dass Ihr Plan für die Implementierung von Bezeichnungen Folgendes umfasst:</span><span class="sxs-lookup"><span data-stu-id="e6c7e-201">Be sure your plan for implementing labels includes:</span></span>

- <span data-ttu-id="e6c7e-202">Priorisieren der Reihenfolge, in der automatisch angewendete Richtlinien erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-202">Prioritizing the order that auto-apply policies are created.</span></span>

- <span data-ttu-id="e6c7e-203">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-203">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply.</span></span> <span data-ttu-id="e6c7e-204">It can take up to seven days for the labels to be applied to all content that matches the conditions.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-204">It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="e6c7e-205">Beispiel für Priorität für das Erstellen von automatisch angewendeten Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e6c7e-205">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e6c7e-206"><strong>Bezeichnungen</strong></span><span class="sxs-lookup"><span data-stu-id="e6c7e-206"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="e6c7e-207"><strong>Prioritätsreihenfolge beim Erstellen von automatisch angewendeten Richtlinien</strong></span><span class="sxs-lookup"><span data-stu-id="e6c7e-207"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e6c7e-208">Personaldaten – Mitarbeiterdaten</span><span class="sxs-lookup"><span data-stu-id="e6c7e-208">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="e6c7e-209">1</span><span class="sxs-lookup"><span data-stu-id="e6c7e-209">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e6c7e-210">Kundendaten</span><span class="sxs-lookup"><span data-stu-id="e6c7e-210">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="e6c7e-211">2</span><span class="sxs-lookup"><span data-stu-id="e6c7e-211">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e6c7e-212">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="e6c7e-212">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="e6c7e-213">3</span><span class="sxs-lookup"><span data-stu-id="e6c7e-213">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e6c7e-214">Personaldaten – Gehaltsdaten</span><span class="sxs-lookup"><span data-stu-id="e6c7e-214">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="e6c7e-215">4</span><span class="sxs-lookup"><span data-stu-id="e6c7e-215">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e6c7e-216">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="e6c7e-216">Confidential</span></span></td>
<td align="left"><span data-ttu-id="e6c7e-217">5</span><span class="sxs-lookup"><span data-stu-id="e6c7e-217">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e6c7e-218">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="e6c7e-218">Public</span></span></td>
<td align="left"><span data-ttu-id="e6c7e-219">6</span><span class="sxs-lookup"><span data-stu-id="e6c7e-219">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e6c7e-220">Privat</span><span class="sxs-lookup"><span data-stu-id="e6c7e-220">Personal</span></span></td>
<td align="left"><span data-ttu-id="e6c7e-221">Keine automatisch angewendete Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e6c7e-221">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="e6c7e-222">Erstellen von Bezeichnungen und automatisch angewendeten Bezeichnungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="e6c7e-222">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="e6c7e-223">Erstellen Sie Bezeichnungen und Richtlinien im Security Center oder Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-223">Create labels and policies in the security center or the compliance center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e6c7e-224"><strong>Schritt</strong></span><span class="sxs-lookup"><span data-stu-id="e6c7e-224"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="e6c7e-225"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="e6c7e-225"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e6c7e-226">Gewähren von Berechtigungen für Mitglieder Ihres Complianceteams</span><span class="sxs-lookup"><span data-stu-id="e6c7e-226">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e6c7e-227">Die Mitglieder Ihres Complianceteams, die Bezeichnungen erstellen sollen, benötigen Berechtigungen für das Security Center und/oder das Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-227">Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center.</span></span> <span data-ttu-id="e6c7e-228">Gehen Sie im Security Center oder im Compliance Center zu „Berechtigungen“ und ändern Sie die Mitglieder der Gruppe „Complianceadministrator“.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-228">Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="e6c7e-229">Einzelheiten hierzu finden Sie unter <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Gewähren des Zugriffs auf das Security Center und/oder Compliance Center</a>.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-229">See <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Give users access to the security center and/or the compliance center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e6c7e-230">Erstellen Sie Aufbewahrungsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-230">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="e6c7e-231">Wechseln Sie im Security Center oder Compliance Center zu „Klassifizierungen“, wählen Sie „Aufbewahrungsbezeichnungen“, und erstellen Sie die Bezeichnungen für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-231">Go to Classifications in the Security center or the Compliance center, choose Retention labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e6c7e-232">Erstellen automatisch angewendeter Richtlinien für Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e6c7e-232">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="e6c7e-233">Wechseln Sie im Security Center oder Compliance Center zu „Klassifizierungen“, wählen Sie „Bezeichnungsrichtlinien“, und erstellen Sie die Richtlinien für das automatische Anwenden von Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-233">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels.</span></span> <span data-ttu-id="e6c7e-234">Achten Sie darauf, diese Richtlinien in der priorisierten Reihenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-234">Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e6c7e-235">Die folgende Abbildung zeigt, wie Sie eine automatisch angewendete Bezeichnung für die Bezeichnung „Kundendaten“ erstellen können.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-235">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![Erstellen und Anwenden einer Bezeichnung für Kundendaten](../media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="e6c7e-237">In der Abbildung sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e6c7e-237">In the illustration:</span></span>

- <span data-ttu-id="e6c7e-238">Die Bezeichnung „Kundendaten“ wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-238">The "Customer data" label is created.</span></span>

- <span data-ttu-id="e6c7e-239">Die gewünschten vertraulichen Informationstypen für die DSGVO werden aufgeführt: Nationale belgische Nummer, Kreditkartennummer, Kroatische ID-Kartennummer, nationale finnische ID-Nummer.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-239">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

- <span data-ttu-id="e6c7e-240">Erstellen einer automatisch angewendeten Richtlinie, die die Bezeichnung „Kundendaten“ jeder Datei zuweist, die einen der vertraulichen Informationstypen enthält, die der Richtlinie hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="e6c7e-240">Create an auto-apply policy assigns the label "Customer data" to any file that includes one of the sensitive information types that you add to the policy.</span></span>
