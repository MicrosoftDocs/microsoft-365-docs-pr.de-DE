---
title: Zugreifen auf das Verwaltungsportal
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b6310849f27200adbbcbcb1584903011fbdf6145
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146267"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="b2b14-103">Zugreifen auf das Verwaltungsportal</span><span class="sxs-lookup"><span data-stu-id="b2b14-103">Access the admin portal</span></span>

<span data-ttu-id="b2b14-104">Ihr Gateway zum Microsoft Managed Desktop-Dienst ist das Microsoft [Azure-Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b2b14-104">Your gateway to the Microsoft Managed Desktop service is the Microsoft [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="b2b14-105">Weitere Informationen zum verwenden und Anpassen Ihrer Azure-Portal-Erfahrung im Allgemeinen finden Sie in der [Azure-Portal Dokumentation](https://docs.microsoft.com/azure/azure-portal/).</span><span class="sxs-lookup"><span data-stu-id="b2b14-105">For more about using and customizing your Azure portal experience generally, see the [Azure portal documentation](https://docs.microsoft.com/azure/azure-portal/).</span></span> 

<span data-ttu-id="b2b14-106">Ihr Administratorkonto benötigt bestimmte Berechtigungen, um auf das Verwaltungsportal von Microsoft Managed Desktop zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="b2b14-106">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="b2b14-107">Sie können den Administratorzugriff auf diese Features in Ihrer Organisation mithilfe der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) verwalten.</span><span class="sxs-lookup"><span data-stu-id="b2b14-107">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="b2b14-108">Weitere Informationen zu Azure Active Directory Rollen finden Sie unter [Administrator Role Permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="b2b14-108">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="b2b14-109">Weisen Sie Ihren Administrator-Benutzerkonten eine der folgenden Rollen zu, um den Zugriff sicherzustellen:</span><span class="sxs-lookup"><span data-stu-id="b2b14-109">Assign your admin user accounts any of the following roles to ensure access:</span></span>

|<span data-ttu-id="b2b14-110">Azure AD Rolle</span><span class="sxs-lookup"><span data-stu-id="b2b14-110">Azure AD role</span></span>  |<span data-ttu-id="b2b14-111">Berechtigungen für Microsoft Managed Desktops</span><span class="sxs-lookup"><span data-stu-id="b2b14-111">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="b2b14-112">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="b2b14-112">Global Administrator</span></span>     | <span data-ttu-id="b2b14-113">Administratoren mit dieser Rolle verfügen über **Lese-und Schreibberechtigungen** für alle Features im Verwaltungsportal von Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="b2b14-113">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="b2b14-114">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="b2b14-114">Global Reader</span></span>     | <span data-ttu-id="b2b14-115">Administratoren mit dieser Rolle verfügen über **schreibgeschützte Berechtigungen** für alle Features im Verwaltungsportal von Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="b2b14-115">Admins with this role will have **read-only permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="b2b14-116">InTune-Dienst Administrator</span><span class="sxs-lookup"><span data-stu-id="b2b14-116">Intune Service Administrator</span></span>     |  <span data-ttu-id="b2b14-117">Administratoren mit dieser Rolle verfügen über **Lese-und Schreibberechtigungen** für alle Features im Verwaltungsportal von Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="b2b14-117">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="b2b14-118">Dienst Support Administrator</span><span class="sxs-lookup"><span data-stu-id="b2b14-118">Service Support Administrator</span></span>     | <span data-ttu-id="b2b14-119">Administratoren mit dieser Rolle verfügen über **Lese-und Schreibberechtigungen** für alle Features im Verwaltungsportal von Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="b2b14-119">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="b2b14-120">Nur die globale Administrator Rolle verfügt über die erforderlichen Berechtigungen zum *registrieren* Ihrer Organisation in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="b2b14-120">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="b2b14-121">Achten Sie darauf, dass Azure Active Directory-Rollen Benutzerkontenberechtigungen für eine Vielzahl von Microsoft-Diensten erhalten.</span><span class="sxs-lookup"><span data-stu-id="b2b14-121">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="b2b14-122">Nachdem Sie die Registrierung bei Microsoft Managed Desktop abgeschlossen haben, sollten Sie die Rolle immer mit den am *wenigsten* erforderlichen Rechten verwenden, um Ihre anderen Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b2b14-122">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="b2b14-123">Zuweisen von Rollen zu Administratoren</span><span class="sxs-lookup"><span data-stu-id="b2b14-123">Assigning roles to administrators</span></span>

<span data-ttu-id="b2b14-124">Wenn Sie Hilfe beim Zuweisen von Azure Active Directory Rollen benötigen, finden Sie weitere Informationen unter [Administrator Rollen Berechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="b2b14-124">If you need help assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>
