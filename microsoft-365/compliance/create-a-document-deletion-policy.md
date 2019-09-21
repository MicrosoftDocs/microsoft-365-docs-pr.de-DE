---
title: Erstellen einer Dokumentlöschrichtlinie
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: Organisationen müssen häufig Dokumente aufgrund von Konformitäts-, rechtlicher und anderer Bestimmungen für einen bestimmten Zeitraum aufbewahren. Wenn Dokumente aber länger als nötig aufbewahrt werden, kann dies für die Organisation rechtliche Folgen haben.
ms.openlocfilehash: e8f85f4cc9ae541d8a962dfb270e5216c912ac7d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37080945"
---
# <a name="create-a-document-deletion-policy"></a><span data-ttu-id="7e98f-104">Erstellen einer Dokumentlöschrichtlinie</span><span class="sxs-lookup"><span data-stu-id="7e98f-104">Create a document deletion policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e98f-105">Wir empfehlen die Verwendung einer Aufbewahrungsrichtlinie oder von Aufbewahrungs Bezeichnungen, die im Microsoft 365 Compliance Center, im Microsoft 365 Security Center oder im Office 365 Security &amp; Compliance Center anstelle einer Dokument Löschungs Richtlinie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-105">Moving forward, we recommend that you use a retention policy or retention labels created in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security &amp; Compliance Center instead of a document deletion policy.</span></span> <span data-ttu-id="7e98f-106">Dokument Löschungsrichtlinien funktionieren weiterhin nebeneinander mit Aufbewahrungsrichtlinien, wenn Sie jedoch Inhalte an einer beliebigen Stelle in Office 365 beibehalten oder löschen müssen, wird empfohlen, eine Aufbewahrungsrichtlinie zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-106">Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy.</span></span> <span data-ttu-id="7e98f-107">Weitere Informationen finden Sie unter [Verwenden einer Aufbewahrungsrichtlinie anstelle dieser Features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span><span class="sxs-lookup"><span data-stu-id="7e98f-107">For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span> 
  
<span data-ttu-id="7e98f-p103">Organisationen müssen häufig Dokumente aufgrund von Konformitäts-, rechtlicher und anderer Bestimmungen für einen bestimmten Zeitraum aufbewahren. Wenn Dokumente aber länger als nötig aufbewahrt werden, kann dies für die Organisation rechtliche Folgen haben.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p103">Organizations are often required to retain documents for a certain period of time due to compliance, legal, or other regulations. However, retaining documents for longer than required can expose the organization to legal risk.</span></span>
  
