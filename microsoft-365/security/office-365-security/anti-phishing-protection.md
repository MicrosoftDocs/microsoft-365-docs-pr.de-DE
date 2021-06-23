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
ms.openlocfilehash: 2a28e2ecc45be941dbd6e346f9918e1692357840
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083104"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Antiphishingschutz in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Bei *Phishing* handelt es sich um E-Mail-Angriffe, bei denen versucht wird, vertrauliche Informationen mittels Nachrichten zu stehlen, die scheinbar von legitimen oder vertrauenswürdigen Absendern stammen. Es gibt bestimmte Kategorien von Phishing. Beispiel:

- **Spear-Phishing** verwendet fokussierte, angepasste Inhalte, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach der Aufarbeitung der Empfänger durch den Angreifer).

- **Das Einatmen** richtet sich an Führungskräfte oder andere ziele mit hohem Wert innerhalb einer Organisation, um eine maximale Wirkung zu erzielen.

- **Business Email Compromise (BEC)** verwendet gefälschte vertrauenswürdige Absender (Finanzbeauftragte, Kunden, vertrauenswürdige Partner usw.), um Empfänger dazu zu bringen, Zahlungen zu genehmigen, Guthaben zu übertragen oder Kundendaten offenzulegen. Erfahren Sie mehr, in dem Sie [dieses Video](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2) ansehen.

- **Ransomware,** die Ihre Daten verschlüsselt und eine Zahlung zur Entschlüsselung anfordert, beginnt fast immer in Phishing-Nachrichten. Der Antiphishingschutz kann Ihnen nicht helfen, verschlüsselte Dateien zu entschlüsseln, aber er kann ihnen helfen, die anfänglichen Phishingnachrichten zu erkennen, die der Ransomware-Kampagne zugeordnet sind. Weitere Informationen zur Wiederherstellung nach einem Ransomware-Angriff finden Sie unter ["Wiederherstellen nach einem Ransomware-Angriff in Microsoft 365".](recover-from-ransomware.md)

Angesichts der zunehmenden Komplexität von Angriffen ist es für geschulte Benutzer sogar schwierig, komplexe Phishingnachrichten zu erkennen. Glücklicherweise können Exchange Online Protection (EOP) und die zusätzlichen Features in Microsoft Defender für Office 365 hilfreich sein.

## <a name="anti-phishing-protection-in-eop"></a>Antiphishingschutz in EOP

EOP (d. h. Microsoft 365 Organisationen ohne Microsoft Defender für Office 365) enthält Features, die Ihre Organisation vor Phishingbedrohungen schützen können:

- **Spoofintelligenz:** Verwenden Sie den Einblick in die Spoofintelligenz, um erkannte gefälschte Absender in Nachrichten von externen und internen Domänen zu überprüfen und diese erkannten Absender manuell zuzulassen oder zu blockieren. Weitere Informationen finden Sie unter [Spoofintelligenz-Erkenntnisse in EOP](learn-about-spoof-intelligence.md).

- **Antiphishingrichtlinien in EOP:** Aktivieren oder Deaktivieren der Spoofintelligenz, Aktivieren oder Deaktivieren der nicht authentifizierten Absenderidentifikation in Outlook aktivieren oder deaktivieren und Angeben der Aktion für blockierte gefälschte Absender. Weitere Informationen finden Sie unter [Konfigurieren von Antiphishingrichtlinien in EOP.](configure-anti-phishing-policies-eop.md)

- **Zulassen oder Blockieren von Spoofingabsendern in der Liste Mandantenzulassungsliste/ -sperrliste**: Wenn Sie die Sicherheitsbewertung in dem Spoofintelligenz-Erkenntnis außer Kraft setzen, wird der Spoofingabsender zu einem manuellen zugelassenen oder blockierten Eintrag, die nur auf der Registerkarte **Spoofen** in der Mandantenzulassungsliste/ -sperrliste angezeigt wird. Sie können auch zugelassene oder blockierte Einträge für Spoofingabsender erstellen, bevor diese von der Spoofintelligenz erkannt werden. Weitere Informationen finden Sie unter [Verwalten der Mandantenzulassungsliste/ -sperrliste in EOP](tenant-allow-block-list.md).

- **Implizite E-Mail-Authentifizierung:** EOP verbessert standardmäßige E-Mail-Authentifizierungsprüfungen für eingehende E-Mails ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)) mit Absenderzurückruf, Absenderverlauf, Empfängerverlauf, Verhaltensanalysen und anderen erweiterten Techniken, um gefälschte Absender zu identifizieren. Weitere Informationen finden Sie unter [E-Mail-Authentifizierung in Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Zusätzlicher Antiphishingschutz in Microsoft Defender für Office 365

Microsoft Defender für Office 365 enthält weitere und noch fortgeschrittenere Antiphishingfeatures:

- **Antiphishingrichtlinien in Microsoft Defender für Office 365:** Konfigurieren von Identitätswechselschutzeinstellungen für bestimmte Nachrichten- und Absenderdomänen, Postfachintelligenzeinstellungen und anpassbare erweiterte Phishing-Schwellenwerte. Weitere Informationen finden Sie unter [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-mdo-anti-phishing-policies.md). Weitere Informationen zu den Unterschieden zwischen Antiphishingrichtlinien in EOP und Antiphishingrichtlinien in Defender für Office 365 finden Sie unter [Antiphishingrichtlinien in Microsoft 365](set-up-anti-phishing-policies.md).
- **Kampagnenansichten:** Machine Learning und andere Heuristiken identifizieren und analysieren Nachrichten, die an koordinierten Phishingangriffen auf den gesamten Dienst und Ihre Organisation beteiligt sind. Weitere Informationen finden Sie unter [Kampagnenansichten in Microsoft Defender für Office 365](campaigns.md).
- **Angriffssimulationsschulung:** Administratoren können gefälschte Phishingnachrichten erstellen und sie als Bildungstool an interne Benutzer senden. Weitere Informationen finden Sie unter [Simulieren eines Phishingangriffs.](attack-simulation-training.md)

## <a name="other-anti-phishing-resources"></a>Andere Antiphishingressourcen

- Für Endbenutzer: [Schützen Sie sich vor Phishing-Schemas und anderen Formen von Online-Betrug.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Wie Microsoft 365 die Absenderadresse überprüft, um Phishing zu verhindern.](how-office-365-validates-the-from-address.md)
