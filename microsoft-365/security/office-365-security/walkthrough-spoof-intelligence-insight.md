---
title: 'Exemplarische Vorgehensweise: Erkenntnisse der Spoofintelligenz'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie der Einblick in die Spoof-Intelligenz funktioniert. Sie können schnell ermitteln, welche Absender E-Mails rechtmäßig von Domänen an ihre Organisationen senden, die keine E-Mail-Authentifizierungsprüfungen bestehen (SPF, DKIM oder DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc53d49401afe3a0d7871bf5f294126315aacfec
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908094"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Exemplarische Vorgehensweise – Einblick in Spoof Intelligence in Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Defender für Office 365 können Sie mithilfe der Spoof Intelligence-Einsicht schnell ermitteln, welche externen Absender Ihnen legitimerweise nicht authentifizierte E-Mails senden (Nachrichten von Domänen, die SPF-, DKIM- oder DMARC-Prüfungen nicht bestehen).

Indem Sie bekannten externen Absendern das Senden gefälschter Nachrichten von bekannten Speicherorten erlauben, können Sie falsch positive Ergebnisse reduzieren (gute E-Mails sind als schlecht gekennzeichnet). Durch die Überwachung der zugelassenen gefälschten Absender bieten Sie eine zusätzliche Sicherheitsebene, um zu verhindern, dass unsichere Nachrichten in Ihrer Organisation ankommen.

Weitere Informationen zu Berichten und Erkenntnissen finden Sie unter Berichte und Einblicke [im Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).

Diese exemplarische Vorgehensweise ist eine von mehreren für das Security & Compliance Center. Informationen zum Navigieren in Berichten und Einblicken finden Sie in den exemplarischen Vorgehensweisen im Abschnitt [Verwandte](#related-topics) Themen.

> [!NOTE]
> Der Einblick in spoof intelligence zeigt Daten aus den letzten 7 Tagen. Die [Spoof Intelligence-Richtlinie](learn-about-spoof-intelligence.md) und das entsprechende [Get-PhishFilterPolicy-Cmdlet](/powershell/module/exchange/get-phishfilterpolicy) in Exchange Online PowerShell zeigen Daten aus den letzten 30 Tagen an. Der [Get-SpoofMailReport](/powershell/module/exchange/get-spoofmailreport) zeigt Daten für bis zu 90 Tage an.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Sicherheitsdashboard zu** wechseln, verwenden Sie <https://protection.office.com/searchandinvestigation/dashboard> .

  Sie können den Einblick in spoof intelligence aus mehreren Dashboards im Security & Compliance Center anzeigen. Unabhängig davon, welches Dashboard Sie betrachten, bietet der Einblick die gleichen Details und ermöglicht Es Ihnen, schnell die gleichen Aufgaben auszuführen.

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - **Organisationsverwaltung**
  - **Sicherheitsadministrator**
  - **Security Reader**
  - **Globaler Leser**

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweis**: Das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center bietet Benutzern die erforderlichen Berechtigungen im Security & Compliance _Center_ und Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

- Sie aktivieren und deaktivieren spoof intelligence in Antiphishingrichtlinien in Microsoft Defender für Office 365. Spoof intelligence ist standardmäßig aktiviert. Weitere Informationen finden Sie unter [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

- Informationen zur Verwendung von Spoof Intelligence zum Überwachen und Verwalten von Absendern, die Ihnen nicht authentifizierte Nachrichten senden, finden Sie unter [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Öffnen Sie den Einblick in spoof intelligence im Security & Compliance Center

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Dashboard.**

2. Suchen Sie **in** der Zeile Insights nach einem der folgenden Elemente:

   - **Wahrscheinlich spoofierte Domänen in** den letzten sieben Tagen: Diese Einsicht gibt an, dass Spoofintelligenz aktiviert ist (standardmäßig aktiviert).
   - **Spoofschutz** aktivieren: Diese Einsicht zeigt an, dass die Spoofintelligenz deaktiviert ist, und wenn Sie auf die Einblicke klicken, können Sie die Spoofintelligenz aktivieren.

3. Die Einblicke im Dashboard zeigen Ihnen Informationen wie dies:

   ![Screenshot der Einblicke in spoof intelligence](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Diese Einsicht hat zwei Modi:

   - **Einblicksmodus:** Wenn spoof intelligence aktiviert ist, zeigt die Einsicht, wie viele Nachrichten in den letzten sieben Tagen von unseren Funktionen für spoof intelligence betroffen waren.
   - **Was wäre,** wenn Der Modus : Wenn die Spoofintelligenz deaktiviert ist, zeigt die Einsicht, wie viele Nachrichten in den letzten sieben Tagen von unseren Funktionen für spoof intelligence betroffen waren. 

   So oder so sind die spoofierten Domänen, die in der Einsicht angezeigt werden, in zwei Kategorien unterteilt: Verdächtige **Domänen** und **Nicht verdächtige Domänen.**

   - **Verdächtige** Domänen sind:

     - Hochsicherer Spoof: Basierend auf den historischen Sendemustern und der Reputationsnote der Domänen sind wir sehr sicher, dass die Domänen Spoofing sind, und Nachrichten von diesen Domänen sind mit hoher Wahrscheinlichkeit bösartig.

     - Moderater Konfidenzs spoof: Basierend auf historischen Sendemustern und der Reputationsnote der Domänen sind wir moderat davon überzeugt, dass die Domänen Spoofing sind und dass nachrichten, die von diesen Domänen gesendet werden, legitim sind. Falsch positive Ergebnisse sind in dieser Kategorie wahrscheinlicher als spoof mit hoher Wahrscheinlichkeit.

   **Nicht verdächtige Domänen:** Die explizite E-Mail-Authentifizierung der Domäne hat [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC nicht überprüft.](use-dmarc-to-validate-email.md) Die Domäne hat jedoch unsere impliziten E-Mail-Authentifizierungsprüfungen ([zusammengesetzte Authentifizierung](email-validation-and-authentication.md#composite-authentication)) bestanden. Aus diesem Grund wurde keine Antis spoofing-Aktion für die Nachricht ergriffen.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Anzeigen detaillierter Informationen zu verdächtigen Domänen aus dem Einblick in spoof intelligence

1. Klicken Sie auf der Einblicksseite  spoof intelligence auf Verdächtige **Domänen** oder nicht verdächtige Domänen, um zur **Seite Spoof Intelligence Insight zu** wechseln. Die **Seite Spoof Intelligence Insight** enthält die folgenden Informationen:

   - **Spoofed domain:** Die Domäne des spoofierten Benutzers, die im Feld **Von** in E-Mail-Clients angezeigt wird. Diese Adresse wird auch als Adresse `5322.From` bezeichnet.
   - **Infrastruktur**: Wird auch als sendende _Infrastruktur bezeichnet._ Die Domäne in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers. Wenn die Quell-IP-Adresse keinen PTR-Eintrag enthält, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).
   - **Nachrichtenanzahl**: Die Anzahl der Nachrichten aus der sendenden Infrastruktur an Ihre Organisation, die die angegebene spoofed-Domäne innerhalb der letzten 7 Tage enthalten.
   - **Zuletzt gesehen:** Das letzte Datum, an dem eine Nachricht von der sendenden Infrastruktur empfangen wurde, die die spoofierte Domäne enthält.
   - **Spooftyp**: Dieser Wert ist **External**.
   - **Darf ges spooft werden?**: Die hier angezeigten Werte sind:
     - **Ja:** Nachrichten aus der Kombination aus der Domäne des spoofierten Benutzers und der Sendeinfrastruktur sind zulässig und werden nicht als gefälschte E-Mails behandelt.
     - **Nein:** Nachrichten aus der Kombination aus der Domäne des spoofierten Benutzers und der sendenden Infrastruktur werden als Spoofing gekennzeichnet. Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist **Move message to Junk Email folder**).

     Weitere Informationen finden Sie unter [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

2. Wählen Sie ein Element in der Liste aus, um Details zum Domänen-/Sendeinfrastrukturpaar in einem Flyout anzuzeigen. Die Informationen umfassen:
   - Warum wir dies erwischt haben.
   - Was Sie tun müssen.
   - Eine Domänenzusammenfassung.
   - WhoIs-Daten über den Absender.
   - Ähnliche Nachrichten, die wir in Ihrem Mandanten vom gleichen Absender gesehen haben.

   Von hier aus können Sie auch das Domänen-/Sendeinfrastrukturpaar aus der Liste zugelassener Absender **spoofieren** hinzufügen oder entfernen. Legen Sie einfach die Umschalte entsprechend ein.

   ![Screenshot einer Domäne im Detailbereich "Spoof Intelligence Insight"](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Hinzufügen einer Domäne zur Liste zugelassener Spoofs

Das Hinzufügen einer Domäne zur Liste zugelassener Spoofings aus dem Einblick in spoof intelligence ermöglicht nur die Kombination der spoofierten Domäne *und* der sendenden Infrastruktur. Es lässt weder E-Mails von der spoofierten Domäne von einer Quelle noch E-Mails von der sendenden Infrastruktur für eine Beliebige Domäne zu.

Beispielsweise können Sie die folgende Domäne in der Liste Zugelassenes Spoofen zulassen:

- **Domäne**: gmail.com
- **Infrastruktur**: tms.mx.com

Nur E-Mails von diesem Domänen-/Sendeinfrastrukturpaar dürfen spoofen. Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig. Nachrichten in anderen Domänen von tms.mx.com werden durch Spoof intelligence überprüft.

## <a name="related-topics"></a>Verwandte Themen

[Schutz vor Spoofing in Microsoft 365](anti-spoofing-protection.md)