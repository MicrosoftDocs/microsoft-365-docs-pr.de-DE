---
title: Erforderliche Arbeit für die Implementierung von Identitäts-und Gerätezugriffs Richtlinien-Microsoft 365 Enterprise | Microsoft-Dokumente
description: Beschreibt die Richtlinien für Empfehlungen von Microsoft zur Anwendung von Identitäts- und Gerätezugriffsrichtlinien und -konfigurationen
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 99a124ff57816481cde92dd79c3058a2e7b72d31
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43625206"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Erforderliche Arbeit für die Implementierung von Identitäts-und Gerätezugriffs Richtlinien

In diesem Artikel werden die Voraussetzungen beschrieben, die implementiert werden müssen, bevor Sie die empfohlenen Identitäts-und Gerätezugriffs Richtlinien bereitstellen können. In diesem Artikel werden auch die Standardkonfigurationen für Platt Form Clients erläutert, die für die Bereitstellung der besten SSO-Benutzeroberfläche und die technischen Voraussetzungen für bedingten Zugriff empfohlen werden.


## <a name="prerequisites"></a>Voraussetzungen

Vor dem Implementieren der empfohlenen Richtlinien für Identitäts-und Geräte Zugriff gibt es mehrere Voraussetzungen, die Ihre Organisation erfüllen muss. In der folgenden Tabelle sind die Voraussetzungen aufgeführt, die für Ihre Umgebung gelten. 


