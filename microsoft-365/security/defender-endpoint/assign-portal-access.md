---
title: Zuweisen von Benutzerzugriff auf Microsoft Defender Security Center
description: Weisen Sie dem Microsoft Defender for Endpoint-Portal Lese-, Schreib- oder schreibgeschützten Zugriff zu.
keywords: Zuweisen von Benutzerrollen, Zuweisen von Lese- und Schreibzugriff, Zuweisen von schreibgeschützten Zugriffen, Benutzern, Benutzerrollen, Rollen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164763"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a><span data-ttu-id="80fbf-104">Zuweisen von Benutzerzugriff auf Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="80fbf-104">Assign user access to Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="80fbf-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="80fbf-105">**Applies to:**</span></span>
- <span data-ttu-id="80fbf-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="80fbf-106">Azure Active Directory</span></span>
- <span data-ttu-id="80fbf-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="80fbf-107">Office 365</span></span>
- [<span data-ttu-id="80fbf-108">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="80fbf-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="80fbf-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80fbf-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="80fbf-110">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="80fbf-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="80fbf-111">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="80fbf-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="80fbf-112">Defender for Endpoint unterstützt zwei Möglichkeiten zum Verwalten von Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="80fbf-112">Defender for Endpoint supports two ways to manage permissions:</span></span>

- <span data-ttu-id="80fbf-113">**Grundlegende Berechtigungsverwaltung:** Legen Sie Berechtigungen auf Vollzugriff oder schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="80fbf-113">**Basic permissions management**: Set permissions to either full access or read-only.</span></span>
- <span data-ttu-id="80fbf-114">**Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC):** Legen Sie präzise Berechtigungen durch Definieren von Rollen, Zuweisen von Azure AD-Benutzergruppen zu den Rollen und Gewähren von Benutzergruppenzugriff auf Gerätegruppen.</span><span class="sxs-lookup"><span data-stu-id="80fbf-114">**Role-based access control (RBAC)**: Set granular permissions by defining roles, assigning Azure AD user groups to the roles, and granting the user groups access to device groups.</span></span> <span data-ttu-id="80fbf-115">Weitere Informationen zur RBAC finden Sie unter [Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="80fbf-115">For more information on RBAC, see [Manage portal access using role-based access control](rbac.md).</span></span>

> [!NOTE]
> <span data-ttu-id="80fbf-116">Wenn Sie bereits grundlegende Berechtigungen zugewiesen haben, können Sie jederzeit zu RBAC wechseln.</span><span class="sxs-lookup"><span data-stu-id="80fbf-116">If you have already assigned basic permissions, you may switch to RBAC anytime.</span></span> <span data-ttu-id="80fbf-117">Berücksichtigen Sie Folgendes, bevor Sie die Option verwenden:</span><span class="sxs-lookup"><span data-stu-id="80fbf-117">Consider the following before making the switch:</span></span>
> 
> - <span data-ttu-id="80fbf-118">Benutzern mit Vollzugriff (Benutzern, denen die Verzeichnisrolle globaler Administrator oder Sicherheitsadministrator in Azure AD zugewiesen ist) wird automatisch die standardmäßige Defender for Endpoint-Administratorrolle zugewiesen, die ebenfalls Vollzugriff hat.</span><span class="sxs-lookup"><span data-stu-id="80fbf-118">Users with full access (users that are assigned the Global Administrator or Security Administrator directory role in Azure AD), are automatically assigned the default Defender for Endpoint administrator role, which also has full access.</span></span> <span data-ttu-id="80fbf-119">Zusätzliche Azure AD-Benutzergruppen können nach dem Wechsel zu RBAC der Administratorrolle Defender for Endpoint zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="80fbf-119">Additional Azure AD user groups can be assigned to the Defender for Endpoint administrator role after switching to RBAC.</span></span>  <span data-ttu-id="80fbf-120">Nur Benutzer, die der Administratorrolle Defender for Endpoint zugewiesen sind, können Berechtigungen mithilfe von RBAC verwalten.</span><span class="sxs-lookup"><span data-stu-id="80fbf-120">Only users assigned to the Defender for Endpoint administrator role can manage permissions using RBAC.</span></span> 
> - <span data-ttu-id="80fbf-121">Benutzer mit schreibgeschützten Zugriffen (Sicherheitsleser) verlieren den Zugriff auf das Portal, bis ihnen eine Rolle zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="80fbf-121">Users that have read-only access (Security Readers) will lose access to the portal until they are assigned a role.</span></span> <span data-ttu-id="80fbf-122">Beachten Sie, dass nur Azure AD-Benutzergruppen eine Rolle unter RBAC zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="80fbf-122">Note that only Azure AD user groups can be assigned a role under RBAC.</span></span>
> - <span data-ttu-id="80fbf-123">Nach dem Wechsel zu RBAC können Sie nicht mehr auf die Verwendung der grundlegenden Berechtigungsverwaltung umschalten.</span><span class="sxs-lookup"><span data-stu-id="80fbf-123">After switching to RBAC, you will not be able to switch back to using basic permissions management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="80fbf-124">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="80fbf-124">Related topics</span></span>

- [<span data-ttu-id="80fbf-125">Verwenden von grundlegenden Berechtigungen für den Zugriff auf das Portal</span><span class="sxs-lookup"><span data-stu-id="80fbf-125">Use basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="80fbf-126">Verwalten des Portalzugriffs mithilfe des RBAC</span><span class="sxs-lookup"><span data-stu-id="80fbf-126">Manage portal access using RBAC</span></span>](rbac.md)
