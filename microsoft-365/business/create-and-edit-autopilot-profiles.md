---
title: Erstellen und Bearbeiten von AutoPilot-Profilen
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
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Informationen zum Erstellen, bearbeiten, löschen oder Entfernen von autoPilot-Profilen. '
ms.openlocfilehash: 85fc897b2f428afae8d55feeb577021adaa30f72
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277109"
---
# <a name="create-and-edit-autopilot-profiles"></a>Erstellen und Bearbeiten von AutoPilot-Profilen

## <a name="create-a-profile"></a>Erstellen eines Profils

Ein Profil gilt für ein Gerät oder eine Gerätegruppe.
  
1. wählen sie im Microsoft 365 Business Admin center die option **geräte** \> **autopilot**aus.
  
2. Klicken Sie **** auf der Seite Autopilot auf die Register \> Karte **profile** **Profil erstellen**.
    
3. Geben Sie auf der Seite **Profil erstellen** einen Namen für das Profil ein, mit dem Sie es identifizieren können, z.B. Marketing. Aktivieren Sie die gewünschte Einstellung (weitere Informationen finden Sie unter [Informationen zu AutoPilot-Profileinstellungen](autopilot-profile-settings.md)), und wählen Sie **Speichern**.
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Zuweisen eines Profils zu einem Gerät

Nachdem Sie ein Profil erstellt haben, können Sie es einem Gerät oder einer Gruppe von Geräten zuweisen. Sie können ein vorhandenes Profil in der [schrittweisen Anleitung](add-autopilot-devices-and-profile.md) auswählen, es neuen Geräten zuordnen oder ein vorhandenes Profil für ein Gerät oder eine Gerätegruppe ersetzen. 
  
1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**. 
    
2. Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Bearbeiten, Löschen oder Entfernen eines Profils

Nachdem Sie einem Gerät ein Profil zugewiesen haben, können Sie es aktualisieren, auch wenn Sie das Gerät bereits einem Benutzer zugewiesen haben. Wenn sich das Gerät mit dem Internet verbindet, lädt es während des Setupvorgangs die neueste Version Ihres Profils herunter. Wenn der Benutzer das Gerät auf die werkseitigen Standardeinstellungen zurücksetzt, lädt das Gerät erneut die neuesten Updates in Ihr Profil herunter. 
  
### <a name="edit-a-profile"></a>Bearbeiten eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**. 
    
2. Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.
    
    Wenn Sie dies tun, bevor ein Benutzer das Gerät mit dem Internet verbindet, wird das Profil auf den Setupvorgang angewendet.
    
### <a name="delete-a-profile"></a>Löschen eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**. 
    
2. Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.
    
    Wenn Sie ein Profil löschen, wird es von einem Gerät oder einer Gruppe von Geräten entfernt, denen es zugewiesen war.
    
### <a name="remove-a-profile"></a>Entfernen eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**. 
    
2. Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.
    
