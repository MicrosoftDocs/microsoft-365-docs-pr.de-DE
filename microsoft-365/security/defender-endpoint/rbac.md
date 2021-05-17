---
title: Verwenden sie die rollenbasierte Zugriffssteuerung, um einen feinkörnigen Zugriff auf Microsoft Defender Security Center
description: Erstellen Sie Rollen und Gruppen innerhalb Ihrer Sicherheitsvorgänge, um Zugriff auf das Portal zu gewähren.
keywords: rbac, role, based, access, control, groups, control, tier, aad
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
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063840"
---
# <a name="manage-portal-access-using-role-based-access-control"></a><span data-ttu-id="69874-104">Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="69874-104">Manage portal access using role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="69874-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="69874-105">**Applies to:**</span></span>
- <span data-ttu-id="69874-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="69874-106">Azure Active Directory</span></span>
- <span data-ttu-id="69874-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="69874-107">Office 365</span></span>

> <span data-ttu-id="69874-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="69874-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="69874-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="69874-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

<span data-ttu-id="69874-110">Mithilfe der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) können Sie Rollen und Gruppen innerhalb Ihres Sicherheitsbetriebsteams erstellen, um den entsprechenden Zugriff auf das Portal zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="69874-110">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the  portal.</span></span> <span data-ttu-id="69874-111">Basierend auf den von Ihnen erstellten Rollen und Gruppen haben Sie eine feinkörnige Kontrolle darüber, was Benutzer mit Zugriff auf das Portal sehen und tun können.</span><span class="sxs-lookup"><span data-stu-id="69874-111">Based on the roles and groups you create, you have fine-grained control over what users with access to the portal can see and do.</span></span> 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

<span data-ttu-id="69874-112">Große geo verteilte Sicherheitsteams übernehmen in der Regel ein ebenenbasiertes Modell zum Zuweisen und Autorisieren des Zugriffs auf Sicherheitsportale.</span><span class="sxs-lookup"><span data-stu-id="69874-112">Large geo-distributed security operations teams typically adopt a tier-based model to assign and authorize access to security portals.</span></span> <span data-ttu-id="69874-113">Typische Ebenen umfassen die folgenden drei Ebenen:</span><span class="sxs-lookup"><span data-stu-id="69874-113">Typical tiers include the following three levels:</span></span>

<span data-ttu-id="69874-114">Ebene</span><span class="sxs-lookup"><span data-stu-id="69874-114">Tier</span></span> | <span data-ttu-id="69874-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69874-115">Description</span></span>
:---|:---
<span data-ttu-id="69874-116">Ebene 1</span><span class="sxs-lookup"><span data-stu-id="69874-116">Tier 1</span></span> | <span data-ttu-id="69874-117">**Lokales Sicherheitsteam/IT-Team**</span><span class="sxs-lookup"><span data-stu-id="69874-117">**Local security operations team / IT team**</span></span> <br> <span data-ttu-id="69874-118">Dieses Team untersucht in der Regel Warnungen, die in ihrer Geolocation enthalten sind, und eskaliert in Fällen, in denen eine aktive Korrektur erforderlich ist, auf Ebene 2.</span><span class="sxs-lookup"><span data-stu-id="69874-118">This team usually triages and investigates alerts contained within their geolocation and escalates to Tier 2 in cases where an active remediation is required.</span></span>
<span data-ttu-id="69874-119">Ebene 2</span><span class="sxs-lookup"><span data-stu-id="69874-119">Tier 2</span></span> | <span data-ttu-id="69874-120">**Team für regionale Sicherheitsvorgänge**</span><span class="sxs-lookup"><span data-stu-id="69874-120">**Regional security operations team**</span></span> <br> <span data-ttu-id="69874-121">Dieses Team kann alle Geräte für seine Region sehen und Korrekturaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="69874-121">This team can see all the devices for their region and perform remediation actions.</span></span>
<span data-ttu-id="69874-122">Ebene 3</span><span class="sxs-lookup"><span data-stu-id="69874-122">Tier 3</span></span> | <span data-ttu-id="69874-123">**Team für globale Sicherheitsvorgänge**</span><span class="sxs-lookup"><span data-stu-id="69874-123">**Global security operations team**</span></span> <br> <span data-ttu-id="69874-124">Dieses Team besteht aus Sicherheitsexperten und ist autorisiert, alle Aktionen aus dem Portal zu sehen und durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="69874-124">This team consists of security experts and are authorized to see and perform all actions from the portal.</span></span>

