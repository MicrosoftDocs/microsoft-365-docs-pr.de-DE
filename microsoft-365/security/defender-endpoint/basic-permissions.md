---
title: Verwenden grundlegender Berechtigungen für den Zugriff auf Microsoft Defender Security Center
description: Erfahren Sie, wie Sie grundlegende Berechtigungen für den Zugriff auf das Microsoft Defender for Endpoint-Portal verwenden.
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
ms.technology: mde
ms.openlocfilehash: cb5762d2a9e4b62432aba6dacd1033ddc3c7daf2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163671"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="d0b58-104">Verwenden grundlegender Berechtigungen für den Zugriff auf das Portal</span><span class="sxs-lookup"><span data-stu-id="d0b58-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d0b58-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d0b58-105">**Applies to:**</span></span>
- <span data-ttu-id="d0b58-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d0b58-106">Azure Active Directory</span></span>
- [<span data-ttu-id="d0b58-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d0b58-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d0b58-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0b58-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d0b58-109">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d0b58-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d0b58-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d0b58-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="d0b58-111">Lesen Sie die anweisungen unten, um die grundlegende Berechtigungsverwaltung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0b58-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="d0b58-112">Sie können eine der folgenden Lösungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="d0b58-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="d0b58-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0b58-113">Azure PowerShell</span></span>
- <span data-ttu-id="d0b58-114">Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="d0b58-114">Azure portal</span></span>

<span data-ttu-id="d0b58-115">Wechseln Sie zur rollenbasierten Zugriffssteuerung, um die Berechtigungen präzise [zu steuern.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="d0b58-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="d0b58-116">Zuweisen des Benutzerzugriffs mithilfe von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0b58-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="d0b58-117">Sie können Benutzern eine der folgenden Berechtigungsebenen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="d0b58-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="d0b58-118">Vollzugriff (Lese- und Schreibzugriff)</span><span class="sxs-lookup"><span data-stu-id="d0b58-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="d0b58-119">Schreibgeschützter Zugriff</span><span class="sxs-lookup"><span data-stu-id="d0b58-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="d0b58-120">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="d0b58-120">Before you begin</span></span>

- <span data-ttu-id="d0b58-121">Installieren Sie Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0b58-121">Install Azure PowerShell.</span></span> <span data-ttu-id="d0b58-122">Weitere Informationen finden Sie unter Installieren und Konfigurieren [von Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span><span class="sxs-lookup"><span data-stu-id="d0b58-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="d0b58-123">Sie müssen die PowerShell-Cmdlets in einer Befehlszeile mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="d0b58-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="d0b58-124">Stellen Sie eine Verbindung mit Ihrem Azure Active Directory bereit.</span><span class="sxs-lookup"><span data-stu-id="d0b58-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="d0b58-125">Weitere Informationen finden Sie unter [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="d0b58-125">For more information, see [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span></span>

<span data-ttu-id="d0b58-126">**Vollzugriff**</span><span class="sxs-lookup"><span data-stu-id="d0b58-126">**Full access**</span></span> <br>
<span data-ttu-id="d0b58-127">Benutzer mit Vollzugriff können sich anmelden, alle Systeminformationen anzeigen und Warnungen auflösen, Dateien für eine umfassende Analyse übermitteln und das Onboardingpaket herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d0b58-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="d0b58-128">Das Zuweisen von Vollzugriffsrechten erfordert das Hinzufügen der Benutzer zu den integrierten AAD-Rollen "Sicherheitsadministrator" oder "Globaler Administrator".</span><span class="sxs-lookup"><span data-stu-id="d0b58-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="d0b58-129">**Schreibgeschützter Zugriff**</span><span class="sxs-lookup"><span data-stu-id="d0b58-129">**Read-only access**</span></span> <br>
<span data-ttu-id="d0b58-130">Benutzer mit schreibgeschützten Zugriff können sich anmelden, alle Warnungen und zugehörige Informationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d0b58-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="d0b58-131">Sie können keine Warnungszustände ändern, Dateien zur tiefen Analyse übermitteln oder Zustandsänderungsvorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="d0b58-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="d0b58-132">Zum Zuweisen von schreibgeschützten Zugriffsrechten müssen die Benutzer der integrierten Azure AD-Rolle "Security Reader" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d0b58-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="d0b58-133">Verwenden Sie die folgenden Schritte, um Sicherheitsrollen zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="d0b58-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="d0b58-134">Weisen **Sie benutzern für lese-** und schreibzugriff die Rolle des Sicherheitsadministrators mithilfe des folgenden Befehls zu:</span><span class="sxs-lookup"><span data-stu-id="d0b58-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="d0b58-135">Weisen Sie benutzern für den **schreibgeschützten** Zugriff mithilfe des folgenden Befehls die Rolle "Sicherheitsleser" zu:</span><span class="sxs-lookup"><span data-stu-id="d0b58-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="d0b58-136">Weitere Informationen finden Sie unter [Hinzufügen oder Entfernen von Gruppenmitgliedern mithilfe von Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="d0b58-136">For more information, see [Add or remove group members using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="d0b58-137">Zuweisen des Benutzerzugriffs mithilfe des Azure-Portals</span><span class="sxs-lookup"><span data-stu-id="d0b58-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="d0b58-138">Weitere Informationen finden Sie unter [Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="d0b58-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="d0b58-139">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="d0b58-139">Related topic</span></span>

- [<span data-ttu-id="d0b58-140">Verwalten des Portalzugriffs mithilfe von RBAC</span><span class="sxs-lookup"><span data-stu-id="d0b58-140">Manage portal access using RBAC</span></span>](rbac.md)
