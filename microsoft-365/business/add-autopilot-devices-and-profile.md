---
title: Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Erfahren Sie, wie Sie Windows autoPilot verwenden, um neue Windows 10-Geräte für Ihr Unternehmen einzurichten.
ms.openlocfilehash: e0802ddcc0964d0b8d102f7dbdb9116b33cdcf58
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277108"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen

[] Mit Windows AutoPilot können Sie neue Windows 10-Geräte für Ihr Unternehmen so einrichten, dass sie sofort nach Übergabe an Ihre Mitarbeiter produktiv eingesetzt werden können.
  
## <a name="device-requirements"></a>Geräteanforderungen

Geräte müssen diese Anforderungen erfüllen:
  
- Windows 10, Version 1703 oder höher.
    
- Neue Geräte, die nicht auf der Windows-Willkommensseite angezeigt werden.
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Befolgen der Setupanleitung zum Erstellen von Geräten und Profilen

Wenn Sie noch keine Gerätegruppen oder Profile erstellt haben, beginnen Sie am besten mit der schrittweisen Anleitung. Doch Sie können auch ohne die Anleitung [Geräte hinzufügen](create-and-edit-autopilot-devices.md) und ihnen [Profile zuweisen](create-and-edit-autopilot-profiles.md). 
  
1. Suchen Sie im Microsoft 365 Business Admin Center die Karte **Geräteaktionen**, und wählen Sie **Windows mit AutoPilot bereitstellen**.
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. Klicken oder tippen Sie auf der Seite **Windows vorbereiten** auf **Schnellstarthandbuch**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Navigieren Sie auf der Seite **CSV-Datei mit Liste der Geräte hochladen** zu den Speicherorten, an denen Sie die vorbereitete CSV-Datei gespeichert haben, und wählen Sie **Öffnen** \> **Weiter**. Die Datei sollte drei Überschriften aufweisen:
    
  - Spalte A: Seriennummer des Geräts
    
  - Spalte B: Windows-Produkt-ID
    
  - Spalte C: Hardwarehash
    
    Diese Informationen erhalten Sie von Ihrem Hardwareanbieter oder durch Verwendung des [PowerShell-Skripts Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), das eine CSV-Datei generiert. 
    
    Weitere Informationen finden Sie unter [CSV-Datei mit Geräteliste](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Sie können auf der Seite **CSV-Datei mit Liste der Geräte hochladen** auch eine Beispieldatei herunterladen. 
    
4. Auf der Seite **Profil zuweisen** können Sie entweder ein vorhandenes Profil auswählen oder ein neues Profil erstellen. Wenn Sie noch keines haben, werden Sie aufgefordert, ein neues zu erstellen. 
    
    Ein Profil ist eine Sammlung von Einstellungen, die für ein einzelnes Gerät oder eine Gruppe von Geräten gelten können.
    
    Die Standardfunktionen sind erforderlich und werden automatisch festgelegt. Es folgen die Standardfunktionen:
    
  - Cortana, OneDrive und OEM-Registrierung werden übersprungen.
    
  - Erstellen Sie eine Anmeldeumgebung mit Ihrem Unternehmensbranding.
    
  - Ihre Geräte werden mit Azure Active Directory-Konten verbunden und automatisch für die Verwaltung mit Microsoft 365 Business registriert.
    
    Weitere Informationen finden Sie unter
    
    [Informationen zu AutoPilot-Profileinstellungen](autopilot-profile-settings.md) . 
    
5. Die anderen Einstellungen sind **Datenschutzeinstellungen überspringen** und **Nicht zulassen, dass der Benutzer der lokale Administrator wird**. Beide sind standardmäßig auf **Aus** festgelegt. 
    
    Wählen Sie **Weiter** aus.
    
6. Die Seite **Fertig** zeigt an, dass das von Ihnen erstellte (oder ausgewählte) Profil auf die Gerätegruppe angewendet wird, die Sie durch das Hochladen der Liste der Geräte erstellt haben. Diese Einstellungen werden wirksam, wenn sich die Benutzer des Geräts als Nächstes wieder anmelden. Wählen Sie **Schließen** aus.
    