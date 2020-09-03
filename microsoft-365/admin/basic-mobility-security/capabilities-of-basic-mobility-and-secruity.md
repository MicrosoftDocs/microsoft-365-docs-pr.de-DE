---
title: Funktionen der grundlegenden Mobilität und Sicherheit
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
description: Grundlegende Mobilität und Sicherheit können Ihnen helfen, Mobile Geräte zu sichern und zu verwalten.
ms.openlocfilehash: 32393f39655b81313f6592936c55e36ffe029a27
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336916"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Funktionen der grundlegenden Mobilität und Sicherheit

Grundlegende Mobilität und Sicherheit können Ihnen helfen, Mobile Geräte wie iPhones, iPads, Androiden und Windows-Telefone, die von lizenzierten Microsoft 365-Benutzern in Ihrer Organisation verwendet werden, zu sichern und zu verwalten. Sie können Richtlinien für die Verwaltung mobiler Geräte mit Einstellungen erstellen, mit denen Sie den Zugriff auf die Microsoft 365-e-Mails und-Dokumente Ihrer Organisation für unterstützte mobile Geräte und apps steuern können. Wenn ein Gerät verloren geht oder gestohlen wird, können Sie den Geräteinhalt per Remotezugriff löschen, um vertrauliche Organisationsinformationen zu entfernen.

## <a name="supported-devices"></a>Unterstützte Geräte

Sie können die grundlegenden Mobilitäts-und Sicherheitseinstellungen verwenden, um die folgenden Geräte zu sichern und zu verwalten.

- IOS 11,0 oder höhere Versionen
    
- Android 5,0 oder höher Version<sup>3</sup>
    
- Windows 8.1<sup>1</sup>
    
- Windows 8.1 RT<sup>1</sup>
    
- Windows 10<sup>2</sup>
    
- Windows 10 Mobile<sup>2</sup>   

<sup>1</sup> Die Zugriffssteuerung für Windows 8.1 RT Geräte ist auf Exchange ActiveSync limitiert.

<sup>2</sup> Die Zugriffssteuerung für Windows 8.1 RT Geräte ist auf Exchange ActiveSync limitiert.
Für die Zugriffssteuerung für Windows 10 ist ein Abonnement erforderlich, das Azure AD Premium enthält, und das Gerät muss mit Azure Active Directory verbunden werden.

<sup>3</sup> Die Zugriffssteuerung für Windows 8.1 RT Geräte ist auf Exchange ActiveSync limitiert.
Nach Juni 2020 können Android-Versionen später als 9 keine Kennworteinstellungen mit Ausnahme von Samsung Knox-Geräten verwalten.

>[!NOTE]
>Geräte, die bereits mit früheren BS-Versionen registriert sind, funktionieren weiterhin, obwohl sich die Funktionen möglicherweise ohne vorherige Ankündigung ändern.

Wenn Personen in Ihrer Organisation Mobile Geräte verwenden, die nicht von grundlegender Mobilität und Sicherheit unterstützt werden, können Sie den Exchange ActiveSync-App-Zugriff auf Microsoft 365-e-Mails für diese Geräte blockieren, um die Sicherheit Ihrer Organisation zu verbessern. Schritte zum Blockieren von Exchange ActiveSync finden Sie unter [Verwalten von gerätezugriffseinstellungen in Basic Mobility and Security](manage-device-access-settings-in-basic-mobility-and-security.md).

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Zugriffssteuerung für e-Mails und Dokumente von Microsoft 365

In den unterstützten Apps für die verschiedenen Typen von mobilen Geräten in der folgenden Tabelle werden Benutzer aufgefordert, sich für grundlegende Mobilitäts-und Sicherheitseinstellungen anzumelden, in denen eine neue Verwaltungsrichtlinie für mobile Geräte vorliegt, die auf das Gerät eines Benutzers angewendet wird und der Benutzer sich zuvor nicht für das Gerät registriert hat. Wenn das Gerät eines Benutzers nicht einer Richtlinie entspricht, je nachdem, wie die Richtlinie festgelegt wird, wird ein Benutzer möglicherweise für den Zugriff auf Microsoft 365-Ressourcen in diesen apps gesperrt, oder er hat Zugriff, aber Microsoft 365 meldet einen Richtlinienverstoß.

|**Produkt**|**IOS 10,0 oder höher**|**Android 5,0 oder höher**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync umfasst integrierte e-Mail-und Drittanbieter-apps wie Touchdown, die die Exchange ActiveSync-Version 14,1 oder höher verwenden. |E-Mail |E-Mail |
|**Office-Dienst**   und **OneDrive für Unternehmen** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**Auf Telefonen und Tablets**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Nur auf Telefonen:** <br/> Office Mobile |

