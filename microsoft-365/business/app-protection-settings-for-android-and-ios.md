---
title: Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Informationen Sie zum Erstellen, bearbeiten oder löschen eine Richtlinie zur Verwaltung von app und Arbeitsdateien auf Android oder iOS-Geräten zu schützen.
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868129"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte

## <a name="create-an-app-management-policy"></a>Erstellen einer App-Verwaltungsrichtlinie

1. Melden Sie sich bei [Microsoft 365 Business](https://portal.office.com) mit globalen Administratoranmeldeinformationen an. 
    
2. Wählen Sie im Admin Center auf der Karte **Geräterichtlinien** die Option **Richtlinie hinzufügen** aus.
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein. 
    
4. Wählen Sie unter **Richtlinientyp** eine der Optionen **Anwendungsverwaltung für Android** oder **Anwendungsverwaltung für iOS** aus - je nachdem, welchen Richtliniensatz Sie erstellen möchten. 
    
5. Erweitern Sie **Protect Arbeitsdateien bei verlorenen oder gestohlenen Geräten sind** und **den Zugriff von Benutzern auf Office-Dateien auf mobilen Geräten verwalten** \> konfigurieren Sie die Einstellungen wie möchten Sie. Der **Zugriff von Benutzern auf Office-Dateien auf mobilen Geräten verwalten** ist standardmäßig **deaktiviert** , aber es wird empfohlen, dass Sie **es aktivieren** , und übernehmen Sie die Standardwerte. Weitere Informationen finden Sie unter [Einstellungen verfügbar](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) . 
    
    Mit dem Link **Standardeinstellungen zurücksetzen** können Sie jederzeit die Standardeinstellungen wiederherstellen. 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Als Nächstes entscheiden **erhalten, die diese Einstellungen?** Wenn Sie nicht die Standardsicherheitsgruppe für **Alle Benutzer** verwenden möchten, **Ändern**, wählen Sie die Sicherheitsgruppen, die diese Einstellungen erhalten \> **auswählen**.
    
7. Wählen Sie schließlich **Fertig** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu. 
    
## <a name="edit-an-app-management-policy"></a>Bearbeiten einer App-Verwaltungsrichtlinie

1. Wählen Sie auf der Karte **Richtlinien** **Richtlinie bearbeiten**.
    
2. Wählen Sie im Bereich **Richtlinie bearbeiten** die Richtlinie aus, die Sie ändern möchten. 
    
3. Wählen Sie neben jeder Einstellung **Bearbeiten** aus, um die Werte in der Richtlinie zu ändern. Wenn Sie einen Wert ändern, wird er in der Richtlinie automatisch gespeichert. 
    
4. Wenn Sie fertig sind, schließen Sie den Bereich **Richtlinie bearbeiten**. 
    
## <a name="delete-an-app-management-policy"></a>Löschen einer App-Verwaltungsrichtlinie

1. Wählen Sie auf der Registerkarte **Richtlinien** die Option **Richtlinie löschen** aus.
    
2. Wählen Sie die Richtlinien, die Sie löschen möchten, im Bereich **Löschrichtlinie** \> **Wählen**und dann **bestätigen** , löschen die Richtlinie oder Richtlinien, die Sie ausgewählt haben. 
    
## <a name="available-settings"></a>Verfügbare Einstellungen

Die nachstehenden Tabellen enthalten detaillierte Informationen zu den verfügbaren Einstellungen zum Schutz von Arbeitsdateien auf Geräten und den Einstellungen zur Steuerung, wie Benutzer über ihre mobilen Geräte auf Office-Dateien zugreifen können.
  
 Weitere Informationen finden Sie unter [Zuordnung von Microsoft 365 Business-Schutzfunktionen zu Intune-Einstellungen](map-protection-features-to-intune-settings.md). 
  
### <a name="settings-that-protect-work-files"></a>Einstellungen zum Schutz von Arbeitsdateien

Die folgenden Einstellungen stehen zum Schutz von Arbeitsdateien zur Verfügung, wenn das Gerät eines Benutzers verloren geht oder gestohlen wird:
  
|||
|:-----|:-----|
|Einstellung  <br/> |Beschreibung  <br/> |
|Arbeitsdateien von einem inaktiven Gerät löschen nach diesem Zeitraum (Tage)  <br/> |Wenn ein Gerät während der hier festgelegten Anzahl von Tagen nicht genutzt wird, werden alle auf dem Gerät gespeicherten Arbeitsdateien automatisch gelöscht.  <br/> |
|Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen  <br/> |Wenn diese Einstellung auf **Ein** festgelegt wurde, ist der einzige verfügbare Speicherort für Arbeitsdateien OneDrive for Business.  <br/> |
|Arbeitsdateien verschlüsseln  <br/> |Behalten Sie für diese Einstellung **Ein** bei, damit Arbeitsdateien durch Verschlüsselung geschützt werden. Selbst wenn das Gerät verloren geht oder gestohlen wird, kann niemand Ihre Unternehmensdaten lesen.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Einstellungen, die steuern, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen

Mit den folgenden Einstellungen können Sie den Zugriff von Benutzern auf Office-Arbeitsdateien verwalten:
  
|||
|:-----|:-----|
|Einstellung  <br/> |Beschreibung  <br/> |
|Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern  <br/> |Ist diese Einstellung **aktiviert**, müssen Benutzer zusätzlich zum Benutzernamen und Kennwort eine andere Form der Authentifizierung angeben, bevor sie Office-Apps auf ihren mobilen Geräten verwenden können.  <br/> |
|PIN nach dieser Anzahl von fehlerhaften Anmeldeversuchen zurücksetzen  <br/> |Um zu verhindern, dass ein nicht autorisierter Benutzer eine PIN nach dem Zufallsprinzip errät, wird die PIN, die nach der angegebenen Anzahl von Fehlversuchen zurückgesetzt.  <br/> |
|Benutzer müssen sich erneut anmelden, nachdem Office-Apps im Leerlauf waren für  <br/> |Diese Einstellung bestimmt, wie lange ein Benutzer inaktiv sein kann, bevor er dazu aufgefordert wird, sich erneut anzumelden.  <br/> |
|Zugriff auf Arbeitsdateien auf Geräten mit entfernten Nutzungsbeschränkungen verweigern  <br/> |Clevere Benutzer verfügen möglicherweise über ein Gerät, bei dem die Nutzungsbeschränkungen entfernt wurden. Dies bedeutet, dass der Benutzer das Betriebssystem ändern kann, wodurch das Gerät empfänglicher für Schadsoftware werden kann. Solche Geräte können gesperrt werden, wenn die Einstellung auf **Ein** festgelegt wurde.  <br/> |
|Benutzern das Kopieren von Inhalten aus Office-Apps in persönliche Apps erlauben  <br/> |Wir lassen dies standardmäßig, jedoch ist die Einstellung **auf**der Benutzer konnte Informationen in einer Datei in eine persönliche Datei kopieren. Wenn die Einstellung **deaktiviert**ist, kann der Benutzer kann nicht zum Kopieren von Informationen aus einem Konto Arbeit in einer persönlichen app oder persönliches Konto verwendet.<br/> |
   

  

