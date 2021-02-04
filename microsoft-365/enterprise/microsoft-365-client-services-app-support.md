---
title: Microsoft 365-Client- und Dienst-App-Unterstützung
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie Details zur Microsoft 365-Client- und Dienst-App-Unterstützung.
ms.openlocfilehash: 4e32e39281175ed66970a358ff632c2ddbb3ac1a
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097476"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Microsoft 365-Client- und Dienst-App-Unterstützung

Microsoft unterstützt eine Vielzahl von Sicherheits-, Authentifizierungs- und Compliancefeatures, um Kundendaten zu schützen und es IT-Administratoren zu ermöglichen, Richtlinien im Microsoft 365 Admin Center für ihre Benutzer anzupassen. Die folgenden Features sind nur eine Teilmenge der vielen Unternehmensfeatures, die Sie je nach Ihrem Microsoft 365-Abonnement konfigurieren können.

## <a name="client-and-service-support"></a>Client- und Dienstunterstützung

### <a name="continuous-access-evaluation-preview"></a>Kontinuierliche Zugriffsauswertung (Vorschau)

Die kontinuierliche Zugriffsauswertung wird implementiert, indem Dienste wie Exchange Online, SharePoint Online und Teams kritische Ereignisse in Azure Active Directory abonnieren können, damit diese Ereignisse nahezu in Echtzeit ausgewertet und erzwungen werden können. Die Auswertung kritischer Ereignisse ist nicht auf Richtlinien für bedingten Zugriff angewiesen und ist daher in jedem Mandanten verfügbar.

Die folgenden Ereignisse werden derzeit ausgewertet:

- Ein Benutzerkonto wird gelöscht oder deaktiviert
- Das Kennwort für einen Benutzer wird geändert oder zurückgesetzt.
- Die mehrstufige Authentifizierung ist für den Benutzer aktiviert.
- Administrator widerruft explizit alle Aktualisierungstoken für einen Benutzer
- Erhöhtes Benutzerrisiko, das von Azure AD Identity Protection erkannt wird

Weitere Informationen zur kontinuierlichen Zugriffsauswertung für die Client- und Dienst-App-Unterstützung finden Sie unter [Fortlaufende Zugriffsauswertung (Vorschau).](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)

## <a name="client-support"></a>Clientunterstützung

### <a name="certificate-based-authentication"></a>Zertifikatbasierte Authentifizierung

Bei der zertifikatbasierten Authentifizierung (CBA) wird ein digitales Zertifikat verwendet, um einen Benutzer, Computer oder ein Gerät zu identifizieren, bevor der Zugriff auf eine Ressource, ein Netzwerk, eine Anwendung oder einen Dienst gewährt wird. Bei der Benutzerauthentifizierung wird sie häufig in Abstimmung mit herkömmlichen Methoden wie Benutzernamen und Kennwörtern bereitgestellt.

Einige herkömmliche Lösungen funktionieren nur für Benutzer, z. B. Biometrie und Einmalkennwörter (One-Time Passwords, OTP). Bei der zertifikatbasierten Authentifizierung kann dieselbe Lösung für alle Endpunkte verwendet werden. Benutzer, Geräte und das wachsende Internet der Dinge (IoT).

Weitere Informationen zur zertifikatbasierten Authentifizierung für die Client- und Dienst-App-Unterstützung finden Sie unter [Microsoft 365 Client App Support: Certificate-based Authentication](microsoft-365-client-support-certificate-based-authentication.md).

### <a name="conditional-access"></a>Bedingter Zugriff

Bedingter Zugriff ist das Tool, das von Azure Active Directory verwendet wird, um Signale zusammenzubringen, Entscheidungen zu treffen und Unternehmenszugriffsrichtlinien zu erzwingen. Bedingter Zugriff ist das Herzstück des neuen identitätsgesteuerten Steuerelementmodells.

Richtlinien für bedingten Zugriff sind if-then-Anweisungen zum Gewähren des Zugriffs auf Ressourcen. Wenn ein Benutzer auf eine Ressource zugreifen möchte, muss er eine Aktion abschließen. Häufige Signale, die der bedingte Zugriff bei einer Entscheidung über den Richtlinienzugriff verwenden kann, sind:

- Benutzer- oder Gruppenmitgliedschaft
- Informationen zu den IP-Speicherorten
- Geräteinformationen
- Anwendungsinformationen
- Erkennung von Risiken in Echtzeit und berechnet
- Microsoft Cloud App Security (MCAS)

