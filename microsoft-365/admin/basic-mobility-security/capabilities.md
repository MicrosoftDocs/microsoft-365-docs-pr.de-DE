---
title: Funktionen von grundlegender Mobilität und Sicherheit
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Basic Mobility and Security kann Ihnen helfen, mobile Geräte zu sichern und zu verwalten.
ms.openlocfilehash: 746131e90e207d7b888a3ddcaf4ff0656606a2c7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877116"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Funktionen von grundlegender Mobilität und Sicherheit

Basic Mobility and Security kann Ihnen helfen, mobile Geräte wie iPhones, iPads, Androids und Windows Phones zu sichern und zu verwalten, die von lizenzierten Microsoft 365-Benutzern in Ihrer Organisation verwendet werden. Sie können Richtlinien für die Verwaltung mobiler Geräte mit Einstellungen erstellen, mit deren Hilfe Sie den Zugriff auf Microsoft 365-E-Mails und -Dokumente Ihrer Organisation für unterstützte mobile Geräte und Apps steuern können. Wenn ein Gerät verloren geht oder gestohlen wird, können Sie den Geräteinhalt per Remotezugriff löschen, um vertrauliche Organisationsinformationen zu entfernen.

## <a name="supported-devices"></a>Unterstützte Geräte

Sie können Basic Mobility and Security verwenden, um die folgenden Geräte zu sichern und zu verwalten.

- iOS 11.0 oder höher

- Android 5.0 oder höher,<sup>Version 3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup> Die Zugriffssteuerung für Windows 8.1 RT-Geräte ist auf Exchange ActiveSync.

<sup>2</sup> Die Zugriffssteuerung für Windows 8.1 RT-Geräte ist auf Exchange ActiveSync.
Die Zugriffssteuerung für Windows 10 erfordert ein Abonnement, das Azure AD Premium umfasst und das Gerät mit Azure Active Directory verbunden werden muss.

<sup>3</sup> Die Zugriffssteuerung für Windows 8.1 RT-Geräte ist auf Exchange ActiveSync.
Nach Juni 2020 können Android-Versionen, die später als 9 sind, keine Kennworteinstellungen mehr verwalten, es sei denn, sie sind auf Geräten des Herstellers Samsung Knox verfügbar.

>[!NOTE]
>Geräte, die bereits mit früheren Betriebssystemversionen registriert wurden, funktionieren weiterhin, obwohl sich die Funktionen ohne vorherige Ankündigung ändern können.

Wenn Personen in Ihrer Organisation mobile Geräte verwenden, die von Basic Mobility and Security nicht unterstützt werden, sollten Sie den Zugriff auf Microsoft 365-E-Mails Exchange ActiveSync der Exchange ActiveSync-App für diese Geräte blockieren, um die Daten Ihrer Organisation sicherer zu machen. Schritte zum Blockieren Exchange ActiveSync finden Sie unter Verwalten von [Gerätezugriffseinstellungen in Basic Mobility and Security](manage-device-access-settings.md).

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Zugriffssteuerung für Microsoft 365-E-Mails und -Dokumente

Die in der folgenden Tabelle aufgeführten unterstützten Apps für die verschiedenen Typen von mobilen Geräten forderten Benutzer auf, sich bei Basic Mobility and Security zu registrieren, wenn es eine neue Richtlinie zur Verwaltung mobiler Geräte gibt, die auf das Gerät eines Benutzers angewendet wird und der Benutzer das Gerät zuvor noch nicht registriert hat. Wenn das Gerät eines Benutzers nicht einer Richtlinie entspricht, kann es sein, dass ein Benutzer in diesen Apps nicht auf Microsoft 365-Ressourcen zugreifen kann oder Zugriff hat, Microsoft 365 meldet jedoch einen Richtlinienverstoß.

