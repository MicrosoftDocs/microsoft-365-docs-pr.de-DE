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
- AdminTemplateSet
search.appverid:
- MET150
description: Grundlegende Mobilität und Sicherheit können Ihnen helfen, mobile Geräte zu sichern und zu verwalten.
ms.openlocfilehash: 5619ce6a8fa2c705acc6be08e3af8ad6f90a6d99
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393307"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Funktionen von grundlegender Mobilität und Sicherheit

Grundlegende Mobilität und Sicherheit können Ihnen helfen, mobile Geräte wie iPhones, iPads, Androids und Windows Telefone zu sichern und zu verwalten, die von lizenzierten Microsoft 365 Benutzern in Ihrer Organisation verwendet werden. Sie können Richtlinien für die Verwaltung mobiler Geräte mit Einstellungen erstellen, mit denen Sie den Zugriff auf die Microsoft 365 E-Mails und Dokumente Ihrer Organisation für unterstützte mobile Geräte und Apps steuern können. Wenn ein Gerät verloren geht oder gestohlen wird, können Sie den Geräteinhalt per Remotezugriff löschen, um vertrauliche Organisationsinformationen zu entfernen.

## <a name="supported-devices"></a>Unterstützte Geräte

Sie können Basic Mobility and Security verwenden, um die folgenden Geräte zu sichern und zu verwalten.

- iOS 11.0 oder höher

- Android 5.0 oder höher, Version<sup>3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup> Die Zugriffssteuerung für Windows 8.1 RT-Geräte ist auf Exchange ActiveSync beschränkt.

<sup>2</sup> Die Zugriffssteuerung für Windows 10 erfordert ein Abonnement, das Azure AD Premium enthält, und das Gerät muss mit Azure Active Directory verbunden werden.

<sup>3</sup> Nach Juni 2020 können Android-Versionen, die höher als 9 sind, keine Kennworteinstellungen mehr verwalten, außer auf Samsung Knox-Geräten.

> [!NOTE]
> Geräte, die bereits mit früheren Betriebssystemversionen registriert sind, funktionieren weiterhin, obwohl sich die Funktionen möglicherweise ohne vorherige Ankündigung ändern.

Wenn Personen in Ihrer Organisation mobile Geräte verwenden, die von Basic Mobility and Security nicht unterstützt werden, möchten Sie möglicherweise Exchange ActiveSync App-Zugriff auf Microsoft 365 E-Mails für diese Geräte blockieren, um die Daten Ihrer Organisation sicherer zu machen. Schritte zum Blockieren Exchange ActiveSync finden Sie unter [Verwalten von Gerätezugriffseinstellungen in Basic Mobility and Security.](manage-device-access-settings.md)

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Zugriffssteuerung für Microsoft 365 E-Mails und Dokumente

Die unterstützten Apps für die verschiedenen Arten von mobilen Geräten in der folgenden Tabelle fordern Benutzer auf, sich bei Basic Mobility and Security zu registrieren, wenn es eine neue Richtlinie zur Verwaltung mobiler Geräte gibt, die für das Gerät eines Benutzers gilt und der Benutzer das Gerät noch nicht registriert hat. Wenn das Gerät eines Benutzers einer Richtlinie nicht entspricht, wird ein Benutzer je nach Einrichtung der Richtlinie möglicherweise am Zugriff auf Microsoft 365 Ressourcen in diesen Apps gehindert, oder er hat Zugriff, aber Microsoft 365 meldet einen Richtlinienverstoß.

|**Product**|**iOS 10.0 oder höher**|**Android 5.0 oder höher**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync umfasst integrierte E-Mail- und Drittanbieter-Apps wie TouchDown, die Exchange ActiveSync Version 14.1 oder höher verwenden. |E-Mail |E-Mails |
|**Office**   und  **OneDrive for Business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**Auf Smartphones und Tablets:**<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Nur auf Telefonen:** <br/> Office Mobile |

> [!NOTE]
>
> - Die Unterstützung für iOS 10.0 und neuere Versionen umfasst iPhone und iPad Geräte.
> - Die Verwaltung von BlackBerry OS-Geräten wird von Basic Security and Mobility nicht unterstützt. Verwenden Sie BlackBerry Business Cloud Services (BBS) von BlackBerry, um BlackBerry OS-Geräte zu verwalten. Blackberry-Geräte unter Android OS werden als Android-Standardgeräte unterstützt.
> - Benutzer werden nicht aufgefordert, sich zu registrieren, und sie werden nicht blockiert oder für Richtlinienverletzungen gemeldet, wenn sie den mobilen Browser verwenden, um auf Microsoft 365 SharePoint Websites, Dokumente in Office Online oder E-Mails in Outlook Web App zuzugreifen.

Das folgende Diagramm zeigt, was geschieht, wenn sich ein Benutzer mit einem neuen Gerät bei einer App anmeldet, die die Zugriffssteuerung mit Basic Mobility and Security unterstützt. Der Benutzer wird am Zugriff auf Microsoft 365 Ressourcen in der App gehindert, bis er sein Gerät registriert.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Grundlegende Mobilitäts- und Sicherheitszugriffssteuerung":::

