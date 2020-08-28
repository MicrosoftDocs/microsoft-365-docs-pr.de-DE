---
title: Bearbeiten oder Erstellen von Geräteschutz Einstellungen für Windows 10-PCs
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Hier finden Sie Informationen zu den in Microsoft 365 for Business verfügbaren Einstellungen zum Sichern von Windows 10-Geräten.
ms.openlocfilehash: bd992113403c7134fb32bc6cced5bf216843241b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289153"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>Bearbeiten oder Erstellen von Geräteschutz Einstellungen für Windows 10-PCs

Dieser Artikel bezieht sich auf Microsoft 365 Business Premium.

Nachdem Sie auf der Seite Setup die Einstellungen für den standardmäßigen Windows-Schutz eingerichtet haben, können Sie neue hinzufügen, die entweder für alle Benutzer oder für eine Gruppe von Benutzern gelten. Sie können auch alle erstellten Objekte bearbeiten.

## <a name="create-protection-settings-for-windows-10-devices"></a>Erstellen von Schutzeinstellungen für Windows 10-Geräte

Sehen Sie sich ein Video zur Sicherung von Windows 10-Geräten mit Microsoft 365 Business Premium an:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. Wählen Sie im linken Navigationsbereich **Geräte** \> **Richtlinien** \> **Hinzufügen**aus.
3. Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein. 
4. Wählen Sie unter **Richtlinientyp** die Option **Windows 10-Gerätekonfiguration** aus.
5. Expand **Secure Windows 10 Devices** \> configure the settings how you would like. Weitere Informationen finden Sie unter [Verfügbare Einstellungen](#available-settings). 
    
    Mit dem Link **Standardeinstellungen zurücksetzen** können Sie jederzeit die Standardeinstellungen wiederherstellen. 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.
7. Wählen Sie schließlich **Fertig** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu. 

## <a name="edit-windows-10-protection-settings"></a>Bearbeiten von Windows 10-Schutzeinstellungen
 
1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. Wählen Sie im linken Navigationsbereich **Geräte** \> **Richtlinien** aus.
1. Wählen Sie eine vorhandene Windows-Geräterichtlinie aus, und **Bearbeiten**Sie Sie.
1. Klicken Sie neben einer Einstellung, die Sie ändern möchten, auf **Bearbeiten** , und **Speichern**Sie dann.

## <a name="available-settings"></a>Verfügbare Einstellungen

Standardmäßig sind alle Einstellungen auf **Ein** festgelegt. Die folgenden Einstellungen stehen zur Verfügung:
  
Weitere Informationen finden Sie unter [How do Protection Features in Microsoft 365 Premium Map to InTune Settings](map-protection-features-to-intune-settings.md). 
  
|||
|:-----|:-----|
|Einstellung  <br/> |Beschreibung  <br/> |
|PCs vor Viren und anderen Bedrohungen mithilfe von Windows Defender Antivirus schützen  <br/> |Setzt voraus, dass Windows Defender Antivirus aktiviert ist, um PCs vor den Gefahren bei einer Verbindung mit dem Internet zu schützen.  <br/> |
|PCs vor webbasierten Bedrohungen in Microsoft Edge schützen  <br/> |Aktiviert Einstellungen in Edge, die Benutzer vor Websites und Downloads mit Schadsoftware schützen.  <br/> |
|Regeln verwenden, die die Angriffsfläche von Geräten verringern  <br/> |Wenn diese Option aktiviert ist, hilft die Reduzierung der Angriffsfläche, Aktionen und Apps zu blockieren, die häufig von Schadsoftware zum Infizieren von Geräten verwendet werden. Diese Einstellung ist nur verfügbar, wenn Windows Defender Antivirus aktiviert ist. Weitere Informationen finden Sie unter [Verringern der Angriffsfläche](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).  <br/> |
|Ordner vor Bedrohungen wie Ransomware schützen  <br/> |Diese Einstellung verwendet kontrollierten Ordner Zugriff, um Unternehmensdaten vor Änderungen durch verdächtige oder böswillige apps wie Ransomware zu schützen. Diese Typen von apps werden daran gehindert, Änderungen in geschützten Ordnern vorzunehmen. Diese Einstellung ist nur verfügbar, wenn Windows Defender Antivirus aktiviert ist. Weitere Informationen finden Sie unter [Schützen von Ordnern mit gesteuertem Ordner Zugriff](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) .  <br/> |
|Netzwerkzugriff auf potenziell schädliche Inhalte im Internet verhindern  <br/> |Verwenden Sie diese Einstellung, um ausgehende Benutzer Verbindungen zu Internet Standorten mit niedriger Zuverlässigkeit zu blockieren, die Phishing-Scams, Exploits oder andere schädliche Inhalte hosten können. Diese Einstellung ist nur verfügbar, wenn Windows Defender Antivirus auf **ein**festgelegt ist. Weitere Informationen finden Sie unter [Protect Your Network](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).  <br/> |
|Dateien und Ordner auf PCs mit BitLocker vor unbefugtem Zugriff schützen  <br/> |BitLocker schützt Daten durch Verschlüsselung der Computerfestplatten und bietet Schutz vor Datenverlusten, falls ein Computer verloren geht oder gestohlen wird. Weitere Informationen finden Sie unter [häufig gestellte Fragen zu BitLocker](https://go.microsoft.com/fwlink/?linkid=871000).  <br/> |
|Benutzern den Download von Apps aus dem Microsoft Store erlauben  <br/> |Ermöglicht es Benutzern, Apps aus dem Microsoft Store herunterzuladen und zu installieren. Weil Apps alles umfassen - von Spielen bis zu Produktivitätstools - behalten Sie für diese Einstellung **Ein** bei. Sie können sie aber auch deaktivieren, um die Sicherheit zu erhöhen.  <br/> |
|Benutzern den Zugriff auf Cortana erlauben  <br/> |Cortana kann sehr hilfreich sein! Cortana kann Einstellungen für Sie aktivieren oder deaktivieren, Anweisungen geben und sicherstellen, dass Sie pünktlich für Termine sind, sodass diese Einstellung standardmäßig **aktiviert** bleibt.  <br/> |
|Benutzern erlauben, Windows-Tipps und Werbung von Microsoft zu empfangen  <br/> |Windows-Tipps können nützlich sein und Benutzern die Orientierung erleichtern, wenn neue Features veröffentlicht werden.  <br/> |
|Windows 10-Geräte automatisch auf dem neuesten Stand halten  <br/> |Stellt sicher, dass Windows 10-Geräte die neuesten Updates automatisch erhalten.  <br/> |
|Bildschirm deaktivieren, wenn ein Gerät im Leerlauf ist seit dieser Zeitdauer  <br/> |Stellt sicher, dass die Unternehmensdaten bei Benutzerinaktivität geschützt sind. Vielleicht arbeitet ein Benutzer an einem Ort mit Publikumsverkehr, z. B. in einem Café, und entfernt sich von seinem Gerät oder ist nur einen Augenblick abgelenkt, wodurch das Gerät für zufällige Blicke anfällig ist. Mit dieser Einstellung können Sie steuern, wie lange der Benutzer inaktiv sein kann, bevor der Bildschirm abgeschaltet wird.  <br/> |
