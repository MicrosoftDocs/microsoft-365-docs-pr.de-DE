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
ms.openlocfilehash: 6f5ebd0fd42d17354eeb1e03c946ac5446c3667c
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572741"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Exemplarische Vorgehensweise – Spoof Intelligence Insight in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Defender for Office 365 können Sie die Spoof Intelligence-Einblicke verwenden, um schnell zu ermitteln, welche Absender legitimerweise nicht authentifizierte e-Mails senden (Nachrichten von Domänen, die keine SPF-, DKIM-oder DMARC-Überprüfungen durchführen).

Wenn Sie zulassen, dass bekannte Absender gefälschte Nachrichten von bekannten Speicherorten senden, können Sie falsch positive Ergebnisse reduzieren (gute e-Mail-Nachrichten sind als ungültig markiert). Durch Überwachen der zulässigen gefälschten Absender stellen Sie eine zusätzliche Sicherheitsebene bereit, um zu verhindern, dass unsichere Nachrichten in Ihrer Organisation eingehen.

Weitere Informationen zu Berichten und Einblicken finden Sie unter [Reports and Insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).

Diese exemplarische Vorgehensweise ist eine von mehreren für das Security & Compliance Center. Informationen zum Navigieren in Berichten und Einblicken finden Sie unter Exemplarische Vorgehensweisen im Abschnitt " [Verwandte Themen](#related-topics) ".

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Security Dashboard** zu wechseln, verwenden Sie <https://protection.office.com/searchandinvestigation/dashboard> .

  Sie können die Einblicke in Spoof Intelligence aus mehreren Dashboards im Security & Compliance Center anzeigen. Unabhängig davon, für welches Dashboard Sie sich interessieren, bietet die Insight dieselben Details und ermöglicht Ihnen, schnell dieselben Aufgaben auszuführen.

- Sie müssen Berechtigungen im Security & Compliance Center zugewiesen werden, bevor Sie die Verfahren in diesem Artikel ausführen können:
  - **Organisationsverwaltung**
  - **Sicherheits Administrator**
  - **Sicherheits Leser**
  - **Globaler Leser**

  **Hinweis**: beim Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

