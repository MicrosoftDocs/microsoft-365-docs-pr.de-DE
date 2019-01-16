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
ms.openlocfilehash: ee517e774e0606c62efdc67d869ad0aca5a41640
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868214"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Erforderliche Arbeit für die Implementierung von Identität und Gerät Zugriffsrichtlinien

In diesem Artikel werden die erforderlichen Komponenten, die implementiert werden, bevor Sie die empfohlenen Identität und Zugriffsrichtlinien Gerät bereitstellen können. In diesem Artikel werden auch die Plattform Client Standardkonfigurationen, die es wird empfohlen, um SSO am besten für Ihre Benutzer als auch der technischen Voraussetzungen für bedingten Zugriff bereitzustellen.


## <a name="prerequisites"></a>Voraussetzungen

Vor der Implementierung der empfohlenen Identität und Zugriffsrichtlinien Gerät, sind es mehrere Komponenten, die Ihrer Organisation erfüllt sein müssen. Die folgende Tabelle enthält die erforderlichen Komponenten, die für Ihre Umgebung gelten. 


| Konfiguration | Nur für die Cloud | Active Directory mit Hash kennwortsynchronisierung |  Pass-Through-Authentifizierung |  Verbund mit AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Hash Kennwortsynchronisierung konfigurieren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Dies muss zum Erkennen von verlorene Anmeldeinformationen und auf diese für bedingten Zugriff Risiko-basierte fungieren aktiviert sein. **Hinweis:** Dies ist erforderlich, unabhängig davon, ob Ihre Organisation verwalteten Authentifizierung, wie Pass-Through-Authentifizierung (PTA) oder Verbundauthentifizierung verwendet. |    | Ja | Ja | Ja |
| Automatisch melden sich Benutzer in, wenn sie auf ihren corporate Geräten mit dem Unternehmensnetzwerk verbunden sind [nahtlos einmalige Anmeldung auf Aktivieren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) . |  | Ja | Ja |  |
| [Configure namens Netzwerke](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD-Schutz erfasst und analysiert alle verfügbaren Sitzungsdaten um einen Faktor Risiko zu generieren. Es wird empfohlen, dass Sie Ihrer Organisation öffentliche IP-Adressbereiche für Ihr Netzwerk in Azure AD mit dem Namen Netzwerkkonfiguration anzugeben. Datenverkehr von diesen Bereichen erhält eine geringere Risiken Bewertung, und Datenverkehr von außerhalb der Unternehmensfirewall Umgebung erhält eine höhere Risiko Punktzahl. | Ja  | Ja | Ja | Ja |
|[Self-service Password Reset (SSPR) und die mehrstufige Authentifizierung (mehrstufiger Authentifizierung das) für alle Benutzer zu registrieren](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Es wird empfohlen, dass Sie Benutzer für Azure mehrstufiger Authentifizierung das im Voraus registrieren. Azure AD-Schutz nutzt Azure mehrstufiger Authentifizierung das zusätzliche Sicherheit-Überprüfung ausführen. Darüber hinaus sollten für die Anmeldung am besten Benutzer bei der Installation die [Authentifizierung mit Microsoft app](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) und die Microsoft Unternehmensportal app auf ihren Geräten. Dies können aus dem app-Speicher für die einzelnen Plattformen installiert werden. | Ja | Ja | Ja | Ja |
| [Automatische Device Registrierung in die Domäne eingebundener Windows-Computer zu aktivieren](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). Bedingte Access stellt sicher, dass die Geräte, die eine Verbindung mit apps Domäne oder kompatibel sind. Das Gerät muss zur Unterstützung der dies auf Computern mit Windows Azure AD registriert werden.  In diesem Artikel wird erläutert, wie automatische Device-Registrierung konfigurieren. |   | Ja |  Ja |  Ja |
| **Vorbereiten von Ihrem Supportteam**. Haben Sie einen Plan für Benutzer, die mehrstufiger Authentifizierung das nicht durchgeführt werden kann. Dies konnte eine Richtlinie Ausschluss-Gruppe hinzugefügt, oder Registrieren von neuen mehrstufiger Authentifizierung das Informationen für sie. Vor der Durchführung von entweder sicherheitsrelevante ändern, müssen Sie sicherstellen, dass der aktuelle Benutzer die Anforderung stellt. Benutzer-Manager können Sie mit der Genehmigung erfordern ist ein effektiver Schritt. | Ja | Ja | Ja | Ja |  
| [Configure Kennwort Rückschreiben in lokalen AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Kennwort Rückschreiben ermöglicht Azure AD erzwungen, dass Benutzer ihre lokalen Kennwörter ändern, wenn ein Konto mit hohem Risiko Kompromiss erkannt wird. Sie können dieses Feature mit Azure AD-verbinden auf zwei Arten aktivieren: aktivieren **Kennwort Rückschreiben** im optionalen Features Bildschirm des Setup-Assistenten von Azure Active Directory verbinden, oder über Windows PowerShell zu aktivieren. |   | Ja | Ja | Ja |
| [Azure Active Directory-Identitätsschutz aktivieren](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable). Azure AD-Schutz können Sie Identitäten Ihrer Organisation beeinflussen potenzielle Sicherheitsrisiken zu erkennen und Konfigurieren einer Richtlinie für automatische Remediation zu niedrig, Mittel und hoch-Anmeldung Risiken und Benutzer Risiko.  | Ja | Ja | Ja | Ja |
| **Aktivieren der modernen Authentifizierung** für [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) und [Skype für Business Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Moderne Authentifizierung ist eine Voraussetzung für die Verwendung von Multi-Factor Authentication (mehrstufiger Authentifizierung das). Moderne Authentifizierung ist für Office 2016 Clients, SharePoint Online und OneDrive für Unternehmen standardmäßig aktiviert. | Ja | Ja | Ja | Ja |
||||||



## <a name="recommended-client-configurations"></a>Empfohlene Clientkonfigurationen
Dieser Abschnitt beschreibt die Plattform Client Standardkonfigurationen, die es wird empfohlen, um SSO am besten für Ihre Benutzer als auch der technischen Voraussetzungen für bedingten Zugriff bereitzustellen.

### <a name="windows-devices"></a>Windows-Geräte
Wir empfehlen die Windows-10 (Version 1703 oder höher), wie Azure bereitgestellt werden sollen Erfahrung die reibungslose SSO für lokale und Azure AD möglich. Arbeit "oder" Schule ausgestellt Geräte zur Teilnahme Azure AD direkt konfiguriert werden oder wenn die Organisation genutzt lokalen AD-Domäne beitreten, sollte diese Geräte [automatisch konfiguriert und im Hintergrund mit Azure Active Directory registrieren](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Für BYOD Windows-Geräte können Benutzer **Arbeit hinzuzufügen oder Schule Konto**verwenden. Beachten Sie, dass Chrome-Browsers Benutzer auf Windows 10 zum [Installieren einer Erweiterungs](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) der gleichen reibungslose Anmeldung als Edge/IE-Benutzer erhalten müssen. Auch wenn Ihre Organisation in die Domäne eingebundener Windows 7-Geräte umfasst, können Sie Microsoft Jahrestag teilnehmen für nicht - Windows-10-Computer [Herunterladen des Pakets zum Registrieren](https://www.microsoft.com/download/details.aspx?id=53554) der Geräte mit Azure AD installieren.

### <a name="ios-devices"></a>iOS-Geräte
Es wird empfohlen, die [Authentifizierung mit Microsoft app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) auf Geräten der Benutzer vor der Bereitstellung von bedingten Zugriff oder mehrstufiger Authentifizierung das Richtlinien installieren. Mindestens sollte die app installiert werden, wenn Benutzer werden aufgefordert, ihr Gerät mit Azure Active Directory registrieren, durch Hinzufügen einer Arbeit oder Schule Konto oder bei der Installation der Intune Unternehmen Portal app registrieren Sie ihr Gerät in Management. Dies hängt von der konfigurierten bedingten Zugriffsrichtlinie.

### <a name="android-devices"></a>Android-Geräte
Es wird empfohlen, dass Benutzer die [Intune-Unternehmensportal-App](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) und die [Microsoft Authenticator-App](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) installieren, bevor bedingte Zugriffsrichtlinien bereitgestellt werden, oder im Bedarfsfall während bestimmter Authentifizierungsversuche. Nach der Installation der App können Benutzer aufgefordert werden, sich mit Azure AD zu registrieren oder ihr Gerät bei Intune zu registrieren. Dies hängt von der konfigurierten bedingten Zugriffsrichtlinie ab.

Wir empfehlen auch firmeneigenen Geräten (COD) für OEMs und Versionen, die für die Arbeit oder Samsung Knox zulassen-Mail-Konten, verwaltet und geschützt durch Richtlinie Intune MDM Android unterstützen standardisiert sind.


### <a name="recommended-email-clients"></a>Empfohlene E-Mail-Clients
Die folgenden e-Mail-Clients unterstützen moderne Authentifizierung und bedingte Zugriff. 

|Plattform|Client|Version/Hinweise|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [modernen-Authentifizierung aktivieren](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [erforderliche Updates](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook für iOS|[Neueste Version](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook für Android|[Neueste Version](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**Mac OS**|Outlook|2016|
|**Linux**|Nicht unterstützt||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Empfohlene Clientplattformen für den Schutz von Dokumenten
Die folgenden Clients werden empfohlen, wenn eine sichere Dokumente Richtlinie angewendet wurde.

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

<sup>*</sup>Hier erfahren Sie mehr über die Verwendung von bedingten Zugriff mit dem [OneDrive sync-Client](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Office 365-Clientunterstützung
Weitere Informationen zu Office 365-Client-Unterstützung finden Sie unter den folgenden Artikeln:
- [Support für Office 365 Client App - bedingten Zugriff](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Support für Office 365 Client App - Verwaltung von mobilen](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Support für Office 365 Client App - modernen Authentifizierung](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Schützen von Administratorkonten
Azure AD bietet eine einfache Möglichkeit für den Einstieg mit einer vorkonfigurierten bedingte Zugriffsrichtlinie Administratorzugriff schützen. In Azure AD, wechseln Sie zur **bedingten Zugriff** , und suchen Sie nach dieser Richtlinie – **Baseline-Richtlinie: erfordern mehrstufiger Authentifizierung das für Administratoren**. Wählen Sie diese Richtlinie aus, und wählen Sie **Richtlinie sofort verwenden**. 

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
- Verwenden Sie Office 365-Administratorkonten ausschließlich für die Verwaltung. Administratoren sollten einen separaten Benutzer berücksichtigt werden regelmäßig ohne Administratorrechte verwenden und nur verwenden, deren Verwaltungskonto bei Bedarf für die Durchführung eine Aufgabe aus, deren Funktion zugeordnet haben. [Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) -Administratorrollen sind wesentlich mehr Rechte als Office 365-Dienste.
- Befolgen Sie bewährte Methoden zum Sichern von privilegierter Konten in Azure AD, wie in diesem [Artikel](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)beschrieben.

## <a name="next-steps"></a>Nächste Schritte

[Konfigurieren der allgemeinen Identität und Gerät Zugriffsrichtlinien](identity-access-policies.md)

