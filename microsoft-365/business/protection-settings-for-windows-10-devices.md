---
title: Festlegen von Anwendungsschutzeinstellungen für Windows 10-Geräte
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
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
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Hier erfahren Sie, wie Sie eine APP-Verwaltungsrichtlinie erstellen und Arbeitsdateien auf den persönlichen Windows 10-Geräten Ihrer Benutzer schützen.
ms.openlocfilehash: c3e003205da30fa79069946960ef00e4195f0cbc
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44386535"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Festlegen von Anwendungsschutzeinstellungen für Windows 10-Geräte

## <a name="create-an-app-management-policy-for-windows-10"></a>Erstellen einer App-Verwaltungsrichtlinie für Windows 10

Wenn Ihre Benutzer Arbeitsaufgaben auf ihren privaten Windows 10-Geräte ausführen, können Sie Ihre Daten auch auf diesen Geräten schützen.
  
1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. Wählen Sie im linken Navigationsbereich **Geräte** \> **Richtlinien** \> **Hinzufügen**aus.

3. Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein. 
    
4. Wählen Sie unter **Richtlinientyp** die Option **Anwendungsverwaltung für Windows 10** aus.
    
5. Wählen Sie unter **Gerätetyp**entweder **persönlich** oder **Unternehmensbesitz**aus.
    
6. Die Option **Arbeitsdateien verschlüsseln** wird automatisch aktiviert. 
    
7. Aktivieren Sie die Optionen **Benutzer daran hindern, Unternehmensdaten in persönliche Dateien zu kopieren** und **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen**, wenn Sie nicht zulassen möchten, dass Benutzer Arbeitsdateien auf den eigenen PCs speichern. 
    
9. Erweitern Sie **Wiederherstellungsdaten auf Windows-Geräten**. Es **wird empfohlen, dass Sie es**aktivieren.
    
    Bevor Sie zum Speicherort des Zertifikats des Datenwiederherstellungs-Agent navigieren können, müssen Sie zuerst ein Zertifikat erstellen. Anweisungen finden Sie unter [Erstellen und Überprüfen eines Daten Wiederherstellungs-Agents (DRA)-Zertifikats für das verschlüsselnde Datei System (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).
    
    Standardmäßig werden Arbeitsdateien mithilfe eines geheimen Schlüssels verschlüsselt, der auf dem Gerät gespeichert und mit dem Profil des Benutzers verknüpft ist. Nur der Benutzer kann die Datei öffnen und entschlüsseln. Wenn ein Gerät jedoch verloren geht oder ein Benutzers entfernt wird, kann eine Datei im verschlüsselten Zustand zurückbleiben. Ein Administrator kann das DRA-Zertifikat (Data Recovery Agent) zum Entschlüsseln der Datei verwenden.
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Erweitern Sie **Protect additional Network and Cloud Locations** , wenn Sie zusätzliche Domänen oder SharePoint Online Speicherorte hinzufügen möchten, um sicherzustellen, dass die Dateien in allen aufgeführten apps geschützt sind. Wenn Sie für eines der Felder mehr als ein Element eingeben müssen, verwenden Sie ein Semikolon (;) zwischen den Elementen.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.
    
12. Wählen Sie schließlich **Hinzufügen** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu. 
