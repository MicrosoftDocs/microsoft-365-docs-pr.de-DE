---
title: Abonnements, Lizenzen, Konten und Mandanten für Microsoft-Cloud-Angebote
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/25/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365initiative-coredeploy
f1.keywords:
- CSH
ms.assetid: c720cffc-f9b5-4f43-9100-422f86a1027c
ms.custom:
- seo-marvel-apr2020
- Ent_Architecture
description: Lernen Sie die Beziehungen von Organisationen, Abonnements, Lizenzen, Benutzerkonten und Mandanten über die Microsoft-Cloudangebote hinweg kennen.
ms.openlocfilehash: e79189ac4c95f735597352d115038e994710852b
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357958"
---
# <a name="subscriptions-licenses-accounts-and-tenants-for-microsofts-cloud-offerings"></a><span data-ttu-id="dcef4-103">Abonnements, Lizenzen, Konten und Mandanten für Microsoft-Cloud-Angebote</span><span class="sxs-lookup"><span data-stu-id="dcef4-103">Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings</span></span>

<span data-ttu-id="dcef4-104">Microsoft stellt eine Hierarchie von Organisationen, Abonnements, Lizenzen und Benutzerkonten für die konsistente Verwendung von Identitäten und die Abrechnung über seine Cloudangebote hinweg bereit:</span><span class="sxs-lookup"><span data-stu-id="dcef4-104">Microsoft provides a hierarchy of organizations, subscriptions, licenses, and user accounts for consistent use of identities and billing across its cloud offerings:</span></span>
  
- <span data-ttu-id="dcef4-105">Microsoft 365 und Microsoft Office 365</span><span class="sxs-lookup"><span data-stu-id="dcef4-105">Microsoft 365 and Microsoft Office 365</span></span>
- <span data-ttu-id="dcef4-106">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="dcef4-106">Microsoft Azure</span></span>
- <span data-ttu-id="dcef4-107">Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="dcef4-107">Microsoft Dynamics 365</span></span>

## <a name="elements-of-the-hierarchy"></a><span data-ttu-id="dcef4-108">Elemente der Hierarchie</span><span class="sxs-lookup"><span data-stu-id="dcef4-108">Elements of the hierarchy</span></span>

<span data-ttu-id="dcef4-109">Dies sind die Elemente der Hierarchie:</span><span class="sxs-lookup"><span data-stu-id="dcef4-109">Here are the elements of the hierarchy:</span></span>
  
### <a name="organization"></a><span data-ttu-id="dcef4-110">Organization (Organisation)</span><span class="sxs-lookup"><span data-stu-id="dcef4-110">Organization</span></span>

<span data-ttu-id="dcef4-p101">Eine Organisation stellt eine Wirtschaftseinheit dar, die Microsoft-Cloudangebote verwendet und in der Regel von einem oder mehreren öffentlichen DNS-Domänennamen (Domain Name System) identifiziert wird, z. B. contoso.com. Die Organisation ist ein Container für Abonnements.</span><span class="sxs-lookup"><span data-stu-id="dcef4-p101">An organization represents a business entity that is using Microsoft cloud offerings, typically identified by one or more public Domain Name System (DNS) domain names, such as contoso.com. The organization is a container for subscriptions.</span></span>
  
### <a name="subscriptions"></a><span data-ttu-id="dcef4-113">Abonnements</span><span class="sxs-lookup"><span data-stu-id="dcef4-113">Subscriptions</span></span>

<span data-ttu-id="dcef4-114">Ein Abonnement ist eine Vereinbarung mit Microsoft zur Verwendung einer oder mehrerer Cloudplattformen oder -dienste, für die basierend auf einer Lizenzgebühr pro Benutzer oder einem cloudbasierten Ressourcenverbrauch Kosten anfallen.</span><span class="sxs-lookup"><span data-stu-id="dcef4-114">A subscription is an agreement with Microsoft to use one or more Microsoft cloud platforms or services, for which charges accrue based on either a per-user license fee or on cloud-based resource consumption.</span></span> 

