---
title: Begrenzen der versehentlichen Exposition
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
description: Erfahren Sie, wie Sie die versehentliche Exposition von Informationen bei der Freigabe von Dateien für Personen außerhalb der Organisation begrenzen.
ms.openlocfilehash: 952337790ce2f0418dd5ab637435f1523b27b562
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928412"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a><span data-ttu-id="4f125-103">Begrenzen der versehentlichen Exposition von Dateien bei deren Freigabe für Personen außerhalb der Organisation</span><span class="sxs-lookup"><span data-stu-id="4f125-103">Limit accidental exposure to files when sharing with people outside your organization</span></span>

<span data-ttu-id="4f125-104">Bei der Freigabe von Dateien und Ordnern für Personen außerhalb der Organisation gibt es eine Vielzahl an Optionen, um das Risiko zu minimieren, dass vertrauliche Informationen versehentlich freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4f125-104">When sharing files and folders with people outside your organization, there are a variety of options to reduce the chances of accidentally sharing sensitive information.</span></span> <span data-ttu-id="4f125-105">Sie können aus den Optionen in diesem Artikel wählen, um die Anforderungen Ihrer Organisation optimal zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="4f125-105">You can choose from the options in this article to best meet the needs of your organization.</span></span>

## <a name="use-best-practices-for-anyone-links"></a><span data-ttu-id="4f125-106">Bewährte Methoden für „Jeder“-Links verwenden</span><span class="sxs-lookup"><span data-stu-id="4f125-106">Use best practices for Anyone links</span></span>

<span data-ttu-id="4f125-107">Wenn Personen in Ihrer Organisation eine Freigabe ohne Authentifizierung vornehmen müssen, Sie jedoch befürchten, dass nicht authentifizierte Personen Inhalte ändern, lesen Sie [Bewährte Methoden für die Freigabe ohne Authentifizierung](best-practices-anonymous-sharing.md), um Anleitungen zum Arbeiten mit der Freigabe ohne Authentifizierung in Ihrer Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4f125-107">If people in your organization need to do unauthenticated sharing, but you're concerned about unauthenticated people modifying content, read [Best practices for unauthenticated sharing](best-practices-anonymous-sharing.md) for guidance on how to work with unauthenticated sharing in your organization.</span></span>

## <a name="turn-off-anyone-links"></a><span data-ttu-id="4f125-108">Deaktivieren von "Jeder"-Links</span><span class="sxs-lookup"><span data-stu-id="4f125-108">Turn off Anyone links</span></span>

<span data-ttu-id="4f125-109">Wir empfehlen, die *Jeder*-Links für den entsprechenden Inhalt aktiviert zu lassen, da dies die einfachste Freigabemöglichkeit ist und das Risiko reduziert, dass Benutzer andere Lösungen außerhalb der Kontrolle Ihrer IT-Abteilung suchen.</span><span class="sxs-lookup"><span data-stu-id="4f125-109">We recommend leaving *Anyone* links enabled for appropriate content because it's the easiest way to share and can help reduce the risk of users seeking other solutions that are outside the control of your IT department.</span></span> <span data-ttu-id="4f125-110">*Jeder*-Links können an andere weitergeleitet werden, aber Dateizugriff ist nur für diejenigen möglich, die den Link haben.</span><span class="sxs-lookup"><span data-stu-id="4f125-110">*Anyone* links can be forwarded to others, but file access is only available to those who have the link.</span></span>

<span data-ttu-id="4f125-111">Wenn Personen von außerhalb der Organisation sich beim Zugreifen auf Inhalte in SharePoint, Gruppen oder Teams authentifizieren sollen, können Sie die *Jeder*-Freigabe deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4f125-111">If you always want people outside your organization to authenticate when accessing content in SharePoint, Groups, or Teams, you can turn off *Anyone* sharing.</span></span> <span data-ttu-id="4f125-112">Das verhindert, dass Benutzer Inhalte ohne Authentifizierung freigeben.</span><span class="sxs-lookup"><span data-stu-id="4f125-112">This will prevent users from unauthenticated sharing of content.</span></span>

<span data-ttu-id="4f125-113">Wenn Sie die *Jeder*-Links deaktivieren, können Benutzer Elemente weiterhin mit *Bestimmte Personen*-Links für Gäste freigeben.</span><span class="sxs-lookup"><span data-stu-id="4f125-113">If you disable *Anyone* links, users can still easily share with guests using *Specific people* links.</span></span> <span data-ttu-id="4f125-114">In diesem Fall müssen sich alle Personen außerhalb der Organisation authentifizieren, bevor sie auf die freigegebenen Inhalte zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="4f125-114">In this case, all people outside your organization will be required to authenticate before they can access the shared content.</span></span>

