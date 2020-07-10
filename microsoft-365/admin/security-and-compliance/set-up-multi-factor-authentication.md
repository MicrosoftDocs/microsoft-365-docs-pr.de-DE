---
title: Einrichten der Multi-Faktor-Authentifizierung für Benutzer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Hier erfahren Sie, wie Sie die Multi-Faktor-Authentifizierung für Ihre Organisation einrichten.
monikerRange: o365-worldwide
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083538"
---
# <a name="set-up-multi-factor-authentication"></a>Einrichten der mehrstufigen Authentifizierung
  
Ihre Kenntnis der [Multi-Faktor-Authentifizierung (MFA) und deren Unterstützung in Microsoft 365](multi-factor-authentication-microsoft-365.md) vorausgesetzt, ist es an der Zeit, diese einzurichten und für Ihre Organisation bereitzustellen.

Prüfen Sie, bevor Sie beginnen, ob diese speziellen Bedingungen für Sie zutreffen, und führen Sie die entsprechenden Schritte aus:

- Wenn Office 2013-Clients auf Windows-Geräten installiert sind, [aktivieren Sie die moderne Authentifizierung](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).

- Wenn Verzeichnisdienste von Drittanbietern mit Active Directory Federation Services (AD FS) genutzt werden, richten Sie den Azure MFA-Server ein. Weitere Informationen finden Sie unter [Erweiterte Szenarien mit Azure Multi-Faktor-Authentifizierung und VPN-Lösungen von Drittanbietern](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).

