---
title: Entwerfen einer isolierten SharePoint Online-Teamwebsite
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Entwerfen Sie isolierte SharePoint Online-Teamwebsites, einschließlich der Bestimmung von Berechtigungsstufen, zuweisen von Berechtigungen zu Benutzern mit Zugriffsgruppen und geschachtelten Azure AD-Gruppen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0f92a925948dbf6c8c5c1beb6b9c709f508c4b3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165511"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="2a4b8-103">Entwerfen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="2a4b8-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2a4b8-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="2a4b8-104">**Applies to**</span></span>
- [<span data-ttu-id="2a4b8-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="2a4b8-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="2a4b8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a4b8-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


 <span data-ttu-id="2a4b8-107">**Zusammenfassung:** Lernen Sie die Schritte zum Entwerfen von isolierten SharePoint Online-Teamwebsites kennen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-107">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="2a4b8-108">In diesem Artikel werden die wichtigsten Entwurfsentscheidungen erläutert, die Sie vor der Erstellung einer isolierten SharePoint Online-Teamwebsite treffen müssen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-108">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="2a4b8-109">Phase 1: Ermitteln der SharePoint-Gruppen und Berechtigungsstufen</span><span class="sxs-lookup"><span data-stu-id="2a4b8-109">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="2a4b8-110">Jede SharePoint Online-Teamwebsite wird standardmäßig mit den folgenden SharePoint-Gruppen erstellt:</span><span class="sxs-lookup"><span data-stu-id="2a4b8-110">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="2a4b8-111">\<site name> Member</span><span class="sxs-lookup"><span data-stu-id="2a4b8-111">\<site name> Members</span></span>

- <span data-ttu-id="2a4b8-112">\<site name> Besucher</span><span class="sxs-lookup"><span data-stu-id="2a4b8-112">\<site name> Visitors</span></span>

- <span data-ttu-id="2a4b8-113">\<site name> Besitzer</span><span class="sxs-lookup"><span data-stu-id="2a4b8-113">\<site name> Owners</span></span>

<span data-ttu-id="2a4b8-114">Diese Gruppen sind von Microsoft 365- und Azure Active Directory (AD)-Gruppen getrennt und stellen die Grundlage für die Zuweisung von Berechtigungen für die Ressourcen der Website bereit.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-114">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="2a4b8-p101">Der Satz von spezifischen Berechtigungen, der bestimmt, welche Aktionen ein Mitglied einer SharePoint-Gruppe auf einer Website ausführen kann, ist eine Berechtigungsstufe. Für eine SharePoint Online-Teamwebsite gibt es standardmäßig drei Berechtigungsstufen: Bearbeitungszugriff, Lesezugriff und Vollzugriff. In der folgenden Tabelle ist die standardmäßige Korrelation von SharePoint-Gruppen und zugewiesenen Berechtigungsstufen dargestellt:</span><span class="sxs-lookup"><span data-stu-id="2a4b8-p101">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level. There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control. The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="2a4b8-118">SharePoint-Gruppe</span><span class="sxs-lookup"><span data-stu-id="2a4b8-118">SharePoint group</span></span>|<span data-ttu-id="2a4b8-119">Berechtigungsstufe</span><span class="sxs-lookup"><span data-stu-id="2a4b8-119">Permission level</span></span>|
|---|---|
|<span data-ttu-id="2a4b8-120">\<site name> Member</span><span class="sxs-lookup"><span data-stu-id="2a4b8-120">\<site name> Members</span></span>|<span data-ttu-id="2a4b8-121">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="2a4b8-121">Edit</span></span>|
|<span data-ttu-id="2a4b8-122">\<site name> Besucher</span><span class="sxs-lookup"><span data-stu-id="2a4b8-122">\<site name> Visitors</span></span>|<span data-ttu-id="2a4b8-123">Lesen</span><span class="sxs-lookup"><span data-stu-id="2a4b8-123">Read</span></span>|
|<span data-ttu-id="2a4b8-124">\<site name> Besitzer</span><span class="sxs-lookup"><span data-stu-id="2a4b8-124">\<site name> Owners</span></span>|<span data-ttu-id="2a4b8-125">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="2a4b8-125">Full control</span></span>|
|

 <span data-ttu-id="2a4b8-p102">**Bewährte Methode:** Sie können weitere SharePoint-Gruppen und Berechtigungsstufen erstellen. Allerdings wird empfohlen, die SharePoint-Standardgruppen und die Berechtigungsstufen für die isolierte SharePoint Online-Website zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-p102">**Best practice:** You can create additional SharePoint groups and permission levels. However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="2a4b8-128">Hier sind die standardmäßigen SharePoint-Gruppen und -Berechtigungsstufen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-128">Here are the default SharePoint groups and permission levels.</span></span>

![Die standardmäßigen SharePoint-Gruppen und -Berechtigungsstufen für eine SharePoint Online-Website.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="2a4b8-130">Phase 2: Zuweisen von Berechtigungen zu Benutzern mit Zugriffsgruppen</span><span class="sxs-lookup"><span data-stu-id="2a4b8-130">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="2a4b8-131">Sie können Benutzern Berechtigungen zuweisen, indem Sie ihr Benutzerkonto oder eine Microsoft 365- oder Azure AD-Gruppe, in der das Benutzerkonto Mitglied ist, den SharePoint-Gruppen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-131">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="2a4b8-132">Nach dem Hinzufügen werden den Benutzerkonten, entweder direkt oder indirekt über die Mitgliedschaft in einer Microsoft 365- oder Azure AD-Gruppe, die der SharePoint-Gruppe zugeordnete Berechtigungsstufe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-132">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="2a4b8-133">Am Beispiel der SharePoint-Standardgruppen bedeutet dies:</span><span class="sxs-lookup"><span data-stu-id="2a4b8-133">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="2a4b8-134">Mitgliedern der **\<site name> Mitglieder der** SharePoint-Gruppe, die Benutzerkonten und Gruppen umfassen kann, wird die Berechtigungsstufe "Bearbeiten"  zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-134">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="2a4b8-135">Mitgliedern der **\<site name> Besucher-SharePoint-Gruppe,** die Sowohl Benutzerkonten als auch Gruppen umfassen kann, wird die Berechtigungsstufe "Lesen"  zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-135">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="2a4b8-136">Mitgliedern der **\<site name> Besitzer-SharePoint-Gruppe,** die Sowohl Benutzerkonten als auch Gruppen umfassen kann, wird die Berechtigungsstufe **"Vollpunkt"** zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-136">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="2a4b8-p104">**Bewährte Methode:** Obwohl Sie Berechtigungen über einzelne Benutzerkonten verwalten können, empfehlen wir stattdessen die Verwendung einer einzelnen Azure AD-Gruppe, die als Zugriffsgruppe bezeichnet wird. Dadurch wird die Verwaltung von Berechtigungen über Mitgliedschaft in der Zugriffsgruppe anstelle der Verwaltung der Liste von Benutzerkonten für jede SharePoint-Gruppe erleichtert.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-p104">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead. This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="2a4b8-139">Azure AD-Gruppen für Microsoft 365 sind unterschiedliche Microsoft 365-Gruppen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-139">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="2a4b8-140">Azure AD-Gruppen werden im Microsoft 365 Admin Center angezeigt, deren **Typ** auf **"Sicherheit"** festgelegt ist und keine E-Mail-Adresse haben.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-140">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="2a4b8-141">Azure AD-Gruppen können verwaltet werden in:</span><span class="sxs-lookup"><span data-stu-id="2a4b8-141">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="2a4b8-142">Active Directory-Domänendienste (AD DS)</span><span class="sxs-lookup"><span data-stu-id="2a4b8-142">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="2a4b8-143">Dies sind Gruppen, die in Ihrer lokalen AD DS-Infrastruktur erstellt und mit Ihrem Microsoft 365-Abonnement synchronisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-143">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="2a4b8-144">Im Microsoft 365 Admin Center haben diese Gruppen den **Status** "Synchronisiert mit **Active Directory".**</span><span class="sxs-lookup"><span data-stu-id="2a4b8-144">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="2a4b8-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="2a4b8-145">Office 365</span></span>

    <span data-ttu-id="2a4b8-146">Dies sind Gruppen, die mit dem Microsoft 365 Admin Center, dem Azure-Portal oder Microsoft PowerShell erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-146">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="2a4b8-147">Im Microsoft 365 Admin Center haben diese Gruppen den **Status** **"Cloud".**</span><span class="sxs-lookup"><span data-stu-id="2a4b8-147">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="2a4b8-148">**Bewährte Methode:** Wenn Sie AD DS lokal verwenden und mit Ihrem Microsoft 365-Abonnement synchronisieren, führen Sie die Benutzer- und Gruppenverwaltung mit AD DS durch.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-148">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="2a4b8-149">Für isolierte SharePoint Online-Teamwebsites sieht die empfohlene Gruppenstruktur wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="2a4b8-149">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="2a4b8-150">SharePoint-Gruppe</span><span class="sxs-lookup"><span data-stu-id="2a4b8-150">SharePoint group</span></span>|<span data-ttu-id="2a4b8-151">Azure AD-basierte Zugriffsgruppe</span><span class="sxs-lookup"><span data-stu-id="2a4b8-151">Azure AD-based access group</span></span>|<span data-ttu-id="2a4b8-152">Berechtigungsstufe</span><span class="sxs-lookup"><span data-stu-id="2a4b8-152">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="2a4b8-153">\<site name> Member</span><span class="sxs-lookup"><span data-stu-id="2a4b8-153">\<site name> Members</span></span>|<span data-ttu-id="2a4b8-154">\<site name> Member</span><span class="sxs-lookup"><span data-stu-id="2a4b8-154">\<site name> Members</span></span>|<span data-ttu-id="2a4b8-155">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="2a4b8-155">Edit</span></span>|
|<span data-ttu-id="2a4b8-156">\<site name> Besucher</span><span class="sxs-lookup"><span data-stu-id="2a4b8-156">\<site name> Visitors</span></span>|<span data-ttu-id="2a4b8-157">\<site name> Viewer</span><span class="sxs-lookup"><span data-stu-id="2a4b8-157">\<site name> Viewers</span></span>|<span data-ttu-id="2a4b8-158">Lesen</span><span class="sxs-lookup"><span data-stu-id="2a4b8-158">Read</span></span>|
|<span data-ttu-id="2a4b8-159">\<site name> Besitzer</span><span class="sxs-lookup"><span data-stu-id="2a4b8-159">\<site name> Owners</span></span>|<span data-ttu-id="2a4b8-160">\<site name> Administratoren</span><span class="sxs-lookup"><span data-stu-id="2a4b8-160">\<site name> Admins</span></span>|<span data-ttu-id="2a4b8-161">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="2a4b8-161">Full control</span></span>|
|

 <span data-ttu-id="2a4b8-162">**Bewährte Methode:** Obwohl Sie entweder Microsoft 365- oder Azure AD-Gruppen als Mitglieder von SharePoint-Gruppen verwenden können, empfehlen wir die Verwendung von Azure AD-Gruppen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-162">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="2a4b8-163">Azure AD-Gruppen, die entweder über AD DS oder Microsoft 365 verwaltet werden, bieten Ihnen mehr Flexibilität bei der Verwendung geschachtelter Gruppen zum Zuweisen von Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-163">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="2a4b8-164">Hier sind die standardmäßigen SharePoint-Gruppen, die für die Verwendung von Azure AD-basierten Zugriffsgruppen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-164">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![Verwenden von Zugriffsgruppen als Mitglieder standardmäßiger SharePoint Online-Websitegruppen.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="2a4b8-166">Beachten Sie beim Entwerfen der drei Zugriffsgruppen die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="2a4b8-166">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="2a4b8-167">In der Zugriffsgruppe "Administratoren" sollten nur wenige Mitglieder vorhanden sein, die einer kleinen Anzahl von SharePoint Online-Administratoren, die die Teamwebsite verwalten, entspricht. **\<site name>**</span><span class="sxs-lookup"><span data-stu-id="2a4b8-167">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="2a4b8-168">Die meisten Ihrer Websitemitglieder befinden sich in den **\<site name> Zugriffsgruppen "Mitglieder"** oder **\<site name> "Viewer".**</span><span class="sxs-lookup"><span data-stu-id="2a4b8-168">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="2a4b8-169">Da Websitemitglieder in **\<site name> der** Zugriffsgruppe "Mitglieder" die Möglichkeit haben, Ressourcen auf der Website zu löschen oder zu ändern, sollten Sie deren Mitgliedschaft sorgfältig abschätzen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-169">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="2a4b8-170">Fügen Sie im Zweifelsfall das Websitemitglied der Zugriffsgruppe **\<site name> "Viewer"** hinzu.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-170">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="2a4b8-171">Hier ist ein Beispiel für die SharePoint-Gruppen und Zugriffsgruppen für eine isolierte Website mit dem Namen ProjectX.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-171">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![Ein Beispiel für die Verwendung von Zugriffsgruppen für eine SharePoint Online-Website mit dem Namen ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="2a4b8-173">Phase 3: Verwenden von geschachtelten Azure AD-Gruppen</span><span class="sxs-lookup"><span data-stu-id="2a4b8-173">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="2a4b8-p110">Für ein Projekt, das auf eine kleine Anzahl von Personen beschränkt ist, ist es in den meisten Fällen ausreichend, den SharePoint-Gruppen der Website eine einzelne Ebene von Azure AD-basierten Zugriffsgruppen hinzuzufügen. Wenn jedoch eine große Anzahl von Personen vorhanden ist und diese Personen bereits Mitglied in bestehenden Azure AD-Gruppen sind, können Sie SharePoint-Berechtigungen einfacher mithilfe geschachtelter Gruppen zuweisen, d. h. Gruppen, die andere Gruppen als Mitglieder enthalten.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-p110">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios. However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="2a4b8-p111">Beispiel: Sie möchten eine isolierte SharePoint Online-Teamwebsite für die Zusammenarbeit zwischen den Leitern der Abteilungen Vertrieb, Marketing, Technik, Recht und Support erstellen, und diese Abteilungen haben bereits eigene Gruppen mit Benutzerkonten der Führungskräfte als Mitgliedern. Anstatt eine neue Gruppe für die neuen Websitemitglieder zu erstellen und alle einzelnen Benutzerkonten der Führungskräfte hinzuzufügen, fügen Sie die vorhandenen Führungskräftegruppen für die einzelnen Abteilung zur neuen Gruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-p111">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership. Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="2a4b8-178">Wenn Sie ein Microsoft 365-Abonnement für mehrere Organisationen freigeben, kann eine einzelne Ebene der Gruppenmitgliedschaft für eine isolierte Website für eine Organisation aufgrund der einfachen Anzahl von Benutzerkonten schwierig zu verwalten sein.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-178">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="2a4b8-179">In diesem Fall können Sie zum Verwalten der Berechtigungen geschachtelte Azure AD-Gruppen für jede Organisation verwenden, die die Gruppen innerhalb der Organisationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-179">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="2a4b8-180">So verwenden Sie geschachtelte Azure AD-Gruppen:</span><span class="sxs-lookup"><span data-stu-id="2a4b8-180">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="2a4b8-181">Identifizieren oder erstellen Sie die Azure AD-Gruppen, die Benutzerkonten enthalten sollen, und fügen Sie die entsprechenden Benutzerkonten als Mitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-181">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="2a4b8-182">Erstellen Sie die Azure AD-basierte Containerzugriffsgruppe, die die anderen Azure AD-Gruppen enthalten soll, und fügen Sie die Gruppen als Mitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-182">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="2a4b8-183"> Um die entsprechende Zugriffsebene für die Containerzugriffsgruppe festzulegen, identifizieren Sie die SharePoint-Gruppe und die entsprechende Berechtigungsstufe.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-183">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="2a4b8-184">Sie können keine geschachtelten Microsoft 365-Gruppen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-184">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="2a4b8-185">Hier ist ein Beispiel für geschachtelte Azure AD-Gruppen für die ProjectX-Mitgliederzugriffsgruppe.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-185">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![Ein Beispiel für die Verwendung von geschachtelten Zugriffsgruppen für die Mitgliederzugriffsgruppe für die ProjectX-Website.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="2a4b8-187">Da alle Benutzerkonten in den Teams "Forschung", "Technik" und "Project Leads" Websitemitglieder sein sollen, ist es einfacher, ihre Azure AD-Gruppen der Zugriffsgruppe "ProjectX-Mitglieder" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2a4b8-187">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="2a4b8-188">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="2a4b8-188">Next step</span></span>

<span data-ttu-id="2a4b8-189">Wenn Sie eine isolierte Website in der Produktion erstellen und konfigurieren möchten, finden Sie entsprechende Informationen unter [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="2a4b8-189">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a4b8-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a4b8-190">See Also</span></span>

[<span data-ttu-id="2a4b8-191">Isolierte SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="2a4b8-191">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="2a4b8-192">Verwalten einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="2a4b8-192">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="2a4b8-193">Bereitstellen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="2a4b8-193">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