>[!NOTE]
- >Unterstützung für IOS 10,0 und höhere Versionen umfasst iPhone-und iPad-Geräte.
- >Die Verwaltung von BlackBerry OS-Geräten wird von der Verwaltung mobiler Geräte für Microsoft 365 nicht unterstützt. Verwenden Sie BlackBerry Business Cloud Services (BBCs) von BlackBerry, um BlackBerry OS-Geräte zu verwalten. BlackBerry-Geräte mit Android OS werden als Standard-Android-Geräte unterstützt.
- >Benutzer werden nicht zur Registrierung aufgefordert und nicht für Richtlinienverstöße gesperrt oder gemeldet, wenn Sie den mobilen Browser verwenden, um auf Microsoft 365 SharePoint-Websites, Dokumente in Office Online oder e-Mails in Outlook Web App zuzugreifen.
    
Das folgende Diagramm zeigt, was passiert, wenn sich ein Benutzer mit einem neuen Gerät bei einer App anmeldet, die die Zugriffssteuerung mit grundlegender Mobilität und Sicherheit unterstützt. Dem Benutzer wird der Zugriff auf Microsoft 365-Ressourcen in der APP bis zum Registrieren des Geräts blockiert.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Grundlegende Mobilitäts-und Sicherheitszugriffssteuerung":::

