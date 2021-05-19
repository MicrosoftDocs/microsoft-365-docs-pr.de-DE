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
description: Administratoren können mehr über die Antiphishingschutzfunktionen in Exchange Online Protection (EOP) und Microsoft Defender for Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 290f5f7797d987fb65a99e3f9e656bfec4cf83f3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538339"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Antiphishingschutz in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Bei *Phishing* handelt es sich um E-Mail-Angriffe, bei denen versucht wird, vertrauliche Informationen mittels Nachrichten zu stehlen, die scheinbar von legitimen oder vertrauenswürdigen Absendern stammen. Es gibt bestimmte Kategorien von Phishing. Beispiel:

- **Beim Phishing** werden gezielt angepasste Inhalte verwendet, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach der Aufklärung der Empfänger durch den Angreifer).

- **Der Walfang richtet** sich an Führungskräfte oder andere ziele mit hohem Wert innerhalb einer Organisation, um eine maximale Wirkung zu erzielen.

- **Business Email Compromise (BEC)** verwendet gefälschte vertrauenswürdige Absender (Finanzbeamte, Kunden, vertrauenswürdige Partner usw.), um Empfänger dazu zu verwenden, Zahlungen zu genehmigen, Geld zu übertragen oder Kundendaten offen zu stellen. Erfahren Sie mehr, in dem Sie [dieses Video](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2) ansehen.

- **Ransomware,** die Ihre Daten verschlüsselt und zahlungen zur Entschlüsselung fordert, beginnt fast immer mit Phishingnachrichten. Antiphishingschutz hilft Ihnen nicht, verschlüsselte Dateien zu entschlüsseln, aber er kann dazu beitragen, die anfänglichen Phishingnachrichten zu erkennen, die der Ransomware-Kampagne zugeordnet sind. Weitere Informationen zum Wiederherstellen nach einem Ransomware-Angriff finden Sie unter [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).

Mit der zunehmenden Komplexität von Angriffen ist es für geschulte Benutzer sogar schwierig, anspruchsvolle Phishingnachrichten zu identifizieren. Glücklicherweise können Exchange Online Protection (EOP) und die zusätzlichen Features in Microsoft Defender for Office 365 helfen.

## <a name="anti-phishing-protection-in-eop"></a>Antiphishingschutz in EOP

EOP (d. h. Microsoft 365 Organisationen ohne Microsoft Defender for Office 365) enthält Features, die Ihre Organisation vor Phishingbedrohungen schützen können:

- **Spoof intelligence**: Verwenden Sie die Spion-Intelligence-Einblicke, um erkannte gefälschte Absender in Nachrichten von externen und internen Domänen zu überprüfen und diese erkannten Absender manuell zu erlauben oder zu blockieren. Weitere Informationen finden Sie unter [Spoof Intelligence Insight in EOP](learn-about-spoof-intelligence.md).

- **Antiphishingrichtlinien in EOP:** Aktivieren oder Deaktivieren der Spoofintelligenz, Aktivieren oder Deaktivieren der nicht authentifizierten Absenderidentifikation in Outlook ein oder aus, und geben Sie die Aktion für blockierte spoofierte Absender an. Weitere Informationen finden Sie unter [Konfigurieren von Antiphishingrichtlinien in EOP](configure-anti-phishing-policies-eop.md).

- Zulassen oder Blockieren von gefälschten Absendern in der Mandanten zulassen/Blockieren-Liste: Wenn Sie das Urteil in der Spoof Intelligence-Einsicht außer Kraft setzen, wird der gefälschte Absender zu einem manuellen Zulassen oder Blockieren des **Eintrags,** der nur auf der Registerkarte **Spoof** in der Mandanten-Zulassen-/Sperrliste angezeigt wird. Sie können auch manuell Zulassen oder Blockieren von Einträgen für Spoof-Absender erstellen, bevor sie von spoof intelligence erkannt werden. Weitere Informationen finden Sie [unter Manage the Tenant Allow/Block List in EOP](tenant-allow-block-list.md).

- Implizite E-Mail-Authentifizierung: EOP verbessert standardmäßige E-Mail-Authentifizierungsüberprüfungen für eingehende E-Mails ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)) mit Absenderverdingung, Absenderverlauf, Empfängerverlauf, Verhaltensanalyse und anderen erweiterten Techniken, um gefälschte Absender zu identifizieren. Weitere Informationen finden Sie unter [E-Mail-Authentifizierung in Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Zusätzlicher Antiphishingschutz in Microsoft Defender für Office 365

Microsoft Defender für Office 365 enthält weitere und noch fortgeschrittenere Antiphishingfeatures:

- **Antiphishingrichtlinien in Microsoft Defender for Office 365:** Konfigurieren von Identitätswechselschutzeinstellungen für bestimmte Nachrichtensender und Absenderdomänen, Postfachintelligenzeinstellungen und anpassbare erweiterte Phishingschwellenwerte. Weitere Informationen finden Sie unter [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md). Weitere Informationen zu den Unterschieden zwischen Antiphishingrichtlinien in EOP und Antiphishingrichtlinien in Defender for Office 365 finden Sie unter [Antiphishingrichtlinien in Microsoft 365](set-up-anti-phishing-policies.md).

- **Kampagnenansichten:** Maschinelles Lernen und andere Heuristiken identifizieren und analysieren Nachrichten, die an koordinierten Phishingangriffen gegen den gesamten Dienst und Ihre Organisation beteiligt sind. Weitere Informationen finden Sie unter [Kampagnenansichten in Microsoft Defender for Office 365](campaigns.md).

- **Angriffssimulator:** Administratoren können gefälschte Phishingnachrichten erstellen und als Bildungstool an interne Benutzer senden. Weitere Informationen finden Sie unter [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Andere Antiphishingressourcen

- Für Endbenutzer: [Schützen Sie sich vor Phishingschemas und anderen Formen von Onlinebetrug.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Überprüfen Microsoft 365 Von-Adresse, um Phishing zu verhindern.](how-office-365-validates-the-from-address.md)
