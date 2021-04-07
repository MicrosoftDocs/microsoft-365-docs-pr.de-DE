---
title: Identitäts- und Gerätezugriffsrichtlinien zum Zulassen des B2B-Zugriffs für Gastbenutzer und externe Benutzer – Microsoft 365 for Enterprise | Microsoft Docs
description: Beschreibt die empfohlenen Richtlinien für bedingten Zugriff und verwandte Richtlinien zum Schutz des Zugriffs von Gästen und externen Benutzern.
ms.prod: m365-security
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
audience: Admin
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
ms.technology: mdo
ms.openlocfilehash: 4ce52c40e622f55b0fd231ec634c4897fea1d6f5
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615495"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Richtlinien zum Zulassen des Gastzugriffs und des externen B2B-Zugriffs durch B2B

In diesem Artikel wird die Anpassung der empfohlenen Geräte- und Identitätszugriffsrichtlinien erläutert, um Gästen und externen Benutzern, die über ein Azure Active Directory (Azure AD) Business-to-Business (B2B)-Konto verfügen, zugriff zu ermöglichen. Diese Anleitung baut auf den [allgemeinen Identitäts- und Gerätezugriffsrichtlinien auf.](identity-access-policies.md)

Diese Empfehlungen sind so konzipiert, dass sie auf die **Basisebene** des Schutzes angewendet werden. Sie können die Empfehlungen jedoch auch an Ihre spezifischen Anforderungen für den **vertraulichen** und streng **regulierten Schutz** anpassen.

Wenn Sie einen Pfad für B2B-Konten zur Authentifizierung bei Ihrem Azure AD-Mandanten bereitstellen, erhalten diese Konten keinen Zugriff auf Ihre gesamte Umgebung. B2B-Benutzer und ihre Konten haben Zugriff auf Dienste und Ressourcen, z. B. Dateien, die ihnen von der Richtlinie für bedingten Zugriff zur Verfügung stehen.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Aktualisieren der allgemeinen Richtlinien zum Zulassen und Schützen von Gästen und externem Benutzerzugriff

Dieses Diagramm zeigt, welche Richtlinien zwischen den allgemeinen Identitäts- und Gerätezugriffsrichtlinien für B2B-Gast- und externen Benutzerzugriff hinzugefügt oder aktualisiert werden.

[![Zusammenfassung der Richtlinienupdates zum Schutz des Gastzugriffs](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

In der folgenden Tabelle sind die Richtlinien aufgeführt, die Sie entweder erstellen und aktualisieren müssen. Die allgemeinen Richtlinien verknüpfen mit den zugehörigen Konfigurationsanweisungen im Artikel [Allgemeine Identitäts- und Gerätezugriffsrichtlinien.](identity-access-policies.md)

|Schutzebene|Richtlinien|Weitere Informationen|
|---|---|---|
|**Basisplan**|[MFA immer für Gäste und externe Benutzer benötigen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Erstellen Sie diese neue Richtlinie, und konfigurieren Sie: <ul><li>Wählen **Sie für > Benutzer** und Gruppen > Include die Option Benutzer und Gruppen auswählen aus, und wählen Sie dann Alle gast- und externen Benutzer **aus.** </li><li>Lassen **Sie für > Bedingungen > Anmeldung** alle Optionen deaktiviert, um die mehrstufige Authentifizierung (MFA) immer zu erzwingen.</li></ul>|
||[MFA erforderlich, wenn das Anmelderisiko *mittel oder* hoch *ist*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ändern Sie diese Richtlinie, um Gäste und externe Benutzer auszuschließen.|
||[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ändern Sie diese Richtlinie, um Gäste und externe Benutzer auszuschließen.|

Um Gäste und externe Benutzer in Richtlinien für bedingten Zugriff ein- oder auszuschließen, aktivieren Sie für **Zuordnungen >** Benutzer und Gruppen > Include or **Exclude** alle Gast- und **externe Benutzer**.

![Bildschirmaufnahme von Steuerelementen für das Ausschließen von Gästen und externen Benutzern](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Weitere Informationen

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Gast- und externer Benutzerzugriff mit Microsoft Teams

Microsoft Teams definiert die folgenden Benutzer:

- **Der Gastzugriff** verwendet ein Azure AD B2B-Konto, das als Mitglied eines Teams hinzugefügt werden kann und Zugriff auf die Kommunikation und Ressourcen des Teams hat.

- **Der externe Zugriff** ist für einen externen Benutzer ohne B2B-Konto. Der externe Benutzerzugriff umfasst Einladungen, Anrufe, Chats und Besprechungen, umfasst jedoch keine Teammitgliedschaft und keinen Zugriff auf die Ressourcen des Teams.

Weitere Informationen finden Sie im [Vergleich zwischen Gästen und externem Benutzerzugriff für Teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).

Weitere Informationen zum Schützen von Identitäts- und Gerätezugriffsrichtlinien für Teams finden Sie unter Richtlinienempfehlungen zum Schützen von [Teams-Chats, -Gruppen und -Dateien.](teams-access-policies.md)

### <a name="require-mfa-always-for-guest-and-external-users"></a>MFA immer für Gastbenutzer und externe Benutzer erforderlich

Diese Richtlinie fordert Gäste auf, sich für MFA in Ihrem Mandanten zu registrieren, unabhängig davon, ob sie für MFA in ihrem Home-Mandanten registriert sind. Beim Zugriff auf Ressourcen in Ihrem Mandanten müssen Gäste und externe Benutzer MFA für jede Anforderung verwenden.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Ausschließen von Gästen und externen Benutzern von risikobasierten MFA

Organisationen können zwar risikobasierte Richtlinien für B2B-Benutzer mithilfe von Azure AD Identity Protection erzwingen, es gibt jedoch Einschränkungen bei der Implementierung von Azure AD Identity Protection für Benutzer der B2B-Zusammenarbeit in einem Ressourcenverzeichnis aufgrund ihrer identität, die im Heimverzeichnis vorhanden ist. Aufgrund dieser Einschränkungen empfiehlt Microsoft, Gäste von risikobasierten MFA-Richtlinien auszuschließen und von diesen Benutzern die verwendung von MFA zu verlangen.

Weitere Informationen finden Sie unter [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).

### <a name="excluding-guests-and-external-users-from-device-management"></a>Ausschließen von Gästen und externen Benutzern von der Geräteverwaltung

Nur eine Organisation kann ein Gerät verwalten. Wenn Sie Gäste und externe Benutzer nicht von Richtlinien ausschließen, die Gerätekonformität erfordern, blockieren diese Richtlinien diese Benutzer.

## <a name="next-step"></a>Nächster Schritt

![Schritt 4: Richtlinien für Microsoft 365-Cloud-Apps und Microsoft Cloud App Security](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurieren von Richtlinien für bedingten Zugriff für:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
- [Microsoft Cloud App Security](mcas-saas-access-policies.md)
 