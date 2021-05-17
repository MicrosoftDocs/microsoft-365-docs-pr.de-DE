---
title: Bereitstellen Microsoft 365 Verzeichnissynchronisierung in Microsoft Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: Erfahren Sie, wie Sie Azure AD Verbinden auf einem virtuellen Computer in Azure bereitstellen, um Konten zwischen Ihrem lokalen Verzeichnis und dem Azure AD-Mandanten zu synchronisieren.
ms.openlocfilehash: 52c1bb2eb53cc4e6753d528e0d82822b2a0eebc5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919086"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a><span data-ttu-id="ebc6b-103">Bereitstellen Microsoft 365 Verzeichnissynchronisierung in Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="ebc6b-103">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>

<span data-ttu-id="ebc6b-104">Azure Active Directory (Azure AD) Verbinden (früher als Verzeichnissynchronisierungstool, Verzeichnissynchronisierungstool oder DirSync.exe-Tool bezeichnet) ist eine Anwendung, die Sie auf einem Server installieren, der der Domäne beigetreten ist, um Ihre lokalen Active Directory Domain Services (AD DS)-Benutzer mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-104">Azure Active Directory (Azure AD) Connect (formerly known as the Directory Synchronization tool, Directory Sync tool, or the DirSync.exe tool) is an application that you install on a domain-joined server to synchronize your on-premises Active Directory Domain Services (AD DS) users to the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="ebc6b-105">Microsoft 365 verwendet Azure AD für seinen Verzeichnisdienst.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-105">Microsoft 365 uses Azure AD for its directory service.</span></span> <span data-ttu-id="ebc6b-106">Ihr Microsoft 365 umfasst einen Azure AD-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-106">Your Microsoft 365 subscription includes an Azure AD tenant.</span></span> <span data-ttu-id="ebc6b-107">Dieser Mandant kann auch für die Verwaltung der Identitäten Ihrer Organisation mit anderen Cloudworkloads verwendet werden, einschließlich anderer SaaS-Anwendungen und Apps in Azure.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-107">This tenant can also be used for management of your organization's identities with other cloud workloads, including other SaaS applications and apps in Azure.</span></span>

<span data-ttu-id="ebc6b-108">Sie können Azure AD Connect auf einem lokalen Server installieren, doch wir empfehlen aus den folgenden Gründen die Installation auf einem virtuellen Computer in Azure:</span><span class="sxs-lookup"><span data-stu-id="ebc6b-108">You can install Azure AD Connect on a on-premises server, but you can also install it on a virtual machine in Azure for these reasons:</span></span>
  
- <span data-ttu-id="ebc6b-109">Sie können cloudbasierte Server schneller bereitstellen und konfigurieren und so die Dienste Ihren Benutzern schneller zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-109">You can provision and configure cloud-based servers faster, making the services available to your users sooner.</span></span>
- <span data-ttu-id="ebc6b-110">Azure bietet eine bessere Verfügbarkeit von Websites mit weniger Aufwand.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-110">Azure offers better site availability with less effort.</span></span>
- <span data-ttu-id="ebc6b-111">Sie können die Anzahl der lokalen Server in Ihrer Organisation verringern.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-111">You can reduce the number of on-premises servers in your organization.</span></span>

