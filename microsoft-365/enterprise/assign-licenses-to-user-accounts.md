---
title: Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326507"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="758d5-103">Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="758d5-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="758d5-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="758d5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="758d5-105">Für das nur-Cloud-Identitätsmodell können Sie Microsoft 365-Lizenzen den Benutzerkonten zuweisen, je nachdem, wie Sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="758d5-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="758d5-106">Wenn Active Directory-Domänendienste (AD DS) Benutzerkonten zum ersten Mal synchronisiert werden, wird für das hybride Identitätsmodell nicht automatisch ein Standort oder eine Microsoft 365-Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="758d5-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="758d5-107">**Sie müssen jedes Benutzerkonto mit einem Benutzerstandort vor oder zusammen mit dem Zuweisen einer Lizenz konfigurieren.**</span><span class="sxs-lookup"><span data-stu-id="758d5-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="758d5-108">In beiden Fällen müssen Sie Benutzerkonten eine Lizenz zuweisen, damit Ihre Benutzer auf Microsoft 365-Dienste wie e-Mail und Microsoft Teams zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="758d5-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="758d5-109">Sie können Benutzerkonten entweder einzeln oder automatisch über die Gruppenmitgliedschaft Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="758d5-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="758d5-110">Wenn Sie Microsoft 365-Lizenzen einzelnen Benutzerkonten zuweisen möchten, können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="758d5-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="758d5-111">Das Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="758d5-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="758d5-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="758d5-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="758d5-113">Das Azure AD Admin Center</span><span class="sxs-lookup"><span data-stu-id="758d5-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="758d5-114">Gruppenbasierte Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="758d5-114">Group-based licensing</span></span>

<span data-ttu-id="758d5-115">Sie können Sicherheitsgruppen in Azure AD so konfigurieren, dass Lizenzen automatisch aus einer Gruppe von Abonnements für alle Mitglieder der Gruppe zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="758d5-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="758d5-116">Dies wird als *gruppenbasierte Lizenzierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="758d5-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="758d5-117">Wenn ein Benutzerkonto der Gruppe hinzugefügt oder aus ihr entfernt wird, werden die Lizenzen für die Gruppenabonnements dem Benutzerkonto automatisch zugewiesen, bzw. die Zuweisung wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="758d5-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="758d5-118">Stellen Sie sicher, dass Sie genug Lizenzen für alle Gruppenmitglieder haben.</span><span class="sxs-lookup"><span data-stu-id="758d5-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="758d5-119">Wenn keine Lizenzen mehr vorhanden sind, werden neuen Benutzern keine Lizenzen zugewiesen, bis Lizenzen verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="758d5-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="758d5-120">Sie sollten  nicht die gruppenbasierte Lizenzierung für Gruppen konfigurieren, die Azure Business to Business (B2B)-Konten enthalten.</span><span class="sxs-lookup"><span data-stu-id="758d5-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="758d5-121">Weitere Informationen finden Sie unter [Gruppenbasierte Lizenzierung in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="758d5-121">For more informaion, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="758d5-122">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="758d5-122">Next steps</span></span>

<span data-ttu-id="758d5-123">Mit den entsprechenden Benutzerkonten, denen Lizenzen zugewiesen wurden, können Sie nun folgende Aufgaben durchsetzen:</span><span class="sxs-lookup"><span data-stu-id="758d5-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="758d5-124">Implementieren der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="758d5-124">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="758d5-125">Bereitstellen von Client Software wie Microsoft 365-apps</span><span class="sxs-lookup"><span data-stu-id="758d5-125">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="758d5-126">Einrichten der Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="758d5-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="758d5-127">Konfigurieren von Diensten und Anwendungen</span><span class="sxs-lookup"><span data-stu-id="758d5-127">Configure services and applications</span></span>](configure-services-and-applications.md)
