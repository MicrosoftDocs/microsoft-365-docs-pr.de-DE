---
title: Deaktivieren der Anforderungen für sichere Kennwörter für Benutzer
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
description: Erfahren Sie, wie Sie mithilfe von Windows PowerShell sichere Kennwortanforderungen für Ihre Benutzer festlegen.
ms.openlocfilehash: 87ba9e0323c379d8c2589dbb82c38c531dd9d047
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286267"
---
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="a312d-103">Deaktivieren der Anforderungen für sichere Kennwörter für Benutzer</span><span class="sxs-lookup"><span data-stu-id="a312d-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="a312d-104">In diesem Artikel wird erläutert, wie Sie sichere Kennwortanforderungen für Ihre Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a312d-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="a312d-105">Sichere Kennwortanforderungen sind in Ihrer Microsoft 365 für Unternehmen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a312d-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="a312d-106">Ihre Organisation hat möglicherweise Anforderungen, um sichere Kennwörter zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a312d-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="a312d-107">Führen Sie die folgenden Schritte aus, um sichere Kennwortanforderungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a312d-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="a312d-108">Sie müssen diese Schritte mithilfe von PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="a312d-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a312d-109">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="a312d-109">Before you begin</span></span>

<span data-ttu-id="a312d-110">Dieser Artikel richtet sich an Personen, die die Kennwortrichtlinie für ein Unternehmen, eine Schule oder eine gemeinnützige Organisation verwalten.</span><span class="sxs-lookup"><span data-stu-id="a312d-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="a312d-111">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="a312d-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="a312d-112">Was ist ein Administratorkonto?</span><span class="sxs-lookup"><span data-stu-id="a312d-112">What's an admin account?</span></span>](/microsoft-365/business-video/admin-center-overview) <span data-ttu-id="a312d-113">Sie müssen ein [globaler Administrator oder Kennwortadministrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="a312d-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="a312d-114">Sie müssen auch eine Verbindung mit Microsoft 365 mit PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="a312d-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="a312d-115">Festlegen sicherer Kennwörter</span><span class="sxs-lookup"><span data-stu-id="a312d-115">Set strong passwords</span></span>

1. <span data-ttu-id="a312d-116">[Verbinden mit PowerShell zum Microsoft 365.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="a312d-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="a312d-117">Mithilfe von PowerShell können Sie die Anforderungen für sichere Kennwörter für alle Benutzer mit dem folgenden Befehl deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="a312d-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="a312d-118">"userPrincipalName" muss im Anmeldeformat im Internetformat vorliegen, auf das der Benutzername folgt, gefolgt von "at sign" (@) und einem Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="a312d-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="a312d-119">Beispiel: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a312d-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="a312d-120">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="a312d-120">Related content</span></span>

[<span data-ttu-id="a312d-121">Herstellen einer Verbindung mit Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a312d-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="a312d-122">Weitere Informationen zu PowerShell-MsolUser-Befehlen</span><span class="sxs-lookup"><span data-stu-id="a312d-122">More information on PowerShell MsolUser commands</span></span>](/powershell/azure/active-directory/install-adv2)

[<span data-ttu-id="a312d-123">Weitere Informationen zur Kennwortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="a312d-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
