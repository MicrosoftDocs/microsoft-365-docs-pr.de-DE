---
title: Einrichten der mehrstufigen Authentifizierung für Benutzer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Hier erfahren Sie, wie Sie die mehrstufige Authentifizierung für Ihre Organisation einrichten.
monikerRange: o365-worldwide
ms.openlocfilehash: ca1a8bd47e2fa5bbd7b7aed396debefaad10ea5e
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351715"
---
# <a name="set-up-multi-factor-authentication"></a>Einrichten der mehrstufigen Authentifizierung
  
Basierend auf Ihrem Verständnis der [mehrstufigen Authentifizierung (MFA) und seiner Unterstützung in Microsoft 365](multi-factor-authentication-microsoft-365.md)ist es an der Zeit, es einzurichten und für Ihre Organisation bereitzustellen.

Bevor Sie beginnen, sollten Sie feststellen, ob diese speziellen Bedingungen auf Sie zutreffen, und die entsprechende Aktion durchführen:

- Wenn Sie Office 2013 Clients auf Windows-Geräten haben, aktivieren Sie die [moderne Authentifizierung](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).

- Wenn Sie über Drittanbieter-Verzeichnisdienste mit Active Directory Verbunddienste (AD FS) verfügen, richten Sie den Azure MFA-Server ein. Weitere Informationen finden Sie unter [Erweiterte Szenarien mit mehrstufiger Azure-Authentifizierung und VPN-Lösungen von Drittanbietern](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) .

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Schritt 1: entscheiden Sie sich für die Methode, dass Ihre Benutzer MFA verwenden

Es gibt drei Möglichkeiten, Ihre Benutzer zur Verwendung von MFA für die Anmeldung zu zwingen. Details finden Sie unter [MFA Support in Microsoft 365](multi-factor-authentication-microsoft-365.md) .

- Sicherheitsstandards (empfohlen für kleine Unternehmen)

  Wenn Sie Ihr Abonnement oder eine Testversion nach dem 21. Oktober 2019 gekauft haben und Sie unerwarteterweise zur MFA aufgefordert werden, wurden [Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) für Ihr Abonnement automatisch aktiviert.
  
  Für jedes neue Microsoft 365-Abonnement werden automatisch Sicherheitsstandards aktiviert. Dies bedeutet, dass jeder Benutzer MFA einrichten und die Microsoft Authenticator-App auf seinem mobilen Gerät installieren muss.

  Alle Benutzer müssen die Microsoft Authenticator-App verwenden, da ihre zusätzliche Überprüfungsmethode und die Legacy Authentifizierung blockiert werden. 

- Richtlinien für bedingten Zugriff (empfohlen für Unternehmen)

  Benutzer wählen die zusätzliche Überprüfungsmethode während der MFA-Registrierung aus.

- Konto pro Benutzer (nicht empfohlen)

  Benutzer wählen die zusätzliche Überprüfungsmethode während der MFA-Registrierung aus.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Schritt 2: Testen Sie MFA auf Ihren Pilotbenutzern.

Wenn Sie Richtlinien für bedingten Zugriff oder MFA auf Benutzerbasis (nicht empfohlen) verwenden, wählen Sie Pilotbenutzer in Ihrem Unternehmen oder Ihrer Organisation aus, um die MFA-Registrierung und-Anmeldung zu testen. Zum Beispiel:

- Erstellen Sie für Richtlinien für bedingten Zugriff eine Pilotbenutzergruppe und eine Richtlinie, die MFA für die Mitglieder der Gruppe und für alle apps erfordert. Fügen Sie dann die Konten Ihres Pilot Benutzers zur Gruppe hinzu.

- Aktivieren Sie für den MFA pro Benutzer die Option MFA für die Benutzerkonten ihrer Pilotbenutzer jeweils.

Arbeiten Sie mit ihren Pilotbenutzern zusammen, um Fragen und Probleme zur Vorbereitung auf ein reibungsloses Rollout in Ihrer Organisation zu behandeln.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>SCHRITT 3: Informieren Sie Ihre Organisation, dass MFA kommt

Verwenden Sie e-Mail-Benachrichtigungen, Flur Poster, Teambesprechungen oder formelle Schulungen, um sicherzustellen, dass Ihre Mitarbeiter Folgendes verstehen:

- Warum MFA für Anmeldungen erforderlich ist
- [Registrieren für die zusätzliche Überprüfungsmethode](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [Vorgehensweise anmelden nach der Registrierung](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [Vorgehensweise ändern ihrer zusätzlichen Überprüfungsmethode](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [Umgang mit Situationen wie ein neues Smartphone](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

Stellen Sie sicher, dass Ihre Mitarbeiter verstehen, ***wann die MFA-Anforderung auferlegt*** wird, damit Sie nicht überrascht.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Schritt 4: Rollout der MFA-Anforderung für Ihre Organisation oder Benutzer

Stellen Sie basierend auf der ausgewählten MFA-Anforderungsmethode die MFA-Authentifizierung für die Mitarbeiter außerhalb ihrer Pilottester bereit.

### <a name="security-defaults"></a>Sicherheitsstandards

Sie aktivieren oder deaktivieren Sicherheitseinstellungen im **Eigenschaften** Bereich für Azure Active Directory (Azure AD) im Azure-Portal.

1.  Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit globalen Administratoranmeldeinformationen an.
2.  Wechseln Sie zur [Seite Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  Wählen Sie am unteren Rand der Seite **Sicherheitsstandards verwalten** aus.
4.  Wählen Sie **Ja** aus, um Sicherheitsstandards zu aktivieren, und **Nein** , um Sicherheitsstandards zu deaktivieren, und wählen Sie dann **Speichern**aus.

Wenn Sie [grundlegende Richtlinien für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)verwendet haben, erfahren Sie hier, wie Sie mit Sicherheitsstandards fortfahren.

1.  Wechseln Sie zur [Seite bedingte Zugriffs-Richtlinien](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Wählen Sie die einzelnen Basisrichtlinien **aus, und legen** Sie die **Option Richtlinie aktivieren** auf **aus**fest.
2.  Wechseln Sie zur [Seite Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Wählen Sie am unteren Rand der Seite **Sicherheitsstandards verwalten** aus.
5.  Wählen Sie **Ja** aus, um Sicherheitsstandards zu aktivieren, und **Nein** , um Sicherheitsstandards zu deaktivieren, und wählen Sie dann **Speichern**aus.

### <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Erstellen, konfigurieren und aktivieren Sie die entsprechenden Richtlinien, die die Gruppe von Benutzern enthalten, die MFA für die Anmeldung benötigen.

### <a name="per-user-mfa-not-recommended"></a>MFA pro Benutzer (nicht empfohlen)

Aktivieren Sie Benutzerkonten für den MFA, der Ihrem Rollout entspricht.

### <a name="supporting-your-employees"></a>Unterstützung ihrer Mitarbeiter

Wenn sich Ihre Mitarbeiter registrieren und mit der Anmeldung bei MFA beginnen, stellen Sie sicher, dass Ihre IT-Spezialisten, die IT-Abteilung oder der Helpdesk Fragen beantworten und Probleme schnell beheben können.

In diesem Artikel finden Sie [Informationen zur Problembehandlung bei MFA-Anmeldungen](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2). 


