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
description: Administratoren erfahren, wie die Spoof Intelligence-Einblicke funktionieren, und wie Sie schnell ermitteln können, welche Absender legitimerweise nicht authentifizierte e-Mails senden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5995095e442bbcd07ddf4538b67be6e1b14fd8f1
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844212"
---
# <a name="walkthrough---defender-for-office-365-spoof-intelligence-insight-in-microsoft-365"></a>Exemplarische Vorgehensweise-Defender for Office 365 Spoof Intelligence Insight in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Defender for Office 365 können Sie die Spoof Intelligence-Einblicke verwenden, um schnell zu ermitteln, welche Absender legitimerweise nicht authentifizierte e-Mails senden. Durch die Möglichkeit, gefälschte Nachrichten zu senden, können Sie das Risiko verringern, dass falsch positive Ergebnisse an Ihre Benutzer gesendet werden. Sie können auch die Spoof Intelligence-Einblicke verwenden, um zugelassene Domänen Paare zu überwachen und zu verwalten, um eine zusätzliche Sicherheitsebene bereitzustellen und zu verhindern, dass unsichere Nachrichten in Ihrer Organisation eingehen.

Wenn Sie noch keine [Erfahrung mit Berichten und Einblicken in das Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)haben, kann es hilfreich sein, zu sehen, wie Sie einfach von einem Dashboard zu einer Einblicke und empfohlenen Aktionen navigieren können.

Diese exemplarische Vorgehensweise ist eine von mehreren für das Security & Compliance Center. Informationen zum Navigieren in Berichten und Einblicken finden Sie unter Exemplarische Vorgehensweisen im Abschnitt "Verwandte Themen".

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Security Dashboard** zu wechseln, verwenden Sie <https://protection.office.com/searchandinvestigation/dashboard> .

  Sie können die Einblicke in Spoof Intelligence aus mehreren Dashboards im Security & Compliance Center anzeigen. Unabhängig davon, für welches Dashboard Sie sich interessieren, bietet die Insight dieselben Details und ermöglicht Ihnen, schnell dieselben Aufgaben auszuführen.

- Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Thema ausführen können. Um die Spoof Intelligence-Einblicke verwenden zu können, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
  - **Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).
  - **Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
  - **Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Sie aktivieren und deaktivieren Spoof Intelligence in Anti-Phishing-Richtlinien in Microsoft Defender für Office 365. Weitere Informationen finden Sie unter [configure Anti-Phishing Policies in Microsoft Defender for Office 365 in Microsoft 365](configure-atp-anti-phishing-policies.md).

