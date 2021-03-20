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
description: Grundlegende Mobilität und Sicherheit können Ihnen dabei helfen, mobile Geräte zu sichern und zu verwalten.
ms.openlocfilehash: 468f06edf16eb6ea00fd4d26c716bc145474dd25
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904276"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Funktionen von grundlegender Mobilität und Sicherheit

Grundlegende Mobilität und Sicherheit können Ihnen dabei helfen, mobile Geräte wie iPhones, iPads, Androids und Windows Phones zu sichern und zu verwalten, die von lizenzierten Microsoft 365-Benutzern in Ihrer Organisation verwendet werden. Sie können Verwaltungsrichtlinien für mobile Geräte mit Einstellungen erstellen, mit deren Hilfe Sie den Zugriff auf die Microsoft 365-E-Mails und Dokumente Ihrer Organisation für unterstützte mobile Geräte und Apps steuern können. Wenn ein Gerät verloren geht oder gestohlen wird, können Sie den Geräteinhalt per Remotezugriff löschen, um vertrauliche Organisationsinformationen zu entfernen.

## <a name="supported-devices"></a>Unterstützte Geräte

Sie können basic Mobility and Security verwenden, um die folgenden Geräte zu sichern und zu verwalten.

- iOS 11.0 oder höher

- Android 5.0 oder höher Version<sup>3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup> Die Zugriffssteuerung für Windows 8.1 RT-Geräte ist auf Exchange ActiveSync.

<sup>2</sup> Die Zugriffssteuerung für Windows 8.1 RT-Geräte ist auf Exchange ActiveSync.
Die Zugriffssteuerung für Windows 10 erfordert ein Abonnement, das Azure AD Premium enthält und das Gerät mit Azure Active Directory verbunden werden muss.

<sup>3</sup> Die Zugriffssteuerung für Windows 8.1 RT-Geräte ist auf Exchange ActiveSync.
Nach Juni 2020 können Android-Versionen nach 9 keine Kennworteinstellungen mehr verwalten, außer auf Samsung -Knox-Geräten.

>[!NOTE]
>Geräte, die bereits mit früheren Betriebssystemversionen registriert wurden, funktionieren weiterhin, obwohl sich die Funktionen ohne vorherige Ankündigung ändern können.

Wenn Personen in Ihrer Organisation mobile Geräte verwenden, die von Basic Mobility and Security nicht unterstützt werden, sollten Sie den Zugriff von Exchange ActiveSync-Apps auf Microsoft 365-E-Mails für diese Geräte blockieren, um die Daten Ihrer Organisation sicherer zu machen. Schritte zum Blockieren Exchange ActiveSync finden Sie [unter Verwalten von Gerätezugriffseinstellungen in Basic Mobility and Security](manage-device-access-settings.md).

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Zugriffssteuerung für Microsoft 365-E-Mails und -Dokumente

Die unterstützten Apps für die verschiedenen Typen von mobilen Geräten in der folgenden Tabelle forderten Benutzer auf, sich bei Basic Mobility and Security zu registrieren, wenn es eine neue Verwaltungsrichtlinie für mobile Geräte gibt, die auf das Gerät eines Benutzers angewendet wird und der Benutzer das Gerät noch nicht registriert hat. Wenn das Gerät eines Benutzers einer Richtlinie nicht entspricht, wird einem Benutzer je nach Einrichtung der Richtlinie möglicherweise der Zugriff auf Microsoft 365-Ressourcen in diesen Apps blockiert, oder er hat möglicherweise Zugriff, microsoft 365 meldet jedoch einen Richtlinienverstoß.

|**Produkt**|**iOS 10.0 oder höher**|**Android 5.0 oder höher**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync enthält integrierte E-Mail- und Drittanbieter-Apps wie TouchDown, die Exchange ActiveSync Version 14.1 oder höher verwenden. |E-Mail |E-Mail senden |
|**Office**   und  **OneDrive for Business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**Auf Smartphones und Tablets:**<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Nur auf Telefonen:** <br/> Office Mobile |

>[!NOTE]
- >Die Unterstützung für iOS 10.0 und höher umfasst iPhone- und iPad-Geräte.
- >Die Verwaltung von BlackBerry OS-Geräten wird von Basic Security and Mobility nicht unterstützt. Verwenden Sie BlackBerry Business Cloud Services (BBCS) von BlackBerry, um BlackBerry OS-Geräte zu verwalten. Blackberry-Geräte mit Android OS werden als Standardmäßige Android-Geräte unterstützt
- >Benutzer werden nicht zur Registrierung aufgefordert und werden nicht wegen Richtlinienverletzungen blockiert oder gemeldet, wenn sie den mobilen Browser für den Zugriff auf Microsoft 365-SharePoint-Websites, Dokumente in Office Online oder E-Mails in Outlook Web App verwenden.

Das folgende Diagramm zeigt, was passiert, wenn sich ein Benutzer mit einem neuen Gerät bei einer App meldet, die die Zugriffssteuerung mit Basic Mobility and Security unterstützt. Dem Benutzer wird der Zugriff auf Microsoft 365-Ressourcen in der App bis zur Registrierung des Geräts blockiert.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Grundlegende Zugriffssteuerung für Mobilität und Sicherheit":::

