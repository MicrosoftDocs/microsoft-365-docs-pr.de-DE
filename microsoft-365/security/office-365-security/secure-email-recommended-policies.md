---
title: Empfohlene Richtlinien für sichere E-Mails – Microsoft 365 unternehmensweite | Microsoft Docs
description: Beschreibt die Richtlinien für Empfehlungen von Microsoft zur Anwendung von E-Mail-Richtlinien und -Konfigurationen.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: c5f5837f4e4069a67bc080178fefd10bd2a08629
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599851"
---
# <a name="policy-recommendations-for-securing-email"></a>Richtlinienempfehlungen für sichere E-Mails

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)

In diesem Artikel wird beschrieben, wie Sie die empfohlenen Identitäts- und Gerätezugriffsrichtlinien implementieren, um E-Mail- und E-Mail-Clients der Organisation zu schützen, die moderne Authentifizierung und bedingten Zugriff unterstützen. Diese Anleitung baut auf den [Allgemeinen Identitäts- und](identity-access-policies.md) Gerätezugriffsrichtlinien auf und enthält auch einige zusätzliche Empfehlungen.

Diese Empfehlungen basieren auf drei verschiedenen Sicherheits- und Schutzebenen, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können: **Basisplan,** vertraulich und streng **reguliert.** Weitere Informationen zu den Sicherheitsebenen und den empfohlenen Clientbetriebssystemen, auf die hier verwiesen wird, finden Sie in der [Einführung zu den empfohlenen Sicherheitsrichtlinien und -konfigurationen](microsoft-365-policies-configurations.md).

