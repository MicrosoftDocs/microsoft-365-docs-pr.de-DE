---
title: Erforderliche Arbeit für die Implementierung von Identität und Gerät Zugriffsrichtlinien - Microsoft 365 Enterprise | Microsoft-Dokumente
description: Beschreibt die Richtlinien für Empfehlungen von Microsoft zur Anwendung von Identitäts- und Gerätezugriffsrichtlinien und -konfigurationen
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: e97b16b3520d500737e0b397e8e2a515ecac9b3f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868214"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Erforderliche Arbeit für die Implementierung von Identität und Gerät Zugriffsrichtlinien

In diesem Artikel werden die erforderlichen Komponenten, die zum Implementieren, bevor Sie die empfohlenen Identität und Zugriffsrichtlinien Gerät bereitstellen können erforderlich sind. In diesem Artikel werden auch die Plattform Client Standardkonfigurationen, die es wird empfohlen, um SSO am besten für Ihre Benutzer als auch die technischen Voraussetzungen für bedingten Zugriff bereitzustellen.


## <a name="prerequisites"></a>Voraussetzungen

Vor der Implementierung der empfohlenen Identität und Zugriffsrichtlinien Gerät, sind es mehrere Komponenten, die Ihrer Organisation erfüllt sein müssen. Finden Sie in der folgenden Tabelle für die erforderlichen Komponenten, die für Ihre Umgebung gelten. 