> [!NOTE]
> Richtlinien und Zugriffsregeln, die in Basic Mobility and Security for Microsoft 365 Business Standard erstellt wurden, überschreiben Exchange ActiveSync Postfachrichtlinien und Gerätezugriffsregeln, die im Exchange Admin Center erstellt wurden. Nachdem ein Gerät in Basic Mobility and Security for Microsoft 365 Business Standard registriert wurde, werden alle Exchange ActiveSync Postfachrichtlinie oder Gerätezugriffsregel für mobile Geräte, die auf das Gerät angewendet werden, ignoriert. Weitere Informationen zu Exchange ActiveSync finden Sie [unter Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="policy-settings-for-mobile-devices"></a>Richtlinieneinstellungen für mobile Geräte

Wenn Sie eine Richtlinie erstellen, um den Zugriff mit bestimmten aktivierten Einstellungen zu blockieren, werden Benutzer am Zugriff auf Microsoft 365 Ressourcen gehindert, wenn sie eine unterstützte App verwenden, die in [der Zugriffssteuerung für Microsoft 365-E-Mails und -Dokumente](capabilities.md)aufgeführt ist.

Die Einstellungen, die Benutzer am Zugriff auf Microsoft 365 Ressourcen gehindert werden können, finden Sie in den folgenden Abschnitten:

- Sicherheit

- Verschlüsselung

- Jailbroken

- Verwaltetes E-Mail-Profil

Die folgende Abbildung zeigt beispielsweise, was passiert, wenn ein Benutzer mit einem registrierten Gerät mit einer Sicherheitseinstellung in einer mobilen Geräteverwaltungsrichtlinie, die für sein Gerät gilt, nicht kompatibel ist. Der Benutzer meldet sich bei einer App an, die die Zugriffssteuerung mit Basic Mobility and Security unterstützt. Sie werden am Zugriff auf Microsoft 365 Ressourcen in der App gehindert, bis ihr Gerät der Sicherheitseinstellung entspricht.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Grundlegende Meldung zur Mobilität und Sicherheitscompliance":::

In den folgenden Abschnitten sind die Richtlinieneinstellungen aufgeführt, die Sie verwenden können, um mobile Geräte zu schützen und zu verwalten, die eine Verbindung mit Ihren Microsoft 365 Organisationsressourcen herstellen.

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
|Datenverschlüsselung auf Geräten<sup>1</sup> anfordern |Nein|Ja|Ja|

<sup>1</sup> Mit Samsung Knox können Sie auch Verschlüsselung auf Speicherkarten anfordern.

## <a name="jail-broken-setting"></a>Jailbroken-Einstellung

|**Name der Einstellung**|**iOS 7.1 und höher**|**Android 5 und höher**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Gerät muss ohne Jailbreak und ohne Rootzugriff sein |Ja|Ja|Ja|

## <a name="managed-email-profile-option"></a>Verwaltetes E-Mail-Profil

Die folgende Option kann Benutzer am Zugriff auf ihre Microsoft 365 E-Mails hindern, wenn sie ein manuell erstelltes E-Mail-Profil verwenden. Benutzer auf iOS-Geräten müssen ihr manuell erstelltes E-Mail-Profil löschen, bevor sie auf ihre E-Mails zugreifen können. Nachdem sie das Profil gelöscht haben, wird automatisch ein neues Profil auf dem Gerät erstellt. Anweisungen dazu, wie Endbenutzer konform werden können, finden Sie unter [Ein vorhandenes E-Mail-Konto wurde gefunden.](/intune-user-help/existing-company-email-account-found)

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
|Google-Sicherung zulassen  |–|Nein|Ja|
|Automatische Synchronisierung des Google-Kontos zulassen  |–|Nein|Ja|

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

Sie können die folgenden zusätzlichen Richtlinieneinstellungen mithilfe von Security & Compliance Center PowerShell-Cmdlets festlegen. Weitere Informationen finden Sie unter [Security & Compliance Center PowerShell.](/powershell/exchange/scc-powershell)

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

## <a name="settings-supported-by-windows"></a>von Windows unterstützte Einstellungen

Sie können Windows 10 Geräte verwalten, indem Sie sie als mobile Geräte registrieren. Nachdem eine entsprechende Richtlinie bereitgestellt wurde, müssen Sich Benutzer mit Windows 10 Geräten bei der ersten Verwendung der integrierten E-Mail-App für den Zugriff auf ihre Microsoft 365 E-Mail registrieren (erfordert ein Azure AD Premium-Abonnement).

Die folgenden Einstellungen werden für Windows 10 Geräte unterstützt, die als mobile Geräte registriert sind. Diese Einstellung verhindert nicht, dass Benutzer auf Microsoft 365 Ressourcen zugreifen.

### <a name="security-settings"></a>Sicherheitseinstellungen

- Alphanumerisches Kennwort anfordern

- Minimale Kennwortlänge

- Anzahl von Anmeldefehlern, bevor die Gerätedaten gelöscht werden

- Minuten der Inaktivität, bevor das Gerät gesperrt wird

- Kennwortablauf (Tage)

- Kennwortverlauf verfolgen und Wiederverwendung verhindern

> [!NOTE]
> Die folgenden Einstellungen, die Kennwörter schützen, steuern nur lokale Windows Konten. Windows Konten, die über den Beitritt zu einer Domäne oder Azure Active Directory bereitgestellt werden, sind von diesen Einstellungen nicht betroffen.

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

Wenn ein Gerät verloren geht oder gestohlen wird, können Sie vertrauliche Organisationsdaten entfernen und den Zugriff auf Ihre Microsoft 365 Organisationsressourcen verhindern, indem Sie eine Zurücksetzung aus dem Security & Compliance Center > **Data Loss Prevention** Device  >  **Management** ausführen. Sie können eine ausgewählte Zurücksetzung durchführen, um nur Organisationsdaten zu entfernen, oder alle Daten vollständig von einem Gerät löschen und es auf die werkseitigen Einstellungen zurücksetzen.

Weitere Informationen finden Sie unter ["Zurücksetzen eines mobilen Geräts in Basic Mobility and Security".](wipe-mobile-device.md)

## <a name="related-content"></a>Verwandte Inhalte

[Übersicht über grundlegende Mobilität und Sicherheit für Microsoft 365](overview.md) (Artikel)\
[Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security](create-device-security-policies.md) (Artikel)