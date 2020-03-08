---
title: Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: In diesem Artikel erfahren Sie, wie Sie Windows Autopilot zum Einrichten neuer Windows 10-Geräte für Ihr Unternehmen verwenden, damit Sie für die Verwendung durch den Mitarbeiter verfügbar sind.
ms.openlocfilehash: 3b1cf297914862aaa74fdf9a8bb7290d00f73b1d
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561578"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen

Sie können Windows Autopilot verwenden, um **neue** Windows 10-Geräte für Ihr Unternehmen einzurichten, damit diese bereitgestellt werden, wenn Sie Sie an Ihre Mitarbeiter weitergeben.
  
## <a name="device-requirements"></a>Geräteanforderungen

Geräte müssen diese Anforderungen erfüllen:
  
- Windows 10, Version 1703 oder höher
    
- Neue Geräte, die die Out-of-Box-Erfahrung von Windows noch nicht durchlaufen haben
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Befolgen der Setupanleitung zum Erstellen von Geräten und Profilen

[![Hinweis, der Sie darüber informiert, dass sich das Admin Center ändert und Sie unter "aka.ms/aboutM365preview" weitere Details finden.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Wenn Sie noch keine Gerätegruppen oder Profile erstellt haben, ist die beste Möglichkeit, mit der ersten Schritte zu beginnen, die schrittweise Anleitung. Sie können auch [Geräte hinzufügen](create-and-edit-autopilot-devices.md) und Ihnen [profile zuweisen](create-and-edit-autopilot-profiles.md) , ohne die Anleitung zu verwenden. 
  
1. Wechseln Sie zum Admin Center auf <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Wählen Sie im linken Navigationsbereich **Geräte** \> **Autopilot**aus.

    ![Wählen Sie im Admin Center Geräte und dann Autopilot aus.](../media/AutoPilot.png)
  
2. Klicken oder tippen Sie auf der Seite **Autopilot** auf **Start Guide**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Navigieren Sie auf der Seite **Upload. CSV-Datei mit Geräteliste** zu einem Speicherort, an dem Sie die vorbereitete bereit haben. CSV-Datei, und **Öffnen** \> Sie dann **Next**. Die Datei muss drei Kopfzeilen aufweisen:
    
    - Spalte A: Seriennummer des Geräts
    
    - Spalte B: Windows-Produkt-ID
    
    - Spalte C: Hardwarehash
    
    Sie können diese Informationen von Ihrem Hardwareanbieter abrufen, oder Sie können das [PowerShell-Skript Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) verwenden, um eine CSV-Datei zu generieren. 
    
    Weitere Informationen finden Sie unter [CSV-Datei mit Geräteliste](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Sie können auf der Seite **CSV-Datei mit Liste der Geräte hochladen** auch eine Beispieldatei herunterladen. 
    
4. Auf der Seite **Profil zuweisen** können Sie entweder ein vorhandenes Profil auswählen oder einen neuen erstellen. Wenn Sie noch nicht über eine verfügen, werden Sie aufgefordert, eine zu erstellen. 
    
    Ein Profil ist eine Sammlung von Einstellungen, die für ein einzelnes Gerät oder eine Gruppe von Geräten gelten können.
    
    Die Standardfeatures sind erforderlich und werden automatisch festgelegt. Es folgen die Standardfunktionen:
    
    - Überspringen Sie Cortana, OneDrive und OEM-Registrierung.
    
    - Erstellen Sie eine Anmeldeumgebung mit Ihrem Unternehmensbranding.
    
    - Verbinden Sie Ihre Geräte mit Azure Active Directory-Konten, und registrieren Sie Sie automatisch für die Verwaltung durch Microsoft 365 Business.
    
    Weitere Informationen finden Sie unter [Informationen zu Autopilot-Profileinstellungen](autopilot-profile-settings.md). 
    
5. Die anderen Einstellungen sind **Datenschutzeinstellungen überspringen** und **Nicht zulassen, dass der Benutzer der lokale Administrator wird**. Beide sind standardmäßig auf **Aus** festgelegt. 
    
    Wählen Sie **Weiter** aus.
    
6. **Sie haben** angegeben, dass das Profil, das Sie erstellt (oder ausgewählt haben), auf die Gerätegruppe angewendet wird, die Sie durch Hochladen der Geräteliste erstellt haben. Die Einstellungen werden wirksam, wenn sich die Geräte Benutzer als nächstes anmelden. Wählen Sie **Schließen** aus.
    
