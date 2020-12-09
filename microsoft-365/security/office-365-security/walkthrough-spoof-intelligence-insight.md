---
title: Exemplarische Vorgehensweise – Spoof Intelligence Insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie die Spoof Intelligence-Einblicke funktionieren. Sie können schnell ermitteln, welche Absender legitimerweise e-Mails in ihre Organisationen aus Domänen senden, die keine e-Mail-Authentifizierungsprüfungen (SPF, DKIM oder DMARC) durchführen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9139a2b4c3c7ed8262f3d75b445defb869371d07
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602105"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Exemplarische Vorgehensweise – Spoof Intelligence Insight in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Defender for Office 365 können Sie die Spoof Intelligence-Einblicke verwenden, um schnell zu ermitteln, welche externen Absender legitimerweise nicht authentifizierte e-Mails senden (Nachrichten von Domänen, die keine SPF-, DKIM-oder DMARC-Überprüfungen durchführen).

Durch die Möglichkeit, dass bekannte externe Absender gefälschte Nachrichten von bekannten Speicherorten senden, können Sie falsch positive Ergebnisse reduzieren (gute e-Mail-Adressen werden als ungültig markiert). Durch Überwachen der zulässigen gefälschten Absender stellen Sie eine zusätzliche Sicherheitsebene bereit, um zu verhindern, dass unsichere Nachrichten in Ihrer Organisation eingehen.

Weitere Informationen zu Berichten und Einblicken finden Sie unter [Reports and Insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).

Diese exemplarische Vorgehensweise ist eine von mehreren für das Security & Compliance Center. Informationen zum Navigieren in Berichten und Einblicken finden Sie unter Exemplarische Vorgehensweisen im Abschnitt " [Verwandte Themen](#related-topics) ".

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Security Dashboard** zu wechseln, verwenden Sie <https://protection.office.com/searchandinvestigation/dashboard> .

  Sie können die Einblicke in Spoof Intelligence aus mehreren Dashboards im Security & Compliance Center anzeigen. Unabhängig davon, für welches Dashboard Sie sich interessieren, bietet die Insight dieselben Details und ermöglicht Ihnen, schnell dieselben Aufgaben auszuführen.

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - **Organisationsverwaltung**
  - **Sicherheits Administrator**
  - **Sicherheits Leser**
  - **Globaler Leser**

  **Hinweis**: beim Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