<span data-ttu-id="69874-125">Defender for Endpoint RBAC wurde entwickelt, um Ihr ebenen- oder rollenbasiertes Auswahlmodell zu unterstützen und ihnen eine präzise Kontrolle darüber zu geben, welche Rollen angezeigt werden können, auf welche Geräte sie zugreifen können und welche Aktionen sie ausführen können.</span><span class="sxs-lookup"><span data-stu-id="69874-125">Defender for Endpoint RBAC is designed to support your tier- or role-based model of choice and gives you granular control over what roles can see, devices they can access, and actions they can take.</span></span> <span data-ttu-id="69874-126">Das RBAC-Framework ist um die folgenden Steuerelemente zentriert:</span><span class="sxs-lookup"><span data-stu-id="69874-126">The RBAC framework is centered around the following controls:</span></span>

- <span data-ttu-id="69874-127">**Steuern, wer bestimmte Aktionen ergreifen kann**</span><span class="sxs-lookup"><span data-stu-id="69874-127">**Control who can take specific action**</span></span>
  - <span data-ttu-id="69874-128">Erstellen Sie benutzerdefinierte Rollen, und steuern Sie, auf welche Defender for Endpoint-Funktionen sie präzise zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="69874-128">Create custom roles and control what Defender for Endpoint capabilities they can access with granularity.</span></span>
 
- <span data-ttu-id="69874-129">**Steuern, wer Informationen zu bestimmten Gerätegruppen oder -gruppen sehen kann**</span><span class="sxs-lookup"><span data-stu-id="69874-129">**Control who can see information on specific device group or groups**</span></span>
  - <span data-ttu-id="69874-130">[Erstellen Sie Gerätegruppen](machine-groups.md) nach bestimmten Kriterien wie Namen, Tags, Domänen und anderen, und gewähren Sie ihnen dann mithilfe einer bestimmten Azure Active Directory (Azure AD)-Benutzergruppe Rollenzugriff.</span><span class="sxs-lookup"><span data-stu-id="69874-130">[Create device groups](machine-groups.md) by specific criteria such as names, tags, domains, and others, then grant role access to them using a specific  Azure Active Directory (Azure AD) user group.</span></span>

<span data-ttu-id="69874-131">Zum Implementieren des rollenbasierten Zugriffs müssen Sie Administratorrollen definieren, entsprechende Berechtigungen zuweisen und den Rollen zugewiesene Azure AD-Benutzergruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="69874-131">To implement role-based access, you'll need to define admin roles, assign corresponding permissions, and assign Azure AD user groups assigned to the roles.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="69874-132">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="69874-132">Before you begin</span></span>
<span data-ttu-id="69874-133">Vor der Verwendung von RBAC ist es wichtig, dass Sie die Rollen verstehen, die Berechtigungen erteilen können, und die Folgen des Aktivierens von RBAC.</span><span class="sxs-lookup"><span data-stu-id="69874-133">Before using RBAC, it's important that you understand the roles that can grant permissions and the consequences of turning on RBAC.</span></span>


> [!WARNING]
> <span data-ttu-id="69874-134">Bevor Sie das Feature aktivieren, ist es wichtig, dass Sie über eine Rolle des globalen Administrators oder Sicherheitsadministrators in Azure AD verfügen und dass Ihre Azure AD-Gruppen bereit sind, das Risiko zu verringern, dass das Portal gesperrt wird.</span><span class="sxs-lookup"><span data-stu-id="69874-134">Before enabling the feature, it's important that you have a Global Administrator role or Security Administrator role in Azure AD and that you have your Azure AD groups ready to reduce the risk of being locked out of the portal.</span></span> 

