---
title: Automatisches Installieren oder Deinstallieren von Office auf Windows 10-Geräten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Installieren oder deinstallieren Sie Office auf Windows 10-Geräten im Microsoft 365 Business Admin Center. '
ms.openlocfilehash: fef4a543aed489202bf05dfb1e8cafbb784ca819
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277275"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="6bf44-103">Automatisches Installieren oder Deinstallieren von Office auf Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="6bf44-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

<span data-ttu-id="6bf44-104">[] Sie können Office über das Microsoft 365 Business Admin Center auf Windows 10-PCs schnell und einfach installieren.</span><span class="sxs-lookup"><span data-stu-id="6bf44-104">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="6bf44-105">Um zu verstehen, wie dies bei zuvor installierten Office-Apps funktioniert, lesen Sie [Vorbereiten der Office-Clientinstallation](prepare-for-office-client-deployment.md), bevor Sie mit diesem Vorgang beginnen.</span><span class="sxs-lookup"><span data-stu-id="6bf44-105">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="6bf44-106">Verwalten von Office-Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="6bf44-106">Manage Office deployments</span></span>

1. <span data-ttu-id="6bf44-107">Melden Sie sich beim [Admin Center](https://aka.ms/bcsportal) mit globalen Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="6bf44-107">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="6bf44-108">Wählen Sie auf der Karte **Geräte** die Option **Office-Bereitstellung verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="6bf44-108">On the **Devices** card, choose **Manage Office Deployment**.</span></span>
      <span data-ttu-id="6bf44-109">Wenn die **Device Actions** -Karte nicht angezeigt wird, klicken Sie auf der Admin Center- **Start** Seite auf **Hinzufügen** (+), um Sie Ihrem Administrator-Home hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6bf44-109">If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="6bf44-111">Wählen Sie in dem daraufhin geöffneten Bereich **Office-Bereitstellung verwalten** die Option **Gruppe hinzufügen** und dann die gewünschte(n) Gruppe(n) aus.</span><span class="sxs-lookup"><span data-stu-id="6bf44-111">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="6bf44-112">Nachdem Sie diese Gruppe(n) hinzugefügt haben, wählen Sie aus der Dropdownliste **Bereitstellungsaktion** einen der beiden Einträge **Office schnellstmöglich installieren** oder **Office deinstallieren** aus.</span><span class="sxs-lookup"><span data-stu-id="6bf44-112">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="6bf44-114">Wählen Sie **Weiter**\> aus, um die Einstellungen zu überprüfen. Wählen Sie dann **Bestätigen** aus.</span><span class="sxs-lookup"><span data-stu-id="6bf44-114">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="6bf44-115">Eine 32-Bit-Instanz von Office wird auf den Geräten automatisch installiert oder deinstalliert, deren Besitzer die Benutzer sind, die Sie durch die von Ihnen verwendete(n) Gruppe(n) festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="6bf44-115">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="6bf44-116">Um dies zu überprüfen, können Sie den Task-Manager auf einem Computer öffnen, der für eine Office-Installation ausgewählt wurde, und nach dem Prozess "Microsoft Office Klick-und-Los" suchen.</span><span class="sxs-lookup"><span data-stu-id="6bf44-116">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


