---
title: Aktivieren von Domänenbeitritt zu Windows 10-Geräten, die von Microsoft 365 Business verwaltet werden
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Erfahren Sie, wie Sie mit Microsoft 365 lokale AD-verbundene Windows 10-Geräte schützen können.
ms.openlocfilehash: d61b3bf6be50d6b21e7b883774567bb63995e60e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278075"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Aktivieren von Domänenbeitritt zu Windows 10-Geräten, die von Microsoft 365 Business verwaltet werden

Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business einrichten, um Ihre Windows 10-Geräte zu schützen, ohne dabei den Zugriff auf lokale Ressourcen zu gewährleisten, die lokal authentifiziert werden müssen. Sie können dies einrichten, indem Sie zunächst Ihr Active Directory mit Azure Active Directory synchronisieren, gefolgt von der Registrierung der Windows 10-Geräte mit Azure AD und der Anmeldung für die Verwaltung mobiler Geräte durch Microsoft 365 Business.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Einrichten von Domänen verbundenen Geräten, die von Microsoft 365 Business verwaltet werden

Zum Einrichten der Domänen verbundenen Geräte Ihrer Organisation, die zusätzlich zu lokalen Active Directory-Funktionen von Azure Active Directory bereitgestellt werden, können Sie **hybride Azure AD-verbundene Geräte**implementieren. Dabei handelt es sich um Geräte, die sowohl mit Ihrem lokalen Active Directory als auch mit Ihrem Azure Active Directory verbunden sind. Hybride Azure AD-verbundene Geräte können von Microsoft 365 Business geschützt und verwaltet werden. 
  
Führen Sie die folgenden Schritte aus, um Ihre Windows 10-Geräte Hybrid Azure AD zu verbinden und von Microsoft 365 Business zu verwalten.
  
1. Führen Sie den Assistenten für die Verzeichnissynchronisierung und Azure Active Directory Connect wie unter [Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)beschrieben aus, um Ihre Benutzer, Gruppen und Kontakte aus dem lokalen Active Directory in Azure Active Directory zu synchronisieren.
    
    > [!NOTE]
    > Die Schritte sind für Microsoft 365 Business identisch. 
  
2. Bevor Sie Schritt 3 abschließen, um Windows 10-Geräte als Hybriden Azure AD-Beitritt zu aktivieren, müssen Sie sicherstellen, dass die folgenden Voraussetzungen erfüllt sind:
    
   - Sie führen die neueste Version von Azure AD Connect aus.
    
   - Azure AD Connect hat alle Computerobjekte der Geräte synchronisiert, für die eine hybride Azure AD-Verknüpfung verwendet werden soll. Wenn die Computerobjekte zu bestimmten Organisationseinheiten (OU) gehören, stellen Sie sicher, dass diese OUs auch für die Synchronisierung in Azure AD Connect festgelegt sind.
    
3. Registrieren Sie vorhandene mit der Domäne verbundene Windows 10-Geräte als hybrides Azure AD-Mitglied, und registrieren Sie Sie für die Verwaltung mobiler Geräte von InTune (Microsoft 365 Business):
    
4. BeFolgen Sie die Schritt-für-Schritt-Anweisungen unter [How to configure Hybrid Azure Active Directory Joined Devices](https://go.microsoft.com/fwlink/p/?linkid=872870). Dadurch wird die Synchronisierung Ihrer lokalen Active Directory-Verbindung mit Windows 10-Computern aktiviert, sodass diese Cloud-fähig ist.
    
5. Informationen zum Registrieren eines Windows 10-Geräts für die Verwaltung mobiler Geräte finden Sie unter [Registrieren eines Windows 10-Geräts mit InTune mithilfe einer Gruppenrichtlinie](https://go.microsoft.com/fwlink/p/?linkid=872871) . Sie können die Gruppenrichtlinie auf lokaler Computerebene oder für Massenvorgänge festlegen, indem Sie diese Gruppenrichtlinieneinstellung auf dem Domänencontrollerserver erstellen. 
    

