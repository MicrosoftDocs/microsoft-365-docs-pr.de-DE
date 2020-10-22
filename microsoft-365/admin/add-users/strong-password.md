---
title: Deaktivieren strenger Kennwortanforderungen für Benutzer
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
description: In diesem Artikel erfahren Sie, wie Sie mithilfe von Windows PowerShell sichere Kennwortanforderungen für Ihre Benutzer festlegen können.
ms.openlocfilehash: f9a0b76d024cc18552657144e4ccf8de8a72f0d9
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655735"
---
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="7549d-103">Deaktivieren strenger Kennwortanforderungen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="7549d-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="7549d-104">In diesem Artikel wird erläutert, wie Sie strenge Kennwortanforderungen für Ihre Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7549d-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="7549d-105">Starke Kennwortanforderungen sind in Ihrer Microsoft 365 for Business-Organisation standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7549d-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="7549d-106">Ihre Organisation verfügt möglicherweise über Anforderungen zum Deaktivieren sicherer Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="7549d-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="7549d-107">Führen Sie die folgenden Schritte aus, um sichere Kennwortanforderungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7549d-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="7549d-108">Sie müssen diese Schritte mithilfe von PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="7549d-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7549d-109">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="7549d-109">Before you begin</span></span>

<span data-ttu-id="7549d-110">Dieser Artikel richtet sich an Personen, die die Kennwortrichtlinie für ein Unternehmen, eine Schule oder eine gemeinnützige Organisation verwalten.</span><span class="sxs-lookup"><span data-stu-id="7549d-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="7549d-111">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="7549d-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="7549d-112">Was ist ein Administratorkonto?</span><span class="sxs-lookup"><span data-stu-id="7549d-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="7549d-113">Sie müssen ein [globaler Administrator oder Kenn Wort Administrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="7549d-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="7549d-114">Sie müssen auch eine Verbindung mit Microsoft 365 mit PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="7549d-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="7549d-115">Festlegen sicherer Kennwörter</span><span class="sxs-lookup"><span data-stu-id="7549d-115">Set strong passwords</span></span>

1. <span data-ttu-id="7549d-116">Stellen [Sie eine Verbindung mit Microsoft 365 mit PowerShell her](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7549d-116">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="7549d-117">Mithilfe von PowerShell können Sie mit dem folgenden Befehl sichere Kennwortanforderungen für alle Benutzer deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="7549d-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="7549d-118">Das userPrincipalName muss sich im Internet-Format für die Anmeldedatei befinden, wobei dem Benutzernamen das @-Zeichen und ein Domänenname folgen.</span><span class="sxs-lookup"><span data-stu-id="7549d-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="7549d-119">Beispiel: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7549d-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="7549d-120">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="7549d-120">Related content</span></span>

[<span data-ttu-id="7549d-121">Herstellen einer Verbindung mit Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="7549d-121">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="7549d-122">Weitere Informationen zu PowerShell-MsolUser-Befehlen</span><span class="sxs-lookup"><span data-stu-id="7549d-122">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="7549d-123">Weitere Informationen zur Kennwortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="7549d-123">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)