|**Product**|**iOS 10.0 oder höher**|**Android 5.0 oder höher**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync enthält integrierte E-Mail- und Drittanbieter-Apps wie TouchDown, die Exchange ActiveSync Version 14.1 oder höher verwenden. |E-Mail |E-Mails |
|**Office**   und  **OneDrive for Business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**Auf Smartphones und Tablets:**<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Nur auf Telefonen:** <br/> Office Mobile |

>[!NOTE]
- >Die Unterstützung für iOS 10.0 und höher umfasst iPhone- und iPad-Geräte.
- >Die Verwaltung von BlackBerry -BETRIEBSSYSTEM-Geräten wird von Basic Security and Mobility nicht unterstützt. Verwenden Sie BlackBerry Business Cloud Services (BBCS) von BlackBerry zum Verwalten von BlackBerry OS-Geräten. Blackberry-Geräte, auf deren Betriebssystem Android ausgeführt wird, werden als standardmäßige Android-Geräte unterstützt.
- >Benutzer werden nicht zur Registrierung aufgefordert und werden nicht aufgrund von Richtlinienverletzungen blockiert oder gemeldet, wenn sie den mobilen Browser für den Zugriff auf Microsoft 365 SharePoint-Websites, Dokumente in Office Online oder E-Mails in Outlook Web App verwenden.

Das folgende Diagramm zeigt, was geschieht, wenn sich ein Benutzer mit einem neuen Gerät bei einer App meldet, die die Zugriffssteuerung mit Basic Mobility and Security unterstützt. Der Benutzer wird am Zugriff auf Microsoft 365-Ressourcen in der App blockiert, bis er sein Gerät registriert.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Grundlegende Zugriffssteuerung für Mobilität und Sicherheit":::

