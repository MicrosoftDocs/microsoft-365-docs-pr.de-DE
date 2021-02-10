---
title: Empfohlene Richtlinien für sichere E-Mails – Microsoft 365 Enterprise | Microsoft Docs
description: Beschreibt die Richtlinien für Empfehlungen von Microsoft zur Anwendung von E-Mail-Richtlinien und -Konfigurationen.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 653b16b7b3f6637440e3740830ffe9f9a51c6dd8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166507"
---
# <a name="policy-recommendations-for-securing-email"></a>Richtlinienempfehlungen für sichere E-Mails

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)


In diesem Artikel wird beschrieben, wie Sie die empfohlenen Identitäts- und Gerätezugriffsrichtlinien implementieren, um E-Mail- und E-Mail-Clients der Organisation zu schützen, die moderne Authentifizierung und bedingten Zugriff unterstützen. Dieser Leitfaden basiert auf den [allgemeinen Identitäts- und](identity-access-policies.md) Gerätezugriffsrichtlinien und enthält auch einige zusätzliche Empfehlungen.

Diese Empfehlungen basieren auf drei verschiedenen Sicherheits- und Schutzebenen, die basierend auf der Granularität Ihrer Anforderungen angewendet werden **können:** **Basisplan,** vertraulich und hochgradig **reguliert.** Weitere Informationen zu den Sicherheitsebenen und den empfohlenen Clientbetriebssystemen, auf die hier verwiesen wird, finden Sie in der [Einführung zu den empfohlenen Sicherheitsrichtlinien und -konfigurationen](microsoft-365-policies-configurations.md).

Diese Empfehlungen erfordern, dass Ihre Benutzer moderne E-Mail-Clients verwenden, einschließlich Outlook für iOS und Android auf mobilen Geräten. Outlook für iOS und Android bietet Unterstützung für die besten Features von Office 365. Diese mobilen Outlook-Apps sind auch mit Sicherheitsfunktionen entworfen, die die mobile Verwendung unterstützen und mit anderen Microsoft Cloud Security Funktionen zusammenarbeiten. Weitere Informationen finden Sie unter Häufig gestellte Fragen zu [Outlook für iOS und Android.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)

## <a name="update-common-policies-to-include-email"></a>Aktualisieren gängiger Richtlinien mit E-Mails

Zum Schutz von E-Mails zeigt das folgende Diagramm, welche Richtlinien anhand der allgemeinen Identitäts- und Gerätezugriffsrichtlinien aktualisiert werden müssen.

