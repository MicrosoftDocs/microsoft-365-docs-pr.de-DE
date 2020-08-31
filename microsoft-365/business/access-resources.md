---
title: Zugreifen auf lokale Ressourcen von einem Azure AD verbundenen Gerät in Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Hier erfahren Sie, wie Sie Zugriff auf lokale Ressourcen wie Branchen-apps, Dateifreigaben und Drucker aus einem Azure-Active Directory, dem Windows 10-Gerät beigetreten ist.
ms.openlocfilehash: 9b83781afee746b06bbdf90962de0f55ffbcb118
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307491"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="03173-103">Zugreifen auf lokale Ressourcen von einem Azure AD verbundenen Gerät in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="03173-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="03173-104">Dieser Artikel bezieht sich auf Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="03173-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="03173-105">Jedes Windows 10-Gerät, das Azure Active Directory beigetreten ist, hat Zugriff auf alle cloudbasierten Ressourcen wie Ihre Microsoft 365-apps und kann durch Microsoft 365 Business Premium geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="03173-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="03173-106">Sie können auch Zugriff auf lokale Ressourcen wie Branchen-apps, Dateifreigaben und Drucker gewähren.</span><span class="sxs-lookup"><span data-stu-id="03173-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="03173-107">Um den Zugriff zuzulassen, verwenden Sie [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) , um Ihre lokale Active Directory mit Azure Active Directory zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="03173-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="03173-108">Weitere Informationen finden Sie unter [Einführung in die Geräteverwaltung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="03173-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="03173-109">Die Schritte sind auch in den folgenden Abschnitten zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="03173-109">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03173-110">Dieses Verfahren gilt nur für OAuth und NTLM.</span><span class="sxs-lookup"><span data-stu-id="03173-110">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="03173-111">Kerberos wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="03173-111">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="03173-112">Ausführen Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="03173-112">Run Azure AD Connect</span></span>

<span data-ttu-id="03173-113">Führen Sie die folgenden Schritte aus, um die Azure AD verbundenen Geräte Ihrer Organisation für den Zugriff auf lokale Ressourcen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="03173-113">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="03173-114">Führen Sie den Assistenten für die Verzeichnissynchronisierung aus, und Azure AD Connect wie unter [Einrichten der Verzeichnissynchronisierung für Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)beschrieben, um Ihre Benutzer, Gruppen und Kontakte von der lokalen Active Directory in Azure Active Directory zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="03173-114">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="03173-115">Nachdem die Verzeichnissynchronisierung abgeschlossen ist, stellen Sie sicher, dass die Windows 10-Geräte Ihrer Organisation Azure AD verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="03173-115">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="03173-116">Dieser Schritt wird auf jedem Windows 10-Gerät einzeln ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03173-116">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="03173-117">Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business Premium-Benutzer](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="03173-117">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="03173-118">Sobald die Windows 10-Geräte Azure AD beigetreten sind, müssen alle Benutzer ihre Geräte neu starten und sich mit Ihren Microsoft 365 Business Premium-Anmeldeinformationen anmelden.</span><span class="sxs-lookup"><span data-stu-id="03173-118">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="03173-119">Alle Geräte haben jetzt auch Zugriff auf lokale Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="03173-119">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="03173-120">Es sind keine weiteren Schritte erforderlich, um Zugriff auf lokale Ressourcen für Azure AD verbundene Geräte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="03173-120">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="03173-121">Diese Funktionalität ist in Windows 10 integriert.</span><span class="sxs-lookup"><span data-stu-id="03173-121">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="03173-122">Wenn Sie Pläne zur Anmeldung auf dem AADJ-Gerät als Kenn Wort Methode wie PIN/Bio-Metric über WHFB Credential Login haben und dann auf lokale Ressourcen (Freigaben, Drucker.. usw.), bitte beachten Sie https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="03173-122">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="03173-123">Wenn Ihre Organisation nicht bereit ist, die oben beschriebene Bereitstellung in der Azure AD beigefügten Gerätekonfiguration vorzulegen, sollten Sie die [Konfiguration einer hybriden Azure AD verbundenen Gerätekonfiguration](manage-windows-devices.md)in prüfen.</span><span class="sxs-lookup"><span data-stu-id="03173-123">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="03173-124">Überlegungen beim Beitritt von Windows-Geräten zu Azure AD</span><span class="sxs-lookup"><span data-stu-id="03173-124">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="03173-125">Wenn das Windows-Gerät, das Sie Azure-AD beigetreten sind, zuvor einer Domäne beigetreten war oder sich in einer Arbeitsgruppe befand, sollten Sie die folgenden Einschränkungen in Frage stellen:</span><span class="sxs-lookup"><span data-stu-id="03173-125">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="03173-126">Wenn ein Gerät Azure AD Beitritt, wird ein neuer Benutzer erstellt, ohne auf ein vorhandenes Profil zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="03173-126">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="03173-127">Profile müssen manuell migriert werden.</span><span class="sxs-lookup"><span data-stu-id="03173-127">Profiles must be manually migrated.</span></span> <span data-ttu-id="03173-128">Ein Benutzerprofil enthält Informationen wie Favoriten, lokale Dateien, Browsereinstellungen und Start Menü Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="03173-128">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="03173-129">Ein optimaler Ansatz besteht darin, ein Drittanbietertool zu finden, um vorhandene Dateien und Einstellungen dem neuen Profil zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="03173-129">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="03173-130">Wenn das Gerät Gruppenrichtlinienobjekte (Group Policy Objects, GPO) verwendet, verfügen einige GPOs möglicherweise nicht über einen vergleichbaren [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in InTune.</span><span class="sxs-lookup"><span data-stu-id="03173-130">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="03173-131">Führen Sie das [FMAT-Tool](https://www.microsoft.com/download/details.aspx?id=45520) aus, um vergleichbare Kryptografiedienstanbieter für vorhandene GPOs zu finden.</span><span class="sxs-lookup"><span data-stu-id="03173-131">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="03173-132">Benutzer können sich nicht bei Anwendungen authentifizieren, die von der Active Directory-Authentifizierung abhängen.</span><span class="sxs-lookup"><span data-stu-id="03173-132">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="03173-133">Bewerten Sie die Legacy-APP, und aktualisieren Sie diese in einer APP, die eine moderne Authentifizierung verwendet, wenn möglich.</span><span class="sxs-lookup"><span data-stu-id="03173-133">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="03173-134">Active Directory Druckersuche funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="03173-134">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="03173-135">Sie können direkte Druckerpfade für alle Benutzer bereitstellen oder [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)verwenden.</span><span class="sxs-lookup"><span data-stu-id="03173-135">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
