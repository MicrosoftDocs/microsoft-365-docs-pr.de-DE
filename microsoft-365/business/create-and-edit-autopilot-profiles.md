---
title: Erstellen und Bearbeiten von AutoPilot-Profilen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Hier erfahren Sie, wie Sie Autopilot-Profile erstellen, bearbeiten, löschen oder entfernen.
ms.openlocfilehash: f7fdc2632e93c48e043fe158842f8395d6a89e14
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320236"
---
# <a name="create-and-edit-autopilot-profiles"></a>Erstellen und Bearbeiten von AutoPilot-Profilen

## <a name="create-a-profile"></a>Erstellen eines Profils

Ein Profil gilt für ein Gerät oder eine Gerätegruppe.
  
1. Wählen Sie im Microsoft 365 Business Admin Center die Option **Geräte** \> **Autopilot**aus.
  
2. Klicken Sie auf der Seite **Autopilot** auf **** die Register \> Karte Profile Profil **Erstellen**.
    
3. Geben Sie auf der Seite **Profil erstellen** einen Namen für das Profil ein, das Sie bei der Identifizierung unterstützt, beispielsweise Marketing. Aktivieren Sie die gewünschte Einstellung, und wählen Sie dann **Speichern**aus. Weitere Informationen zu Autopilot-Profileinstellungen finden Sie unter [Informationen zu Autopilot-Profileinstellungen](autopilot-profile-settings.md).
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Zuweisen eines Profils zu einem Gerät

Nachdem Sie ein Profil erstellt haben, können Sie es auf ein Gerät oder eine Gruppe von Geräten anwenden. Sie können ein vorhandenes Profil in der [schrittweisen Anleitung](add-autopilot-devices-and-profile.md) auswählen und auf neue Geräte anwenden oder ein vorhandenes Profil für ein Gerät oder eine Gerätegruppe ersetzen. 
  
1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**. 
    
2. Aktivieren Sie das Kontrollkästchen neben einem Gerätenamen, und wählen Sie im **Geräte** Bereich ein Profil aus der Dropdownliste **** \> zugewiesenes Profil **Speichern**aus.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Bearbeiten, Löschen oder Entfernen eines Profils

Nachdem Sie einem Gerät ein Profil zugewiesen haben, können Sie es aktualisieren, auch wenn Sie das Gerät bereits einem Benutzer zugewiesen haben. Wenn sich das Gerät mit dem Internet verbindet, lädt es während des Setupvorgangs die neueste Version Ihres Profils herunter. Wenn der Benutzer das Gerät auf die werkseitigen Standardeinstellungen zurücksetzt, lädt das Gerät erneut die neuesten Updates in Ihr Profil herunter. 
  
### <a name="edit-a-profile"></a>Bearbeiten eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**. 
    
2. Aktivieren Sie das Kontrollkästchen neben einem Gerätenamen, und aktualisieren Sie im **Profil** Bereich alle verfügbaren Einstellungen \> **Speichern**.
    
    Wenn Sie dies tun, bevor ein Benutzer das Gerät mit dem Internet verbindet, wird das Profil auf den Setupvorgang angewendet.
    
### <a name="delete-a-profile"></a>Löschen eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**. 
    
2. Aktivieren Sie das Kontrollkästchen neben einem Gerätenamen, und wählen Sie im **Profil** Bereich die Option **Profil** \> **Speichern**löschen aus.
    
    Wenn Sie ein Profil löschen, wird es von einem Gerät oder einer Gruppe von Geräten entfernt, denen es zugewiesen war.
    
### <a name="remove-a-profile"></a>Entfernen eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**. 
    
2. Aktivieren Sie das Kontrollkästchen neben einem Gerätenamen, und wählen Sie im **Geräte** Bereich **keine** aus der Dropdownliste **** \> zugewiesenes Profil **Speichern**aus.
    