[![Zusammenfassung der Richtlinienupdates zum Schutz des Zugriffs auf Teams und seine abhängigen Dienste](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[Sehen Sie sich eine größere Version dieses Bilds an.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Beachten Sie, dass eine neue Richtlinie für Exchange Online zum Blockieren von ActiveSync-Clients hinzu kommt. Dadurch wird die Verwendung von Outlook Mobile erzwingt.

Wenn Sie Exchange Online und Outlook beim Einrichten in den Bereich der Richtlinien aufgenommen haben, müssen Sie nur die neue Richtlinie erstellen, um die ActiveSync-Clients zu blockieren. Überprüfen Sie die in der folgenden Tabelle aufgeführten Richtlinien, und nehmen Sie die empfohlenen Ergänzungen vor, oder vergewissern Sie sich, dass diese bereits enthalten sind. Jede Richtlinie ist mit den zugehörigen Konfigurationsanweisungen in [allgemeinen Identitäts- und Gerätezugriffsrichtlinien verknüpft.](identity-access-policies.md)

|Schutzebene|Richtlinien|Weitere Informationen|
|---|---|---|
|**Basisplan**|[MFA erforderlich, wenn das Anmelderisiko *mittel oder* hoch *ist*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Hinzufügen von Exchange Online in die Zuweisung von Cloud-Apps|
||[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Hinzufügen von Exchange Online in die Zuweisung von Cloud-Apps|
||[Anwenden von APP-Datenschutzrichtlinien](identity-access-policies.md#apply-app-data-protection-policies)|Stellen Sie sicher, dass Outlook in der Liste der Apps enthalten ist. Achten Sie darauf, die Richtlinie für jede Plattform (iOS, Android, Windows) zu aktualisieren.|
||[Erfordert genehmigte Apps und app-Schutz](identity-access-policies.md#require-approved-apps-and-app-protection)|Hinzufügen von Exchange Online in die Liste der Cloud-Apps|
||[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Hinzufügen von Exchange Online in die Liste der Cloud-Apps|
||[Blockieren von ActiveSync-Clients](#block-activesync-clients)|Hinzufügen dieser neuen Richtlinie|
|**Vertraulich**|[MFA erforderlich, wenn das Anmelderisiko *niedrig,* *mittel oder* *hoch ist*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Hinzufügen von Exchange Online in die Zuweisung von Cloud-Apps|
||[Kompatible *PCs* und mobile Geräte erforderlich](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Hinzufügen von Exchange Online in die Liste der Cloud-Apps|
|**Streng geregelt**|[*MFA* immer erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Hinzufügen von Exchange Online in die Zuweisung von Cloud-Apps|
|

## <a name="block-activesync-clients"></a>Blockieren von ActiveSync-Clients

Diese Richtlinie hindert ActiveSync-Clients daran, andere Richtlinien für bedingten Zugriff zu umgehen. Die Richtlinienkonfiguration gilt nur für ActiveSync-Clients. Durch Die Auswahl **[der Richtlinie "App-Schutz erforderlich"](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** blockiert diese Richtlinie ActiveSync-Clients. Details zum Erstellen dieser Richtlinie finden Sie unter "App-Schutzrichtlinie erforderlich" für den [Cloud-App-Zugriff mit bedingten Zugriff.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)

- Folgen Sie "Schritt 2: Konfigurieren einer Azure AD-Richtlinie für bedingten Zugriff für Exchange Online mit ActiveSync (EAS)" in Szenario [1: Office 365-Apps](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)erfordern genehmigte Apps mit App-Schutzrichtlinien, die Exchange ActiveSync-Clients, die die Standardauthentifizierung nutzen, daran hindert, eine Verbindung mit Exchange Online zu herstellen.

Sie können auch Authentifizierungsrichtlinien verwenden, um die [Standardauthentifizierung](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)zu deaktivieren, wodurch alle Clientzugriffsanforderungen zur Verwendung der modernen Authentifizierung erzwingt werden.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Einschränken des Zugriffs auf Exchange Online aus Outlook im Web

Sie können die Möglichkeit für Benutzer einschränken, Anlagen von Outlook im Web auf umnanageten Geräten herunterzuladen. Benutzer auf diesen Geräten können diese Dateien mit Office Online anzeigen und bearbeiten, ohne die Dateien auf dem Gerät zu übertragen und zu speichern. Sie können auch blockieren, dass Benutzern Anlagen auf einem nicht verwalteten Gerät angezeigt werden.

Die Schritte sind hier aufgeführt:

1. [Stellen Sie eine Verbindung mit einer Exchange Online Remote -PowerShell-Sitzung.](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
2. Wenn Sie noch keine OWA-Postfachrichtlinie haben, erstellen Sie eine mit dem [Cmdlet "New-OwaMailboxPolicy".](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)
3. Wenn Sie das Anzeigen von Anlagen, aber kein Herunterladen zulassen möchten, verwenden Sie diesen Befehl:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Wenn Sie Anlagen blockieren möchten, verwenden Sie diesen Befehl:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Erstellen Sie im Azure-Portal eine neue Richtlinie für bedingten Zugriff mit den folgenden Einstellungen:

   **Zuordnungen** \> **Benutzer und Gruppen:** Wählen Sie die geeigneten Benutzer und Gruppen aus, um sie ein- und auszuschließen.

   **Zuordnungen** \> **Cloud-Apps oder -Aktionen** \> **Cloud-Apps** \> **Include** \> **Auswählen von Apps:** **Auswählen von Office 365 Exchange Online**

   **Zugriffssteuerungen** \> **Sitzung:** Auswählen von **erzwungenen Einschränkungen für die App verwenden**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Erfordern, dass iOS- und Android-Geräte Outlook verwenden müssen

Um sicherzustellen, dass Benutzer von iOS- und Android-Geräten nur mit Outlook für iOS und Android auf Arbeits- oder Schulinhalte zugreifen können, benötigen Sie eine Richtlinie für bedingten Zugriff für diese potenziellen Benutzer.

Informationen zum Konfigurieren dieser Richtlinie finden Sie unter "Verwalten des Zugriffs auf die [Messagingzusammenarbeit mithilfe von Outlook für iOS und Android".]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)

## <a name="set-up-message-encryption"></a>Einrichten der Nachrichtenverschlüsselung

Mit den neuen Funktionen der Office 365-Nachrichtenverschlüsselung (Office 365 Message Encryption, OME), die die Schutzfunktionen in Azure Information Protection nutzen, kann Ihre Organisation geschützte E-Mails problemlos für alle Benutzer auf jedem Gerät freigeben. Benutzer können geschützte Nachrichten mit anderen Microsoft 365-Organisationen und Nicht-Kunden senden und empfangen, die Outlook.com, Gmail und andere E-Mail-Dienste verwenden.

Weitere Informationen finden Sie unter [Einrichten der neuen Office 365-Nachrichtenverschlüsselungsfunktionen.](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)

## <a name="next-steps"></a>Nächste Schritte

![Schritt 4: Richtlinien für Microsoft 365-Cloud-Apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurieren Sie Richtlinien für bedingten Zugriff für:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
