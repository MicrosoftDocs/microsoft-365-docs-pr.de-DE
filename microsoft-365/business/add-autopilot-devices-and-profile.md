---
title: Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Erfahren Sie, wie Sie Windows AutoPilot zum Einrichten neuer Windows 10-Geräte für Ihr Unternehmen verwenden, damit sie für die Verwendung durch Mitarbeiter bereit sind.
ms.openlocfilehash: cd8777e6ae2e395506d2bf308c99309de1e24805
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578525"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen

Sie können Windows AutoPilot verwenden, um neue **Windows** 10-Geräte für Ihr Unternehmen zu einrichten, damit sie einsatzbereit sind, wenn Sie sie Ihren Mitarbeitern zur Verfügung stellen.
  
## <a name="device-requirements"></a>Geräteanforderungen

Geräte müssen die folgenden Anforderungen erfüllen:
  
- Windows 10, Version 1703 oder höher
    
- Neue Geräte, die windows-out-of-box noch nicht erlebt haben
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Befolgen der Setupanleitung zum Erstellen von Geräten und Profilen

[![Hinweis, der Sie darüber informiert, dass sich das Admin Center ändert und Sie unter "aka.ms/aboutM365preview" weitere Details finden.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)

Wenn Sie noch keine Gerätegruppen oder Profile erstellt haben, können Sie am besten die schrittweise Anleitung verwenden. Sie können auch [Geräte hinzufügen](create-and-edit-autopilot-devices.md) und [ihnen Profile](create-and-edit-autopilot-profiles.md) zuweisen, ohne die Anleitung zu verwenden. 
  
1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Wählen Sie im linken Navigationsbereich **Geräte** \> **AutoPilot aus.**

    ![Wählen Sie im Admin Center Geräte und dann AutoPilot aus.](../media/AutoPilot.png)
  
2. Klicken oder tippen Sie auf der Seite **AutoPilot** auf **Start guide**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Navigieren Sie auf der Seite **CSV-Datei mit** Liste der Geräte hochladen zu einem Speicherort, an dem Sie die vorbereitet haben. CSV-Datei, dann **Öffnen Sie** \> **Weiter**. Die Datei muss drei Kopfzeilen enthalten:
    
    - Spalte A: Seriennummer des Geräts
    
    - Spalte B: Windows-Produkt-ID
    
    - Spalte C: Hardwarehash
    
    Sie können diese Informationen vom Hardwareanbieter abrufen oder das [Get-WindowsAutoPilotInfo PowerShell-Skript](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) verwenden, um eine CSV-Datei zu generieren. 
    
    Weitere Informationen finden Sie unter [CSV-Datei mit Geräteliste](../admin/misc/device-list.md). Sie können auf der Seite **CSV-Datei mit Liste der Geräte hochladen** auch eine Beispieldatei herunterladen. 
    
> [!NOTE]
> Dieses Skript verwendet WMI, um Eigenschaften abzurufen, die für einen Kunden zum Registrieren eines Geräts bei Windows Autopilot erforderlich sind. Beachten Sie, dass es normal ist, dass die resultierende #A0 keinen #A1 (Windows Product ID) sammelt, da dies nicht erforderlich ist, um ein Gerät zu registrieren, und PKID, die NULL in der Ausgabe-CSV ist, ist vollkommen in Ordnung. Nur die Seriennummer und der Hardwarehash werden aufgefüllt.
    
4. Auf der **Seite Profil zuweisen** können Sie entweder ein vorhandenes Profil auswählen oder ein neues erstellen. Wenn Sie noch keines haben, werden Sie aufgefordert, eine zu erstellen. 
    
    Ein Profil ist eine Sammlung von Einstellungen, die für ein einzelnes Gerät oder eine Gruppe von Geräten gelten können.
    
    Die Standardfeatures sind erforderlich und werden automatisch festgelegt. Es folgen die Standardfunktionen:
    
    - Überspringen Der Registrierung von Cortana, OneDrive und OEM.
    
    - Erstellen Sie eine Anmeldeumgebung mit Ihrem Unternehmensbranding.
    
    - Verbinden Sie Ihre Geräte mit Azure Active Directory-Konten, und registrieren Sie sie automatisch, damit sie von Microsoft 365 Business Premium verwaltet werden.
    
    Weitere Informationen finden Sie unter [Informationen zu AutoPilot-Profileinstellungen](autopilot-profile-settings.md). 
    
5. Die anderen Einstellungen sind **Datenschutzeinstellungen überspringen** und **Nicht zulassen, dass der Benutzer der lokale Administrator wird**. Beide sind standardmäßig auf **Aus** festgelegt. 
    
    Wählen Sie **Weiter** aus.
    
6. **Sie sind fertig,** gibt an, dass das profil, das Sie erstellt (oder ausgewählt) haben, auf die Gerätegruppe angewendet wird, die Sie erstellt haben, indem Sie die Liste der Geräte hochladen. Die Einstellungen werden wirksam, wenn sich die Gerätebenutzer als Nächstes anmelden. Wählen Sie **Schließen** aus.
