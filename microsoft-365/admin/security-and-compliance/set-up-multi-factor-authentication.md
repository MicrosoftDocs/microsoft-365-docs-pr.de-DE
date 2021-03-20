---
title: Einrichten der Multi-Faktor-Authentifizierung für Benutzer
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
ms.openlocfilehash: 54c862d8f7c25472d84557e177a9107d2c14d846
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914462"
---
# <a name="set-up-multi-factor-authentication"></a>Einrichten der mehrstufigen Authentifizierung

Ihre Kenntnis der [Multi-Faktor-Authentifizierung (MFA) und deren Unterstützung in Microsoft 365](multi-factor-authentication-microsoft-365.md) vorausgesetzt, ist es an der Zeit, diese einzurichten und für Ihre Organisation bereitzustellen.

> [!IMPORTANT]
> Wenn Sie Ihr Abonnement oder Ihre Testversion nach dem 21. Oktober 2019 erworben haben und beim Anmelden eine MFA-Aufforderung erhalten, wurden automatisch die [Sicherheitsstandards](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) für Ihr Abonnement aktiviert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Sie müssen globaler Administrator sein, um MFA zu verwalten. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).
- Wenn Sie das veraltete MFA auf Benutzerbasis aktiviert haben, [deaktivieren Sie die Legacy-MFA auf Benutzerbasis](#turn-off-legacy-per-user-mfa).
- Wenn Office 2013-Clients auf Windows-Geräten installiert sind, [aktivieren Sie die moderne Authentifizierung für Office 2013-Clients](./enable-modern-authentication.md).
- Erweitert: Wenn Verzeichnisdienste von Drittanbietern mit Active Directory Federation Services (AD FS) genutzt werden, richten Sie den Azure MFA-Server ein. Weitere Informationen finden Sie unter [Erweiterte Szenarien mit Azure AD Multi-Factor Authentication und VPN-Lösungen von Drittanbietern](/azure/active-directory/authentication/howto-mfaserver-nps-vpn).

## <a name="turn-security-defaults-on-or-off"></a>Aktivieren oder Deaktivieren von Sicherheitsstandards

In den meisten Organisationen bieten Sicherheitsstandards ein gutes Maß an zusätzlicher Anmeldesicherheit. Weitere Informationen hierzu finden Sie unter [Was sind Sicherheitsstandards?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Wenn Ihr Abonnement neu ist, sind die Sicherheitsstandards möglicherweise bereits automatisch für Sie aktiviert.

Die Standardsicherheitseinstellungen können Sie im Azure-Portal im Bereich **Einstellungen** für Active Directory (Azure AD) aktivieren oder deaktivieren.

1. Melden Sie sich mit den Anmeldeinformationen des globalen Administrators beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.
2. Wählen Sie im linken Navigationsbereich **Alle anzeigen** und dann unter **Admin Center** die Option **Azure Active Directory** aus.
3. Im **Azure Active Directory Admin Center** wählen Sie dann **Azure Active Directory** \> **Eigenschaften** aus.
4. Wählen Sie unten auf der Seite **Sicherheitsstandards verwalten** aus.
5. Wählen Sie **Ja** aus, um die zu aktivieren oder **Nein**, um die Sicherheitsstandards zu deaktivieren. Klicken Sie anschließend auf **Speichern**.

Wenn Sie bisher [Basisrichtlinien für den bedingten Zugriff](/azure/active-directory/conditional-access/concept-baseline-protection) verwendet haben, werden Sie aufgefordert, diese zu deaktivieren, bevor Sie Sicherheitsstandards nutzen.

1. Wechseln Sie zur Seite [Zugangsberechtigung – Richtlinien](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2. Wählen Sie jede grundlegende Richtlinie aus, die auf **Ein** gesetzt ist und setzen Sie **Richtlinie aktivieren** auf **Aus**.
3. Wechseln Sie zur Seite [Azure Active Directory – Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4. Wählen Sie unten auf der Seite **Standardsicherheitseinstellungen verwalten** aus.
5. Wählen Sie **Ja** aus, um die Standardsicherheitseinstellungen zu aktivieren und **Nein**, um die Standardsicherheitseinstellungen zu deaktivieren. Klicken Sie anschließend auf **Speichern**.

## <a name="use-conditional-access-policies"></a>Verwenden von Richtlinien für den bedingten Zugriff

Wenn Ihre Organisation detailliertere Anforderungen an die Anmeldesicherheit hat, können Richtlinien für den bedingten Zugriff Ihnen mehr Kontrolle bieten. Mit bedingtem Zugriff können Sie Richtlinien erstellen und definieren, die auf Anmeldeereignisse reagieren und zusätzliche Aktionen anfordern, bevor einem Benutzer der Zugriff auf eine Anwendung oder einen Dienst gewährt wird.

> [!IMPORTANT]
> Deaktivieren Sie sowohl “MFA auf Benutzerbasis” als auch “Sicherheitsstandards”, bevor Sie die Richtlinien für den bedingten Zugriff aktivieren.

Bedingter Zugriff ist für Kunden verfügbar, die Azure AD Premium P1 oder Lizenzen erworben haben, die dies beinhalten, wie z. B. Microsoft 365 Business Premium und Microsoft 365 E3. Weitere Informationen finden Sie unter [Erstellen einer Richtlinie für den bedingten Zugriff](/azure/active-directory/authentication/tutorial-enable-azure-mfa).

Risikobasierter bedingter Zugriff ist in der Azure AD Premium P2-Lizenz oder Lizenzen, die diese umfassen, verfügbar, z. B. Microsoft 365 E5. Weitere Informationen finden Sie unter [Risikoabhängiger bedingter Zugriff](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).

Weitere Informationen zu Azure AD P1 und P2 finden Sie unter [Azure Active Directory – Preise](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="turn-on-modern-authentication-for-your-organization"></a>Aktivieren von moderner Authentifizierung für Ihre Organisation

Bei den meisten Abonnements wird die moderne Authentifizierung automatisch aktiviert. Wenn Sie Ihr Abonnement jedoch vor August 2017 gekauft haben, müssen Sie wahrscheinlich die moderne Authentifizierung aktivieren, damit Funktionen wie die mehrstufige Authentifizierung in Windows-Clients wie Outlook funktionieren.


1. Wählen Sie im Microsoft 365 Admin Center im linken Navigationsbereich **Einstellungen** \> **Organisationseinstellungen** aus.
2. Wählen Sie unter der Registerkarte **Dienste** die **moderne Authentifizierung** aus, und vergewissern Sie sich, dass im Bereich **Moderne Authentifizierung** die Option **Moderne Authentifizierung aktivieren** ausgewählt ist. Wählen Sie **Änderungen speichern** aus.

### <a name="turn-off-legacy-per-user-mfa"></a>Deaktivieren der Legacy-MFA auf Benutzerbasis

Wenn bisher die veraltete MFA auf Benutzerbasis aktiviert ist, müssen Sie diese deaktivieren, bevor Sie "Sicherheitsstandards" aktivieren.

1. Wählen Sie im Microsoft 365 Admin Center im linken Navigationsbereich **Benutzer** \> **Aktive Benutzer** aus.
1. Wählen Sie auf der Seite **Aktive Benutzer** die Option **Mehrstufige Authentifizierung** aus.
1. Wählen Sie auf der Seite "Mehrstufige Authentifizierung" jeden Benutzer aus, und setzen Sie Status für die mehrstufige Authentifizierung auf **Deaktiviert**.

## <a name="next-steps"></a>Nächste Schritte

- [Wie sie sich für die zusätzliche Überprüfungsmethode registrieren](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Was ist mehrstufige Authentifizierung?](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [Wie sie sich nach der Registrierung anmelden](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Wie sie die zusätzliche Überprüfungsmethode ändern können](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-topics"></a>Verwandte Themen

[Video: Aktivieren der mehrstufigen Authentifizierung](../../business-video/turn-on-mfa.md)

[Video: Aktivieren der mehrstufigen Authentifizierung für Ihr Telefon](../../business-video/set-up-mfa.md)