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
description: In diesem Artikel erfahren Sie, wie Sie Microsoft 365 in Ihre vorhandenen Verzeichnisdienste und lokalen Umgebungen integrieren.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923966"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="34293-103">Microsoft 365-Integration in lokale Umgebungen</span><span class="sxs-lookup"><span data-stu-id="34293-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="34293-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="34293-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="34293-105">Sie können Microsoft 365 in Ihre vorhandenen lokalen Active Directory Domain Services (AD DS) und in lokale Installationen von Exchange Server, Skype for Business Server 2015 oder SharePoint Server integrieren.</span><span class="sxs-lookup"><span data-stu-id="34293-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="34293-106">Wenn Sie AD DS integrieren, können Sie Benutzerkonten für beide Umgebungen synchronisieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="34293-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="34293-107">Sie können auch die Kennworthashsynchronisierung (Password Hash Synchronization, PHS) oder einmaliges Anmelden (Single Sign-On, SSO) hinzufügen, damit sich Benutzer mit ihren lokalen Anmeldeinformationen bei beiden Umgebungen anmelden können.</span><span class="sxs-lookup"><span data-stu-id="34293-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="34293-108">Bei der Integration in lokale Serverprodukte erstellen Sie eine Hybridumgebung.</span><span class="sxs-lookup"><span data-stu-id="34293-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="34293-109">Eine Hybridumgebung kann beim Migrieren von Benutzern oder Informationen zu Microsoft 365 hilfreich sein, oder Sie können weiterhin einige Benutzer oder einige Informationen lokal und einige in der Cloud haben.</span><span class="sxs-lookup"><span data-stu-id="34293-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="34293-110">Weitere Informationen zu Hybridumgebungen finden Sie unter [Hybrid Cloud](../solutions/cloud-architecture-models.md#hybrid).</span><span class="sxs-lookup"><span data-stu-id="34293-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="34293-111">Sie können auch die Azure Active Directory (Azure AD)-Berater für benutzerdefinierte Setupanleitungen im Microsoft 365 Admin Center verwenden (Sie müssen bei Microsoft 365 angemeldet sein):</span><span class="sxs-lookup"><span data-stu-id="34293-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="34293-112">Azure AD-Einrichtungshandbuch</span><span class="sxs-lookup"><span data-stu-id="34293-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="34293-113">Synchronisieren von Benutzern aus dem Verzeichnis Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="34293-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="34293-114">Bereitstellungsratgeber für Active Directory Federation Services (AD FS)</span><span class="sxs-lookup"><span data-stu-id="34293-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="34293-115">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="34293-115">Before you begin</span></span>

