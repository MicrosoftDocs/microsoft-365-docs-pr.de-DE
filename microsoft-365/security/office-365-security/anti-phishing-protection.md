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
ms.service: O365-seccomp
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
description: Administratoren können Informationen zu den Features zum Schutz vor Phishing in Exchange Online Protection (EoP) und Microsoft Defender für Office 365 erhalten.
ms.openlocfilehash: 51c539a47f1c137dbacbfaaf63212e1bb115860c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844512"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Anti-Phishing-Schutz in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Bei *Phishing* handelt es sich um E-Mail-Angriffe, bei denen versucht wird, vertrauliche Informationen mittels Nachrichten zu stehlen, die scheinbar von legitimen oder vertrauenswürdigen Absendern stammen. Es gibt bestimmte Kategorien von Phishing. Zum Beispiel:

- **Spear-Phishing** verwendet fokussierte, angepasste Inhalte, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach Aufklärung der Empfänger durch den Angreifer).

- **Walfang** richtet sich an Führungskräfte oder andere hochwertige Ziele innerhalb einer Organisation für maximale Wirkung.

- **Business eMail Kompromiss (BEC)** verwendet gefälschte vertrauenswürdige Absender (Finanzmitarbeiter, Kunden, vertrauenswürdige Partner usw.), um Empfänger in die Genehmigung von Zahlungen, die Übertragung von Guthaben oder das Aufdecken von Kundendaten zu betrügen.

- **Ransomware** , die Ihre Daten verschlüsselt und die Zahlung zur Entschlüsselung verlangt. fast immer beginnt in Phishing-Nachrichten. Der Schutz vor Phishing kann Ihnen nicht dabei helfen, verschlüsselte Dateien zu entschlüsseln, aber er kann bei der Erkennung der anfänglichen Phishing-Nachrichten helfen, die der Ransomware-Kampagne zugeordnet sind. Weitere Informationen zum Wiederherstellen nach einem Ransomware-Angriff finden Sie unter [Recover by a Ransomware Attack in Microsoft 365](recover-from-ransomware.md).

Aufgrund der wachsenden Komplexität von Angriffen ist es für geschulte Benutzer sogar schwierig, anspruchsvolle Phishing-Nachrichten zu identifizieren. Glücklicherweise können Exchange Online Protection (EoP) und die zusätzlichen Features in Microsoft Defender für Office 365 hilfreich sein.

## <a name="anti-phishing-protection-in-eop"></a>Antiphishingschutz in EOP

EoP (Microsoft 365-Organisationen ohne Microsoft Defender für Office 365) enthält Features, mit denen Ihre Organisation vor Phishing-Bedrohungen geschützt werden kann:

- **Spoofing Intelligence** : Überprüfen Sie gefälschte Nachrichten von Absendern in internen und externen Domänen und lassen Sie diese Absender zu oder blockieren Sie sie. Weitere Informationen finden Sie unter [configure Spoof Intelligence in EoP](learn-about-spoof-intelligence.md).

- **Anti-Phishing-Richtlinien in EoP** : Aktivieren oder deaktivieren Sie Spoof Intelligence, aktivieren oder deaktivieren Sie die nicht authentifizierte Absender Identifikation in Outlook, und geben Sie die Aktion für blockierte gefälschte Absender an (in den Ordner "Junk-e-Mail" oder "Quarantäne" verschieben). Weitere Informationen finden Sie unter [configure Anti-Phishing Policies in EoP](configure-anti-phishing-policies-eop.md).

- **Implizite e-Mail-Authentifizierung** : EoP verbessert standardmäßige e-Mail-Authentifizierungsüberprüfungen für eingehende e-Mails ( [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)) mit Absenderzuverlässigkeit, Absender Verlauf, Empfänger Verlauf, Verhaltensanalyse und anderen erweiterten Techniken zur Identifizierung gefälschter Absender. Weitere Informationen finden Sie unter [E-Mail-Authentifizierung in Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Zusätzlicher Schutz gegen Phishing in Microsoft Defender für Office 365

Microsoft Defender für Office 365 enthält zusätzliche und erweiterte Features zum Schutz vor Phishing:

- **Anti-Phishing-Richtlinien in Microsoft Defender für Office 365** : Erstellen neuer benutzerdefinierter Richtlinien, Konfigurieren von Einstellungen für die Anti-Identitätswechsel (schützen von Benutzern und Domänen vor Identitätswechsel), Post Fachnachrichten Einstellungen und anpassbaren erweiterten Phishing-Schwellenwerten. Weitere Informationen finden Sie unter [configure Anti-Phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md). Weitere Informationen zu den Unterschieden zwischen Anti-Phishing-Richtlinien in EoP und Anti-Phishing-Richtlinien in Defender für Office 365 finden Sie unter [Anti-Phishing Policies in Microsoft 365](set-up-anti-phishing-policies.md).

- **Kampagnen Ansichten** : Maschinelles Lernen und andere Heuristiken identifizieren und analysieren Nachrichten, die an koordinierten Phishing-Angriffen für den gesamten Dienst und Ihre Organisation beteiligt sind. Weitere Informationen finden Sie unter [Kampagnen Ansichten in Microsoft Defender für Office 365](campaigns.md).

- **Angriffs Simulator** : Administratoren können gefälschte Phishing-Nachrichten erstellen und Sie als Schulungstool an interne Benutzer senden. Weitere Informationen finden Sie unter [Attack Simulator in Microsoft Defender für Office 365](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Weitere Anti-Phishing-Ressourcen

- Für Endbenutzer: [schützen Sie sich vor Phishing-Schemas und anderen Formen von Onlinebetrug](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).

- [Wie Microsoft 365 die Absenderadresse überprüft, um Phishing zu verhindern](how-office-365-validates-the-from-address.md).
