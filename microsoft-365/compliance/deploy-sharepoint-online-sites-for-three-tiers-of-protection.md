---
title: Bereitstellen von SharePoint Online-Websites für drei Schutzebenen
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 'Zusammenfassung: Erstellen und Konfigurieren von SharePoint Online-Teamwebsites für verschiedene Ebenen des Informationsschutzes.'
ms.openlocfilehash: 44aa7c126e3ac4b077868c055f35c0b99d678b58
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636133"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="e07c8-103">Bereitstellen von SharePoint Online-Websites für drei Schutzebenen</span><span class="sxs-lookup"><span data-stu-id="e07c8-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

<span data-ttu-id="e07c8-p101">Verwenden Sie die Schritte in diesem Artikel, um Richtlinien für grundlegende, vertrauliche und streng vertrauliche SharePoint Online-Teamwebsites zu entwerfen. Weitere Informationen zu diesen drei Schutzebenen finden Sie unter [Sichern von SharePoint Online-Websites und -Dateien](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="e07c8-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="e07c8-106">Grundlegende SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="e07c8-106">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="e07c8-p102">Der grundlegende Schutz enthält sowohl öffentliche als auch private Teamwebsites. Öffentliche Teamwebsites können von allen Benutzern in der Organisation entdeckt werden, und alle haben Zugriff darauf. Private Websites dagegen können nur von Mitgliedern der Microsoft 365-Gruppe entdeckt werden, die der Teamwebsite zugeordnet sind, und nur sie haben Zugriff darauf. Diese beiden Arten von Teamwebsites erlauben Mitgliedern, die Website für andere Personen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="e07c8-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Microsoft 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="e07c8-111">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="e07c8-111">Public</span></span>

<span data-ttu-id="e07c8-112">Um eine grundlegende SharePoint Online-Teamwebsite mit öffentlichem Zugriff und Berechtigungen zu erstellen, befolgen Sie bitte [diese Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="e07c8-112">To create a baseline SharePoint Online team site with public access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="e07c8-113">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e07c8-113">Here is your resulting configuration.</span></span>
  
![Grundschutz für eine öffentliche SharePoint Online-Teamwebsite.](../media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="e07c8-115">Privat</span><span class="sxs-lookup"><span data-stu-id="e07c8-115">Private</span></span>

<span data-ttu-id="e07c8-116">Um eine grundlegende SharePoint Online-Teamwebsite mit privatem Zugriff und Berechtigungen zu erstellen, befolgen Sie bitte [diese Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="e07c8-116">To create a baseline SharePoint Online team site with private access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>
  
<span data-ttu-id="e07c8-117">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e07c8-117">Here is your resulting configuration.</span></span>
  
![Grundschutz für eine private SharePoint Online-Teamwebsite.](../media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="e07c8-119">Vertrauliche SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="e07c8-119">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="e07c8-120">Eine sensible SharePoint Online-Teamwebsite wird zunächst als private Teamwebsite erstellt.</span><span class="sxs-lookup"><span data-stu-id="e07c8-120">A sensitive SharePoint Online team site starts as a private team site.</span></span>
  
<span data-ttu-id="e07c8-121">Erstellen Sie zuerst die private SharePoint Online-Teamwebsite laut den [folgenden Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="e07c8-121">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="e07c8-122">Konfigurieren Sie als daraufhin auf der neuen SharePoint Online-Teamwebsite die gewünschten Berechtigungen anhand der folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="e07c8-122">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="e07c8-123">Klicken Sie in der Symbolleiste der SharePoint-Teamwebsite auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="e07c8-123">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="e07c8-124">Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="e07c8-124">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="e07c8-125">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e07c8-125">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="e07c8-126">Die Ergebnisse dieser Berechtigungseinstellungen sehen folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="e07c8-126">The results of these permission settings are:</span></span>

- <span data-ttu-id="e07c8-127">Die Möglichkeit, dass Mitglieder Inhalte mit anderen Mitgliedern teilen, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e07c8-127">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="e07c8-128">Die Möglichkeit, dass Nicht-Mitglieder Zugriff anfordern, ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e07c8-128">The ability for non-members to request access is enabled.</span></span>

<span data-ttu-id="e07c8-129">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e07c8-129">Here is your resulting configuration.</span></span>
  
![Schutzebene „Vertraulich“ für eine isolierte SharePoint Online-Teamwebsite.](../media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="e07c8-131">Die Mitglieder der Website können nun über Gruppenmitgliedschaft in einer der Zugriffsgruppen sicher an den Ressourcen der Website zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e07c8-131">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="e07c8-132">Streng vertrauliche SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="e07c8-132">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="e07c8-133">Bei einer streng vertraulichen SharePoint Online-Teamwebsite handelt es sich um eine private Teamwebsite mit zusätzlichen Berechtigungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e07c8-133">A highly confidential SharePoint Online team site is a private team site with additional permissions settings.</span></span>

<span data-ttu-id="e07c8-134">Erstellen Sie zuerst die private SharePoint Online-Teamwebsite laut den [folgenden Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="e07c8-134">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="e07c8-135">Konfigurieren Sie als daraufhin auf der neuen SharePoint Online-Teamwebsite die gewünschten Berechtigungen anhand der folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="e07c8-135">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="e07c8-136">Klicken Sie in der Symbolleiste der SharePoint-Teamwebsite auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="e07c8-136">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="e07c8-137">Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="e07c8-137">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="e07c8-138">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus.</span><span class="sxs-lookup"><span data-stu-id="e07c8-138">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="e07c8-139">Deaktivieren Sie **Zugriffsanforderungen zulassen**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e07c8-139">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="e07c8-140">Die Ergebnisse dieser Berechtigungseinstellungen sehen folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="e07c8-140">The results of these permission settings are:</span></span>

- <span data-ttu-id="e07c8-141">Die Möglichkeit, dass Mitglieder Inhalte mit anderen Mitgliedern teilen, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e07c8-141">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="e07c8-142">Die Möglichkeit, dass Nicht-Mitglieder Zugriff anfordern, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e07c8-142">The ability for non-members to request access is disabled.</span></span>

<span data-ttu-id="e07c8-143">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e07c8-143">Here is your resulting configuration.</span></span>
  
![Schutzebene „Streng vertraulich“ für eine isolierte SharePoint Online-Teamwebsite.](../media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="e07c8-145">Die Mitglieder der Website können nun über Gruppenmitgliedschaft in einer der Zugriffsgruppen sicher an den Ressourcen der Website zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e07c8-145">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="e07c8-146">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e07c8-146">Next step</span></span>

[<span data-ttu-id="e07c8-147">Schützen von SharePoint Online-Dateien mit Bezeichnungen und Verhindern von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="e07c8-147">Protect SharePoint Online files with labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a><span data-ttu-id="e07c8-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e07c8-148">See also</span></span>

[<span data-ttu-id="e07c8-149">Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützigen Organisationen und andere agile Organisationen</span><span class="sxs-lookup"><span data-stu-id="e07c8-149">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="e07c8-150">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="e07c8-150">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