<span data-ttu-id="7e98f-110">Mit einer Richtlinie zum Löschen von Dokumenten können Sie das Risiko proaktiv verringern, indem Sie Dokumente in einer Website nach einem bestimmten Zeitraum löschen (beispielsweise können Sie fünf Jahre nach dem Erstellen der Dokumente die OneDrive für Unternehmen Websites von Benutzern löschen.</span><span class="sxs-lookup"><span data-stu-id="7e98f-110">With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span> 
  
<span data-ttu-id="7e98f-p104">Nach dem Erstellen einer Dokumentlöschrichtlinie können Sie sie einer Vorlage für Websitesammlung zuweisen, damit die Richtlinie für alle Websitesammlungen, die aus dieser Vorlage erstellt werden, verfügbar ist. Sie können außerdem einer bestimmten Websitesammlung eine Richtlinie zuweisen, die alle Richtlinien, die der Vorlage für diese Websitesammlung möglicherweise schon zugewiesen wurden, außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p104">After you create a document deletion policy, you can assign it to a site collection template, so that the policy is available to all site collections created from that template. You can also assign a policy to a specific a site collection, which overrides any policies that may have been assigned to the template for that site collection.</span></span>
  
![Startseite des Dokument Löschrichtlinien Centers](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a><span data-ttu-id="7e98f-114">Richtlinienvorlagen</span><span class="sxs-lookup"><span data-stu-id="7e98f-114">Policy templates</span></span>

<span data-ttu-id="7e98f-p105">Sie können eine Dokumentlöschrichtlinie von Grund auf neu erstellen oder eine unserer Beispielrichtlinien verwenden. Im Compliance Policy Center finden Sie Beispielrichtlinien, die Sie entweder sofort verwenden oder als Ausgangsbasis verwenden und umbenennen oder ändern können.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p105">You can create a document deletion policy from scratch, or you can use one of the sample policies. The Compliance Policy Center includes sample policies that you can use as is, or you can use them as a starting point and then rename or modify them.</span></span>
  
![Beispiele für Dokument Löschungsrichtlinien](media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a><span data-ttu-id="7e98f-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7e98f-118">Examples of how to use document deletion policies</span></span>

<span data-ttu-id="7e98f-119">Einer Websitesammlung oder einer websitesammlungsvorlage kann eine weitere Richtlinie zugewiesen sein, und jede dieser Richtlinien kann eine oder mehrere Regeln haben.</span><span class="sxs-lookup"><span data-stu-id="7e98f-119">A site collection or a site collection template can have one more policies assigned to it, and each of those policies can have one or more rules.</span></span> <span data-ttu-id="7e98f-120">Es kann jedoch nur eine Richtlinie pro Standort aktiv sein, und es kann immer nur eine Löschregel für die Bibliotheken innerhalb der Website aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="7e98f-120">However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![Diagramm mit Beziehung zwischen Richtlinien](media/IP-Two-policies-four-rules.png)
  
<span data-ttu-id="7e98f-122">Außerdem können Sie eine Richtlinie als obligatorisch oder Standard und eine Löschregel als Standardregel auswählen:</span><span class="sxs-lookup"><span data-stu-id="7e98f-122">In addition, you can select a policy as mandatory or default, and you can select a deletion rule as a default rule:</span></span> 
  
- <span data-ttu-id="7e98f-123">**Verbindliche Richtlinie** Wenn eine Richtlinie als obligatorisch gekennzeichnet ist, kann der Websitesammlung oder Vorlage nur eine Richtlinie zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-123">**Mandatory policy**When a policy is marked as mandatory, only one policy can be assigned to the site collection or template.</span></span> <span data-ttu-id="7e98f-124">Die Richtlinie muss als Standard gekennzeichnet sein und wird auf alle Websites angewendet.</span><span class="sxs-lookup"><span data-stu-id="7e98f-124">The policy must be marked as default and will be applied to all sites.</span></span> <span data-ttu-id="7e98f-125">Websitebesitzer können die Richtlinie nicht abwählen.</span><span class="sxs-lookup"><span data-stu-id="7e98f-125">Site owners cannot opt out of the policy.</span></span>
    
- <span data-ttu-id="7e98f-126">**Standardrichtlinie** Wenn eine Richtlinie als Standard festgelegt ist, ist die Richtlinie automatisch in allen Websites aktiv, denen Sie zugewiesen ist, ohne dass der Websitebesitzer eine Aktion benötigt.</span><span class="sxs-lookup"><span data-stu-id="7e98f-126">**Default policy**When a policy is set as default, the policy is automatically active in all sites that it's assigned to with no action required by site owner.</span></span>
    
- <span data-ttu-id="7e98f-127">**Standardregel** Wenn eine Löschregel als Standard festgelegt ist, wird Sie automatisch auf alle Bibliotheken in den Websites angewendet, in denen die Richtlinie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7e98f-127">**Default rule**When a deletion rule is set as default, it is automatically applied to all libraries in the sites that use the policy.</span></span>
    
<span data-ttu-id="7e98f-128">Die folgenden Beispiele erläutern, wann Sie möglicherweise eine obligatorische Richtlinie oder Standardrichtlinien und -regeln verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="7e98f-128">The following examples explain when you might want to use a mandatory policy or default policies and rules.</span></span>
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a><span data-ttu-id="7e98f-129">Beispiel 1: Anwenden einer einzelnen Richtlinie mit einer einzelnen Regel auf eine Vorlage für Websitesammlung</span><span class="sxs-lookup"><span data-stu-id="7e98f-129">Example 1: Apply a single policy with a single rule to a site collection template</span></span>

<span data-ttu-id="7e98f-p108">Angenommen, Sie möchten eine Dokumentlöschrichtlinie für eine vielfältige Reihe von unstrukturierten Inhalten erzwingen, z. B. alle Websites von OneDrive for Business oder alle Teamwebsites. Wenn Sie sicherstellen möchten, dass eine einzelne Dokumentlöschrichtlinie auf allen Websites aktiv ist, die von einer Vorlage für Websitesammlung erstellt wurde, können Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="7e98f-p108">You may want to enforce a document deletion policy across a broad range of unstructured content, such as all OneDrive for Business sites or all team sites. If you want to ensure that a single document deletion policy is active in all sites created from a site collection template, you can:</span></span>
  
1. <span data-ttu-id="7e98f-132">Erstellen Sie eine einzelne Richtlinie mit einer einzelnen Standardlöschregel.</span><span class="sxs-lookup"><span data-stu-id="7e98f-132">Create a single policy with a single default deletion rule.</span></span>
    
2. <span data-ttu-id="7e98f-133">Legen Sie die Richtlinie als obligatorisch und Standard fest.</span><span class="sxs-lookup"><span data-stu-id="7e98f-133">Set the policy as mandatory and default.</span></span>
    
3. <span data-ttu-id="7e98f-134">Weisen Sie die Richtlinie einer Vorlage für Websitesammlung zu.</span><span class="sxs-lookup"><span data-stu-id="7e98f-134">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="7e98f-p109">In diesem Beispiel wird die Standardlöschregel auf alle Bibliotheken in allen Websitesammlungen angewendet, die aufgrund der Vorlage erstellt wurden, und die Websitebesitzer können die Richtlinie nicht abwählen. Dies ist die einfachste Möglichkeit, um eine Dokumentlöschrichtlinie umfassend und strikt zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p109">In this example, the default deletion rule will be applied to all libraries in all site collections created from the template, and site owners cannot opt out of the policy. This is the simplest way to broadly and rigidly enforce a document deletion policy.</span></span>
  
![Diagramm mit einer einzelnen verbindlichen Richtlinie](media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a><span data-ttu-id="7e98f-138">Beispiel 2: Anwenden einer einzelnen Richtlinie mit mehreren Regeln auf eine websitesammlungsvorlage</span><span class="sxs-lookup"><span data-stu-id="7e98f-138">Example 2: Apply a single policy with several rules to a site collection template</span></span>

<span data-ttu-id="7e98f-p110">Websitebesitzer wissen oft am besten, welche Art von Inhalten ihre Website enthält, sodass Sie Websitebesitzern die Auswahl der für ihre Website am besten geeigneten Löschregel ermöglichen können. Sie können auch zulassen, dass Websitebesitzer die Richtlinie ganz abwählen.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p110">Site owners often know best what type of content their site contains, so you may choose to allow site owners to select the deletion rule that best applies to their site. You may also want to allow site owners to opt out of a policy entirely.</span></span>
  
<span data-ttu-id="7e98f-p111">Auch dann können Sie die Richtlinien noch zentral erstellen und verwalten. Sie können auch eine Richtlinie und Regel als den Standard auswählen, sodass eine Richtlinie so lange aktiv ist, bis der Websitebesitzer eine andere auswählt oder die Richtlinie abwählt. Wenn Sie Websitebesitzern diese Flexibilität bieten möchten, können Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="7e98f-p111">At the same time, you can still centrally create and manage the policies. You can also select one policy and rule as the default, so that a policy is always in effect until the site owner chooses a different one or opts out. If you want to provide such flexibility to site owners, you can:</span></span>
  
1. <span data-ttu-id="7e98f-143">Erstellen Sie eine einzelne Richtlinie mit mehreren Löschregeln, und legen Sie eine Regel als den Standard fest.</span><span class="sxs-lookup"><span data-stu-id="7e98f-143">Create a single policy with several deletion rules, and set one rule as the default.</span></span>
    
2. <span data-ttu-id="7e98f-144">Legen Sie die Richtlinie als die Standardrichtlinie fest.</span><span class="sxs-lookup"><span data-stu-id="7e98f-144">Set the policy as the default policy.</span></span>
    
3. <span data-ttu-id="7e98f-145">Weisen Sie die Richtlinie einer Vorlage für Websitesammlung zu.</span><span class="sxs-lookup"><span data-stu-id="7e98f-145">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="7e98f-146">Websitebesitzer können eine der alternativen Löschregeln auswählen, die Richtlinie abwählen oder nichts unternehmen und die Standardrichtlinie und -regel übernehmen.</span><span class="sxs-lookup"><span data-stu-id="7e98f-146">Site owners can select one of the alternate deletion rules, opt out of the policy, or do nothing and be subject to the default policy and rule.</span></span>
  
![Diagramm, das eine Richtlinie mit vielen Regeln zeigt](media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a><span data-ttu-id="7e98f-148">Beispiel 3: Anwenden mehrerer Richtlinien mit mindestens einer Regel auf eine Websitesammlung</span><span class="sxs-lookup"><span data-stu-id="7e98f-148">Example 3: Apply several policies with one or more rules to a site collection</span></span>

<span data-ttu-id="7e98f-p112">In diesem Beispiel haben Websitebesitzer die höchste Flexibilität, weil sie aus mehreren Richtlinien auswählen und nach der Auswahl einer Richtlinie oft aus mehreren Regeln auswählen können. Eine Richtlinie und eine Regel sind als der Standard festgelegt, sodass eine Richtlinie so lange aktiv ist, bis der Websitebesitzer eine andere auswählt oder die Richtlinie abwählt. Beachten Sie Folgendes: Wenn Sie keine Richtlinie und Regel als Standard festlegen, sind auf der Website keine Richtlinien oder Regeln für die Dokumentbibliotheken aktiv, bis der Websitebesitzer eine Aktion durchführt, um sie auszuwählen und anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p112">This example provides the maximum flexibility to site owners because they can choose from several policies, and after selecting a policy they can often choose from several rules. One policy and rule are set as default, so that a policy is always in effect until the site owner chooses a different one or opts out. Note that if you do not set a policy and rule as the default, then no policies or rules will be active for the document libraries in the site until the site owner takes action to select and apply them.</span></span>
  
<span data-ttu-id="7e98f-p113">Im Unterschied zu den vorherigen beiden Beispielen werden diese Richtlinien einer bestimmten Websitesammlung zugewiesen, nicht der Vorlage für Websitesammlung. Die Richtlinien können also gezielter für den Inhalt in einer bestimmten Websitesammlung angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p113">Unlike the previous two examples, these policies are assigned to a specific site collection — not the site collection template. This means the policies can be more specifically tailored for the content in a specific site collection.</span></span>
  
<span data-ttu-id="7e98f-p114">Richtlinien und Regeln werden vererbt. Websitebesitzer können für ihre Website eine Richtlinie und Regel auswählen, und alle Unterwebsites erben die Richtlinie von der übergeordneten Website. Ein Besitzer einer Unterwebsite kann aber die Vererbung aufheben, indem er eine andere Richtlinie und Regel auswählt, die wiederum für alle Unterwebsites gilt, bis die Vererbung wieder aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p114">Policies and rules are inherited. Site owners can select a policy and rule for their site, and all subsites inherit the policy from the parent. However, an owner of a subsite can break inheritance by selecting a different policy and rule, which in turn applies to all subsites until inheritance is broken again.</span></span>
  
<span data-ttu-id="7e98f-156">Um dieses Szenario einzurichten, können Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="7e98f-156">To set up this scenario, you can:</span></span>
  
1. <span data-ttu-id="7e98f-157">Erstellen Sie mehrere Richtlinien, die jeweils mindestens eine Regel enthalten.</span><span class="sxs-lookup"><span data-stu-id="7e98f-157">Create several policies that each contains one or more rules.</span></span>
    
2. <span data-ttu-id="7e98f-158">Legen Sie eine Richtlinie und Regel als den Standard fest.</span><span class="sxs-lookup"><span data-stu-id="7e98f-158">Set a policy and rule as the default.</span></span>
    
3. <span data-ttu-id="7e98f-159">Weisen Sie die Richtlinien einer bestimmten Websitesammlung zu.</span><span class="sxs-lookup"><span data-stu-id="7e98f-159">Assign the policies to a specific site collection.</span></span>
    
<span data-ttu-id="7e98f-160">Außerdem werden die Richtlinien und Regeln für eine bestimmte Websitesammlung angepasst, bei der die Websitebesitzer die Vererbung aufheben können, indem sie die Richtlinie und Regel auswählen, die sich am besten für ihre Website eignet.</span><span class="sxs-lookup"><span data-stu-id="7e98f-160">In addition, the policies and rules are tailored to a specific site collection, where site owners can break inheritance by selecting the policy and rule that best applies to their site.</span></span>
  
![Diagramm mit vielen Richtlinien und Regeln](media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a><span data-ttu-id="7e98f-162">Erstellen einer Dokumentlöschrichtlinie</span><span class="sxs-lookup"><span data-stu-id="7e98f-162">Create a document deletion policy</span></span>

1. <span data-ttu-id="7e98f-163">Navigieren Sie im Office &amp; 365Security Compliance Center zur **Aufbewahrung**der **Datenverwaltung** \> .</span><span class="sxs-lookup"><span data-stu-id="7e98f-163">In the Office 365Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="7e98f-164">Klicken Sie unter **Löschen**auf **Dokument Löschrichtlinien für SharePoint Online und OneDrive für Unternehmen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-164">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="7e98f-165">Das Document Deletion Policy Center wird auf einer neuen Registerkarte im Browser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7e98f-165">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
    <span data-ttu-id="7e98f-166">Wenn Sie zum ersten Mal vom Security &amp; Compliance Center zum Dokument Löschrichtlinien Center navigieren, wird das Richtlinien Center automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="7e98f-166">The first time you navigate from the Security &amp; Compliance Center to the Document Deletion Policy Center, the policy center is automatically created for you.</span></span> <span data-ttu-id="7e98f-167">Alternativ können Sie das Richtlinien Center manuell erstellen, indem Sie [die Websitesammlung erstellen](http://go.microsoft.com/fwlink/p/?LinkID=404342) und auf der Registerkarte **Enterprise** die Option **Compliance Policy Center** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7e98f-167">Alternatively, you can manually create the policy center by [creating the site collection](http://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab.</span></span> 
    
2. <span data-ttu-id="7e98f-168">Wählen Sie **Löschrichtlinien**aus.</span><span class="sxs-lookup"><span data-stu-id="7e98f-168">Choose **Deletion Policies**.</span></span>
    
    ![Löschrichtlinien (Option)](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="7e98f-170">Wählen Sie **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="7e98f-170">Choose **new item**.</span></span>
    
4. <span data-ttu-id="7e98f-p117">Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein. Websitebesitzer wählen eine Richtlinie möglicherweise aufgrund ihres Namens und ihrer Beschreibung aus. Geben Sie daher ausreichende Informationen an, damit sie die richtige Richtlinie auswählen können.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p117">Enter a policy name and description. Site owners may be selecting a policy for their site based on this name and description, so include enough information for them to choose the correct policy.</span></span>
    
5. <span data-ttu-id="7e98f-173">Um eine Regel zu erstellen, wählen Sie **Neu** aus.</span><span class="sxs-lookup"><span data-stu-id="7e98f-173">To create a rule, choose **New**.</span></span>
    
6. <span data-ttu-id="7e98f-174">Geben Sie einen Namen ein, und wählen Sie die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="7e98f-174">Enter a name and choose the following options:</span></span>
    
  - <span data-ttu-id="7e98f-175">Wählen Sie aus, ob die Regel Dokumente dauerhaft oder in den Papierkorb löschen soll.</span><span class="sxs-lookup"><span data-stu-id="7e98f-175">Choose whether the rule will permanently delete documents or delete them to the Recycle Bin.</span></span> <span data-ttu-id="7e98f-176">Der Papierkorb bietet ein Sicherheitsnetz der zweiten Stufe, bevor ein Element permanent von einer Website gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="7e98f-176">The Recycle Bin provides a second-stage safety net before an item is permanently deleted from a site.</span></span> <span data-ttu-id="7e98f-177">Weitere Informationen zum Papierkorb finden Sie unter [leeren des Papierkorbs oder Wiederherstellen Ihrer Dateien](http://go.microsoft.com/fwlink/p/?LinkID=404348).</span><span class="sxs-lookup"><span data-stu-id="7e98f-177">For more information about the Recycle Bin, see [Empty the Recycle Bin or restore your files](http://go.microsoft.com/fwlink/p/?LinkID=404348).</span></span>
    
  - <span data-ttu-id="7e98f-178">Wählen Sie aus, ob das Löschdatum ab dem Datum der Dokumenterstellung oder der letzten Dokumentänderung berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e98f-178">Choose whether the deletion date is calculated from the date when a document was created or last modified.</span></span>
    
  - <span data-ttu-id="7e98f-179">Geben Sie die Anzahl der Tage, Monate oder Jahre als Zeitraum ein, nach dem das Dokument gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e98f-179">Enter a number of days, months, or years as the time period after which a document will be deleted.</span></span>
    
  - <span data-ttu-id="7e98f-p119">Wählen Sie, ob die Regel eine Standardregel ist. Die erste Regel, die Sie erstellen, wird automatisch als die Standardregel festgelegt. Eine Standardregel wird automatisch auf alle Bibliotheken auf den Websites angewendet, die die Richtlinie verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p119">Choose whether the rule is a default rule. The first rule that you create is automatically set as the default rule. A default rule is automatically applied to all libraries in the sites that use the policy.</span></span>
    
![Seite "neue Löschregel"](media/IP-New-deletion-rule.png)
  
7. <span data-ttu-id="7e98f-184">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-184">Click **Save**.</span></span>
    
8. <span data-ttu-id="7e98f-p120">Erstellen Sie zusätzliche Regeln, wenn Sie zulassen möchten, dass Websitebesitzer andere Regeln auswählen und auf ihre Website anwenden können. Falls vorhanden wird die Standardregel angewendet, wenn der Websitebesitzer keine Aktion durchführt.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p120">Create additional rules if you want site owners to be able to choose different rules to apply to their site. The default rule, if any, will be applied if the site owner takes no action.</span></span>
    
9. <span data-ttu-id="7e98f-187">Um eine Regel aus einer Richtlinie zu entfernen, wählen Sie die Regel aus, klicken Sie auf **Löschen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-187">To remove a rule from a policy, select the rule, click **Delete**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7e98f-188">Wenn Sie eine Regel löschen und die Richtlinie keine Standardregel enthält, wird für diese Richtlinie keine Regel angewendet, d. h., es werden keine Dokumente gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7e98f-188">If you delete a rule, and the policy does not contain a default rule, then no rule will be in effect for that policy—in other words, no documents will be deleted.</span></span> 
  
![Bestätigen, dass die Regel aus der Richtlinien Meldung entfernt wird](media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a><span data-ttu-id="7e98f-190">Zuweisen der Dokumentlöschrichtlinie zu einer Vorlage für Websitesammlung</span><span class="sxs-lookup"><span data-stu-id="7e98f-190">Assign the document deletion policy to a site collection template</span></span>

<span data-ttu-id="7e98f-191">Durch das Zuweisen einer Richtlinie zu einer Vorlage für Websitesammlung machen Sie die Richtlinie für alle Websitesammlungen verfügbar, die aufgrund dieser Vorlage erstellt werden, einschließlich bereits vorhandener und künftiger Websitesammlungen.</span><span class="sxs-lookup"><span data-stu-id="7e98f-191">By assigning a policy to a site collection template, you make the policy available to all site collections created from that template, including both existing site collections and site collections created in the future.</span></span>
  
<span data-ttu-id="7e98f-192">Beachten Sie, dass es sich bei dem für eine Dokument Löschrichtlinie angegebenen Zeitraum um die Zeit seit dem Erstellen oder Ändern des Dokuments und nicht um die Zeit seit der Zuweisung der Richtlinie handelt.</span><span class="sxs-lookup"><span data-stu-id="7e98f-192">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="7e98f-193">Wenn Sie die Richtlinie zum ersten Mal zuweisen, werden alle Dokumente auf der Website ausgewertet und, falls sie die Kriterien erfüllen, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7e98f-193">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="7e98f-194">Dies trifft auf alle vorhandenen Dokumente zu, nicht nur auf neue Dokumente, die seit der Zuweisung der Richtlinie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-194">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="7e98f-195">Navigieren Sie im &amp; Security Compliance Center zur **Aufbewahrung**der **Datenverwaltung** \> .</span><span class="sxs-lookup"><span data-stu-id="7e98f-195">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="7e98f-196">Klicken Sie unter **Löschen**auf **Dokument Löschrichtlinien für SharePoint Online und OneDrive für Unternehmen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-196">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="7e98f-197">Das Document Deletion Policy Center wird auf einer neuen Registerkarte im Browser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7e98f-197">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="7e98f-198">Wählen Sie **Richtlinienzuweisungen für Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-198">Choose **Policy Assignments for Templates**.</span></span>
    
    ![Option "Richtlinienzuweisungen für Vorlagen"](media/IP-Policy-Assignments-for-Templates-option.png)
  
3. <span data-ttu-id="7e98f-200">Wählen Sie **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="7e98f-200">Choose **new item**.</span></span>
    
4. <span data-ttu-id="7e98f-201">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7e98f-201">Do one of the following:</span></span>
    
  - <span data-ttu-id="7e98f-202">Um die Richtlinie einer Vorlage für Websitesammlung wie die Teamwebsitevorlage zuzuweisen, wählen Sie **Vorlage für Websitesammlung zuweisen** aus, und wählen Sie die Vorlage für Websitesammlung.</span><span class="sxs-lookup"><span data-stu-id="7e98f-202">To assign the policy to a site collection template such as the Team Site template, select **Assign to site collection template**, and then select the site collection template.</span></span>
    
  - <span data-ttu-id="7e98f-203">Wenn Sie die Richtlinie Benutzern ein Laufwerk für Unternehmen zuweisen möchten, wählen Sie **OneDrive für Unternehmen Vorlage zuweisen**aus, die unten hervorgehoben ist.</span><span class="sxs-lookup"><span data-stu-id="7e98f-203">To assign the policy to users' One Drive for Business, choose **Assign to OneDrive for Business Template**, highlighted below.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7e98f-204">Wenn Sie eine Richtlinie zu einer Vorlage für Websitesammlung zuweisen, wird die Richtlinie für bereits vorhandene Websitesammlungen, die aufgrund dieser Vorlage erstellt wurden, und für künftige Websitesammlungen verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="7e98f-204">When you assign a policy to a site collection template, that policy will be available both to existing site collections created from that template and to site collections created in the future.</span></span> 
  
![Auswählen einer Vorlagenseite mit OneDrive-Option](media/IP-Choose-a-template.png)
  
5. <span data-ttu-id="7e98f-206">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-206">Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7e98f-207">Jeder Vorlage kann immer nur ein Satz von Richtlinien zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-207">Each template can have only one set of policies assigned to it.</span></span> <span data-ttu-id="7e98f-208">Wenn ein Fehler angezeigt wird, der besagt, dass dieser Vorlage bereits Richtlinien zugewiesen wurden **,** \> wählen Sie in der linken Navigations \> Leiste **zuweisen zur Websitesammlung** auswählen aus wählen Sie eine Websitesammlung aus, um die Gruppe von Richtlinien anzuzeigen und zu verwalten, die bereits zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7e98f-208">If you see an error saying that this template already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** in the left navigation \> select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
6. <span data-ttu-id="7e98f-209">Wählen Sie **Zugewiesene Richtlinien verwalten** und die zuzuweisenden Richtlinien aus, und legen Sie dann fest, ob eine Richtlinie die Standardrichtlinie sein soll.</span><span class="sxs-lookup"><span data-stu-id="7e98f-209">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="7e98f-210">Wenn Sie eine Standardrichtlinie festlegen, wird die Richtlinie für alle Websites, die der Richtlinie zugewiesen wurden, automatisch aktiv, ohne dass der Websitebesitzer eine Aktion durchführen muss.</span><span class="sxs-lookup"><span data-stu-id="7e98f-210">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![Seite "Richtlinien hinzufügen und verwalten"](media/IP-Add-and-manage-policies-page.png)
  
7. <span data-ttu-id="7e98f-212">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-212">Click **Save**.</span></span>
    
8. <span data-ttu-id="7e98f-p125">Wenn Sie die Richtlinie auf allen Websites erzwingen möchten, ohne zuzulassen, dass Websitebesitzer sie abwählen können, wählen Sie **Richtlinie als obligatorisch kennzeichnen** aus. Wenn Sie eine Richtlinie als obligatorisch kennzeichnen, kann einer Vorlage für Websitesammlung nur diese einzelne Richtlinie zugewiesen werden. Die Richtlinie muss außerdem als Standard gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p125">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection template. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="7e98f-216">Wenn diese Option ausgegraut ist, wählen Sie **Zugewiesene Richtlinien verwalten** aus, und stellen Sie sicher, dass mindestens eine Richtlinie zugewiesen und als Standard festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7e98f-216">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
9. <span data-ttu-id="7e98f-217">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-217">Click **Save**.</span></span>
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a><span data-ttu-id="7e98f-218">Zuweisen der Dokumentlöschrichtlinie zu einer Websitesammlung</span><span class="sxs-lookup"><span data-stu-id="7e98f-218">Assign the document deletion policy to a site collection</span></span>

<span data-ttu-id="7e98f-p126">Durch das Zuweisen einer Richtlinie zu einer bestimmten Websitesammlung machen Sie die Richtlinie nur für diese Websitesammlung verfügbar. Sie können also Richtlinien näher an den Inhalt in der Websitesammlung anpassen. Außerdem setzen Richtlinien, die einer bestimmten Websitesammlung zugewiesen werden, alle Richtlinien, die der Vorlage für diese Websitesammlung zugewiesen sind, außer Kraft. Zum Beispiel setzt eine Richtlinie, die der (aus der Teamwebsitevorlage erstellten) Websitesammlung Vertriebsabteilung zugewiesen ist, alle Richtlinien außer Kraft, die der Teamwebsitevorlage zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p126">By assigning a policy to a specific site collection, you make the policy available only to that specific site collection. This means you can tailor policies more closely to the content in the site collection. Also, policies assigned to a specific site collection will override any policies that are assigned to the template for that site collection. For example, a policy assigned to the Sales Department site collection (created from the Team Site template) will override any policies assigned to the Team Site template.</span></span>
  
<span data-ttu-id="7e98f-223">Beachten Sie, dass es sich bei dem für eine Dokument Löschrichtlinie angegebenen Zeitraum um die Zeit seit dem Erstellen oder Ändern des Dokuments und nicht um die Zeit seit der Zuweisung der Richtlinie handelt.</span><span class="sxs-lookup"><span data-stu-id="7e98f-223">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="7e98f-224">Wenn Sie die Richtlinie zum ersten Mal zuweisen, werden alle Dokumente auf der Website ausgewertet und, falls sie die Kriterien erfüllen, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7e98f-224">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="7e98f-225">Dies trifft auf alle vorhandenen Dokumente zu, nicht nur auf neue Dokumente, die seit der Zuweisung der Richtlinie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-225">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="7e98f-226">Navigieren Sie im &amp; Security Compliance Center zur **Aufbewahrung**der **Datenverwaltung** \> .</span><span class="sxs-lookup"><span data-stu-id="7e98f-226">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="7e98f-227">Wählen Sie unter **Löschen**die Option **Dokument Löschrichtlinien für SharePoint Online und OneDrive für Unternehmen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="7e98f-227">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="7e98f-228">Das Document Deletion Policy Center wird auf einer neuen Registerkarte im Browser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7e98f-228">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="7e98f-229">Wählen Sie **Richtlinienzuweisungen für Websitesammlungen**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-229">Choose **Policy Assignments for Site Collections**.</span></span>
    
    ![Richtlinienzuweisungen für Websitesammlungen (Option)](media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. <span data-ttu-id="7e98f-231">Wählen Sie **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="7e98f-231">Choose **new item**.</span></span>
    
4. <span data-ttu-id="7e98f-232">Wählen Sie **Websitesammlung auswählen**aus.</span><span class="sxs-lookup"><span data-stu-id="7e98f-232">Choose **Choose a site collection**.</span></span> <span data-ttu-id="7e98f-233">Suchen Sie nach der Websitesammlung anhand des Namens oder der URL, wählen Sie die Websitesammlung aus, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-233">Search for the site collection by name or URL, select the site collection and click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7e98f-234">Jeder Websitesammlung kann immer nur ein Satz von Richtlinien zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-234">Each site collection can have only one set of policies assigned to it.</span></span> <span data-ttu-id="7e98f-235">Wenn ein Fehler angezeigt wird, der besagt, dass dieser Websitesammlung bereits Richtlinien zugewiesen wurden, wählen Sie **"** \> der **Websitesammlung zuweisen** " aus, und wählen Sie eine Websitesammlung aus, um den bereits zugewiesenen Satz von Richtlinien anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="7e98f-235">If you see an error saying that this site collection already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** and select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
![Auswählen einer Website Sammlungsseite](media/IP-Choose-a-site-collection-page.png)
  
5. <span data-ttu-id="7e98f-237">Wählen Sie **Zugewiesene Richtlinien verwalten** und die zuzuweisenden Richtlinien aus, und legen Sie dann fest, ob eine Richtlinie die Standardrichtlinie sein soll.</span><span class="sxs-lookup"><span data-stu-id="7e98f-237">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="7e98f-238">Wenn Sie eine Standardrichtlinie festlegen, wird die Richtlinie für alle Websites, die der Richtlinie zugewiesen wurden, automatisch aktiv, ohne dass der Websitebesitzer eine Aktion durchführen muss.</span><span class="sxs-lookup"><span data-stu-id="7e98f-238">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![Seite "Richtlinien hinzufügen und verwalten"](media/IP-Add-and-manage-policies-page.png)
  
6. <span data-ttu-id="7e98f-240">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-240">Click **Save**.</span></span>
    
7. <span data-ttu-id="7e98f-p132">Wenn Sie die Richtlinie auf allen Websites erzwingen möchten, ohne zuzulassen, dass Websitebesitzer sie abwählen können, wählen Sie **Richtlinie als obligatorisch kennzeichnen** aus. Wenn Sie eine Richtlinie als obligatorisch kennzeichnen, kann einer Websitesammlung nur diese einzelne Richtlinie zugewiesen werden. Die Richtlinie muss außerdem als Standard gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-p132">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="7e98f-244">Wenn diese Option ausgegraut ist, wählen Sie **Zugewiesene Richtlinien verwalten** aus, und stellen Sie sicher, dass mindestens eine Richtlinie zugewiesen und als Standard festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7e98f-244">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
8. <span data-ttu-id="7e98f-245">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-245">Click **Save**.</span></span>
    
## <a name="delete-a-policy-assignment"></a><span data-ttu-id="7e98f-246">Löschen einer Richtlinienzuweisung</span><span class="sxs-lookup"><span data-stu-id="7e98f-246">Delete a policy assignment</span></span>

<span data-ttu-id="7e98f-247">Wenn Sie eine Zuweisung löschen, werden die zugewiesenen Richtlinien nicht mehr auf die Websites in der Websitesammlung oder Vorlage für Websitesammlung angewendet.</span><span class="sxs-lookup"><span data-stu-id="7e98f-247">When you delete an assignment, the assigned policies will no longer apply to any sites in the site collection or site collection template.</span></span>
  
1. <span data-ttu-id="7e98f-248">Navigieren Sie im &amp; Security Compliance Center zur **Aufbewahrung**der **Datenverwaltung** \> .</span><span class="sxs-lookup"><span data-stu-id="7e98f-248">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="7e98f-249">Wählen Sie unter **Löschen**die Option **Dokument Löschrichtlinien für SharePoint Online und OneDrive für Unternehmen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="7e98f-249">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="7e98f-250">Das Document Deletion Policy Center wird auf einer neuen Registerkarte im Browser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7e98f-250">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="7e98f-251">Wählen Sie entweder \*\*Richtlinienzuweisungen für Vorlagen \*\* oder **Richtlinienzuweisungen für Websitesammlungen**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-251">Choose either **Policy Assignments for Templates** or **Policy Assignments for Site Collections**.</span></span>
    
3. <span data-ttu-id="7e98f-252">Wählen Sie das Zuordnungselement aus, und klicken Sie auf **Element löschen**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-252">Select the assignment item and click **Delete Item**.</span></span>
    
    ![Befehl "Element löschen" für Richtlinienzuweisung](media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a><span data-ttu-id="7e98f-254">Löschen einer Richtlinie</span><span class="sxs-lookup"><span data-stu-id="7e98f-254">Delete a policy</span></span>

<span data-ttu-id="7e98f-255">Eine verwendete Richtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="7e98f-255">You can't delete a policy that's in use.</span></span> <span data-ttu-id="7e98f-256">Bevor Sie eine Richtlinie löschen können, müssen Sie zunächst alle Zuordnungen zu Websitesammlungen und Websitesammlungsvorlagen löschen, die diese Richtlinie enthalten – siehe den vorherigen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="7e98f-256">Before you can delete a policy, you first need to delete all assignments to site collections and site collection templates that include that policy—see the previous section.</span></span>
  
1. <span data-ttu-id="7e98f-257">Wählen Sie im &amp; Security Compliance \> Center in der linken Navigation \> unter Manage Document **Delete** \> \> Policies for SharePoint Online and OneDrive die Option **Data Management** **Retention** aus. \*\* für Unternehmen\*\*.</span><span class="sxs-lookup"><span data-stu-id="7e98f-257">In the Security &amp; Compliance Center \> choose **Data management** \> **Retention** in the left navigation \> under **Delete** \> **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="7e98f-258">Das Document Deletion Policy Center wird auf einer neuen Registerkarte im Browser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7e98f-258">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="7e98f-259">Wählen Sie \* \* Löschrichtlinien \* \* aus.</span><span class="sxs-lookup"><span data-stu-id="7e98f-259">Choose \*\* Deletion Policies \*\*.</span></span>
    
    ![Löschrichtlinien (Option)](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="7e98f-261">Wählen Sie die Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="7e98f-261">Select the policy.</span></span>
    
4. <span data-ttu-id="7e98f-262">Entfernen Sie auf \> der Register \> Karte Menü Band **Elemente** die **Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-262">On the Ribbon \> **Items** tab \> **Remove Policy**.</span></span>
    
    ![Schaltfläche ' Richtlinie entfernen ' auf dem Menüband](media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. <span data-ttu-id="7e98f-264">Wenn die Richtlinie verwendet wird, werden Sie gefragt, ob Sie die Richtlinie aus allen Websitesammlungen entfernen möchten, in denen Sie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7e98f-264">If the policy is in use, you'll be asked if you want to remove the policy from all of the site collections where it's being used.</span></span> <span data-ttu-id="7e98f-265">Wenn Sie sich sicher sind, wählen Sie **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e98f-265">If you're sure, choose **OK**.</span></span>
    
    ![Bestätigungsnachricht für die Richtlinie löschen](media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a><span data-ttu-id="7e98f-267">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e98f-267">See also</span></span>

[<span data-ttu-id="7e98f-268">Übersicht über Dokumentlöschrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7e98f-268">Overview of document deletion policies</span></span>](document-deletion-policies.md)

[<span data-ttu-id="7e98f-269">Anwenden oder Entfernen einer Dokumentlöschrichtlinie für eine Website</span><span class="sxs-lookup"><span data-stu-id="7e98f-269">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

