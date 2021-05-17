---
title: Verwalten des Gastzugriffs in Microsoft 365 Gruppen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Erfahren Sie, wie Sie Gäste zu einer Microsoft 365 hinzufügen, Gastbenutzer anzeigen und PowerShell verwenden, um den Gastzugriff zu steuern.
ms.openlocfilehash: 114fc1b5262f1632c7e7a8d1aa339c2470223288
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908606"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="32f6e-103">Verwalten des Gastzugriffs in Microsoft 365 Gruppen</span><span class="sxs-lookup"><span data-stu-id="32f6e-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="32f6e-104">Standardmäßig ist der Gastzugriff für Microsoft 365 für Ihre Organisation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="32f6e-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="32f6e-105">Administratoren können steuern, ob sie den Gastzugriff für die ganze Organisation oder für einzelne Gruppen zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="32f6e-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="32f6e-106">Wenn sie aktiviert ist, können Gruppenmitglieder Gastbenutzer über Microsoft 365 web Outlook einladen.</span><span class="sxs-lookup"><span data-stu-id="32f6e-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="32f6e-107">Einladungen werden zur Genehmigung an den Gruppenbesitzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="32f6e-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="32f6e-108">Nach der Genehmigung wird der Gastbenutzer dem Verzeichnis und der Gruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="32f6e-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="32f6e-109">Yammer Enterprise-Netzwerke, die sich im nativen Modus oder im [EU-Gebiet](/yammer/manage-security-and-compliance/manage-data-compliance) befinden, unterstützen keine Netzwerkgäste.</span><span class="sxs-lookup"><span data-stu-id="32f6e-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="32f6e-110">Microsoft 365 Verbundene Yammer unterstützen derzeit keinen Gastzugriff, Aber Sie können nicht verbundene externe Gruppen in Ihrem Yammer erstellen.</span><span class="sxs-lookup"><span data-stu-id="32f6e-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="32f6e-111">Entsprechende Anleitungen finden Sie unter [Erstellen und Verwalten von externen Gruppen in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups).</span><span class="sxs-lookup"><span data-stu-id="32f6e-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="32f6e-112">Der Gastzugriff in Gruppen wird häufig als Teil eines breiter gefächerten Szenarios verwendet, das SharePoint oder Teams umfasst.</span><span class="sxs-lookup"><span data-stu-id="32f6e-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="32f6e-113">Diese Dienste besitzen ihre eigenen Einstellungen für die Gastfreigabe.</span><span class="sxs-lookup"><span data-stu-id="32f6e-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="32f6e-114">Umfassende Anweisungen zum Einrichten der gemeinsamen Nutzung über Gruppen, SharePoint und Teams hinweg finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="32f6e-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="32f6e-115">Zusammenarbeit mit Gästen in einer Website</span><span class="sxs-lookup"><span data-stu-id="32f6e-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="32f6e-116">Zusammenarbeit mit Gästen in einem Team</span><span class="sxs-lookup"><span data-stu-id="32f6e-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="32f6e-117">Verwalten des Gastzugriffs von Gruppen</span><span class="sxs-lookup"><span data-stu-id="32f6e-117">Manage groups guest access</span></span>

<span data-ttu-id="32f6e-118">Wenn Sie den Gastzugriff in Gruppen aktivieren oder deaktivieren möchten, können Sie dies im Microsoft 365 Admin Center tun.</span><span class="sxs-lookup"><span data-stu-id="32f6e-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="32f6e-119">Wechseln Sie im Admin Center zu **Alle Organisationseinstellungen** Einstellungen anzeigen, und wählen Sie auf der Registerkarte Dienste die Option Microsoft 365 \>  \>  **aus.** </span><span class="sxs-lookup"><span data-stu-id="32f6e-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="32f6e-120">Wählen Sie **auf Microsoft 365** Seite Gruppen aus, ob Personen außerhalb Ihrer Organisation auf Gruppenressourcen zugreifen oder Gruppenbesitzer Personen außerhalb Ihrer Organisation zu Gruppen hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="32f6e-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="32f6e-121">Hinzufügen von Gästen zu Microsoft 365 aus dem Admin Center</span><span class="sxs-lookup"><span data-stu-id="32f6e-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="32f6e-122">Wenn der Gast bereits in Ihrem Verzeichnis vorhanden ist, können Sie ihn über das Microsoft 365 Admin Center zu Ihren Gruppen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="32f6e-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="32f6e-123">(Gruppen mit dynamischer Mitgliedschaft müssen [in einem Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule)verwaltet werden.)</span><span class="sxs-lookup"><span data-stu-id="32f6e-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="32f6e-124">Wechseln Sie im Admin Center zur Seite **Gruppen** > **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="32f6e-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="32f6e-125">Klicken Sie auf die Gruppe, der Sie den Gast hinzufügen möchten, und wählen Sie **auf** der Registerkarte Mitglieder alle anzeigen und **Mitglieder** verwalten aus.</span><span class="sxs-lookup"><span data-stu-id="32f6e-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="32f6e-126">Wählen Sie **Mitglieder hinzufügen** und dann den Namen der Person, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="32f6e-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="32f6e-127">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="32f6e-127">Select **Save**.</span></span>

<span data-ttu-id="32f6e-128">Wenn Sie einen Gast direkt zum Verzeichnis hinzufügen möchten, können Sie [Benutzer der Azure Active Directory-B2B-Zusammenarbeit im Azure-Portal hinzufügen](/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="32f6e-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="32f6e-129">Wenn Sie die Informationen eines Gastes bearbeiten möchten, können Sie die [Profilinformationen eines Benutzers mithilfe von Azure Active Directory hinzufügen oder aktualisieren](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="32f6e-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="32f6e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32f6e-130">See also</span></span>

[<span data-ttu-id="32f6e-131">Blockieren von Gastbenutzern aus einer bestimmten Gruppe</span><span class="sxs-lookup"><span data-stu-id="32f6e-131">Block guest users from a specific group</span></span>](../../solutions/per-group-guest-access.md)

[<span data-ttu-id="32f6e-132">Verwalten der Gruppenmitgliedschaft im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="32f6e-132">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="32f6e-133">Azure Active Directory Domain Services-Zugriffsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="32f6e-133">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="32f6e-134">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="32f6e-134">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)