| Konfiguration | Nur für die Cloud | Active Directory mit Hash kennwortsynchronisierung |  Verbund mit AD FS |
| :------------- | :-----------: | :--------------: | :------------: |
|  [Hash Kennwortsynchronisierung konfigurieren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Dies muss aktiviert sein, um verlorene Anmeldeinformationen zu erkennen und zum Ausführen an diese Risiken basierend bedingten Zugriff. **Hinweis:** Dies ist erforderlich, unabhängig davon, ob Ihre Organisation verwalteten Authentifizierung, wie Pass-Through-Authentifizierung (PTA) oder Verbundauthentifizierung verwendet. |    | Ja | Ja |
| Automatisch melden sich Benutzer in, wenn sie auf ihren corporate Geräten mit dem Unternehmensnetzwerk verbunden sind [nahtlos einmaliges Anmelden aktivieren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) . |  | Ja |  |
| [Configure namens Netzwerke](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD-Schutz erfasst und analysiert alle verfügbaren Sitzungsdaten um einen Faktor Risiko zu generieren. Es wird empfohlen, dass Sie Ihrer Organisation öffentliche IP-Adressbereiche für Ihr Netzwerk in Azure AD mit dem Namen Netzwerkkonfiguration anzugeben. Datenverkehr von diesen Bereichen erhält einen Faktor Risiko, damit der Datenverkehr von außerhalb der Unternehmensfirewall Umgebung als höhere Risiko Punktzahl behandelt wird. | Ja  | Ja | Ja |
|[Self-service Password Reset (SSPR) und die mehrstufige Authentifizierung (mehrstufiger Authentifizierung das) für alle Benutzer zu registrieren](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Es wird empfohlen, dass Sie Benutzer für Azure mehrstufiger Authentifizierung das im Voraus registrieren. Azure AD-Schutz nutzt Azure mehrstufiger Authentifizierung das zusätzliche Sicherheit-Überprüfung ausführen. Darüber hinaus sollten für die Anmeldung am besten Benutzer bei der Installation der [Microsoft Authentifizierungsserver App](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) und die Microsoft-Unternehmensportal app auf ihren Geräten. Dies können aus dem app-Speicher für die einzelnen Plattformen installiert werden. | Ja | Ja | Ja |
| [Aktivieren der automatischen Geräteregistrierung von in der Domäne eingebundenen Windows-Computern](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup): Mit dem bedingten Zugriff können Sie sicherstellen, dass das Gerät, das sich mit dem Dienst verbindet, in die Domäne eingebunden oder mit ihr kompatibel ist. Für eine Unterstützung auf Windows-Computern muss das Gerät bei Azure AD registriert sein.  In diesem Artikel wird die Konfiguration der automatischen Geräteregistrierung erläutert. |   | Ja |  Ja |
| **Vorbereiten Ihres Supportteams**: Sie sollten vorausplanen, wie Sie mit Benutzern umgehen, die keine MFA durchführen können. Sie können sie z.B. einer Gruppe für den Richtlinienausschluss hinzufügen oder neue MFA-Informationen für sie registrieren. Bevor Sie eine dieser sicherheitsrelevanten Änderungen vornehmen, müssen Sie sicherstellen, dass die Anforderung auch vom tatsächlichen Benutzer gesendet wird. Es kann hilfreich sein, den Vorgesetzten des Benutzers bei der Genehmigung mit einzubeziehen. | Ja | Ja | Ja |
| [Konfigurieren der Kennwortrückschreibung in lokalem AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started): Über das Rückschreiben von Kennwörtern kann Azure AD die Benutzer im Fall eines hohen Gefährdungsrisikos des Kontos dazu auffordern, ihre lokalen Kennwörter zu ändern. Diese Funktion kann mithilfe von Azure AD Connect auf zwei Arten aktiviert werden: Sie können das Rückschreiben von Kennwörtern entweder im Setup-Assistenten für Azure AD Connect auf dem Bildschirm für optionale Funktionen oder über Windows PowerShell aktivieren. |   | Ja | Ja |
| [Azure Active Directory-Identitätsschutz aktivieren](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable). Azure AD-Schutz können Sie Identitäten Ihrer Organisation beeinflussen potenzielle Sicherheitsrisiken zu erkennen und Konfigurieren von automatischen Behebung Richtlinie zu niedrig, Mittel und hoch-Anmeldung Risiken und Benutzer Risiko.  | Ja | Ja | Ja |
| **Aktivieren der modernen Authentifizierung** für [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) und [Skype für Business Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Moderne Authentifizierung ist eine Voraussetzung für die Verwendung von Multi-Factor Authentication (mehrstufiger Authentifizierung das). Moderne Authentifizierung ist für Office 2016 Clients, SharePoint Online und OneDrive für Unternehmen standardmäßig aktiviert. | Ja | Ja | Ja |
|||||



## <a name="recommended-client-configurations"></a>Empfohlene Clientkonfigurationen
Dieser Abschnitt beschreibt die von uns empfohlenen Standardkonfigurationen für Ihren Plattform-Client, um die bestmögliche Benutzererfahrung bei der einmaligen Anmeldung zu erzielen und die technischen Voraussetzungen für einen bedingten Zugriff bereitzustellen.

### <a name="windows-devices"></a>Windows-Geräte
Windows 10 (Version 1703 oder höher) wird empfohlen, da Azure zur Bereitstellung der bestmöglichen SSO-Erfahrung für lokale Prozesse und Azure AD konzipiert ist. Geräte mit Geschäfts- oder Schulkonten sollten so konfiguriert werden, dass sie direkt mit Azure AD verknüpft werden. Wenn aber die Organisation einen lokalen AD-Domänenbeitritt verwendet, sollten diese Geräte [so konfiguriert werden, dass Sie automatisch und im Hintergrund bei Azure AD registriert werden](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Bei BYOD-Windows-Geräten können Benutzer „Geschäfts- oder Schulkonto hinzufügen“ verwenden. Beachten Sie, dass Benutzer eines Chrome-Browsers unter Windows 10 eine [Erweiterung installieren](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) müssen, damit die Benutzer die gleiche problemlose Anmeldeerfahrung wie unter Edge/IE erleben können. Falls in Ihrer Organisation Windows 7-Rechner in der Domäne verwendet werden, können Sie das „Microsoft Workplace Join für Nicht-Windows 10 Computer“-[Paket zum Registrieren](https://www.microsoft.com/download/details.aspx?id=53554) dieser Geräte mit Azure AD installieren.

### <a name="ios-devices"></a>iOS-Geräte
Es wird empfohlen, die [Authentifizierung mit Microsoft app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) auf Geräten der Benutzer vor der Bereitstellung von bedingten Zugriff oder mehrstufiger Authentifizierung das Richtlinien installieren. Mindestens sollte die app installiert werden, wenn Benutzer aufgefordert werden, registrieren ihr Gerät mit Azure AD durch Hinzufügen einer Arbeit oder Schule Konto oder beim Installieren von Intune Unternehmen Portal app ihr Gerät in Management registrieren. Dies hängt von der konfigurierten bedingten Zugriffsrichtlinie.

### <a name="android-devices"></a>Android-Geräte
Es wird empfohlen, dass Benutzer die [Intune-Unternehmensportal-App](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en
) und die [Microsoft Authenticator-App](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) installieren, bevor bedingte Zugriffsrichtlinien bereitgestellt werden, oder im Bedarfsfall während bestimmter Authentifizierungsversuche. Nach der Installation der App können Benutzer aufgefordert werden, sich mit Azure AD zu registrieren oder ihr Gerät bei Intune zu registrieren. Dies hängt von der konfigurierten bedingten Zugriffsrichtlinie ab.

Wir empfehlen außerdem, dass firmeneigene Geräte (COD) auf OEMs und Versionen standardisiert werden, die Android for Work oder Samsung Knox zur Verwaltung von E-Mail-Konten und zum Schutz durch Intune-MDM-Richtlinien unterstützen.


### <a name="recommended-email-clients"></a>Empfohlene E-Mail-Clients
Die folgenden e-Mail-Clients unterstützen moderne Authentifizierung und bedingte Zugriff. 

|Plattform|Client|Version/Hinweise|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Aktivieren der modernen Authentifizierung](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [Erforderliche Updates](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook für iOS|[Neueste Version](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook für Android|[Neueste Version](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**Mac OS**|Outlook|2016|
|**Linux**|Nicht unterstützt||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Empfohlene Clientplattformen für den Schutz von Dokumenten
Die folgenden Clients werden empfohlen, wenn eine Richtlinie zum Schutz von Dokumenten angewendet wurde:

|Plattform|Word/Excel/PowerPoint|OneNote|OneDrive-App|SharePoint-App|OneDrive-Synchronisierungsclient|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Unterstützt|Unterstützt|N/V|N/V|Vorschau<sup>*</sup>|
|Windows 8.1|Unterstützt|Unterstützt|N/V|N/V|Vorschau<sup>*</sup>|
|Windows 10|Unterstützt|Unterstützt|N/V|N/V|Vorschau<sup>*</sup>|
|Windows Phone 10|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|
|Android|Unterstützt|Unterstützt|Unterstützt|Unterstützt|N/V|
|iOS|Unterstützt|Unterstützt|Unterstützt|Unterstützt|N/V|
|Mac OS|Öffentliche Vorschau|Öffentliche Vorschau|N/V|N/V|Nicht unterstützt|
|Linux|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|

<sup>*</sup>Hier erfahren Sie mehr über die Verwendung von bedingten Zugriff mit dem [OneDrive Sync-Client](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Office 365-Clientunterstützung
Weitere Informationen zu Office 365-Client-Unterstützung finden Sie unter den folgenden Artikeln:
- [Support für Office 365 Client App - bedingten Zugriff](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Support für Office 365 Client App - Verwaltung von mobilen](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Support für Office 365 Client App - modernen Authentifizierung](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Schützen von Administratorkonten
Azure Active Directory bietet eine einfache Möglichkeit für den Einstieg mit einer vorkonfigurierten bedingte Zugriffsrichtlinie Administratorzugriff schützen. In Azure AD, wechseln Sie zu der Blade bedingten Zugriff, und suchen Sie nach dieser Richtlinie – **Baseline-Richtlinie: erfordern mehrstufiger Authentifizierung das für Administratoren**. Klicken Sie auf diese Richtlinie, und wählen Sie **Richtlinie sofort verwenden**. 

Diese Richtlinie erfordert mehrstufiger Authentifizierung das für die folgenden Rollen:
- Globale Administratoren
- SharePoint-Administratoren
- Exchange-Administratoren
- Bedingte Access-Administratoren
- Sicherheits-Administratoren

Weitere Informationen finden Sie unter [Sicherheitsrichtlinien für Azure AD-Administratorkonten Baseline](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/).

Folgende: zusätzliche Informationen
- Verwenden Sie Azure AD privilegierten Identitätsmanagement, um die Anzahl der beständigen Administratorkonten reduziert. Finden Sie unter [Verwenden von PIM](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Systemzugriff Management in Office 365 verwenden](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview) , um Ihre Organisation Verstöße zu schützen, die möglicherweise einer vorhandenen verwenden privilegierten Administratorkonten mit stehende Zugriff auf vertrauliche Daten oder Zugriff auf wichtige Konfigurationseinstellungen. 
- Verwenden Sie Office 365-Administratorkonten ausschließlich für die Verwaltung. Administratoren sollten einen separaten Benutzer berücksichtigt werden regelmäßig ohne Administratorrechte verwenden und nur verwenden, deren Verwaltungskonto bei Bedarf für die Durchführung eine Aufgabe aus, deren Funktion zugeordnet haben. [Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) -Administratorrollen berechtigt, deutlich mehr zu Office 365-Dienste.
- Befolgen Sie bewährte Methoden zum Sichern von privilegierter Konten in Azure AD, wie in diesem [Artikel](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)beschrieben.

## <a name="next-steps"></a>Nächste Schritte

[Konfigurieren der allgemeinen Identität und Gerät Zugriffsrichtlinien](identity-access-policies.md)