<span data-ttu-id="69874-135">Wenn Sie sich zum ersten Mal Microsoft Defender Security Center, erhalten Sie entweder Vollzugriff oder schreibgeschützten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="69874-135">When you first log in to Microsoft Defender Security Center, you're granted either full access or read only access.</span></span> <span data-ttu-id="69874-136">Vollzugriffsrechte werden Benutzern mit Sicherheitsadministrator- oder globalen Administratorrollen in Azure AD gewährt.</span><span class="sxs-lookup"><span data-stu-id="69874-136">Full access rights are granted to users with Security Administrator or Global Administrator roles in Azure AD.</span></span> <span data-ttu-id="69874-137">Benutzer mit einer Rolle "Security Reader" in Azure AD erhalten schreibgeschützten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="69874-137">Read only access is granted to users with a Security Reader role in Azure AD.</span></span> 

<span data-ttu-id="69874-138">Eine Person mit einer Administratorrolle "Defender for Endpoint Global" hat uneingeschränkten Zugriff auf alle Geräte, unabhängig von ihrer Gerätegruppenzuordnung und den Azure AD-Benutzergruppenzuweisungen.</span><span class="sxs-lookup"><span data-stu-id="69874-138">Someone with a Defender for Endpoint Global administrator role has unrestricted access to all devices, regardless of their device group association and the Azure AD user groups assignments</span></span>

> [!WARNING]
> <span data-ttu-id="69874-139">Anfangs können nur personen mit den Rechten des globalen Azure AD-Administrators oder des Sicherheitsadministrators Rollen in Microsoft Defender Security Center erstellen und zuweisen, daher ist es wichtig, dass die richtigen Gruppen in Azure AD bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69874-139">Initially, only those with Azure AD Global Administrator or Security Administrator rights will be able to create and assign roles in Microsoft Defender Security Center, therefore, having the right groups ready in Azure AD is important.</span></span>
>
> <span data-ttu-id="69874-140">**Wenn Sie die rollenbasierte Zugriffssteuerung aktivieren, verlieren Benutzer mit schreibgeschützten Berechtigungen (z. B. Benutzer, die der Azure AD Security-Leserrolle zugewiesen sind) den Zugriff, bis sie einer Rolle zugewiesen sind.**</span><span class="sxs-lookup"><span data-stu-id="69874-140">**Turning on role-based access control will cause users with read-only permissions (for example, users assigned to Azure AD Security reader role) to lose access until they are assigned to a role.**</span></span> 
>
><span data-ttu-id="69874-141">Benutzern mit Administratorberechtigungen wird automatisch die standardmäßig integrierte globale Administratorrolle Defender for Endpoint mit vollständigen Berechtigungen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="69874-141">Users with admin permissions are automatically assigned the default built-in Defender for Endpoint global administrator role with full permissions.</span></span> <span data-ttu-id="69874-142">Nachdem Sie sich für die Verwendung von RBAC angemeldet haben, können Sie der globalen Administratorrolle Defender for Endpoint weitere Benutzer zuweisen, die keine Azure AD Global- oder Sicherheitsadministratoren sind.</span><span class="sxs-lookup"><span data-stu-id="69874-142">After opting in to use RBAC, you can assign additional users that are not Azure AD Global or Security Administrators to the Defender for Endpoint global administrator role.</span></span> 
>
> <span data-ttu-id="69874-143">Nachdem Sie sich für die Verwendung von RBAC angemeldet haben, können Sie nicht wie bei der ersten Anmeldung am Portal zu den ursprünglichen Rollen zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="69874-143">After opting in to use RBAC, you cannot revert to the initial roles as when you first logged into the portal.</span></span> 



## <a name="related-topic"></a><span data-ttu-id="69874-144">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="69874-144">Related topic</span></span>
- [<span data-ttu-id="69874-145">Erstellen und Verwalten von Gerätegruppen in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="69874-145">Create and manage device groups in Microsoft Defender for Endpoint</span></span>](machine-groups.md)
