---
title: Zugriff auf lokale Ressourcen von einem Azure AD gehörenden Gerät in Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Erfahren Sie, wie erhalten Sie Zugriff auf lokale Ressourcen, wie Line Of Business-apps, Dateifreigaben und Drucker von Azure Active Directory Windows 10 Gerät verbunden.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867586"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="34ef5-103">Zugriff auf lokale Ressourcen von einem Azure AD gehörenden Gerät in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="34ef5-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="34ef5-p101">Alle Windows 10-Geräte, die Azure Active Directory verbunden ist haben Zugriff auf alle cloudbasierte Ressourcen wie Ihre apps für Office 365 und kann von Microsoft 365 Business geschützt werden. Um den Zugriff auf lokale Ressourcen wie Zeile des Business (LOB) apps, Dateifreigaben und Drucker zu ermöglichen, müssen Sie Ihre lokale Active Directory mithilfe von [Azure Active Directory verbinden](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)mit Azure Active Directory synchronisieren. Finden Sie unter [Einführung in die Verwaltung von Geräten in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) , um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="34ef5-p101">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business. To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span> 
  
## <a name="run-azure-ad-connect"></a><span data-ttu-id="34ef5-107">Ausführen von Azure Active Directory verbinden</span><span class="sxs-lookup"><span data-stu-id="34ef5-107">Run Azure AD Connect</span></span>

<span data-ttu-id="34ef5-108">Gehen Sie folgendermaßen vor, um beigetreten Azure AD-Geräte für den Zugriff auf lokale Ressourcen auf Ihrer Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="34ef5-108">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="34ef5-109">Führen Sie zum Synchronisieren der Benutzer, Gruppen und Kontakte aus der lokalen Active Directory in Azure Active Directory-Assistenten für die-Synchronisierung, und Azure Active Directory verbinden als in [Einrichten von verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34ef5-109">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="34ef5-p102">Nach Abschluss die verzeichnissynchronisierung, stellen Sie sicher, dass Ihre Organisation Windows 10 Geräte Azure AD verbunden sind. Dieser Schritt ist auf jedem Gerät Windows 10 einzeln ausgeführt. Einzelheiten finden Sie unter [Einrichten von Windows-Geräte für Microsoft 365 Geschäftsbenutzer](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="34ef5-p102">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined. This step is done individually on each Windows 10 device. See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="34ef5-p103">Nachdem die Geräte 10 für Windows Azure AD verbunden sind, sollte jeder Benutzer ihre Geräte und melden Sie sich mit den Anmeldeinformationen ihres Microsoft 365 Business neu starten. Alle Geräte werden nun auf sowie auf lokale Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="34ef5-p103">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials. All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="34ef5-p104">Es sind keine zusätzliche Schritte erforderlich Zugriff auf lokale, dass Ressourcen für Azure AD Geräte verbunden. Dies ist die integrierte Funktionalität in Windows 10 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="34ef5-p104">No additional steps are required to get access to on-premise resources for Azure AD joined devices. This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="34ef5-117">Wenn Ihre Organisation nicht zum Bereitstellen von in Azure AD beigetreten Gerätekonfiguration oben beschriebenen bereit ist, sollten Sie einrichten [Hybrid Azure AD beigetreten Gerätekonfiguration](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="34ef5-117">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="34ef5-118">Aspekte beim Beitritt Ihre Geräte Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="34ef5-118">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="34ef5-119">Wenn Sie die Teilnahme an einer Windows-Gerät, die zuvor in die Domäne eingebundener wurde Azure AD sind oder in einer Arbeitsgruppe, müssen Sie die folgenden Nachteile beachten:</span><span class="sxs-lookup"><span data-stu-id="34ef5-119">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="34ef5-p105">Wenn ein Gerät Azure AD beigetreten ist, erstellt es einen neuen Benutzer ohne verweisen auf ein vorhandenes Profil. Um dieses Problem zu beheben, müssen Profile manuell migriert werden müssen. Ein Benutzerprofil enthält Informationen wie Favoriten, lokale Dateien, Browsereinstellungen, Start im Menü Einstellungen usw.. Ein bewährte Ansatz besteht darin, ein Drittanbieter-Tool Zuordnen von vorhandenen Dateien und Einstellungen zu dem neuen Profil suchen</span><span class="sxs-lookup"><span data-stu-id="34ef5-p105">When a device Azure AD joins, it creates a new user without referencing an existing profile. To fix this, profiles need to be manually migrated. A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>
    
- <span data-ttu-id="34ef5-p106">Wenn das Gerät (Group Policy Objects, GPOs) verwendet wird, möglicherweise einige Gruppenrichtlinienobjekte eine vergleichbare [Konfiguration-Dienstanbieter](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) nicht in Intune. Führen Sie das [Tool MMAT](https://www.microsoft.com/download/details.aspx?id=45520) vergleichbare Kryptografiedienstanbieter für vorhandene Gruppenrichtlinienobjekte zu finden.</span><span class="sxs-lookup"><span data-stu-id="34ef5-p106">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span> 
    
- <span data-ttu-id="34ef5-p107">Benutzer werden nicht authentifiziert für Clientanwendungen, die von Active Directory-Authentifizierung abhängen. Für den Umgang mit dadurch auswerten mit einer Vorversion app und erwägen Sie eine Aktualisierung zu einer app, die moderne Auth möglichst verwendet.</span><span class="sxs-lookup"><span data-stu-id="34ef5-p107">Users will not be able to authenticate to applications that depend on Active Directory authentication. To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>
    
- <span data-ttu-id="34ef5-p108">Active Directory Drucker Discovery funktioniert nicht. Um dieses Problem zu beheben, bieten Sie direkte Druckerpfade für alle Benutzer oder nutzen Sie [Hybrid Cloud drucken](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="34ef5-p108">Active Directory printer discovery will not work. To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
    

