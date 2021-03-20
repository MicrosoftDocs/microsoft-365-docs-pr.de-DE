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
ms.openlocfilehash: e380efffc1bf29cbd4d3a77d32e4d1f8b2994da3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905008"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Microsoft 365-Client- und Dienst-App-Unterstützung

Microsoft unterstützt eine vielzahl von Sicherheits-, Authentifizierungs- und Compliancefeatures, um Kundendaten zu schützen und IT-Administratoren die Anpassung von Richtlinien im Microsoft 365 Admin Center für ihre Benutzer zu ermöglichen. Die folgenden Features sind nur eine Teilmenge der vielen Unternehmensfeatures, die Sie je nach Ihrem Microsoft 365-Abonnement konfigurieren können.

## <a name="client-and-service-support"></a>Client- und Dienstunterstützung

### <a name="continuous-access-evaluation-preview"></a>Kontinuierliche Zugriffsauswertung (Vorschau)

Die kontinuierliche Zugriffsauswertung wird implementiert, indem Diensten wie Exchange Online, SharePoint Online und Teams das Abonnieren kritischer Ereignisse in Azure Active Directory ermöglicht wird, sodass diese Ereignisse nahezu in Echtzeit ausgewertet und erzwungen werden können. Die Bewertung kritischer Ereignisse ist nicht auf Richtlinien für bedingten Zugriff angewiesen, sodass sie in jedem Mandanten verfügbar sind.

Die folgenden Ereignisse werden derzeit ausgewertet:

- Ein Benutzerkonto wird gelöscht oder deaktiviert
- Das Kennwort für einen Benutzer wird geändert oder zurückgesetzt.
- Die mehrstufige Authentifizierung ist für den Benutzer aktiviert
- Administrator widerruft explizit alle Aktualisierungstoken für einen Benutzer
- Erhöhtes Benutzerrisiko, das von Azure AD Identity Protection erkannt wird

Weitere Informationen zur kontinuierlichen Zugriffsauswertung für den Client- und Dienst-App-Support finden Sie unter [Continuous access evaluation (preview)](/azure/active-directory/conditional-access/concept-continuous-access-evaluation).

## <a name="client-support"></a>Clientunterstützung

### <a name="certificate-based-authentication"></a>Zertifikatbasierte Authentifizierung

Die zertifikatbasierte Authentifizierung (CBA) ist die Verwendung eines digitalen Zertifikats zum Identifizieren eines Benutzers, Computers oder Geräts, bevor zugriff auf eine Ressource, ein Netzwerk, eine Anwendung oder einen Dienst gewährt wird. Bei der Benutzerauthentifizierung wird sie häufig in Abstimmung mit herkömmlichen Methoden wie Benutzernamen und Kennwörtern bereitgestellt.

Einige herkömmliche Lösungen funktionieren nur für Benutzer, z. B. biometrie- und einmalkennwörter (OTP). Bei der zertifikatbasierten Authentifizierung kann dieselbe Lösung für alle Endpunkte verwendet werden. Benutzer, Geräte und das wachsende Internet der Dinge (Internet of Things, IoT).

Weitere Informationen zur zertifikatbasierten Authentifizierung für die Client- und Dienst-App-Unterstützung finden Sie unter [Microsoft 365 Client App Support: Certificate-based Authentication](microsoft-365-client-support-certificate-based-authentication.md).

### <a name="conditional-access"></a>Bedingter Zugriff

Bedingter Zugriff ist das tool, das von Azure Active Directory verwendet wird, um Signale zusammenzubringen, Entscheidungen zu treffen und Richtlinien für den Organisatorischen Zugriff zu erzwingen. Bedingter Zugriff steht im Mittelpunkt des neuen identitätsgesteuerten Steuerelementmodells.

Richtlinien für bedingten Zugriff sind if-then-Anweisungen zum Gewähren des Zugriffs auf Ressourcen. Wenn ein Benutzer auf eine Ressource zugreifen möchte, muss der Benutzer eine Aktion abschließen. Allgemeine Signale, die bedingter Zugriff bei der Entscheidung über den Richtlinienzugriff verwenden kann, sind:

- Benutzer- oder Gruppenmitgliedschaft
- Informationen zum IP-Standort
- Geräteinformationen
- Anwendungsinformationen
- Echtzeit- und berechnete Risikoerkennung
- Microsoft Cloud App Security (MCAS)

