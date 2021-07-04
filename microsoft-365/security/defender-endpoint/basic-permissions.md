---
title: Verwenden grundlegender Berechtigungen für den Zugriff auf Microsoft Defender Security Center
description: Erfahren Sie, wie Sie grundlegende Berechtigungen für den Zugriff auf das Microsoft Defender für Endpunkt-Portal verwenden.
keywords: Benutzerrollen zuweisen, Lese- und Schreibzugriff zuweisen, schreibgeschützten Zugriff zuweisen, Benutzer, Benutzerrollen, Rollen
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
ms.openlocfilehash: e7c208998e436245c53b90905858b7cf7ebe91d6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290195"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="07a5b-104">Verwenden von grundlegenden Berechtigungen für den Zugriff auf das Portal</span><span class="sxs-lookup"><span data-stu-id="07a5b-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="07a5b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="07a5b-105">**Applies to:**</span></span>
- <span data-ttu-id="07a5b-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="07a5b-106">Azure Active Directory</span></span>
- [<span data-ttu-id="07a5b-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="07a5b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="07a5b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07a5b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="07a5b-109">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="07a5b-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="07a5b-110">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="07a5b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="07a5b-111">Informationen zur Verwendung der grundlegenden Berechtigungsverwaltung finden Sie in den nachstehenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="07a5b-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="07a5b-112">Sie können eine der folgenden Lösungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="07a5b-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="07a5b-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="07a5b-113">Azure PowerShell</span></span>
- <span data-ttu-id="07a5b-114">Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="07a5b-114">Azure portal</span></span>

<span data-ttu-id="07a5b-115">Um eine präzise Kontrolle über Berechtigungen zu erhalten, [wechseln Sie zur rollenbasierten Zugriffssteuerung.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="07a5b-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="07a5b-116">Zuweisen des Benutzerzugriffs mithilfe von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="07a5b-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="07a5b-117">Sie können Benutzern eine der folgenden Berechtigungsstufen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="07a5b-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="07a5b-118">Vollzugriff (Lese- und Schreibzugriff)</span><span class="sxs-lookup"><span data-stu-id="07a5b-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="07a5b-119">Schreibgeschützter Zugriff</span><span class="sxs-lookup"><span data-stu-id="07a5b-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="07a5b-120">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="07a5b-120">Before you begin</span></span>

- <span data-ttu-id="07a5b-121">Installieren Sie Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07a5b-121">Install Azure PowerShell.</span></span> <span data-ttu-id="07a5b-122">Weitere Informationen finden Sie unter ["So installieren und konfigurieren Sie Azure PowerShell.](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)</span><span class="sxs-lookup"><span data-stu-id="07a5b-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="07a5b-123">Sie müssen die PowerShell-Cmdlets in einer Befehlszeile mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="07a5b-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="07a5b-124">Verbinden zu Ihrem Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="07a5b-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="07a5b-125">Weitere Informationen finden Sie unter [Verbinden-MsolService](/powershell/module/msonline/connect-msolservice).</span><span class="sxs-lookup"><span data-stu-id="07a5b-125">For more information, see [Connect-MsolService](/powershell/module/msonline/connect-msolservice).</span></span>

<span data-ttu-id="07a5b-126">**Vollzugriff**</span><span class="sxs-lookup"><span data-stu-id="07a5b-126">**Full access**</span></span> <br>
<span data-ttu-id="07a5b-127">Benutzer mit Vollzugriff können sich anmelden, alle Systeminformationen anzeigen und Warnungen auflösen, Dateien für eine umfassende Analyse übermitteln und das Onboardingpaket herunterladen.</span><span class="sxs-lookup"><span data-stu-id="07a5b-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="07a5b-128">Das Zuweisen von Vollzugriffsrechten erfordert das Hinzufügen der Benutzer zu den integrierten AAD-Rollen "Sicherheitsadministrator" oder "Globaler Administrator".</span><span class="sxs-lookup"><span data-stu-id="07a5b-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="07a5b-129">**Schreibgeschützter Zugriff**</span><span class="sxs-lookup"><span data-stu-id="07a5b-129">**Read-only access**</span></span> <br>
<span data-ttu-id="07a5b-130">Benutzer mit schreibgeschütztem Zugriff können sich anmelden, alle Warnungen und zugehörige Informationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="07a5b-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="07a5b-131">Sie können keine Warnungszustände ändern, Keine Dateien für eine umfassende Analyse übermitteln oder Vorgänge zur Zustandsänderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="07a5b-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="07a5b-132">Um schreibgeschützte Zugriffsrechte zuzuweisen, müssen Sie die Benutzer der integrierten Azure AD-Rolle "Security Reader" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="07a5b-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="07a5b-133">Führen Sie die folgenden Schritte aus, um Sicherheitsrollen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="07a5b-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="07a5b-134">Weisen Sie der Sicherheitsadministratorrolle mithilfe des folgenden Befehls Benutzer für Lese- **und Schreibzugriff** zu:</span><span class="sxs-lookup"><span data-stu-id="07a5b-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="07a5b-135">Weisen Sie für **den schreibgeschützten** Zugriff benutzer mithilfe des folgenden Befehls der Rolle "Sicherheitsleseberechtigter" zu:</span><span class="sxs-lookup"><span data-stu-id="07a5b-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="07a5b-136">Weitere Informationen finden Sie unter [Hinzufügen oder Entfernen von Gruppenmitgliedern mit Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="07a5b-136">For more information, see [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="07a5b-137">Zuweisen des Benutzerzugriffs über das Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="07a5b-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="07a5b-138">Weitere Informationen finden Sie unter [Zuweisen von Administrator- und Nicht-Administratorrollen zu Benutzern mit Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="07a5b-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="07a5b-139">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="07a5b-139">Related topic</span></span>

- [<span data-ttu-id="07a5b-140">Verwalten des Portalzugriffs mithilfe des RBAC</span><span class="sxs-lookup"><span data-stu-id="07a5b-140">Manage portal access using RBAC</span></span>](rbac.md)