- Sie aktivieren und deaktivieren Spoof Intelligence in Anti-Phishing-Richtlinien in Microsoft Defender für Office 365. Weitere Informationen finden Sie unter [configure Anti-Phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

- Informationen zum Verwenden von Spoof Intelligence zum Überwachen und Verwalten von Absendern, die nicht authentifizierte Nachrichten senden, finden Sie unter [configure Spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Öffnen Sie die Spoof Intelligence-Einblicke im Security & Compliance Center.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Dashboard.**

2. Suchen Sie in der Zeile **Insights** nach einem der folgenden Elemente:

   - **Spoof Intelligence ist aktiviert**: die Einblicke werden als **gefälschte Domänen bezeichnet, bei denen die Authentifizierung der letzten 30 Tage nicht erfolgreich** war. Dies ist die Standardeinstellung.
   - **Spoof Intelligence ist deaktiviert**: die Einblicke in benannten **aktivieren Spoof Protection**, und klicken Sie auf Sie können Sie Spoof Intelligence aktivieren.

3. Die Einblicke in das Dashboard zeigt Ihnen Informationen wie die folgende:

   ![Screenshot von Spoof Intelligence Insight](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Diese Einblicke umfasst zwei Modi:

   - **Insight-Modus**: Wenn Spoof Intelligence aktiviert ist, zeigt Ihnen die Einblicke, wie viele Nachrichten in den letzten 30 Tagen durch unsere Spoof Intelligence-Funktionen beeinflusst wurden.

   - **Was** ist, wenn-Modus: Wenn Spoof Intelligence deaktiviert ist, dann zeigt Ihnen die Einsicht, wie viele Nachrichten in den letzten 30 Tagen von unseren Spoof Intelligence-Funktionen betroffen *wären* .

   In beiden Fällen werden die in der Insight angezeigten gefälschten Domänen in zwei Kategorien unterteilt: **verdächtige Domänen Paare** und **nicht verdächtige Domänen Paare**. Diese Kategorien werden weiter in drei verschiedene Buckets unterteilt, die Sie überprüfen können.

   Ein **Domänenpaar** ist eine Kombination aus der von-Adresse und der sendenden Infrastruktur:

   - Die Absenderadresse ist die e-Mail-Adresse des Absenders, die im Feld von in e-Mail-Clients angezeigt wird. Diese Adresse wird auch als Adresse bezeichnet `5322.From` .

   - Die sendende Infrastruktur oder der Absender ist die Organisationsdomäne des Reverse-DNS-Lookups (PTR-Eintrags) der sendenden IP-Adresse. Wenn die sendende IP-Adresse keinen PTR-Eintrag hat, wird der Absender von der sendenden IP mit der Subnetzmaske 255.255.255.0 in der CIDR-Notation (/24) identifiziert. Wenn die IP-Adresse beispielsweise 192.168.100.100 lautet, lautet die vollständige IP-Adresse des Absenders 192.168.100.100/24.

   Zu den **verdächtigen Domänen Paaren** gehören:

   - **Spoofing mit hoher Vertrauens** Würdigkeit: basierend auf den Verlaufs Sende Mustern und dem Reputations Ergebnis der Domänen sind wir sehr zuversichtlich, dass die Domänen Spoofing sind und Nachrichten aus diesen Domänen eher bösartig sind.

   - **Gemäßigte Vertrauens Parodie**: basierend auf Verlaufs Sende Mustern und dem Reputationswert der Domänen sind wir mit mittlerer Zuversicht überzeugt, dass die Domänen Spoofing sind und dass von diesen Domänen gesendete Nachrichten legitim sind. Falsch positive Ergebnisse sind in dieser Kategorie eher als hochgradig vertrauenswürdige Spoofing.

   - **Nicht verdächtige Domänen Paare** (einschließlich **geretteter Spoofing**): die Domänen-fehlgeschlagene explizite e-Mail-Authentifizierung überprüft [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)). Die Domäne bestanden jedoch unsere impliziten e-Mail-Authentifizierungsprüfungen ([kombinierte Authentifizierung](email-validation-and-authentication.md#composite-authentication)). Dies hat zur Folge, dass keine Anti-Spoofing-Aktion für die Nachricht durchgeführt wurde.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Anzeigen detaillierter Informationen zu verdächtigen Domänen Paaren aus dem Spoof Intelligence-Insight

1. Klicken Sie auf der Spoof Intelligence-Einblicke auf eines der Domänen Paare (hoch, moderat oder gerettet).

   Die Seite **Spoof Intelligence Insight** wird angezeigt. Auf der Seite wird eine Liste mit Absendern angezeigt, die nicht authentifizierte e-Mails an Ihre Organisation senden.

   Anhand dieser Informationen können Sie bestimmen, ob gefälschte Nachrichten autorisiert sind oder ob Sie weitere Aktionen ausführen müssen.

   Sie können die Informationen nach Nachrichtenanzahl, dem Datum, an dem die Spoof zuletzt erkannt wurde, und vieles mehr sortieren.

2. Wählen Sie ein Element in der Tabelle aus, um einen Detailbereich mit umfangreichen Informationen zum Domänenpaar zu öffnen. Die Informationen umfassen Folgendes:
   - Warum wir dies erwischt haben.
   - Was Sie tun müssen.
   - Eine Domänen Zusammenfassung.
   - Whois-Daten über den Absender.
   - Ähnliche Nachrichten, die wir in Ihrem Mandanten vom gleichen Absender gesehen haben.

   Von hier aus können Sie auch das Domänenpaar aus der Liste sicherer Absender von **AllowedToSpoof** hinzufügen oder entfernen.

   ![Screenshot einer Domäne im Detailbereich "Spoof Intelligence Insight"](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a>Hinzufügen oder Entfernen einer Domäne aus der AllowedToSpoof-Liste

Sie fügen oder entfernen eine Domäne aus der Liste AllowedToSpoof (Safe Sender) im Detailbereich des Spoof Intelligence Insight für das Domänenpaar. Legen Sie die Umschaltfläche einfach entsprechend fest.

Wenn ein Domänenpaar nur zugelassen wird, ist die Kombination aus der gefälschten Domäne *und* der sendenden Infrastruktur möglich. Es werden keine e-Mails von der gefälschten Domäne aus einer beliebigen Quelle zugelassen, und es werden keine e-Mails von der sendenden Infrastruktur für eine beliebige Domäne zugelassen.

Beispielsweise können Sie dem folgenden Domänenpaar Spoofing-Nachrichten an Ihre Organisation senden:

- *Spoofing-Domäne*: gmail.com "
- *Sendende Infrastruktur* `tms.mx.com` :

Nur e-Mails von diesem Domänenpaar dürfen Spoofing durchgehen. Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig. Nachrichten in anderen Domänen von TMS.MX.com werden durch Spoof Intelligence überprüft.

## <a name="related-topics"></a>Verwandte Themen

[Schutz gegen Spoofing in Microsoft 365](anti-spoofing-protection.md)
