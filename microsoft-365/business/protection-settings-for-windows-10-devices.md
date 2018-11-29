---
title: Festlegen von Anwendungsschutzeinstellungen für Windows 10-Geräte
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Informationen Sie zum Erstellen einer app Richtlinie zur Verwaltung und schützen Sie Arbeitsdateien auf Windows-10-Geräten.
ms.openlocfilehash: acf19a72d994185a35b2e425f8334a73a121ee10
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867761"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Festlegen von Anwendungsschutzeinstellungen für Windows 10-Geräte

## <a name="create-an-app-management-policy-for-windows-10"></a>Erstellen einer App-Verwaltungsrichtlinie für Windows 10

Wenn Ihre Benutzer Arbeitsaufgaben auf ihren privaten Windows 10-Geräte ausführen, können Sie Ihre Daten auch auf diesen Geräten schützen.
  
1. Melden Sie sich bei [Microsoft 365 Business](https://portal.office.com) mit globalen Administratoranmeldeinformationen an. Klicken Sie auf die Kachel **Admin**, um zum Admin Center zu wechseln. 
    
2. Wählen Sie auf der Karte **Geräterichtlinien** des Admin-Portals **Richtlinie hinzufügen** aus.
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein. 
    
4. Wählen Sie unter **Richtlinientyp** die Option **Anwendungsverwaltung für Windows 10** aus.
    
5. Klicken Sie unter ** Gerätetyp **, wählen Sie **Persönliche** oder **Unternehmen gehören**.
    
6. Die Option **Arbeitsdateien verschlüsseln** wird automatisch aktiviert. 
    
7. Aktivieren Sie die Optionen **Benutzer daran hindern, Unternehmensdaten in persönliche Dateien zu kopieren** und **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen**, wenn Sie nicht zulassen möchten, dass Benutzer Arbeitsdateien auf den eigenen PCs speichern. 
    
8. Erweitern Sie **den Zugriff von Benutzern auf Office-Dateien auf Geräten verwalten** \> konfigurieren Sie die Einstellungen wie möchten Sie. Der **Zugriff von Benutzern auf Office-Geräte auf mobilen Geräten verwalten** ist standardmäßig **deaktiviert** , aber es wird empfohlen, dass Sie **es aktivieren** , und übernehmen Sie die Standardwerte. Weitere Informationen finden Sie unter [Einstellungen verfügbar](protection-settings-for-windows-10-devices.md#bkmk_settings) . 
    
    Mit dem Link **Standardeinstellungen zurücksetzen** können Sie jederzeit die Standardeinstellungen wiederherstellen. 
    
9. Erweitern Sie **Daten auf Windows-Geräten wiederherstellen**, und es wird empfohlen, die Option zu **aktivieren**.
    
    Bevor Sie zum Speicherort des Zertifikats des Datenwiederherstellungs-Agent navigieren können, müssen Sie zuerst ein Zertifikat erstellen. Anweisungen finden Sie unter [Erstellen und Überprüfen eines DRA-Zertifikats (Data Recovery Agent, Datenwiederherstellungs-Agent) des verschlüsselnden Dateisystems (Encrypting File System, EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).
    
    Standardmäßig werden Arbeitsdateien mithilfe eines geheimen Schlüssels verschlüsselt, der auf dem Gerät gespeichert und mit dem Profil des Benutzers verknüpft ist. Nur der Benutzer kann die Datei öffnen und entschlüsseln. Wenn ein Gerät jedoch verloren geht oder ein Benutzers entfernt wird, kann eine Datei im verschlüsselten Zustand zurückbleiben. Das Zertifikat des Datenwiederherstellungs-Agents (DRA) kann von einem Administrator verwendet werden, um die Datei zu entschlüsseln.
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Erweitern Sie **Zusätzliche Netzwerk- und Cloudspeicherorte schützen**, wenn Sie weitere Domänen oder SharePoint Online-Speicherorte hinzufügen möchten, um sicherzustellen, dass Dateien in allen aufgelisteten Apps geschützt werden. Wenn Sie für eines der Felder mehr als ein Element eingeben müssen, verwenden Sie ein Semikolon (;) zwischen den Elementen. 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Als Nächstes entscheiden **erhalten, die diese Einstellungen?** Wenn Sie nicht die Standardsicherheitsgruppe für **Alle Benutzer** verwenden möchten, **Ändern**, wählen Sie die Sicherheitsgruppen, die diese Einstellungen erhalten \> **auswählen**.
    
12. Wählen Sie schließlich **Hinzufügen** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu. 
    
## <a name="available-settings"></a>Verfügbare Einstellungen

Mit den folgenden Einstellungen können Sie den Zugriff von Benutzern auf Office-Arbeitsdateien verwalten.
  
Weitere Informationen finden Sie unter [Zuordnung von Microsoft 365 Business-Schutzfunktionen zu Intune-Einstellungen](map-protection-features-to-intune-settings.md).
  
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern  <br/> |Ist diese Einstellung **aktiviert**, müssen Benutzer zusätzlich zum Benutzernamen und Kennwort eine andere Form der Authentifizierung angeben, bevor sie Office-Apps auf ihren mobilen Geräten verwenden können.  <br/> |
|PIN nach dieser Anzahl von fehlerhaften Anmeldeversuchen zurücksetzen  <br/> |Um zu verhindern, dass ein nicht autorisierter Benutzer eine PIN nach dem Zufallsprinzip errät, wird die PIN, die nach der angegebenen Anzahl von Fehlversuchen zurückgesetzt.  <br/> |
|Benutzer müssen sich erneut anmelden, nachdem Office-Apps im Leerlauf waren für  <br/> |Diese Einstellung bestimmt, wie lange ein Benutzer inaktiv sein kann, bevor er dazu aufgefordert wird, sich erneut anzumelden.  <br/> |
   

