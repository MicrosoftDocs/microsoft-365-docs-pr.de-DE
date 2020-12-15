---
title: Identitäts-und Gerätezugriffs Richtlinien für das Zulassen von Gast-und externem B2B-Zugriff – Microsoft 365 für Unternehmen | Microsoft-Dokumente
description: Beschreibt den empfohlenen bedingten Zugriff und verwandte Richtlinien zum Schützen des Zugriffs von Gast-und externen Benutzern.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: c2c01278831433c02e5c869dba83f223eea57d27
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683235"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Richtlinien für das Zulassen von Gast-und externen B2B-Zugriff

In diesem Artikel wird beschrieben, wie Sie die empfohlenen allgemeinen Identitäts-und Gerätezugriffs Richtlinien anpassen können, um den Zugriff für Gast-und externe Benutzer zuzulassen, die über ein Business-to-Business-Konto (B2B) von Azure Active Directory (Azure AD) verfügen. Dieser Leitfaden basiert auf den [allgemeinen Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md).

Diese Empfehlungen sind darauf ausgelegt, auf die **grundlegende** Schutzebene anzuwenden. Sie können jedoch auch die Empfehlungen basierend auf der Granularität Ihrer Anforderungen für **sensiblen** und **streng reglementierten** Schutz anpassen.

Durch die Bereitstellungeines Pfads für B2B-Konten zur Authentifizierung bei Ihrem Azure AD Mandanten erhalten diese Konten keinen Zugriff auf Ihre gesamte Umgebung. B2B-Benutzer und ihre Konten haben nur Zugriff auf Ressourcen, die für Sie (beispielsweise Dateien) innerhalb der in bedingten Zugriffsrichtlinien gewährten Dienste freigegeben werden.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Aktualisieren der allgemeinen Richtlinien zum zulassen und schützen von Gast und externem Zugriff

Um Gast-und externen Zugriff mit Azure AD B2B-Konten zu schützen, zeigt das folgende Diagramm, welche Richtlinien hinzugefügt oder von den allgemeinen Richtlinien für Identitäts-und Geräte Zugriff aktualisiert werden sollen.

[![Zusammenfassung der Richtlinienupdates zum Schützen des Gastzugriffs](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Anzeigen einer größeren Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

In der folgenden Tabelle sind die Richtlinien aufgeführt, die Sie entweder erstellen und aktualisieren müssen. Die allgemeinen Richtlinien verweisen auf die zugehörigen Konfigurationsanweisungen im Artikel [Allgemeine Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md) .

|Schutzebene|Richtlinien|Weitere Informationen|
|---|---|---|
|**Basisplan**|[MFA immer für Gast und externe Benutzer erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Erstellen Sie diese neue Richtlinie, und konfigurieren Sie Folgendes: <ul><li> Wählen Sie für **Zuordnungen > Benutzer und Gruppen > einschließen** die **Option Benutzer und Gruppen auswählen** aus, und wählen Sie dann **alle Gast-und externen Benutzer** aus. </li><li> Lassen Sie für **Zuordnungen > Bedingungen > Anmeldung** die Option Alle Optionen deaktiviert, damit die mehrstufige Authentifizierung (MFA) immer erzwungen wird.</li>|
||[MFA erforderlich, wenn das Anmelde Risiko *Mittel* groß oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ändern Sie diese Richtlinie, um Gast-und externe Benutzer auszuschließen.|
||[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ändern Sie diese Richtlinie, um Gast-und externe Benutzer auszuschließen.|

Wenn Sie Gast-und externe Benutzer in Richtlinien für den bedingten Zugriff einbeziehen oder ausschließen möchten, überprüfen Sie für **Zuordnungen > Benutzer und Gruppen, die > einschließen** oder **ausschließen**, **alle Gast-und externen Benutzer**.

![Bildschirmaufzeichnung von Steuerelementen zum Ausschließen von Gast-und externen Benutzern](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Weitere Informationen

### <a name="guest-and-external-access-with-microsoft-teams"></a>Gast-und externer Zugriff mit Microsoft Teams

Microsoft Teams definiert Folgendes:

- **Gastzugriff** verwendet ein Azure AD B2B-Konto, das als Mitglied eines Teams hinzugefügt werden kann und über alle Berechtigungen für den Zugriff auf die Kommunikation und die Ressourcen des Teams verfügt.

- **Externer Zugriff** ist für einen externen Benutzer, der über kein B2B-Konto verfügt. Externer Zugriff kann Einladungen und Teilnahme an anrufen, Chats und Besprechungen umfassen, umfasst jedoch nicht die Teammitgliedschaft und den Zugriff auf die Ressourcen des Teams.

Weitere Informationen finden Sie unter [Vergleich zwischen Gast und externem Zugriff für Teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).

Weitere Informationen zum Sichern von Identitäts-und Gerätezugriffs Richtlinien für Teams finden Sie unter [Richtlinien Empfehlungen für das Sichern von teamchats, Gruppen und Dateien](teams-access-policies.md) .

### <a name="require-mfa-always-for-guest-and-external-users"></a>MFA immer für Gast und externe Benutzer erforderlich

Diese Richtlinie fordert Gäste auf, sich für MFA in Ihrem Mandanten zu registrieren, unabhängig davon, ob Sie für MFA in Ihrem Wohnsitz Mandanten registriert sind. Beim Zugriff auf Ressourcen in Ihrem Mandanten müssen Gast-und externe Benutzer MFA für jede Anforderung verwenden.

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Ausschließen von Gast-und externen Benutzern aus risikobasierter MFA

Während Organisationen risikobasierte Richtlinien für B2B-Benutzer mithilfe Azure AD Identitätsschutzes erzwingen können, gibt es Einschränkungen bei der Implementierung von Azure AD Identity Protection für Benutzer der B2B-Zusammenarbeit in einem Ressourcenverzeichnis, da ihre Identität in Ihrem Basisverzeichnis vorhanden ist. Aufgrund dieser Einschränkungen empfiehlt Microsoft, Gastbenutzer von risikobasierten MFA-Richtlinien auszuschließen, und diese Benutzer müssen immer MFA verwenden.

Weitere Informationen finden Sie unter [Einschränkungen des Identitätsschutzes für Benutzer in der B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).

### <a name="excluding-guest-and-external-users-from-device-management"></a>Ausschließen von Gast-und externen Benutzern aus der Geräteverwaltung

Nur eine Organisation kann ein Gerät verwalten. Wenn Sie Gast-und externe Benutzer nicht von Richtlinien ausschließen, die die Gerätekompatibilität erfordern, werden diese Benutzer durch diese Richtlinien blockiert.

## <a name="next-step"></a>Nächster Schritt

![Schritt 4: Richtlinien für Microsoft 365 Cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurieren von Richtlinien für bedingten Zugriff für:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