<span data-ttu-id="4f125-115">Je nach Ihren Anforderungen können Sie *Jeder*-Links für bestimmte Sites oder für Ihre gesamte Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4f125-115">Depending on your needs, you can disable *Anyone* links for specific sites, or for your whole organization.</span></span>

<span data-ttu-id="4f125-116">So deaktivieren Sie *Jeder*-Links für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="4f125-116">To turn off *Anyone* links for your organization</span></span>
1. <span data-ttu-id="4f125-117">Klicken Sie im SharePoint Admin Center links in der Navigation auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="4f125-117">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="4f125-118">Legen Sie für die SharePoint-Einstellungen für die externe Freigabe **Neue und vorhandene Gäste** fest.</span><span class="sxs-lookup"><span data-stu-id="4f125-118">Set the SharePoint external sharing settings to **New and existing guests**.</span></span>

   ![Screenshot der externen SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. <span data-ttu-id="4f125-120">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4f125-120">Click **Save**.</span></span>

<span data-ttu-id="4f125-121">So deaktivieren Sie *Jeder*-Links für eine Site</span><span class="sxs-lookup"><span data-stu-id="4f125-121">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="4f125-122">Erweitern Sie im SharePoint Admin Center links in der Navigation **Sites** und klicken Sie auf **Aktive Sites**.</span><span class="sxs-lookup"><span data-stu-id="4f125-122">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="4f125-123">Wählen Sie die Website aus, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4f125-123">Select the site that you want to configure.</span></span>
3. <span data-ttu-id="4f125-124">Klicken Sie im Menüband auf **Freigabe**. </span><span class="sxs-lookup"><span data-stu-id="4f125-124">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="4f125-125">Vergewissern Sie sich, dass die Freigabe auf **Neue und vorhandene Gäste** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4f125-125">Ensure that sharing is set to **New and existing guests**.</span></span>

   ![Screenshot der externen SharePoint-Freigabeeinstellungen auf Websiteebene](../media/sharepoint-site-external-sharing-settings.png)

5. <span data-ttu-id="4f125-127">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4f125-127">If you made changes, click **Save**.</span></span>

## <a name="domain-filtering"></a><span data-ttu-id="4f125-128">Domänenfilter</span><span class="sxs-lookup"><span data-stu-id="4f125-128">Domain filtering</span></span>

<span data-ttu-id="4f125-129">Sie können Zulassungs- oder Verweigerungsliste für Domänen verwenden, um festzulegen, welche Domänen Ihre Benutzer bei der Freigabe für Personen außerhalb der Organisation verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4f125-129">You can use domain allow or deny lists to specify which domains your users can use when sharing with people outside your organization.</span></span>

<span data-ttu-id="4f125-130">Mit einer Zulassungsliste können Sie eine Liste der Domänen festlegen, aus denen Benutzer in Ihrer Organisation Inhalte für Personen außerhalb der Organisation freigeben können.</span><span class="sxs-lookup"><span data-stu-id="4f125-130">With an allow list, you can specify a list of domains where users in your organization can share with people outside your organization.</span></span> <span data-ttu-id="4f125-131">Die Freigabe für andere Domänen wird blockiert.</span><span class="sxs-lookup"><span data-stu-id="4f125-131">Sharing with to other domains is blocked.</span></span> <span data-ttu-id="4f125-132">Wenn Ihre Organisation nur mit Personen aus einer Liste bestimmter Domänen zusammenarbeitet, können Sie diese Funktion verwenden, um die Freigabe für andere Domänen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="4f125-132">If your organization only collaborates with people from a list of specific domains, you can use this feature to prevent sharing with other domains.</span></span>

<span data-ttu-id="4f125-133">Mit einer Verweigerungsliste können Sie eine Liste der Domänen festlegen, aus denen Benutzer in Ihrer Organisation keine Inhalte für Personen außerhalb der Organisation freigeben können.</span><span class="sxs-lookup"><span data-stu-id="4f125-133">With a deny list, you can specify a list of domains from which users in your organization cannot share with people outside your organization.</span></span> <span data-ttu-id="4f125-134">Die Freigabe der aufgeführten Domänen wird blockiert.</span><span class="sxs-lookup"><span data-stu-id="4f125-134">Sharing with the listed domains is blocked.</span></span> <span data-ttu-id="4f125-135">Dies kann hilfreich sein, wenn Sie beispielsweise Konkurrenten haben, die Sie daran hindern möchten, auf Inhalte in Ihrer Organisation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4f125-135">This can be useful if you have competitors, for example, who you want to prevent from accessing content in your organization.</span></span>

<span data-ttu-id="4f125-136">Die Zulassungs- und Verweigerungslisten wirken sich nur auf die Freigabe für Gäste aus.</span><span class="sxs-lookup"><span data-stu-id="4f125-136">The allow and deny lists only affect sharing with guests.</span></span> <span data-ttu-id="4f125-137">Benutzer können weiterhin für Personen aus verbotenen Domänen freigeben, indem sie *Jeder*-Links verwenden, wenn Sie diese nicht deaktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="4f125-137">Users can still share with people from prohibited domains by using *Anyone* links if you haven't disabled them.</span></span> <span data-ttu-id="4f125-138">Für optimale Ergebnisse in Bezug auf die Zulassungs- und Ablehnungslisten für Domänen, ziehen Sie die Deaktivierung von *Jeder*-Links wie oben beschrieben in Betracht.</span><span class="sxs-lookup"><span data-stu-id="4f125-138">For best results with domain allow and deny lists, consider disabling *Anyone* links as described above.</span></span>

<span data-ttu-id="4f125-139">So richten Sie eine Zulassungs- oder Ablehnungsliste ein</span><span class="sxs-lookup"><span data-stu-id="4f125-139">To set up a domain allow or deny list</span></span>
1. <span data-ttu-id="4f125-140">Klicken Sie im SharePoint Admin Center links in der Navigation auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="4f125-140">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="4f125-141">Aktivieren Sie unter **Erweiterte Einstellungen für externe Freigabe** das Kontrollkästchen **Externe Freigabe nach Domäne einschränken**.</span><span class="sxs-lookup"><span data-stu-id="4f125-141">Under **Advanced settings for external sharing**, select the **Limit external sharing by domain** check box.</span></span>
3. <span data-ttu-id="4f125-142">Klicken Sie auf **Domänen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4f125-142">Click **Add domains**.</span></span>
4. <span data-ttu-id="4f125-143">Wählen Sie aus, ob Domänen blockiert werden sollen, geben Sie die Domänen ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f125-143">Select whether you want to block domains, type the domains, and click **OK**.</span></span>

   ![Screenshot der SharePoint-Einstellung "Einschränken der externen Freigabe mithilfe von Domänen"](../media/sharepoint-sharing-block-domain.png)

5. <span data-ttu-id="4f125-145">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4f125-145">Click **Save**.</span></span>

<span data-ttu-id="4f125-146">Wenn Sie die Freigabe mithilfe von Domänen auf einer höheren Ebene als SharePoint und OneDrive einschränken möchten, [lassen Sie Einladungen in Azure Active Directory für B2B-Benutzer aus bestimmten Organisationen zu oder blockieren Sie sie](/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="4f125-146">If you want to limit sharing by domain at a higher level than SharePoint and OneDrive, you can [allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list) in Azure Active Directory.</span></span> <span data-ttu-id="4f125-147">(Sie müssen die [SharePoint- und OneDrive-Integration mit Azure AD B2B Preview](/sharepoint/sharepoint-azureb2b-integration-preview) konfigurieren, damit diese Einstellungen für SharePoint und OneDrive wirksam sind.)</span><span class="sxs-lookup"><span data-stu-id="4f125-147">(You must configure the [SharePoint and OneDrive integration with Azure AD B2B Preview](/sharepoint/sharepoint-azureb2b-integration-preview) for these settings to affect SharePoint and OneDrive.)</span></span>

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a><span data-ttu-id="4f125-148">Einschränken der Freigabe von Dateien, Ordnern und Websites für Personen außerhalb Ihrer Organisation auf bestimmte Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="4f125-148">Limit sharing of files, folders, and sites with people outside your organization to specified security groups</span></span>

<span data-ttu-id="4f125-149">Sie können die Freigabe von Dateien, Ordnern und Websites für Personen außerhalb Ihrer Organisation auf Mitglieder einer bestimmten Sicherheitsgruppe einschränken.</span><span class="sxs-lookup"><span data-stu-id="4f125-149">You can restrict sharing of files, folders, and sites with people outside your organization to members of a specific security group.</span></span> <span data-ttu-id="4f125-150">Dies ist nützlich, wenn Sie die externe Freigabe aktivieren, dafür aber einen Genehmigungsworkflow oder einem Anforderungsprozess festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="4f125-150">This is useful if you want to enable external sharing, but with an approval workflow or request process.</span></span> <span data-ttu-id="4f125-151">Alternativ dazu können Sie von Ihren Benutzern verlangen, dass sie einen Schulungskurs absolvieren, bevor sie der Sicherheitsgruppe hinzugefügt werden und ihnen die externe Freigage erlaubt wird.</span><span class="sxs-lookup"><span data-stu-id="4f125-151">Alternatively, you might require your users to complete a training course before they're added to the security group and are allowed to share externally.</span></span>

<span data-ttu-id="4f125-152">So schränken Sie die externe Freigabe auf Mitglieder einer Sicherheitsgruppe ein</span><span class="sxs-lookup"><span data-stu-id="4f125-152">To limit external sharing to members of a security group</span></span>
1. <span data-ttu-id="4f125-153">Klicken Sie im [SharePoint Admin Center](https://admin.microsoft.com/sharepoint) links in der Navigation unter **Richtlinien** auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="4f125-153">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), in the left navigation, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="4f125-154">Erweitern Sie **Weitere Einstellungen für die externe Freigabe** unter **Externe Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="4f125-154">Under **External sharing**, expand **More external sharing settings**.</span></span>

3. <span data-ttu-id="4f125-155">Wählen Sie **Ausschließlich Benutzern in bestimmten Sicherheitsgruppen die externe Freigabe erlauben** und dann **Sicherheitsgruppen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="4f125-155">Select **Allow only users in specific security groups to share externally**, and then select **Manage security groups**.</span></span>

    ![Screenshot des Bereichs "Sicherheitsgruppen verwalten"](/sharepoint/sharepointonline/media/manage-security-groups.png)

4. <span data-ttu-id="4f125-157">Geben Sie im Feld **Sicherheitsgruppe hinzufügen** einen Namen für eine Sicherheitsgruppe ein.</span><span class="sxs-lookup"><span data-stu-id="4f125-157">In the **Add a security group** box, enter a name for a security group.</span></span> <span data-ttu-id="4f125-158">Das Feld "Sicherheitsgruppe" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4f125-158">The security group box appears.</span></span>

5. <span data-ttu-id="4f125-159">Wählen Sie neben dem Namen der Sicherheitsgruppe aus der Dropdownliste **kann freigeben für** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="4f125-159">Next to the security group name, from the **Can share with** dropdown, select either:</span></span>

    - <span data-ttu-id="4f125-160">**Nur authentifizierte Gäste** (Standard)</span><span class="sxs-lookup"><span data-stu-id="4f125-160">**Authenticated guests only** (default)</span></span>
    - <span data-ttu-id="4f125-161">**Jeder**</span><span class="sxs-lookup"><span data-stu-id="4f125-161">**Anyone**</span></span>

6. <span data-ttu-id="4f125-162">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4f125-162">Select **Save**.</span></span>

<span data-ttu-id="4f125-163">Dies wirkt sich auf Dateien, Ordner und Sites, aber nicht auf Microsoft 365-Gruppen oder -Teams aus.</span><span class="sxs-lookup"><span data-stu-id="4f125-163">Note that this affects files, folders, and sites, but not Microsoft 365 groups or Teams.</span></span> <span data-ttu-id="4f125-164">Wenn Mitglieder Gäste zu einer privaten Microsoft 365-Gruppe oder einem privaten Team in Microsoft Teams einladen, wird die Einladung zur Genehmigung an den Gruppen- oder Teambesitzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="4f125-164">When members invite guests to a private Microsoft 365 group or a private team in Microsoft Teams, the invitation is sent to the group or team owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f125-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f125-165">See Also</span></span>

[<span data-ttu-id="4f125-166">Erstellen einer sicheren Umgebung für die Gastfreigabe</span><span class="sxs-lookup"><span data-stu-id="4f125-166">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="4f125-167">Bewährte Methoden zum Freigeben von Dateien und Ordnern für anonyme Benutzer</span><span class="sxs-lookup"><span data-stu-id="4f125-167">Best practices for sharing files and folders with anonymous users</span></span>](best-practices-anonymous-sharing.md)