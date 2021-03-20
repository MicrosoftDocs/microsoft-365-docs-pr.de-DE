---
title: Zugreifen auf lokale Ressourcen von einem Azure AD-beigetretenen Gerät in Microsoft 365 Business
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
description: Erfahren Sie, wie Sie von einem Azure Active Directory-bei Windows 10-Gerät beigetretenen Windows 10-Gerät Zugriff auf lokale Ressourcen wie Unternehmens-Apps, Dateifreigaben und Drucker erhalten.
ms.openlocfilehash: b78509d72cbd9b3c121039c4965625bf5c21c7e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913520"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="6484f-103">Zugreifen auf lokale Ressourcen von einem Azure AD-beigetretenen Gerät in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="6484f-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="6484f-104">Dieser Artikel gilt für Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="6484f-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="6484f-105">Jedes Windows 10-Gerät, dem Azure Active Directory beigetreten ist, hat Zugriff auf alle cloudbasierten Ressourcen, z. B. Ihre Microsoft 365-Apps, und kann durch Microsoft 365 Business Premium geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="6484f-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="6484f-106">Sie können auch zugriff auf lokale Ressourcen wie Branchen-Apps, Dateifreigaben und Drucker zulassen.</span><span class="sxs-lookup"><span data-stu-id="6484f-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="6484f-107">Verwenden Sie Azure [AD Connect,](/azure/active-directory/connect/active-directory-aadconnect) um den Zugriff zu ermöglichen, um Ihr lokales Active Directory mit Azure Active Directory zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="6484f-107">To allow access, use [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="6484f-108">Weitere Informationen finden Sie unter [Einführung in die Geräteverwaltung in Azure Active Directory](/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="6484f-108">To learn more, see [Introduction to device management in Azure Active Directory](/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="6484f-109">Die Schritte werden auch in den folgenden Abschnitten zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="6484f-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="6484f-110">Ausführen von Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="6484f-110">Run Azure AD Connect</span></span>

<span data-ttu-id="6484f-111">Führen Sie die folgenden Schritte aus, um den azure AD-beigetretenen Geräten Ihrer Organisation den Zugriff auf lokale Ressourcen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6484f-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="6484f-112">Führen Sie zum Synchronisieren Ihrer Benutzer, Gruppen und Kontakte aus dem lokalen Active Directory in Azure Active Directory den Assistenten für die Verzeichnissynchronisierung und Azure AD Connect aus, wie unter Einrichten der Verzeichnissynchronisierung für [Office 365 beschrieben.](../enterprise/set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="6484f-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](../enterprise/set-up-directory-synchronization.md).</span></span>
    
2. <span data-ttu-id="6484f-113">Stellen Sie nach Abschluss der Verzeichnissynchronisierung sicher, dass die Windows 10-Geräte Ihrer Organisation Azure AD beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="6484f-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="6484f-114">Dieser Schritt wird auf jedem Windows 10-Gerät einzeln ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6484f-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="6484f-115">Weitere Informationen finden Sie unter Einrichten von [Windows-Geräten für Microsoft 365 Business](set-up-windows-devices.md) Premium-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6484f-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="6484f-116">Sobald die Windows 10-Geräte Azure AD beigetreten sind, muss jeder Benutzer seine Geräte neu starten und sich mit seinen Microsoft 365 Business Premium-Anmeldeinformationen anmelden.</span><span class="sxs-lookup"><span data-stu-id="6484f-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="6484f-117">Alle Geräte haben jetzt auch Zugriff auf lokale Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="6484f-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="6484f-118">Es sind keine weiteren Schritte erforderlich, um Zugriff auf lokale Ressourcen für Azure AD-beigetretene Geräte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6484f-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="6484f-119">Diese Funktionalität ist in Windows 10 integrierte.</span><span class="sxs-lookup"><span data-stu-id="6484f-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="6484f-120">Wenn Sie planen, sich beim AADJ-Gerät anzumelden, das keine Kennwortmethode wie PIN/Biometrik über die WHFB-Anmeldeinformationen ist, und dann auf lokale Ressourcen (Freigaben, Drucker. usw.), folgen Sie bitte https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="6484f-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="6484f-121">Wenn Ihre Organisation nicht bereit für die Bereitstellung in der oben beschriebenen Azure AD-Gerätekonfiguration ist, sollten Sie die Konfiguration der Azure [AD-Beigetretenen Hybridgeräte einrichten.](manage-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="6484f-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="6484f-122">Überlegungen beim Beitritt von Windows-Geräten zu Azure AD</span><span class="sxs-lookup"><span data-stu-id="6484f-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="6484f-123">Wenn das Windows-Gerät, dem Sie Azure-AD beigetreten sind, zuvor einer Domäne oder einer Arbeitsgruppe beigetreten ist, sollten Sie die folgenden Einschränkungen beachten:</span><span class="sxs-lookup"><span data-stu-id="6484f-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="6484f-124">Wenn ein Gerät Azure AD beitritt, erstellt es einen neuen Benutzer, ohne auf ein vorhandenes Profil zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="6484f-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="6484f-125">Profile müssen manuell migriert werden.</span><span class="sxs-lookup"><span data-stu-id="6484f-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="6484f-126">Ein Benutzerprofil enthält Informationen wie Favoriten, lokale Dateien, Browsereinstellungen und Startmenüeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6484f-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="6484f-127">Ein optimaler Ansatz besteht in der Suche nach einem Drittanbietertool, um vorhandene Dateien und Einstellungen dem neuen Profil zu zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="6484f-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="6484f-128">Wenn das Gerät Gruppenrichtlinienobjekte (Group Policy Objects, GPO) verwendet, verfügen einige Gruppenrichtlinienobjekte möglicherweise nicht über einen vergleichbaren [Konfigurationsdienstanbieter (Configuration Service Provider,](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) CSP) in Intune.</span><span class="sxs-lookup"><span data-stu-id="6484f-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="6484f-129">Führen Sie das [MMAT-Tool aus,](https://www.microsoft.com/download/details.aspx?id=45520) um vergleichbare CSPs für vorhandene Gruppenrichtlinienobjekte zu finden.</span><span class="sxs-lookup"><span data-stu-id="6484f-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="6484f-130">Benutzer können sich möglicherweise nicht bei Anwendungen authentifizieren, die von der Active Directory-Authentifizierung abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="6484f-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="6484f-131">Bewerten Sie die Legacy-App, und erwägen Sie nach Möglichkeit das Aktualisieren auf eine App, die moderne Auth verwendet.</span><span class="sxs-lookup"><span data-stu-id="6484f-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="6484f-132">Die Active Directory-Druckerermittlung funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="6484f-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="6484f-133">Sie können direkte Druckerpfade für alle Benutzer bereitstellen oder [Universal Print verwenden.](/universal-print/)</span><span class="sxs-lookup"><span data-stu-id="6484f-133">You can provide direct printer paths for all users or use [Universal Print](/universal-print/).</span></span>