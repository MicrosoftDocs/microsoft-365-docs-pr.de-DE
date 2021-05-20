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
description: Erfahren Sie, wie Sie Gäste zu einer Microsoft 365 Gruppe hinzufügen, Gastbenutzer anzeigen und PowerShell verwenden, um den Gastzugriff zu steuern.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571937"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="dc4dd-103">Verwalten des Gastzugriffs in Microsoft 365 Gruppen</span><span class="sxs-lookup"><span data-stu-id="dc4dd-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="dc4dd-104">Standardmäßig ist der Gastzugriff für Microsoft 365 Gruppen für Ihre Organisation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="dc4dd-105">Administratoren können steuern, ob sie den Gastzugriff für die ganze Organisation oder für einzelne Gruppen zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="dc4dd-106">Wenn diese Aktiviert ist, können Gruppenmitglieder Gastbenutzer über Outlook im Web zu einer Microsoft 365 Gruppe einladen.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="dc4dd-107">Einladungen werden zur Genehmigung an den Gruppenbesitzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="dc4dd-108">Nach der Genehmigung wird der Gastbenutzer dem Verzeichnis und der Gruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="dc4dd-109">Yammer Enterprise-Netzwerke, die sich im nativen Modus oder im [EU-Gebiet](/yammer/manage-security-and-compliance/manage-data-compliance) befinden, unterstützen keine Netzwerkgäste.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="dc4dd-110">Microsoft 365 Verbundene Yammer Gruppen unterstützen derzeit keinen Gastzugriff, sie können jedoch nicht verbundene externe Gruppen in Ihrem Yammer Netzwerk erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="dc4dd-111">Entsprechende Anleitungen finden Sie unter [Erstellen und Verwalten von externen Gruppen in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups).</span><span class="sxs-lookup"><span data-stu-id="dc4dd-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="dc4dd-112">Der Gastzugriff in Gruppen wird häufig als Teil eines breiter gefächerten Szenarios verwendet, das SharePoint oder Teams umfasst.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="dc4dd-113">Diese Dienste besitzen ihre eigenen Einstellungen für die Gastfreigabe.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="dc4dd-114">Umfassende Anweisungen zum Einrichten der gemeinsamen Nutzung über Gruppen, SharePoint und Teams hinweg finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="dc4dd-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="dc4dd-115">Zusammenarbeit mit Gästen in einer Website</span><span class="sxs-lookup"><span data-stu-id="dc4dd-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="dc4dd-116">Zusammenarbeit mit Gästen in einem Team</span><span class="sxs-lookup"><span data-stu-id="dc4dd-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="dc4dd-117">Verwalten des Gastzugriffs von Gruppen</span><span class="sxs-lookup"><span data-stu-id="dc4dd-117">Manage groups guest access</span></span>

<span data-ttu-id="dc4dd-118">Wenn Sie den Gastzugriff in Gruppen aktivieren oder deaktivieren möchten, können Sie dies im Microsoft 365 Admin Center tun.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="dc4dd-119">Wechseln Sie im Admin Center zu Alle Einstellungen Organisationseinstellungen **anzeigen,** \>  \>  und wählen Sie auf der Registerkarte **Dienste** **Microsoft 365 Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="dc4dd-120">Wählen Sie auf der Seite **Microsoft 365 Gruppen** aus, ob Sie Personen außerhalb Ihrer Organisation den Zugriff auf Gruppenressourcen gewähren oder Gruppenbesitzer Personen außerhalb Ihrer Organisation zu Gruppen hinzufügen lassen möchten.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="dc4dd-121">Hinzufügen von Gästen zu einer Microsoft 365 Gruppe aus dem Admin Center</span><span class="sxs-lookup"><span data-stu-id="dc4dd-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="dc4dd-122">Wenn der Gast bereits in Ihrem Verzeichnis vorhanden ist, können Sie ihn über das Microsoft 365 Admin Center zu Ihren Gruppen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="dc4dd-123">(Gruppen mit dynamischer Mitgliedschaft müssen [in Azure Active Directory verwaltet](/azure/active-directory/enterprise-users/groups-create-rule)werden.)</span><span class="sxs-lookup"><span data-stu-id="dc4dd-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="dc4dd-124">Wechseln Sie im Admin Center zur Seite **Gruppen** > **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="dc4dd-125">Klicken Sie auf die Gruppe, der Sie den Gast hinzufügen möchten, und wählen Sie **alle Anzeigen und Verwalten** von Mitgliedern auf der Registerkarte **Mitglieder** aus.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="dc4dd-126">Wählen Sie **Mitglieder hinzufügen** und dann den Namen der Person, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="dc4dd-127">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dc4dd-127">Select **Save**.</span></span>

<span data-ttu-id="dc4dd-128">Wenn Sie einen Gast direkt zum Verzeichnis hinzufügen möchten, können Sie [Benutzer der Azure Active Directory-B2B-Zusammenarbeit im Azure-Portal hinzufügen](/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="dc4dd-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="dc4dd-129">Wenn Sie die Informationen eines Gastes bearbeiten möchten, können Sie die [Profilinformationen eines Benutzers mithilfe von Azure Active Directory hinzufügen oder aktualisieren](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="dc4dd-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="dc4dd-130">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="dc4dd-130">Related content</span></span>

<span data-ttu-id="dc4dd-131">[Blockieren von Gastbenutzern aus einer bestimmten Gruppe](../../solutions/per-group-guest-access.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="dc4dd-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>

<span data-ttu-id="dc4dd-132">[Verwalten der Gruppenmitgliedschaft im Microsoft 365 Admin Center](add-or-remove-members-from-groups.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="dc4dd-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>
  
<span data-ttu-id="dc4dd-133">[Azure Active Directory-Zugriff auf Rezensionen](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="dc4dd-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>

<span data-ttu-id="dc4dd-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="dc4dd-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>