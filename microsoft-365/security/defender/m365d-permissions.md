---
title: Verwalten des Zugriffs auf Microsoft 365 Defender Daten im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Berechtigungen für Daten in Microsoft 365 Defender
keywords: Zugriff, Berechtigungen, Microsoft 365 Defender, M365, Sicherheit, MCAS, Cloud App Security, Microsoft Defender für Endpunkt, Bereich, Bereichsdefinition, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 738315c446fd57d4cd027de92eb77b0029f84323
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177528"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="0aa7a-104">Verwalten des Zugriffs auf Microsoft 365 Defender mit Azure Active Directory globalen Rollen</span><span class="sxs-lookup"><span data-stu-id="0aa7a-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0aa7a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0aa7a-105">**Applies to:**</span></span>
- <span data-ttu-id="0aa7a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0aa7a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0aa7a-107">Es gibt zwei Möglichkeiten zum Verwalten des Zugriffs auf Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0aa7a-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="0aa7a-108">**Rollen für globale Azure Active Directory (AD)**</span><span class="sxs-lookup"><span data-stu-id="0aa7a-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="0aa7a-109">**Benutzerdefinierter Rollenzugriff**</span><span class="sxs-lookup"><span data-stu-id="0aa7a-109">**Custom role access**</span></span>

<span data-ttu-id="0aa7a-110">Konten, die den folgenden **globalen Azure Active Directory (AD)-Rollen** zugewiesen sind, können auf Microsoft 365 Defender Funktionen und Daten zugreifen:</span><span class="sxs-lookup"><span data-stu-id="0aa7a-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="0aa7a-111">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="0aa7a-111">Global administrator</span></span>
- <span data-ttu-id="0aa7a-112">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="0aa7a-112">Security administrator</span></span>
- <span data-ttu-id="0aa7a-113">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="0aa7a-113">Security Operator</span></span>
- <span data-ttu-id="0aa7a-114">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="0aa7a-114">Global Reader</span></span>
- <span data-ttu-id="0aa7a-115">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="0aa7a-115">Security Reader</span></span>

<span data-ttu-id="0aa7a-116">Zum Überprüfen von Konten mit diesen Rollen, siehe[Berechtigungen im Microsoft 365 Security Center](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="0aa7a-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="0aa7a-117">**Der benutzerdefinierte Rollenzugriff** ist eine neue Funktion in Microsoft 365 Defender und ermöglicht es Ihnen, den Zugriff auf bestimmte Daten, Aufgaben und Funktionen in Microsoft Defender 365 zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="0aa7a-118">Benutzerdefinierte Rollen bieten mehr Kontrolle als globale Azure AD-Rollen, sodass Benutzer nur den Zugriff erhalten, den sie mit den am wenigsten eingeschränkten Rollen benötigen.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="0aa7a-119">Benutzerdefinierte Rollen können zusätzlich zu globalen Azure AD-Rollen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="0aa7a-120">[Weitere Informationen zu benutzerdefinierten Rollen.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0aa7a-120">[Learn more about custom roles](custom-roles.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0aa7a-121">Dieser Artikel bezieht sich nur auf die Verwaltung globaler Azure Active Directory Rollen.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-121">This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="0aa7a-122">Weitere Informationen zur Verwendung einer benutzerdefinierten rollenbasierten Zugriffssteuerung finden Sie unter ["Benutzerdefinierte Rollen für die rollenbasierte Zugriffssteuerung".](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0aa7a-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="0aa7a-123">Zugriff auf Funktionen</span><span class="sxs-lookup"><span data-stu-id="0aa7a-123">Access to functionality</span></span>
<span data-ttu-id="0aa7a-124">Der Zugriff auf bestimmte Funktionen hängt von Ihrer [Azure AD-Rolle](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)ab.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="0aa7a-125">Wenden Sie sich an einen globalen Administrator, wenn Sie Zugriff auf bestimmte Funktionen benötigen, für die Ihnen oder Ihrer Benutzergruppe eine neue Rolle zugewiesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="0aa7a-126">Genehmigen ausstehender automatischer Vorgänge</span><span class="sxs-lookup"><span data-stu-id="0aa7a-126">Approve pending automated tasks</span></span>
<span data-ttu-id="0aa7a-127">[Automatisierte Untersuchungen und Reaktionen](m365d-autoir-actions.md) können Maßnahmen an E-Mails, Weiterleitungsregeln, Dateien, Persistenzmechanismen und anderen Artefakten durchführen, die bei Untersuchungen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-127">[Automated investigation and remediation](m365d-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="0aa7a-128">Um ausstehende Aktionen, für die eine explizite Genehmigung erforderlich ist, genehmigen oder ablehnen zu können, müssen Ihnen in Microsoft 365 bestimmte Rollen zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="0aa7a-129">Weitere Informationen hierzu finden Sie unter [Info-Center-Berechtigungen](m365d-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="0aa7a-129">To learn more, see [Action center permissions](m365d-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="0aa7a-130">Zugriff auf Daten</span><span class="sxs-lookup"><span data-stu-id="0aa7a-130">Access to data</span></span>
<span data-ttu-id="0aa7a-131">Der Zugriff auf Microsoft 365 Defender Daten kann mithilfe des Bereichs gesteuert werden, der Benutzergruppen in Microsoft Defender für Endpunkt rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="0aa7a-132">Wenn Ihr Zugriff nicht auf eine bestimmte Gruppe von Geräten im Defender für Endpunkt beschränkt wurde, haben Sie vollzugriff auf Daten in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="0aa7a-133">Sobald Ihrem Konto jedoch bereichsbezogener Zugriff gewährt wurde, werden nur die Daten zu den Geräten in dem betreffenden Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="0aa7a-134">Wenn Sie beispielsweise nur einer Benutzergruppe mit einer Microsoft Defender für Endpunkt-Rolle angehören und dieser Benutzergruppe nur Zugriff auf Verkaufsgeräte gewährt wurde, werden nur Daten zu Verkaufsgeräten in Microsoft 365 Defender angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="0aa7a-135">Weitere Informationen zu RBAC-Einstellungen in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0aa7a-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="0aa7a-136">Microsoft Cloud App Security-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="0aa7a-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="0aa7a-137">Während der Vorschau erzwingt Microsoft 365 Defender keine Zugriffssteuerungen basierend auf Cloud App Security Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="0aa7a-138">Der Zugriff auf Microsoft 365 Defender Daten wird von diesen Einstellungen nicht beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0aa7a-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0aa7a-139">Related topics</span></span>
- [<span data-ttu-id="0aa7a-140">Benutzerdefinierte Rollen in der rollenbasierten Zugriffssteuerung für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0aa7a-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="0aa7a-141">Azure AD-Rollen</span><span class="sxs-lookup"><span data-stu-id="0aa7a-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="0aa7a-142">Microsoft Defender für Endpunkt-RBAC</span><span class="sxs-lookup"><span data-stu-id="0aa7a-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="0aa7a-143">Rollen in Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0aa7a-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)