Alle anderen Benutzer werden bei Bedarf zu einer zusätzlichen Authentifizierung aufgefordert. Weitere Informationen finden Sie unter [Zwei-Faktor-Authentifizierung – Methode und Einstellungen](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Schritt 1: Entscheiden Sie sich für eine Methode, die Ihre Benutzer für die MFA verwenden müssen.

> [!NOTE]
> Sie müssen ein globaler Administrator sein, um die MFA einrichten oder ändern zu können. Es gibt drei Möglichkeiten, die MFA für die Anmeldung Ihrer Benutzer einzubinden. Weitere Informationen finden Sie unter [MFA-Support in Microsoft 365](multi-factor-authentication-microsoft-365.md).

- Standardsicherheitseinstellungen (empfohlen für kleine Unternehmen)

  Wenn Sie Ihr Abonnement oder Ihre Testversion nach dem 21. Oktober 2019 erworben haben und unerwartet eine MFA-Aufforderung erhalten, wurden automatisch die [Standardsicherheitseinstellungen](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) für Ihr Abonnement aktiviert.
  
  Bei jedem neuen Microsoft 365-Abonnement sind automatisch die Standardsicherheitseinstellungen aktiviert. Dies bedeutet, dass jeder Benutzer die Multi-Faktor-Authentifizierung (MFA) einrichten und die Microsoft Authenticator-App auf dem Mobilgerät installieren muss.

  Alle Benutzer müssen die Microsoft Authenticator-App als zusätzliche Überprüfungsmethode verwenden. Die Legacy-Authentifizierung wird blockiert. 

- Zugangsberechtigungsrichtlinien (empfohlen für Unternehmen)

  Die Benutzer wählen die zusätzliche Überprüfungsmethode während der MFA-Registrierung.

- Nach Benutzerkonto (nicht empfohlen)

  Die Benutzer wählen die zusätzliche Überprüfungsmethode während der MFA-Registrierung.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Schritt 2: Testen Sie die MFA mit Ihren Pilotbenutzern

Wenn Sie die MFA anhand von Zugangsberechtigungsrichtlinien oder nach Benutzerkonto (nicht empfohlen) verwenden, sollten Sie Pilotbenutzer in Ihrem Unternehmen oder Ihrer Organisation auswählen, um die MFA-Registrierung und die Anmeldung zu testen. Zum Beispiel:

- Wenn Sie Zugangsberechtigungsrichtlinien verwenden, müssen Sie eine Pilotbenutzergruppe und eine entsprechende Richtlinie erstellen, die die MFA für die Mitglieder der Gruppe und alle Apps erforderlich macht. Fügen Sie dann die Konten Ihrer Pilotbenutzer der Gruppe hinzu.

- Wenn Sie die MFA nach Benutzerkonto verwenden, müssen Sie die MFA für die einzelnen Benutzerkonten Ihrer Pilotbenutzer aktivieren.

Arbeiten Sie mit Ihren Pilotbenutzern zusammen und klären Sie Fragen und Probleme, um auf eine reibungslose Bereitstellung für Ihre Organisation vorbereitet zu sein.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Schritt 3: Informieren Sie Ihre Organisation, dass die MFA eingerichtet wird

Nutzen Sie E-Mail-Benachrichtigungen, Plakate, Teambesprechungen oder entsprechende Schulungen, um sicherzustellen, dass Ihre Mitarbeiter folgendes verstehen:

- Warum die MFA für Anmeldungen erforderlich ist
- [Wie sie sich für die zusätzliche Überprüfungsmethode registrieren](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Wie sie sich nach der Registrierung anmelden](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Wie sie die zusätzliche Überprüfungsmethode ändern können](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [Wie z. B. bei einem Wechsel des Smartphones vorgegangen werden muss](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

Stellen Sie vor allem sicher, dass Ihre Mitarbeiter verstehen ***ab wann die MFA Voraussetzung wird***, sodass es zu keinen Überraschungen kommt.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Schritt 4: Bereitstellung der MFA für Ihre Organisation oder Benutzer

Stellen Sie die MFA, entsprechend der von Ihnen gewählten MFA-Methode, für alle Mitarbeiter bereit.

### <a name="security-defaults"></a>Standardsicherheitseinstellungen 

Die Standardsicherheitseinstellungen können Sie im Azure-Portal im Bereich **Einstellungen** für Active Directory (Azure AD) aktivieren oder deaktivieren.

1.  Melden Sie sich mit den Anmeldeinformationen des globalen Administrators beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.
2.  Wechseln Sie zur Seite [Azure Active Directory – Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  Wählen Sie unten auf der Seite **Standardsicherheitseinstellungen verwalten** aus.
4.  Wählen Sie **Ja** aus, um die Standardsicherheitseinstellungen zu aktivieren und **Nein**, um die Standardsicherheitseinstellungen zu deaktivieren. Klicken Sie anschließend auf **Speichern**.

Wenn Sie bisher [grundlegende Zugangsberechtigungsrichtlinien](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) verwendet haben, gehen Sie folgendermaßen vor, um die Standardsicherheitseinstellungen zu nutzen.

1.  Wechseln Sie zur Seite [Zugangsberechtigung – Richtlinien](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Wählen Sie jede grundlegende Richtlinie aus, die auf **Ein** gesetzt ist und setzen Sie **Richtlinie aktivieren** auf **Aus**.
2.  Wechseln Sie zur Seite [Azure Active Directory – Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Wählen Sie unten auf der Seite **Standardsicherheitseinstellungen verwalten** aus.
5.  Wählen Sie **Ja** aus, um die Standardsicherheitseinstellungen zu aktivieren und **Nein**, um die Standardsicherheitseinstellungen zu deaktivieren. Klicken Sie anschließend auf **Speichern**.

### <a name="conditional-access-policies"></a>Zugangsberechtigungsrichtlinien

Erstellen, konfigurieren und aktivieren Sie die geeigneten Richtlinien für die Benutzergruppe, für die die MFA zur Anmeldung erforderlich ist.

### <a name="per-user-mfa-not-recommended"></a>MFA nach Benutzerkonto (nicht empfohlen)

Aktivieren Sie die Benutzerkonten entsprechend Ihrem Rollout für die MFA.

### <a name="supporting-your-employees"></a>Unterstützung ihrer Mitarbeiter

Wenn Ihre Mitarbeiter sich registrieren und die Anmeldung mittels MFA nutzen, sollten Sie sicherstellen, dass Ihre IT-Experten, Ihre IT-Abteilung oder Ihr Helpdesk Fragen beantworten und Probleme schnell beheben können.

In diesem Artikel finden Sie [Informationen zur Problembehandlung bei der Anmeldung mit MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2). 