<span data-ttu-id="34293-116">Bevor Sie Microsoft 365 und eine lokale Umgebung integrieren, müssen Sie auch die Netzwerkplanung und [Leistungsoptimierung tun.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="34293-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="34293-117">Außerdem ist es wichtig, dass Sie die verfügbaren [Identitätsmodelle](about-microsoft-365-identity.md) verstehen.</span><span class="sxs-lookup"><span data-stu-id="34293-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="34293-118">Eine Liste der Tools zum Verwalten von [Microsoft 365-Benutzerkonten](manage-microsoft-365-accounts.md) finden Sie unter Verwalten von Microsoft 365-Konten.</span><span class="sxs-lookup"><span data-stu-id="34293-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="34293-119">Integrieren von Microsoft 365 in AD DS</span><span class="sxs-lookup"><span data-stu-id="34293-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="34293-120">Wenn Sie über vorhandene Benutzerkonten in AD DS verfügen, möchten Sie nicht alle diese Konten in Microsoft 365 neu erstellen und riskieren Unterschiede oder Fehler zwischen den Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="34293-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="34293-121">Mit der Verzeichnissynchronisierung können Sie diese Konten zwischen Ihren lokalen und Onlineumgebungen spiegeln.</span><span class="sxs-lookup"><span data-stu-id="34293-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="34293-122">Bei der Verzeichnissynchronisierung müssen sich die Benutzer nicht neue Informationen zu jeder Umgebung merken, und Sie brauchen die Konten nicht zweimal zu erstellen oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="34293-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="34293-123">Sie müssen Ihr [lokales](prepare-for-directory-synchronization.md) Verzeichnis für die Verzeichnissynchronisierung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="34293-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Mit Verzeichnissynchronisierung sorgen Sie dafür, dass die Informationen für lokale und Online-Benutzerkonten synchronisiert bleiben.](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="34293-125">Wenn Sich Benutzer mit ihren lokalen Anmeldeinformationen bei Microsoft 365 anmelden können sollen, können Sie auch SSO konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="34293-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="34293-126">Mit SSO ist Microsoft 365 so konfiguriert, dass er der lokalen Umgebung für die Benutzerauthentifizierung vertraut.</span><span class="sxs-lookup"><span data-stu-id="34293-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Bei der einmaligen Anmeldung steht dasselbe Konto in der lokalen und der Onlineumgebung zur Verfügung.](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="34293-128">Verzeichnissynchronisierung mit oder ohne Kennworthashsynchronisierung oder Pass-Through-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="34293-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="34293-129">Ein Benutzer meldet sich mit seinem Benutzerkonto (domäne\benutzername) bei seiner lokalen Umgebung an.</span><span class="sxs-lookup"><span data-stu-id="34293-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="34293-130">Wenn sie zu Microsoft 365 wechseln, müssen sie sich erneut mit ihrem Arbeits- oder Schulkonto (user@domain.com) anmelden.</span><span class="sxs-lookup"><span data-stu-id="34293-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="34293-131">Der Benutzername ist in beiden Umgebungen identisch.</span><span class="sxs-lookup"><span data-stu-id="34293-131">The user name is the same in both environments.</span></span> <span data-ttu-id="34293-132">Wenn Sie PHS oder PTA hinzufügen, hat der Benutzer dasselbe Kennwort für beide Umgebungen, muss diese Anmeldeinformationen jedoch bei der Anmeldung bei Microsoft 365 erneut angeben.</span><span class="sxs-lookup"><span data-stu-id="34293-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="34293-133">Die Verzeichnissynchronisierung mit PHS ist die am häufigsten verwendete Verzeichnissynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="34293-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="34293-134">Verwenden Sie Azure AD Connect, um die Verzeichnissynchronisierung einrichten.</span><span class="sxs-lookup"><span data-stu-id="34293-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="34293-135">Anweisungen finden Sie unter [Einrichten der Verzeichnissynchronisierung für Microsoft 365](set-up-directory-synchronization.md) und [Azure AD Connect mit Expresseinstellungen.](/azure/active-directory/hybrid/how-to-connect-install-express)</span><span class="sxs-lookup"><span data-stu-id="34293-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

<span data-ttu-id="34293-136">Erfahren Sie mehr [über die Vorbereitung der Verzeichnissynchronisierung mit Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="34293-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="34293-137">Verzeichnissynchronisierung mit SSO</span><span class="sxs-lookup"><span data-stu-id="34293-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="34293-138">Ein Benutzer meldet sich mit seinem Benutzerkonto bei seiner lokalen Umgebung an.</span><span class="sxs-lookup"><span data-stu-id="34293-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="34293-139">Wenn sie zu Microsoft 365 wechseln, werden sie entweder automatisch angemeldet, oder sie melden sich mit denselben Anmeldeinformationen an, die sie für ihre lokale Umgebung verwenden (Domäne\Benutzername).</span><span class="sxs-lookup"><span data-stu-id="34293-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="34293-140">Zum Einrichten von SSO verwenden Sie ebenfalls Azure Active Directory Connect.</span><span class="sxs-lookup"><span data-stu-id="34293-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="34293-141">Anweisungen finden Sie unter [Benutzerdefinierte Installation von Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span><span class="sxs-lookup"><span data-stu-id="34293-141">For instructions, see [Custom installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>

<span data-ttu-id="34293-142">Weitere Informationen finden Sie unter [Einmaliges Anmelden](/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="34293-142">For more information, see [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="34293-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="34293-143">Azure AD Connect</span></span>

<span data-ttu-id="34293-144">Azure AD Connect ersetzt ältere Versionen von Identitätsintegrationstools wie DirSync und Azure AD Sync. Wenn Sie von Azure Active Directory Sync auf Azure AD Connect aktualisieren möchten, lesen Sie [die Upgradeanweisungen](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span><span class="sxs-lookup"><span data-stu-id="34293-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span></span> 

## <a name="see-also"></a><span data-ttu-id="34293-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34293-145">See also</span></span>

[<span data-ttu-id="34293-146">Übersicht zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="34293-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)