---
title: Verwalten des Zugriffs auf Microsoft 365 Defender-Daten im Microsoft 365 Security Center
description: Informationen zum Verwalten von Berechtigungen für Daten in Microsoft 365 Defender
keywords: Zugriff, Berechtigungen, MTP, Microsoft Threat Protection, M365, Sicherheit, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, Bereich, bereichsbezogen, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930138"
---
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="5cf3a-104">Verwalten des Zugriffs auf Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5cf3a-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5cf3a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5cf3a-105">**Applies to:**</span></span>
- <span data-ttu-id="5cf3a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5cf3a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5cf3a-107">Konten, denen die folgenden Azure Active Directory (AD)-Rollen zugewiesen sind, können auf Microsoft 365 -Defender-Funktionen und -Daten zugreifen:</span><span class="sxs-lookup"><span data-stu-id="5cf3a-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="5cf3a-108">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="5cf3a-108">Global administrator</span></span>
- <span data-ttu-id="5cf3a-109">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="5cf3a-109">Security administrator</span></span>
- <span data-ttu-id="5cf3a-110">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="5cf3a-110">Security Operator</span></span>
- <span data-ttu-id="5cf3a-111">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="5cf3a-111">Global Reader</span></span>
- <span data-ttu-id="5cf3a-112">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="5cf3a-112">Security Reader</span></span>

<span data-ttu-id="5cf3a-113">Zum Überprüfen von Konten mit diesen Rollen, siehe[Berechtigungen im Microsoft 365 Security Center](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="5cf3a-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="5cf3a-114">Zugriff auf Funktionen</span><span class="sxs-lookup"><span data-stu-id="5cf3a-114">Access to functionality</span></span>
<span data-ttu-id="5cf3a-115">Der Zugriff auf bestimmte Funktionen hängt von Ihrer [Azure AD-Rolle](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)ab.</span><span class="sxs-lookup"><span data-stu-id="5cf3a-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="5cf3a-116">Wenden Sie sich an einen globalen Administrator, wenn Sie Zugriff auf bestimmte Funktionen benötigen, für die Ihnen oder Ihrer Benutzergruppe eine neue Rolle zugewiesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="5cf3a-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="5cf3a-117">Genehmigen ausstehender automatischer Vorgänge</span><span class="sxs-lookup"><span data-stu-id="5cf3a-117">Approve pending automated tasks</span></span>
<span data-ttu-id="5cf3a-118">[Automatisierte Untersuchungen und Reaktionen](mtp-autoir-actions.md) können Maßnahmen an E-Mails, Weiterleitungsregeln, Dateien, Persistenzmechanismen und anderen Artefakten durchführen, die bei Untersuchungen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="5cf3a-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="5cf3a-119">Um ausstehende Aktionen, für die eine explizite Genehmigung erforderlich ist, genehmigen oder ablehnen zu können, müssen Ihnen in Microsoft 365 bestimmte Rollen zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="5cf3a-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="5cf3a-120">Weitere Informationen hierzu finden Sie unter [Info-Center-Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="5cf3a-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="5cf3a-121">Zugriff auf Daten</span><span class="sxs-lookup"><span data-stu-id="5cf3a-121">Access to data</span></span>
<span data-ttu-id="5cf3a-122">Der Zugriff auf Microsoft 365 -Defender-Daten kann mithilfe des Bereichs gesteuert werden, der Benutzergruppen in der rollenbasierten Zugriffssteuerung (RBAC) von Microsoft Defender for Endpoint zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="5cf3a-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="5cf3a-123">Wenn Ihr Zugriff nicht auf eine bestimmte Gruppe von Geräten im Defender for Endpoint begrenzt wurde, haben Sie Vollzugriff auf Daten in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5cf3a-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="5cf3a-124">Sobald Ihrem Konto jedoch bereichsbezogener Zugriff gewährt wurde, werden nur die Daten zu den Geräten in dem betreffenden Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5cf3a-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="5cf3a-125">Wenn Sie beispielsweise nur zu einer Benutzergruppe mit einer Microsoft Defender for Endpoint-Rolle gehören und dieser Benutzergruppe nur Zugriff auf Verkaufsgeräte gegeben wurde, werden nur Daten zu Verkaufsgeräten in Microsoft 365 Defender angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5cf3a-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="5cf3a-126">Weitere Informationen zu rbAC-Einstellungen in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5cf3a-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="5cf3a-127">Microsoft Cloud App Security-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="5cf3a-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="5cf3a-128">Während der Vorschau erzwingt Microsoft 365 Defender keine Zugriffssteuerungen basierend auf Cloud App Security-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="5cf3a-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="5cf3a-129">Der Zugriff auf Microsoft 365 Defender-Daten ist von diesen Einstellungen nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="5cf3a-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5cf3a-130">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5cf3a-130">Related topics</span></span>

- [<span data-ttu-id="5cf3a-131">Azure AD-Rollen</span><span class="sxs-lookup"><span data-stu-id="5cf3a-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="5cf3a-132">Microsoft Defender für Endpoint RBAC</span><span class="sxs-lookup"><span data-stu-id="5cf3a-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="5cf3a-133">Rollen in Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5cf3a-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