- <span data-ttu-id="dcef4-115">Bei den SaaS-basierten (Software-as-a-Service) Cloudangeboten von Microsoft (Microsoft 365 und Dynamics 365) werden Lizenzgebühren pro Benutzer abgerechnet.</span><span class="sxs-lookup"><span data-stu-id="dcef4-115">Microsoft's Software as a Service (SaaS)-based cloud offerings (Microsoft 365 and Dynamics 365) charge per-user license fees.</span></span> 
- <span data-ttu-id="dcef4-116">Bei den PaaS- und IaaS-Cloudangeboten (Platform-as-a-Service; Infrastructure-as-a-Service) von Microsoft (Azure) wird basierend auf dem Ressourcenverbrauch in der Cloud abgerechnet.</span><span class="sxs-lookup"><span data-stu-id="dcef4-116">Microsoft's Platform as a Service (PaaS) and Infrastructure as a Service (IaaS) cloud offerings (Azure) charge based on cloud resource consumption.</span></span>
 
<span data-ttu-id="dcef4-p102">Sie können auch ein Testabonnement verwenden, das Abonnement läuft jedoch nach einem bestimmten Zeitraum oder einem bestimmten Betrag von Verbrauchsgebühren ab. Sie können ein Testabonnement in ein kostenpflichtiges Abonnement umwandeln.</span><span class="sxs-lookup"><span data-stu-id="dcef4-p102">You can also use a trial subscription, but the subscription expires after a specific amount of time or consumption charges. You can convert a trial subscription to a paid subscription.</span></span>
  
<span data-ttu-id="dcef4-119">Organisationen können mehrere Abonnements für die Cloudangebote von Microsoft haben.</span><span class="sxs-lookup"><span data-stu-id="dcef4-119">Organizations can have multiple subscriptions for Microsoft's cloud offerings.</span></span> <span data-ttu-id="dcef4-120">Abbildung 1 zeigt eine einzelne Organisation mit mehreren Microsoft 365-Abonnements, einem Dynamics 365-Abonnement und mehreren Azure-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="dcef4-120">Figure 1 shows a single organization that has multiple Microsoft 365 subscriptions, a Dynamics 365 subscription, and multiple Azure subscriptions.</span></span>

<span data-ttu-id="dcef4-121">**Abbildung 1: Beispiel für eine Organisation mit mehreren Abonnements**</span><span class="sxs-lookup"><span data-stu-id="dcef4-121">**Figure 1: Example of multiple subscriptions for an organization**</span></span>

![Eine Beispielorganisation mit mehreren Abonnements für Microsoft Cloud-Angebote.](../media/Subscriptions/Subscriptions-Fig1.png)
  
### <a name="licenses"></a><span data-ttu-id="dcef4-123">Lizenzen</span><span class="sxs-lookup"><span data-stu-id="dcef4-123">Licenses</span></span>

<span data-ttu-id="dcef4-124">Bei den SaaS-Cloudangeboten von Microsoft ermöglicht eine Lizenz einem bestimmten Benutzerkonto, die Dienste des Cloudangebots zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="dcef4-124">For Microsoft's SaaS cloud offerings, a license allows a specific user account to use the services of the cloud offering.</span></span> <span data-ttu-id="dcef4-125">Ihnen wird eine feste monatliche Gebühr als Teils Ihres Abonnements in Rechnung gestellt.</span><span class="sxs-lookup"><span data-stu-id="dcef4-125">You are charged a fixed monthly fee as part of your subscription.</span></span> <span data-ttu-id="dcef4-126">Administratoren weisen Lizenzen einzelnen Benutzerkonten in dem Abonnement zu.</span><span class="sxs-lookup"><span data-stu-id="dcef4-126">Administrators assign licenses to individual user accounts in the subscription.</span></span> <span data-ttu-id="dcef4-127">Für das Beispiel in Abbildung 2 verfügt die Contoso Corporation über ein Microsoft 365 E5-Abonnement mit 100 Lizenzen, mit dem bis zu 100 einzelne Benutzerkonten die Features und Dienste von Microsoft 365 E5 nutzen können.</span><span class="sxs-lookup"><span data-stu-id="dcef4-127">For the example in Figure 2, the Contoso Corporation has a Microsoft 365 E5 subscription with 100 licenses, which allows to up to 100 individual user accounts to use Microsoft 365 E5 features and services.</span></span>
  
