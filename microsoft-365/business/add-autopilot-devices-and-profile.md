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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Erfahren Sie, wie Sie mit Windows AutoPilot neue Windows 10-Geräte für Ihr Unternehmen einrichten, damit sie für die Verwendung durch Mitarbeiter bereit sind.
ms.openlocfilehash: f263cc90656ae5e7be1a89e3c7f56bfb2d0e3651
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099748"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen

Sie können Windows AutoPilot verwenden, um neue **Windows** 10-Geräte für Ihr Unternehmen so zu einrichten, dass sie einsatzbereit sind, wenn Sie sie Ihren Mitarbeitern zur Verfügung stellen.
  
## <a name="device-requirements"></a>Geräteanforderungen

Geräte müssen diese Anforderungen erfüllen:
  
- Windows 10, Version 1703 oder höher
    
- Neue Geräte, die die Windows-Out-of-Box-Erfahrung noch nicht verwendet haben
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Befolgen der Setupanleitung zum Erstellen von Geräten und Profilen

[![Hinweis, der Sie darüber informiert, dass sich das Admin Center ändert und Sie unter "aka.ms/aboutM365preview" weitere Details finden.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Wenn Sie noch keine Gerätegruppen oder Profile erstellt haben, können Sie am besten mit der schrittweisen Anleitung beginnen. Sie können auch [Geräte hinzufügen](create-and-edit-autopilot-devices.md) und [ihnen Profile](create-and-edit-autopilot-profiles.md) zuweisen, ohne die Anleitung zu verwenden. 
  
1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Wählen Sie im linken Navigationsbereich **"Geräte** \> **AutoPilot" aus.**

    ![Wählen Sie im Admin Center Geräte und dann AutoPilot aus.](../media/AutoPilot.png)
  
2. Klicken oder tippen Sie auf der Seite **"AutoPilot"** auf **"Starthandbuch".**
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Navigieren Sie **auf der Seite "CSV-Datei mit** Liste der Geräte hochladen" zu einem Speicherort, an dem Sie die vorbereitet haben. CSV-Datei, dann **Öffnen Sie** \> **"Weiter".** Die Datei muss drei Kopfzeilen enthalten:
    
    - Spalte A: Seriennummer des Geräts
    
    - Spalte B: Windows-Produkt-ID
    
    - Spalte C: Hardwarehash
    
    Sie können diese Informationen von Ihrem Hardwareanbieter erhalten, oder Sie können das [Get-WindowsAutoPilotInfo -PowerShell-Skript](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) verwenden, um eine CSV-Datei zu generieren. 
    
    Weitere Informationen finden Sie unter [CSV-Datei mit Geräteliste](https://docs.microsoft.com/microsoft-365/admin/misc/device-list). Sie können auf der Seite **CSV-Datei mit Liste der Geräte hochladen** auch eine Beispieldatei herunterladen. 
    
> [!NOTE]
> Dieses Skript verwendet WMI zum Abrufen von Eigenschaften, die ein Kunde zum Registrieren eines Geräts bei Windows Autopilot benötigt. Beachten Sie, dass es normal ist, dass die resultierende #A0 keinen Windows Product ID (PKID)-Wert sammelt, da dies nicht erforderlich ist, um ein Gerät zu registrieren, und PKID, die NULL in der Ausgabe-CSV ist, völlig in Ordnung ist. Nur die Seriennummer und der Hardwarehash werden aufgefüllt.
    
4. Auf der **Seite "Profil zuweisen"** können Sie entweder ein vorhandenes Profil auswählen oder ein neues erstellen. Wenn Sie noch keines haben, werden Sie aufgefordert, eine zu erstellen. 
    
    Ein Profil ist eine Sammlung von Einstellungen, die für ein einzelnes Gerät oder eine Gruppe von Geräten gelten können.
    
    Die Standardfeatures sind erforderlich und werden automatisch festgelegt. Es folgen die Standardfunktionen:
    
    - Überspringen Sie die Cortana-, OneDrive- und OEM-Registrierung.
    
    - Erstellen Sie eine Anmeldeumgebung mit Ihrem Unternehmensbranding.
    
    - Verbinden Sie Ihre Geräte mit Azure Active Directory-Konten, und registrieren Sie sie automatisch, damit sie von Microsoft 365 Business Premium verwaltet werden.
    
    Weitere Informationen finden Sie unter ["Informationen zu AutoPilot-Profileinstellungen".](autopilot-profile-settings.md) 
    
5. Die anderen Einstellungen sind **Datenschutzeinstellungen überspringen** und **Nicht zulassen, dass der Benutzer der lokale Administrator wird**. Beide sind standardmäßig auf **Aus** festgelegt. 
    
    Wählen Sie **Weiter** aus.
    
6. **Sie sind fertig und** geben an, dass das profil, das Sie erstellt (oder ausgewählt) haben, auf die Gerätegruppe angewendet wird, die Sie durch Hochladen der Geräteliste erstellt haben. Die Einstellungen werden wirksam, wenn sich die Gerätebenutzer als Nächstes anmelden. Wählen Sie **Schließen** aus.
    
