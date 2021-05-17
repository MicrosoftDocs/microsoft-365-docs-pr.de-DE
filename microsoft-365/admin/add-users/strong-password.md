---
title: Deaktivieren starker Kennwortanforderungen für Benutzer
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie starke Kennwortanforderungen für Ihre Benutzer mithilfe von Windows PowerShell.
ms.openlocfilehash: de2f47bb88fe4cb3d00e45698fe006035faa4e5c
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222073"
---
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="e5ddb-103">Deaktivieren starker Kennwortanforderungen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="e5ddb-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="e5ddb-104">In diesem Artikel wird erläutert, wie Sie starke Kennwortanforderungen für Ihre Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="e5ddb-105">Starke Kennwortanforderungen sind standardmäßig in Ihrer Microsoft 365 Business Organization aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="e5ddb-106">Ihre Organisation muss möglicherweise sichere Kennwörter deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="e5ddb-107">Führen Sie die folgenden Schritte aus, um starke Kennwortanforderungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="e5ddb-108">Sie müssen diese Schritte mithilfe von PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e5ddb-109">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="e5ddb-109">Before you begin</span></span>

<span data-ttu-id="e5ddb-110">Dieser Artikel ist für Personen, die die Kennwortrichtlinie für ein Unternehmen, eine Schule oder gemeinnützige Organisation verwalten.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="e5ddb-111">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="e5ddb-112">Was ist ein Administratorkonto?</span><span class="sxs-lookup"><span data-stu-id="e5ddb-112">What's an admin account?</span></span>](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview) <span data-ttu-id="e5ddb-113">Sie müssen ein globaler [Administrator oder Kennwortadministrator sein,](about-admin-roles.md) um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="e5ddb-114">Sie müssen auch eine Verbindung mit Microsoft 365 PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="e5ddb-115">Festlegen von starken Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="e5ddb-115">Set strong passwords</span></span>

1. <span data-ttu-id="e5ddb-116">[Verbinden sie Microsoft 365 PowerShell .](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="e5ddb-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="e5ddb-117">Mit PowerShell können Sie starke Kennwortanforderungen für alle Benutzer mit dem folgenden Befehl deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="e5ddb-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="e5ddb-118">Der userPrincipalName muss im Anmeldeformat im Internetformat vorliegen, in dem auf den Benutzernamen das At-Zeichen (@) und ein Domänenname folgen.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="e5ddb-119">Beispiel: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="e5ddb-120">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="e5ddb-120">Related content</span></span>

[<span data-ttu-id="e5ddb-121">Herstellen einer Verbindung mit Microsoft 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5ddb-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="e5ddb-122">Weitere Informationen zu PowerShell-MsolUser-Befehlen</span><span class="sxs-lookup"><span data-stu-id="e5ddb-122">More information on PowerShell MsolUser commands</span></span>](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="e5ddb-123">Weitere Informationen zur Kennwortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e5ddb-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)