Bei diesen Zugriffsentscheidungen können die Richtlinien unterschiedliche Aktionen ausführen:

- Die Richtlinie kann den Zugriff blockieren: Diese Konfiguration ist die restriktivste Aktion und hindert den Benutzer am Zugriff auf die Ressource.
- Die Richtlinie kann Zugriff gewähren: Diese Konfiguration ist weniger restriktiv und erfordert möglicherweise eine oder mehrere der folgenden Optionen:

    - Mehrstufige Authentifizierung
    - Das Gerät, das als kompatibel gekennzeichnet werden soll
    - Das Gerät ist azure AD-hybrid beigetreten
    - Eine genehmigte Client-App
    - App-Schutzrichtlinie konfiguriert (Vorschau)

Weitere Informationen zum bedingten Zugriff für die Client- und Dienst-App-Unterstützung finden Sie unter:

- [Microsoft 365 Client App Support: Gerätebasierter bedingter Zugriff](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>Mobile Anwendungsverwaltung (Mobile Application Management)

Benutzer greifen häufig sowohl auf Organisationsdokumente als auch auf persönliche Dokumente, E-Mails und Daten auf demselben mobilen Gerät zu. Diese Geräte befinden sich häufig im persönlichen Besitz und sollten so konfiguriert werden, dass sowohl Organisationsdaten als auch die Persönlichen Daten des Benutzers geschützt werden.

Wenn ein Benutzer auf Organisationsdaten zutritt, muss die Organisation darauf vertrauen, dass Organisationsrichtlinien, z. B. Konfigurationsrichtlinien und Schutzrichtlinien, angewendet werden, um Organisationsdaten auf dem Gerät zu schützen. Darüber hinaus sollten die persönlichen Inhalte des Benutzers auf dem Gerät außerhalb der Kontrolle der Organisation bleiben.

Für von der Organisation verwaltete Inhalte können Sie Anwendungsverwaltungsrichtlinien anwenden, um zu steuern, wie mithilfe von Microsoft Intune auf Daten zugegriffen, freigegeben und verwendet wird. Beispielsweise werden die folgenden Aktionen unterstützt:

- Remote wipe the managed organization content (alsoreferred to org data)
- Verhindern des Pastings von Organisationsinhalten an Nicht-Organisationsstandorte
- Erfordern einer PIN für den Zugriff auf Organisationsinhalte
- Verhindern, dass verwaltete Apps auf jailbroken oder gerooteten Geräten ausgeführt werden
- Verhindern, dass Organisationsinhalte in nicht genehmigten Cloudspeicheranbietern gespeichert werden
- Verhindern, dass nicht genehmigte Inhalte in verwaltete Anwendungen übertragen werden
- Zugriff auf Organisationsinhalte nur zulassen, nachdem Richtlinien angewendet wurden
- Bereitstellen der Anwendungskonfiguration zum Verwalten des Verhaltens und der Einstellungen der Anwendung
- Einschränken der verwalteten Anwendung auf eine definierte Identität durch Deaktivieren von Funktionen mit mehreren Identitäten oder persönliche Nutzung

Weitere Informationen zur Verwaltung mobiler Anwendungen mit Microsoft Intune finden Sie unter [Was ist Microsoft Intune-App-Verwaltung?](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

[Mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) ist eine Methode der Computerzugriffssteuerung, bei der einem Benutzer zugriff nur gewährt wird, nachdem einem Authentifizierungsmechanismus mehrere separate Nachweise erfolgreich präsentiert wurden. Diese Methode verwendet in der Regel mindestens zwei der folgenden Kategorien:

- Wissen (etwas, das sie wissen)
- Besitz (etwas, das sie haben)
- Inherence (etwas, was sie sind)

Weitere Informationen zur mehrstufigen Authentifizierung für die Client- und Dienst-App-Unterstützung finden Sie unter [Microsoft 365 Client App Support: Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md).

### <a name="single-sign-on"></a>Single Sign-On

Einmaliges Anmelden (Single Sign-On, SSO) bietet Sicherheit und Komfort, wenn sich Ihre Benutzer bei Anwendungen in Azure Active Directory anmelden. Bei einmaligem Anmelden melden sich Benutzer einmal mit einem Konto an, um auf lokale Active Directory Domain Services (AD DS)-Domänengeräte, Software as a Service (SaaS)-Anwendungen und Webanwendungen in Ihrer Organisation zu zugreifen.

Weitere Informationen zum einmaligen Anmelden für den Client- und Dienst-App-Support finden Sie unter [Microsoft 365 Client App Support: Einmaliges Anmelden](microsoft-365-client-support-single-sign-on.md).

## <a name="services-support"></a>Unterstützung von Diensten

### <a name="modern-authentication"></a>Moderne Authentifizierung

Mit der modernen Authentifizierung können sich Kunden in neuen Szenarien bei Office 365 authentifizieren und Mandantenadministratoren bestimmte Authentifizierungsanforderungen für den gesamten Office 365-Mandanten erzwingen, z. B.:

- Mehrstufige Authentifizierungsunterstützung für die administrative Interaktion mit dem Mandanz und den Diensten sowie für die Interaktion zwischen Endbenutzern und Anwendungen und deren Daten
- Bedingter Zugriff
- SAML-basiertes Anmelden eines Identitätsanbieters eines Drittanbieters
- Smartcard-Anmeldung auf PCs
- Zertifikatbasierte Authentifizierung auf mobilen Geräten
- Die Übertragung von Anmeldeinformationen über die Standardauthentifizierung ist nicht mehr erforderlich.

Weitere Informationen zur Unterstützung moderner Authentifizierungsdienste finden Sie unter [Authentication vs. authorization](/azure/active-directory/develop/authentication-vs-authorization).

### <a name="azure-active-directory-conditional-access"></a>Bedingter Zugriff in Microsoft Azure Active Directory

Azure Active Directory (Azure AD) Regeln für bedingten Zugriff ermöglichen Es Kunden, den Zugriff auf Onlinedienste basierend auf Attributen wie Gerätekonformität oder Netzwerkspeicherort zu steuern. Die folgenden Lösungen können verwendet werden:

- Azure AD multi-factor authentication-based Conditional Access
- Standortbasierter bedingter Azure AD-Zugriff
- Gerätebasierter bedingter Azure AD-Zugriff

Azure AD Regeln für bedingten Zugriff werden pro Anwendung angewendet und stehen Kunden zur Verfügung, um den Zugriff basierend auf unterschiedlichen Bedingungen zu steuern. Mithilfe von [Mobile Device Management (MDM)](/mem/intune/fundamentals/what-is-device-management)oder Intune müssen Kunden den Zugriff auf Microsoft 365 nur auf benutzer beschränken können, die ein Organisationsgerät verwenden oder ihr persönliches Gerät für die Verwaltung registriert haben. Kunden können beispielsweise Regeln für bedingten Zugriff konfigurieren, um Steuerelemente zu erzwingen, z. B.:

- Nur Zugriff von Geräten zulassen, die der Domäne beigetreten sind oder domänenkonform sind
- Erzwingen der mehrstufigen Authentifizierung für den zugriff auf Exchange Online-Dienste

Weitere Informationen zu bedingten Azure Active Directory-Zugriffen finden Sie unter [Was ist bedingter Zugriff?](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>TLS 1.2-Unterstützung

Um unseren Kunden die beste Verschlüsselung zu bieten, plant Microsoft, die Unterstützung für die Transport Layer Security (TLS)-Versionen 1.0 und 1.1 in Office 365 und Office 365 GCC nicht mehr zu unterstützen.

Wir verstehen, dass die Sicherheit Ihrer Daten wichtig ist, und wir legen großen Wert auf Transparenz bezüglich Änderungen, die Ihre Nutzung des TLS-Dienstes beeinträchtigen könnten. Es wird empfohlen, dass alle Client-Server- und Browser-Server-Kombinationen TLS 1.2 (oder eine spätere Version) verwenden, um die Verbindung mit Office 365-Diensten aufrecht zu erhalten. Dies erfordert möglicherweise Updates für bestimmte Client-Server- bzw. Browser-Server-Kombinationen.

Weitere Informationen zur Unterstützung von TLS 1.2-Support und -Diensten finden Sie unter [Preparing for TLS 1.2 in Office 365 and Office 365 GCC](../compliance/prepare-tls-1.2-in-office-365.md).