<span data-ttu-id="dcef4-128">**Abbildung 2: Lizenzen innerhalb der SaaS-basierten Abonnements für eine Organisation**</span><span class="sxs-lookup"><span data-stu-id="dcef4-128">**Figure 2: Licenses within the SaaS-based subscriptions for an organization**</span></span>

![Ein Beispiel für mehrere Lizenzen innerhalb von Abonnements für auf SaaS-basierende Microsoft-Cloudangebote.](../media/Subscriptions/Subscriptions-Fig2.png)
  
<span data-ttu-id="dcef4-130">Bei PaaS-basierten Azure-Clouddiensten sind Softwarelizenzen in den Dienstpreis integriert.</span><span class="sxs-lookup"><span data-stu-id="dcef4-130">For Azure PaaS-based cloud services, software licenses are built into the service pricing.</span></span>
  
<span data-ttu-id="dcef4-p105">Bei IaaS-basierten virtuellen Azure-Computern sind möglicherweise zusätzliche Lizenzen zur Nutzung der Software oder der Anwendung erforderlich, die auf einem virtuellen Computerabbild installiert ist. Einige virtuelle Computerabbilder weisen lizenzierte Versionen der installierten Software auf, und die Kosten sind in dem Minutenpreis für den Server enthalten. Beispiele hierfür sind die virtuellen Computerabbilder für SQL Server 2014 und SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="dcef4-p105">For Azure IaaS-based virtual machines, additional licenses to use the software or application installed on a virtual machine image might be required. Some virtual machine images have licensed versions of software installed and the cost is included in the per-minute rate for the server. Examples are the virtual machine images for SQL Server 2014 and SQL Server 2016.</span></span> 
  
<span data-ttu-id="dcef4-p106">Einige virtuelle Computerabbilder verfügen über Testversionen von installierten Anwendungen benötigen zusätzliche Softwareanwendungslizenzen für die Verwendung über den Testzeitraum hinaus. Das virtuelle Computerabbild der Testversion von SharePoint Server 2016 enthält beispielsweise eine Testversion von SharePoint Server 2016 (vorinstalliert). Um SharePoint Server 2016 nach dem Ablaufdatum der Testversion weiter zu verwenden, müssen Sie eine Lizenz für SharePoint Server 2016 und Clientlizenzen von Microsoft erwerben. Diese Gebühren fallen unabhängig von dem Azure-Abonnement an, und der Minutenpreis für das Ausführen des virtuellen Computers tritt weiterhin zu.</span><span class="sxs-lookup"><span data-stu-id="dcef4-p106">Some virtual machine images have trial versions of applications installed and need additional software application licenses for use beyond the trial period. For example, the SharePoint Server 2016 Trial virtual machine image includes a trial version of SharePoint Server 2016 pre-installed. To continue using SharePoint Server 2016 after the trial expiration date, you must purchase a SharePoint Server 2016 license and client licenses from Microsoft. These charges are separate from the Azure subscription and the per-minute rate to run the virtual machine still applies.</span></span>
  
### <a name="user-accounts"></a><span data-ttu-id="dcef4-138">Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="dcef4-138">User accounts</span></span>

<span data-ttu-id="dcef4-139">Benutzerkonten für alle Microsoft-Cloudangebote werden in einem Azure AD-Mandanten (Azure AD) gespeichert, der Benutzerkonten und -gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="dcef4-139">User accounts for all of Microsoft's cloud offerings are stored in an Azure Active Directory (Azure AD) tenant, which contains user accounts and groups.</span></span> <span data-ttu-id="dcef4-140">Ein Azure AD-Mandant kann mit Ihren vorhandenen Active Directory Domain Services (AD DS)-Konten mithilfe von Azure AD Connect, einem Windows Server-basierten Dienst, synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="dcef4-140">An Azure AD tenant can be synchronized with your existing Active Directory Domain Services (AD DS) accounts using Azure AD Connect, a Windows server-based service.</span></span> <span data-ttu-id="dcef4-141">Dies wird als Verzeichnissynchronisierung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dcef4-141">This is known as directory synchronization.</span></span>
  
<span data-ttu-id="dcef4-142">Abbildung 3 zeigt ein Beispiel für mehrere Abonnements einer Organisation, die einen allgemeinen Azure AD-Mandanten verwendet, der die Konten der Organisation enthält.</span><span class="sxs-lookup"><span data-stu-id="dcef4-142">Figure 3 shows an example of multiple subscriptions of an organization using a common Azure AD tenant that contains the organization's accounts.</span></span>
  
