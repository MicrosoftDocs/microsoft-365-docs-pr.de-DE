---
title: Erste Schritte mit dem Inhalts-Explorer
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Mit dem Inhalts-Explorers zur Datenklassifizierung können Sie beschriftete Elemente systemintern anzeigen.
ms.openlocfilehash: 19ad68d3c32046754e366919e8c4e66336945624
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080724"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="70d43-103">Erste Schritte mit dem Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="70d43-103">Get started with content explorer</span></span>

<span data-ttu-id="70d43-104">Mit dem Inhalts-Explorers zur Datenklassifizierung können Sie die Elemente, die auf der Übersichtsseite zusammengefasst wurden, systemintern anzeigen.</span><span class="sxs-lookup"><span data-stu-id="70d43-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![Screenshot des erweiterten Inhalts-Explorers](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="70d43-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="70d43-106">Prerequisites</span></span>

<span data-ttu-id="70d43-107">Jedem Konto, das auf die Datenklassifizierung zugreift und sie verwendet, muss eine Lizenz aus einem dieser Abonnements zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="70d43-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="70d43-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="70d43-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="70d43-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="70d43-109">Office 365 (E5)</span></span>
- <span data-ttu-id="70d43-110">Advanced Compliance (E5)-Add-on</span><span class="sxs-lookup"><span data-stu-id="70d43-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="70d43-111">Advanced Threat Intelligence (E5)-Add-on</span><span class="sxs-lookup"><span data-stu-id="70d43-111">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="70d43-112">Microsoft 365 E5/A5 Info Protection & Governance</span><span class="sxs-lookup"><span data-stu-id="70d43-112">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="70d43-113">Microsoft 365 E5/A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="70d43-113">Microsoft 365 E5/A5 Compliance</span></span>


### <a name="permissions"></a><span data-ttu-id="70d43-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="70d43-114">Permissions</span></span>