- Sie aktivieren und deaktivieren Spoof Intelligence in Anti-Phishing-Richtlinien in Microsoft Defender für Office 365. Spoof Intelligence ist standardmäßig aktiviert. Weitere Informationen finden Sie unter [configure Anti-Phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

- Informationen zum Verwenden von Spoof Intelligence zum Überwachen und Verwalten von Absendern, die nicht authentifizierte Nachrichten senden, finden Sie unter [configure Spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Öffnen Sie die Spoof Intelligence-Einblicke im Security & Compliance Center.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Dashboard.**

2. Suchen Sie in der Zeile **Insights** nach einem der folgenden Elemente:

   - **Wahrscheinliche gefälschte Domänen in den letzten sieben Tagen**: Diese Erkenntnis gibt an, dass Spoof Intelligence aktiviert ist (Sie ist standardmäßig aktiviert).
   - **Spoofschutz aktivieren**: Diese Erkenntnis gibt an, dass Spoof Intelligence deaktiviert ist, und durch Klicken auf die Einblicke können Sie Spoof Intelligence aktivieren.

3. Die Einblicke in das Dashboard zeigt Ihnen Informationen wie die folgende:

   ![Screenshot von Spoof Intelligence Insight](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Diese Einblicke umfasst zwei Modi:

   - **Insight-Modus**: Wenn Spoof Intelligence aktiviert ist, zeigt Ihnen die Einblicke, wie viele Nachrichten in den letzten sieben Tagen durch unsere Spoof Intelligence-Funktionen beeinflusst wurden.
   - **Was** ist, wenn-Modus: Wenn Spoof Intelligence deaktiviert ist, dann zeigt Ihnen die Einsicht, wie viele Nachrichten in den letzten sieben Tagen von unseren Spoof Intelligence-Funktionen betroffen *wären* .

   In beiden Fällen werden die in der Insight angezeigten gefälschten Domänen in zwei Kategorien unterteilt: **verdächtige Domänen** und **nicht verdächtige Domänen**.

   - Zu den **verdächtigen Domänen** gehören:

     - Spoofing mit hoher Vertrauenswürdigkeit: basierend auf den Verlaufs Sende Mustern und dem Reputations Ergebnis der Domänen sind wir sehr zuversichtlich, dass die Domänen Spoofing sind und Nachrichten aus diesen Domänen eher bösartig sind.

     - Gemäßigte Vertrauens Parodie: basierend auf Verlaufs Sende Mustern und dem Reputationswert der Domänen sind wir mit mittlerer Zuversicht überzeugt, dass die Domänen Spoofing sind und dass von diesen Domänen gesendete Nachrichten legitim sind. Falsch positive Ergebnisse sind in dieser Kategorie eher als hochgradig vertrauenswürdige Spoofing.

   **Nicht verdächtige Domänen**: die Domänen-fehlgeschlagene explizite e-Mail-Authentifizierung überprüft [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)). Die Domäne bestanden jedoch unsere impliziten e-Mail-Authentifizierungsprüfungen ([kombinierte Authentifizierung](email-validation-and-authentication.md#composite-authentication)). Dies hat zur Folge, dass keine Anti-Spoofing-Aktion für die Nachricht durchgeführt wurde.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Anzeigen detaillierter Informationen zu verdächtigen Domänen aus der Spoof Intelligence-Einblicke

1. Klicken Sie im Bereich Spoof Intelligence Insight auf **verdächtige Domänen** oder **nicht verdächtige Domänen** , um zur Seite **Spoof Intelligence Insight** zu gelangen. Die Seite **Spoof Intelligence Insight** enthält die folgenden Informationen:

   - **Spoofed Domain**: die Domäne des gefälschten Benutzers, die im Feld **von** in e-Mail-Clients angezeigt wird. Diese Adresse wird auch als Adresse bezeichnet `5322.From` .
   - **Infrastruktur**: auch als _sendende Infrastruktur_ bezeichnet. Die Domäne, die in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-e-Mail-Servers gefunden wurde. Wenn die Quell-IP-Adresse keinen PTR-Eintrag aufweist, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (beispielsweise 192.168.100.100/24).
   - **Nachrichtenanzahl**: die Anzahl der Nachrichten von der sendenden Infrastruktur an Ihre Organisation, die die angegebene gefälschte Domäne in den letzten 7 Tagen enthalten.
   - **Zuletzt gesehen**: das letzte Datum, an dem eine Nachricht von der sendenden Infrastruktur empfangen wurde, die die gefälschte Domäne enthält.
   - **Spoof-Typ**: dieser Wert ist **extern**.
   - **Spoofing erlaubt?**: die Werte, die Sie hier sehen, sind:
     - **Yes**: Nachrichten aus der Kombination der Domäne des gefälschten Benutzers und der sendenden Infrastruktur sind zulässig und werden nicht als gefälschte e-Mails behandelt.
     - **No**: Nachrichten aus der Kombination der Domäne des gefälschten Benutzers und der sendenden Infrastruktur werden als gefälscht gekennzeichnet. Die Aktion wird von der standardmäßigen Anti-Phishing-Richtlinie oder von benutzerdefinierten Anti-Phishing-Richtlinien gesteuert (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).

     Weitere Informationen finden Sie unter [configure Anti-Phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

2. Wählen Sie ein Element in der Liste aus, um Details zum Domänen-/Sendeinfrastruktur Paar in einem Flyout anzuzeigen. Die Informationen umfassen Folgendes:
   - Warum wir dies erwischt haben.
   - Was Sie tun müssen.
   - Eine Domänen Zusammenfassung.
   - Whois-Daten über den Absender.
   - Ähnliche Nachrichten, die wir in Ihrem Mandanten vom gleichen Absender gesehen haben.

   Von hier aus können Sie auch die Domäne/das Senden von Infrastruktur Paaren aus der Liste der **zulässigen Absender Genehmigungen** zulassen hinzufügen oder entfernen. Legen Sie die Umschaltfläche einfach entsprechend fest.

   ![Screenshot einer Domäne im Detailbereich "Spoof Intelligence Insight"](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Hinzufügen einer Domäne zur Liste "zulässig zu Spoof"

Das Hinzufügen einer Domäne zur Liste zulässiger Spoof aus der Spoof Intelligence-Einsicht ermöglicht nur die Kombination der gefälschten Domäne *und* der sendenden Infrastruktur. Es werden keine e-Mails von der gefälschten Domäne aus einer beliebigen Quelle zugelassen, und es werden keine e-Mails von der sendenden Infrastruktur für eine beliebige Domäne zugelassen.

Beispielsweise können Sie die folgende Domäne der Liste zulässiger spoofs erlauben:

- **Domäne**: gmail.com
- **Infrastruktur**: TMS.MX.com

Nur e-Mails aus diesem Domänen-/Sendeinfrastruktur paar können Spoofing durchgehen. Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig. Nachrichten in anderen Domänen von TMS.MX.com werden durch Spoof Intelligence überprüft.

## <a name="related-topics"></a>Verwandte Themen

[Schutz gegen Spoofing in Microsoft 365](anti-spoofing-protection.md)