- In Microsoft 365-Organisationen mit Exchange Online Postfächern und in eigenständigen Exchange Online Schutz (EoP) ohne Exchange Online Postfächer können Sie Spoof Intelligence zum Überwachen und Verwalten von Absendern verwenden, von denen Sie nicht authentifizierte Nachrichten senden. Weitere Informationen finden Sie unter [Konfigurieren der Spoofintelligenz in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Öffnen Sie die Spoof Intelligence-Einblicke im Security & Compliance Center.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Dashboard.**

2. Suchen Sie in der Zeile **Insights** nach einem der folgenden Elemente:

   - **Spoof Intelligence ist aktiviert** : die Einblicke werden als **gefälschte Domänen bezeichnet, bei denen die Authentifizierung der letzten 30 Tage nicht erfolgreich** war. Dies ist die Standardeinstellung.

   - **Spoof Intelligence ist deaktiviert** : die Einblicke in benannten **aktivieren Spoof Protection** , und klicken Sie auf Sie können Sie Spoof Intelligence aktivieren.

3. Die Einblicke in das Dashboard zeigt Ihnen Informationen wie die folgende:

   ![Screenshot von Spoof Intelligence Insight](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Diese Einblicke umfasst zwei Modi:

   - **Insight-Modus**. Wenn Sie eine Spoof-Richtlinie aktiviert haben, zeigt Ihnen die Einsicht, wie viele e-Mails in den letzten 30 Tagen von unseren Spoof Intelligence-Funktionen betroffen waren.

   - **Was ist, wenn-Modus**. Wenn Sie keine Spoof-Richtlinie aktiviert haben, zeigt Ihnen die Einsicht, wie viele e-Mails von unseren Spoof Intelligence-Funktionen in den letzten 30 Tagen betroffen  *wären*  .

   In beiden Fällen werden die in der Insight angezeigten gefälschten Domänen in zwei Kategorien unterteilt: **verdächtige Domänen Paare** und **nicht verdächtige Domänen Paare**. Diese Kategorien werden weiter in drei verschiedene Buckets unterteilt, die Sie überprüfen können.

   Ein **Domänenpaar** ist eine Kombination aus der von-Adresse und der sendenden Infrastruktur:

   - Die Absenderadresse ist die e-Mail-Adresse des Absenders, die in e-Mail-Clients angezeigt wird. Diese Adresse identifiziert den Autor der E-Mail. Das heißt, das Postfach der Person oder des Systems, das sich für das Schreiben der Nachricht verantwortlich zeichnet. Diese Adresse wird auch als Adresse bezeichnet `5322.From` .

   - Die sendende Infrastruktur oder der Absender ist die Organisationsdomäne des Reverse-DNS-Lookups (PTR-Eintrags) der sendenden IP-Adresse. Wenn die sendende IP-Adresse keinen PTR-Eintrag hat, wird der Absender von der sendenden IP mit der Subnetzmaske 255.255.255.0 in der CIDR-Notation (/24) identifiziert. Wenn die IP-Adresse beispielsweise 192.168.100.100 lautet, lautet die vollständige IP-Adresse des Absenders 192.168.100.100/24.

   Zu den **verdächtigen Domänen Paaren** gehören:

   - **Spoofing mit hoher Zuverlässigkeit** : Microsoft 365 hat starke Signale erhalten, dass diese Domänen verdächtig sind, basierend auf den Verlaufs Sende Mustern und dem Reputations Ergebnis der Domänen. Microsoft 365 ist sehr zuversichtlich, dass die Domänen Spoofing sind und dass Nachrichten, die von diesen Domänen gesendet werden, eher legitim sind.

   - **Gemäßigte Zuverlässigkeits Spoof** : Microsoft 365 erhielt moderate Signale, dass diese Domänen verdächtig sind, basierend auf Verlaufs Sende Mustern und dem Reputations Ergebnis der Domänen. Office 365 ist gemäßigt zuversichtlich, dass die Domänen Spoofing sind und dass von diesen Domänen gesendete Nachrichten legitim sind. Dieser Bucket hat eine größere Chance, falsch positive Ergebnisse (fps) zu enthalten als den Spoofing-Bucket mit hoher Vertrauenswürdigkeit.

   - **Nicht-verdächtige Domänen Paare** (einschließlich **geretteter Spoofing** ): "gerettete Spoof" sind Domänen, bei denen die explizite Authentifizierungsüberprüfung [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)fehlgeschlagen ist, aber unsere impliziten e-Mail-Authentifizierungsprüfungen ( [kombinierte Authentifizierung](email-validation-and-authentication.md#composite-authentication)) bestanden haben. Daher hat Microsoft 365 die e-Mails in Ihrem Namen gerettet, und es wurde keine Antispoofing-Aktion für die Nachricht ausgeführt.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Anzeigen detaillierter Informationen zu verdächtigen Domänen Paaren aus dem Spoof Intelligence-Insight

1. Klicken Sie auf der Spoof Intelligence-Einblicke auf eines der Domänen Paare (hoch, moderat oder gerettet).

   Die Seite **Spoof Intelligence Insight** wird angezeigt und zeigt eine Liste von Absendern an, die nicht authentifizierte e-Mails an Ihre Organisation senden. Die Informationen auf dieser Seite helfen Ihnen zu bestimmen, ob gefälschte Nachrichten autorisiert sind oder ob Sie weitere Aktionen ausführen müssen. Sie können die Informationen nach Nachrichtenanzahl, dem Datum, an dem die Spoof zuletzt erkannt wurde, und vieles mehr sortieren. (Klicken Sie beispielsweise auf Spaltenüberschriften wie **Nachrichtenanzahl** oder **zuletzt gesehen**.)

2. Wählen Sie ein Element in der Tabelle aus, um einen Detailbereich mit umfangreichen Informationen über das Domänenpaar zu öffnen, einschließlich der Gründe für diese Erfassung, was Sie tun müssen, eine Domänen Zusammenfassung, Whois-Daten über den Absender und ähnliche e-Mails, die wir in Ihrem Mandanten vom gleichen Absender gesehen haben. Von hier aus können Sie auch das Domänenpaar aus der Liste sicherer Absender von **AllowedToSpoof** hinzufügen oder entfernen.

   ![Screenshot einer Domäne im Detailbereich "Spoof Intelligence Insight"](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Hinzufügen oder Entfernen einer Domäne aus der Liste sicherer Absender von AllowedToSpoof

Sie können eine Domäne aus der Liste sicherer Absender von AllowedToSpoof hinzufügen oder entfernen, während Sie das Domänenpaar im Detailbereich der Spoof Intelligence-Einblicke überprüfen. Legen Sie die Umschaltfläche einfach entsprechend fest.

Dadurch wird die eindeutige Kombination aus Domänen Paaren der gefälschten Domäne und der sendenden Infrastruktur geändert, und es wird keine Abdeckung für die gesamte Spoofing-Domäne oder die sendende Infrastruktur isoliert bereitgestellt.

Wenn Sie beispielsweise das folgende Domänenpaar zur Absender Zulassungsliste "AllowedToSpoof" hinzufügen: die  *spoofed-Domäne*  "gmail.com" und die *Sendeinfrastruktur* "TMS *. MX.com",* dann dürfen nur e-Mails von diesem Domänenpaar Spoofing durchführen. Andere Absender, die versuchen, "gmail.com" und andere Domänen zu spoofen, die "TMS.MX.com" Spoof versuchen, werden weiterhin durch Spoof Intelligence geschützt.

## <a name="related-topics"></a>Verwandte Themen

[Schutz gegen Spoofing in Microsoft 365](anti-spoofing-protection.md)
