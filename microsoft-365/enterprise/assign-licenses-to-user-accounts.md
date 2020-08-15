---
title: Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Beschreibt, wie Sie Benutzerkonten Microsoft 365-Lizenzen einzeln oder basierend auf einer Gruppenmitgliedschaft zuweisen.
ms.openlocfilehash: 60936e52bffa58d50419f771e670848ee76271fd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690331"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="1aa1e-103">Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="1aa1e-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="1aa1e-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1aa1e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1aa1e-105">Für das nur-Cloud-Identitätsmodell können Sie Microsoft 365-Lizenzen den Benutzerkonten zuweisen, je nachdem, wie Sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="1aa1e-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="1aa1e-106">Wenn Active Directory-Domänendienste (AD DS) Benutzerkonten zum ersten Mal synchronisiert werden, wird für das hybride Identitätsmodell nicht automatisch eine Microsoft 365-Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1aa1e-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license.</span></span> <span data-ttu-id="1aa1e-107">Sie müssen zunächst jedes Benutzerkonto mit einem Benutzer Speicherort konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1aa1e-107">You must first configure each user account with a user location.</span></span>

<span data-ttu-id="1aa1e-108">In beiden Fällen müssen Sie Benutzerkonten eine Lizenz zuweisen, damit Ihre Benutzer auf Microsoft 365-Dienste wie e-Mail und Microsoft Teams zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1aa1e-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="1aa1e-109">Sie können Benutzerkonten entweder einzeln oder automatisch über die Gruppenmitgliedschaft Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1aa1e-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="1aa1e-110">Wenn Sie Microsoft 365-Lizenzen einzelnen Benutzerkonten zuweisen möchten, können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="1aa1e-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="1aa1e-111">Das Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="1aa1e-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="1aa1e-112">PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1aa1e-112">PowerShell for Microsoft 365</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

<span data-ttu-id="1aa1e-113">Informationen zur automatischen Zuweisung von Lizenzen finden Sie unter [Group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="1aa1e-113">For automatic license assignment, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1aa1e-114">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1aa1e-114">Next steps</span></span>

<span data-ttu-id="1aa1e-115">Mit dem vollständigen Benutzer kontensatz, dem Lizenzen zugewiesen wurden, können Sie nun folgende Aufgaben durchsetzen:</span><span class="sxs-lookup"><span data-stu-id="1aa1e-115">With the full set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="1aa1e-116">Implementieren der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1aa1e-116">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="1aa1e-117">Bereitstellen von Client Software wie Microsoft 365-apps</span><span class="sxs-lookup"><span data-stu-id="1aa1e-117">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="1aa1e-118">Einrichten der Verwaltung mobiler Geräte in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1aa1e-118">Set up Mobile Device Management in Microsoft 365</span></span>](https://support.office.com/article/set-up-mobile-device-management-mdm-in-office-365-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [<span data-ttu-id="1aa1e-119">Konfigurieren von Diensten und Anwendungen</span><span class="sxs-lookup"><span data-stu-id="1aa1e-119">Configure services and applications</span></span>](configure-services-and-applications.md)
