---
title: Erforderliche Arbeit für die Implementierung von Identitäts- und Gerätezugriffsrichtlinien – Microsoft 365 for Enterprise | Microsoft Docs
description: In diesem Artikel werden die Voraussetzungen beschrieben, die Sie für die Verwendung von Identitäts- und Gerätezugriffsrichtlinien und -konfigurationen erfüllen müssen.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: e7fa58afcf61c82071416422a7a5ea6a7e8f1ec0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907204"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Erforderliche Arbeit für die Implementierung von Identitäts- und Gerätezugriffsrichtlinien

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- Azure

In diesem Artikel werden die Voraussetzungen beschrieben, die Administratoren erfüllen müssen, um empfohlene Identitäts- und Gerätezugriffsrichtlinien zu verwenden und bedingten Zugriff zu verwenden. Außerdem werden die empfohlenen Standardwerte für die Konfiguration von Clientplattformen für die beste Einmaliges Anmelden (Single Sign-On, SSO) erläutert.

## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie die empfohlenen Identitäts- und Gerätezugriffsrichtlinien verwenden, muss Ihre Organisation die voraussetzungen erfüllen. Die Anforderungen sind für die verschiedenen aufgeführten Identitäts- und Authentifizierungsmodelle unterschiedlich:

- Rein cloudbasiert
- Hybrid mit #A0 (Password Hash Sync)
- Hybrid mit Pass-Through-Authentifizierung (PTA)
- Verbund

In der folgenden Tabelle sind die erforderlichen Features und deren Konfiguration aufgeführt, die für alle Identitätsmodelle gelten, sofern nicht angegeben.

