---
title: Erstellen und Bearbeiten von AutoPilot-Profilen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Erfahren Sie, wie Sie ein AutoPilot-Profil erstellen und auf ein Gerät anwenden sowie ein Profil bearbeiten oder löschen oder ein Profil von einem Gerät entfernen.
ms.openlocfilehash: 414243da88fb6f39f8e6067d19d49ffe955f725f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580252"
---
# <a name="create-and-edit-autopilot-profiles"></a>Erstellen und Bearbeiten von AutoPilot-Profilen

## <a name="create-a-profile"></a>Erstellen eines Profils

Ein Profil gilt für ein Gerät oder eine Gerätegruppe.
  
1. Wählen Sie im Microsoft 365 Admin Center **Geräte** \> **AutoPilot aus.**
  
2. Wählen Sie **auf der Seite AutoPilot** die **Registerkarte** Profile profil \> **erstellen aus.**
    
3. Geben Sie **auf der** Seite Profil erstellen einen Namen für das Profil ein, mit dem Sie es identifizieren können, z. B. Marketing. Aktivieren Sie die einstellung, die Sie möchten, und wählen Sie dann **Speichern aus.** Weitere Informationen zu AutoPilot-Profileinstellungen finden Sie unter [Informationen zu AutoPilot-Profileinstellungen](autopilot-profile-settings.md).
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Zuweisen eines Profils zu einem Gerät

Nachdem Sie ein Profil erstellt haben, können Sie es auf ein Gerät oder eine Gruppe von Geräten anwenden. Sie können ein vorhandenes [](add-autopilot-devices-and-profile.md) Profil in der schrittweisen Anleitung auswählen und auf neue Geräte anwenden oder ein vorhandenes Profil für ein Gerät oder eine Gruppe von Geräten ersetzen. 
  
1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**. 
    
2. Aktivieren Sie das Kontrollkästchen neben einem  Gerätenamen, und wählen  Sie im Gerätebereich ein Profil aus der Dropdownliste Zugewiesenes Profil \> **speichern aus.**
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Bearbeiten, Löschen oder Entfernen eines Profils

Nachdem Sie einem Gerät ein Profil zugewiesen haben, können Sie es aktualisieren, auch wenn Sie das Gerät bereits einem Benutzer zugewiesen haben. Wenn sich das Gerät mit dem Internet verbindet, lädt es während des Setupvorgangs die neueste Version Ihres Profils herunter. Wenn der Benutzer das Gerät auf die werkseitigen Standardeinstellungen zurücksetzt, lädt das Gerät erneut die neuesten Updates in Ihr Profil herunter. 
  
### <a name="edit-a-profile"></a>Bearbeiten eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**. 
    
2. Aktivieren Sie das Kontrollkästchen neben einem Gerätenamen, und aktualisieren Sie im **Profilbereich** alle verfügbaren Einstellungen \> **Speichern**.
    
    Wenn Sie dies tun, bevor ein Benutzer das Gerät mit dem Internet verbindet, wird das Profil auf den Setupvorgang angewendet.
    
### <a name="delete-a-profile"></a>Löschen eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**. 
    
2. Aktivieren Sie das Kontrollkästchen neben einem Gerätenamen, und wählen Sie im **Profilbereich** Profil **speichern** \> **aus.**
    
    Wenn Sie ein Profil löschen, wird es von einem Gerät oder einer Gruppe von Geräten entfernt, denen es zugewiesen war.
    
### <a name="remove-a-profile"></a>Entfernen eines Profils

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**. 
    
2. Aktivieren Sie das Kontrollkästchen neben einem  Gerätenamen, und wählen  Sie im Gerätebereich in der Dropdownliste Zugewiesenes Profil Speichern die Option **Keine** \> **aus.**
    
