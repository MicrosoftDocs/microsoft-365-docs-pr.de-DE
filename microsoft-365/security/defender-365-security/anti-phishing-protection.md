---
title: Antiphishingschutz
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Administratoren können sich über die Antiphishingschutzfunktionen in Exchange Online Protection (EOP) und Microsoft Defender für Office 365 informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0ca7a83e8e8d66bd58fddfc46f53df32f4f623c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065567"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Antiphishingschutz in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Bei *Phishing* handelt es sich um E-Mail-Angriffe, bei denen versucht wird, vertrauliche Informationen mittels Nachrichten zu stehlen, die scheinbar von legitimen oder vertrauenswürdigen Absendern stammen. Es gibt bestimmte Kategorien von Phishing. Zum Beispiel:

- **Beim Phishing** werden gezielt angepasste Inhalte verwendet, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach der Aufklärung der Empfänger durch den Angreifer).

- **Der Walfang richtet** sich an Führungskräfte oder andere ziele mit hohem Wert innerhalb einer Organisation, um eine maximale Wirkung zu erzielen.

- **Business Email Compromise (BEC)** verwendet gefälschte vertrauenswürdige Absender (Finanzbeamte, Kunden, vertrauenswürdige Partner usw.), um Empfänger dazu zu verwenden, Zahlungen zu genehmigen, Geld zu übertragen oder Kundendaten offen zu stellen.

- **Ransomware,** die Ihre Daten verschlüsselt und zahlungen zur Entschlüsselung fordert, beginnt fast immer mit Phishingnachrichten. Antiphishingschutz hilft Ihnen nicht, verschlüsselte Dateien zu entschlüsseln, aber er kann dazu beitragen, die anfänglichen Phishingnachrichten zu erkennen, die der Ransomware-Kampagne zugeordnet sind. Weitere Informationen zum Wiederherstellen nach einem Ransomware-Angriff finden Sie unter [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).

Mit der zunehmenden Komplexität von Angriffen ist es für geschulte Benutzer sogar schwierig, anspruchsvolle Phishingnachrichten zu identifizieren. Glücklicherweise können Exchange Online Protection (EOP) und die zusätzlichen Features in Microsoft Defender für Office 365 hilfreich sein.

## <a name="anti-phishing-protection-in-eop"></a>Antiphishingschutz in EOP

EOP (d. h. Microsoft 365-Organisationen ohne Microsoft Defender für Office 365) enthält Features, die Ihre Organisation vor Phishingbedrohungen schützen können:

- **Spoofing Intelligence**: Überprüfen Sie gefälschte Nachrichten von Absendern in internen und externen Domänen und lassen Sie diese Absender zu oder blockieren Sie sie. Weitere Informationen finden Sie unter [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).

- **Antiphishingrichtlinien in EOP:** Aktivieren oder Deaktivieren der Spoofintelligenz, Aktivieren oder Deaktivieren der nicht authentifizierten Absenderidentifikation in Outlook und Angeben der Aktion für blockierte spoofierte Absender (Wechseln in Junk-E-Mail-Ordner oder Quarantäne). Weitere Informationen finden Sie unter [Konfigurieren von Antiphishingrichtlinien in EOP](configure-anti-phishing-policies-eop.md).

- Implizite E-Mail-Authentifizierung: EOP verbessert standardmäßige E-Mail-Authentifizierungsüberprüfungen für eingehende E-Mails ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)) mit Absenderverdingung, Absenderverlauf, Empfängerverlauf, Verhaltensanalyse und anderen erweiterten Techniken, um gefälschte Absender zu identifizieren. Weitere Informationen finden Sie unter [E-Mail-Authentifizierung in Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Zusätzlicher Antiphishingschutz in Microsoft Defender für Office 365

Microsoft Defender für Office 365 enthält weitere und noch fortgeschrittenere Antiphishingfeatures:

- **Antiphishingrichtlinien in Microsoft Defender für Office 365:** Erstellen neuer benutzerdefinierter Richtlinien, Konfigurieren von Einstellungen für den Identitätswechsel (Schutz von Benutzern und Domänen vor Identitätswechsel), Einstellungen für die Postfachintelligenz und anpassbare erweiterte Phishingschwellenwerte. Weitere Informationen finden Sie unter [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md). Weitere Informationen zu den Unterschieden zwischen Antiphishingrichtlinien in EOP und Antiphishingrichtlinien in Defender for Office 365 finden Sie unter [Antiphishingrichtlinien in Microsoft 365](set-up-anti-phishing-policies.md).

- **Kampagnenansichten:** Maschinelles Lernen und andere Heuristiken identifizieren und analysieren Nachrichten, die an koordinierten Phishingangriffen gegen den gesamten Dienst und Ihre Organisation beteiligt sind. Weitere Informationen finden Sie unter [Kampagnenansichten in Microsoft Defender für Office 365](campaigns.md).

- **Angriffssimulator:** Administratoren können gefälschte Phishingnachrichten erstellen und als Bildungstool an interne Benutzer senden. Weitere Informationen finden Sie unter [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Andere Antiphishingressourcen

- Für Endbenutzer: [Schützen Sie sich vor Phishingschemas und anderen Formen von Onlinebetrug.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [So überprüft Microsoft 365 die Von-Adresse, um Phishing zu verhindern.](how-office-365-validates-the-from-address.md)
