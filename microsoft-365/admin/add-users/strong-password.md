---
title: Festlegen einer strengen Kennwortanforderung für Benutzer
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
ms.openlocfilehash: 1634e2f0de2cdd2cac5e1928adbef54457e50716
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626143"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="d4bcc-103">Festlegen einer strengen Kennwortanforderung für Benutzer</span><span class="sxs-lookup"><span data-stu-id="d4bcc-103">Set strong password requirement for users</span></span>

<span data-ttu-id="d4bcc-104">In diesem Artikel wird erklärt, wie Sie sichere Kennwortanforderungen für Ihre Benutzer festlegen.</span><span class="sxs-lookup"><span data-stu-id="d4bcc-104">This article explains how to set strong password requirements for your users.</span></span> <span data-ttu-id="d4bcc-105">Sie müssen diese Schritte mithilfe von PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="d4bcc-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d4bcc-106">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="d4bcc-106">Before you begin</span></span>

<span data-ttu-id="d4bcc-107">Dieser Artikel richtet sich an Personen, die die Kennwortrichtlinie für ein Unternehmen, eine Schule oder eine gemeinnützige Organisation verwalten.</span><span class="sxs-lookup"><span data-stu-id="d4bcc-107">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="d4bcc-108">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="d4bcc-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="d4bcc-109">[Was ist ein Administratorkonto?](../admin-overview/admin-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d4bcc-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> <span data-ttu-id="d4bcc-110">Sie müssen ein [globaler Administrator oder Kenn Wort Administrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d4bcc-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="d4bcc-111">Sie müssen auch eine Verbindung mit Microsoft 365 mit PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="d4bcc-111">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="d4bcc-112">Festlegen sicherer Kennwörter</span><span class="sxs-lookup"><span data-stu-id="d4bcc-112">Set strong passwords</span></span>

1. <span data-ttu-id="d4bcc-113">Stellen [Sie eine Verbindung mit Microsoft 365 mit PowerShell her](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d4bcc-113">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="d4bcc-114">Mithilfe von PowerShell können Sie mit dem folgenden Befehl sichere Kennwortanforderungen für alle Benutzer aktivieren:</span><span class="sxs-lookup"><span data-stu-id="d4bcc-114">Using PowerShell, you can turn on strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> <span data-ttu-id="d4bcc-115">Das userPrincipalName muss sich im Internet-Format für die Anmeldedatei befinden, wobei dem Benutzernamen das @-Zeichen und ein Domänenname folgen.</span><span class="sxs-lookup"><span data-stu-id="d4bcc-115">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="d4bcc-116">Beispiel: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d4bcc-116">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="d4bcc-117">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="d4bcc-117">Related content</span></span>

[<span data-ttu-id="d4bcc-118">Herstellen einer Verbindung mit Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4bcc-118">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="d4bcc-119">Weitere Informationen zu PowerShell-MsolUser-Befehlen</span><span class="sxs-lookup"><span data-stu-id="d4bcc-119">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="d4bcc-120">Weitere Informationen zur Kennwortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="d4bcc-120">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)