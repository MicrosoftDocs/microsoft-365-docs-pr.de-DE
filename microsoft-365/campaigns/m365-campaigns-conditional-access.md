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
description: Erfahren Sie, wie Sie MFA erfordern und Richtlinien für bedingten Zugriff für Microsoft 365 Business einrichten.
ms.openlocfilehash: b13ba9f8c948d9a1209655c44871ca62cb5354dd
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044500"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Mehrstufige Authentifizierung erforderlich und Einrichten von Richtlinien für bedingten Zugriff

Sie schützen den Zugriff auf Ihre Daten mit mehrstufiger Authentifizierung und Richtlinien für bedingten Zugriff. Diese erhöhen die Sicherheit erheblich. Microsoft stellt eine Reihe von grundlegenden Richtlinien für bedingten Zugriff zur Verfügung, die für alle Kunden empfohlen werden. Basisrichtlinien sind eine Reihe vordefinierter Richtlinien, die Organisationen vor vielen häufigen Angriffen schützen. Zu diesen häufigen Angriffen gehören Kennwort-Spray, Wiedergabe und Phishing.

Diese Richtlinien erfordern, dass Administratoren und Benutzer unter bestimmten Bedingungen eine zweite Authentifizierungsform (mehrstufige Authentifizierung oder MFA) eingeben. Wenn beispielsweise ein Benutzer in Ihrer Organisation versucht, sich von einem anderen Land oder von einem unbekannten Gerät bei Microsoft 365 zu anmelden, kann die Anmeldung als riskant betrachtet werden. Der Benutzer muss eine zusätzliche Form der Authentifizierung bereitstellen (z. B. einen Fingerabdruck oder einen Code), um seine Identität nachzuweisen.

Derzeit umfassen die Basisrichtlinien die folgenden Richtlinien:

- Einrichten im Microsoft 365 Admin Center:
  - **MFA für Administratoren** erforderlich: Erfordert die mehrstufige Authentifizierung für die privilegiertesten Administratorrollen, einschließlich des globalen Administrators.
  - **Endbenutzerschutz:** Erfordert eine mehrstufige Authentifizierung für Benutzer nur, wenn eine Anmeldung riskant ist. 
- Einrichten im Azure Active Directory-Portal:
  - **Blockieren der Legacyauthentifizierung:** Ältere Client-Apps und einige neue Apps verwenden keine neueren, sichereren Authentifizierungsprotokolle. Diese älteren Apps können Richtlinien für bedingten Zugriff umgehen und nicht autorisierten Zugriff auf Ihre Umgebung erhalten. Diese Richtlinie blockiert den Zugriff von Clients, die bedingten Zugriff nicht unterstützen. 
  - **MFA für Dienstverwaltung** erforderlich: Erfordert eine mehrstufige Authentifizierung für den Zugriff auf Verwaltungstools, einschließlich des Azure-Portals (in dem Sie Basisrichtlinien konfigurieren).

Es wird empfohlen, alle diese Basisrichtlinien zu aktivieren. Nachdem diese Richtlinien aktiviert wurden, werden Administratoren und Benutzer aufgefordert, sich für die mehrstufige Azure AD-Authentifizierung zu registrieren.

Weitere Informationen zu diesen Richtlinien finden Sie unter [Was sind Basisrichtlinien?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)

## <a name="require-mfa"></a>MFA erforderlich

So fordern Sie an, dass sich alle Benutzer mit einer zweiten Form der ID anmelden:

1. Wechseln Sie zum Admin Center, <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> und wählen Sie Setup **aus.**

2. On the Setup page, choose **View** in the **Make sign-in more secure** card.

    ![Sorgen Sie dafür, dass die Anmeldung sicherer ist.](../media/setupmfa.png)
3. Wählen Sie auf der Seite "Anmeldung sicherer machen" die Option **"Erste Schritte" aus.**

4. Aktivieren Sie im Sicherheitsbereich "Anmeldung stärken"  die Kontrollkästchen neben "Mehrstufige Authentifizierung für Administratoren erforderlich" und "Benutzer müssen sich für die mehrstufige Authentifizierung registrieren und den Zugriff blockieren, wenn ein Risiko erkannt **wird".**
    Stellen Sie sicher, dass Sie das Administratorkonto für Notfälle oder "Break-Glass" von der MFA-Anforderung im Feld "Benutzer **suchen"** ausschließen. [](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)

    ![Stärken Sie die Sicherheitsseite für die Einsingung.](../media/requiremfa.png)

5. Klicken **Sie unten auf** der Seite auf "Richtlinie erstellen".

## <a name="set-up-baseline-policies"></a>Einrichten von Basisrichtlinien

1. Wechseln Sie zum [Azure-Portal,](https://portal.azure.com)und navigieren Sie dann zu **Azure Active Directory** Conditional \> **Access,** um eine neue Richtlinie zu **erstellen.**

Weitere Informationen finden Sie in den folgenden spezifischen Anweisungen für jede Richtlinie: <br>
    - [MFA für Administratoren erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [MFA für Benutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [Blockieren von Legacy-Authentifizierung](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [MFA für Die Dienstverwaltung erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> Vorschaurichtlinien sind nicht mehr vorhanden, und Benutzer müssen eigene Richtlinien erstellen.

Sie können zusätzliche Richtlinien einrichten, z. B. die Anforderung genehmigter Client-Apps. Weitere Informationen finden Sie in der [Dokumentation zum bedingten Zugriff.](https://docs.microsoft.com/azure/active-directory/conditional-access/)