<span data-ttu-id="70d43-115">Um Zugriff auf die Registerkarte „Inhalts-Explorer“ zu erhalten, muss einem Konto die Mitgliedschaft in einer dieser Rollen oder Rollengruppen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="70d43-115">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="70d43-116">**Microsoft 365-Rollengruppen**</span><span class="sxs-lookup"><span data-stu-id="70d43-116">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="70d43-117">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="70d43-117">Global administrator</span></span>
- <span data-ttu-id="70d43-118">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="70d43-118">Compliance administrator</span></span>
- <span data-ttu-id="70d43-119">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="70d43-119">Security administrator</span></span>
- <span data-ttu-id="70d43-120">Compliancedatenadministrator</span><span class="sxs-lookup"><span data-stu-id="70d43-120">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70d43-121">Die Mitgliedschaft in diesen Rollengruppen erlaubt Ihnen nicht, die Liste der Elemente im Inhalts-Explorer oder den Inhalt der Elemente im Inhalts-Explorer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="70d43-121">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="70d43-122">Erforderliche Berechtigungen für den Zugriff auf Elemente im Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="70d43-122">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="70d43-123">Der Zugriff auf den Inhalts-Explorer ist hochgradig eingeschränkt, da Sie damit den Inhalt überprüfter Dateien lesen können.</span><span class="sxs-lookup"><span data-stu-id="70d43-123">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70d43-124">Diese Berechtigungen ersetzen die Berechtigungen, die den Elementen lokal zugewiesen sind, was die Anzeige des Inhalts ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="70d43-124">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="70d43-125">Es gibt zwei Rollen, die Zugriff auf den Inhalts-Explorer gewähren, und diese werden mithilfe des [Microsoft Security & Compliance Centers](https://protection.office.com/permissions)gewährt:</span><span class="sxs-lookup"><span data-stu-id="70d43-125">There are two roles that grant access to content explorer and it is granted using the [Microsoft Security & Compliance Center](https://protection.office.com/permissions):</span></span>

- <span data-ttu-id="70d43-126">**Inhalts Explorer-Listenanzeige**: Durch die Mitgliedschaft in dieser Rollengruppe können Sie jedes Element und dessen Speicherort in der Listenansicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="70d43-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="70d43-127">Die Rolle `data classification list viewer` wurde dieser Rollengruppe bereits zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="70d43-127">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="70d43-128">**Inhalts-Explorer-Inhaltsanzeige**: Durch die Mitgliedschaft in dieser Rollengruppe können Sie die Inhalte aller Elemente in der Liste anzeigen.</span><span class="sxs-lookup"><span data-stu-id="70d43-128">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="70d43-129">Die Rolle `data classification content viewer` wurde dieser Rollengruppe bereits zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="70d43-129">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="70d43-130">Das Konto, das Sie für den Zugriff auf den Inhalts-Explorer verwenden, muss einer oder beiden Rollengruppen angehören.</span><span class="sxs-lookup"><span data-stu-id="70d43-130">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="70d43-131">Hierbei handelt es sich um unabhängige Rollengruppen, die nicht kumulativ sind.</span><span class="sxs-lookup"><span data-stu-id="70d43-131">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="70d43-132">Wenn Sie beispielsweise einem Konto die Möglichkeit geben möchten, nur die Elemente und deren Speicherorte anzuzeigen, erteilen Sie Inhalts-Explorer-Listenanzeige-Rechte.</span><span class="sxs-lookup"><span data-stu-id="70d43-132">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="70d43-133">Wenn Sie möchten, dass dasselbe Konto auch in der Lage ist, die Inhalte der Elemente in der Liste anzuzeigen, erteilen Sie zusätzlich Inhalts-Explorer-Inhaltsanzeige-Rechte.</span><span class="sxs-lookup"><span data-stu-id="70d43-133">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="70d43-134">Sie können auch eine oder beide Rollen einer benutzerdefinierten Rollengruppe zuweisen, um den Zugriff auf den Inhalts-Explorer anzupassen.</span><span class="sxs-lookup"><span data-stu-id="70d43-134">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="70d43-135">Ein globaler Administrator, ein Compliance-Administrator oder ein Datenadministrator kann die erforderliche Rollengruppenmitgliedschaft Inhalts-Explorer-Listenanzeige und Inhalts-Explorer-Inhaltsanzeige zuweisen.</span><span class="sxs-lookup"><span data-stu-id="70d43-135">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="70d43-136">Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="70d43-136">Content explorer</span></span>

<span data-ttu-id="70d43-137">Der Inhalts-Explorer zeigt eine aktuelle Momentaufnahme der Elemente mit einer Vertraulichkeitsbezeichnung, einer Aufbewahrungsbezeichnung oder von Elementen, die in Ihrer Organisation als vertraulicher Informationstyp klassifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="70d43-137">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="70d43-138">Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="70d43-138">Sensitive information types</span></span>

<span data-ttu-id="70d43-139">Mithilfe einer [DLP-Richtlinie](data-loss-prevention-policies.md) können vertrauliche Informationen geschützt werden, die als **vertraulicher Informationstyp** definiert sind.</span><span class="sxs-lookup"><span data-stu-id="70d43-139">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="70d43-140">Microsoft 365 umfasst [Definitionen für viele gängige Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md) aus vielen verschiedenen Regionen, die für Sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="70d43-140">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="70d43-141">Beispielsweise Kreditkartennummern, Bankkontonummern, Personalausweisnummern und Windows Live ID-Dienstnummern.</span><span class="sxs-lookup"><span data-stu-id="70d43-141">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="70d43-142">Der Inhalts-Explorer sucht derzeit nicht nach vertraulichen Informationstypen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70d43-142">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="70d43-143">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="70d43-143">Sensitivity labels</span></span>

<span data-ttu-id="70d43-144">Eine [Vertraulichkeitsbezeichnung](sensitivity-labels.md) ist einfach ein Tag, das den Wert des Elements für Ihre Organisation angibt.</span><span class="sxs-lookup"><span data-stu-id="70d43-144">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="70d43-145">Sie kann manuell oder automatisch angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="70d43-145">It can be applied manually, or automatically.</span></span> <span data-ttu-id="70d43-146">Sobald sie angewendet wurde, wird sie in das Dokument eingebettet und mit diesem überall hin weitergebenen.</span><span class="sxs-lookup"><span data-stu-id="70d43-146">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="70d43-147">Eine Vertraulichkeitsbezeichnung aktiviert verschiedene Schutzmaßnahmen, z. B. ein obligatorisches Wasserzeichen oder die Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="70d43-147">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="70d43-148">Vertraulichkeitsbezeichnungen müssen für Dateien in SharePoint und OneDrive aktiviert sein, damit die entsprechenden Daten in der Datenklassifizierungsseite eingeblendet werden können.</span><span class="sxs-lookup"><span data-stu-id="70d43-148">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="70d43-149">Weitere Informationen finden Sie unter [Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in Microsoft Office SharePoint Online und OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="70d43-149">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="70d43-150">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="70d43-150">Retention labels</span></span>

<span data-ttu-id="70d43-151">Mithilfe einer [Aufbewahrungbezeichnung](retention.md) können Sie festlegen, wie lange ein entsprechend gekennzeichnetes Element aufbewahrt wird, und welche Schritte vor dem Löschen ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="70d43-151">A [retention label](retention.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="70d43-152">Aufbewahrungbezeichnungen können manuell oder automatisch über Richtlinien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="70d43-152">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="70d43-153">Sie können Ihre Organisation dabei unterstützen, rechtliche und behördliche Vorschriften einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="70d43-153">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="70d43-154">Verwendung des Inhalts-Explorers</span><span class="sxs-lookup"><span data-stu-id="70d43-154">How to use content explorer</span></span>

1. <span data-ttu-id="70d43-155">Öffnen Sie **Microsoft 365 Compliance Center**  > **Datenklassifizierung** > **Inhalts-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="70d43-155">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="70d43-156">Wenn Sie den Namen der Bezeichnung oder den Typ vertraulicher Informationen kennen, können Sie ihn in das Filterfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="70d43-156">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="70d43-157">Alternativ können Sie auch nach dem Element suchen, indem Sie den Beschriftungstyp erweitern und die Bezeichnung in der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="70d43-157">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="70d43-158">Wählen Sie unter **Alle Standorte** einen Standort aus, und gliedern Sie die Ordnerstruktur bis zu dem Element weiter auf.</span><span class="sxs-lookup"><span data-stu-id="70d43-158">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="70d43-159">Doppelklicken Sie, um das Element systemintern im Inhalts-Explorer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="70d43-159">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="70d43-160">Exportieren</span><span class="sxs-lookup"><span data-stu-id="70d43-160">Export</span></span>
<span data-ttu-id="70d43-161">Das Steuerelement **Exportieren** erstellt eine .csv-Datei, die eine Auflistung dessen enthält, was im Bereich **Alle Speicherorte** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="70d43-161">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![Steuerelement „Exportieren“ – Datenklassifizierung](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="70d43-163">Suchen</span><span class="sxs-lookup"><span data-stu-id="70d43-163">Search</span></span>

<span data-ttu-id="70d43-164">Wenn Sie einen Speicherort, z. B. einen Exchange-Ordner oder eine SharePoint- oder OneDrive-Website, aufschlüsseln, wird das **Suchtool** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="70d43-164">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![Inhalts-Explorer – Suchtool](../media/data_classification_search_tool.png)


<span data-ttu-id="70d43-166">Der Bereich des Suchtools richtet sich danach, was im Bereich **Alle Speicherorte** angezeigt wird und wonach Sie suchen können, variiert je nach ausgewähltem Speicherort.</span><span class="sxs-lookup"><span data-stu-id="70d43-166">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="70d43-167">Wenn **Exchange** der ausgewählte Speicherort ist, können Sie die vollständige E-Mail-Adresse des Postfachs durchsuchen, z. B. `user@domainname.com`.</span><span class="sxs-lookup"><span data-stu-id="70d43-167">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="70d43-168">Wenn entweder **SharePoint** oder **OneDrive** als Speicherort ausgewählt ist, wird das Suchtool angezeigt, wenn Sie nach Website-Namen, Ordnern und Dateien suchen.</span><span class="sxs-lookup"><span data-stu-id="70d43-168">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="70d43-169">**OneDrive** Wir haben uns Ihr wertvolles Feedback zur OneDrive-Integration während unseres Vorschauprogramms angehört.</span><span class="sxs-lookup"><span data-stu-id="70d43-169">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="70d43-170">Basierend auf diesem Feedback wird die OneDrive-Funktionalität in der Vorschau verbleiben, bis alle Fixes vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="70d43-170">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="70d43-171">Abhängig von Ihrem Mandanten sehen einige Kunden OneDrive möglicherweise nicht als Speicherort.</span><span class="sxs-lookup"><span data-stu-id="70d43-171">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="70d43-172">Wir wissen Ihre anhaltende Unterstützung diesbezüglich zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="70d43-172">We appreciate your continued support on this.</span></span>

<span data-ttu-id="70d43-173">Sie können nach folgendem suchen:</span><span class="sxs-lookup"><span data-stu-id="70d43-173">You can search on:</span></span>


|<span data-ttu-id="70d43-174">Wert</span><span class="sxs-lookup"><span data-stu-id="70d43-174">value</span></span>|<span data-ttu-id="70d43-175">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70d43-175">example</span></span>  |
|---------|---------|
|<span data-ttu-id="70d43-176">vollständiger Websitename</span><span class="sxs-lookup"><span data-stu-id="70d43-176">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="70d43-177">Stammordner-Name – ruft alle Unterordner ab</span><span class="sxs-lookup"><span data-stu-id="70d43-177">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="70d43-178">Dateiname</span><span class="sxs-lookup"><span data-stu-id="70d43-178">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="70d43-179">Text am Anfang des Dateinamens</span><span class="sxs-lookup"><span data-stu-id="70d43-179">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="70d43-180">Text nach einem Unterstrich ( _ ) im Dateinamen</span><span class="sxs-lookup"><span data-stu-id="70d43-180">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="70d43-181">`Resume` oder `1234`</span><span class="sxs-lookup"><span data-stu-id="70d43-181">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="70d43-182">Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="70d43-182">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="70d43-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70d43-183">See also</span></span>

- [<span data-ttu-id="70d43-184">Weitere Informationen zu Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="70d43-184">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="70d43-185">Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="70d43-185">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="70d43-186">Entitätsdefinitionen für Typen vertraulicher Informationstypen.md</span><span class="sxs-lookup"><span data-stu-id="70d43-186">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="70d43-187">Übersicht über die Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="70d43-187">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
