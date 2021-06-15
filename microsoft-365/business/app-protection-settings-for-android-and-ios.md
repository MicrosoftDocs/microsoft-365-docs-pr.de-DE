---
title: Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Erfahren Sie, wie Sie eine App-Verwaltungsrichtlinie erstellen, bearbeiten oder löschen und Arbeitsdateien auf Android- oder iOS-Geräten schützen.
ms.openlocfilehash: 92dce1e8761e53b85df85f2a84f30ab307f63e6d
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925061"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte

Dieser Artikel bezieht sich auf Microsoft 365 Business Premium.

## <a name="create-an-app-management-policy"></a>Erstellen einer App-Verwaltungsrichtlinie

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. Wählen Sie im linken Navigationsbereich **"Geräterichtlinien** \>  \> **hinzufügen"** aus.
  
3. Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein. 
    
4. Wählen Sie unter **"Richtlinientyp"** die **Option "Anwendungsverwaltung für Android"** oder **"Anwendungsverwaltung für iOS"** aus, je nachdem, welchen Richtliniensatz Sie erstellen möchten. 
    
5. Erweitern Sie **"Arbeitsdateien schützen", wenn Geräte verloren gehen oder gestohlen werden,** und **verwalten Sie, wie Benutzer auf Office Dateien auf mobilen Geräten zugreifen.** Konfigurieren Sie die gewünschten Einstellungen. **Verwalten Sie, wie Benutzer auf Office Dateien auf mobilen Geräten** standardmäßig **deaktiviert** sind. Es wird jedoch empfohlen, sie **zu** aktivieren und die Standardwerte zu akzeptieren. Weitere Informationen finden Sie unter [Verfügbare Einstellungen.](#available-settings) 
    
    Mit dem Link **Standardeinstellungen zurücksetzen** können Sie jederzeit die Standardeinstellungen wiederherstellen. 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Next decide **Who will get these settings?** Wenn Sie die Standardsicherheitsgruppe **"Alle Benutzer"** nicht verwenden möchten, wählen Sie **"Ändern"** aus, und wählen Sie die Sicherheitsgruppen aus, die diese Einstellungen \> **auswählen.**
    
7. Wählen Sie schließlich **Fertig** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu. 
    
## <a name="edit-an-app-management-policy"></a>Bearbeiten einer App-Verwaltungsrichtlinie

1. Wählen Sie auf der Karte **"Richtlinien"** die Option **"Richtlinie bearbeiten"** aus.
    
2. Wählen Sie im Bereich **Richtlinie bearbeiten** die Richtlinie aus, die Sie ändern möchten. 
    
3. Wählen Sie neben jeder Einstellung **Bearbeiten** aus, um die Werte in der Richtlinie zu ändern. Wenn Sie einen Wert ändern, wird er automatisch in der Richtlinie gespeichert.
    
4. Schließen Sie nach Abschluss des Vorgangs den **Bereich "Richtlinie bearbeiten".** 
    
## <a name="delete-an-app-management-policy"></a>Löschen einer App-Verwaltungsrichtlinie

1. Wählen Sie auf der Seite **"Richtlinien"** eine Richtlinie aus, und **löschen Sie** dann .
    
2. Wählen Sie im **Bereich "Richtlinie löschen"** die Option **"Bestätigen"** aus, um die von Ihnen gewählte Richtlinie oder Richtlinien zu löschen. 
    
## <a name="available-settings"></a>Verfügbare Einstellungen

Die folgenden Tabellen enthalten ausführliche Informationen zu den verfügbaren Einstellungen zum Schutz von Arbeitsdateien auf Geräten sowie zu den Einstellungen, die steuern, wie Benutzer von ihren mobilen Geräten aus auf Office Dateien zugreifen.
  
 Weitere Informationen finden Sie unter [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md). 
  
### <a name="settings-that-protect-work-files"></a>Einstellungen zum Schutz von Arbeitsdateien

Die folgenden Einstellungen stehen zum Schutz von Arbeitsdateien zur Verfügung, wenn das Gerät eines Benutzers verloren geht oder gestohlen wird:


|Einstellung  <br/> |Beschreibung  <br/> |
|:-----|:-----|
|Arbeitsdateien von einem inaktiven Gerät löschen nach diesem Zeitraum (Tage)  <br/> |Wenn ein Gerät für die Hier angegebene Anzahl von Tagen nicht verwendet wird, werden alle auf dem Gerät gespeicherten Arbeitsdateien automatisch gelöscht.  <br/> |
|Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen  <br/> |Wenn diese Einstellung **aktiviert** ist, ist der einzige verfügbare Speicherort für Arbeitsdateien OneDrive for Business.  <br/> |
|Arbeitsdateien verschlüsseln  <br/> |Behalten Sie für diese Einstellung **Ein** bei, damit Arbeitsdateien durch Verschlüsselung geschützt werden. Auch wenn das Gerät verloren geht oder gestohlen wird, kann niemand Ihre Unternehmensdaten lesen.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Einstellungen, die steuern, wie Benutzer auf mobilen Geräten auf Office-Dateien zugreifen

Mit den folgenden Einstellungen können Sie den Zugriff von Benutzern auf Office-Arbeitsdateien verwalten:


|Einstellung  <br/> |Beschreibung  <br/> |
|:-----|:-----|
|Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern  <br/> |Wenn diese Einstellung **aktiviert** ist, müssen Benutzer zusätzlich zu ihrem Benutzernamen und Kennwort eine andere Authentifizierungsform bereitstellen, bevor sie Office Apps auf ihren mobilen Geräten verwenden können.<br/> |
|PIN nach dieser Anzahl von fehlerhaften Anmeldeversuchen zurücksetzen  <br/> |Um zu verhindern, dass ein nicht autorisierter Benutzer eine PIN nach dem Zufallsprinzip errät, wird die PIN, die nach der angegebenen Anzahl von Fehlversuchen zurückgesetzt.  <br/> |
|Benutzer müssen sich erneut anmelden, nachdem Office-Apps im Leerlauf waren für  <br/> |Diese Einstellung bestimmt, wie lange sich ein Benutzer im Leerlauf befinden kann, bevor er aufgefordert wird, sich erneut anzumelden.  <br/> |
|Zugriff auf Arbeitsdateien auf Geräten mit entfernten Nutzungsbeschränkungen verweigern  <br/> |Clevere Benutzer verfügen möglicherweise über ein Gerät, bei dem die Nutzungsbeschränkungen entfernt wurden. Dies bedeutet, dass der Benutzer das Betriebssystem ändern kann, wodurch das Gerät empfänglicher für Schadsoftware werden kann. Solche Geräte können gesperrt werden, wenn die Einstellung auf **Ein** festgelegt wurde.  <br/> |
|Benutzern nicht erlauben, Inhalte aus Office Apps in persönliche Apps zu kopieren  <br/> |Wir lassen dies standardmäßig zu, aber wenn die Einstellung **aktiviert** ist, könnte der Benutzer Informationen in einer Arbeitsdatei in eine persönliche Datei kopieren. Wenn die Einstellung **deaktiviert** ist, kann der Benutzer keine Informationen von einem Geschäftskonto in eine persönliche App oder ein persönliches Konto kopieren.  <br/> |
