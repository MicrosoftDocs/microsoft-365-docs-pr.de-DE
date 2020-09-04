---
title: Erforderliche Arbeit für die Implementierung von Identitäts-und Gerätezugriffs Richtlinien – Microsoft 365 für Unternehmen | Microsoft-Dokumente
description: Beschreibt die Voraussetzungen vor der Implementierung von Richtlinien und Konfigurationen für den Identitäts-und Geräte Zugriff.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/01/2020
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 40910c00a91a1e98d01fe2e25a4f9aed828a024a
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357974"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Erforderliche Arbeit für die Implementierung von Identitäts-und Gerätezugriffs Richtlinien

In diesem Artikel werden die Voraussetzungen beschrieben, die implementiert werden müssen, bevor Sie die empfohlenen Identitäts-und Gerätezugriffs Richtlinien bereitstellen können. In diesem Artikel werden auch die empfohlenen Standardkonfigurationen für Platt Form Clients behandelt, um den Benutzern die besten einmaligen Anmeldeinformationen (Single Sign-on, SSO) zu bieten, sowie die technischen Voraussetzungen für bedingten Zugriff.

## <a name="prerequisites"></a>Voraussetzungen

Vor dem Implementieren der empfohlenen Richtlinien für Identitäts-und Geräte Zugriff gibt es verschiedene Voraussetzungen, die Ihre Organisation für diese Identitäts-und Authentifizierungsmodelle für Microsoft 365 und Office 365 erfüllen muss:

- Rein cloudbasiert
- Hybrid mit Password Hash Sync (PHS)-Authentifizierung
- Hybrid mit Pass-Through-Authentifizierung (PTA)
- Verbund

In der folgenden Tabelle sind die erforderlichen Features und deren Konfiguration aufgeführt, die für alle Identitäts Modelle gelten, sofern nicht anders angegeben. 

