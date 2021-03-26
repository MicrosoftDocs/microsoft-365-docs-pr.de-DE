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
ms.openlocfilehash: 3acec7b3edd60dca1befa5347cd39afa884a3c03
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222806"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="a6587-104">Verwalten des Zugriffs auf Microsoft 365 Defender mit globalen Azure Active Directory-Rollen</span><span class="sxs-lookup"><span data-stu-id="a6587-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a6587-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a6587-105">**Applies to:**</span></span>
- <span data-ttu-id="a6587-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6587-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a6587-107">Es gibt zwei Möglichkeiten zum Verwalten des Zugriffs auf Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6587-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="a6587-108">**Globale Azure Active Directory(Azure AD)-Rollen**</span><span class="sxs-lookup"><span data-stu-id="a6587-108">**Global Azure Active Directory (Azure AD) roles**</span></span>
- <span data-ttu-id="a6587-109">**Benutzerdefinierter Rollenzugriff**</span><span class="sxs-lookup"><span data-stu-id="a6587-109">**Custom role access**</span></span>

<span data-ttu-id="a6587-110">Konten, denen die folgenden **globalen Azure AD-Rollen zugewiesen sind,** können auf Microsoft 365 Defender-Funktionen und -Daten zugreifen:</span><span class="sxs-lookup"><span data-stu-id="a6587-110">Accounts assigned the following **Global Azure AD roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="a6587-111">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="a6587-111">Global administrator</span></span>
- <span data-ttu-id="a6587-112">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="a6587-112">Security administrator</span></span>
- <span data-ttu-id="a6587-113">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="a6587-113">Security Operator</span></span>
- <span data-ttu-id="a6587-114">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="a6587-114">Global Reader</span></span>
- <span data-ttu-id="a6587-115">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="a6587-115">Security Reader</span></span>

<span data-ttu-id="a6587-116">Zum Überprüfen von Konten mit diesen Rollen, siehe[Berechtigungen im Microsoft 365 Security Center](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="a6587-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="a6587-117">**Benutzerdefinierter** Rollenzugriff ist eine neue Funktion in Microsoft 365 Defender und ermöglicht ihnen die Verwaltung des Zugriffs auf bestimmte Daten, Aufgaben und Funktionen in Microsoft Defender 365.</span><span class="sxs-lookup"><span data-stu-id="a6587-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="a6587-118">Benutzerdefinierte Rollen bieten mehr Kontrolle als globale Azure AD-Rollen und bieten Benutzern nur den zugriff, den sie benötigen, mit den am wenigsten zulässigen Rollen.</span><span class="sxs-lookup"><span data-stu-id="a6587-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="a6587-119">Benutzerdefinierte Rollen können zusätzlich zu globalen Azure AD-Rollen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a6587-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="a6587-120">[Erfahren Sie mehr über benutzerdefinierte Rollen](custom-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a6587-120">[Learn more about custom roles](custom-roles.md).</span></span>

><span data-ttu-id="a6587-121">! [HINWEIS] Dieser Artikel gilt nur für die Verwaltung globaler Azure AD-Rollen.</span><span class="sxs-lookup"><span data-stu-id="a6587-121">![NOTE] This article applies only to managing global Azure AD roles.</span></span> <span data-ttu-id="a6587-122">Weitere Informationen zum Verwenden der benutzerdefinierten rollenbasierten Zugriffssteuerung finden Sie unter [Benutzerdefinierte Rollen für die rollenbasierte Zugriffssteuerung.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a6587-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="a6587-123">Zugriff auf Funktionen</span><span class="sxs-lookup"><span data-stu-id="a6587-123">Access to functionality</span></span>
<span data-ttu-id="a6587-124">Der Zugriff auf bestimmte Funktionen hängt von Ihrer [Azure AD-Rolle](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)ab.</span><span class="sxs-lookup"><span data-stu-id="a6587-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="a6587-125">Wenden Sie sich an einen globalen Administrator, wenn Sie Zugriff auf bestimmte Funktionen benötigen, für die Ihnen oder Ihrer Benutzergruppe eine neue Rolle zugewiesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="a6587-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="a6587-126">Genehmigen ausstehender automatischer Vorgänge</span><span class="sxs-lookup"><span data-stu-id="a6587-126">Approve pending automated tasks</span></span>
<span data-ttu-id="a6587-127">[Automatisierte Untersuchungen und Reaktionen](mtp-autoir-actions.md) können Maßnahmen an E-Mails, Weiterleitungsregeln, Dateien, Persistenzmechanismen und anderen Artefakten durchführen, die bei Untersuchungen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="a6587-127">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="a6587-128">Um ausstehende Aktionen, für die eine explizite Genehmigung erforderlich ist, genehmigen oder ablehnen zu können, müssen Ihnen in Microsoft 365 bestimmte Rollen zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="a6587-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="a6587-129">Weitere Informationen hierzu finden Sie unter [Info-Center-Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="a6587-129">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="a6587-130">Zugriff auf Daten</span><span class="sxs-lookup"><span data-stu-id="a6587-130">Access to data</span></span>
<span data-ttu-id="a6587-131">Der Zugriff auf Microsoft 365 Defender-Daten kann mithilfe des Bereichs gesteuert werden, der Benutzergruppen in Microsoft Defender for Endpoint role-based access control (RBAC) zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="a6587-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="a6587-132">Wenn Ihr Zugriff nicht auf eine bestimmte Gruppe von Geräten in Defender for Endpoint begrenzt wurde, haben Sie vollzugriff auf Daten in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a6587-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="a6587-133">Sobald Ihrem Konto jedoch bereichsbezogener Zugriff gewährt wurde, werden nur die Daten zu den Geräten in dem betreffenden Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6587-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="a6587-134">Wenn Sie beispielsweise nur einer Benutzergruppe mit einer Microsoft Defender for Endpoint-Rolle angehören und diese Benutzergruppe nur Zugriff auf Verkaufsgeräte erhalten hat, werden nur Daten zu Verkaufsgeräten in Microsoft 365 Defender angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6587-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="a6587-135">Weitere Informationen zu RBAC-Einstellungen in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a6587-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="a6587-136">Microsoft Cloud App Security-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a6587-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="a6587-137">Während der Vorschau erzwingt Microsoft 365 Defender keine Zugriffssteuerungen basierend auf Cloud App Security-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a6587-137">During the preview, Microsoft 365 Defender does not enforce access controls based on Cloud App Security settings.</span></span> <span data-ttu-id="a6587-138">Der Zugriff auf Microsoft 365 Defender-Daten wird von diesen Einstellungen nicht beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="a6587-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a6587-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a6587-139">Related topics</span></span>
- [<span data-ttu-id="a6587-140">Benutzerdefinierte Rollen in der rollenbasierten Zugriffssteuerung für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6587-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="a6587-141">Azure AD-Rollen</span><span class="sxs-lookup"><span data-stu-id="a6587-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="a6587-142">Microsoft Defender for Endpoint RBAC</span><span class="sxs-lookup"><span data-stu-id="a6587-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="a6587-143">Rollen in Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a6587-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)