<span data-ttu-id="dcef4-143">**Abbildung 3: Mehrere Abonnements einer Organisation, die den gleichen Azure AD-Mandanten verwenden**</span><span class="sxs-lookup"><span data-stu-id="dcef4-143">**Figure 3: Multiple subscriptions of an organization that use the same Azure AD tenant**</span></span>

![Eine Beispielorganisation mit mehreren Abonnements, die alle den gleichen Azure AD-Mandanten verwenden.](../media/Subscriptions/Subscriptions-Fig3.png)
  
### <a name="tenants"></a><span data-ttu-id="dcef4-145">Mandanten</span><span class="sxs-lookup"><span data-stu-id="dcef4-145">Tenants</span></span>

<span data-ttu-id="dcef4-146">Bei SaaS-Cloudangeboten ist der Mandant die regionale Stelle, an der sich die Server befinden, die Clouddienste bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dcef4-146">For SaaS cloud offerings, the tenant is the regional location that houses the servers providing cloud services.</span></span> <span data-ttu-id="dcef4-147">Die Contoso Corporation hat beispielsweise Europa als Region zum Hosten ihrer Microsoft 365-, EMS- und Dynamics 365-Mandanten für die 15.000 Mitarbeiter in der Pariser Zentrale festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dcef4-147">For example, the Contoso Corporation chose the European region to host its Microsoft 365, EMS, and Dynamics 365 tenants for the 15,000 workers in their Paris headquarters.</span></span>
  
<span data-ttu-id="dcef4-p109">Azure PaaS-Dienste und in Azure IaaS gehostete VM-basierte Arbeitslasten können Mandanten in einem beliebigen Azure-Rechenzentrum auf der ganzen Welt haben. Sie geben das Azure-Rechenzentrum an, das als Standort bezeichnet wird, wenn Sie die Azure PaaS-App oder den Dienst bzw. das Element einer IaaS-IT-Arbeitslast erstellen.</span><span class="sxs-lookup"><span data-stu-id="dcef4-p109">Azure PaaS services and virtual machine-based workloads hosted in Azure IaaS can have tenancy in any Azure datacenter across the world. You specify the Azure datacenter, known as the location, when you create the Azure PaaS app or service or element of an IaaS workload.</span></span>
  
<span data-ttu-id="dcef4-150">Bei einem Azure AD-Mandanten handelt es sich um eine bestimmte Instanz von Azure AD, die Konten und Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="dcef4-150">An Azure AD tenant is a specific instance of Azure AD containing accounts and groups.</span></span> <span data-ttu-id="dcef4-151">Kostenpflichtige oder Testabonnements von Microsoft 365 oder Dynamics 365 enthalten einen kostenlosen Azure AD-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="dcef4-151">Paid or trial subscriptions of Microsoft 365 or Dynamics 365 include a free Azure AD tenant.</span></span> <span data-ttu-id="dcef4-152">Dieser Azure AD-Mandant enthält keine anderen Azure-Dienste und ist nicht das gleiche wie ein Azure-Testabonnement oder ein kostenpflichtiges Azure-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="dcef4-152">This Azure AD tenant does not include other Azure services and is not the same as an Azure trial or paid subscription.</span></span>
  
### <a name="summary-of-the-hierarchy"></a><span data-ttu-id="dcef4-153">Zusammenfassung der Hierarchie</span><span class="sxs-lookup"><span data-stu-id="dcef4-153">Summary of the hierarchy</span></span>

<span data-ttu-id="dcef4-154">Es folgt eine kurze Wiederholung:</span><span class="sxs-lookup"><span data-stu-id="dcef4-154">Here is a quick recap:</span></span>
  
