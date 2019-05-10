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
ms.openlocfilehash: 94e5761b516c150caa11048be73d97f468b09fb5
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660572"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a>Automatisches Installieren oder Deinstallieren von Office auf Windows 10-Geräten

![Banner, das auf https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

[] Sie können Office über das Microsoft 365 Business Admin Center auf Windows 10-PCs schnell und einfach installieren.
  
Um zu verstehen, wie dies bei zuvor installierten Office-Apps funktioniert, lesen Sie [Vorbereiten der Office-Clientinstallation](prepare-for-office-client-deployment.md), bevor Sie mit diesem Vorgang beginnen. 
  
## <a name="manage-office-deployments"></a>Verwalten von Office-Bereitstellungen

1. Melden Sie sich beim [Admin Center](https://aka.ms/bcsportal) mit globalen Administratoranmeldeinformationen an. 
    
2. Wählen Sie auf der Karte **Geräte** die Option **Office-Bereitstellung verwalten** aus.
      Wenn die **Device Actions** -Karte nicht angezeigt wird, klicken Sie auf der Admin Center- **Start** Seite auf **Hinzufügen** (+), um Sie Ihrem Administrator-Home hinzuzufügen.
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. Wählen Sie in dem daraufhin geöffneten Bereich **Office-Bereitstellung verwalten** die Option **Gruppe hinzufügen** und dann die gewünschte(n) Gruppe(n) aus.
    
4. Nachdem Sie diese Gruppe(n) hinzugefügt haben, wählen Sie aus der Dropdownliste **Bereitstellungsaktion** einen der beiden Einträge **Office schnellstmöglich installieren** oder **Office deinstallieren** aus.
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. Wählen Sie **Weiter**\> aus, um die Einstellungen zu überprüfen. Wählen Sie dann **Bestätigen** aus.
    
Eine 32-Bit-Instanz von Office wird auf den Geräten automatisch installiert oder deinstalliert, deren Besitzer die Benutzer sind, die Sie durch die von Ihnen verwendete(n) Gruppe(n) festgelegt haben.
  
Um dies zu überprüfen, können Sie den Task-Manager auf einem Computer öffnen, der für eine Office-Installation ausgewählt wurde, und nach dem Prozess "Microsoft Office Klick-und-Los" suchen.
  


