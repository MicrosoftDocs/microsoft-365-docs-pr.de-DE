---
title: Verhindern, dass Gäste einer bestimmten Gruppe hinzugefügt werden
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Erfahren Sie, wie Sie verhindern, dass Gäste zu einer bestimmten Gruppe hinzugefügt werden
ms.openlocfilehash: 1db2055f3e546c05905dbf4c854333387112f06e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538927"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="b0944-103">Verhindern, dass Gäste zu einer bestimmten Gruppe oder Microsoft 365 hinzugefügt Microsoft Teams werden</span><span class="sxs-lookup"><span data-stu-id="b0944-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="b0944-104">Wenn Sie den Gastzugriff auf die meisten Gruppen und Teams zulassen möchten, aber über einiges verfügen möchten, an dem Sie den Gastzugriff verhindern möchten, können Sie den Gastzugriff für einzelne Gruppen und Teams blockieren.</span><span class="sxs-lookup"><span data-stu-id="b0944-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="b0944-105">(Das Blockieren des Gastzugriffs auf ein Team erfolgt durch Blockieren des Gastzugriffs auf die zugeordnete Gruppe.) Dadurch wird verhindert, dass neue Gäste hinzugefügt werden, gäste, die sich bereits in der Gruppe oder im Team befinden, werden jedoch nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="b0944-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="b0944-106">Wenn Sie Vertraulichkeitsbezeichnungen in Ihrer Organisation verwenden, wird empfohlen, sie zu verwenden, um den Gastzugriff pro Gruppe zu steuern.</span><span class="sxs-lookup"><span data-stu-id="b0944-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="b0944-107">Informationen dazu finden Sie unter Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von [Inhalten in Microsoft Teams,](../compliance/sensitivity-labels-teams-groups-sites.md)Microsoft 365 gruppen und SharePoint Websites .</span><span class="sxs-lookup"><span data-stu-id="b0944-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span> <span data-ttu-id="b0944-108">Dies ist der empfohlene Ansatz.</span><span class="sxs-lookup"><span data-stu-id="b0944-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="b0944-109">Ändern von Gruppeneinstellungen mithilfe von Microsoft PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0944-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="b0944-110">Sie können auch verhindern, dass neue Gäste zu einzelnen Gruppen mit PowerShell hinzu kommen.</span><span class="sxs-lookup"><span data-stu-id="b0944-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="b0944-111">(Denken Sie daran, dass die dem Team zugeordnete SharePoint über [separate Gastfreigabesteuerelemente verfügt.)](/sharepoint/change-external-sharing-site)</span><span class="sxs-lookup"><span data-stu-id="b0944-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="b0944-112">Sie müssen die Vorschauversion von [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2) (Modulname **AzureADPreview**) verwenden, um die Gastzugriffseinstellung auf Gruppenebene zu ändern:</span><span class="sxs-lookup"><span data-stu-id="b0944-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="b0944-113">Wenn Sie zuvor noch keine Version des Azure AD PowerShell-Moduls installiert haben, lesen Sie [Installieren des Azure AD-Moduls](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview), und folgen Sie den Anweisungen zum Installieren der öffentlichen Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="b0944-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="b0944-114">Wenn Sie die allgemein verfügbare Version 2.0 des Azure AD PowerShell-Moduls (AzureAD) installiert haben, müssen Sie sie deinstallieren, indem Sie `Uninstall-Module AzureAD` in ihrer PowerShell-Sitzung ausführen, und dann mit `Install-Module AzureADPreview` die Vorschauversion installieren.</span><span class="sxs-lookup"><span data-stu-id="b0944-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="b0944-115">Wenn Sie die Vorschauversion bereits installiert haben, führen Sie `Install-Module AzureADPreview` aus, um sicherzustellen, dass es sich um die neueste Version dieses Moduls handelt.</span><span class="sxs-lookup"><span data-stu-id="b0944-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="b0944-116">Sie müssen über globale Administratorrechte verfügen, um diese Befehle ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="b0944-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="b0944-117">Führen Sie das folgende Skript aus und ändern Sie */<GroupName/>* auf den Namen der Gruppe, für den Sie Gastzugriff sperren möchten.</span><span class="sxs-lookup"><span data-stu-id="b0944-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="b0944-118">Zum Überprüfen Ihrer Einstellungen führen Sie diesen Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b0944-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="b0944-119">Die Überprüfung sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b0944-119">The verification looks like this:</span></span>
    
![Screenshot des PowerShell-Fensters, das anzeigt, dass der Gastgruppenzugriff auf falsch festgelegt wurde.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="b0944-121">Zulassen oder Blockieren des Gastzugriffs basierend auf der Domäne</span><span class="sxs-lookup"><span data-stu-id="b0944-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="b0944-122">Sie können Gäste zulassen oder blockieren, die eine bestimmte Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0944-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="b0944-123">Nehmen wir z. B. an, dass Ihr Unternehmen (Contoso) über eine Partnerschaft mit einem anderen Unternehmen (Fabrikam) verfügt. Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, damit Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="b0944-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="b0944-124">Weitere Informationen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="b0944-124">For more information, see [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="b0944-125">Hinzufügen von Gästen zur globalen Adressliste</span><span class="sxs-lookup"><span data-stu-id="b0944-125">Add guests to the global address list</span></span>

<span data-ttu-id="b0944-126">Standardmäßig sind Gastbenutzer in der globalen Adressliste von Exchange nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="b0944-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="b0944-127">Führen Sie die nachstehenden Schritte aus, um einen Gast in der globalen Adressliste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b0944-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="b0944-128">Suchen Sie die ObjectID des Gasts, indem Sie:</span><span class="sxs-lookup"><span data-stu-id="b0944-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="b0944-129">Führen Sie dann die folgenden Aktionen mit den entsprechenden Werten für Objekt-ID, Vorname, Nachname, Anzeigename und Telefonnummer aus.</span><span class="sxs-lookup"><span data-stu-id="b0944-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="b0944-130">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b0944-130">Related topics</span></span>

[<span data-ttu-id="b0944-131">Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="b0944-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="b0944-132">Erstellen eines Plans für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="b0944-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="b0944-133">Verwalten von Gruppenmitgliedschaften im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="b0944-133">Manage Group membership in the Microsoft 365 admin center</span></span>](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="b0944-134">Azure Active Directory Domain Services-Zugriffsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="b0944-134">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="b0944-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="b0944-135">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)