Hinweis: in MDM for Microsoft 365 Business Standard erstellte Richtlinien und Zugriffsregeln setzen die Postfachrichtlinien für mobile Geräte von Exchange ActiveSync und Gerätezugriffsregeln außer Kraft, die im Exchange Admin Center erstellt wurden. Nachdem ein Gerät in MDM für Microsoft 365 Business Standard registriert wurde, werden alle Exchange ActiveSync-Postfachrichtlinien für mobile Geräte oder Gerätezugriffsregeln, die auf das Gerät angewendet werden, ignoriert. Weitere Informationen zu Exchange ActiveSync finden Sie unter [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="policy-settings-for-mobile-devices"></a>Richtlinieneinstellungen für mobile Geräte

Wenn Sie eine Richtlinie zum Blockieren des Zugriffs mit bestimmten Einstellungen erstellen, wird Benutzern der Zugriff auf Microsoft 365-Ressourcen blockiert, wenn eine unterstützte App verwendet wird, die in der [Zugriffssteuerung für Microsoft 365-e-Mails und-Dokumente](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0?ui=en-us&rs=en-us&ad=us#bkmk_accesscontrol)aufgeführt ist. 

Die Einstellungen, die Benutzern den Zugriff auf Microsoft 365-Ressourcen sperren können, sind in den folgenden Abschnitten aufgeführt:

- Sicherheit
    
- Verschlüsselung
    
- Jailbroken
    
- Verwaltetes E-Mail-Profil  

Die folgende Abbildung zeigt beispielsweise, was passiert, wenn ein Benutzer mit einem registrierten Gerät mit einer Sicherheitseinstellung in einer mobilen Geräteverwaltungsrichtlinie, die für sein Gerät gilt, nicht kompatibel ist. Der Benutzer meldet sich bei einer APP an, die die Zugriffssteuerung mit grundlegender Mobilität und Sicherheit unterstützt. Sie können den Zugriff auf Microsoft 365-Ressourcen in der APP erst dann sperren, wenn Ihr Gerät der Sicherheitseinstellung entspricht.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Grundlegende Mobilitäts-und Sicherheits Konformitäts Nachricht":::

In den folgenden Abschnitten werden die Richtlinieneinstellungen aufgeführt, die Sie zum Sichern und Verwalten von mobilen Geräten verwenden können, die eine Verbindung mit Ihren Microsoft 365-Organisationsressourcen herstellen.

## <a name="security-settings"></a>Sicherheitseinstellungen

|**Name der Einstellung**|**IOS 7,1 und höher**|**Android 5 und höher**|**Samsung Knox**|
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

|**Name der Einstellung**|**IOS 7,1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Datenverschlüsselung auf Geräten<sup>1</sup> erforderlich |Nein|Ja|Ja|

<sup>1</sup> Mit Samsung Knox können Sie auch eine Verschlüsselung auf Speicherkarten verlangen. 

## <a name="jail-broken-setting"></a>Jailbroken-Einstellung 

|**Name der Einstellung**|**IOS 7,1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Gerät muss ohne Jailbreak und ohne Rootzugriff sein |Ja|Ja|Ja|

## <a name="managed-email-profile-option"></a>Verwaltetes E-Mail-Profil 

Die folgende Option kann Benutzer daran hindern, auf Ihre Microsoft 365-e-Mails zuzugreifen, wenn Sie ein manuell erstelltes e-Mail-Profil verwenden. Benutzer auf iOS-Geräten müssen ihr manuell erstelltes E-Mail-Profil löschen, bevor sie auf ihre E-Mails zugreifen können. Nachdem Sie das Profil gelöscht haben, wird automatisch ein neues Profil auf dem Gerät erstellt. Anweisungen dazu, wie Endbenutzer kompatibel werden können, finden Sie unter [ein vorhandenes e-Mail-Konto wurde gefunden](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).

|**Name der Einstellung**|**IOS 7,1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|E-Mail-Profil ist verwaltet |Ja|Nein|Nein|

## <a name="cloud-settings"></a>Cloud-Einstellungen 

|**Name der Einstellung**|**IOS 7,1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Verschlüsselte Sicherung anfordern |Ja|Nein|Nein|
|Cloud-Sicherung blockieren |Ja|Nein|Nein|
|Dokumentsynchronisierung blockieren |Ja|Nein|Nein|
|Fotosynchronisierung blockieren  |Ja|Nein|Nein|
|Google-Sicherung zulassen  |Nicht zutreffend|Nein|Ja|
|Automatische Synchronisierung des Google-Kontos zulassen  |Nicht zutreffend|Nein|Ja|

## <a name="system-settings"></a>Systemeinstellungen 

|**Name der Einstellung**|**IOS 7,1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bildschirmaufnahme blockieren |Ja|Nein|Ja|
|Senden von Diagnosedaten vom Gerät aus blockieren |Ja|Nein|Ja|

## <a name="application-settings"></a>Anwendungseinstellungen 

|**Name der Einstellung**|**IOS 7,1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Videokonferenzen auf Gerät blockieren |Ja|Nein|Nein|
|Zugriff auf Anwendungsspeicher blockieren |Ja|Nein|Ja|
|Kennwort beim Zugriff auf Anwendungsspeicher erforderlich |Nein|Ja|Ja|

## <a name="device-capabilities-settings"></a>Gerätefunktionseinstellungen 

|**Name der Einstellung**|**IOS 7,1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Verbindung mit Speicherwechselmedien blockieren |Ja|Ja|Nein|
|Bluetooth-Verbindungen blockieren |Ja|Ja|Nein|

##  <a name="additional-settings"></a>Zusätzliche Einstellungen 

Sie können die folgenden zusätzlichen Richtlinieneinstellungen mithilfe von PowerShell-Cmdlets festlegen. Weitere Informationen finden Sie unter [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).

|**Name der Einstellung**|**IOS 7,1 und höher**|**Android 5 und höher**|
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
|Parametermaxpasswordgraceperiod |Ja|Nein|
|PasswordQuality |Nein|Ja|
|SystemSecurityTLS  |Ja|Nein|
|WLANEnabled  |Nein|Nein|

## <a name="settings-supported-by-windows"></a>Von Windows unterstützte Einstellungen 

Sie können Windows 10-Geräte verwalten, indem Sie Sie als mobile Geräte registrieren. Nachdem eine zutreffende Richtlinie bereitgestellt wurde, müssen sich Benutzer mit Windows 10-Geräten bei der ersten Verwendung der integrierten e-Mail-App für den Zugriff auf Ihre Microsoft 365-e-Mail-Adresse für die grundlegende Mobilität und Sicherheit registrieren (erfordert Azure AD Premium-Abonnement).

Die folgenden Einstellungen werden für Windows 10-Geräte unterstützt, die als mobile Geräte registriert sind. Durch diese Einstellung wird verhindert, dass Benutzer auf Microsoft 365-Ressourcen zugreifen.

### <a name="security-settings"></a>Sicherheitseinstellungen

- Alphanumerisches Kennwort anfordern

- Minimale Kennwortlänge
    
- Anzahl von Anmeldefehlern, bevor die Gerätedaten gelöscht werden
    
- Minuten der Inaktivität, bevor das Gerät gesperrt wird
    
- Kennwortablauf (Tage)
    
- Kennwortverlauf verfolgen und Wiederverwendung verhindern   

>[!NOTE]
>Die folgenden Einstellungen zum regulieren von Kennwörtern Steuern nur lokale Windows-Konten. Windows-Konten, die über den Beitritt einer Domäne oder Azure-Active Directory bereitgestellt werden, sind von diesen Einstellungen nicht betroffen.

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

Wenn ein Gerät verloren geht oder gestohlen wird, können Sie vertrauliche Organisationsdaten entfernen und den Zugriff auf Ihre Microsoft 365-Organisationsressourcen verhindern, indem Sie eine Zurücksetzung aus Sicherheits & Compliance Center > **Datenverlust Verhinderung**  >  **Geräteverwaltung**durchführen. Sie können eine ausgewählte Zurücksetzung durchführen, um nur Organisationsdaten zu entfernen, oder alle Daten vollständig von einem Gerät löschen und es auf die werkseitigen Einstellungen zurücksetzen.

Weitere Informationen finden Sie unter [wischen eines mobilen Geräts in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über grundlegende Mobilität und Sicherheit für Microsoft 365](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[Erstellen von Gerätesicherheitsrichtlinien in grundlegender Mobilität und Sicherheit](create-device-security-policies-in-basic-mmobility-and-security.md)