---
title: Verwalten des Zugriffs auf Microsoft Threat Protection-Daten im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Berechtigungen für Daten in Microsoft Threat Protection verwalten
keywords: Zugriff, Berechtigungen, MTP, Microsoft Threat Protection, M365, Sicherheit, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, Bereich, bereichsbezogen, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f747737fc94241ca5f65ad9881715f517d5fbe3c
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773839"
---
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="cdc84-104">Verwalten des Zugriffs auf Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cdc84-104">Manage access to Microsoft Threat Protection</span></span>

<span data-ttu-id="cdc84-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cdc84-105">**Applies to:**</span></span>
- <span data-ttu-id="cdc84-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cdc84-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="cdc84-107">Konten, denen die folgenden Azure Active Directory (AD)-Rollen zugewiesen sind, können auf Microsoft Threat Protection-Funktionen und -Daten zugreifen:</span><span class="sxs-lookup"><span data-stu-id="cdc84-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="cdc84-108">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="cdc84-108">Global administrator</span></span>
- <span data-ttu-id="cdc84-109">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="cdc84-109">Security administrator</span></span>
- <span data-ttu-id="cdc84-110">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="cdc84-110">Security Operator</span></span>
- <span data-ttu-id="cdc84-111">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="cdc84-111">Global Reader</span></span>
- <span data-ttu-id="cdc84-112">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="cdc84-112">Security Reader</span></span>

<span data-ttu-id="cdc84-113">Zum Überprüfen von Konten mit diesen Rollen, siehe[Berechtigungen im Microsoft 365 Security Center](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="cdc84-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="cdc84-114">Zugriff auf Funktionen</span><span class="sxs-lookup"><span data-stu-id="cdc84-114">Access to functionality</span></span>
<span data-ttu-id="cdc84-115">Der Zugriff auf bestimmte Funktionen hängt von Ihrer [Azure AD-Rolle](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)ab.</span><span class="sxs-lookup"><span data-stu-id="cdc84-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="cdc84-116">Wenden Sie sich an einen globalen Administrator, wenn Sie Zugriff auf bestimmte Funktionen benötigen, für die Ihnen oder Ihrer Benutzergruppe eine neue Rolle zugewiesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="cdc84-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="cdc84-117">Genehmigen ausstehender automatischer Vorgänge</span><span class="sxs-lookup"><span data-stu-id="cdc84-117">Approve pending automated tasks</span></span>
<span data-ttu-id="cdc84-118">[Automatisierte Untersuchungen und Reaktionen](mtp-autoir-actions.md) können Maßnahmen an E-Mails, Weiterleitungsregeln, Dateien, Persistenzmechanismen und anderen Artefakten durchführen, die bei Untersuchungen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="cdc84-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="cdc84-119">Um ausstehende Aktionen, für die eine explizite Genehmigung erforderlich ist, genehmigen oder ablehnen zu können, müssen Ihnen in Microsoft 365 bestimmte Rollen zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="cdc84-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="cdc84-120">Weitere Informationen hierzu finden Sie unter [Info-Center-Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="cdc84-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="cdc84-121">Zugriff auf Daten</span><span class="sxs-lookup"><span data-stu-id="cdc84-121">Access to data</span></span>
<span data-ttu-id="cdc84-122">Der Zugriff auf Microsoft Threat Protection-Daten kann über den Bereich gesteuert werden, der Benutzergruppen in der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) von Microsoft Defender ATP zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="cdc84-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="cdc84-123">Wenn Ihr Zugriff in Microsoft Defender ATP nicht auf eine bestimmte Gruppe von Geräten eingeschränkt wurde, haben Sie Vollzugriff auf die Daten in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="cdc84-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="cdc84-124">Sobald Ihrem Konto jedoch bereichsbezogener Zugriff gewährt wurde, werden nur die Daten zu den Geräten in dem betreffenden Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cdc84-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="cdc84-125">Wenn Sie beispielsweise nur einer Benutzergruppe mit einer Microsoft Defender ATP-Rolle angehören und dieser Benutzergruppe nur der Zugriff auf Verkaufsgeräte gewährt wurde, werden Ihnen in Microsoft Threat Protection nur Daten zu Verkaufsgeräten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cdc84-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> <span data-ttu-id="cdc84-126">Weitere Informationen hierzu finden Sie unter [RBAC-Einstellungen in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac).</span><span class="sxs-lookup"><span data-stu-id="cdc84-126">[Learn more about RBAC settings in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)</span></span>

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="cdc84-127">Microsoft Cloud App Security-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="cdc84-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="cdc84-128">Während der Vorschau erzwingt Microsoft Threat Protection keine auf den Sicherheitseinstellungen in Cloud App Security basierende Zugriffssteuerung.</span><span class="sxs-lookup"><span data-stu-id="cdc84-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="cdc84-129">Diese Einstellungen wirken sich nicht auf den Zugriff auf Microsoft Threat Protection-Daten aus.</span><span class="sxs-lookup"><span data-stu-id="cdc84-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cdc84-130">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cdc84-130">Related topics</span></span>

- [<span data-ttu-id="cdc84-131">Azure AD-Rollen</span><span class="sxs-lookup"><span data-stu-id="cdc84-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="cdc84-132">Rollenbasierte Zugriffssteuerung in Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="cdc84-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="cdc84-133">Rollen in Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cdc84-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
