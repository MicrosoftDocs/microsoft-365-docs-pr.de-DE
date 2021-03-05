---
title: Einrichten von Richtlinien für bedingten Zugriff
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie MFA benötigen und Richtlinien für bedingten Zugriff für Microsoft 365 Business einrichten.
ms.openlocfilehash: e16b7f4ff7d215ee749435806be214a807cc60a4
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453669"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Mehrstufige Authentifizierung erforderlich und Einrichten von Richtlinien für bedingten Zugriff

Sie schützen den Zugriff auf Ihre Daten mit mehrstufiger Authentifizierung und Richtlinien für bedingten Zugriff. Diese erhöhen die Sicherheit erheblich. Microsoft bietet eine Reihe von Basisrichtlinien für bedingten Zugriff, die für alle Kunden empfohlen werden. Basisrichtlinien sind eine Reihe vordefinierter Richtlinien, die Organisationen vor vielen häufigen Angriffen schützen. Diese häufigen Angriffe können Kennwort-Spray, Wiedergabe und Phishing umfassen.

Für diese Richtlinien müssen Administratoren und Benutzer unter bestimmten Bedingungen eine zweite Authentifizierungsform (als mehrstufige Authentifizierung oder MFA bezeichnet) eingeben. Wenn beispielsweise ein Benutzer in Ihrer Organisation versucht, sich von einem anderen Land oder von einem unbekannten Gerät bei Microsoft 365 zu anmelden, kann die Anmeldung als riskant angesehen werden. Der Benutzer muss eine zusätzliche Form der Authentifizierung (z. B. einen Fingerabdruck oder code) bereitstellen, um seine Identität nachweisen zu können.

Derzeit umfassen die Basisrichtlinien die folgenden Richtlinien:

- Einrichten im Microsoft 365 Admin Center:
  - **MFA für Administratoren** erforderlich: Erfordert die mehrstufige Authentifizierung für die privilegiertesten Administratorrollen, einschließlich des globalen Administrators.
  - **Endbenutzerschutz:** Erfordert eine mehrstufige Authentifizierung für Benutzer nur, wenn eine Anmeldung riskant ist. 
- Einrichten im Azure Active Directory-Portal:
  - **Blockieren der** Legacyauthentifizierung: Ältere Client-Apps und einige neue Apps verwenden keine neueren, sichereren Authentifizierungsprotokolle. Diese älteren Apps können Richtlinien für bedingten Zugriff umgehen und nicht autorisierten Zugriff auf Ihre Umgebung erhalten. Diese Richtlinie blockiert den Zugriff von Clients, die bedingten Zugriff nicht unterstützen. 
  - **MFA für Die Dienstverwaltung** erforderlich: Erfordert die mehrstufige Authentifizierung für den Zugriff auf Verwaltungstools, einschließlich des Azure-Portals (in dem Sie Basisrichtlinien konfigurieren).

Es wird empfohlen, alle diese Basisrichtlinien zu aktivieren. Nachdem diese Richtlinien aktiviert wurden, werden Administratoren und Benutzer aufgefordert, sich für die mehrstufige Azure AD-Authentifizierung zu registrieren.

Weitere Informationen zu diesen Richtlinien finden Sie unter [Was sind Basisrichtlinien?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)

## <a name="require-mfa"></a>MFA erforderlich

So fordern Sie, dass sich alle Benutzer mit einer zweiten Form von ID anmelden:

1. Wechseln Sie zum Admin Center <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> unter, und wählen Sie **Setup aus.**

2. Wählen Sie auf der Seite Setup **in der** Option **Anmeldung sicherer** machen die Option Anzeigen aus.

    ![Machen Sie die Anmeldung sicherer.](../media/setupmfa.png)
3. Wählen Sie auf der Seite Anmeldung sicherer machen die Option **Erste Schritte aus.**

4. Aktivieren Sie im Bereich Verstärkung der Anmeldesicherheit  die Kontrollkästchen neben Mehrstufige Authentifizierung für Administratoren erfordern und Benutzer für die mehrstufige Authentifizierung registrieren und den Zugriff blockieren, wenn ein Risiko **erkannt wird.**
    Schließen Sie das [Notfall-](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) oder "Unterbrechungsglas"-Administratorkonto aus der MFA-Anforderung im Feld Benutzer **suchen** aus.

    ![Stärken Sie die Sicherheitsseite für einsing-In.](../media/requiremfa.png)

5. Klicken **Sie unten auf** der Seite auf Richtlinie erstellen.

## <a name="set-up-baseline-policies"></a>Einrichten von Basisrichtlinien

1. Wechseln Sie zum [Azure-Portal,](https://portal.azure.com)und navigieren Sie dann zu **Bedingter Azure Active** \> **Directory-Sicherheitszugriff,** \>  um eine neue Richtlinie **zu erstellen.**

Sehen Sie sich die folgenden spezifischen Anweisungen für jede Richtlinie an: <br>
    - [MFA für Administratoren erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [MFA für Benutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [Blockieren der Legacyauthentifizierung](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [MFA für die Dienstverwaltung erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> Vorschaurichtlinien sind nicht mehr vorhanden, und Benutzer müssen eigene Richtlinien erstellen.

Sie können zusätzliche Richtlinien einrichten, z. B. die Anforderung genehmigter Client-Apps. Weitere Informationen finden Sie in der [Dokumentation zum bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/).
