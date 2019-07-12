---
title: Festlegen von Geräteschutzeinstellungen für Windows 10-PCs
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Erfahren Sie mehr über die standardmäßigen und anderen Einstellungen, die in Microsoft 365 Business zum Sichern von Windows 10-Geräten verfügbar sind.
ms.openlocfilehash: 844bddc4b93c7dc543ad6c6a79f5cf92c96ceff0
ms.sourcegitcommit: 0c1227dc79b66bab529bf178c5672791369ba471
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "35630607"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>Festlegen von Geräteschutzeinstellungen für Windows 10-PCs

## <a name="secure-windows-10-devices"></a>Absichern von Windows 10-Geräten

Schauen Sie sich ein Video mit Informationen zum Sichern von Windows 10-Geräten mit Microsoft 365 Business an:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. Wählen Sie im linken Navigationsbereich **Geräte** \> **Richtlinien** \> **Hinzufügen**aus.
  
3. Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein. 
    
4. Wählen Sie unter **Richtlinientyp** die Option **Windows 10-Gerätekonfiguration** aus.
    
5. Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](#available-settings) for more information. 
    
    Über den Link **Standardeinstellungen zurücksetzen** können Sie die Standardeinstellung jederzeit wiederherstellen. 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.
    
7. Wählen Sie schließlich **Fertig** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu. 
    
## <a name="available-settings"></a>Verfügbare Einstellungen

Standardmäßig sind alle Einstellungen auf **Ein** festgelegt. Die folgenden Einstellungen stehen zur Verfügung:
  
Weitere Informationen finden Sie unter [Zuordnung von Microsoft 365 Business-Schutzfunktionen zu Intune-Einstellungen](map-protection-features-to-intune-settings.md). 
  
|||
|:-----|:-----|
|Einstellung  <br/> |Beschreibung  <br/> |
|PCs vor Viren und anderen Bedrohungen mithilfe von Windows Defender Antivirus schützen  <br/> |Setzt voraus, dass Windows Defender Antivirus aktiviert ist, um PCs vor den Gefahren bei einer Verbindung mit dem Internet zu schützen.  <br/> |
|PCs vor webbasierten Bedrohungen in Microsoft Edge schützen  <br/> |Aktiviert Einstellungen in Edge, die Benutzer vor Websites und Downloads mit Schadsoftware schützen.  <br/> |
|Regeln verwenden, die die Angriffsfläche von Geräten verringern  <br/> |Wenn diese Option aktiviert ist, hilft die Reduzierung der Angriffsfläche, Aktionen und Apps zu blockieren, die häufig von Schadsoftware zum Infizieren von Geräten verwendet werden. Diese Einstellung ist nur verfügbar, wenn Windows Defender Antivirus aktiviert ist. Weitere Informationen finden Sie unter [Verringern der Angriffsfläche](https://go.microsoft.com/fwlink/?linkid=870417).  <br/> |
|Ordner vor Bedrohungen wie Ransomware schützen  <br/> |Diese Einstellung verwendet kontrollierten Ordnerzugriff zum Schutz von Unternehmensdaten vor Änderungen durch verdächtige oder böswillige apps, z. B. Ransomware. Diese Arten von Apps werden daran gehindert, Änderungen in geschützten Ordnern vorzunehmen. Diese Einstellung ist nur verfügbar, wenn Windows Defender Antivirus aktiviert ist. Weitere Informationen finden Sie unter [Schützen von Ordnern durch kontrollierten Ordnerzugriff](https://go.microsoft.com/fwlink/?linkid=870418).  <br/> |
|Netzwerkzugriff auf potenziell schädliche Inhalte im Internet verhindern  <br/> |Mithilfe dieser Einstellung können Sie ausgehende Benutzerverbindungen zu nicht vertrauenswürdigen Internetseiten blockieren, die Phishing-Betrügereien, Exploits oder andere schädliche Inhalte enthalten können. Diese Einstellung ist nur verfügbar, wenn Windows Defender Antivirus aktiviert ist. Weitere Informationen finden Sie unter [Schützen Sie Ihr Netzwerk](https://go.microsoft.com/fwlink/?linkid=870419).  <br/> |
|Dateien und Ordner auf PCs mit BitLocker vor unbefugtem Zugriff schützen  <br/> |BitLocker schützt Daten durch Verschlüsselung der Computerfestplatten und bietet Schutz vor Datenverlusten, falls ein Computer verloren geht oder gestohlen wird. Weitere Informationen finden Sie unter [Häufig gestellte Fragen zu Bitlocker](https://go.microsoft.com/fwlink/?linkid=871000).  <br/> |
|Benutzern den Download von Apps aus dem Microsoft Store erlauben  <br/> |Ermöglicht es Benutzern, Apps aus dem Microsoft Store herunterzuladen und zu installieren. Weil Apps alles umfassen - von Spielen bis zu Produktivitätstools - behalten Sie für diese Einstellung **Ein** bei. Sie können sie aber auch deaktivieren, um die Sicherheit zu erhöhen.  <br/> |
|Benutzern den Zugriff auf Cortana erlauben  <br/> |Cortana kann sehr hilfreich sein! Sie kann Einstellungen automatisch aktivieren oder deaktivieren, Wegbeschreibungen liefern und sicherstellen, dass Sie Ihre Termine einhalten. Deshalb ist diese Einstellung standardmäßig auf **Ein** festgelegt.  <br/> |
|Benutzern erlauben, Windows-Tipps und Werbung von Microsoft zu empfangen  <br/> |Windows-Tipps können nützlich sein und Benutzern die Orientierung erleichtern, wenn neue Features veröffentlicht werden.  <br/> |
|Windows 10-Geräte automatisch auf dem neuesten Stand halten  <br/> |Stellt sicher, dass Windows 10-Geräte die neuesten Updates automatisch erhalten.  <br/> |
|Bildschirm deaktivieren, wenn ein Gerät im Leerlauf ist seit dieser Zeitdauer  <br/> |Stellt sicher, dass die Unternehmensdaten bei Benutzerinaktivität geschützt sind. Vielleicht arbeitet ein Benutzer an einem Ort mit Publikumsverkehr, z. B. in einem Café, und entfernt sich von seinem Gerät oder ist nur einen Augenblick abgelenkt, wodurch das Gerät für zufällige Blicke anfällig ist. Mit dieser Einstellung können Sie steuern, wie lange der Benutzer inaktiv sein kann, bevor der Bildschirm abgeschaltet wird.  <br/> |
   
  

