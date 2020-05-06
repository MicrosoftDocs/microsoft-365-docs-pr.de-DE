---
title: Anti-Phishing-Schutz in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: In diesem Artikel werden die verfügbaren Online Ressourcen vorgestellt, die verwendet werden können, um sich mit Anti-Phishing-Optionen und-Strategien in Microsoft 365 vertraut zu machen und Sie zu implementieren.
ms.openlocfilehash: 09d384376b1e44989987c40ef3c7860e4fac6167
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033762"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Anti-Phishing-Schutz in Microsoft 365

*Phishing* ein e-Mail-Angriff, der versucht, vertrauliche Informationen in Nachrichten zu stehlen, die scheinbar von legitimen oder vertrauenswürdigen Absendern sind. Es gibt bestimmte Kategorien von Phishing. Zum Beispiel:

- **Spear-Phishing** verwendet sehr fokussierte und angepasste Inhalte, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach Aufklärung der Empfänger durch den Angreifer).

- **Walfang** richtet sich an Führungskräfte oder andere hochwertige Ziele innerhalb einer Organisation für maximale Wirkung.

- **Business e-Mail-Kompromiss (BEC)** verwendet gefälschte vertrauenswürdige Absender (Finanzmitarbeiter, Kunden, vertrauenswürdige Partner usw.), um den Empfänger dazu zu verleiten, Zahlungen zu genehmigen, Geld zu überweisen oder Kundendaten offenzulegen.

- **Ransomware** , die Ihre Daten verschlüsselt und die Zahlung zur Entschlüsselung verlangt. fast immer beginnt in Phishing-Nachrichten. Der Schutz vor Phishing kann Ihnen nicht dabei helfen, verschlüsselte Dateien zu entschlüsseln, aber er kann bei der Erkennung der anfänglichen Phishing-Nachrichten helfen, die der Ransomware-Kampagne zugeordnet sind. Weitere Informationen zum Wiederherstellen nach einem Ransomware-Angriff finden Sie unter [Recover by a Ransomware Attack in Microsoft 365](recover-from-ransomware.md).

Aufgrund der wachsenden Komplexität von Angriffen ist es für geschulte Benutzer sogar schwierig, anspruchsvolle Phishing-Nachrichten zu identifizieren. Glücklicherweise können Exchange Online Protection (EoP) und die zusätzlichen Features in Microsoft 365 Advanced Threat Protection (ATP) hilfreich sein.

## <a name="anti-phishing-protection-in-eop"></a>Anti-Phishing-Schutz in EoP

EoP (Microsoft 365-Organisationen ohne ATP) enthält Features, mit denen Ihre Organisation vor Phishing-Bedrohungen geschützt werden kann:

- **Spoofing Intelligence**: Überprüfen Sie gefälschte Nachrichten von Absendern in internen und externen Domänen und lassen Sie diese Absender zu oder blockieren Sie sie. Weitere Informationen finden Sie unter [Konfigurieren der Spoofintelligenz in Microsoft 365](learn-about-spoof-intelligence.md).

- **Anti-Phishing-Richtlinien in EoP**: Aktivieren oder deaktivieren Sie Spoof Intelligence, aktivieren oder deaktivieren Sie die nicht authentifizierte Absender Identifikation in Outlook, und geben Sie die Aktion für blockierte gefälschte Absender an (in den Ordner "Junk-e-Mail" oder "Quarantäne" verschieben). Weitere Informationen finden Sie unter [configure Anti-Phishing Policies in EoP](configure-anti-phishing-policies-eop.md).

- **Implizite e-Mail-Authentifizierung**: EoP verbessert standardmäßige e-Mail-Authentifizierungsüberprüfungen für eingehende e-Mails ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)) mit Absenderzuverlässigkeit, Absender Verlauf, Empfänger Verlauf, Verhaltensanalyse und anderen erweiterten Techniken zur Identifizierung gefälschter Absender. Weitere Informationen finden Sie unter [E-Mail-Authentifizierung in Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Zusätzlicher Schutz gegen Phishing in Office 365 ATP

Office 365 ATP enthält zusätzliche und erweiterte Features zum Schutz vor Phishing:

- **Richtlinien für ATP-Anti-Phishing**: Erstellen neuer benutzerdefinierter Richtlinien, Konfigurieren von Einstellungen für antiidentitäts Wechsel (schützen von Benutzern und Domänen vor Identitätswechsel), Post Fachnachrichten Einstellungen und anpassbaren erweiterten Phishing-Schwellenwerten. Weitere Informationen finden Sie unter [configure ATP Anti-Phishing Policies in Microsoft 365](configure-atp-anti-phishing-policies.md). Weitere Informationen zu den Unterschieden zwischen Anti-Phishing-Richtlinien und ATP-AntiPhishing-Richtlinien finden Sie unter [Anti-Phishing Policies in Microsoft 365](set-up-anti-phishing-policies.md).

- **Kampagnen Ansichten**: Maschinelles Lernen und andere Heuristiken identifizieren und analysieren Nachrichten, die an koordinierten Phishing-Angriffen für den gesamten Dienst und Ihre Organisation beteiligt sind. Weitere Informationen finden Sie unter [Kampagnen Ansichten in Office 365 ATP](campaigns.md).

- **Angriffs Simulator**: Administratoren können gefälschte Phishing-Nachrichten erstellen und Sie als Schulungstool an interne Benutzer senden. Weitere Informationen finden Sie unter [Attack Simulator in Office 365 ATP](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Weitere Anti-Phishing-Ressourcen

- Für Endbenutzer: [schützen Sie sich vor Phishing-Schemas und anderen Formen von Onlinebetrug](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).

- [Wie Microsoft 365 die Absenderadresse überprüft, um Phishing zu verhindern](how-office-365-validates-the-from-address.md).