|Konfiguration|Ausnahmen|
|---|:---:|
|[Konfigurieren von PHS](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).  Dies muss aktiviert sein, um durchgesickerte Anmeldeinformationen zu erkennen und diese für risikobasierten bedingten Zugriff zu verwenden. **Hinweis:** Dies ist unabhängig davon erforderlich, ob Ihre Organisation die Verbundauthentifizierung verwendet.|Rein cloudbasiert|
|[Aktivieren Sie eine nahtlose einmalige](/azure/active-directory/connect/active-directory-aadconnect-sso) Anmeldung, um Benutzer automatisch zu anmelden, wenn sie sich auf ihren Organisationsgeräten befinden, die mit Ihrem Organisationsnetzwerk verbunden sind.|Cloud-only und Verbund|
|[Konfigurieren sie benannte Speicherorte](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations). Azure AD Identity Protection sammelt und analysiert alle verfügbaren Sitzungsdaten, um eine Risikobewertung zu generieren. Es wird empfohlen, die öffentlichen IP-Bereiche Ihrer Organisation für Ihr Netzwerk in der Azure AD named locations-Konfiguration anzugeben. Datenverkehr, der von diesen Bereichen kommt, wird mit einer geringeren Risikosentwertung und Datenverkehr von außerhalb der Organisationsumgebung mit einer höheren Risikopunktzahl angegeben.||
|[Registrieren Sie alle Benutzer für die Self-Service-Kennwortzurücksetzung (Self-Service Password Reset, SSPR) und die mehrstufige Authentifizierung (MFA).](/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) Es wird empfohlen, Benutzer für die mehrstufige Azure AD-Authentifizierung im Voraus zu registrieren. Azure AD Identity Protection verwendet die mehrstufige Azure AD-Authentifizierung, um zusätzliche Sicherheitsüberprüfungen durchzuführen. Darüber hinaus empfehlen wir Benutzern, die Microsoft [Authenticator-App](/azure/active-directory/user-help/microsoft-authenticator-app-how-to) und die Microsoft Company Portal-App auf ihren Geräten zu installieren, um eine optimale Anmeldeerfahrung zu bieten. Diese können im App Store für jede Plattform installiert werden.||
|[Aktivieren der automatischen Geräteregistrierung von Windows-Computern, die der Domäne beigetreten sind.](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup) Bedingter Zugriff sorgt dafür, dass Geräte, die eine Verbindung mit Apps herstellen, domänenverbindet oder kompatibel sind. Um dies auf Windows-Computern zu unterstützen, muss das Gerät bei Azure AD registriert sein.  In diesem Artikel wird erläutert, wie Sie die automatische Geräteregistrierung konfigurieren.|Rein cloudbasiert|
|**Vorbereiten Ihres Supportteams**: Sie sollten vorausplanen, wie Sie mit Benutzern umgehen, die keine MFA durchführen können. Sie können sie z.B. Dies kann das Hinzufügen zu einer Richtlinienausschlussgruppe oder das Registrieren neuer MFA-Informationen für sie sein. Bevor Sie eine dieser sicherheitssensitiven Änderungen vornehmen, müssen Sie sicherstellen, dass der tatsächliche Benutzer die Anforderung stellt. Es kann hilfreich sein, den Vorgesetzten des Benutzers bei der Genehmigung mit einzubeziehen.||
|[Konfigurieren des Kennwortrückschreibens in lokales AD](/azure/active-directory/active-directory-passwords-getting-started). Mit dem Kennwortrückschreiben kann Azure AD festlegen, dass Benutzer ihre lokalen Kennwörter ändern müssen, wenn ein Risiko für die Kontogefährdung erkannt wird. Sie können dieses Feature mithilfe von Azure AD Connect  auf zwei Arten aktivieren: Aktivieren Sie entweder das Kennwortrückschreiben im Bildschirm optionale Features des Azure AD Connect-Setup-Assistenten, oder aktivieren Sie es über Windows PowerShell.|Rein cloudbasiert|
|[Konfigurieren des Azure AD-Kennwortschutzes](/azure/active-directory/authentication/concept-password-ban-bad). Der Azure AD-Kennwortschutz erkennt und blockiert als schwach bekannte Kennwörter und deren Varianten und kann zusätzlich für Ihre Organisation spezifische schwache Ausdrücke blockieren. Listen standardmäßig global gesperrter Kennwörter werden automatisch auf alle Benutzer in einem Azure AD-Mandanten angewendet. Sie können zusätzliche Einträge in einer benutzerdefinierten Liste gesperrter Kennwörter angeben. Wenn Benutzer ihre Kennwörter ändern oder zurücksetzen, werden diese Listen gesperrter Kennwörter überprüft, um die Verwendung von sicheren Kennwörtern zu erzwingen.||
|[Aktivieren Sie Azure Active Directory Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection). Azure AD Identity Protection ermöglicht es Ihnen, potenzielle Sicherheitsrisiken zu erkennen, die sich auf die IdentitätEn Ihrer Organisation ausdingen, und eine automatisierte Korrekturrichtlinie auf ein niedriges, mittleres und hohes Anmelderisiko und ein hohes Benutzerrisiko zu konfigurieren.||
|**Aktivieren der modernen Authentifizierung** [für Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) und Skype for Business [Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Die moderne Authentifizierung ist eine Voraussetzung für die Verwendung von MFA. Die moderne Authentifizierung ist standardmäßig für Office 2016- und 2019-Clients, SharePoint und OneDrive for Business aktiviert.||
|

## <a name="recommended-client-configurations"></a>Empfohlene Clientkonfigurationen

In diesem Abschnitt werden die Standardkonfigurationen für Plattformclients beschrieben, die empfohlen werden, um Den Benutzern die beste SSO-Erfahrung sowie die technischen Voraussetzungen für bedingten Zugriff zu bieten.

### <a name="windows-devices"></a>Windows-Geräte

Wir empfehlen Windows 10 (Version 2004 oder höher), da Azure für eine möglichst reibungslose SSO-Erfahrung sowohl für lokale als auch für Azure AD konzipiert ist. Von Geschäfts- oder Schuleinrichtungen ausgestellte Geräte sollten für den direkten Beitritt zu Azure AD konfiguriert werden, oder wenn die Organisation den lokalen AD-Domänen beitreten verwendet, sollten diese Geräte für die automatische und automatische Registrierung bei [Azure AD konfiguriert werden.](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)

Für BYOD-Windows-Geräte können Benutzer Arbeits- oder **Schulkonto hinzufügen verwenden.** Beachten Sie, dass Benutzer des Google Chrome-Browsers [](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) auf Windows 10-Geräten eine Erweiterung installieren müssen, um die gleiche reibungslose Anmeldeerfahrung wie Microsoft Edge-Benutzer zu erhalten. Wenn Ihre Organisation über Domänen-Windows 8 oder 8.1-Geräte verfügt, können Sie Microsoft Workplace Join auch für Nicht-Windows 10-Computer installieren. [Laden Sie das Paket herunter, um die](https://www.microsoft.com/download/details.aspx?id=53554) Geräte bei Azure AD zu registrieren.

### <a name="ios-devices"></a>iOS-Geräte

Es wird empfohlen, die [Microsoft Authenticator-App auf](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) Benutzergeräten zu installieren, bevor Sie Richtlinien für bedingten Zugriff oder MFA bereitstellen. Die App sollte mindestens installiert werden, wenn Benutzer aufgefordert werden, ihr Gerät bei Azure AD zu registrieren, indem sie ein Firmen- oder Schulkonto hinzufügen oder die Intune-Unternehmensportal-App installieren, um ihr Gerät bei der Verwaltung zu registrieren. Dies hängt von der konfigurierten Richtlinie für bedingten Zugriff ab.

### <a name="android-devices"></a>Android-Geräte

Es wird empfohlen, dass Benutzer die [Intune Company Portal-App](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) und [die Microsoft Authenticator-App](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) installieren, bevor Richtlinien für bedingten Zugriff bereitgestellt werden oder wenn dies bei bestimmten Authentifizierungsversuchen erforderlich ist. Nach der Installation der App können Benutzer aufgefordert werden, sich mit Azure AD zu registrieren oder ihr Gerät bei Intune zu registrieren. Dies hängt von der konfigurierten Richtlinie für bedingten Zugriff ab.

Außerdem wird empfohlen, dass Geräte im Besitz der Organisation auf OEMs und Versionen, die Android for Work oder Samsung Knox unterstützen, standardisiert sind, um E-Mail-Konten zu ermöglichen, die durch intune-MDM-Richtlinie verwaltet und geschützt werden.

### <a name="recommended-email-clients"></a>Empfohlene E-Mail-Clients

Die folgenden E-Mail-Clients unterstützen moderne Authentifizierung und bedingten Zugriff.

|Plattform|Client|Version/Hinweise|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [Aktivieren der modernen Authentifizierung](../../admin/security-and-compliance/enable-modern-authentication.md) <p> [Erforderliche Updates](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook für iOS|[Neueste Version](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook für Android|[Neueste Version](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 und 2016|
|**Linux**|Nicht unterstützt||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>Empfohlene Clientplattformen für den Schutz von Dokumenten

Die folgenden Clients werden empfohlen, wenn eine Richtlinie für sichere Dokumente angewendet wurde.

|Plattform|Word/Excel/PowerPoint|OneNote|OneDrive-App|SharePoint-App|[OneDrive-Synchronisierungsclient](/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|Unterstützt|Unterstützt|Nicht zutreffend|Nicht zutreffend|Unterstützt|
|Windows 10|Unterstützt|Unterstützt|Nicht zutreffend|Nicht zutreffend|Unterstützt|
|Android|Unterstützt|Unterstützt|Unterstützt|Unterstützt|N/V|
|iOS|Unterstützt|Unterstützt|Unterstützt|Unterstützt|N/V|
|macOS|Unterstützt|Unterstützt|Nicht zutreffend|Nicht zutreffend|Nicht unterstützt|
|Linux|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|Nicht unterstützt|
|

### <a name="microsoft-365-client-support"></a>Microsoft 365-Clientunterstützung

Weitere Informationen zur Clientunterstützung in Microsoft 365 finden Sie in den folgenden Artikeln:

- [Microsoft 365 Client App Support – Bedingter Zugriff](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Microsoft 365 Client App Support – Mehrstufige Authentifizierung](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>Schützen von Administratorkonten

Für Microsoft 365 E3 oder E5 oder mit separaten Azure AD Premium P1- oder P2-Lizenzen können Sie MFA für Administratorkonten mit einer manuell erstellten Richtlinie für bedingten Zugriff benötigen. Weitere Informationen finden Sie unter [Conditional Access: Require MFA for administrators.](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)

Für Editionen von Microsoft 365 oder Office 365, [](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) die bedingten Zugriff nicht unterstützen, können Sie Sicherheitseinstellungen aktivieren, um MFA für alle Konten zu erfordern.

Hier sind einige weitere Empfehlungen:

- Verwenden [Sie Azure AD Privileged Identity Management,](/azure/active-directory/privileged-identity-management/pim-getting-started) um die Anzahl der beständigen Administratorkonten zu reduzieren.
- [Verwenden Sie privilegierte Zugriffsverwaltung,](../../compliance/privileged-access-management-overview.md) um Ihre Organisation vor Verstößen zu schützen, die vorhandene privilegierte Administratorkonten mit ständigem Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen verwenden können.
- Erstellen und verwenden Sie separate Konten, denen [Microsoft 365-Administratorrollen](../../admin/add-users/about-admin-roles.md) nur für die *Verwaltung zugewiesen sind.* Administratoren sollten über ein eigenes Benutzerkonto für die reguläre nicht administrative Verwendung verfügen und nur dann ein Administratorkonto verwenden, wenn dies erforderlich ist, um eine Aufgabe auszuführen, die mit ihrer Rollen- oder Auftragsfunktion verknüpft ist.
- Befolgen [Sie bewährte Methoden](/azure/active-directory/admin-roles-best-practices) zum Sichern privilegierter Konten in Azure AD.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 2: Konfigurieren der allgemeinen Identitäts- und Zugriffsrichtlinien für bedingten Zugriff](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[Konfigurieren der allgemeinen Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md)