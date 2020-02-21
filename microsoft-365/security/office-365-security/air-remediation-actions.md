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
ms.openlocfilehash: 1a39ffb5bf57e0f4ffa38a210c299480d3081345
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175929"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Behebungsaktionen nach einer automatisierten Untersuchung in Office 365

## <a name="remediation-actions-overview"></a>Übersicht über Behebungsaktionen

Zu den [automatisierten Ermittlungs-und Antwortfunktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection gehören bestimmte Korrekturaktionen. Wenn eine automatische Untersuchung ausgeführt wird oder abgeschlossen ist, wird in der Regel eine oder mehrere Korrekturaktionen angezeigt, die von Ihrem Sicherheits Betriebsteam genehmigt werden müssen, um den Vorgang fortzusetzen. In der folgenden Tabelle sind die derzeit in Office 365 Advanced Threat Protection verfügbaren Korrekturaktionen zusammengefasst. 

|Aktion | Beschreibung |
|-----|-----|
|URL blockieren (Zeitpunkt des Klickens) |Schutz vor e-Mails und Dokumenten, die bösartige URLs enthalten. Auf diese Weise können böswillige Links und Verwandte Webseiten über [sichere Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) blockiert werden, wenn der Benutzer auf einen Link in einer vorhandenen Office-Datei oder in einer älteren e-Mail-Nachricht klickt. |
|Weiche e-Mail löschen  |Weiche Löschen bestimmter e-Mail-Nachrichten aus dem Postfach eines Benutzers|
|E-Mail-Cluster mit Soft Delete  |Soft Delete böswillige e-Mail-Nachrichten, die einer Abfrage aus den Postfächern aller Benutzer entsprechen|
|Externe E-Mail-Weiterleitung deaktivieren |Entfernt die Weiterleitungsregel aus dem Postfach eines bestimmten Endbenutzers.|

## <a name="approve-or-reject-pending-actions"></a>Genehmigen (oder ablehnen) Ausstehende Aktionen

![Seite "Luft Ermittlungsaktionen"](../../media/air-investigationactionspage.png)

Während Sie die [Details einer Untersuchung](air-view-investigation-results.md)anzeigen, können Sie alle ausstehenden Korrekturaktionen genehmigen oder ablehnen. Wir empfehlen, dies so schnell wie möglich zu tun, damit Ihre automatisierten Untersuchungen abgeschlossen werden.

> [!IMPORTANT]
> Geeignete Berechtigungen sind erforderlich, um Korrekturaktionen zu genehmigen oder abzulehnen. Siehe [erforderliche Berechtigungen für die Verwendung von Air-Funktionen](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).

1. Klicken Sie auf die Registerkarte **Aktionen** .

2. W?hlen Sie ein Element in der Liste aus. (Dadurch werden die Schaltflächen genehmigen und ablehnen aktiviert.)

3. Überprüfen Sie die verfügbaren Informationen für die ausgewählten Elemente, und genehmigen oder lehnen Sie die Aktion (en) dann entweder ab. 

 - Mit **genehmigen** kann die Wiederherstellung beginnen.
 - **Reject** nimmt keine weiteren Aktionen vor

## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu automatisierten Untersuchungen und Antworten in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)