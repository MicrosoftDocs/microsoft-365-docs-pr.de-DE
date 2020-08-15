---
title: Microsoft 365-Integration in lokale Umgebungen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2019
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
ms.openlocfilehash: 46f0fab6396dd1db82524ea1aeedc6894ce7ab70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690848"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="e0789-103">Microsoft 365-Integration in lokale Umgebungen</span><span class="sxs-lookup"><span data-stu-id="e0789-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="e0789-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e0789-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e0789-105">Sie können Microsoft 365 mit Ihren vorhandenen Verzeichnisdiensten und mit einer lokalen Installation von Exchange Server, Skype for Business Server 2015 oder SharePoint Server integrieren.</span><span class="sxs-lookup"><span data-stu-id="e0789-105">You can integrate Microsoft 365 with your existing directory services and with an on-premises installation of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="e0789-106">Wenn Sie die Integration in die Verzeichnisdienste durchführen, können Sie Benutzerkonten für beide Umgebungen synchronisieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="e0789-106">When you integrate with directory services, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="e0789-107">Sie können auch die Kennworthashsynchronisierung oder das einmalige Anmelden (Single Sign-on, SSO) hinzufügen, damit sich die Benutzer mit Ihren lokalen Anmeldeinformationen bei beiden Umgebungen anmelden können.</span><span class="sxs-lookup"><span data-stu-id="e0789-107">You can also add password hash synchronization or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="e0789-108">Bei der Integration in lokale Serverprodukte erstellen Sie eine Hybridumgebung.</span><span class="sxs-lookup"><span data-stu-id="e0789-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="e0789-109">Eine Hybridumgebung kann bei der Migration von Benutzern oder Informationen zu Microsoft 365 helfen, oder Sie können weiterhin einige Benutzer oder einige lokale Informationen und einige in der Cloud haben.</span><span class="sxs-lookup"><span data-stu-id="e0789-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="e0789-110">Weitere Informationen zu Hybridumgebungen finden Sie unter [Übersicht über die Hybridcloud](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="e0789-110">For more information about hybrid environments, see [Hybrid cloud overview](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span></span>

<span data-ttu-id="e0789-111">Sie können auch die Azure Active Directory (Azure AD)-Ratgeber für angepasste Setup Anleitungen verwenden (Sie müssen bei Microsoft 365 angemeldet sein):</span><span class="sxs-lookup"><span data-stu-id="e0789-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="e0789-112">Synchronisieren von Benutzern aus dem Verzeichnis Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="e0789-112">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="e0789-113">Bereitstellungsratgeber für AD FS</span><span class="sxs-lookup"><span data-stu-id="e0789-113">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
- [<span data-ttu-id="e0789-114">Azure AD-Installationshandbuch</span><span class="sxs-lookup"><span data-stu-id="e0789-114">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="e0789-115">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="e0789-115">Before you begin</span></span>

<span data-ttu-id="e0789-116">Bevor Sie Microsoft 365 und eine lokale Umgebung integrieren, müssen Sie auch an der [Netzwerkplanung und der Leistungsoptimierung](network-planning-and-performance.md)teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="e0789-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to attend to [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="e0789-117">Außerdem ist es wichtig, dass Sie die verfügbaren [Identitätsmodelle](about-microsoft-365-identity.md) verstehen.</span><span class="sxs-lookup"><span data-stu-id="e0789-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="e0789-118">Eine Liste der Tools, die Sie zum Verwalten von Microsoft 365-Benutzern und-Konten verwenden können, finden Sie unter [Verwalten von Microsoft 365-Konten](manage-microsoft-365-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="e0789-118">See [where to manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 users and accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-directory-services"></a><span data-ttu-id="e0789-119">Integrieren von Microsoft 365 mit Verzeichnisdiensten</span><span class="sxs-lookup"><span data-stu-id="e0789-119">Integrate Microsoft 365 with directory services</span></span>
<span data-ttu-id="e0789-120">Wenn Sie über vorhandene Benutzerkonten in einem lokalen Verzeichnis verfügen, möchten Sie nicht alle diese Konten in Microsoft 365 neu erstellen und möglicherweise Unterschiede oder Fehler zwischen den Umgebungen einführen.</span><span class="sxs-lookup"><span data-stu-id="e0789-120">If you have existing user accounts in an on-premises directory, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="e0789-121">Mithilfe der Verzeichnissynchronisierung können Sie diese Konten zwischen der Onlineumgebung und der lokalen Umgebung spiegeln.</span><span class="sxs-lookup"><span data-stu-id="e0789-121">Directory synchronization helps you mirror those accounts between your online and on-premises environments.</span></span> <span data-ttu-id="e0789-122">Bei der Verzeichnissynchronisierung müssen sich die Benutzer nicht neue Informationen zu jeder Umgebung merken, und Sie brauchen die Konten nicht zweimal zu erstellen oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e0789-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="e0789-123">Sie müssen [Ihr lokales Verzeichnis für die](prepare-for-directory-synchronization.md) Verzeichnissynchronisierung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="e0789-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Mit Verzeichnissynchronisierung sorgen Sie dafür, dass die Informationen für lokale und Online-Benutzerkonten synchronisiert bleiben.](../media/a64af0d0-9be6-46b1-8727-277e683abf5e.png)
  
<span data-ttu-id="e0789-125">Wenn Sie möchten, dass sich Benutzer bei Microsoft 365 mit Ihren lokalen Anmeldeinformationen anmelden können, können Sie auch SSO konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e0789-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="e0789-126">Mit SSO wird Microsoft 365 so konfiguriert, dass die lokale Umgebung für die Benutzerauthentifizierung vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="e0789-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Bei der einmaligen Anmeldung steht dasselbe Konto in der lokalen und der Onlineumgebung zur Verfügung.](../media/d76235f2-8a53-405e-b8ef-dfa4cfc208b8.png)
  
<span data-ttu-id="e0789-128">Unterschiedliche Techniken der Benutzerkontenverwaltung bieten Ihren Benutzern unterschiedliche Erfahrungen, wie in der nachstehenden Tabelle gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e0789-128">Different user account management techniques provide different experiences for your users, as shown in the following table.</span></span>
 
### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication"></a><span data-ttu-id="e0789-129">Verzeichnissynchronisierung mit oder ohne Kennworthashsynchronisierung oder Passthrough-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e0789-129">Directory synchronization with or without password hash synchronization or pass-through authentication</span></span>

<span data-ttu-id="e0789-130">Ein Benutzer meldet sich mit seinem Benutzerkonto (domäne\benutzername) bei seiner lokalen Umgebung an.</span><span class="sxs-lookup"><span data-stu-id="e0789-130">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="e0789-131">Wenn Sie zu Microsoft 365 wechseln, müssen Sie sich mit Ihrem Arbeits-oder Schulkonto (User@Domain.com) erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="e0789-131">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="e0789-132">Der Benutzername ist in beiden Umgebungen identisch.</span><span class="sxs-lookup"><span data-stu-id="e0789-132">The user name is the same in both environments.</span></span> <span data-ttu-id="e0789-133">Wenn Sie Kennworthash Synchronisierung oder Pass-Through-Authentifizierung hinzufügen, verfügt der Benutzer über dasselbe Kennwort für beide Umgebungen, muss diese Anmeldeinformationen jedoch erneut bereitstellen, wenn er sich bei Microsoft 365 anmeldet.</span><span class="sxs-lookup"><span data-stu-id="e0789-133">When you add password hash sync or pass-through authentication, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="e0789-134">Verzeichnissynchronisierung mit Kennworthashsynchronisierung ist das am häufigsten verwendete Szenario der Verzeichnissynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="e0789-134">Directory synchronization with password hash sync is the most commonly used directory sync scenario.</span></span>

<span data-ttu-id="e0789-135">Verwenden Sie Azure Active Directory Connect, um die Verzeichnissynchronisierung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="e0789-135">To set up directory synchronization, use Azure Active Directory Connect.</span></span> <span data-ttu-id="e0789-136">Anweisungen finden Sie unter [Einrichten der Verzeichnissynchronisierung für Microsoft 365](set-up-directory-synchronization.md)und [Azure AD Verbindung mit Express-Einstellungen](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span><span class="sxs-lookup"><span data-stu-id="e0789-136">For instructions, read [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md), and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="e0789-137">Erfahren Sie mehr über die [Vorbereitung der Verzeichnissynchronisierung auf Microsoft 365](prepare-for-directory-synchronization.md) und [die Integration Ihrer lokalen identifiziert sich mit Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span><span class="sxs-lookup"><span data-stu-id="e0789-137">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md) and [integrating your on-premises identifies with Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="e0789-138">Verzeichnissynchronisierung mit SSO</span><span class="sxs-lookup"><span data-stu-id="e0789-138">Directory synchronization with SSO</span></span>

<span data-ttu-id="e0789-139">Ein Benutzer meldet sich mit seinem Benutzerkonto bei seiner lokalen Umgebung an.</span><span class="sxs-lookup"><span data-stu-id="e0789-139">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="e0789-140">Wenn Sie zu Microsoft 365 wechseln, werden Sie entweder automatisch angemeldet, oder Sie melden sich mit den gleichen Anmeldeinformationen an, die Sie für Ihre lokale Umgebung verwenden (Domäne \ Benutzername).</span><span class="sxs-lookup"><span data-stu-id="e0789-140">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="e0789-141">Zum Einrichten von SSO verwenden Sie ebenfalls Azure Active Directory Connect.</span><span class="sxs-lookup"><span data-stu-id="e0789-141">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="e0789-142">Anweisungen finden Sie unter [Benutzerdefinierte Installation von Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="e0789-142">For instructions, read [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="e0789-143">Weitere Informationen zum [einmaligen Anmelden bei Anwendungen in Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="e0789-143">Learn more about [single sign-on to applications in Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="e0789-144">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="e0789-144">Azure AD Connect</span></span>

<span data-ttu-id="e0789-145">Azure AD Connect ersetzt ältere Versionen von Identitätsintegrationstools wie DirSync und Azure AD Sync. Weitere Informationen finden Sie unter [Was bedeutet Hybrididentität in Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969).</span><span class="sxs-lookup"><span data-stu-id="e0789-145">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. For more information, see [What is hybrid identity with Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969).</span></span> <span data-ttu-id="e0789-146">Informationen zum Aktualisieren von Azure AD Sync auf Azure AD Connect finden Sie in den [Aktualisierungsanweisungen](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="e0789-146">If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

<span data-ttu-id="e0789-147">Siehe auch [Bereitstellen der Microsoft 365-Verzeichnissynchronisierung in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span><span class="sxs-lookup"><span data-stu-id="e0789-147">Also see [Deploy Microsoft 365 Directory Synchronization in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0789-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0789-148">See also</span></span>

[<span data-ttu-id="e0789-149">Übersicht zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e0789-149">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
