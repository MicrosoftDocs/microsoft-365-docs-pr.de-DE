---
title: Microsoft 365-Integration in lokale Umgebungen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: In diesem Artikel erfahren Sie, wie Sie Microsoft 365 mit Ihren vorhandenen Verzeichnisdiensten und lokalen Umgebungen integrieren.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384884"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="c6865-103">Microsoft 365-Integration in lokale Umgebungen</span><span class="sxs-lookup"><span data-stu-id="c6865-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="c6865-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c6865-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c6865-105">Sie können Microsoft 365 mit Ihren vorhandenen lokalen Active Directory-Domänendienste (AD DS) und mit lokalen Installationen von Exchange Server, Skype for Business Server 2015 oder SharePoint Server integrieren.</span><span class="sxs-lookup"><span data-stu-id="c6865-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="c6865-106">Wenn Sie AD DS integrieren, können Sie Benutzerkonten für beide Umgebungen synchronisieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="c6865-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="c6865-107">Sie können auch die Kennworthash Synchronisierung (PHS) oder einmaliges Anmelden (Single Sign-on, SSO) hinzufügen, damit sich Benutzer bei beiden Umgebungen mit Ihren lokalen Anmeldeinformationen anmelden können.</span><span class="sxs-lookup"><span data-stu-id="c6865-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="c6865-108">Bei der Integration in lokale Serverprodukte erstellen Sie eine Hybridumgebung.</span><span class="sxs-lookup"><span data-stu-id="c6865-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="c6865-109">Eine Hybridumgebung kann bei der Migration von Benutzern oder Informationen zu Microsoft 365 helfen, oder Sie können weiterhin einige Benutzer oder einige lokale Informationen und einige in der Cloud haben.</span><span class="sxs-lookup"><span data-stu-id="c6865-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="c6865-110">Weitere Informationen zu Hybrid Umgebungen finden Sie unter [Hybrid Cloud](../solutions/cloud-architecture-models.md#hybrid).</span><span class="sxs-lookup"><span data-stu-id="c6865-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="c6865-111">Sie können auch die Azure Active Directory (Azure AD)-Ratgeber für angepasste Einrichtungsanleitungen im Microsoft 365 Admin Center verwenden (Sie müssen bei Microsoft 365 angemeldet sein):</span><span class="sxs-lookup"><span data-stu-id="c6865-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="c6865-112">Azure AD-Installationshandbuch</span><span class="sxs-lookup"><span data-stu-id="c6865-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="c6865-113">Synchronisieren von Benutzern aus dem Verzeichnis Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="c6865-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="c6865-114">Bereitstellungs Ratgeber für Active Directory Verbunddienste (AD FS)</span><span class="sxs-lookup"><span data-stu-id="c6865-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="c6865-115">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="c6865-115">Before you begin</span></span>