Diese Empfehlungen erfordern, dass Ihre Benutzer moderne E-Mail-Clients verwenden, einschließlich Outlook für iOS und Android auf mobilen Geräten. Outlook für iOS und Android bieten Unterstützung für die besten Features von Office 365. Diese mobilen Outlook sind auch mit Sicherheitsfunktionen entworfen, die die mobile Nutzung unterstützen und mit anderen Microsoft Cloud Security-Funktionen zusammenarbeiten. Weitere Informationen finden Sie unter [Outlook für iOS und Android FAQ](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="update-common-policies-to-include-email"></a>Aktualisieren gängiger Richtlinien auf E-Mails

Zum Schutz von E-Mails zeigt das folgende Diagramm, welche Richtlinien aus den allgemeinen Identitäts- und Gerätezugriffsrichtlinien aktualisiert werden.

[![Zusammenfassung der Richtlinienupdates zum Schutz des Zugriffs auf Teams und deren abhängige Dienste](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Beachten Sie, dass eine neue Richtlinie zum Blockieren Exchange Online ActiveSync-Clients hinzu kommt. Dadurch wird die Verwendung von Outlook erzwingt.

Wenn Sie Exchange Online und Outlook in den Bereich der Richtlinien einbezogen haben, müssen Sie nur die neue Richtlinie zum Blockieren von ActiveSync-Clients erstellen. Überprüfen Sie die in der folgenden Tabelle aufgeführten Richtlinien, und nehmen Sie entweder die empfohlenen Ergänzungen vor, oder vergewissern Sie sich, dass diese bereits enthalten sind. Jede Richtlinie verknüpft sich mit den zugehörigen Konfigurationsanweisungen unter [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md).

|Schutzebene|Richtlinien|Weitere Informationen|
|---|---|---|
|**Basisplan**|[MFA erforderlich, wenn das Anmelderisiko *mittel oder* hoch *ist*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Hinzufügen Exchange Online in die Zuweisung von Cloud-Apps|
||[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Hinzufügen Exchange Online in die Zuweisung von Cloud-Apps|
||[Anwenden von APP-Datenschutzrichtlinien](identity-access-policies.md#apply-app-data-protection-policies)|Stellen Sie sicher, Outlook in der Liste der Apps enthalten ist. Aktualisieren Sie die Richtlinie für jede Plattform (iOS, Android, Windows)|
||[Benötigen genehmigter Apps und APP-Schutz](identity-access-policies.md#require-approved-apps-and-app-protection)|Hinzufügen Exchange Online in die Liste der Cloud-Apps|
||[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Hinzufügen Exchange Online in die Liste der Cloud-Apps|
||[Blockieren von ActiveSync-Clients](#block-activesync-clients)|Hinzufügen dieser neuen Richtlinie|
|**Vertraulich**|[MFA erforderlich, wenn das Anmelderisiko *niedrig,* *mittel oder* hoch *ist*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Hinzufügen Exchange Online in die Zuweisung von Cloud-Apps|
||[Erfordern kompatibler PCs *und* mobiler Geräte](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Hinzufügen Exchange Online in die Liste der Cloud-Apps|
|**Streng geregelt**|[*MFA* immer erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Hinzufügen Exchange Online in die Zuweisung von Cloud-Apps|
|

## <a name="block-activesync-clients"></a>Blockieren von ActiveSync-Clients

Diese Richtlinie verhindert, dass ActiveSync-Clients andere Richtlinien für bedingten Zugriff umgehen. Die Richtlinienkonfiguration gilt nur für ActiveSync-Clients. Durch Auswählen **[der Option App-Schutzrichtlinie erforderlich](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** blockiert diese Richtlinie ActiveSync-Clients. Details zum Erstellen dieser Richtlinie finden Sie unter [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

- Folgen Sie "Schritt 2: Konfigurieren einer Azure AD-Richtlinie für bedingten Zugriff für Exchange Online mit ActiveSync (EAS)" in Szenario [1: Office 365-Apps](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)benötigen genehmigte Apps mit App-Schutzrichtlinien, wodurch verhindert wird, dass Exchange ActiveSync-Clients die Standardauthentifizierung nutzen, um eine Verbindung mit Exchange Online.

Sie können auch Authentifizierungsrichtlinien verwenden, um [die Standardauthentifizierung](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)zu deaktivieren, wodurch alle Clientzugriffsanforderungen die moderne Authentifizierung verwenden müssen.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Einschränken des Zugriffs auf Exchange Online von Outlook im Web

Sie können die Möglichkeit für Benutzer einschränken, Anlagen aus Outlook auf umnanaged-Geräten herunterzuladen. Benutzer auf diesen Geräten können diese Dateien mit Office Online anzeigen und bearbeiten, ohne die Dateien auf dem Gerät zu übertragen und zu speichern. Sie können auch blockieren, dass Benutzer Anlagen auf einem nicht verwalteten Gerät sehen.

Die Schritte sind hier aufgeführt:

1. [Verbinden zu einer Exchange Online Remote PowerShell-Sitzung .](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
2. Wenn Sie noch nicht über eine OWA-Postfachrichtlinie verfügen, erstellen Sie eine mit dem [Cmdlet New-OwaMailboxPolicy.](/powershell/module/exchange/new-owamailboxpolicy)
3. Wenn Sie die Anzeige von Anlagen zulassen möchten, aber keinen Download ausführen möchten, verwenden Sie diesen Befehl:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Wenn Sie Anlagen blockieren möchten, verwenden Sie diesen Befehl:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Erstellen Sie im Azure-Portal eine neue Richtlinie für bedingten Zugriff mit den folgenden Einstellungen:

   **Zuordnungen** \> **Benutzer und Gruppen:** Wählen Sie geeignete Benutzer und Gruppen aus, die sie ein- und ausschließen möchten.

   **Zuordnungen** \> **Cloud-Apps oder -Aktionen** \> **Cloud-Apps** \> **Include** \> **Apps auswählen:** Wählen **Sie Office 365 Exchange Online**

   **Zugriffssteuerelemente** \> **Sitzung**: Select **Use app enforced restrictions**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Fordern Sie an, dass iOS- und Android-Geräte Outlook

Um sicherzustellen, dass Benutzer von iOS- und Android-Geräten nur über Outlook für iOS und Android auf Arbeits- oder Schulinhalte zugreifen können, benötigen Sie eine Richtlinie für bedingten Zugriff für diese potenziellen Benutzer.

Weitere Informationen zum Konfigurieren dieser Richtlinie finden Sie unter Verwalten des Zugriffs auf die Messagingzusammenarbeit mithilfe von [Outlook für iOS und Android](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).

## <a name="set-up-message-encryption"></a>Einrichten der Nachrichtenverschlüsselung

Mit den neuen Office 365-Nachrichtenverschlüsselung (OME)-Funktionen, die die Schutzfunktionen in Azure Information Protection nutzen, kann Ihre Organisation geschützte E-Mails problemlos für jeden Benutzer auf jedem Gerät freigeben. Benutzer können geschützte Nachrichten über Outlook.com, Gmail und andere E-Mail-Dienste Microsoft 365 Organisationen sowie Nichtkunden senden und empfangen.

Weitere Informationen finden Sie unter [Einrichten neuer Office 365-Nachrichtenverschlüsselung Funktionen](../../compliance/set-up-new-message-encryption-capabilities.md).

## <a name="next-steps"></a>Nächste Schritte

![Schritt 4: Richtlinien für Microsoft 365 Cloud-Apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurieren von Richtlinien für bedingten Zugriff für:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