- <span data-ttu-id="dcef4-155">Eine Organisation kann mehrere Abonnements haben.</span><span class="sxs-lookup"><span data-stu-id="dcef4-155">An organization can have multiple subscriptions</span></span>
    
  - <span data-ttu-id="dcef4-156">Ein Abonnement kann mehrere Lizenzen haben.</span><span class="sxs-lookup"><span data-stu-id="dcef4-156">A subscription can have multiple licenses</span></span>
    
  - <span data-ttu-id="dcef4-157">Lizenzen können einzelnen Benutzerkonten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="dcef4-157">Licenses can be assigned to individual user accounts</span></span>
    
  - <span data-ttu-id="dcef4-158">Benutzerkonten werden in einem Azure AD-Mandanten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dcef4-158">User accounts are stored in an Azure AD tenant</span></span>
    
<span data-ttu-id="dcef4-159">Im Folgenden finden Sie ein Beispiel für die Beziehung von Organisationen, Abonnements, Lizenzen und Benutzerkonten:</span><span class="sxs-lookup"><span data-stu-id="dcef4-159">Here is an example of the relationship of organizations, subscriptions, licenses, and user accounts:</span></span>
  
- <span data-ttu-id="dcef4-160">Eine durch ihre öffentlichen Domänennamen identifizierte Organisation.</span><span class="sxs-lookup"><span data-stu-id="dcef4-160">An organization identified by its public domain name.</span></span>
    
  - <span data-ttu-id="dcef4-161">Ein Microsoft 365 E3-Abonnement mit Benutzerlizenzen.</span><span class="sxs-lookup"><span data-stu-id="dcef4-161">A Microsoft 365 E3 subscription with user licenses.</span></span>
    
    <span data-ttu-id="dcef4-162">Ein Microsoft 365 E5-Abonnement mit Benutzerlizenzen.</span><span class="sxs-lookup"><span data-stu-id="dcef4-162">A Microsoft 365 E5 subscription with user licenses.</span></span>
    
    <span data-ttu-id="dcef4-163">Ein Dynamics 365-Abonnement mit Benutzerlizenzen.</span><span class="sxs-lookup"><span data-stu-id="dcef4-163">A Dynamics 365 subscription with user licenses.</span></span>
    
    <span data-ttu-id="dcef4-164">Mehrere Azure-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="dcef4-164">Multiple Azure subscriptions.</span></span>
    
  - <span data-ttu-id="dcef4-165">Die Benutzerkonten der Organisation in einem gemeinsamen Azure AD-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="dcef4-165">The organization's user accounts in a common Azure AD tenant.</span></span>
    
<span data-ttu-id="dcef4-166">Mehrere Abonnements für Cloudangebote von Microsoft können denselben Azure AD-Mandanten verwenden, der als gemeinsamer Identitätsanbieter fungiert.</span><span class="sxs-lookup"><span data-stu-id="dcef4-166">Multiple Microsoft cloud offering subscriptions can use the same Azure AD tenant that acts as a common identity provider.</span></span> <span data-ttu-id="dcef4-167">Ein zentraler Azure AD-Mandant, der die synchronisierten Konten Ihrer lokalen AD DS enthält, stellt eine cloudbasierte IDaaS (Identity-as-a-Service) für Ihre Organisation bereit.</span><span class="sxs-lookup"><span data-stu-id="dcef4-167">A central Azure AD tenant that contains the synchronized accounts of your on-premises AD DS provides cloud-based Identity as a Service (IDaaS) for your organization.</span></span> 
  
<span data-ttu-id="dcef4-168">**Abbildung 4: Synchronisierte lokale Konten und IDaaS für eine Organisation**</span><span class="sxs-lookup"><span data-stu-id="dcef4-168">**Figure 4: Synchronized on-premises accounts and IDaaS for an organization**</span></span>

![IDaaS (Identity as a Service) für Ihre Organisation.](../media/Subscriptions/Subscriptions-Fig4.png)
  
<span data-ttu-id="dcef4-p112">In Abbildung 4 wird gezeigt, wie ein gemeinsamer Azure AD-Mandant von Microsoft-SaaS-Cloudangeboten, Azure PaaS-Apps und virtuellen Computern in Azure IaaS verwendet wird, die Azure AD-Domänendienste verwenden. Die lokale AD DS-Gesamtstruktur wird mithilfe von Azure AD Connect mit dem Azure AD-Mandanten synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="dcef4-p112">Figure 4 shows how a common Azure AD tenant is used by Microsoft's SaaS cloud offerings, Azure PaaS apps, and virtual machines in Azure IaaS that use Azure AD Domain Services. Azure AD Connect synchronizes the on-premises AD DS forest with the Azure AD tenant.</span></span>
  