<span data-ttu-id="c6865-116">Bevor Sie Microsoft 365 und eine lokale Umgebung integrieren, müssen Sie auch die [Netzwerkplanung und die Leistungsoptimierung](network-planning-and-performance.md)durchführen.</span><span class="sxs-lookup"><span data-stu-id="c6865-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="c6865-117">Außerdem ist es wichtig, dass Sie die verfügbaren [Identitätsmodelle](about-microsoft-365-identity.md) verstehen.</span><span class="sxs-lookup"><span data-stu-id="c6865-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="c6865-118">Unter [Verwalten von Microsoft 365-Konten](manage-microsoft-365-accounts.md) finden Sie eine Liste der Tools, die Sie zum Verwalten von Microsoft 365-Benutzerkonten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c6865-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="c6865-119">Integrieren von Microsoft 365 mit AD DS</span><span class="sxs-lookup"><span data-stu-id="c6865-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="c6865-120">Wenn Sie über vorhandene Benutzerkonten in AD DS verfügen, möchten Sie nicht alle diese Konten in Microsoft 365 neu erstellen und möglicherweise Unterschiede oder Fehler zwischen den Umgebungen einführen.</span><span class="sxs-lookup"><span data-stu-id="c6865-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="c6865-121">Die Verzeichnissynchronisierung unterstützt Sie beim Spiegeln dieser Konten zwischen Ihren lokalen und Online-Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="c6865-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="c6865-122">Bei der Verzeichnissynchronisierung müssen sich die Benutzer nicht neue Informationen zu jeder Umgebung merken, und Sie brauchen die Konten nicht zweimal zu erstellen oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c6865-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="c6865-123">Sie müssen [Ihr lokales Verzeichnis für die](prepare-for-directory-synchronization.md) Verzeichnissynchronisierung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="c6865-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Mit Verzeichnissynchronisierung sorgen Sie dafür, dass die Informationen für lokale und Online-Benutzerkonten synchronisiert bleiben.](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="c6865-125">Wenn Sie möchten, dass sich Benutzer bei Microsoft 365 mit Ihren lokalen Anmeldeinformationen anmelden können, können Sie auch SSO konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c6865-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="c6865-126">Mit SSO wird Microsoft 365 so konfiguriert, dass die lokale Umgebung für die Benutzerauthentifizierung vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="c6865-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Bei der einmaligen Anmeldung steht dasselbe Konto in der lokalen und der Onlineumgebung zur Verfügung.](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="c6865-128">Verzeichnissynchronisierung mit oder ohne Kennworthash Synchronisierung oder Pass-Through-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="c6865-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="c6865-129">Ein Benutzer meldet sich mit seinem Benutzerkonto (domäne\benutzername) bei seiner lokalen Umgebung an.</span><span class="sxs-lookup"><span data-stu-id="c6865-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="c6865-130">Wenn Sie zu Microsoft 365 wechseln, müssen Sie sich mit Ihrem Arbeits-oder Schulkonto (User@Domain.com) erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="c6865-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="c6865-131">Der Benutzername ist in beiden Umgebungen identisch.</span><span class="sxs-lookup"><span data-stu-id="c6865-131">The user name is the same in both environments.</span></span> <span data-ttu-id="c6865-132">Wenn Sie PHS oder PTA hinzufügen, verfügt der Benutzer über dasselbe Kennwort für beide Umgebungen, muss diese Anmeldeinformationen jedoch erneut bereitstellen, wenn er sich bei Microsoft 365 anmeldet.</span><span class="sxs-lookup"><span data-stu-id="c6865-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="c6865-133">Die Verzeichnissynchronisierung mit PHS ist die am häufigsten verwendete Verzeichnissynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="c6865-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="c6865-134">Verwenden Sie Azure AD Connect, um die Verzeichnissynchronisierung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c6865-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="c6865-135">Anweisungen finden Sie unter [Einrichten der Verzeichnissynchronisierung für Microsoft 365](set-up-directory-synchronization.md) und [Azure AD Connect with Express Settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span><span class="sxs-lookup"><span data-stu-id="c6865-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="c6865-136">Erfahren Sie mehr über [die Vorbereitung der Verzeichnissynchronisierung auf Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="c6865-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="c6865-137">Verzeichnissynchronisierung mit SSO</span><span class="sxs-lookup"><span data-stu-id="c6865-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="c6865-138">Ein Benutzer meldet sich mit seinem Benutzerkonto bei seiner lokalen Umgebung an.</span><span class="sxs-lookup"><span data-stu-id="c6865-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="c6865-139">Wenn Sie zu Microsoft 365 wechseln, werden Sie entweder automatisch angemeldet, oder Sie melden sich mit den gleichen Anmeldeinformationen an, die Sie für Ihre lokale Umgebung verwenden (Domäne \ Benutzername).</span><span class="sxs-lookup"><span data-stu-id="c6865-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="c6865-140">Zum Einrichten von SSO verwenden Sie ebenfalls Azure Active Directory Connect.</span><span class="sxs-lookup"><span data-stu-id="c6865-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="c6865-141">Anweisungen finden Sie unter [Custom install of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="c6865-141">For instructions, see [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="c6865-142">Weitere Informationen finden Sie unter [Single Sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="c6865-142">For more information, see [single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="c6865-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="c6865-143">Azure AD Connect</span></span>

<span data-ttu-id="c6865-144">Azure AD Connect ersetzt ältere Versionen von Identitäts Integrationstools wie Dirsync und Azure AD Sync. Wenn Sie die Aktualisierung von Azure Active Directory Sync mit Azure AD Connect durchführen möchten, lesen Sie [die Upgrade-Anweisungen](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="c6865-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

## <a name="see-also"></a><span data-ttu-id="c6865-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6865-145">See also</span></span>

[<span data-ttu-id="c6865-146">Übersicht zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c6865-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