| Konfiguration | Ausnahmen |
| :------------- | :-----------: |
|  [Konfigurieren der Kenn Wort Hash Synchronisierung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).  Dies muss aktiviert sein, um durchgesickerte Anmeldeinformationen zu erkennen und Sie für den risikobasierten bedingten Zugriff zu tätigen. **Hinweis:** Dies ist erforderlich, unabhängig davon, ob in Ihrer Organisation eine hybride Verbundauthentifizierung verwendet wird. |  Rein cloudbasiert |
| [Aktivieren Sie das nahtlose einmalige Anmelden](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) , um Benutzer automatisch zu signieren, wenn Sie sich auf Ihren Organisations Geräten befinden, die mit Ihrem Organisationsnetzwerk verbunden sind. | Nur Cloud und Verbund  |
| [Konfigurieren Sie benannte Netzwerke](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identitätsschutz erfasst und analysiert alle verfügbaren Sitzungsdaten, um ein Risikoergebnis zu generieren. Es wird empfohlen, die öffentlichen IP-Bereiche Ihrer Organisation für Ihr Netzwerk in der Konfiguration Azure AD benannte Netzwerke anzugeben. Für den Datenverkehr, der aus diesen Bereichen stammt, wird ein verringertes Risikoergebnis erzielt, und Datenverkehr von außerhalb der Organisationsumgebung erhält ein höheres Risikoergebnis. | |
|[Registrieren Sie alle Benutzer für Self-Service Password Reset (SSPR) und mehrstufige Authentifizierung (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Es wird empfohlen, dass Sie vor der Zeit Benutzer für die Azure Multi-Factor Authentication registrieren. Azure AD Identitätsschutz nutzt die mehrstufige Azure-Authentifizierung, um eine zusätzliche Sicherheitsüberprüfung durchzuführen. Für eine optimale Anmelde Erfahrung empfehlen wir außerdem, dass Benutzer die [Microsoft Authenticator-App](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) und die Microsoft-Unternehmens Portal-App auf Ihren Geräten installieren. Diese können aus dem App Store für jede Plattform installiert werden. | |
| [Aktivieren der automatischen Geräteregistrierung für mit der Domäne verbundene Windows-Computer](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). Bedingter Zugriff stellt sicher, dass Geräte, die mit apps verbunden sind, der Domäne beigetreten sind oder kompatibel sind. Um dies auf Windows-Computern zu unterstützen, muss das Gerät mit Azure AD registriert sein.  In diesem Artikel wird beschrieben, wie Sie die automatische Geräteregistrierung konfigurieren. | Rein cloudbasiert |
| **Vorbereiten Ihres Supportteams**: Sie sollten vorausplanen, wie Sie mit Benutzern umgehen, die keine MFA durchführen können. Sie können sie z.B. Dies könnte das Hinzufügen zu einer Richtlinien Ausschlussgruppe oder das Registrieren neuer MFA-Informationen für Sie sein. Bevor Sie eine dieser sicherheitsrelevanten Änderungen vornehmen, müssen Sie sicherstellen, dass der tatsächliche Benutzer die Anforderung macht. Es kann hilfreich sein, den Vorgesetzten des Benutzers bei der Genehmigung mit einzubeziehen. | |  
| [Konfigurieren des Kenn Wort Rückschreibens für lokale Ad](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Durch das Kenn Wort Rückschreiben können Azure AD festlegen, dass Benutzer ihre lokalen Kennwörter ändern müssen, wenn eine risikoreiche Konto Gefährdung erkannt wird. Sie können dieses Feature mit Azure AD Connect auf zwei Arten aktivieren: entweder aktivieren Sie das Rückschreiben von **Kennwörtern** im optionalen Features-Bildschirm des Setup-Assistenten für Azure AD Connect, oder aktivieren Sie es über Windows PowerShell. | Rein cloudbasiert |
| [Konfigurieren Sie Azure AD Kennwortschutz](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad). Azure AD Kennwortschutz erkennt und blockiert bekannte schwache Kennwörter und deren Varianten und kann auch zusätzliche schwache Ausdrücke blockieren, die für Ihre Organisation spezifisch sind. Standardmäßige globale gesperrte Kenn Wortlisten werden automatisch auf alle Benutzer in einem Azure AD Mandanten angewendet. Sie können zusätzliche Einträge in einer benutzerdefinierten Liste gesperrter Kennwörter definieren. Wenn Benutzer ihre Kennwörter ändern oder zurücksetzen, werden diese gesperrten Kenn Wortlisten überprüft, um die Verwendung sicherer Kennwörter zu erzwingen. | |
| [Aktivieren Sie Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection). Mit Azure AD Identity Protection können Sie potenzielle Sicherheitsrisiken erkennen, die sich auf die Identitäten Ihrer Organisation auswirken, und eine automatisierte Behebungs Richtlinie auf niedrigem, mittlerem und hohem Anmelde Risiko und Benutzer Risiko konfigurieren.  | |
| **Aktivieren Sie die moderne Authentifizierung** für [Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) und [Skype for Business Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Die moderne Authentifizierung ist eine Voraussetzung für die Verwendung der mehrstufigen Authentifizierung (MFA). Die moderne Authentifizierung ist für Office 2016 Clients, SharePoint Online und OneDrive für Unternehmen standardmäßig aktiviert. |  |
|||

## <a name="recommended-client-configurations"></a>Empfohlene Clientkonfigurationen
In diesem Abschnitt werden die Standardkonfigurationen für Platt Form Clients beschrieben, die für die Bereitstellung der besten SSO-Benutzeroberfläche und die technischen Voraussetzungen für bedingten Zugriff empfohlen werden.

### <a name="windows-devices"></a>Windows-Geräte
Wir empfehlen Windows 10 (Version 2004 oder höher), da Azure so konzipiert ist, dass es sowohl lokal als auch Azure AD eine möglichst reibungslose SSO-Funktionalität bietet. Arbeits-oder Schul ausgestellte Geräte sollten so konfiguriert werden, dass Sie direkt an Azure AD teilnehmen oder wenn die Organisation lokale Ad-Domänenbeitritt verwendet, diese Geräte sollten so konfiguriert werden, [dass Sie automatisch mit Azure AD registriert](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)werden.

Für BYOD-Windows-Geräte können Benutzer **Add work oder School Account**verwenden. Beachten Sie, dass Benutzer des Google Chrome-Browsers auf Windows 10-Geräten [eine Erweiterung installieren](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) müssen, um die gleiche glatte Anmelde Erfahrung wie Microsoft Edge-Benutzer zu erhalten. Wenn Ihre Organisation Windows 8-oder 8,1-Geräte mit einer Domäne verbunden ist, können Sie auch Microsoft Workplace Join für nicht-Windows 10-Computer installieren. [Laden Sie das Paket herunter, um](https://www.microsoft.com/download/details.aspx?id=53554) die Geräte mit Azure AD zu registrieren.

### <a name="ios-devices"></a>iOS-Geräte
Es wird empfohlen, die [Microsoft Authenticator-App](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) auf Benutzergeräten zu installieren, bevor Sie den bedingten Zugriff oder MFA-Richtlinien bereitstellen. Die APP sollte mindestens installiert werden, wenn Benutzer aufgefordert werden, Ihr Gerät bei Azure AD zu registrieren, indem Sie ein Geschäfts-oder Schulkonto hinzufügen oder wenn Sie die Intune-Unternehmensportal-App installieren, um Ihr Gerät in die Verwaltung einzuschreiben. Dies hängt von der konfigurierten Richtlinie für den bedingten Zugriff ab.

### <a name="android-devices"></a>Android-Geräte
Es wird empfohlen, dass Benutzer die [InTune-Unternehmens Portal-App](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) und die [Microsoft Authenticator-App](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) installieren, bevor Richtlinien für den bedingten Zugriff bereitgestellt werden oder bei bestimmten Authentifizierungsversuchen erforderlich sind. Nach der Installation der App können Benutzer aufgefordert werden, sich mit Azure AD zu registrieren oder ihr Gerät bei Intune zu registrieren. Dies hängt von der konfigurierten Richtlinie für den bedingten Zugriff ab.

Wir empfehlen auch, dass die organisationseigenen Geräte auf OEMs und Versionen standardisiert sind, die Android for Work oder Samsung Knox unterstützen, damit e-Mail-Konten verwaltet und durch InTune-MDM-Richtlinien geschützt werden können.


### <a name="recommended-email-clients"></a>Empfohlene E-Mail-Clients
Die folgenden e-Mail-Clients unterstützen moderne Authentifizierung und bedingten Zugriff. 

|Plattform|Client|Version/Hinweise|
|:-------|:-----|:------------|
|**Windows**|Outlook|2019, 2016, 2013 <BR> [Aktivieren der modernen Authentifizierung](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication), [erforderliche Updates](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook für iOS|[Neueste Version](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook für Android|[Neueste Version](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**MacOS**|Outlook|2019 und 2016|
|**Linux**|Nicht unterstützt||
|||

### <a name="recommended-client-platforms-when-securing-documents"></a>Empfohlene Clientplattformen für den Schutz von Dokumenten

Die folgenden Clients werden empfohlen, wenn eine Richtlinie für sichere Dokumente angewendet wurde.

|Plattform|Word/Excel/PowerPoint|OneNote|OneDrive-App|SharePoint-App|[OneDrive-Synchronisierungsclient](https://docs.microsoft.com/onedrive/enable-conditional-access)|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 8.1|Unterstützt|Unterstützt|Nicht zutreffend|Nicht zutreffend|Unterstützt|
|Windows 10|Unterstützt|Unterstützt|Nicht zutreffend|Nicht zutreffend|Unterstützt|
|Android|Unterstützt|Unterstützt|Unterstützt|Unterstützt|N/V|
|iOS|Unterstützt|Unterstützt|Unterstützt|Unterstützt|N/V|
|MacOS|Unterstützt|Unterstützt|Nicht zutreffend|Nicht zutreffend|Nicht unterstützt|
|Linux|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|

### <a name="microsoft-365-client-support"></a>Microsoft 365-Clientunterstützung

Weitere Informationen zur Clientunterstützung in Microsoft 365 finden Sie in den folgenden Artikeln:

- [Microsoft 365-Client-App-Unterstützung – bedingter Zugriff](microsoft-365-client-support-conditional-access.md)
- [Microsoft 365-Client-App-Support-moderne Authentifizierung](microsoft-365-client-support-modern-authentication.md)

## <a name="protecting-administrator-accounts"></a>Schützen von Administratorkonten

Für Microsoft 365 E3 oder E5 oder mit separaten Azure AD Premium P1-oder P2-Lizenzen können Sie MFA für Administratorkonten mit einer manuell erstellten Richtlinie für den bedingten Zugriff benötigen. Weitere Informationen finden Sie unter [Conditional Access: MFA for Administrators require](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) .

Für Editionen von Microsoft 365 oder Office 365, die keinen bedingten Zugriff unterstützen, können Sie [Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) aktivieren, um MFA für alle Konten zu benötigen.

Hier sind einige zusätzliche Empfehlungen:

- Verwenden Sie [Azure AD privilegierten Identitätsverwaltung](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) , um die Anzahl der beständigen Administratorkonten zu reduzieren. 
- [Verwenden Sie die privilegierte Zugriffsverwaltung](../compliance/privileged-access-management-overview.md) , um Ihre Organisation vor Verstößen zu schützen, die vorhandene privilegierte Administratorkonten mit dem ständigen Zugriff auf vertrauliche Daten oder den Zugriff auf wichtige Konfigurationseinstellungen verwenden können. 
- Erstellen und verwenden Sie separate Konten, denen [Microsoft 365-Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) *nur für die Verwaltung*zugewiesen sind. Administratoren sollten über ein eigenes Benutzerkonto für eine reguläre, nicht administrative Nutzung verfügen und nur dann ein Administratorkonto verwenden, wenn es erforderlich ist, um eine Aufgabe abzuschließen, die mit ihrer Rolle oder ihrer Aufgaben Funktion verknüpft ist. 
- Führen Sie [bewährte Methoden](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) zum Sichern von privilegierten Konten in Azure AD aus.

## <a name="next-step"></a>Nächster Schritt

![Schritt 2: Konfigurieren der allgemeinen Identitäts-und Zugriffsrichtlinien für den bedingten Zugriff](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)

[Konfigurieren der allgemeinen Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md)
