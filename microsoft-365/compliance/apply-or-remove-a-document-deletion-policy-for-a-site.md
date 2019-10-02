---
title: Anwenden oder Entfernen einer Dokumentlöschrichtlinie für eine Website
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Unternehmen unterliegen häufig compliancebezogenen, rechtlichen oder anderen Vorschriften, nach denen sie Dokumente eine bestimmte Zeit lang aufbewahren müssen. Werden Dokumente jedoch länger als erforderlich aufbewahrt, kann dies für das Unternehmen ein rechtliches Risiko darstellen. Daher hat Ihr Unternehmen für Ihre Website möglicherweise eine Dokumentlöschrichtlinie erstellt, nach der z. B. allgemeine Geschäftsdokumente fünf Jahre nach Erstellung gelöscht werden müssen.
ms.openlocfilehash: 3f5228c26cc4e12c129a57e2141e3eea50d029a2
ms.sourcegitcommit: 1eecd7b127462585c35b0c96a179d37db45f6013
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "37342958"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="91141-105">Anwenden oder Entfernen einer Dokumentlöschrichtlinie für eine Website</span><span class="sxs-lookup"><span data-stu-id="91141-105">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="91141-p102">Unternehmen unterliegen häufig compliancebezogenen, rechtlichen oder anderen Vorschriften, nach denen sie Dokumente eine bestimmte Zeit lang aufbewahren müssen. Werden Dokumente jedoch länger als erforderlich aufbewahrt, kann dies für das Unternehmen ein rechtliches Risiko darstellen. Daher hat Ihr Unternehmen für Ihre Website möglicherweise eine Dokumentlöschrichtlinie erstellt, nach der z. B. allgemeine Geschäftsdokumente fünf Jahre nach Erstellung gelöscht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="91141-p102">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time. However, retaining documents for longer than required can expose the organization to legal risk. For this reason, your organization may have created a document deletion policy for your site — for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="91141-109">Abhängig von Ihrem Unternehmen kann eine Dokumentlöschrichtlinie eine der folgenden Eigenschaften aufweisen:</span><span class="sxs-lookup"><span data-stu-id="91141-109">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="91141-110">**Obligatorisch** Ein Websitebesitzer kann keine obligatorische Richtlinie deaktivieren, die automatisch auf die Website angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="91141-110">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="91141-111">**Standardmäßig** Eine Standardrichtlinie wird automatisch auf eine Website angewendet. Ein Websiteeigentümer hat jedoch folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="91141-111">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="91141-112">Auswählen einer anderen Richtlinie, sofern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="91141-112">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="91141-113">Vollständiges Abwählen der Richtlinie, wenn sie für die Inhalte der Website nicht relevant ist.</span><span class="sxs-lookup"><span data-stu-id="91141-113">Opt out of the policy entirely if it is not relevant to the content in the site.</span></span>
    
