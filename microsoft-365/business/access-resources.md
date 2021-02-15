---
title: Zugreifen auf lokale Ressourcen von einem In Azure AD beigetretenen Gerät in Microsoft 365 Business
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
description: Erfahren Sie, wie Sie von einem mit Azure Active Directory beigetretenen Windows 10-Gerät Zugriff auf lokale Ressourcen wie Line-of-Business-Apps, Dateifreigaben und Drucker erhalten.
ms.openlocfilehash: fc02fd30f41f25f52e653e750a6bdfd1bd7f800e
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233838"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="b43f3-103">Zugreifen auf lokale Ressourcen von einem In Azure AD beigetretenen Gerät in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b43f3-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="b43f3-104">Dieser Artikel bezieht sich auf Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b43f3-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="b43f3-105">Jedes Windows 10-Gerät, dem Azure Active Directory beigetreten ist, hat Zugriff auf alle cloudbasierten Ressourcen, z. B. Ihre Microsoft 365-Apps, und kann durch Microsoft 365 Business Premium geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="b43f3-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="b43f3-106">Sie können auch den Zugriff auf lokale Ressourcen wie Branchen-Apps, Dateifreigaben und Drucker zulassen.</span><span class="sxs-lookup"><span data-stu-id="b43f3-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="b43f3-107">Um den Zugriff zu ermöglichen, verwenden [Sie Azure AD Connect,](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) um Ihr lokales Active Directory mit Azure Active Directory zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="b43f3-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="b43f3-108">Weitere Informationen finden Sie unter [Einführung in die Geräteverwaltung in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/device-management-introduction)</span><span class="sxs-lookup"><span data-stu-id="b43f3-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="b43f3-109">Die Schritte werden auch in den folgenden Abschnitten zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="b43f3-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="b43f3-110">Ausführen von Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="b43f3-110">Run Azure AD Connect</span></span>

<span data-ttu-id="b43f3-111">Führen Sie die folgenden Schritte aus, um den azure AD-beigetretenen Geräten Ihrer Organisation den Zugriff auf lokale Ressourcen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b43f3-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="b43f3-112">Um Ihre Benutzer, Gruppen und Kontakte aus dem lokalen Active Directory mit Azure Active Directory zu synchronisieren, führen Sie den Assistenten für die Verzeichnissynchronisierung und Azure AD Connect aus, wie unter Einrichten der Verzeichnissynchronisierung für [Office 365 beschrieben.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</span><span class="sxs-lookup"><span data-stu-id="b43f3-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="b43f3-113">Stellen Sie nach Abschluss der Verzeichnissynchronisierung sicher, dass die Windows 10-Geräte Ihrer Organisation in Azure AD verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="b43f3-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="b43f3-114">Dieser Schritt wird auf jedem Windows 10-Gerät einzeln ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b43f3-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="b43f3-115">Weitere [Informationen finden Sie unter "Einrichten von Windows-Geräten für Microsoft 365 Business Premium-Benutzer".](set-up-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="b43f3-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="b43f3-116">Sobald die Windows 10-Geräte Azure AD beigetreten sind, muss jeder Benutzer seine Geräte neu starten und sich mit seinen Microsoft 365 Business Premium-Anmeldeinformationen anmelden.</span><span class="sxs-lookup"><span data-stu-id="b43f3-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="b43f3-117">Alle Geräte haben jetzt auch Zugriff auf lokale Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="b43f3-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="b43f3-118">Es sind keine zusätzlichen Schritte erforderlich, um Zugriff auf lokale Ressourcen für azure AD-beigetretene Geräte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b43f3-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="b43f3-119">Diese Funktionalität ist in Windows 10 integrierte.</span><span class="sxs-lookup"><span data-stu-id="b43f3-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="b43f3-120">Wenn Sie planen, sich beim anderen AADJ-Gerät als der Kennwortmethode wie PIN/Biometrie über die Anmeldeinformationen des WHFB anzumelden und dann auf lokale Ressourcen (Freigaben, Drucker) zu zugreifen. usw.), folgen Sie bitte https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="b43f3-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="b43f3-121">Wenn Ihre Organisation nicht bereit für die Bereitstellung in der oben beschriebenen Azure AD-Gerätekonfiguration ist, erwägen Sie die Einrichtung der Azure [AD-Geräte-Hybridkonfiguration.](manage-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="b43f3-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="b43f3-122">Überlegungen beim Beitritt von Windows-Geräten zu Azure AD</span><span class="sxs-lookup"><span data-stu-id="b43f3-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="b43f3-123">Wenn das Windows-Gerät, dem Sie Azure AD beigetreten sind, zuvor einer Domäne oder einer Arbeitsgruppe beigetreten ist, sollten Sie die folgenden Einschränkungen beachten:</span><span class="sxs-lookup"><span data-stu-id="b43f3-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="b43f3-124">Wenn ein Gerät mit Azure AD beitritt, wird ein neuer Benutzer erstellt, ohne auf ein vorhandenes Profil zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="b43f3-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="b43f3-125">Profile müssen manuell migriert werden.</span><span class="sxs-lookup"><span data-stu-id="b43f3-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="b43f3-126">Ein Benutzerprofil enthält Informationen wie Favoriten, lokale Dateien, Browsereinstellungen und Startmenüeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="b43f3-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="b43f3-127">Ein optimaler Ansatz besteht in der Suche nach einem Drittanbietertool, um vorhandene Dateien und Einstellungen dem neuen Profil zu zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="b43f3-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="b43f3-128">Wenn das Gerät Gruppenrichtlinienobjekte (Group Policy Objects, GPO) verwendet, verfügen einige Gruppenrichtlinienobjekte möglicherweise nicht über einen vergleichbaren [Konfigurationsdienstanbieter (Configuration Service Provider,](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) CSP) in Intune.</span><span class="sxs-lookup"><span data-stu-id="b43f3-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="b43f3-129">Führen Sie das [Tool MMAT aus,](https://www.microsoft.com/download/details.aspx?id=45520) um nach vergleichbaren CSPs für vorhandene Gruppenrichtlinienobjekte zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b43f3-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="b43f3-130">Benutzer können sich möglicherweise nicht bei Anwendungen authentifizieren, die von der Active Directory-Authentifizierung abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="b43f3-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="b43f3-131">Bewerten Sie die Legacy-App, und erwägen Sie nach Möglichkeit das Aktualisieren auf eine App, die moderne Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b43f3-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="b43f3-132">Die Active Directory-Druckerermittlung funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="b43f3-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="b43f3-133">Sie können direkte Druckerpfade für alle Benutzer bereitstellen oder [universelles Drucken verwenden.](https://aka.ms/UPDocs)</span><span class="sxs-lookup"><span data-stu-id="b43f3-133">You can provide direct printer paths for all users or use [Universal Print](https://aka.ms/UPDocs).</span></span>
