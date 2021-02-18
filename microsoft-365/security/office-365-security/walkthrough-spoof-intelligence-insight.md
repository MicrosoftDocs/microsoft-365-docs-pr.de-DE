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
description: Administratoren können erfahren, wie der Einblick in Spoofing Intelligence funktioniert. Sie können schnell ermitteln, welche Absender E-Mails legitimerweise aus Domänen an ihre Organisationen senden, die keine E-Mail-Authentifizierungsprüfungen bestehen (SPF, DKIM oder DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 91cd26498b2a14166f1be10921b9d5b2ea8d583c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287971"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Exemplarische Vorgehensweise – Einblick in Spoofing Intelligence in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Defender für Office 365 können Sie den Einblick in die Spoofintelligenz verwenden, um schnell zu ermitteln, welche externen Absender Ihnen legitimerweise nicht authentifizierte E-Mails senden (Nachrichten von Domänen, die keine SPF-, DKIM- oder DMARC-Überprüfungen bestehen).

Indem Sie bekannten externen Absendern das Senden von gefälschten Nachrichten von bekannten Speicherorten erlauben, können Sie falsch positive Ergebnisse verringern (gute E-Mails sind als "schlecht" gekennzeichnet). Indem Sie die zulässigen gefälschten Absender überwachen, bieten Sie eine zusätzliche Sicherheitsebene, um zu verhindern, dass unsichere Nachrichten in Ihrer Organisation ankommen.

Weitere Informationen zu Berichten und Einblicken finden Sie unter Berichte und Einblicke [im Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).

Diese exemplarische Vorgehensweise ist eine von mehreren für das Security & Compliance Center. Informationen zum Navigieren in Berichten und Einblicken finden Sie in den exemplarischen Vorgehensweisen im Abschnitt ["Verwandte Themen".](#related-topics)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite des **Sicherheitsdashboards zu** wechseln, verwenden Sie <https://protection.office.com/searchandinvestigation/dashboard> .

  Sie können den Einblick in Spoofing Intelligence aus mehreren Dashboards im Security & Compliance Center anzeigen. Unabhängig davon, welches Dashboard Sie betrachten, bietet der Einblick die gleichen Details und ermöglicht Es Ihnen, die gleichen Aufgaben schnell auszuführen.

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - **Organisationsverwaltung**
  - **Sicherheitsadministrator**
  - **Sicherheitsleseprogramm**
  - **Globaler Leser**

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweis:** Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance _Center_ sowie Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

- Sie aktivieren und deaktivieren spoofing intelligence in Antiphishingrichtlinien in Microsoft Defender für Office 365. Spoofintelligenz ist standardmäßig aktiviert. Weitere Informationen finden Sie unter ["Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365".](configure-atp-anti-phishing-policies.md)

- Informationen zur Verwendung von Spoofintelligenz zum Überwachen und Verwalten von Absendern, die Ihnen nicht authentifizierte Nachrichten senden, finden Sie unter Konfigurieren von Spoofintelligenz [in Microsoft 365.](learn-about-spoof-intelligence.md)

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Öffnen des Einblicks für Spoofing Intelligence im Security & Compliance Center

1. Wechseln Sie im Security & Compliance Center zum **Threat Management** \> **Dashboard.**

2. Suchen Sie in der Zeile **"Insights"** nach einem der folgenden Elemente:

   - **Wahrscheinlich gefälschte Domänen** in den letzten sieben Tagen: Dieser Einblick gibt an, dass Spoofintelligenz aktiviert ist (standardmäßig aktiviert).
   - **Aktivieren von Spoofingschutz:** Dieser Einblick weist darauf hin, dass die Spoofintelligenz deaktiviert ist, und wenn Sie auf die Einblicke klicken, können Sie Spoofing Intelligence aktivieren.

3. Die Einblicke im Dashboard zeigen Ihnen Informationen wie die hier gezeigten:

   ![Screenshot von Einblicken in spoofing intelligence](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Dieser Einblick hat zwei Modi:

   - **Einblicksmodus:** Wenn Spoofing Intelligence aktiviert ist, zeigt der Einblick, wie viele Nachrichten in den letzten sieben Tagen von unseren Funktionen für Spoofing intelligence betroffen waren.
   - **Was wäre im** Modus: Wenn Spoofing Intelligence deaktiviert ist, zeigt der Einblick, wie viele Nachrichten in den letzten sieben Tagen von unseren Funktionen für Spoofing Intelligence betroffen waren. 

   In beiden Arten werden die in den Einblicken angezeigten  gefälschten Domänen in zwei Kategorien unterteilt: verdächtige Domänen und **nicht verdächtige Domänen.**

   - **Zu den verdächtigen** Domänen gehören:

     - Spoofing mit hoher Vertrauenswürdigkeit: Basierend auf den historischen Sendemustern und der Bewertung der Domänen sind wir sehr sicher, dass es sich bei den Domänen um Spoofing handelt und Nachrichten von diesen Domänen mit hoher Wahrscheinlichkeit schädlich sind.

     - Moderater Konfidenzs spoofing: Basierend auf historischen Sendemustern und der Bewertung der Reputation der Domänen sind wir moderat sicher, dass die Domänen Spoofing sind und dass nachrichten, die von diesen Domänen gesendet werden, legitim sind. Falsch positive Ergebnisse sind in dieser Kategorie wahrscheinlicher als Spoofing mit hoher Wahrscheinlichkeit.

   **Nicht verdächtige Domänen:** Die Domäne hat die explizite E-Mail-Authentifizierung nicht [überprüft SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)). Die Domäne hat jedoch unsere impliziten E-Mail-Authentifizierungsprüfungen[(zusammengesetzte Authentifizierung) bestanden.](email-validation-and-authentication.md#composite-authentication) Dies hat zur Folge, dass keine Antis spoofing-Aktion für die Nachricht ergriffen wurde.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Anzeigen detaillierter Informationen zu verdächtigen Domänen aus dem Einblick in spoof intelligence

1. Klicken Sie im Einblick in spoofing intelligence auf **verdächtige** Domänen oder nicht verdächtige Domänen, um zur **Seite "Spoofing Intelligence Insight" zu** gelangen.  Die **Seite "Spoof Intelligence Insight"** enthält die folgenden Informationen:

   - **Gefälschte Domäne:** Die Domäne des gefälschten Benutzers, die in E-Mail-Clients im Feld **"Von"** angezeigt wird. Diese Adresse wird auch als Adresse `5322.From` bezeichnet.
   - **Infrastruktur:** Auch als sendende _Infrastruktur bezeichnet._ Die Domäne in einem Reverse-DNS-Lookup (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers. Wenn die Quell-IP-Adresse keinen PTR-Eintrag hat, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).
   - **Anzahl der** Nachrichten: Die Anzahl der Nachrichten von der sendenden Infrastruktur an Ihre Organisation, die die angegebene Spoofdomäne innerhalb der letzten 7 Tage enthalten.
   - **Zuletzt gesehen:** Das letzte Datum, an dem eine Nachricht von der sendenden Infrastruktur empfangen wurde, die die gefälschte Domäne enthält.
   - **Spooftyp:** Dieser Wert ist **extern**.
   - **Spoofing zulässig?**: Die hier angezeigten Werte sind:
     - **Ja:** Nachrichten aus der Kombination aus der Domäne des gefälschten Benutzers und der sendenden Infrastruktur sind zulässig und werden nicht als gefälschte E-Mails behandelt.
     - **Nein:** Nachrichten aus der Kombination aus der Domäne des gefälschten Benutzers und der sendenden Infrastruktur werden als Spoofing gekennzeichnet. Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist "Nachricht in Junk-E-Mail-Ordner **verschieben").**

     Weitere Informationen finden Sie unter [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365.](configure-atp-anti-phishing-policies.md)

2. Wählen Sie ein Element in der Liste aus, um Details zum Domänen-/Sendeinfrastrukturpaar in einem Flyout anzuzeigen. Die Informationen umfassen:
   - Warum wir dies erwischt haben.
   - Was Sie tun müssen.
   - Eine Domänenzusammenfassung.
   - WhoIs-Daten über den Absender.
   - Ähnliche Nachrichten, die wir in Ihrem Mandanten von demselben Absender gesehen haben.

   Von hier aus können Sie auch das Domänen-/Sendeinfrastrukturpaar aus der Liste zugelassener Absender für **Spoofing** hinzufügen oder entfernen. Legen Sie die Umschalt umschalten Sie einfach entsprechend.

   ![Screenshot einer Domäne im Detailbereich "Spoof intelligence insight"](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Hinzufügen einer Domäne zur Liste zugelassener Spoofings

Das Hinzufügen einer Domäne zur Liste zugelassener Spoofings aus dem Einblick  in die Spoofintelligenz lässt nur die Kombination der gefälschten Domäne und der sendenden Infrastruktur zu. Es lässt weder E-Mails von der gefälschten Domäne von einer Quelle noch E-Mails von der sendenden Infrastruktur für eine beliebige Domäne zu.

Beispielsweise können Sie der folgenden Domäne die Liste der zulässigen Spoofings erlauben:

- **Domäne**: gmail.com
- **Infrastruktur:** tms.mx.com

Nur E-Mails von diesem Domänen-/Sendeinfrastrukturpaar dürfen gefälscht werden. Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig. Nachrichten in anderen Domänen von tms.mx.com werden durch Spoofintelligenz überprüft.

## <a name="related-topics"></a>Verwandte Themen

[Antis spoofing protection in Microsoft 365](anti-spoofing-protection.md)