> [!NOTE]
> Richtlinien und Zugriffsregeln, die in Basic Mobility and Security für Microsoft 365 Business Standard erstellt wurden, setzen Exchange ActiveSync Postfachrichtlinien und Gerätezugriffsregeln für mobile Geräte außer Kraft, die im Exchange Admin Center erstellt wurden. Nachdem ein Gerät in Basic Mobility and Security für Microsoft 365 Business Standard registriert wurde, werden alle auf das Gerät angewendeten Exchange ActiveSync-Postfachrichtlinien oder Gerätezugriffsregeln für mobile Geräte ignoriert. Weitere Informationen zu Exchange ActiveSync finden Sie unter [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="policy-settings-for-mobile-devices"></a>Richtlinieneinstellungen für mobile Geräte

Wenn Sie eine Richtlinie zum Blockieren des Zugriffs mit bestimmten aktivierten Einstellungen erstellen, werden Benutzer am Zugriff auf Microsoft 365-Ressourcen blockiert, wenn sie eine unterstützte App verwenden, die in der Zugriffssteuerung für [Microsoft 365-E-Mails](capabilities.md)und -Dokumente aufgeführt ist. 

Die Einstellungen, die Benutzer am Zugriff auf Microsoft 365-Ressourcen blockieren können, finden Sie in den folgenden Abschnitten:

- Sicherheit

- Verschlüsselung

- Jailbroken

- Verwaltetes E-Mail-Profil  

Die folgende Abbildung zeigt beispielsweise, was passiert, wenn ein Benutzer mit einem registrierten Gerät mit einer Sicherheitseinstellung in einer mobilen Geräteverwaltungsrichtlinie, die für sein Gerät gilt, nicht kompatibel ist. Der Benutzer meldet sich bei einer App an, die die Zugriffssteuerung mit Basic Mobility and Security unterstützt. Sie werden am Zugriff auf Microsoft 365-Ressourcen in der App blockiert, bis ihr Gerät die Sicherheitseinstellung erfüllt.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Grundlegende Mobilitäts- und Sicherheits-Compliance-Nachricht":::

In den folgenden Abschnitten werden die Richtlinieneinstellungen aufgeführt, mit deren Hilfe Sie mobile Geräte schützen und verwalten können, die eine Verbindung mit Den Ressourcen Ihrer Microsoft 365-Organisation herstellen.

## <a name="security-settings"></a>Sicherheitseinstellungen

|**Name der Einstellung**|**iOS 7.1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Kennwort erforderlich|Ja|Ja|Ja|
|Verhindern einfacher Kennwörter|Ja|Nein|Nein|
|Alphanumerisches Kennwort anfordern|Ja|Nein|Nein|
|Minimale Kennwortlänge |Ja|Ja|Ja|
|Anzahl von Anmeldefehlern, bevor die Gerätedaten gelöscht werden |Ja|Ja|Ja|
|Minuten der Inaktivität, bevor das Gerät gesperrt wird |Ja|Ja|Ja|
|Kennwortablauf (Tage) |Ja|Ja|Ja|
|Kennwortverlauf verfolgen und Wiederverwendung verhindern |Ja|Ja|Ja|

## <a name="encryption-settings"></a>Verschlüsselungseinstellungen

|**Name der Einstellung**|**iOS 7.1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Datenverschlüsselung auf Geräten<sup>1 erforderlich</sup> |Nein|Ja|Ja|

<sup>1</sup> Mit Samsung Knox können Sie auch eine Verschlüsselung auf Speicherkarten verlangen. 

## <a name="jail-broken-setting"></a>Jailbroken-Einstellung 

|**Name der Einstellung**|**iOS 7.1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Gerät muss ohne Jailbreak und ohne Rootzugriff sein |Ja|Ja|Ja|

## <a name="managed-email-profile-option"></a>Verwaltetes E-Mail-Profil 

Die folgende Option kann den Zugriff von Benutzern auf ihre Microsoft 365-E-Mails blockieren, wenn sie ein manuell erstelltes E-Mail-Profil verwenden. Benutzer auf iOS-Geräten müssen ihr manuell erstelltes E-Mail-Profil löschen, bevor sie auf ihre E-Mails zugreifen können. Nachdem sie das Profil gelöscht haben, wird automatisch ein neues Profil auf dem Gerät erstellt. Anweisungen dazu, wie Endbenutzer konform werden können, finden Sie unter [Ein vorhandenes E-Mail-Konto wurde gefunden.](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)

|**Name der Einstellung**|**iOS 7.1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|E-Mail-Profil ist verwaltet |Ja|Nein|Nein|

## <a name="cloud-settings"></a>Cloud-Einstellungen

|**Name der Einstellung**|**iOS 7.1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Verschlüsselte Sicherung anfordern |Ja|Nein|Nein|
|Cloud-Sicherung blockieren |Ja|Nein|Nein|
|Dokumentsynchronisierung blockieren |Ja|Nein|Nein|
|Fotosynchronisierung blockieren  |Ja|Nein|Nein|
|Sichern von Google zulassen  |Nicht zutreffend|Nein|Ja|
|Automatische Synchronisierung des Google -Kontos zulassen  |Nicht zutreffend|Nein|Ja|

## <a name="system-settings"></a>Systemeinstellungen

|**Name der Einstellung**|**iOS 7.1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bildschirmaufnahme blockieren |Ja|Nein|Ja|
|Senden von Diagnosedaten vom Gerät aus blockieren |Ja|Nein|Ja|

## <a name="application-settings"></a>Anwendungseinstellungen

|**Name der Einstellung**|**iOS 7.1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Videokonferenzen auf Gerät blockieren |Ja|Nein|Nein|
|Zugriff auf Anwendungsspeicher blockieren |Ja|Nein|Ja|
|Kennwort beim Zugriff auf Anwendungsspeicher erforderlich |Nein|Ja|Ja|

## <a name="device-capabilities-settings"></a>Gerätefunktionseinstellungen

|**Name der Einstellung**|**iOS 7.1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Verbindung mit Speicherwechselmedien blockieren |Ja|Ja|Nein|
|Bluetooth-Verbindungen blockieren |Ja|Ja|Nein|

## <a name="additional-settings"></a>Zusätzliche Einstellungen

Sie können die folgenden zusätzlichen Richtlinieneinstellungen mithilfe von Security & Compliance Center -PowerShell-Cmdlets festlegen. Weitere Informationen finden Sie unter [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell).

|**Name der Einstellung**|**iOS 7.1 und höher**|**Android 5 und höher**|
|:-----|:-----|:-----|
|CameraEnabled|Ja|Ja|
|RegionRatings|Ja|Nein|
|MoviesRatings|Ja|Nein|
|TVShowsRating |Ja|Nein|
|AppsRatings |Ja|Nein|
|AllowVoiceDialing |Ja|Nein|
|AllowVoiceAssistant |Ja|Nein|
|AllowAssistantWhileLocked  |Ja|Nein|
|AllowPassbookWhileLocked |Ja|Nein|
|MaxPasswordGracePeriod |Ja|Nein|
|PasswordQuality |Nein|Ja|
|SystemSecurityTLS  |Ja|Nein|
|WLANEnabled  |Nein|Nein|

## <a name="settings-supported-by-windows"></a>Von Windows unterstützte Einstellungen

Sie können Windows 10-Geräte verwalten, indem Sie sie als mobile Geräte registrieren. Nachdem eine entsprechende Richtlinie bereitgestellt wurde, müssen sich Benutzer mit Windows 10-Geräten bei Basic Mobility and Security registrieren, wenn sie die integrierte E-Mail-App zum ersten Mal für den Zugriff auf ihre Microsoft 365-E-Mail verwenden (erfordert ein Azure AD Premium-Abonnement).

Die folgenden Einstellungen werden für Windows 10-Geräte unterstützt, die als mobile Geräte registriert sind. Diese Einstellung sperrt Benutzer nicht am Zugriff auf Microsoft 365-Ressourcen.

### <a name="security-settings"></a>Sicherheitseinstellungen

- Alphanumerisches Kennwort anfordern

- Minimale Kennwortlänge

- Anzahl von Anmeldefehlern, bevor die Gerätedaten gelöscht werden

- Minuten der Inaktivität, bevor das Gerät gesperrt wird

- Kennwortablauf (Tage)

- Kennwortverlauf verfolgen und Wiederverwendung verhindern

>[!NOTE]
>Die folgenden Einstellungen für Kennwörter steuern nur lokale Windows-Konten. Windows-Konten, die über den Beitritt zu einer Domäne oder Azure Active Directory bereitgestellt werden, sind von diesen Einstellungen nicht betroffen.

### <a name="system-settings"></a>Systemeinstellungen

Das Senden von Diagnosedaten vom Gerät blockieren.

### <a name="additional-settings"></a>Zusätzliche Einstellungen

Sie können diese zusätzlichen Richtlinieneinstellungen mithilfe von PowerShell-Cmdlets festlegen:

- AllowConvenienceLogon

- UserAccountControlStatus

- FirewallStatus

- AutoUpdateStatus

- AntiVirusStatus

- AntiVirusSignatureStatus

- SmartScreenEnabled

- WorkFoldersSyncUrl

## <a name="remotely-wipe-a-mobile-device"></a>Mobiles Gerät per Remotezugriff zurücksetzen

Wenn ein Gerät verloren geht oder gestohlen wird, können Sie vertrauliche Unternehmensdaten entfernen und den Zugriff auf Ihre Microsoft 365-Organisationsressourcen verhindern, indem Sie eine Zurücknahme aus dem Security & Compliance Center > **Data loss prevention** Device management ( Verhinderung von Datenverlust)  >  **unternehmen.** Sie können eine ausgewählte Zurücksetzung durchführen, um nur Organisationsdaten zu entfernen, oder alle Daten vollständig von einem Gerät löschen und es auf die werkseitigen Einstellungen zurücksetzen.

Weitere Informationen finden Sie unter [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über grundlegende Mobilität und Sicherheit für Microsoft 365](overview.md)

[Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security](create-device-security-policies.md)