## <a name="combining-subscriptions-for-multiple-microsoft-cloud-offerings"></a><span data-ttu-id="dcef4-172">Kombinieren von Abonnements für mehrere Microsoft-Cloudangebote</span><span class="sxs-lookup"><span data-stu-id="dcef4-172">Combining subscriptions for multiple Microsoft cloud offerings</span></span>

<span data-ttu-id="dcef4-173">Die folgende Tabelle beschreibt, wie Sie mehrere Microsoft-Cloudangebote basierend auf dem Vorhandensein eines Abonnement für einen Typ von Cloudangebot (die Bezeichnungen laufen in der ersten Spalte nach unten) und dem Hinzufügen eines Abonnements für ein anderes Cloudangebot (von links nach rechts) kombinieren können.</span><span class="sxs-lookup"><span data-stu-id="dcef4-173">The following table describes how you can combine multiple Microsoft cloud offerings based on already having a subscription for one type of cloud offering (the labels going down the first column) and adding a subscription for a different cloud offering (going across the columns).</span></span>
  
||<span data-ttu-id="dcef4-174">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="dcef4-174">**Microsoft 365**</span></span>|<span data-ttu-id="dcef4-175">**Azure**</span><span class="sxs-lookup"><span data-stu-id="dcef4-175">**Azure**</span></span>|<span data-ttu-id="dcef4-176">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="dcef4-176">**Dynamics 365**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dcef4-177">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="dcef4-177">**Microsoft 365**</span></span> <br/> |<span data-ttu-id="dcef4-178">NA</span><span class="sxs-lookup"><span data-stu-id="dcef4-178">NA</span></span>  <br/> |<span data-ttu-id="dcef4-179">Sie fügen ein Azure-Abonnement zu Ihrer Organisation aus dem Azure-Portal hinzu.</span><span class="sxs-lookup"><span data-stu-id="dcef4-179">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="dcef4-180">Sie fügen ein Dynamics 365-Abonnement zu Ihrer Organisation aus dem Microsoft 365 Admin Center hinzu.</span><span class="sxs-lookup"><span data-stu-id="dcef4-180">You add a Dynamics 365 subscription to your organization from the Microsoft 365 admin center.</span></span>  <br/> |
|<span data-ttu-id="dcef4-181">**Azure**</span><span class="sxs-lookup"><span data-stu-id="dcef4-181">**Azure**</span></span> <br/> |<span data-ttu-id="dcef4-182">Sie fügen ein Microsoft 365-Abonnement zu Ihrer Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="dcef4-182">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="dcef4-183">NA</span><span class="sxs-lookup"><span data-stu-id="dcef4-183">NA</span></span>  <br/> |<span data-ttu-id="dcef4-184">Sie fügen ein Dynamics 365-Abonnement zu Ihrer Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="dcef4-184">You add a Dynamics 365 subscription to your organization.</span></span>  <br/> |
|<span data-ttu-id="dcef4-185">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="dcef4-185">**Dynamics 365**</span></span> <br/> |<span data-ttu-id="dcef4-186">Sie fügen ein Microsoft 365-Abonnement zu Ihrer Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="dcef4-186">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="dcef4-187">Sie fügen ein Azure-Abonnement zu Ihrer Organisation aus dem Azure-Portal hinzu.</span><span class="sxs-lookup"><span data-stu-id="dcef4-187">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="dcef4-188">NA</span><span class="sxs-lookup"><span data-stu-id="dcef4-188">NA</span></span>  <br/> |
   
<span data-ttu-id="dcef4-189">Eine einfache Möglichkeit zum Hinzufügen von Abonnements zu Ihrer Organisation für Microsoft SaaS-basierte Dienste erfolgt über das Admin Center:</span><span class="sxs-lookup"><span data-stu-id="dcef4-189">An easy way to add subscriptions to your organization for Microsoft SaaS-based services is through the admin center:</span></span>
  
1. <span data-ttu-id="dcef4-190">Melden Sie sich mit Ihrem globalen Administratorkonto beim Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) an.</span><span class="sxs-lookup"><span data-stu-id="dcef4-190">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with your global administrator account.</span></span>
    
