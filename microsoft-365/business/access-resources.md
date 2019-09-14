---
title: Zugreifen auf lokale Ressourcen von einem Azure AD verbundenen Gerät in Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Hier erfahren Sie, wie Sie Zugriff auf lokale Ressourcen wie Branchen-apps, Dateifreigaben und Drucker aus einem Azure-Active Directory, dem Windows 10-Gerät beigetreten ist.
ms.openlocfilehash: ab9049e78617372463b8446dc8f8bc0089d8c117
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981659"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="68e7f-103">Zugreifen auf lokale Ressourcen von einem Azure AD verbundenen Gerät in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="68e7f-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="68e7f-104">Jedes Windows 10-Gerät, das als Azure Active Directory beigetreten ist, hat Zugriff auf alle Cloud-basierten Ressourcen wie Ihre Office 365-apps und kann von Microsoft 365 Business geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="68e7f-104">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="68e7f-105">Um auch Zugriff auf lokale Ressourcen wie Branchen-apps, Dateifreigaben und Drucker zu gewähren, müssen Sie Ihre lokale Active Directory mit Azure Active Directory mithilfe von [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="68e7f-105">To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span> <span data-ttu-id="68e7f-106">Im folgenden Video werden die Schritte zum Einrichten dieser Einstellung für das gängigste Szenario erläutert.</span><span class="sxs-lookup"><span data-stu-id="68e7f-106">The following video details the steps for how to set this up for the most common scenario.</span></span>
 
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]

<span data-ttu-id="68e7f-107">Weitere Informationen finden Sie unter [Einführung in die Geräteverwaltung in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) .</span><span class="sxs-lookup"><span data-stu-id="68e7f-107">See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span>
<span data-ttu-id="68e7f-108">Die Schritte sind auch in den folgenden Abschnitten zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="68e7f-108">The steps are also summarized in the following sections.</span></span>

## <a name="run-azure-ad-connect"></a><span data-ttu-id="68e7f-109">Ausführen Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="68e7f-109">Run Azure AD Connect</span></span>

<span data-ttu-id="68e7f-110">Führen Sie die folgenden Schritte aus, um die Azure AD verbundenen Geräte Ihrer Organisation für den Zugriff auf lokale Ressourcen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="68e7f-110">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="68e7f-111">Führen Sie den Assistenten für die Verzeichnissynchronisierung aus, und Azure AD Connect wie unter [Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)beschrieben, um Ihre Benutzer, Gruppen und Kontakte von der lokalen Active Directory in Azure Active Directory zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="68e7f-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="68e7f-112">Stellen Sie nach Abschluss der Verzeichnissynchronisierung sicher, dass die Windows 10-Geräte Ihrer Organisation Azure AD verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="68e7f-112">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="68e7f-113">Dieser Schritt wird auf jedem Windows 10-Gerät einzeln ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="68e7f-113">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="68e7f-114">Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business-Benutzer](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="68e7f-114">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="68e7f-115">Sobald die Windows 10-Geräte Azure AD beigetreten sind, sollten alle Benutzer ihre Geräte neu starten und sich mit Ihren Microsoft 365-Geschäfts Anmeldeinformationen anmelden.</span><span class="sxs-lookup"><span data-stu-id="68e7f-115">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="68e7f-116">Alle Geräte können nun auch auf lokale Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="68e7f-116">All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="68e7f-117">Es sind keine weiteren Schritte erforderlich, um Zugriff auf lokale Ressourcen für Azure AD verbundene Geräte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="68e7f-117">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="68e7f-118">Hierbei handelt es sich um integrierte Funktionen, die in Windows 10 verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="68e7f-118">This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="68e7f-119">Wenn Ihre Organisation nicht bereit ist, in der oben beschriebenen Azure AD beigefügten Gerätekonfiguration bereitzustellen, sollten Sie die [Konfiguration einer hybriden Azure AD](manage-windows-devices.md)die Verbindung mit dem Gerät konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="68e7f-119">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="68e7f-120">Überlegungen zum Verbinden Ihrer Windows-Geräte mit Azure AD</span><span class="sxs-lookup"><span data-stu-id="68e7f-120">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="68e7f-121">Wenn Sie Azure AD einem Windows-Gerät beitreten, das zuvor einer Domäne oder einer Arbeitsgruppe beigetreten ist, müssen Sie die folgenden Einschränkungen in Frage stellen:</span><span class="sxs-lookup"><span data-stu-id="68e7f-121">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="68e7f-122">Wenn ein Gerät Azure AD Beitritt, wird ein neuer Benutzer erstellt, ohne auf ein vorhandenes Profil zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="68e7f-122">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="68e7f-123">Um dies zu beheben, müssen Profile manuell migriert werden.</span><span class="sxs-lookup"><span data-stu-id="68e7f-123">To fix this, profiles need to be manually migrated.</span></span> <span data-ttu-id="68e7f-124">Ein Benutzerprofil enthält Informationen wie Favoriten, lokale Dateien, Browsereinstellungen, Start Menü Einstellungen usw. Ein optimaler Ansatz besteht darin, ein Drittanbietertool zu finden, um vorhandene Dateien und Einstellungen dem neuen Profil zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="68e7f-124">A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>

- <span data-ttu-id="68e7f-125">Wenn das Gerät Gruppenrichtlinienobjekte (Group Policy Objects, GPO) verwendet, verfügen einige GPOs möglicherweise nicht über einen vergleichbaren [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in InTune.</span><span class="sxs-lookup"><span data-stu-id="68e7f-125">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="68e7f-126">Führen Sie das [FMAT-Tool](https://www.microsoft.com/download/details.aspx?id=45520) aus, um vergleichbare Kryptografiedienstanbieter für vorhandene GPOs zu finden.</span><span class="sxs-lookup"><span data-stu-id="68e7f-126">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="68e7f-127">Benutzer können sich bei Anwendungen, die von der Active Directory Authentifizierung abhängen, nicht authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="68e7f-127">Users will not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="68e7f-128">Um dies zu bewältigen, verwenden Sie eine Legacy-APP, und aktualisieren Sie eine APP, die nach Möglichkeit moderne Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="68e7f-128">To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>

- <span data-ttu-id="68e7f-129">Die Active Directory Druckererkennung funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="68e7f-129">Active Directory printer discovery will not work.</span></span> <span data-ttu-id="68e7f-130">Um dies zu beheben, stellen Sie direkte Druckerpfade für alle Benutzer bereit oder nutzen Sie den [Hybriden Cloud-Druck](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="68e7f-130">To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
