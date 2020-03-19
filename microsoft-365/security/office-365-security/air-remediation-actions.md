---
title: Korrekturaktionen in Office 365 automatisierte Untersuchung und Antwort
keywords: Luft, autoIR, ATP, automatisiert, Untersuchung, Antwort, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Erfahren Sie mehr Überkorrektur Aktionen in automatisierten Ermittlungs-und Antwortfunktionen in Office 365 Advanced Threat Protection-Plan 2.
ms.openlocfilehash: 2efe0124304a9f9dcfdc92b548c850882ad507a0
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836858"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Behebungsaktionen nach einer automatisierten Untersuchung in Office 365

## <a name="remediation-actions"></a>Wartungsaktionen

Zu den [automatischen Ermittlungs-und Antwortfunktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 gehören bestimmte Korrekturaktionen. Wenn eine automatische Untersuchung ausgeführt wird oder abgeschlossen ist, wird in der Regel eine oder mehrere Korrekturaktionen angezeigt, die von Ihrem Sicherheits Betriebsteam genehmigt werden müssen, um den Vorgang fortzusetzen. 

In der folgenden Tabelle sind die derzeit in Office 365 ATP verfügbaren Korrekturaktionen zusammengefasst. 

|Aktion | Beschreibung |
|-----|-----|
|URL blockieren (Zeitpunkt des Klickens) |Schützt vor e-Mail-Nachrichten und Dokumenten, die bösartige URLs enthalten. Auf diese Weise können böswillige Links und Verwandte Webseiten über [sichere Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) blockiert werden, wenn der Benutzer auf einen Link in einer vorhandenen Office-Datei oder in einer älteren e-Mail-Nachricht klickt. |
|Weiche e-Mail löschen  |Weiche Löschen bestimmter e-Mail-Nachrichten aus dem Postfach eines Benutzers. <br/>Eine vorläufig gelöschte Nachricht wird in den Ordner "Wiederherstellbare Elemente" des Benutzers verschoben und so lange aufbewahrt, bis der Aufbewahrungszeitraum für gelöschte Elemente abläuft. |
|E-Mail-Cluster mit Soft Delete  |Soft Delete böswillige e-Mail-Nachrichten, die einer Abfrage aus den Postfächern aller Benutzer entsprechen. <br/>Vorläufig gelöschte Nachrichten werden in den Ordner "Wiederherstellbare Elemente" der Benutzer verschoben und bis zum Ablauf des Aufbewahrungszeitraums für gelöschte Elemente beibehalten. |
|Externe E-Mail-Weiterleitung deaktivieren |Entfernt eine Weiterleitungsregel aus dem Postfach eines bestimmten Endbenutzers.|

> [!NOTE]
> In Office 365 ATP werden keine Korrekturaktionen automatisch durchgeführt. Korrekturaktionen werden nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt. 

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen ausstehender oder abgeschlossener Korrekturaktionen nach einer automatisierten Untersuchung in Office 365](air-review-approve-pending-completed-actions.md)

- [Details und Ergebnisse einer automatisierten Untersuchung in Office 365](air-view-investigation-results.md)