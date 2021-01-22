---
title: Identitäts- und Gerätezugriffsrichtlinien zum Zulassen des Gast- und externen Benutzerzugriffs – Microsoft 365 Enterprise | Microsoft Docs
description: Beschreibt die empfohlenen Richtlinien für bedingten Zugriff und verwandte Richtlinien zum Schutz des Zugriffs von Gästen und externen Benutzern.
ms.prod: m365-security
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
ms.technology: mdo
ms.openlocfilehash: 2ef494f8e383f50f16b1e64f6387b6e5d62459c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932610"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Richtlinien zum Zulassen des Gastzugriffs und des externen B2B-Benutzerzugriffs

In diesem Artikel wird das Anpassen der empfohlenen Geräte- und Identitätszugriffsrichtlinien erläutert, um Den Zugriff für Gäste und externe Benutzer zu ermöglichen, die über ein Azure Active Directory (Azure AD) Business-to-Business (B2B)-Konto verfügen. Diese Anleitung basiert auf den [allgemeinen Identitäts- und Gerätezugriffsrichtlinien.](identity-access-policies.md)

Diese Empfehlungen gelten für die **grundlegende** Schutzebene. Sie können die Empfehlungen jedoch auch basierend auf Ihren spezifischen Anforderungen für den Schutz **vertraulicher** und **streng regulierter Daten** anpassen.

Wenn Sie einen Pfad für B2B-Konten zur Authentifizierung bei Ihrem Azure AD-Mandanten bereitstellen, erhalten diese Konten keinen Zugriff auf Ihre gesamte Umgebung. Benutzer von B2B und deren Konten haben Zugriff auf Dienste und Ressourcen, z. B. Dateien, die durch die Richtlinie für bedingten Zugriff für sie freigegeben werden.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Aktualisieren der allgemeinen Richtlinien zum Zulassen und Schützen von Gästen und externem Benutzerzugriff

Dieses Diagramm zeigt, welche Richtlinien zwischen den allgemeinen Identitäts- und Gerätezugriffsrichtlinien für den B2B-Gast- und externen Benutzerzugriff hinzugefügt oder aktualisiert werden müssen.

[![Zusammenfassung der Richtlinienupdates zum Schutz des Gastzugriffs](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Sehen Sie sich eine größere Version dieses Bilds an.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

In der folgenden Tabelle sind die Richtlinien aufgeführt, die Sie entweder erstellen und aktualisieren müssen. Die allgemeinen Richtlinien sind mit den zugehörigen Konfigurationsanweisungen im Artikel ["Allgemeine Identitäts- und Gerätezugriffsrichtlinien"](identity-access-policies.md) verknüpft.

|Schutzebene|Richtlinien|Weitere Informationen|
|---|---|---|
|**Basisplan**|[MFA immer für Gäste und externe Benutzer erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Erstellen Sie diese neue Richtlinie, und konfigurieren Sie: <ul><li>For **Assignments > Users and groups > Include**, choose Select users and **groups,** and then select All guest and external **users**.</li><li>Lassen **Sie für > A0**> A0 alle Optionen deaktiviert, um die mehrstufige Authentifizierung (MFA) immer zu erzwingen.</li></ul>|
||[MFA erforderlich, wenn das Anmelderisiko *mittel oder* hoch *ist*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ändern Sie diese Richtlinie, um Gäste und externe Benutzer auszuschließen.|
||[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ändern Sie diese Richtlinie, um Gäste und externe Benutzer auszuschließen.|

Wenn Sie Gäste und externe Benutzer in Richtlinien für bedingten Zugriff ein- oder ausschließen möchten, aktivieren Sie für Aufgaben > Benutzer und Gruppen **> Ein-** oder Ausschließen alle Gast- und **externen Benutzer.**

![Bildschirmaufnahme von Steuerelementen für das Ausschließen von Gästen und externen Benutzern](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Weitere Informationen

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Zugriff auf Gäste und externe Benutzer mit Microsoft Teams

Microsoft Teams definiert die folgenden Benutzer:

- **Gastzugriff** verwendet ein Azure AD B2B-Konto, das als Mitglied eines Teams hinzugefügt werden kann und Zugriff auf die Kommunikation und die Ressourcen des Teams hat.

- **Der externe** Zugriff ist für einen externen Benutzer ohne ein B2B-Konto. Der Zugriff durch externe Benutzer umfasst Einladungen, Anrufe, Chats und Besprechungen, umfasst jedoch keine Teammitgliedschaft und keinen Zugriff auf die Ressourcen des Teams.

Weitere Informationen finden Sie im Vergleich zwischen Gästen und [externem Benutzerzugriff für Teams.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)

Weitere Informationen zum Sichern von Identitäts- und Gerätezugriffsrichtlinien für Teams finden Sie unter Richtlinienempfehlungen zum Sichern von [Teams-Chats,](teams-access-policies.md)-Gruppen und -Dateien.

### <a name="require-mfa-always-for-guest-and-external-users"></a>MFA immer für Gastbenutzer und externe Benutzer erforderlich

Diese Richtlinie fordert Gäste auf, sich für MFA in Ihrem Mandanten zu registrieren, unabhängig davon, ob sie für MFA in ihrem Home-Mandanten registriert sind. Beim Zugriff auf Ressourcen in Ihrem Mandanten müssen Gäste und externe Benutzer MFA für jede Anforderung verwenden.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Ausschließen von Gästen und externen Benutzern von risikobasierten MFA

Während Organisationen risikobasierte Richtlinien für B2B-Benutzer mithilfe von Azure AD Identity Protection erzwingen können, gibt es aufgrund ihrer in ihrem Startverzeichnis vorhandenen Identität Einschränkungen bei der Implementierung von Azure AD Identity Protection für Benutzer der B2B-Zusammenarbeit in einem Ressourcenverzeichnis. Aufgrund dieser Einschränkungen empfiehlt Microsoft, Gäste von risikobasierten Richtlinien für MFA auszuschließen und von diesen Benutzern die Verwendung von MFA zu verlangen.

Weitere Informationen finden Sie unter ["Einschränkungen des Identitätsschutzes für Benutzer der B2B-Zusammenarbeit".](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)

### <a name="excluding-guests-and-external-users-from-device-management"></a>Ausschließen von Gästen und externen Benutzern aus der Geräteverwaltung

Nur eine Organisation kann ein Gerät verwalten. Wenn Sie Gäste und externe Benutzer nicht von Richtlinien ausschließen, die Gerätekonformität erfordern, blockieren diese Richtlinien diese Benutzer.

## <a name="next-step"></a>Nächster Schritt

![Schritt 4: Richtlinien für Microsoft 365-Cloud-Apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurieren Sie Richtlinien für bedingten Zugriff für:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