> [!NOTE]
> Richtlinien und Zugriffsregeln, die in Basic Mobility and Security for Microsoft 365 Business Standard erstellt wurden, setzen Exchange ActiveSync Postfachrichtlinien und Gerätezugriffsregeln für mobile Geräte außer Kraft, die im Exchange Admin Center erstellt wurden. Nachdem ein Gerät in Basic Mobility and Security für Microsoft 365 Business Standard registriert wurde, werden alle auf das Gerät angewendeten Exchange ActiveSync-Postfachrichtlinien oder Gerätezugriffsregel ignoriert. Weitere Informationen zu Exchange ActiveSync finden Sie [unter Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="policy-settings-for-mobile-devices"></a>Richtlinieneinstellungen für mobile Geräte

Wenn Sie eine Richtlinie zum Blockieren des Zugriffs mit bestimmten aktivierten Einstellungen erstellen, wird benutzern der Zugriff auf Microsoft 365-Ressourcen blockiert, wenn sie eine unterstützte App verwenden, die unter Zugriffssteuerung für [Microsoft 365-E-Mails](capabilities.md)und -Dokumente aufgeführt ist. 

Die Einstellungen, die Den Zugriff auf Microsoft 365-Ressourcen für Benutzer blockieren können, finden Sie in den folgenden Abschnitten:

- Sicherheit

- Verschlüsselung

- Jailbroken

- Verwaltetes E-Mail-Profil  

Die folgende Abbildung zeigt beispielsweise, was passiert, wenn ein Benutzer mit einem registrierten Gerät mit einer Sicherheitseinstellung in einer mobilen Geräteverwaltungsrichtlinie, die für sein Gerät gilt, nicht kompatibel ist. Der Benutzer meldet sich bei einer App an, die die Zugriffssteuerung mit Basic Mobility and Security unterstützt. Sie können nicht auf Microsoft 365-Ressourcen in der App zugreifen, bis ihr Gerät die Sicherheitseinstellung erfüllt.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Grundlegende Mobilitäts- und Sicherheits-Compliance-Nachricht":::

In den folgenden Abschnitten sind die Richtlinieneinstellungen aufgeführt, mit deren Hilfe Sie mobile Geräte schützen und verwalten können, die eine Verbindung mit Ihren Microsoft 365-Organisationsressourcen herstellen.

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

<sup>1</sup> Mit Samsung Knox können Sie auch eine Verschlüsselung auf Speicherkarten erfordern. 

## <a name="jail-broken-setting"></a>Jailbroken-Einstellung 

|**Name der Einstellung**|**iOS 7.1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Gerät muss ohne Jailbreak und ohne Rootzugriff sein |Ja|Ja|Ja|

## <a name="managed-email-profile-option"></a>Verwaltetes E-Mail-Profil 

Mit der folgenden Option können Benutzer den Zugriff auf ihre Microsoft 365-E-Mails blockieren, wenn sie ein manuell erstelltes E-Mail-Profil verwenden. Benutzer auf iOS-Geräten müssen ihr manuell erstelltes E-Mail-Profil löschen, bevor sie auf ihre E-Mails zugreifen können. Nachdem sie das Profil gelöscht haben, wird automatisch ein neues Profil auf dem Gerät erstellt. Anweisungen dazu, wie Endbenutzer kompatibel werden können, finden Sie unter [Ein vorhandenes E-Mail-Konto wurde gefunden.](/intune-user-help/existing-company-email-account-found)

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
|Zulassen der Google-Sicherung  |Nicht zutreffend|Nein|Ja|
|Automatische Synchronisierung des Google-Kontos zulassen  |Nicht zutreffend|Nein|Ja|

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

Sie können die folgenden zusätzlichen Richtlinieneinstellungen mithilfe von Security & Compliance Center PowerShell-Cmdlets festlegen. Weitere Informationen finden Sie unter [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).

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

Sie können Windows 10-Geräte verwalten, indem Sie sie als mobile Geräte registrieren. Nachdem eine entsprechende Richtlinie bereitgestellt wurde, müssen sich Benutzer mit Windows 10-Geräten bei Basic Mobility and Security registrieren, wenn sie die integrierte E-Mail-App zum ersten Mal verwenden, um auf ihre Microsoft 365-E-Mails zu zugreifen (erfordert Azure AD Premium-Abonnement).

Die folgenden Einstellungen werden für Windows 10-Geräte unterstützt, die als mobile Geräte registriert sind. Diese Einstellung blockiert benutzer nicht den Zugriff auf Microsoft 365-Ressourcen.

### <a name="security-settings"></a>Sicherheitseinstellungen

- Alphanumerisches Kennwort anfordern

- Minimale Kennwortlänge

- Anzahl von Anmeldefehlern, bevor die Gerätedaten gelöscht werden

- Minuten der Inaktivität, bevor das Gerät gesperrt wird

- Kennwortablauf (Tage)

- Kennwortverlauf verfolgen und Wiederverwendung verhindern

>[!NOTE]
>Die folgenden Einstellungen, die Kennwörter regeln, steuern nur lokale Windows-Konten. Windows-Konten, die über den Beitritt zu einer Domäne oder Azure Active Directory bereitgestellt werden, sind von diesen Einstellungen nicht betroffen.

### <a name="system-settings"></a>Systemeinstellungen

Blockieren des Sendens von Diagnosedaten vom Gerät.

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

Wenn ein Gerät verloren geht oder gestohlen wird, können Sie vertrauliche Organisationsdaten entfernen und den Zugriff auf Ihre Microsoft 365-Organisationsressourcen verhindern, indem Sie das Security & Compliance Center > **Data loss prevention** Device  >  **management** löschen. Sie können eine ausgewählte Zurücksetzung durchführen, um nur Organisationsdaten zu entfernen, oder alle Daten vollständig von einem Gerät löschen und es auf die werkseitigen Einstellungen zurücksetzen.

Weitere Informationen finden Sie [unter Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über grundlegende Mobilität und Sicherheit für Microsoft 365](overview.md)

[Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security](create-device-security-policies.md)