Wenn Sie diese Zugriffsentscheidungen treffen, können die Richtlinien unterschiedliche Aktionen ausführen:

- Die Richtlinie kann den Zugriff blockieren: Diese Konfiguration ist die restriktivste Aktion und hindert den Benutzer am Zugriff auf die Ressource.
- Die Richtlinie kann Zugriff gewähren: Diese Konfiguration ist eine weniger restriktive Entscheidung und erfordert möglicherweise noch eine oder mehrere der folgenden Optionen:

    - Mehrstufige Authentifizierung
    - Das Gerät, das als kompatibel gekennzeichnet werden soll
    - Das Gerät ist mit Azure AD hybrid verbunden.
    - Eine genehmigte Client-App
    - Konfigurierte App-Schutzrichtlinie (Vorschau)

Weitere Informationen zum bedingten Zugriff für die Client- und Dienst-App-Unterstützung finden Sie unter:

- [Microsoft 365-Client-App-Unterstützung: Gerätebasierter bedingter Zugriff](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>Mobile Anwendungsverwaltung (Mobile Application Management)

Benutzer greifen häufig sowohl auf Organisationsdokumente als auch auf persönliche Dokumente, E-Mails und Daten von demselben mobilen Gerät aus zu. Diese Geräte befinden sich häufig im persönlichen Besitz und sollten so konfiguriert werden, dass sowohl Organisationsdaten als auch der persönliche Datenschutz des Benutzers geschützt werden.

Wenn ein Benutzer auf Organisationsdaten zu zugegriffen hat, muss die Organisation darauf vertrauen, dass Organisationsrichtlinien, z. B. Konfigurations- und Schutzrichtlinien, angewendet werden, um Organisationsdaten auf dem Gerät zu schützen. Darüber hinaus sollten die persönlichen Inhalte des Benutzers auf dem Gerät außerhalb der Kontrolle der Organisation bleiben.

Für von der Organisation verwaltete Inhalte können Sie Anwendungsverwaltungsrichtlinien anwenden, um zu steuern, wie mithilfe von Microsoft Intune auf Daten zugegriffen, freigegeben und verwendet wird. Die folgenden Aktionen werden beispielsweise unterstützt:

- Remote wipe the managed organization content (alsoreferred to org data)
- Verhindern des Einsendens von Organisationsinhalten in Nicht-Organisation-Speicherorte
- Erfordern einer PIN für den Zugriff auf Organisationsinhalte
- Verhindern, dass verwaltete Apps auf Geräten mit Jailbreaks oder Gerootet ausgeführt werden
- Verhindern, dass Inhalte der Organisation in nicht genehmigten Cloudspeicheranbietern gespeichert werden
- Verhindern, dass nicht genehmigte Inhalte in verwaltete Anwendungen übertragen werden
- Zugriff auf Organisationsinhalte erst zulassen, nachdem Richtlinien angewendet wurden
- Bereitstellen der Anwendungskonfiguration zum Verwalten des Verhaltens und der Einstellungen der Anwendung
- Beschränken sie die verwaltete Anwendung auf eine definierte Identität, indem Sie Funktionen mit mehreren Identitäten oder die persönliche Nutzung deaktivieren.

Weitere Informationen zur Verwaltung mobiler Anwendungen mit Microsoft Intune finden Sie unter [Was ist Microsoft Intune-App-Verwaltung?](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

[Mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) ist eine Methode der Computerzugriffssteuerung, bei der einem Benutzer zugriff gewährt wird, nachdem er mehrere separate Nachweise für einen Authentifizierungsmechanismus erfolgreich präsentiert hat. Bei dieser Methode werden in der Regel mindestens zwei der folgenden Kategorien verwendet:

- Wissen (etwas, das sie wissen)
- Besitz (etwas, das sie haben)
- Rückschluss (etwas, was sie sind)

Weitere Informationen zur mehrstufigen Authentifizierung für die Client- und Dienst-App-Unterstützung finden Sie unter [Microsoft 365 Client App Support: Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md).

### <a name="single-sign-on"></a>Single Sign-On

Einmaliges Anmelden (Single Sign-On, SSO) bietet Sicherheit und Komfort, wenn sich Ihre Benutzer bei Anwendungen in Azure Active Directory anmelden. Bei einmaligem Anmelden melden sich Benutzer einmal mit einem Konto an, um auf lokale Ad DS(Active Directory Domain Services)-Domänengeräte, Software-as-a-Service-Anwendungen (SaaS)-Anwendungen und Webanwendungen in Ihrer Organisation zu zugreifen.

Weitere Informationen zum einmaligen Anmelden für die Unterstützung von Client- und Dienst-Apps finden Sie unter [Microsoft 365 Client App Support: Single Sign-On](microsoft-365-client-support-single-sign-on.md).

## <a name="services-support"></a>Unterstützung von Diensten

### <a name="modern-authentication"></a>Moderne Authentifizierung

Die moderne Authentifizierung ermöglicht neuen Szenarien für Kunden die Authentifizierung bei Office 365 und für Mandantenadministratoren, um bestimmte Authentifizierungsanforderungen für den gesamten Office 365-Mandanten zu erzwingen, z. B.:

- Unterstützung der mehrstufigen Authentifizierung für administrative Interaktionen mit dem Mandanz und diensten sowie Endbenutzerinteraktionen mit Anwendungen und deren Daten
- Bedingter Zugriff
- SAML-basierter Identitätsanbieter für die Anmeldung
- Smartcardprotokoll auf PCs
- Zertifikatbasierte Authentifizierung auf mobilen Geräten
- Die Übertragung von Anmeldeinformationen über die Standardauthentifizierung ist nicht mehr erforderlich.

Weitere Informationen zur Unterstützung moderner Authentifizierungsdienste finden Sie unter [Authentifizierung im Vergleich zur Autorisierung.](/azure/active-directory/develop/authentication-vs-authorization)

### <a name="azure-active-directory-conditional-access"></a>Bedingter Azure Active Directory-Zugriff

Azure Active Directory (Azure AD)-Regeln für bedingten Zugriff ermöglichen Es Kunden, den Zugriff auf Onlinedienste basierend auf Attributen wie Gerätekonformität oder Netzwerkstandort zu steuern. Die folgenden Lösungen können verwendet werden:

- Azure AD multi-factor authentication-based Conditional Access
- Standortbasierter bedingter Zugriff in Azure AD
- Gerätebasierter bedingter Azure AD-Zugriff

Azure AD Bedingte Zugriffsregeln werden pro Anwendung angewendet und stehen Kunden zur Verfügung, um den Zugriff basierend auf unterschiedlichen Bedingungen zu steuern. Mithilfe der mobilen Geräteverwaltung [(Mobile Device Management, MDM)](/mem/intune/fundamentals/what-is-device-management)oder Intune müssen Kunden den Zugriff auf Microsoft 365 auf diejenigen Benutzer beschränken können, die ein Organisationsgerät verwenden oder ihr persönliches Gerät für die Verwaltung registriert haben. Kunden können beispielsweise Regeln für bedingten Zugriff konfigurieren, um Steuerelemente wie die folgenden zu erzwingen:

- Zugriff nur von Geräten zulassen, die domänen- oder domänenkonform sind
- Erzwingen der mehrstufigen Authentifizierung für alle Zugriffe auf Exchange Online-Dienste

Weitere Informationen zum bedingten Zugriff in Azure Active Directory finden Sie unter [Was ist bedingter Zugriff?](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>TLS 1.2-Unterstützung

Um unseren Kunden die beste Verschlüsselung zu bieten, plant Microsoft, die Unterstützung für die Transport Layer Security (TLS)-Versionen 1.0 und 1.1 in Office 365 und Office 365 GCC nicht mehr zu unterstützen.

Wir verstehen, dass die Sicherheit Ihrer Daten wichtig ist, und wir legen großen Wert auf Transparenz bezüglich Änderungen, die Ihre Nutzung des TLS-Dienstes beeinträchtigen könnten. Es wird empfohlen, dass alle Client-Server- und Browser-Server-Kombinationen TLS 1.2 (oder eine neuere Version) verwenden, um die Verbindung zu Office 365-Diensten auf unterhalten. Dies erfordert möglicherweise Updates für bestimmte Client-Server- bzw. Browser-Server-Kombinationen.

Weitere Informationen zur Unterstützung von TLS 1.2-Support und -Diensten finden Sie unter Vorbereiten von [TLS 1.2 in Office 365 und Office 365 GCC](/microsoft-365/compliance/prepare-tls-1.2-in-office-365).