- <span data-ttu-id="91141-114">**Weder verpflichtend noch standardmäßig** In diesem Fall wird auf die Website keine Richtlinie automatisch angewendet, und der Websiteeigentümer muss Maßnahmen ergreifen, um eine Richtlinie anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="91141-114">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="91141-p103">Eine Dokumentlöschrichtlinie kann mehr als eine Regel enthalten. So kann eine Regel etwa besagen, dass Dokumente ein Jahr nach deren Erstellung gelöscht werden, während eine andere Regel besagen kann, dass Dokumente ein Jahr nach der letzten Änderung gelöscht werden. Wenn eine Richtlinie mehr als eine Regel enthält, können Sie die Regel auswählen, die sich für Ihre Website am besten eignet. Die Löschregel wird auf alle Bibliotheken in der Website angewendet. In einer Website kann jeweils immer nur eine Richtlinie und eine Regel aktiv sein. Eine Regel kann wie eine Richtlinie als Standard festgelegt werden, sodass sie automatisch angewendet wird, wenn die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="91141-p103">A document deletion policy may contain more than one rule — for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified. If a policy contains more than one rule, you can select the rule that best applies to your site. The delete rule will be applied to all libraries within the site. Only one policy and one rule can be active in a site at one time. Like a policy, a rule can be set as default, so that it is applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="91141-p104">Außerdem werden Dokumentlöschrichtlinien vererbt. Wenn Sie eine Richtlinie oder Regel für Ihre Website auswählen, wird diese Auswahl von allen Unterwebsites geerbt. Der Besitzer einer Website kann die Vererbung allerdings durch Auswahl einer anderen Richtlinie oder Regel unterbrechen. Berücksichtigen Sie bei der Auswahl einer Richtlinie oder Regel die Inhalte aller Unterwebsites unterhalb Ihrer Website.</span><span class="sxs-lookup"><span data-stu-id="91141-p104">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="91141-123">Anzeigen der in einer Websitesammlung verfügbaren Dokumentlöschrichtlinien</span><span class="sxs-lookup"><span data-stu-id="91141-123">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="91141-p105">Ihr Unternehmen kann unterschiedlichen Websitesammlungen unterschiedliche Richtlinien zuweisen. Auf Ebene der Websitesammlung kann der Besitzer einer Websitesammlung alle Dokumentlöschrichtlinien anzeigen, die für diese Websitesammlung verfügbar sind. Die Richtlinien wurden möglicherweise für die Websitesammlungsvorlage (und somit für alle mit dieser Vorlage erstellten Websitesammlungen) oder für diese bestimmte Websitesammlung verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="91141-p105">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="91141-127">Wählen Sie auf der Website auf oberster Ebene in der Websitesammlung in der oberen rechten Ecke **Einstellungen** [Zahnradsymbol] \> **Websiteeinstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="91141-127">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="91141-128">**Dokument Löschungsrichtlinien**unter **Websitesammlungsverwaltung** \> .</span><span class="sxs-lookup"><span data-stu-id="91141-128">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="91141-129">Der Link **Dokument Löschungsrichtlinien** wird nur angezeigt, wenn der Websitesammlung Richtlinien zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="91141-129">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="91141-130">Außerdem wird der Link nicht unmittelbar nach dem Zuweisen von Richtlinien zur Website angezeigt – es kann bis zu 24 Stunden dauern, bis die Richtlinien zugewiesen sind, wenn der Link **Dokument Löschungsrichtlinien** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="91141-130">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="91141-131">Auf dieser Seite können Sie Folgendes anzeigen:</span><span class="sxs-lookup"><span data-stu-id="91141-131">On this page you can view:</span></span>
    
  - <span data-ttu-id="91141-p107">Die aktuell zugewiesenen Richtlinien und die zugehörigen Regeln. Wählen Sie eine Richtlinie aus, um die Regeln im rechten Fenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="91141-p107">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="91141-134">Bei der Standardrichtlinie, falls vorhanden, steht in der Spalte **Standard\*\*\*\*Ja**.</span><span class="sxs-lookup"><span data-stu-id="91141-134">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="91141-135">Unterhalb der Liste wird eine Meldung angezeigt, wenn die Richtlinie als **Verpflichtend** zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="91141-135">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="91141-p108">Diese Liste ist schreibgeschützt und dient dem Websitesiteeigentümer dazu, alle verfügbaren Richtlinien und Regeln anzuzeigen. Informationen zum Anwenden einer Richtlinie finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="91141-p108">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![Ansicht der einer Websitesammlung zugewiesenen Dokument Löschungsrichtlinien](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="91141-139">Anwenden oder Entfernen einer Dokumentlöschrichtlinie für eine Website</span><span class="sxs-lookup"><span data-stu-id="91141-139">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="91141-140">Für Sie als Besitzer einer Website oder Websitesammlung gibt es in Ihrem Unternehmen möglicherweise Richtlinien, die Sie auf Ihre Website anwenden oder komplett abwählen können.</span><span class="sxs-lookup"><span data-stu-id="91141-140">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="91141-141">Wählen Sie in der oberen rechten Ecke **Einstellungen** [Zahnradsymbol] \> **Websiteeinstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="91141-141">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="91141-142">**Dokument Löschungsrichtlinien**unter **Websiteverwaltung** \> .</span><span class="sxs-lookup"><span data-stu-id="91141-142">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="91141-143">Der Link **Dokument Löschungsrichtlinien** wird nur angezeigt, wenn der Websitesammlung Richtlinien zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="91141-143">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="91141-144">Außerdem wird der Link nicht unmittelbar nach dem Zuweisen von Richtlinien zur Website angezeigt – es kann bis zu 24 Stunden dauern, bis die Richtlinien zugewiesen sind, wenn der Link **Dokument Löschungsrichtlinien** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="91141-144">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="91141-145">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="91141-145">Do one of the following:</span></span>
    
  - <span data-ttu-id="91141-146">**So wenden Sie eine Richtlinie an** Wählen Sie eine \> Richtlinie aus wählen Sie eine \> Regel in dieser Richtlinie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="91141-146">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="91141-p110">In einer Website kann jeweils immer nur eine Richtlinie und eine Regel aktiv sein. Ihr Unternehmen stellt möglicherweise mehrere Richtlinien und Regeln zur Auswahl oder nur eine Richtlinie oder Regel bereit.</span><span class="sxs-lookup"><span data-stu-id="91141-p110">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![Option "Richtlinie auswählen"](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="91141-150">**So deaktivieren Sie eine Richtlinie** Wählen Sie **Opt-out: Do Note DELETE** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="91141-150">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="91141-p111">Als Websitebesitzer können Sie eine Dokumentlöschrichtlinie abwählen, wenn die Richtlinie Ihrer Meinung nach für Inhalte Ihrer Website nicht geeignet ist. Eine Richtlinie, die als **Verpflichtend** gekennzeichnet ist, kann allerdings nicht abgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="91141-p111">As a site owner, you can opt out of a document deletion policy if you determine that the policy is not applicable to the content in your site. However, you cannot opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![Opt-out-Option](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="91141-154">Dokumentlöschrichtlinien haben Vorrang vor anderen Richtlinien</span><span class="sxs-lookup"><span data-stu-id="91141-154">Document deletion policies override other policies</span></span>

<span data-ttu-id="91141-155">Eine Website verwendet möglicherweise andere Richtlinie für die Aufbewahrung und Löschung von Inhalten:</span><span class="sxs-lookup"><span data-stu-id="91141-155">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="91141-156">Inhaltstyprichtlinien für die Websitesammlung.</span><span class="sxs-lookup"><span data-stu-id="91141-156">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="91141-157">Informationsverwaltungsrichtlinien für eine Liste oder Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="91141-157">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="91141-158">Wenn Sie eine Dokumentlöschrichtlinie auf eine Website anwenden, die für eine Liste oder Bibliothek bereits Inhaltstyp- oder Informationsverwaltungsrichtlinien verwendet, werden diese Richtlinien ignoriert, während die Dokumentlöschrichtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="91141-158">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="91141-159">Wenn andere Richtlinien ignoriert werden, wird die Meldung "Inhalt auf dieser Website verwendet Dokument Löschungsrichtlinien" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91141-159">If other policies are ignored, you will see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="91141-p113">Das bedeutet, dass Sie für eine Website nur Richtlinien verwenden sollten, die für strukturierte Inhalte (Informationsverwaltungs- und Inhaltstyprichtlinien) oder unstrukturierte Inhalte (Dokumentlöschungsrichtlinien) gedacht sind, und nicht beide Arten von Richtlinien. Wenn Sie eine Dokumentlöschrichtlinie abwählen, wird die Warnung nicht angezeigt, und andere Richtlinientypen werden weiterhin angewendet.</span><span class="sxs-lookup"><span data-stu-id="91141-p113">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both. If you opt out of a document deletion policy, the warning will not be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="91141-162">Websiterichtlinien sind von Dokumentlöschungsrichtlinien nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="91141-162">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="91141-163">Prüfen, ob Inhaltstyprichtlinien ignoriert werden</span><span class="sxs-lookup"><span data-stu-id="91141-163">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="91141-164">Wenn Ihre Website Inhaltstyprichtlinien verwendet hat und nun diese Meldung angezeigt wird, werden diese Richtlinien nicht mehr angewendet.</span><span class="sxs-lookup"><span data-stu-id="91141-164">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="91141-165">Wenn Sie die Richtlinien für den Inhaltstyp wiederherstellen möchten, können Sie die Richtlinie für das Löschen von Dokumenten aus Ihrer Website entfernen (siehe oben beschrieben), wenn eine Opt-out-Option zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="91141-165">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="91141-166">Wenn keine Option zum Deaktivieren vorhanden ist, ist die Richtlinie für das Löschen von Dokumenten zwingend erforderlich, und Sie müssen sich an den Compliance Officer in Ihrer Organisation wenden.</span><span class="sxs-lookup"><span data-stu-id="91141-166">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="91141-167">Wählen Sie in der oberen rechten Ecke **Einstellungen** [Zahnradsymbol] \> **Websiteeinstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="91141-167">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="91141-168">Unter **Inhaltstyp Richtlinienvorlagen**für **Websiteverwaltung** \> .</span><span class="sxs-lookup"><span data-stu-id="91141-168">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![Warnung vor der Website, dass Dokument Löschungsrichtlinien verwendet werden](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="91141-170">Prüfen, ob Informationsverwaltungsrichtlinien ignoriert werden</span><span class="sxs-lookup"><span data-stu-id="91141-170">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="91141-171">Wenn Ihre Website Informationsverwaltungsrichtlinien verwendet hat und nun diese Meldung angezeigt wird, werden diese Richtlinien nicht mehr angewendet.</span><span class="sxs-lookup"><span data-stu-id="91141-171">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="91141-172">Um die Richtlinien für die Informationsverwaltung wiederherzustellen, können Sie die Dokument Löschungs Richtlinie wie oben beschrieben aus Ihrer Website entfernen, wenn eine Opt-out-Option zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="91141-172">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="91141-173">Wenn keine Option zum Deaktivieren vorhanden ist, ist die Richtlinie für das Löschen von Dokumenten zwingend erforderlich, und Sie müssen sich an den Compliance Officer in Ihrer Organisation wenden.</span><span class="sxs-lookup"><span data-stu-id="91141-173">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="91141-174">Für eine Liste oder Bibliothek auf der Registerkarte \> \*\*\*\* \> **Bibliothekseinstellungen** \> der Menü Bandbibliothek unter **Berechtigungen und Verwaltungs** \> **Informationsverwaltungsrichtlinien Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="91141-174">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![Warnung vor der Website, dass Dokument Löschungsrichtlinien verwendet werden](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="91141-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91141-176">See also</span></span>

[<span data-ttu-id="91141-177">Übersicht über Dokumentlöschrichtlinien</span><span class="sxs-lookup"><span data-stu-id="91141-177">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="91141-178">Erstellen einer Dokumentlöschrichtlinie</span><span class="sxs-lookup"><span data-stu-id="91141-178">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

