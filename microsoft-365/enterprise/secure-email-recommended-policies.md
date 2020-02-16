---
title: Empfohlene Richtlinien für sichere E-Mails – Microsoft 365 Enterprise | Microsoft-Dokumentation
description: Beschreibt die Richtlinien für Empfehlungen von Microsoft zur Anwendung von E-Mail-Richtlinien und -Konfigurationen.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: aea95dae0165eb23331b2fa24d5fc752df3f4345
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084309"
---
# <a name="policy-recommendations-for-securing-email"></a>Richtlinienempfehlungen für sichere E-Mails

In diesem Artikel wird beschrieben, wie Sie die empfohlenen Identitäts-und Gerätezugriffs Richtlinien implementieren, um organisatorische e-Mail-und e-Mail-Clients zu schützen, die moderne Authentifizierung und bedingten Zugriff unterstützen. Dieser Leitfaden baut auf den [allgemeinen Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md) auf und enthält außerdem einige zusätzliche Empfehlungen.

Diese Empfehlungen basieren auf drei verschiedenen Ebenen der Sicherheit und des Schutzes, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können: **Baseline**, **sensibel**und **stark reguliert**. Weitere Informationen zu den Sicherheitsebenen und den empfohlenen Clientbetriebssystemen, auf die hier verwiesen wird, finden Sie in der [Einführung zu den empfohlenen Sicherheitsrichtlinien und -konfigurationen](microsoft-365-policies-configurations.md).

Diese Empfehlungen erfordern, dass Ihre Benutzer moderne e-Mail-Clients verwenden, einschließlich Outlook für IOS und Android auf mobilen Geräten. Outlook für IOS und Android bieten Unterstützung für die besten Features von Office 365. Diese mobilen Outlook-apps werden außerdem mit Sicherheitsfunktionen entworfen, die die mobile Nutzung unterstützen und mit anderen Microsoft Cloud-Sicherheitsfunktionen zusammenarbeiten. Weitere Informationen finden Sie unter [Outlook für IOS und Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="updating-common-policies-to-include-email"></a>Aktualisieren allgemeiner Richtlinien zum Einschließen von e-Mails

Das folgende Diagramm veranschaulicht die allgemeinen Richtlinien für Identitäts-und Geräte Zugriff und gibt an, welche Richtlinien aktualisiert werden müssen, um e-Mails zu schützen. Beachten Sie das Hinzufügen einer neuen Regel für Exchange Online zum Blockieren von ActiveSync-Clients. Dadurch wird die Verwendung von Outlook Mobile erzwungen.

![Zusammenfassung der Richtlinienaktualisierungen zum Schutz von e-Mails](../media/identity-access-ruleset-mail.png)

Wenn Sie Exchange Online und Outlook in den Bereich der Richtlinien einbezogen haben, wenn Sie Sie eingerichtet haben, müssen Sie nur die neue Richtlinie erstellen, um ActiveSync-Clients zu blockieren. Überprüfen Sie die in der folgenden Tabelle aufgeführten Richtlinien, und nehmen Sie entweder die empfohlenen Ergänzungen vor, oder bestätigen Sie, dass diese bereits enthalten sind. Jede Regel enthält Links zu den zugehörigen Konfigurationsanweisungen im Artikel [Allgemeine Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md) .

|Schutzebene|Richtlinien|Weitere Informationen|
|:---------------|:-------|:----------------|
|**Basisplan**|[MFA erforderlich, wenn das Anmelde Risiko *Mittel* groß oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von Exchange Online in die Zuweisung von Cloud-apps|
|        |[Sperrt Clients, die moderne Authentifizierung nicht unterstützen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Einbeziehen von Exchange Online in die Zuweisung von Cloud-apps|
|        |[Definieren von App-Schutzrichtlinien](identity-access-policies.md#high-risk-users-must-change-password)|Stellen Sie sicher, dass Outlook in der Liste der Apps enthalten ist. Achten Sie darauf, die Richtlinie für jede Plattform (Ios, Android, Windows) zu aktualisieren.|
|        |[Genehmigte apps erfordern](identity-access-policies.md#require-approved-apps)|Einschließen von Exchange Online in die Liste der Cloud-apps|
|        |[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Einschließen von Exchange Online in die Liste der Cloud-apps|
|        |[Blockieren von ActiveSync-Clients](#block-activesync-clients)|Diese neue Richtlinie hinzufügen| 
|**Vertraulich**|[MFA erforderlich, wenn das Anmelde Risiko *niedrig*, *Mittel* oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Einbeziehen von Exchange Online in die Zuweisung von Cloud-apps|
|         |[Erfordern von kompatiblen PCs *und* mobilen Geräten](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Einschließen von Exchange Online in die Liste der Cloud-apps|
|**Hochgradig reguliert**|[*Immer* MFA erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Einbeziehen von Exchange Online in die Zuweisung von Cloud-apps|

## <a name="block-activesync-clients"></a>Blockieren von ActiveSync-Clients

Mit dieser Richtlinie wird verhindert, dass ActiveSync-Clients andere bedingte Zugriffsregeln umgehen. Die Regelkonfiguration gilt nur für ActiveSync-Clients. Wenn Sie die Option **genehmigte Client-App anfordern**auswählen, blockiert diese Richtlinie ActiveSync-Clients. So konfigurieren Sie diese Richtlinie:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen Sie **apps auswählen**aus, wählen Sie **Office 365 Exchange Online**aus. Wählen **Sie auswählen** und **Fertig**aus.

8. Wählen Sie **Bedingungen**aus, und wählen Sie dann **Client-apps**aus.

9. Wählen Sie für **configure**die Option **Ja**aus. Überprüfen Sie nur Folgendes: **Mobile Apps und Desktop Clients** und **Exchange ActiveSync-Clients**. Klicken Sie auf **Fertig**.

10. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

11. Wählen Sie **Zugriff gewähren**aus, wählen Sie **genehmigte Client-App anfordern**aus.  Wählen Sie für mehrere Steuerelemente **die Option ausgewählte Steuerelemente erfordern**aus, und wählen Sie dann **auswählen**aus.

12. Klicken Sie auf **Erstellen**.

## <a name="setup-office-365-message-encryption"></a>Einrichten Office 365 Nachrichtenverschlüsselung

Mit den neuen Funktionen für die Office 365 Nachrichtenverschlüsselung (OM), die die Schutzfunktionen in Azure Information Protection nutzen, kann Ihre Organisation problemlos geschützte e-Mails für alle Benutzer auf jedem Gerät freigeben. Benutzer können mit Outlook.com, Gmail und anderen e-Mail-Diensten geschützte Nachrichten mit anderen Office 365 Organisationen sowie nicht-Office 365-Kunden senden und empfangen.

Weitere Informationen finden Sie unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e).

## <a name="next-steps"></a>Nächste Schritte

[Weitere Informationen zu Richtlinienempfehlungen zum Schutz von SharePoint-Websites und -Dokumenten](sharepoint-file-access-policies.md)
