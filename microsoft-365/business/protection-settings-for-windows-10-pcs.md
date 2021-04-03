---
title: Bearbeiten oder Erstellen von Geräteschutzeinstellungen für Windows 10-PCs
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Erfahren Sie mehr über die in Microsoft 365 Business verfügbaren Einstellungen zum Sichern von Windows 10-Geräten.
ms.openlocfilehash: acfb27b2e4592d4ed1e446a63c9495ae07d916de
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578225"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>Bearbeiten oder Erstellen von Geräteschutzeinstellungen für Windows 10-PCs

Dieser Artikel gilt für Microsoft 365 Business Premium.

Nachdem Sie standardmäßige Windows-Schutzeinstellungen auf der Seite Setup eingerichtet haben, können Sie neue Einstellungen hinzufügen, die für alle Benutzer oder eine Gruppe von Benutzern gelten. Sie können auch alle erstellten Bearbeiten.

## <a name="create-protection-settings-for-windows-10-devices"></a>Erstellen von Schutzeinstellungen für Windows 10-Geräte

Sehen Sie sich ein Video zum Sichern von Windows 10-Geräten mit Microsoft 365 Business Premium an:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. Wählen Sie im  linken Navigationsgerät \> **Geräterichtlinien** \> **hinzufügen aus.**
3. Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein. 
4. Wählen Sie unter **Richtlinientyp** die Option **Windows 10-Gerätekonfiguration** aus.
5. Expand **Secure Windows 10 Devices** \> configure the settings how you would like. Weitere Informationen finden Sie unter [Verfügbare Einstellungen](#available-settings). 
    
    Mit dem Link **Standardeinstellungen zurücksetzen** können Sie jederzeit die Standardeinstellungen wiederherstellen. 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.
7. Wählen Sie schließlich **Fertig** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu. 

## <a name="edit-windows-10-protection-settings"></a>Bearbeiten von Windows 10-Schutzeinstellungen
 
1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. Wählen Sie im  linken Navigationsgerät \> **Geräterichtlinien aus.**
1. Wählen Sie eine vorhandene Windows-Geräterichtlinie aus, und bearbeiten **Sie dann .**
1. Wählen **Sie Bearbeiten** neben einer Einstellung aus, die Sie ändern möchten, und **speichern.**

## <a name="available-settings"></a>Verfügbare Einstellungen

Standardmäßig sind alle Einstellungen auf **Ein** festgelegt. Die folgenden Einstellungen stehen zur Verfügung:
  
Weitere Informationen finden Sie unter [How do protection features in Microsoft 365 Premium map to Intune settings](map-protection-features-to-intune-settings.md). 
  
|||
|:-----|:-----|
|Einstellung  <br/> |Beschreibung  <br/> |
|PCs vor Viren und anderen Bedrohungen mithilfe von Windows Defender Antivirus schützen  <br/> |Setzt voraus, dass Windows Defender Antivirus aktiviert ist, um PCs vor den Gefahren bei einer Verbindung mit dem Internet zu schützen.  <br/> |
|PCs vor webbasierten Bedrohungen in Microsoft Edge schützen  <br/> |Aktiviert Einstellungen in Edge, die Benutzer vor Websites und Downloads mit Schadsoftware schützen.  <br/> |
|Regeln verwenden, die die Angriffsfläche von Geräten verringern  <br/> |Wenn diese Option aktiviert ist, hilft die Reduzierung der Angriffsfläche, Aktionen und Apps zu blockieren, die häufig von Schadsoftware zum Infizieren von Geräten verwendet werden. Diese Einstellung ist nur verfügbar, wenn Windows Defender Antivirus aktiviert ist. Weitere Informationen finden Sie unter [Verringern der Angriffsfläche](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).  <br/> |
|Ordner vor Bedrohungen wie Ransomware schützen  <br/> |Diese Einstellung verwendet kontrollierten Ordnerzugriff, um Unternehmensdaten vor Änderungen durch verdächtige oder schädliche Apps wie Ransomware zu schützen. Diese Arten von Apps werden am Vornehmen von Änderungen in geschützten Ordnern blockiert. Diese Einstellung ist nur verfügbar, wenn Windows Defender Antivirus aktiviert ist. Weitere Informationen finden Sie unter Schützen von Ordnern mit [kontrolliertem](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) Ordnerzugriff.  <br/> |
|Netzwerkzugriff auf potenziell schädliche Inhalte im Internet verhindern  <br/> |Verwenden Sie diese Einstellung, um ausgehende Benutzerverbindungen zu Internetstandorten mit niedriger Reputation zu blockieren, die Phishingbetrüger, Exploits oder andere schädliche Inhalte hosten können. Diese Einstellung ist nur verfügbar, Windows Defender Antivirus auf **Ein festgelegt ist.** Weitere Informationen finden Sie unter [Protect your network](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).  <br/> |
|Dateien und Ordner auf PCs mit BitLocker vor unbefugtem Zugriff schützen  <br/> |BitLocker schützt Daten durch Verschlüsselung der Computerfestplatten und bietet Schutz vor Datenverlusten, falls ein Computer verloren geht oder gestohlen wird. Weitere Informationen finden Sie unter [Bitlocker FAQ](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).  <br/> |
|Benutzern den Download von Apps aus dem Microsoft Store erlauben  <br/> |Ermöglicht es Benutzern, Apps aus dem Microsoft Store herunterzuladen und zu installieren. Weil Apps alles umfassen - von Spielen bis zu Produktivitätstools - behalten Sie für diese Einstellung **Ein** bei. Sie können sie aber auch deaktivieren, um die Sicherheit zu erhöhen.  <br/> |
|Benutzern den Zugriff auf Cortana erlauben  <br/> |Cortana kann sehr hilfreich sein! Cortana kann Einstellungen für Sie aktivieren oder deaktivieren, Wegbeschreibungen geben und sicherstellen, dass Sie für Termine zurZeit sind, sodass diese Einstellung standardmäßig **aktiviert** bleibt.  <br/> |
|Benutzern erlauben, Windows-Tipps und Werbung von Microsoft zu empfangen  <br/> |Windows-Tipps können nützlich sein und Benutzern die Orientierung erleichtern, wenn neue Features veröffentlicht werden.  <br/> |
|Windows 10-Geräte automatisch auf dem neuesten Stand halten  <br/> |Stellt sicher, dass Windows 10-Geräte die neuesten Updates automatisch erhalten.  <br/> |
|Bildschirm deaktivieren, wenn ein Gerät im Leerlauf ist seit dieser Zeitdauer  <br/> |Stellt sicher, dass die Unternehmensdaten bei Benutzerinaktivität geschützt sind. Vielleicht arbeitet ein Benutzer an einem Ort mit Publikumsverkehr, z. B. in einem Café, und entfernt sich von seinem Gerät oder ist nur einen Augenblick abgelenkt, wodurch das Gerät für zufällige Blicke anfällig ist. Mit dieser Einstellung können Sie steuern, wie lange der Benutzer inaktiv sein kann, bevor der Bildschirm abgeschaltet wird.  <br/> |