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
ms.openlocfilehash: f42ea3159dc5ed975852aaca10ce6f344b71d749
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175631"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Antiphishingschutz in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Bei *Phishing* handelt es sich um E-Mail-Angriffe, bei denen versucht wird, vertrauliche Informationen mittels Nachrichten zu stehlen, die scheinbar von legitimen oder vertrauenswürdigen Absendern stammen. Es gibt bestimmte Kategorien von Phishing. Zum Beispiel:

- **Beim Phishing** von Phishing werden fokussierte, angepasste Inhalte verwendet, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach der Aufarbeitung der Empfänger durch den Angreifer).

- **Der Whaling** richtet sich an Führungskräfte oder andere hochwertige Ziele innerhalb einer Organisation, um eine maximale Wirkung zu erzielen.

- **BeC (Business Email Compromise)** verwendet gefälschte vertrauenswürdige Absender (Finanzbeauftragte, Kunden, vertrauenswürdige Partner usw.), um Empfänger dazu zu verwenden, Zahlungen zu genehmigen, Guthaben zu übertragen oder Kundendaten offen zu geben.

- **Ransomware,** die Ihre Daten verschlüsselt und eine Zahlung zur Entschlüsselung verlangt, beginnt fast immer bei Phishingnachrichten. Der Antiphishingschutz kann Ihnen nicht dabei helfen, verschlüsselte Dateien zu entschlüsseln, aber er kann dazu beitragen, die anfänglichen Phishingnachrichten zu erkennen, die der Ransomware-Kampagne zugeordnet sind. Weitere Informationen zum Wiederherstellen nach einem Ransomware-Angriff finden Sie unter "Wiederherstellen nach einem [Ransomware-Angriff in Microsoft 365".](recover-from-ransomware.md)

Mit der zunehmenden Komplexität von Angriffen ist es für geschulte Benutzer sogar schwierig, komplexe Phishingnachrichten zu identifizieren. Glücklicherweise können Exchange Online Protection (EOP) und die zusätzlichen Features in Microsoft Defender für Office 365 hilfreich sein.

## <a name="anti-phishing-protection-in-eop"></a>Antiphishingschutz in EOP

EOP (d. h. Microsoft 365-Organisationen ohne Microsoft Defender für Office 365) enthält Features, die Ihre Organisation vor Phishingbedrohungen schützen können:

- **Spoofing Intelligence**: Überprüfen Sie gefälschte Nachrichten von Absendern in internen und externen Domänen und lassen Sie diese Absender zu oder blockieren Sie sie. Weitere Informationen finden Sie unter [Konfigurieren der Spoofintelligenz in EOP.](learn-about-spoof-intelligence.md)

- **Antiphishingrichtlinien in EOP:** Aktivieren oder Deaktivieren der Spoofintelligenz, Aktivieren oder Deaktivieren der Identifizierung nicht authentifizierter Absender in Outlook und Festlegen der Aktion für blockierte gefälschte Absender (In Junk-E-Mail-Ordner oder Quarantäne verschieben). Weitere Informationen finden Sie unter [Konfigurieren von Antiphishingrichtlinien in EOP.](configure-anti-phishing-policies-eop.md)

- **Implizite** E-Mail-Authentifizierung: EOP verbessert standardmäßige E-Mail-Authentifizierungsprüfungen für eingehende E-Mails ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)) mit Absenderverifikation, Absenderverlauf, Empfängerverlauf, Verhaltensanalyse und anderen erweiterten Techniken zur Identifizierung gefälschter Absender. Weitere Informationen finden Sie unter [E-Mail-Authentifizierung in Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Zusätzlicher Antiphishingschutz in Microsoft Defender für Office 365

Microsoft Defender für Office 365 enthält weitere und noch fortgeschrittenere Antiphishingfeatures:

- **Antiphishingrichtlinien in Microsoft Defender für Office 365:** Erstellen neuer benutzerdefinierter Richtlinien, Konfigurieren von Einstellungen für den Identitätswechsel (Schutz von Benutzern und Domänen vor Identitätswechsel), Einstellungen für die Postfachintelligenz und anpassbare erweiterte Phishingschwellenwerte. Weitere Informationen finden Sie unter ["Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365".](configure-atp-anti-phishing-policies.md) Weitere Informationen zu den Unterschieden zwischen Antiphishingrichtlinien in EOP und Antiphishingrichtlinien in Defender für Office 365 finden Sie [unter Antiphishingrichtlinien in Microsoft 365.](set-up-anti-phishing-policies.md)

- **Kampagnenansichten:** Maschinelles Lernen und andere Heuristiken identifizieren und analysieren Nachrichten, die an koordinierten Phishingangriffen gegen den gesamten Dienst und Ihre Organisation beteiligt sind. Weitere Informationen finden Sie unter [Kampagnenansichten in Microsoft Defender für Office 365.](campaigns.md)

- **Angriffssimulator:** Administratoren können gefälschte Phishingnachrichten erstellen und diese als Bildungstool an interne Benutzer senden. Weitere Informationen finden Sie unter ["Angriffssimulator" in Microsoft Defender für Office 365.](attack-simulator.md)

## <a name="other-anti-phishing-resources"></a>Weitere Antiphishingressourcen

- Für Endbenutzer: [Schützen Sie sich vor Phishingschemas und anderen Formen von Online-Betrug.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Wie Microsoft 365 die "Von"-Adresse überprüft, um Phishing zu verhindern.](how-office-365-validates-the-from-address.md)
