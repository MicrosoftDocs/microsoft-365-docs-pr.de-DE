---
title: Erstellen und Bearbeiten von AutoPilot-Profilen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: 'Informationen Sie zum Erstellen, bearbeiten, löschen oder Entfernen von AutoPilot Profile. '
ms.openlocfilehash: 4658a27e5f2c64a52f8a7d08b3fc13df5e239dc3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867863"
---
# <a name="create-and-edit-autopilot-profiles"></a>Erstellen und Bearbeiten von AutoPilot-Profilen

## <a name="create-a-profile"></a>Erstellen eines Profils

Ein Profil gilt für ein Gerät oder eine Gerätegruppe.
  
1. Wählen Sie im Microsoft 365 Business Admin Center auf der Karte **Geräteaktionen** die Option **Windows mit AutoPilot bereitstellen**. 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile** \> **Profil erstellen**.
    
3. Geben Sie auf der Seite **Profil erstellen** einen Namen für das Profil ein, mit dem Sie es identifizieren können, z.B. Marketing. Aktivieren Sie die gewünschte Einstellung (weitere Informationen finden Sie unter [Informationen zu AutoPilot-Profileinstellungen](autopilot-profile-settings.md)), und wählen Sie **Speichern**.
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Zuweisen eines Profils zu einem Gerät

Nachdem Sie ein Profil erstellt haben, können Sie es einem Gerät oder einer Gruppe von Geräten zuweisen. Sie können ein vorhandenes Profil in der [schrittweisen Anleitung](add-autopilot-devices-and-profile.md) auswählen, es neuen Geräten zuordnen oder ein vorhandenes Profil für ein Gerät oder eine Gerätegruppe ersetzen. 
  
1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**. 
    
2. Klicken Sie auf das Kontrollkästchen neben den Namen eines Geräts und in der Systemsteuerung **Gerät** , wählen Sie aus der Dropdownliste **zugewiesene Profil** ein Profil \> **Speichern**.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Bearbeiten, Löschen oder Entfernen eines Profils

Nachdem Sie einem Gerät ein Profil zugewiesen haben, können Sie es aktualisieren, auch wenn Sie das Gerät bereits einem Benutzer zugewiesen haben. Wenn sich das Gerät mit dem Internet verbindet, lädt es während des Setupvorgangs die neueste Version Ihres Profils herunter. Wenn der Benutzer das Gerät auf die werkseitigen Standardeinstellungen zurücksetzt, lädt das Gerät erneut die neuesten Updates in Ihr Profil herunter. 
  
### <a name="edit-a-profile"></a>Bearbeiten eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**. 
    
2. Klicken Sie auf das Kontrollkästchen neben den Namen eines Geräts und im **Profil** Bereich aktualisieren, die verfügbaren Werte \> **Speichern**.
    
    Wenn Sie dies tun, bevor ein Benutzer das Gerät mit dem Internet verbindet, wird das Profil auf den Setupvorgang angewendet.
    
### <a name="delete-a-profile"></a>Löschen eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**. 
    
2. Klicken Sie auf das Kontrollkästchen neben dem Gerätenamen, und klicken Sie in der Systemsteuerung **Profil** auf **Profil löschen** \> **Speichern**.
    
    Wenn Sie ein Profil löschen, wird es von einem Gerät oder einer Gruppe von Geräten entfernt, denen es zugewiesen war.
    
### <a name="remove-a-profile"></a>Entfernen eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**. 
    
2. Klicken Sie auf das Kontrollkästchen neben den Namen eines Geräts und in der Systemsteuerung **Gerät** , wählen Sie **keine** aus der Dropdownliste **zugewiesene Profil** \> **Speichern**.
    
