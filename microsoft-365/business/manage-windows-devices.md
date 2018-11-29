---
title: Aktivieren Sie in die Domäne eingebundener Windows 10 Geräte von Microsoft 365 Business verwaltet werden
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Erfahren Sie, wie Microsoft 365 schützen aktivieren lokalen AD Windows 10 Geräte verbunden.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867708"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Aktivieren Sie in die Domäne eingebundener Windows 10 Geräte von Microsoft 365 Business verwaltet werden

Wenn Ihre Organisation Windows Server Active Directory lokalen verwendet wird, können Sie Microsoft 365 Business zum Schutz Ihrer Windows 10 Geräte bei gleichzeitiger Wahrung der Zugriff auf lokale Ressourcen, die erfordern lokale Authentifizierung festlegen. Sie können dies richten Sie durch die erste Synchronisierung Ihrer Active Directory mit Azure Active Directory, gefolgt von den Windows-10-Geräten mit Azure Active Directory registrieren und registrieren sie für die Verwaltung von mobilen Geräten von Microsoft 365 Business.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Einrichten von Geräten in die Domäne eingebundener von Microsoft 365 Business verwaltet werden

Zum Einrichten Ihrer Organisation in die Domäne eingebundener Geräte profitieren von der Funktionen von Azure Active Directory zusätzlich zur lokalen Active Directory können Sie **Hybrid Azure AD verbunden Geräte**implementieren. Dies sind Geräte, die sowohl die lokale Active Directory und die Azure Active Directory verbunden sind. Hybride beigetreten Azure AD-Geräte können geschützt und Microsoft 365 Business verwaltet werden. 
  
Führen Sie die Schritte unten, um Ihre Windows 10 Geräte Hybrid Azure AD beigetreten und verwaltet von Microsoft 365 Business stellen.
  
1. Führen Sie zum Synchronisieren der Benutzer, Gruppen und Kontakte aus der lokalen Active Directory in Azure Active Directory den Assistenten für verzeichnissynchronisierung und Azure Active Directory verbinden gemäß [Directory-Synchronisierung für Office 365 einrichten](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > Die Schritte sind exakt identisch für Microsoft 365 Business. 
  
2. Bevor Sie Schritt 3, um Windows 10 Geräte können Hybrid werden Azure AD beigetreten ist abgeschlossen haben, müssen Sie sicherstellen, dass Sie die folgenden Anforderungen erfüllen:
    
   - Sie arbeiten mit die neueste Version von Azure Active Directory verbinden.
    
   - Verbinden von Azure Active Directory synchronisiert hat die Computerobjekte der Geräte Hybrid werden Azure AD verknüpft werden soll. Eine Verbindung herstellen Sie sowie, wenn die Computerobjekte zu bestimmten Organisationseinheiten (OE) gehören, stellen Sie sicher, dass diese OUs für Azure AD-Synchronisierung festgelegt sind.
    
3. Registrieren Sie die vorhandenen Domäne eingebundener Windows 10 Geräte Hybrid Azure AD-beigetreten und für die Verwaltung von mobilen Geräten von Intune (Microsoft 365 Business) zu registrieren:
    
4. Befolgen Sie die Schritt-für-Schritt-Anweisungen unter [How to configure Hybrid Azure Active Directory verbunden Geräte](https://go.microsoft.com/fwlink/p/?linkid=872870)aus. Auf diese Weise können die Synchronisierung der lokalen Active Directory beigetreten Windows 10 Computern und stellen sie die cloud bereit.
    
5. Um ein Windows-10-Gerät für die Verwaltung von mobilen Geräten zu registrieren, finden Sie unter [registrieren ein Geräts Windows 10 mit Intune mithilfe einer Gruppenrichtlinie](https://go.microsoft.com/fwlink/p/?linkid=872871) Anweisungen. Sie können die Gruppenrichtlinie auf einem lokalen Computer Ebene oder für Massenvorgänge, können Sie diese gruppenrichtlinieneinstellung auf Ihre Domänencontrollerserver erstellen. 
    

