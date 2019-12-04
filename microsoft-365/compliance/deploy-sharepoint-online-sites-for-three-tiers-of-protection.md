---
title: Bereitstellen von SharePoint Online-Websites für drei Schutzebenen
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
ms.openlocfilehash: 1396a45103bfbaf6ea2de6c5ba6c4b086da344ec
ms.sourcegitcommit: 58a7bd70a4bcf52530baf5f82507fd5dc4455fd9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "39668863"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="f76d4-103">Bereitstellen von SharePoint Online-Websites für drei Schutzebenen</span><span class="sxs-lookup"><span data-stu-id="f76d4-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

<span data-ttu-id="f76d4-p101">Verwenden Sie die Schritte in diesem Artikel, um Richtlinien für grundlegende, vertrauliche und streng vertrauliche SharePoint Online-Teamwebsites zu entwerfen. Weitere Informationen zu diesen drei Schutzebenen finden Sie unter [Sichern von SharePoint Online-Websites und -Dateien](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="f76d4-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="f76d4-106">Grundlegende SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="f76d4-106">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="f76d4-p102">Der grundlegende Schutz enthält jeweils öffentliche und private Teamwebsites. Öffentliche Teamwebsites können von allen Benutzern in der Organisation ermittelt werden und alle haben Zugriff auf diese. Nur Mitglieder der Office 365-Gruppe, die mit der Teamwebsite verknüpft sind, können die privaten Websites ermitteln und auf diese zugreifen. Diese beiden Arten von Teamwebsites erlauben Mitgliedern, die Website für andere Personen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="f76d4-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="f76d4-111">Public (Öffentlich)</span><span class="sxs-lookup"><span data-stu-id="f76d4-111">Public</span></span>

<span data-ttu-id="f76d4-112">Um eine grundlegende SharePoint Online-Teamwebsite mit öffentlichem Zugriff und Berechtigungen zu erstellen, befolgen Sie bitte [diese Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="f76d4-112">To create a baseline SharePoint Online team site with public access and permissions, do the following:</span></span>

<span data-ttu-id="f76d4-113">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f76d4-113">Here is your resulting configuration.</span></span>
  
![Grundschutz für eine öffentliche SharePoint Online-Teamwebsite.](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="f76d4-115">Privat</span><span class="sxs-lookup"><span data-stu-id="f76d4-115">Private</span></span>

<span data-ttu-id="f76d4-116">Um eine grundlegende SharePoint Online-Teamwebsite mit privatem Zugriff und Berechtigungen zu erstellen, befolgen Sie bitte [diese Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="f76d4-116">To create a baseline SharePoint Online team site with private access and permissions, do the following:</span></span>
  
<span data-ttu-id="f76d4-117">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f76d4-117">Here is your resulting configuration.</span></span>
  
![Grundschutz für eine private SharePoint Online-Teamwebsite.](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="f76d4-119">Vertrauliche SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="f76d4-119">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="f76d4-120">Eine sensible SharePoint Online-Teamwebsite wird zunächst als private Teamwebsite erstellt.</span><span class="sxs-lookup"><span data-stu-id="f76d4-120">A sensitive SharePoint Online team site starts as a private team site.</span></span>
  
<span data-ttu-id="f76d4-121">Erstellen Sie zuerst die private SharePoint Online-Teamwebsite laut den [folgenden Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="f76d4-121">First, create the SharePoint Online team site with these steps.</span></span>

<span data-ttu-id="f76d4-122">Konfigurieren Sie als daraufhin auf der neuen SharePoint Online-Teamwebsite die gewünschten Berechtigungen anhand der folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="f76d4-122">Next, from the new SharePoint Online team site, configure permissions with these steps.</span></span>

1.  <span data-ttu-id="f76d4-123">Klicken Sie in der Symbolleiste der SharePoint-Teamwebsite auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="f76d4-123">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="f76d4-124">Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="f76d4-124">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="f76d4-125">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f76d4-125">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="f76d4-126">Die Ergebnisse dieser Berechtigungseinstellungen sehen folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="f76d4-126">The results of these permission settings are:</span></span>

- <span data-ttu-id="f76d4-127">Die Möglichkeit, dass Mitglieder Inhalte mit anderen Mitgliedern teilen, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f76d4-127">The ability for members to invite other members is disabled.</span></span>
- <span data-ttu-id="f76d4-128">Die Möglichkeit, dass Nicht-Mitglieder Zugriff anfordern, ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f76d4-128">The ability for non-members to request access is enabled.</span></span>

<span data-ttu-id="f76d4-129">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f76d4-129">Here is your resulting configuration.</span></span>
  
![Schutzebene „Vertraulich“ für eine isolierte SharePoint Online-Teamwebsite.](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="f76d4-131">Die Mitglieder der Website können nun über Gruppenmitgliedschaft in einer der Zugriffsgruppen sicher an den Ressourcen der Website zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f76d4-131">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="f76d4-132">Streng vertrauliche SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="f76d4-132">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="f76d4-133">Bei einer streng vertraulichen SharePoint Online-Teamwebsite handelt es sich um eine private Teamwebsite mit zusätzlichen Berechtigungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f76d4-133">A highly confidential SharePoint Online team site is a private team site with additional permissions settings.</span></span>

<span data-ttu-id="f76d4-134">Erstellen Sie zuerst die private SharePoint Online-Teamwebsite laut den [folgenden Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="f76d4-134">First, create the SharePoint Online team site with these steps.</span></span>

<span data-ttu-id="f76d4-135">Konfigurieren Sie als daraufhin auf der neuen SharePoint Online-Teamwebsite die gewünschten Berechtigungen anhand der folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="f76d4-135">Next, from the new SharePoint Online team site, configure permissions with these steps.</span></span>

1.  <span data-ttu-id="f76d4-136">Klicken Sie in der Symbolleiste der SharePoint-Teamwebsite auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="f76d4-136">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="f76d4-137">Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="f76d4-137">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="f76d4-138">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus.</span><span class="sxs-lookup"><span data-stu-id="f76d4-138">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="f76d4-139">Deaktivieren Sie **Zugriffsanforderungen zulassen**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f76d4-139">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="f76d4-140">Die Ergebnisse dieser Berechtigungseinstellungen sehen folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="f76d4-140">The results of these permission settings are:</span></span>

- <span data-ttu-id="f76d4-141">Die Möglichkeit, dass Mitglieder Inhalte mit anderen Mitgliedern teilen, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f76d4-141">The ability for members to invite other members is disabled.</span></span>
- <span data-ttu-id="f76d4-142">Die Möglichkeit, dass Nicht-Mitglieder Zugriff anfordern, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f76d4-142">The ability for non-members to request access is disabled.</span></span>

<span data-ttu-id="f76d4-143">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f76d4-143">Here is your resulting configuration.</span></span>
  
![Schutzebene „Streng vertraulich“ für eine isolierte SharePoint Online-Teamwebsite.](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="f76d4-145">Die Mitglieder der Website können nun über Gruppenmitgliedschaft in einer der Zugriffsgruppen sicher an den Ressourcen der Website zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f76d4-145">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="f76d4-146">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f76d4-146">Next step</span></span>

[<span data-ttu-id="f76d4-147">Schützen von SharePoint Online-Dateien mit Office 365-Bezeichnungen und Verhindern von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="f76d4-147">Protect SharePoint Online files with Office 365 labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a><span data-ttu-id="f76d4-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f76d4-148">See also</span></span>

[<span data-ttu-id="f76d4-149">Sichern von SharePoint Online-Websites und -Dateien</span><span class="sxs-lookup"><span data-stu-id="f76d4-149">Secure SharePoint Online sites and files</span></span>](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="f76d4-150">Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützige Organisationen und andere agile Organisationen</span><span class="sxs-lookup"><span data-stu-id="f76d4-150">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="f76d4-151">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="f76d4-151">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