<span data-ttu-id="ebc6b-p102">Diese Lösung erfordert Konnektivität zwischen dem lokalen Netzwerk und Ihrem virtuellen Azure-Netzwerk. Weitere Informationen finden Sie unter [Verbinden eines lokalen Netzwerks mit einem virtuellen Microsoft Azure-Netzwerk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p102">This solution requires connectivity between your on-premises network and your Azure virtual network. For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ebc6b-114">In diesem Artikel wird die Synchronisierung einer einzelnen Domäne in einer einzelnen Gesamtstruktur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-114">This article describes synchronization of a single domain in a single forest.</span></span> <span data-ttu-id="ebc6b-115">Azure AD Verbinden synchronisiert alle AD DS-Domänen in Ihrer Active Directory-Gesamtstruktur mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-115">Azure AD Connect synchronizes all AD DS domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="ebc6b-116">Wenn Sie mehrere Active Directory-Gesamtstrukturen zum Synchronisieren mit Microsoft 365 haben, finden Sie weitere Informationen unter [Multi-Forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="ebc6b-116">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span> 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a><span data-ttu-id="ebc6b-117">Übersicht über die Bereitstellung Microsoft 365 Verzeichnissynchronisierung in Azure</span><span class="sxs-lookup"><span data-stu-id="ebc6b-117">Overview of deploying Microsoft 365 directory synchronization in Azure</span></span>

<span data-ttu-id="ebc6b-118">Das folgende Diagramm zeigt Azure AD Verbinden, das auf einem virtuellen Computer in Azure (dem Verzeichnissynchronisierungsserver) ausgeführt wird, der eine lokale AD DS-Gesamtstruktur mit einem Microsoft 365 synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-118">The following diagram shows Azure AD Connect running on a virtual machine in Azure (the directory sync server) that synchronizes an on-premises AD DS forest to a Microsoft 365 subscription.</span></span>
  
![Azure AD Verbinden tool on a virtual machine in Azure synchronizing on-premises accounts to the Azure AD tenant of a Microsoft 365 subscription with traffic flow](../media/CP-DirSyncOverview.png)
  
<span data-ttu-id="ebc6b-p104">In diesem Diagramm gibt es zwei Netzwerke, die über eine Standort-zu-Standort-VPN- oder ExpressRoute-Verbindung verbunden sind. Es gibt ein lokales Netzwerk, in dem AD DS-Domänencontroller enthalten sind, und ein virtuelles Azure-Netzwerk mit einem Verzeichnissynchronisierungsserver, einem virtuellen Computer mit ausgeführtem [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). Es gibt zwei Hauptdatenströme, die vom Verzeichnissynchronisierungsserver stammen:</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p104">In the diagram, there are two networks connected by a site-to-site VPN or ExpressRoute connection. There is an on-premises network where AD DS domain controllers are located, and there is an Azure virtual network with a directory sync server, which is a virtual machine running [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). There are two main traffic flows originating from the directory sync server:</span></span>
  
-  <span data-ttu-id="ebc6b-123">Azure AD Connect fragt einen Domänencontroller im lokalen Netzwerk auf Änderungen an Benutzerkonten und Kennwörtern ab.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-123">Azure AD Connect queries a domain controller on the on-premises network for changes to accounts and passwords.</span></span>
-  <span data-ttu-id="ebc6b-124">Azure AD Verbinden sendet die Änderungen an Konten und Kennwörtern an die Azure AD-Instanz Ihres Microsoft 365 Abonnements.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-124">Azure AD Connect sends the changes to accounts and passwords to the Azure AD instance of your Microsoft 365 subscription.</span></span> <span data-ttu-id="ebc6b-125">Da sich der Verzeichnissynchronisierungsserver in einem erweiterten Teil Ihres lokalen Netzwerks befindet, werden diese Änderungen über den Proxyserver des lokalen Netzwerks gesendet.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-125">Because the directory sync server is in an extended portion of your on-premises network, these changes are sent through the on-premises network's proxy server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ebc6b-126">Diese Lösung beschreibt die Synchronisierung einer einzelnen Active Directory-Domäne in einer einzelnen Active Directory-Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-126">This solution describes synchronization of a single Active Directory domain, in a single Active Directory forest.</span></span> <span data-ttu-id="ebc6b-127">Azure AD Verbinden synchronisiert alle Active Directory-Domänen in Ihrer Active Directory-Gesamtstruktur mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-127">Azure AD Connect synchronizes all Active Directory domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="ebc6b-128">Wenn Sie mehrere Active Directory-Gesamtstrukturen zum Synchronisieren mit Microsoft 365 haben, finden Sie weitere Informationen unter [Multi-Forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="ebc6b-128">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span> 
  
<span data-ttu-id="ebc6b-129">Es gibt bei der Bereitstellung dieser Lösung zwei wichtige Schritte:</span><span class="sxs-lookup"><span data-stu-id="ebc6b-129">There are two major steps when you deploy this solution:</span></span>
  
1. <span data-ttu-id="ebc6b-p107">Erstellen eines virtuellen Azure-Netzwerks und Einrichten einer Standort-zu-Standort-VPN-Verbindung mit dem lokalen Netzwerk. Weitere Informationen finden Sie unter [Verbinden eines lokalen Netzwerks mit einem virtuellen Microsoft Azure-Netzwerk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p107">Create an Azure virtual network and establish a site-to-site VPN connection to your on-premises network. For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
    
2. <span data-ttu-id="ebc6b-132">Installieren [Sie Azure AD Verbinden](https://www.microsoft.com/download/details.aspx?id=47594) auf einem virtuellen Computer mit Domänen in Azure, und synchronisieren Sie dann den lokalen AD DS mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-132">Install [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) on a domain-joined virtual machine in Azure, and then synchronize the on-premises AD DS to Microsoft 365.</span></span> <span data-ttu-id="ebc6b-133">Dies umfasst:</span><span class="sxs-lookup"><span data-stu-id="ebc6b-133">This involves:</span></span>
    
    <span data-ttu-id="ebc6b-134">Erstellen eines Virtueller Azure-Computer zum Ausführen von Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-134">Creating an Azure Virtual Machine to run Azure AD Connect.</span></span>
    
    <span data-ttu-id="ebc6b-135">Installieren und Konfigurieren von [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span><span class="sxs-lookup"><span data-stu-id="ebc6b-135">Installing and configuring [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span></span>
    
    <span data-ttu-id="ebc6b-136">Das Konfigurieren von Azure AD Verbinden erfordert die Anmeldeinformationen (Benutzername und Kennwort) eines Azure AD-Administratorkontos und eines AD DS-Unternehmensadministratorkontos.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-136">Configuring Azure AD Connect requires the credentials (user name and password) of an Azure AD administrator account and a AD DS enterprise administrator account.</span></span> <span data-ttu-id="ebc6b-137">Azure AD Verbinden wird sofort und kontinuierlich ausgeführt, um die lokale AD DS-Gesamtstruktur mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-137">Azure AD Connect runs immediately and on an ongoing basis to synchronize the on-premises AD DS forest to Microsoft 365.</span></span>
    
<span data-ttu-id="ebc6b-138">Bevor Sie diese Lösung in der Produktion bereitstellen, können Sie die Anweisungen unter [Die](simulated-ent-base-configuration-microsoft-365-enterprise.md) simulierte Unternehmensbasiskonfiguration verwenden, um diese Konfiguration als Nachweis für das Konzept, für Demonstrationen oder für Experimente zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-138">Before you deploy this solution in production, you can use the instructions in [The simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to set this configuration up as a proof of concept, for demonstrations, or for experimentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ebc6b-139">Wenn die Konfiguration von Azure AD Connect abgeschlossen ist, werden die Anmeldeinformationen für das AD DS-Unternehmensadministratorkonto nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-139">When Azure AD Connect configuration completes, it does not save the AD DS enterprise administrator account credentials.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ebc6b-140">Diese Lösung beschreibt die Synchronisierung einer einzelnen AD DS-Gesamtstruktur mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-140">This solution describes synchronizing a single AD DS forest to Microsoft 365.</span></span> <span data-ttu-id="ebc6b-141">Die in diesem Artikel behandelte Topologie stellt nur eine Möglichkeit zum Implementieren dieser Lösung dar.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-141">The topology discussed in this article represents only one way to implement this solution.</span></span> <span data-ttu-id="ebc6b-142">Die Topologie Ihrer Organisation kann sich je nach ihren eindeutigen Netzwerkanforderungen und Sicherheitsüberlegungen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-142">Your organization's topology might differ based on your unique network requirements and security considerations.</span></span> 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a><span data-ttu-id="ebc6b-143">Planen des Hostings eines Verzeichnissynchronisierungsservers für Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="ebc6b-143">Plan for hosting a directory sync server for Microsoft 365 in Azure</span></span>
<span data-ttu-id="ebc6b-144"><a name="PlanningVirtual"> </a></span><span class="sxs-lookup"><span data-stu-id="ebc6b-144"><a name="PlanningVirtual"> </a></span></span>

### <a name="prerequisites"></a><span data-ttu-id="ebc6b-145">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ebc6b-145">Prerequisites</span></span>

<span data-ttu-id="ebc6b-146">Lesen Sie die folgenden Voraussetzungen für diese Lösung, ehe Sie mit diesem Vorgang beginnen:</span><span class="sxs-lookup"><span data-stu-id="ebc6b-146">Before you begin, review the following prerequisites for this solution:</span></span>
  
- <span data-ttu-id="ebc6b-147">Überprüfen Sie die dazugehörigen Planungsinhalte in [Planen des virtuellen Azure-Netzwerks](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span><span class="sxs-lookup"><span data-stu-id="ebc6b-147">Review the related planning content in [Plan your Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span></span>
    
- <span data-ttu-id="ebc6b-148">Stellen Sie sicher, dass alle [Voraussetzungen](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) für die Konfiguration des virtuellen Azure-Netzwerks erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-148">Ensure that you meet all [Prerequisites](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) for configuring the Azure virtual network.</span></span>
    
- <span data-ttu-id="ebc6b-149">Verfügen Sie Microsoft 365 Abonnement, das das Active Directory-Integrationsfeature enthält.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-149">Have a Microsoft 365 subscription that includes the Active Directory integration feature.</span></span> <span data-ttu-id="ebc6b-150">Weitere Informationen zu Microsoft 365 Abonnements finden Sie auf der [Seite Microsoft 365 Abonnements](https://products.office.com/compare-all-microsoft-office-products?tab=2).</span><span class="sxs-lookup"><span data-stu-id="ebc6b-150">For information about Microsoft 365 subscriptions, go to the [Microsoft 365 subscription page](https://products.office.com/compare-all-microsoft-office-products?tab=2).</span></span>
    
- <span data-ttu-id="ebc6b-151">Bereitstellen eines virtuellen Azure-Computers, auf dem Azure AD Verbinden, um Ihre lokale AD DS-Gesamtstruktur mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-151">Provision one Azure Virtual Machine that runs Azure AD Connect to synchronize your on-premises AD DS forest with Microsoft 365.</span></span>
    
    <span data-ttu-id="ebc6b-152">Sie benötigen die Anmeldeinformationen (Namen und Kennwörter) für das AD DS-Unternehmensadministratorkonto und ein Azure AD-Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-152">You must have the credentials (names and passwords) for a AD DS enterprise administrator account and an Azure AD Administrator account.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="ebc6b-153">Entwurfsannahmen für die Lösungsarchitektur</span><span class="sxs-lookup"><span data-stu-id="ebc6b-153">Solution architecture design assumptions</span></span>

<span data-ttu-id="ebc6b-154">In der folgenden Liste werden die für diese Lösung getroffenen Design-Entscheidungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-154">The following list describes the design choices made for this solution.</span></span>
  
- <span data-ttu-id="ebc6b-p112">Diese Lösung verwendet ein einzelnes virtuelles Azure-Netzwerk mit einer einzelnen Standort-zu-Standort-VPN-Verbindung. Das virtuelle Azure-Netzwerk hostet ein einzelnes Subnetz, das einen Server, den Verzeichnissynchronisierungsserver mit ausgeführtem Azure AD Connect, enthält.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p112">This solution uses a single Azure virtual network with a site-to-site VPN connection. The Azure virtual network hosts a single subnet that has one server, the directory sync server that is running Azure AD Connect.</span></span> 
    
- <span data-ttu-id="ebc6b-157">Im lokalen Netzwerk sind ein Domänencontroller und DNS-Server vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-157">On the on-premises network, a domain controller and DNS servers exist.</span></span>
    
- <span data-ttu-id="ebc6b-p113">Azure AD Connect wird für die Kennworthashsynchronisierung anstatt für das einmalige Anmelden verwendet. Sie müssen keine Infrastruktur für Active Directory-Verbunddienste (AD FS) bereitstellen. Weitere Informationen zu Optionen für einmaliges Anmelden und Kennworthashsynchronisierung finden Sie unter [Wählen der richtigen Authentifizierungsmethode für Ihre Azure Active Directory-Hybrididentitätslösung](/azure/active-directory/hybrid/choose-ad-authn).</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p113">Azure AD Connect performs password hash synchronization instead of single sign-on. You do not have to deploy an Active Directory Federation Services (AD FS) infrastructure. To learn more about password hash synchronization and single sign-on options, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](/azure/active-directory/hybrid/choose-ad-authn).</span></span>
    
<span data-ttu-id="ebc6b-p114">Es folgen einige weitere Entwurfsoptionen, die Sie berücksichtigen sollten, wenn Sie diese Lösung in Ihrer Umgebung bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p114">There are additional design choices that you might consider when you deploy this solution in your environment. These include the following:</span></span>
  
- <span data-ttu-id="ebc6b-163">Wenn es in einem vorhandenen virtuellen Azure-Netzwerk DNS-Server gibt, bestimmen Sie, ob der Verzeichnissynchronisierungsserver diese für die Namensauflösung anstelle der DNS-Server im lokalen Netzwerk verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-163">If there are existing DNS servers in an existing Azure virtual network, determine whether you want your directory sync server to use them for name resolution instead of DNS servers on the on-premises network.</span></span>
    
- <span data-ttu-id="ebc6b-p115">Wenn es Domänencontroller in einem vorhandenen virtuellen Azure-Netzwerk gibt, bestimmen Sie, ob die Konfiguration von Active Directory-Standorten und-Diensten ggf. eine bessere Option für Sie ist. Der Verzeichnissynchronisierungsserver kann die Domänencontroller im virtuellen Azure-Netzwerk anstatt die Domänencontroller im lokalen Netzwerk abfragen, um nach Änderungen an Benutzerkonten und Kennwörtern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p115">If there are domain controllers in an existing Azure virtual network, determine whether configuring Active Directory Sites and Services may be a better option for you. The directory sync server can query the domain controllers in the Azure virtual network for changes in accounts and passwords instead of domain controllers on the on-premises network.</span></span>
    
## <a name="deployment-roadmap"></a><span data-ttu-id="ebc6b-166">Fahrplan für die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="ebc6b-166">Deployment roadmap</span></span>

<span data-ttu-id="ebc6b-167">Das Bereitstellen von Azure AD Connect auf einem virtuellen Computer in Azure umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="ebc6b-167">Deploying Azure AD Connect on a virtual machine in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="ebc6b-168">Phase 1: Erstellen und Konfigurieren des virtuellen Azure-Netzwerks</span><span class="sxs-lookup"><span data-stu-id="ebc6b-168">Phase 1: Create and configure the Azure virtual network</span></span>
    
- <span data-ttu-id="ebc6b-169">Phase 2: Erstellen und Konfigurieren des virtuellen Azure-Computers</span><span class="sxs-lookup"><span data-stu-id="ebc6b-169">Phase 2: Create and configure the Azure virtual machine</span></span>
    
- <span data-ttu-id="ebc6b-170">Phase 3: Installieren und Konfigurieren von Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="ebc6b-170">Phase 3: Install and configure Azure AD Connect</span></span>
    
<span data-ttu-id="ebc6b-171">Nach der Bereitstellung müssen Sie auch Speicherorte und Lizenzen für die neuen Benutzerkonten in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-171">After deployment, you must also assign locations and licenses for the new user accounts in Microsoft 365.</span></span>


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a><span data-ttu-id="ebc6b-172">Phase 1: Erstellen und Konfigurieren des virtuellen Azure-Netzwerks</span><span class="sxs-lookup"><span data-stu-id="ebc6b-172">Phase 1: Create and configure the Azure virtual network</span></span>

<span data-ttu-id="ebc6b-173">Zum Erstellen und Konfigurieren des virtuellen Azure-Netzwerks durchlaufen Sie [Phase 1: Vorbereitung Ihres lokalen Netzwerks](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) und [Phase 2: Erstellen des standortübergreifenden virtuellen Azure-Netzwerks](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) im Fahrplan für die Bereitstellung von [Verbinden eines lokalen Netzwerks mit einem virtuellen Microsoft Azure-Netzwerk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="ebc6b-173">To create and configure the Azure virtual network, complete [Phase 1: Prepare your on-premises network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) and [Phase 2: Create the cross-premises virtual network in Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) in the deployment roadmap of [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
  
<span data-ttu-id="ebc6b-174">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-174">This is your resulting configuration.</span></span>
  
![Phase 1 des Verzeichnissynchronisierungsservers für Microsoft 365 in Azure gehostet](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
<span data-ttu-id="ebc6b-176">Diese Abbildung zeigt ein lokales Netzwerk, das über eine Standort-zu-Standort-VPN- oder ExpressRoute-Verbindung mit einem virtuellen Azure-Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-176">This figure shows an on-premises network connected to an Azure virtual network through a site-to-site VPN or ExpressRoute connection.</span></span>
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a><span data-ttu-id="ebc6b-177">Phase 2: Erstellen und Konfigurieren des virtuellen Azure-Computers</span><span class="sxs-lookup"><span data-stu-id="ebc6b-177">Phase 2: Create and configure the Azure virtual machine</span></span>

<span data-ttu-id="ebc6b-p116">Erstellen Sie den virtuellen Computer in Azure anhand der Anweisungen unter [Erstellen Ihres ersten virtuellen Windows-Computers im Azure-Portal](https://go.microsoft.com/fwlink/p/?LinkId=393098). Verwenden Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p116">Create the virtual machine in Azure using the instructions [Create your first Windows virtual machine in the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098). Use the following settings:</span></span>
  
- <span data-ttu-id="ebc6b-p117">Wählen Sie im Bereich **Grundlagen** das gleiche Abonnement, den gleichen Ort und die gleiche Ressourcengruppe als virtuelles Netzwerk aus. Bewahren Sie den Benutzernamen und das Kennwort an einem sicheren Ort auf. Sie benötigen diese Informationen später für die Verbindung mit dem virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p117">On the **Basics** pane, select the same subscription, location, and resource group as your virtual network. Record the user name and password in a secure location. You will need these later to connect to the virtual machine.</span></span>
    
- <span data-ttu-id="ebc6b-183">Wählen Sie im Bereich zum Auswählen einer **Größe** die Größe **A2 Standard** aus.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-183">On the **Choose a size** pane, choose the **A2 Standard** size.</span></span>
    
- <span data-ttu-id="ebc6b-p118">Wählen Sie im Bereich **Einstellungen** im Abschnitt **Speicher** den Speichertyp **Standard** aus. Wählen Sie im Abschnitt **Netzwerk** den Namen des virtuellen Netzwerks und das Subnetz zum Hosten des Verzeichnissynchronisierungsservers (nicht das Gateway-Subnetz). Alle anderen Einstellungen bleiben bei ihren Standardwerten.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p118">On the **Settings** pane, in the **Storage** section, select the **Standard** storage type. In the **Network** section, select the name of your virtual network and the subnet for hosting the directory sync server (not the GatewaySubnet). Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="ebc6b-187">Stellen Sie sicher, dass der Verzeichnissynchronisierungsserver DNS ordnungsgemäß verwendet. Überprüfen Sie dazu Ihr internes DNS, und vergewissern Sie sich, dass für den virtuellen Computer ein Adresseintrag (A-Datensatz) mit seiner IP-Adresse hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-187">Verify that your directory sync server is using DNS correctly by checking your internal DNS to make sure that an Address (A) record was added for the virtual machine with its IP address.</span></span> 
  
<span data-ttu-id="ebc6b-p119">Befolgen Sie die Anweisungen unter [Herstellen einer Verbindung mit dem virtuellen Computer und Anmelden](/azure/virtual-machines/windows/connect-logon), um über eine Remotedesktopverbindung eine Verbindung mit dem Verzeichnissynchronisierungsserver herzustellen. Fügen Sie den virtuellen Computer nach dem Anmelden der lokalen AD DS-Domäne hinzu.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p119">Use the instructions in [Connect to the virtual machine and sign on](/azure/virtual-machines/windows/connect-logon) to connect to the directory sync server with a Remote Desktop Connection. After signing in, join the virtual machine to the on-premises AD DS domain.</span></span>
  
<span data-ttu-id="ebc6b-p120">Damit Azure AD Connect auf Internetressourcen zugreifen kann, müssen Sie den Verzeichnissynchronisierungsserver für die Verwendung des lokalen Netzwerkproxyservers konfigurieren. Wenden Sie sich für mögliche zusätzlichen Konfigurationsschritte an Ihren Netzwerkadministrator.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p120">For Azure AD Connect to gain access to Internet resources, you must configure the directory sync server to use the on-premises network's proxy server. You should contact your network administrator for any additional configuration steps to perform.</span></span>
  
<span data-ttu-id="ebc6b-192">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-192">This is your resulting configuration.</span></span>
  
![Phase 2 des Verzeichnissynchronisierungsservers für Microsoft 365 in Azure gehostet](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
<span data-ttu-id="ebc6b-194">Diese Abbildung zeigt den virtuellen Computer des Verzeichnissynchronisierungsservers im lokalen virtuellen Azure-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-194">This figure shows the directory sync server virtual machine in the cross-premises Azure virtual network.</span></span>
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a><span data-ttu-id="ebc6b-195">Phase 3: Installieren und Konfigurieren von Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="ebc6b-195">Phase 3: Install and configure Azure AD Connect</span></span>

<span data-ttu-id="ebc6b-196">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="ebc6b-196">Complete the following procedure:</span></span>
  
1. <span data-ttu-id="ebc6b-p121">Stellen Sie mithilfe einer Remotedesktopverbindung mit einem AD DS-Domänenkonto, das über lokale Administratorberechtigungen verfügt, eine Verbindung mit dem Verzeichnissynchronisierungsserver her. Siehe [Herstellen einer Verbindung mit dem virtuellen Computer und Anmelden](/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p121">Connect to the directory sync server using a Remote Desktop Connection with an AD DS domain account that has local administrator privileges. See [Connect to the virtual machine and sign on](/azure/virtual-machines/windows/connect-logon).</span></span>
    
2. <span data-ttu-id="ebc6b-199">Öffnen Sie auf dem Verzeichnissynchronisierungsserver den Artikel Verzeichnissynchronisierung für [Microsoft 365](set-up-directory-synchronization.md) einrichten, und befolgen Sie die Anweisungen für die Verzeichnissynchronisierung mit Kennworthashsynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-199">From the directory sync server, open the [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) article and follow the directions for directory synchronization with password hash synchronization.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="ebc6b-p122">Setup erstellt das Konto **AAD_xxxxxxxxxxxx** in der Organisationseinheit (OU) Lokale Benutzer. Verschieben oder entfernen Sie dieses Konto nicht, da dann die Synchronisierung misslingt.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-p122">Setup creates the **AAD_xxxxxxxxxxxx** account in the Local Users organizational unit (OU). Do not move or remove this account or synchronization will fail.</span></span>
  
<span data-ttu-id="ebc6b-202">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-202">This is your resulting configuration.</span></span>
  
![Phase 3 des Verzeichnissynchronisierungsservers für Microsoft 365 in Azure gehostet](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
<span data-ttu-id="ebc6b-204">Diese Abbildung zeigt den Verzeichnissynchronisierungsserver mit Azure AD Connect im lokalen virtuellen Azure-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-204">This figure shows the directory sync server with Azure AD Connect in the cross-premises Azure virtual network.</span></span>
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a><span data-ttu-id="ebc6b-205">Zuweisen von Speicherorten und Lizenzen zu Benutzern in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ebc6b-205">Assign locations and licenses to users in Microsoft 365</span></span>

<span data-ttu-id="ebc6b-206">Azure AD Verbinden fügt Ihrem Microsoft 365-Abonnement Konten aus dem lokalen AD DS hinzu. Damit sich Benutzer jedoch bei Microsoft 365 anmelden und ihre Dienste nutzen können, müssen die Konten mit einem Standort und Lizenzen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-206">Azure AD Connect adds accounts to your Microsoft 365 subscription from the on-premises AD DS, but in order for users to sign in to Microsoft 365 and use its services, the accounts must be configured with a location and licenses.</span></span> <span data-ttu-id="ebc6b-207">Verwenden Sie die folgenden Schritte, um den Speicherort hinzuzufügen und Lizenzen für die entsprechenden Benutzerkonten zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="ebc6b-207">Use these steps to add the location and activate licenses for the appropriate user accounts:</span></span>
  
1. <span data-ttu-id="ebc6b-208">Melden Sie sich beim [Microsoft 365 Admin Center an,](https://admin.microsoft.com)und klicken Sie dann auf **Admin**.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-208">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com), and then click **Admin**.</span></span>
    
2. <span data-ttu-id="ebc6b-209">Klicken Sie im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-209">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="ebc6b-210">Aktivieren Sie in der Liste der Benutzerkonten das Kontrollkästchen neben dem zu aktivierenden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-210">In the list of user accounts, select the check box next to the user you want to activate.</span></span>
    
4. <span data-ttu-id="ebc6b-211">Klicken Sie auf der Seite für den Benutzer auf **Bearbeiten** für **Produktlizenzen**.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-211">On the page for the user, click **Edit** for **Product licenses**.</span></span>
    
5. <span data-ttu-id="ebc6b-212">Wählen Sie auf der Seite **Produktlizenzen** unter **Speicherort** einen Speicherort für den Benutzer aus, und aktivieren Sie dann die entsprechenden Lizenzen für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-212">On the **Product licenses** page, select a location for the user for **Location**, and then enable the appropriate licenses for the user.</span></span>
    
6. <span data-ttu-id="ebc6b-213">Wenn Sie fertig sind, klicken Sie auf **Speichern**, und klicken Sie dann zweimal auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-213">When complete, click **Save**, and then click **Close** twice.</span></span>
    
7. <span data-ttu-id="ebc6b-214">Kehren Sie zu Schritt 3 zurück, um weitere Benutzer zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-214">Go back to step 3 for additional users.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ebc6b-215">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebc6b-215">See also</span></span>

[<span data-ttu-id="ebc6b-216">Microsoft 365-Lösungs- und Architekturcenter</span><span class="sxs-lookup"><span data-stu-id="ebc6b-216">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)
  
[<span data-ttu-id="ebc6b-217">Verbinden eines lokalen Netzwerks mit einem virtuellen Microsoft Azure-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="ebc6b-217">Connect an on-premises network to a Microsoft Azure virtual network</span></span>](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[<span data-ttu-id="ebc6b-218">Herunterladen von Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="ebc6b-218">Download Azure AD Connect</span></span>](https://www.microsoft.com/download/details.aspx?id=47594)
  
[<span data-ttu-id="ebc6b-219">Einrichten der Verzeichnissynchronisierung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ebc6b-219">Set up directory synchronization for Microsoft 365</span></span>](set-up-directory-synchronization.md)