| Konfiguration | Nur für die Cloud | Active Directory mit Kennworthash Synchronisierung |  Pass-Through-Authentifizierung |  Partnerverbund mit AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Konfigurieren der Kenn Wort Hash Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Dies muss aktiviert sein, um durchgesickerte Anmeldeinformationen zu erkennen und Sie für den risikobasierten bedingten Zugriff zu tätigen. **Hinweis:** Dies ist erforderlich, unabhängig davon, ob Ihre Organisation die verwaltete Authentifizierung verwendet, wie Pass-Through-Authentifizierung (PTA) oder Verbundauthentifizierung. |    | Ja | Ja | Ja |
| [Aktivieren der nahtlosen einmaligen Anmeldung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) zum automatischen Signieren von Benutzern, wenn Sie sich auf Ihren Unternehmensgeräten befinden, die mit Ihrem Unternehmensnetzwerk verbunden sind. |  | Ja | Ja |  |
| [Konfigurieren Sie benannte Netzwerke](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identitätsschutz erfasst und analysiert alle verfügbaren Sitzungsdaten, um ein Risikoergebnis zu generieren. Es wird empfohlen, die öffentlichen IP-Bereiche Ihrer Organisation für Ihr Netzwerk in der Konfiguration Azure AD benannte Netzwerke anzugeben. Bei Datenverkehr aus diesen Bereichen wird ein verringertes Risikoergebnis erzielt, und der Datenverkehr außerhalb der Unternehmensumgebung erhält ein höheres Risikoergebnis. | Ja  | Ja | Ja | Ja |
|[Registrieren Sie alle Benutzer für Self-Service Password Reset (SSPR) und mehrstufige Authentifizierung (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Es wird empfohlen, die Benutzer vor der Zeit für Azure MFA zu registrieren. Azure AD Identitätsschutz nutzt Azure MFA, um zusätzliche Sicherheitsüberprüfung durchzuführen. Für eine optimale Anmelde Erfahrung empfehlen wir außerdem, dass Benutzer die [Microsoft Authenticator-App](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) und die Microsoft-Unternehmens Portal-App auf Ihren Geräten installieren. Diese können aus dem App Store für jede Plattform installiert werden. | Ja | Ja | Ja | Ja |
| [Aktivieren der automatischen Geräteregistrierung für mit der Domäne verbundene Windows-Computer](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). Bedingter Zugriff stellt sicher, dass Geräte, die mit apps verbunden sind, der Domäne beigetreten sind oder kompatibel sind. Um dies auf Windows-Computern zu unterstützen, muss das Gerät mit Azure AD registriert sein.  In diesem Artikel wird beschrieben, wie Sie die automatische Geräteregistrierung konfigurieren. |   | Ja |  Ja |  Ja |
| **Vorbereiten Ihres Supportteams**: Sie sollten vorausplanen, wie Sie mit Benutzern umgehen, die keine MFA durchführen können. Sie können sie z.B. Dies könnte das Hinzufügen zu einer Richtlinien Ausschlussgruppe oder das Registrieren neuer MFA-Informationen für Sie sein. Bevor Sie eine dieser sicherheitsrelevanten Änderungen vornehmen, müssen Sie sicherstellen, dass der tatsächliche Benutzer die Anforderung macht. Es kann hilfreich sein, den Vorgesetzten des Benutzers bei der Genehmigung mit einzubeziehen. | Ja | Ja | Ja | Ja |  
| [Konfigurieren des Kenn Wort Rückschreibens für lokale Ad](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Durch das Kenn Wort Rückschreiben können Azure AD festlegen, dass Benutzer ihre lokalen Kennwörter ändern müssen, wenn eine risikoreiche Konto Gefährdung erkannt wird. Sie können dieses Feature mit Azure AD Connect auf zwei Arten aktivieren: entweder aktivieren Sie das Rückschreiben von **Kennwörtern** im optionalen Features-Bildschirm des Setup-Assistenten für Azure AD Connect, oder aktivieren Sie es über Windows PowerShell. |   | Ja | Ja | Ja |
| [Aktivieren Sie Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/enable). Mit Azure AD Identity Protection können Sie potenzielle Sicherheitsrisiken erkennen, die sich auf die Identitäten Ihrer Organisation auswirken, und eine automatisierte Behebungs Richtlinie auf niedrigem, mittlerem und hohem Anmelde Risiko und Benutzer Risiko konfigurieren.  | Ja | Ja | Ja | Ja |
| **Aktivieren Sie die moderne Authentifizierung** für [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) und [Skype for Business Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Die moderne Authentifizierung ist eine Voraussetzung für die Verwendung der mehrstufigen Authentifizierung (MFA). Die moderne Authentifizierung ist für Office 2016 Clients, SharePoint Online und OneDrive für Unternehmen standardmäßig aktiviert. | Ja | Ja | Ja | Ja |
||||||



## <a name="recommended-client-configurations"></a>Empfohlene Clientkonfigurationen
In diesem Abschnitt werden die Standardkonfigurationen für Platt Form Clients beschrieben, die für die Bereitstellung der besten SSO-Benutzeroberfläche und die technischen Voraussetzungen für bedingten Zugriff empfohlen werden.

### <a name="windows-devices"></a>Windows-Geräte
Wir empfehlen Windows 10 (Version 1703 oder höher), da Azure so konzipiert ist, dass es sowohl lokal als auch Azure AD eine möglichst reibungslose SSO-Funktionalität bietet. Arbeits-oder Schul ausgestellte Geräte sollten so konfiguriert werden, dass Sie direkt an Azure AD teilnehmen oder wenn die Organisation lokale Ad-Domänenbeitritt verwendet, diese Geräte sollten so konfiguriert werden, [dass Sie automatisch mit Azure AD registriert](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)werden.

Für BYOD-Windows-Geräte können Benutzer **Add work oder School Account**verwenden. Beachten Sie, dass Benutzer von Chrome-Browser unter Windows 10 [eine Erweiterung installieren](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) müssen, um die gleiche glatte Anmelde Erfahrung wie Edge/IE-Benutzer zu erhalten. Wenn Ihre Organisation Windows 7 Geräten mit Domänenbeitritt verbunden ist, können Sie auch Microsoft Workplace Join für nicht-Windows 10-Computer installieren, [um das Paket herunterzuladen, um](https://www.microsoft.com/download/details.aspx?id=53554) die Geräte mit Azure AD zu registrieren.

### <a name="ios-devices"></a>iOS-Geräte
Wir empfehlen die Installation der [Microsoft Authenticator-App](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) auf Benutzergeräten vor der Bereitstellung von MFA-Richtlinien oder Richtlinien für bedingten Zugriff. Die APP sollte mindestens installiert werden, wenn Benutzer aufgefordert werden, Ihr Gerät bei Azure AD zu registrieren, indem Sie ein Geschäfts-oder Schulkonto hinzufügen oder wenn Sie die Intune-Unternehmensportal-App installieren, um Ihr Gerät in die Verwaltung einzuschreiben. Dies hängt von der konfigurierten bedingten Zugriffsrichtlinie ab.

### <a name="android-devices"></a>Android-Geräte
Es wird empfohlen, dass Benutzer die [Intune-Unternehmensportal-App](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) und die [Microsoft Authenticator-App](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) installieren, bevor bedingte Zugriffsrichtlinien bereitgestellt werden, oder im Bedarfsfall während bestimmter Authentifizierungsversuche. Nach der Installation der App können Benutzer aufgefordert werden, sich mit Azure AD zu registrieren oder ihr Gerät bei Intune zu registrieren. Dies hängt von der konfigurierten bedingten Zugriffsrichtlinie ab.

Wir empfehlen auch, dass unternehmenseigene Geräte (COD) auf OEMs und Versionen standardisiert sind, die Android for Work oder Samsung Knox unterstützen, damit e-Mail-Konten verwaltet und durch InTune-MDM-Richtlinien geschützt werden können.


### <a name="recommended-email-clients"></a>Empfohlene E-Mail-Clients
Die folgenden e-Mail-Clients unterstützen moderne Authentifizierung und bedingten Zugriff. 

|Plattform|Client|Version/Hinweise|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Aktivieren der modernen Authentifizierung](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [erforderliche Updates](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook für iOS|[Neueste Version](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook für Android|[Neueste Version](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|Nicht unterstützt||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Empfohlene Clientplattformen für den Schutz von Dokumenten
Die folgenden Clients werden empfohlen, wenn eine Richtlinie für sichere Dokumente angewendet wurde.

|Plattform|Word/Excel/PowerPoint|OneNote|OneDrive-App|SharePoint-App|OneDrive-Synchronisierungsclient|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Unterstützt|Unterstützt|Nicht zutreffend|Nicht zutreffend|Vorschau<sup>*</sup>|
|Windows 8.1|Unterstützt|Unterstützt|Nicht zutreffend|Nicht zutreffend|Vorschau<sup>*</sup>|
|Windows 10|Unterstützt|Unterstützt|Nicht zutreffend|Nicht zutreffend|Vorschau<sup>*</sup>|
|Windows Phone 10|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|
|Android|Unterstützt|Unterstützt|Unterstützt|Unterstützt|N/V|
|iOS|Unterstützt|Unterstützt|Unterstützt|Unterstützt|N/V|
|macOS|Öffentliche Vorschau|Öffentliche Vorschau|Nicht zutreffend|Nicht zutreffend|Nicht unterstützt|
|Linux|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|

<sup>*</sup>Erfahren Sie mehr über die Verwendung von bedingtem Zugriff mit dem [OneDrive-synchronisierungsclient](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="microsoft-365-client-support"></a>Microsoft 365-Clientunterstützung
Weitere Informationen zur Clientunterstützung finden Sie in den folgenden Artikeln:
- [Microsoft 365-Client-App-Unterstützung – bedingter Zugriff](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access)
- [Microsoft 365-Client-App-Support-Mobile Anwendungsverwaltung](https://docs.microsoft.com/office365/enterprise/office-365-client-support-mobile-application-management)
- [Microsoft 365-Client-App-Support-moderne Authentifizierung](https://docs.microsoft.com/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Schützen von Administratorkonten
Azure Ad bietet Ihnen eine einfache Möglichkeit, den Administratorzugriff mit einer vorkonfigurierten Richtlinie für bedingten Zugriff zu schützen. Wechseln Sie in Azure AD zu **bedingter Zugriff** , und suchen Sie nach dieser Richtlinie – **Baseline-Richtlinie: MFA für Administratoren erfordern (Vorschau)**. Wählen Sie diese Richtlinie aus, und wählen Sie dann **Richtlinie sofort verwenden**aus. 

Diese Richtlinie erfordert MFA für die folgenden Rollen:
- Globale Administratoren
- SharePoint-Administratoren
- Exchange-Administratoren
- Administrator für bedingten Zugriff
- Sicherheitsadministratoren

Weitere Informationen finden Sie unter [Baseline Security Policy for Azure AD Administrator Accounts](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/).

Weitere Empfehlungen umfassen Folgendes:
- Verwenden Sie Azure AD Privileged Identity Management zum Reduzieren der Anzahl der persistenten Administratorkonten. Weitere Informationen finden Sie unter [Beginn der Verwendung von PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Verwenden Sie die privilegierte Zugriffsverwaltung in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) , um Ihre Organisation vor Verstößen zu schützen, die vorhandene privilegierte Administratorkonten mit dem ständigen Zugriff auf vertrauliche Daten oder den Zugriff auf wichtige Konfigurationseinstellungen verwenden können. 
- Verwenden Sie Administratorkonten nur für die Verwaltung. Administratoren sollten über ein separates Benutzerkonto für die reguläre nicht-administrative Verwendung verfügen und nur dann Ihr Administratorkonto verwenden, wenn es erforderlich ist, um eine Aufgabe abzuschließen, die ihrer Auftragsfunktion zugeordnet ist. [Microsoft 365-Administrator](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) Rollen haben wesentlich mehr Berechtigungen als Microsoft 365-Dienste.
- Führen Sie bewährte Methoden zum Sichern von privilegierten Konten in Azure AD wie in diesem [Artikel](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)beschrieben aus.

## <a name="next-steps"></a>Nächste Schritte

[Konfigurieren der allgemeinen Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md)

