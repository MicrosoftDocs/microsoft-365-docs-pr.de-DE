---
title: Verwalten von Microsoft 365-Gruppen mit PowerShell
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: In diesem Artikel erfahren Sie, wie Sie allgemeine Verwaltungsaufgaben für Microsoft 365-Gruppen in PowerShell ausführen.
ms.openlocfilehash: c1aa551597644b7f41c3445a791ea27579464f7b
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277477"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="d348b-103">Verwalten von Microsoft 365-Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="d348b-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="d348b-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d348b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d348b-105">In diesem Artikel werden die Schritte zum Ausführen häufiger Verwaltungsaufgaben für Gruppen in Microsoft PowerShell beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d348b-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="d348b-106">Zudem sind die PowerShell-Cmdlets für Gruppen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d348b-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="d348b-107">Informationen zum Verwalten von SharePoint-Websites finden Sie unter [Verwalten von SharePoint Online-Websites mithilfe von PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="d348b-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="d348b-108">Link zu Ihren Microsoft 365-Gruppen-Nutzungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="d348b-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="d348b-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="d348b-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="d348b-110">Wenn Benutzer [eine Gruppe in Outlook erstellen oder bearbeiten](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), können Sie über einen Link auf die Nutzungsrichtlinien Ihrer Organisation verweisen.</span><span class="sxs-lookup"><span data-stu-id="d348b-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="d348b-111">Angenommen, einem Gruppennamen muss ein spezielles Präfix oder Suffix hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d348b-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="d348b-112">Verwenden Sie die Azure Active Directory (Azure AD) PowerShell, um Ihre Benutzer auf die Verwendungsrichtlinien Ihrer Organisation für Microsoft 365-Gruppen zu richten.</span><span class="sxs-lookup"><span data-stu-id="d348b-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="d348b-113">Lesen Sie [Azure Active Directory-Cmdlets zum Konfigurieren von Gruppeneinstellungen](https://go.microsoft.com/fwlink/?LinkID=827484), und führen Sie die Schritte unter **Erstellen von Einstellungen auf Verzeichnisebene** aus, um den Link zu den Nutzungsrichtlinien zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d348b-113">Check out [Azure Active Directory cmdlets for configuring group settings](https://go.microsoft.com/fwlink/?LinkID=827484) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="d348b-114">Nachdem Sie das AAD-Cmdlet ausgeführt haben, wird den Benutzern beim Erstellen oder Bearbeiten einer Gruppe in Outlook der Link zu Ihren Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d348b-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![Eine neue Gruppe mit Link zu Nutzungsrichtlinien erstellen](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Auf "Gruppennutzungsrichtlinien" klicken, um die Office 365-Gruppenrichtlinien Ihrer Organisation anzuzeigen](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="d348b-117">Zulassen, dass Benutzer als Microsoft 365-Gruppe senden</span><span class="sxs-lookup"><span data-stu-id="d348b-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="d348b-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="d348b-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="d348b-119">Wenn Sie möchten, dass Ihre Microsoft 365-Gruppen "Senden als" aktivieren, verwenden Sie die Cmdlets [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) und [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) , um dies zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d348b-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="d348b-120">Nachdem Sie diese Einstellung aktiviert haben, können Benutzer von Microsoft 365 Gruppe Outlook oder Outlook im Internet verwenden, um e-Mails als Microsoft 365-Gruppe zu senden und zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="d348b-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="d348b-121">Benutzer können zur Gruppe wechseln, eine neue E-Mail erstellen und das Feld "Senden als" in die E-Mail-Adresse der Gruppe ändern.</span><span class="sxs-lookup"><span data-stu-id="d348b-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="d348b-122">([Sie können diesen Schritt auch im Exchange Admin Center ausführen](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)).</span><span class="sxs-lookup"><span data-stu-id="d348b-122">([You can also do this in the Exchange Admin Center](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="d348b-123">Verwenden Sie das folgende Skript, *\<GroupAlias\>* und ersetzen Sie durch den Alias der Gruppe, die Sie aktualisieren möchten, und *\<UserAlias\>* mit dem Alias des Benutzers, dem Sie Berechtigungen erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="d348b-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="d348b-124">[Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), um das Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d348b-124">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="d348b-125">Sobald das Cmdlet ausgeführt wurde, können Benutzer zu Outlook oder Outlook im Web wechseln und als Gruppe senden, indem sie die E-Mail-Adresse der Gruppe zum Feld **Von** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d348b-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="d348b-126">Erstellen von Klassifizierungen für Microsoft 365-Gruppen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="d348b-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="d348b-127">Sie können Sensitivitäts Bezeichnungen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn Sie eine Microsoft 365-Gruppe erstellen.</span><span class="sxs-lookup"><span data-stu-id="d348b-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="d348b-128">Wenn Sie Gruppen klassifizieren möchten, empfehlen wir die Verwendung von Sensitivitäts Bezeichnungen anstelle des vorherigen Gruppen Klassifizierungs Features.</span><span class="sxs-lookup"><span data-stu-id="d348b-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="d348b-129">Informationen zur Verwendung von Sensitivitäts Bezeichnungen finden Sie unter [use Sensitivity Labels to Protect Content in Microsoft Teams, Microsoft 365 Groups und SharePoint Sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="d348b-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d348b-130">Wenn Sie derzeit Klassifizierungs Bezeichnungen verwenden, stehen diese nicht mehr für Benutzer zur Verfügung, die Gruppen erstellen, sobald die Vertraulichkeits Bezeichnungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d348b-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="d348b-131">Sie können weiterhin das vorherige Gruppen Klassifizierungs Feature verwenden.</span><span class="sxs-lookup"><span data-stu-id="d348b-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="d348b-132">Sie können Klassifikationen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn Sie eine Microsoft 365-Gruppe erstellen.</span><span class="sxs-lookup"><span data-stu-id="d348b-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="d348b-133">Beispielsweise können Sie den Benutzern gestatten, die Klassifizierungen "Standard", "Geheim" und "Streng geheim" für erstellte Gruppen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d348b-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="d348b-134">Gruppenklassifizierungen sind nicht standardmäßig festgelegt, und Sie müssen diese erstellen, damit sie von den Benutzern festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="d348b-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="d348b-135">Verwenden Sie Azure Active Directory PowerShell, um Ihre Benutzer auf die Verwendungsrichtlinien Ihrer Organisation für Microsoft 365-Gruppen zu richten.</span><span class="sxs-lookup"><span data-stu-id="d348b-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="d348b-136">Sehen Sie sich [Azure Active Directory-Cmdlets zum Konfigurieren von Gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) an, und führen Sie die Schritte in den **Erstellen von Einstellungen auf Verzeichnisebene** aus, um die Klassifizierung für Microsoft 365-Gruppen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d348b-136">Check out [Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="d348b-137">Mit dem settings-Attribut *ClassificationDescriptions* können Sie jeder Klassifizierung eine Beschreibung zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d348b-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="d348b-138">wobei die Klassifizierung mit den Zeichenfolgen in der ClassificationList übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="d348b-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="d348b-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d348b-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="d348b-140">Führen Sie nach dem oben genannten Azure Active Directory-Cmdlet zum Festlegen der Klassifizierung das Cmdlet [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) aus, wenn Sie die Klassifizierung für eine bestimmte Gruppe festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="d348b-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="d348b-141">Sie können auch eine neue Gruppe mit einer Klassifizierung erstellen.</span><span class="sxs-lookup"><span data-stu-id="d348b-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="d348b-142">Weitere Informationen zur Verwendung von Exchange Online PowerShell finden Sie unter [Verwenden von PowerShell mit Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) und [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d348b-142">Check out [Using PowerShell with Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="d348b-143">Sobald diese Einstellungen aktiviert sind, kann der Gruppenbesitzer eine Klassifizierung aus dem Dropdownmenü in Outlook im Web und Outlook auswählen und sie aus der Gruppenseite **Bearbeiten** speichern.</span><span class="sxs-lookup"><span data-stu-id="d348b-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Auswählen der Microsoft 365-Gruppen Klassifizierung](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="d348b-145">Ausblenden von Microsoft 365-Gruppen aus der globalen Adressliste.</span><span class="sxs-lookup"><span data-stu-id="d348b-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="d348b-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d348b-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d348b-147">Sie können angeben, ob eine Microsoft 365-Gruppe in der globalen Adressliste (GAL) und anderen Listen in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d348b-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="d348b-148">Wenn Sie beispielsweise eine Gruppe für juristische Abteilungen haben, die nicht in der Adressliste angezeigt werden soll, können Sie verhindern, dass die Gruppe in der GAL angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d348b-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="d348b-149">Führen Sie das Cmdlet Gruppe-Unified Group aus, um die Gruppe wie folgt aus der Adressliste auszublenden:</span><span class="sxs-lookup"><span data-stu-id="d348b-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="d348b-150">Zulassen, dass nur interne Benutzer Nachrichten an Microsoft 365-Gruppen senden</span><span class="sxs-lookup"><span data-stu-id="d348b-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="d348b-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d348b-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d348b-152">Wenn Sie nicht möchten, dass Benutzer aus anderen Organisationen e-Mails an eine Microsoft 365-Gruppe senden, können Sie die Einstellungen für diese Gruppe ändern.</span><span class="sxs-lookup"><span data-stu-id="d348b-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="d348b-153">So können nur interne Benutzer E-Mail-Nachrichten an Ihre Gruppe senden.</span><span class="sxs-lookup"><span data-stu-id="d348b-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="d348b-154">Wenn ein externer Benutzer versucht, eine Nachricht an diese Gruppe zu senden, wird er abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="d348b-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="d348b-155">Führen Sie das Cmdlet "Set-UnifiedGroup" wie folgt aus, um diese Einstellung zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="d348b-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="d348b-156">Hinzufügen von e-Mail-Infos zu Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="d348b-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="d348b-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d348b-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d348b-158">Wenn ein Absender versucht, eine e-Mail an eine Microsoft 365-Gruppe zu senden, kann ihm ein QuickInfo-angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d348b-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="d348b-159">Führen Sie das Cmdlet "Set-UnifiedGroup" aus, um eine E-Mail-Info zur Gruppe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="d348b-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="d348b-160">Neben einer E-Mail-Info können Sie auch "MailTipTranslations" festlegen, wodurch zusätzliche Sprachen für die E-Mail-Info festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d348b-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="d348b-161">Angenommen Sie, Sie möchten die spanische Übersetzung verwenden, dann führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d348b-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="d348b-162">Ändern des Anzeigenamens der Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="d348b-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="d348b-163">Der Anzeigename gibt den Namen der Microsoft 365-Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="d348b-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="d348b-164">Sie können diesen Namen in Ihrem Exchange Admin Center oder Microsoft 365 Admin Center sehen.</span><span class="sxs-lookup"><span data-stu-id="d348b-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="d348b-165">Sie können den Anzeigenamen der Gruppe bearbeiten oder einer vorhandenen Microsoft 365-Gruppe einen Anzeigenamen zuweisen, indem Sie den Befehl "Gruppe-Unifiedgroup" ausführen:</span><span class="sxs-lookup"><span data-stu-id="d348b-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="d348b-166">Ändern der Standardeinstellung von Microsoft 365-Gruppen für Outlook in "öffentlich" oder "Privat"</span><span class="sxs-lookup"><span data-stu-id="d348b-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="d348b-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d348b-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d348b-168">Microsoft 365-Gruppen in Outlook werden standardmäßig als privat erstellt.</span><span class="sxs-lookup"><span data-stu-id="d348b-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="d348b-169">Wenn Ihre Organisation Microsoft 365-Gruppen standardmäßig als Public (oder Back to private) erstellen möchte, verwenden Sie diese PowerShell-Cmdlet-Syntax:</span><span class="sxs-lookup"><span data-stu-id="d348b-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="d348b-170">So legen Sie die Einstellung auf "Privat" fest:</span><span class="sxs-lookup"><span data-stu-id="d348b-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="d348b-171">So überprüfen Sie die Einstellung:</span><span class="sxs-lookup"><span data-stu-id="d348b-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="d348b-172">Weitere Informationen hierzu finden Sie unter [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) und [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span><span class="sxs-lookup"><span data-stu-id="d348b-172">To learn more, see [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="d348b-173">Microsoft 365 Groups-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d348b-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="d348b-174">Die folgenden Cmdlets können mit Microsoft 365-Gruppen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d348b-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="d348b-175">**Name des Cmdlets**</span><span class="sxs-lookup"><span data-stu-id="d348b-175">**Cmdlet name**</span></span>|<span data-ttu-id="d348b-176">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d348b-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d348b-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="d348b-177">Get-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |<span data-ttu-id="d348b-178">Verwenden Sie dieses Cmdlet, um nach vorhandenen Microsoft 365-Gruppen zu suchen und um die Eigenschaften des Group-Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d348b-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="d348b-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="d348b-179">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |<span data-ttu-id="d348b-180">Aktualisieren der Eigenschaften einer bestimmten Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="d348b-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d348b-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="d348b-181">New-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |<span data-ttu-id="d348b-182">Erstellen Sie eine neue Microsoft 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="d348b-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="d348b-183">Dieses Cmdlet stellt einen minimalen Satz von Parametern bereit.</span><span class="sxs-lookup"><span data-stu-id="d348b-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="d348b-184">Um Werte für erweiterte Eigenschaften festzulegen, verwenden Sie nach dem Erstellen der neuen Gruppe "-Unifiedgroup".</span><span class="sxs-lookup"><span data-stu-id="d348b-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="d348b-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="d348b-185">Remove-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |<span data-ttu-id="d348b-186">Löschen einer vorhandenen Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="d348b-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d348b-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="d348b-187">Get-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |<span data-ttu-id="d348b-188">Abrufen von Mitgliedschafts-und Besitzerinformationen für eine Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="d348b-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d348b-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="d348b-189">Add-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |<span data-ttu-id="d348b-190">Hinzufügen von Hunderten oder Tausenden von Benutzern oder neuen Besitzern zu einer vorhandenen Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="d348b-190">Add hundreds or thousands of users, or new owners, to an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d348b-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="d348b-191">Remove-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |<span data-ttu-id="d348b-192">Entfernen von Besitzern und Mitgliedern aus einer vorhandenen Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="d348b-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d348b-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="d348b-193">Get-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |<span data-ttu-id="d348b-194">Wird verwendet, um Informationen zu dem Benutzerfoto abzurufen, das mit einem Konto verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="d348b-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="d348b-195">Benutzerfotos werden in Active Directory gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d348b-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="d348b-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="d348b-196">Set-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |<span data-ttu-id="d348b-197">Wird verwendet, um ein Benutzerfoto mit einem Konto zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="d348b-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="d348b-198">Benutzerfotos werden in Active Directory gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d348b-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="d348b-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="d348b-199">Remove-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |<span data-ttu-id="d348b-200">Entfernen des Fotos für eine Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="d348b-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="d348b-201">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d348b-201">Related topics</span></span>

[<span data-ttu-id="d348b-202">Aktualisieren von Verteilerlisten auf Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="d348b-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="d348b-203">Verwalten von Personen, die Microsoft 365-Gruppen erstellen können</span><span class="sxs-lookup"><span data-stu-id="d348b-203">Manage who can create Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="d348b-204">Verwalten des Gastzugriffs auf Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="d348b-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="d348b-205">Ändern der statischen Gruppenmitgliedschaft in „Dynamisch“</span><span class="sxs-lookup"><span data-stu-id="d348b-205">Change static group membership to dynamic in</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
