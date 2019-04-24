---
title: VoraussetZungen für die Implementierung von Identitäts-und Gerätezugriffs Richtlinien-Microsoft 365 Enterprise | Microsoft-Dokumente
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
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 2bb13d2af70b90f8c98a4bb902156f840e7f57f1
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289006"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>VoraussetZungen für die Implementierung von Identitäts-und Gerätezugriffs Richtlinien

In diesem Artikel werden die Voraussetzungen beschrieben, die implementiert werden müssen, bevor Sie die empfohlenen Identitäts-und Gerätezugriffs Richtlinien bereitstellen können. In diesem Artikel werden auch die standardmäßigen Platt Form Clientkonfigurationen erläutert, die es Ihnen empfehlen, Ihren Benutzern die beste SSO-Benutzererfahrung sowie die technischen Voraussetzungen für bedingten Zugriff bereitzustellen.


## <a name="prerequisites"></a>Voraussetzungen

Vor dem Implementieren der empfohlenen Identitäts-und Gerätezugriffs Richtlinien gibt es mehrere Voraussetzungen, die Ihre Organisation erfüllen muss. In der folgenden Tabelle sind die Voraussetzungen für Ihre Umgebung aufgeführt. 


| Konfiguration | Nur für die Cloud | Active Directory mit Kennworthash Synchronisierung |  Pass-Through-Authentifizierung |  Verbund mit AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Konfigurieren der Kenn Wort Hash Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Dies muss aktiviert sein, um ausstehende Anmeldeinformationen zu finden und Sie für risikobasierten bedingten Zugriff zu bearbeiten. **Hinweis:** Dies ist unabhängig davon erforderlich, ob Ihre Organisation die verwaltete Authentifizierung wie die Passthrough-Authentifizierung (PTA) oder die Verbundauthentifizierung verwendet. |    | Ja | Ja | Ja |
| [Aktivieren der nahtlosen einmaligen Anmeldung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) , um Benutzer automatisch zu signieren, wenn Sie sich auf Ihren Unternehmensgeräten befinden, die mit Ihrem Unternehmensnetzwerk verbunden sind. |  | Ja | Ja |  |
| [Konfigurieren Sie benannte Netzwerke](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identity Protection erfasst und analysiert alle verfügbaren Sitzungsdaten, um eine Risikobewertung zu generieren. Es wird empfohlen, die öffentlichen IP-Bereiche Ihrer Organisation in der Konfiguration von Azure AD mit dem Namen "Netzwerke" für Ihr Netzwerk anzugeben. Der Datenverkehr aus diesen Bereichen erhält eine geringere Risikobewertung, und der Datenverkehr von außerhalb der Unternehmensumgebung erhält einen höheren Risikofaktor. | Ja  | Ja | Ja | Ja |
|[Registrieren Sie alle Benutzer für Self-Service Password Reset (SSPR) und Multi-Factor Authentication (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Es wird empfohlen, Benutzer für Azure MFA vorzeitig zu registrieren. Azure AD Identity Protection verwendet Azure MFA, um zusätzliche Sicherheitsüberprüfung durchzuführen. Darüber hinaus empfehlen wir Benutzern, die [Microsoft Authenticator-App](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) und die Microsoft-Unternehmens Portal-App auf Ihren Geräten zu installieren. Diese können im App Store für jede Plattform installiert werden. | Ja | Ja | Ja | Ja |
| [Aktivieren Sie die automatische Geräteregistrierung für mit der Domäne verbundene Windows-Computer](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). Bedingter Zugriff stellt sicher, dass Geräte, die mit apps verbunden sind, Domänen verbunden oder kompatibel sind. Um dies auf Windows-Computern zu unterstützen, muss das Gerät bei Azure AD registriert werden.  In diesem Artikel wird beschrieben, wie Sie die automatische Geräteregistrierung konfigurieren. |   | Ja |  Ja |  Ja |
| **Vorbereiten Ihres Supportteams**: Sie sollten vorausplanen, wie Sie mit Benutzern umgehen, die keine MFA durchführen können. Sie können sie z.B. Dies könnte Sie zu einer Richtlinien Ausschlussgruppe hinzufügen oder neue MFA-Informationen für Sie registrieren. Bevor Sie eine dieser sicherheitsrelevanten Änderungen vornehmen, müssen Sie sicherstellen, dass der tatsächliche Benutzer die Anforderung stellt. Es kann hilfreich sein, den Vorgesetzten des Benutzers bei der Genehmigung mit einzubeziehen. | Ja | Ja | Ja | Ja |  
| [Konfigurieren des Kenn Wort Rückschreibens in der lokalen AD-Anzeige](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Das Kenn Wort Rückschreiben ermöglicht es Azure AD, zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn eine risikoreiche Konto Gefährdung erkannt wird. Sie können dieses Feature mit Azure AD Connect auf zweierlei Weise aktivieren: entweder im Bildschirm optionale Features des Azure AD Connect-Setup-Assistenten das **Kenn Wort** Rückschreiben aktivieren oder es über Windows PowerShell aktivieren. |   | Ja | Ja | Ja |
| [Aktivieren Sie Azure Active Directory-Identitätsschutz](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable). Mit Azure AD Identity Protection können Sie potenzielle Sicherheitsrisiken, die sich auf die Identitäten Ihrer Organisation auswirken, ermitteln und eine automatisierte Behebungs Richtlinie auf niedriges, mittleres und hohes Anmelde-und Benutzer Risiko konfigurieren.  | Ja | Ja | Ja | Ja |
| **Aktivieren Sie die moderne Authentifizierung** für [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) und für [Skype for Business Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Die moderne Authentifizierung ist eine Voraussetzung für die Verwendung der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA). Die moderne Authentifizierung ist standardmäßig für Office 2016-Clients, SharePoint Online und OneDrive for Business aktiviert. | Ja | Ja | Ja | Ja |
||||||



## <a name="recommended-client-configurations"></a>Empfohlene Clientkonfigurationen
In diesem Abschnitt werden die standardmäßigen Platt Form Clientkonfigurationen beschrieben, die es Ihnen empfehlen, Ihren Benutzern die beste SSO-Benutzererfahrung sowie die technischen Voraussetzungen für bedingten Zugriff bereitzustellen.

### <a name="windows-devices"></a>Windows-Geräte
Wir empfehlen Windows 10 (Version 1703 oder höher), da Azure für die reibungsloseste SSO-Funktionalität sowohl für lokale als auch für Azure AD vorgesehen ist. Arbeiten oder in der Schule ausgestellte Geräte sollten so konfiguriert werden, dass Sie Azure AD direkt beitreten, oder wenn die Organisation lokalen AD-Domänenbeitritt verwendet, sollten diese Geräte so konfiguriert werden, [dass Sie automatisch und lautlos bei Azure AD registriert](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)werden.

Für BYOD-Windows-Geräte können Benutzer das **Add work-oder School-Konto**verwenden. Beachten Sie, dass Chrome-Browser-Benutzer unter Windows 10 [eine Erweiterung installieren](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) müssen, um die gleiche reibungslose Anmeldung wie Edge/IE-Benutzer zu erzielen. Wenn Ihre Organisation über eine Domäne mit Windows 7-Geräten verfügt, können Sie auch Microsoft Workplace Join für nicht-Windows 10-Computer [herunterladen, um](https://www.microsoft.com/download/details.aspx?id=53554) die Geräte mit Azure AD zu registrieren.

### <a name="ios-devices"></a>iOS-Geräte
Wir empfehlen die Installation der [Microsoft Authenticator-App](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) auf Benutzergeräten vor der Bereitstellung von MFA-Richtlinien oder Richtlinien für bedingten Zugriff. Die APP sollte mindestens installiert werden, wenn Benutzer aufgefordert werden, Ihr Gerät mit Azure AD zu registrieren, indem Sie ein Arbeits-oder Schulkonto hinzufügen oder wenn Sie die Intune-Unternehmensportal-App installieren, um Ihr Gerät in die Verwaltung einzuschreiben. Dies hängt von der konfigurierten bedingten Zugriffsrichtlinie ab.

### <a name="android-devices"></a>Android-Geräte
Es wird empfohlen, dass Benutzer die [Intune-Unternehmensportal-App](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) und die [Microsoft Authenticator-App](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) installieren, bevor bedingte Zugriffsrichtlinien bereitgestellt werden, oder im Bedarfsfall während bestimmter Authentifizierungsversuche. Nach der Installation der App können Benutzer aufgefordert werden, sich mit Azure AD zu registrieren oder ihr Gerät bei Intune zu registrieren. Dies hängt von der konfigurierten bedingten Zugriffsrichtlinie ab.

Außerdem wird empfohlen, dass firmeneigene Geräte (COD) auf OEMs und Versionen standardisiert sind, die Android for Work oder Samsung Knox unterstützen, um e-Mail-Konten zu ermöglichen, die von der InTune-MDM-Richtlinie verwaltet und geschützt werden.


### <a name="recommended-email-clients"></a>Empfohlene E-Mail-Clients
Die folgenden e-Mail-Clients unterstützen die moderne Authentifizierung und den bedingten Zugriff. 

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
|Windows 7|Unterstützt|Unterstützt|Nicht zutreffend|N/V|Vorschau<sup>*</sup>|
|Windows 8.1|Unterstützt|Unterstützt|Nicht zutreffend|N/V|Vorschau<sup>*</sup>|
|Windows 10|Unterstützt|Unterstützt|Nicht zutreffend|N/V|Vorschau<sup>*</sup>|
|Windows Phone 10|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|
|Android|Unterstützt|Unterstützt|Unterstützt|Unterstützt|Nicht zutreffend|
|iOS|Unterstützt|Unterstützt|Unterstützt|Unterstützt|Nicht zutreffend|
|macOS|Öffentliche Vorschau|Öffentliche Vorschau|Nicht zutreffend|Nicht zutreffend|Nicht unterstützt|
|Linux|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|

<sup>*</sup>Weitere Informationen zur Verwendung des bedingten Zugriffs mit dem [OneDrive-synchronisierungsclient](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Office 365-Clientunterstützung
Weitere Informationen zur Clientunterstützung für Office 365 finden Sie in den folgenden Artikeln:
- [Office 365-Client-App-Unterstützung-bedingter Zugriff](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365-Client-App-Unterstützung – Verwaltung mobiler Anwendungen](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365-Client-App-Unterstützung – moderne Authentifizierung](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Schützen von Administratorkonten
Azure AD bietet Ihnen eine einfache Möglichkeit, den Administratorzugriff mit einer vorkonfigurierten Richtlinie für den bedingten Zugriff zu schützen. Wechseln Sie in Azure AD zu **bedingter Zugriff** , und suchen Sie nach dieser Richtlinie – **Basisrichtlinie: MFA für Administratoren erforderlich**. Wählen Sie diese Richtlinie aus, und wählen Sie dann **Richtlinie sofort verwenden**aus. 

Diese Richtlinie erfordert MFA für die folgenden Rollen:
- Globale Administratoren
- SharePoint-Administratoren
- Exchange-Administratoren
- Administratoren für bedingten Zugriff
- Sicherheitsadministratoren

Weitere Informationen finden Sie unter [grundlegende Sicherheitsrichtlinien für Azure AD-Administratorkonten](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/).

Zu den weiteren Empfehlungen gehört Folgendes:
- Verwenden Sie Azure AD Privileged Identity Management zum Reduzieren der Anzahl der persistenten Administratorkonten. Weitere Informationen finden Sie unter [Start using PIM](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Verwenden Sie die privilegierte Zugriffsverwaltung in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview) , um Ihre Organisation vor Verstößen zu schützen, die vorhandene privilegierte Administratorkonten mit ständigem Zugriff auf vertrauliche Daten oder Zugriff auf wichtige Konfigurationseinstellungen verwenden können. 
- Verwenden Sie Administratorkonten nur für die Verwaltung. Administratoren sollten über ein separates Benutzerkonto für die reguläre nicht administrative Verwendung verfügen und Ihr Administratorkonto nur verwenden, wenn dies erforderlich ist, um eine Aufgabe zu erledigen, die ihrer Auftragsfunktion zugeordnet ist. [Office 365-Administrator](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) Rollen haben wesentlich mehr Berechtigungen als Office 365-Dienste.
- BeFolgen Sie bewährte Methoden zum Sichern von privilegierten Konten in Azure AD, wie in diesem [Artikel](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)beschrieben.

## <a name="next-steps"></a>Nächste Schritte

[Konfigurieren der allgemeinen Identitäts-und Gerätezugriffs Richtlinien](identity-access-policies.md)