2. <span data-ttu-id="dcef4-191">Klicken Sie im linken Navigationsbereich der **Admin Center**-Startseite auf **Abrechnung** und dann auf **Dienste kaufen**.</span><span class="sxs-lookup"><span data-stu-id="dcef4-191">From the left navigation of the **Admin center** home page, click **Billing**, and then **Purchase services**.</span></span>
    
3. <span data-ttu-id="dcef4-192">Erwerben Sie auf der Seite **Dienste kaufen** Ihre neuen Abonnements.</span><span class="sxs-lookup"><span data-stu-id="dcef4-192">On the **Purchase services** page, purchase your new subscriptions.</span></span>
    
<span data-ttu-id="dcef4-193">Das Admin Center ordnet die Organisation und den Azure AD-Mandanten Ihres Microsoft 365-Abonnements den neuen Abonnements für SaaS-basierte Cloudangebote zu.</span><span class="sxs-lookup"><span data-stu-id="dcef4-193">The admin center assigns the organization and Azure AD tenant of your Microsoft 365 subscription to the new subscriptions for SaaS-based cloud offerings.</span></span>
  
<span data-ttu-id="dcef4-194">So fügen Sie ein Azure-Abonnement mit derselben Organisation und demselben Azure AD-Mandanten wie das Microsoft 365-Abonnement hinzu:</span><span class="sxs-lookup"><span data-stu-id="dcef4-194">To add an Azure subscription with the same organization and Azure AD tenant as your Microsoft 365 subscription:</span></span>
  
1. <span data-ttu-id="dcef4-195">Melden Sie sich mit Ihrem globalen Microsoft 365-Administratorkonto beim Azure-Portal ([https://portal.azure.com](https://portal.azure.com)) an.</span><span class="sxs-lookup"><span data-stu-id="dcef4-195">Sign in to the Azure portal ([https://portal.azure.com](https://portal.azure.com)) with your Microsoft 365 global administrator account.</span></span>
    
2. <span data-ttu-id="dcef4-196">Klicken Sie im linken Navigationsbereich auf **Abonnements** und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dcef4-196">In the left navigation, click **Subscriptions**, and then click **Add**.</span></span>
    
3. <span data-ttu-id="dcef4-197">Wählen Sie auf der Seite **Abonnement hinzufügen** ein Angebot aus, und schließen Sie die Bezahlung und die Vereinbarung ab.</span><span class="sxs-lookup"><span data-stu-id="dcef4-197">On the **Add subscription** page, select an offer and complete the payment information and agreement.</span></span>
    
<span data-ttu-id="dcef4-198">Wenn Sie die Abonnements für Azure und Microsoft 365 einzeln erworben haben und den Microsoft 365 Azure AD-Mandanten von Ihrem Azure-Abonnement aus aufrufen möchten, finden Sie entsprechende Anweisungen unter [Hinzufügen eines vorhandenen Azure-Abonnements zu Ihrem Azure Active Directory-Mandanten](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).</span><span class="sxs-lookup"><span data-stu-id="dcef4-198">If you purchased Azure and Microsoft 365 subscriptions separately and want to access the Microsoft 365 Azure AD tenant from your Azure subscription, see the instructions in [Add an existing Azure subscription to your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="dcef4-199">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcef4-199">See also</span></span>

[<span data-ttu-id="dcef4-200">Illustrationen zu Microsoft Cloud für Enterprise-Architekten</span><span class="sxs-lookup"><span data-stu-id="dcef4-200">Microsoft cloud for enterprise architects illustrations</span></span>](../solutions/cloud-architecture-models.md)
  
[<span data-ttu-id="dcef4-201">Architekturmodelle für SharePoint, Exchange, Skype for Business und Lync</span><span class="sxs-lookup"><span data-stu-id="dcef4-201">Architectural models for SharePoint, Exchange, Skype for Business, and Lync</span></span>](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md)
  
[<span data-ttu-id="dcef4-202">Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="dcef4-202">Hybrid solutions</span></span>](hybrid-solutions.md)

## <a name="next-step"></a><span data-ttu-id="dcef4-203">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="dcef4-203">Next step</span></span>

[<span data-ttu-id="dcef4-204">Bewerten der Microsoft 365-Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="dcef4-204">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
