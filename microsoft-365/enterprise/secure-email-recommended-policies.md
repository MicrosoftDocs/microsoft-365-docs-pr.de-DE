---
title: Empfohlene Richtlinien für sichere e-Mails – Microsoft 365 für Unternehmen | Microsoft-Dokumente
description: Beschreibt die Richtlinien für Empfehlungen von Microsoft zur Anwendung von E-Mail-Richtlinien und -Konfigurationen.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
ms.openlocfilehash: cff9413a7c580fbefd51e48acfc9610b2b07430f
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295514"
---
# <a name="policy-recommendations-for-securing-email"></a>Richtlinienempfehlungen für sichere E-Mails

In diesem Artikel wird beschrieben, wie Sie die empfohlenen Identitäts-und Gerätezugriffs Richtlinien implementieren, um organisatorische e-Mail-und e-Mail-Clients zu schützen, die moderne Authentifizierung und bedingten Zugriff unterstützen. Dieser Leitfaden baut auf den [allgemeinen Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md) auf und enthält außerdem einige zusätzliche Empfehlungen.

Diese Empfehlungen basieren auf drei verschiedenen Ebenen der Sicherheit und des Schutzes, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können: **Baseline**, **sensibel**und **stark reguliert**. Weitere Informationen zu den Sicherheitsebenen und den empfohlenen Clientbetriebssystemen, auf die hier verwiesen wird, finden Sie in der [Einführung zu den empfohlenen Sicherheitsrichtlinien und -konfigurationen](microsoft-365-policies-configurations.md).

Diese Empfehlungen erfordern, dass Ihre Benutzer moderne e-Mail-Clients verwenden, einschließlich Outlook für IOS und Android auf mobilen Geräten. Outlook für IOS und Android bieten Unterstützung für die besten Features von Office 365. Diese mobilen Outlook-apps werden außerdem mit Sicherheitsfunktionen entworfen, die die mobile Nutzung unterstützen und mit anderen Microsoft Cloud-Sicherheitsfunktionen zusammenarbeiten. Weitere Informationen finden Sie unter [Outlook für IOS und Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="updating-common-policies-to-include-email"></a>Aktualisieren allgemeiner Richtlinien zum Einschließen von e-Mails

Das folgende Diagramm zeigt, welche Richtlinien aus den allgemeinen Identitäts-und Gerätezugriffs Richtlinien aktualisiert werden können, um e-Mails zu schützen.

[![Zusammenfassung der Richtlinienaktualisierungen für den Schutz des Zugriffs auf Teams und deren abhängigen Dienste](../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[Anzeigen einer größeren Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Beachten Sie das Hinzufügen einer neuen Richtlinie für Exchange Online zum Blockieren von ActiveSync-Clients. Dadurch wird die Verwendung von Outlook Mobile erzwungen.

Wenn Sie Exchange Online und Outlook in den Bereich der Richtlinien einbezogen haben, wenn Sie Sie eingerichtet haben, müssen Sie nur die neue Richtlinie erstellen, um ActiveSync-Clients zu blockieren. Überprüfen Sie die in der folgenden Tabelle aufgeführten Richtlinien, und nehmen Sie entweder die empfohlenen Ergänzungen vor, oder bestätigen Sie, dass diese bereits enthalten sind. Jede Richtlinie verweist auf die zugehörigen Konfigurationsanweisungen in [allgemeinen Identitäts-und Gerätezugriffs Richtlinien](identity-access-policies.md).

|Schutzebene|Richtlinien|Weitere Informationen|
|:---------------|:-------|:----------------|
|**Basisplan**|[MFA erforderlich, wenn das Anmelde Risiko *Mittel* groß oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von Exchange Online in die Zuweisung von Cloud-apps|
|        |[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Einbeziehen von Exchange Online in die Zuweisung von Cloud-apps|
|        |[Anwenden von App-Datenschutzrichtlinien](identity-access-policies.md#apply-app-data-protection-policies)|Stellen Sie sicher, dass Outlook in der Liste der Apps enthalten ist. Achten Sie darauf, die Richtlinie für jede Plattform (Ios, Android, Windows) zu aktualisieren.|
|        |[Erfordern von genehmigten apps und App-Schutz](identity-access-policies.md#require-approved-apps-and-app-protection)|Einschließen von Exchange Online in die Liste der Cloud-apps|
|        |[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Einschließen von Exchange Online in die Liste der Cloud-apps|
|        |[Blockieren von ActiveSync-Clients](#block-activesync-clients)|Diese neue Richtlinie hinzufügen| 
|**Vertraulich**|[MFA erforderlich, wenn das Anmelde Risiko *niedrig*, *Mittel* oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Einbeziehen von Exchange Online in die Zuweisung von Cloud-apps|
|         |[Erfordern von kompatiblen PCs *und* mobilen Geräten](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Einschließen von Exchange Online in die Liste der Cloud-apps|
|**Streng geregelt**|[*Immer* MFA erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von Exchange Online in die Zuweisung von Cloud-apps|

## <a name="block-activesync-clients"></a>Blockieren von ActiveSync-Clients

Mit dieser Richtlinie wird verhindert, dass ActiveSync-Clients andere Richtlinien für bedingten Zugriff umgehen. Die Richtlinienkonfiguration gilt nur für ActiveSync-Clients. Wenn Sie die Option **[App-Schutzrichtlinie anfordern](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** auswählen, blockiert diese Richtlinie ActiveSync-Clients. Details zum Erstellen dieser Richtlinie finden Sie unter [erfordern von App-Schutzrichtlinien für Cloud-App-Zugriff mit bedingtem Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

- Befolgtes "Schritt 2: Konfigurieren einer Azure AD Richtlinie für den bedingten Zugriff für Exchange Online mit ActiveSync (EAS)" in [Szenario 1: Office 365 apps erfordern genehmigte apps mit App-Schutzrichtlinien](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), wodurch verhindert wird, dass Exchange ActiveSync-Clients die Standardauthentifizierung für die Verbindung mit Exchange Online nutzen.

Sie können auch Authentifizierungsrichtlinien verwenden, um die [Standardauthentifizierung zu deaktivieren](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), wodurch alle Clientzugriffs Anforderungen für die Verwendung der modernen Authentifizierung erzwungen werden.

## <a name="set-up-message-encryption"></a>Einrichten der Nachrichtenverschlüsselung

Mit den neuen Funktionen für die Office 365 Nachrichtenverschlüsselung (OM), die die Schutzfunktionen in Azure Information Protection nutzen, kann Ihre Organisation problemlos geschützte e-Mails für alle Benutzer auf jedem Gerät freigeben. Benutzer können geschützte Nachrichten mit anderen Microsoft 365-Organisationen sowie nicht-Kunden mithilfe von Outlook.com, Gmail und anderen e-Mail-Diensten senden und empfangen.

Weitere Informationen finden Sie unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).

## <a name="next-steps"></a>Weitere Schritte

![Schritt 4: Richtlinien für Microsoft 365 Cloud-apps](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurieren von Richtlinien für bedingten Zugriff für:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](secure-email-recommended-policies.md)
