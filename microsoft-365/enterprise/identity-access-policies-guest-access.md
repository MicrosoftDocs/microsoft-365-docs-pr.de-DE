---
title: Identitäts-und Gerätezugriffs Richtlinien für das Zulassen von Gast-und externem B2B-Zugriff – Microsoft 365 Enterprise | Microsoft-Dokumente
description: Beschreibt den empfohlenen bedingten Zugriff und verwandte Richtlinien zum Schützen des Zugriffs von Gast-und externen Benutzern.
author: BrendaCarter
manager: johmar
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
ms.openlocfilehash: ca9b752f55ebe3fecec4f312bc89b45d99cf0d7d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601052"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Richtlinien für das Zulassen von Gast-und externen B2B-Zugriff
In diesem Artikel wird beschrieben, wie Sie die empfohlenen allgemeinen Richtlinien für Identitäts-und Geräte Zugriff anpassen können, um B2B-Konto Zugriff zu ermöglichen (Gast und externe Benutzer). Dieser Leitfaden basiert auf den [allgemeinen Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md).

Diese Empfehlungen sind darauf ausgelegt, auf die **grundlegende** Schutzebene anzuwenden. Sie können die Empfehlungen jedoch auf der Grundlage der Granularität Ihrer Anforderungen für einen **vertraulichen** und **streng reglementierten** Schutz anpassen. 

Durch die Bereitstellungeines Pfads für B2B-Benutzer zur Authentifizierung bei Ihrem Azure AD Mandanten erhalten diese Benutzer keinen Zugriff auf Ihre gesamte Umgebung. B2B-Benutzer haben nur Zugriff auf Ressourcen, die für Sie (beispielsweise Dateien) innerhalb der in den Richtlinien für bedingten Zugriff gewährten Dienste freigegeben werden.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Aktualisieren der allgemeinen Richtlinien zum zulassen und schützen von Gast und externem Zugriff 

Das folgende Diagramm veranschaulicht die allgemeinen Richtlinien für Identitäts-und Geräte Zugriff und gibt (mit einem Bleistiftsymbol) an, welche Richtlinien zum Schutz von Gast und externem Zugriff hinzugefügt oder aktualisiert werden sollen. 

![Zusammenfassung der Richtlinienupdates zum Schützen des Gastzugriffs](../images/identity-access-ruleset-guest.png)

In der folgenden Tabelle sind die Richtlinien aufgeführt, die Sie entweder aktualisieren oder neu erstellen müssen. Die allgemeinen Richtlinien verweisen auf die zugehörigen Konfigurationsanweisungen im Artikel [Allgemeine Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md) .

|Schutzebene|Richtlinien|Weitere Informationen|
|:---------------|:-------|:----------------|
|**Basisplan**|[MFA immer für Gast und externe Benutzer erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Erstellen Sie diese neue Regel, und wenden Sie Sie nur auf Gäste und externe Benutzer an. Lassen Sie unter Anmelde Risiko alle Optionen deaktiviert, damit MFA immer erzwungen wird.|
|        |[MFA erforderlich, wenn das Anmelde Risiko *Mittel* groß oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ändern Sie diese Regel, um Gast-und externe Benutzer auszuschließen.|
|        |[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ändern Sie diese Regel, um Gast-und externe Benutzer auszuschließen.|

Zum einschließen oder Ausschließen von Gästen und externen Benutzern in Regeln für bedingten Zugriff klicken Sie auf die Registerkarte einschließen oder ausschließen, und aktivieren Sie **alle Gäste und externe Benutzer**.

![Bildschirmaufzeichnung von Steuerelementen zum Ausschließen von Gästen](../images/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Weitere Informationen

### <a name="guests-vs-external-users"></a>Gäste vs. externe Benutzer
In Azure AD sind Gast-und externe Benutzer identisch. Der Benutzertyp für diese beiden Typen ist Gast. Gastbenutzer sind B2B-Benutzer.

Microsoft Teams unterscheidet zwischen Gastbenutzern und externen Benutzern innerhalb der APP, aber dies sind beide B2B-Benutzer bei der Authentifizierung. Weitere Informationen zu Microsoft Teams-Gast-und externen Benutzern finden Sie unter [Aktivieren von Gast-und externem Zugriff für Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).

### <a name="require-mfa-always-for-guest-and-external-users"></a>MFA immer für Gast und externe Benutzer erforderlich
Diese Regel fordert Gäste auf, sich für MFA in Ihrem Mandanten zu registrieren, unabhängig davon, ob Sie für MFA in Ihrem Wohnsitz Mandanten registriert sind. Beim Zugriff auf Ressourcen in Ihrem Mandanten müssen Gäste und externe Benutzer MFA für jede Anforderung verwenden. 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Ausschließen von Gast-und externen Benutzern aus risikobasierter MFA
Während Organisationen risikobasierte Richtlinien für B2B-Benutzer mithilfe des Identitätsschutzes erzwingen können, gibt es Einschränkungen bei der Implementierung des Identitätsschutzes für Benutzer der B2B-Zusammenarbeit in einem Ressourcenverzeichnis aufgrund ihrer vorhandenen Identität in ihrer Heimat. Directory. Aufgrund dieser Einschränkungen empfiehlt Microsoft, Gastbenutzer von risikobasierten MFA-Richtlinien auszuschließen, und diese Benutzer müssen immer MFA verwenden. 

Weitere Informationen finden Sie unter [Einschränkungen des Identitätsschutzes für Benutzer in der B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users). 

### <a name="excluding-guest-and-external-users-from-device-management"></a>Ausschließen von Gast-und externen Benutzern aus der Geräteverwaltung 
Nur eine Organisation kann ein Gerät verwalten. Wenn Sie Gast-und externe Benutzer nicht von Richtlinien ausschließen, die die Gerätekompatibilität erfordern, werden diese Benutzer durch diese Richtlinien blockiert. 

## <a name="next-steps"></a>Nächste Schritte

[Erfahren Sie, wie Sie Teams bedingten Zugriff aktivieren](teams-access-policies.md)

