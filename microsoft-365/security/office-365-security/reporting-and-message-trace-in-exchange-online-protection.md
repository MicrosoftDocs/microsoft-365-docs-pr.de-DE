---
title: Berichterstellung und Nachrichtenablaufverfolgung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie mehr über Berichte und Problembehandlungstools, die Microsoft Exchange Online (EOP)-Administratoren zur Verfügung stehen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 783c7ea0aca47c805daf66592b401a98f739d071
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288079"
---
# <a name="reporting-and-message-trace-in-eop"></a>Berichterstellung und Nachrichtenverfolgung in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer bietet EOP viele verschiedene Berichte, mit denen Sie den Allgemeinen Status und die Integrität Ihrer Organisation ermitteln können. Außerdem gibt es Tools, mit denen Sie die Problembehebung für bestimmte Ereignisse (wenn beispielsweise eine Nachricht nicht beim gewünschten Empfänger ankommt) durchführen können, sowie Überwachungsberichte zur Einhaltung von Vorschriften.

## <a name="usage-reports"></a>Verwendungsberichte

**Microsoft 365-Gruppenaktivität:** Anzeigen von Informationen zur Anzahl der Microsoft 365-Gruppen, die erstellt und verwendet werden.

**E-Mail-Aktivität:** Zeigen Sie Informationen über die Anzahl von Nachrichten an, die in Ihrer gesamten Organisation sowie von bestimmten Benutzern gesendet, empfangen und gelesen wurden.

**E-Mail-App-Nutzung:** Informationen zu den verwendeten E-Mail-Apps anzeigen. Diese umfassen die Gesamtzahl der Verbindungen für die einzelnen Apps und die Versionen von Outlook, die eine Verbindung herstellen.

**Postfachnutzung:** Informationen zu verwendeter Speichernutzung, Kontingentnutzung, Elementanzahl und letzter Aktivität (Senden oder Lesen) für Postfächer anzeigen.

Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Microsoft 365-Berichte im Admin Center – Microsoft 365-Gruppen](../../admin/activity-reports/office-365-groups.md)

- [Microsoft 365-Berichte im Admin Center – E-Mail-Aktivität](../../admin/activity-reports/email-activity.md)

- [Microsoft 365-Berichte im Admin Center – Nutzung von E-Mail-Apps](../../admin/activity-reports/email-apps-usage.md)

- [Microsoft 365-Berichte im Admin Center – Postfachnutzung](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Sicherheitsberichte & Complianceberichte im Microsoft 365 Admin Center

Diese erweiterten Berichte bieten eine interaktive Berichterstellung für EOP-Administratoren, die Zusammenfassungsinformationen und das Anzeigen von Detailinformationen umfasst.

**Defender für Office 365**: Anzeigen von Informationen zu sicheren Links und sicheren Anlagen, die Teil von Microsoft Defender für Office 365 sind.

**EOP:** Anzeigen von Informationen zu Schadsoftwareerkennungen, Spoof-E-Mails, Spamerkennungen und E-Mail-Fluss zu und von Ihrer Organisation.

[Anzeigen von Berichten für Defender für Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Benutzerdefinierte Berichte mit Microsoft Graph

Programmgesteuertes Erstellen von Berichten, die im Admin Center verfügbar sind, mithilfe von Microsoft Graph. Weitere Informationen finden Sie unter [Übersicht über Microsoft Graph](https://docs.microsoft.com/graph/overview) und arbeiten mit Office [365-Verwendungsberichten in Microsoft Graph.](https://docs.microsoft.com/graph/api/resources/report)

## <a name="message-trace"></a>Nachrichtenablaufverfolgung

Ermöglicht das Nachverfolgen von E-Mails auf dem Weg durch EOP. Sie können ermitteln, ob eine E-Mail vom Dienst empfangen, abgelehnt, zurückgestellt oder zugestellt wurde. Außerdem werden die Aktionen der Nachricht gezeigt, bevor diese ihren finalen Status erreicht hat.

Mit diesen Informationen können Sie in effizienter Weise Fragen der Benutzer beantworten, Probleme mit dem Nachrichtenfluss behandeln und Richtlinienänderungen überprüfen und müssen seltener den technischen Support um Unterstützung bitten.

Siehe [Nachrichtenverfolgung im Security & Compliance Center](message-trace-scc.md).

## <a name="audit-logging"></a>Überwachungsprotokollierung

Verfolgt bestimmte Änderungen durch Administratoren Ihrer Organisation. Diese Berichte können Sie zum Behandeln von Konfigurationsproblemen sowie zum Ermitteln der Ursache von Sicherheits- oder Kompatibilitätsproblemen heranziehen. Siehe [Überwachungsberichte in EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Meldung und Verfügbarkeit und Latenz Nachrichtenverfolgungsdaten

In der folgenden Tabelle wird beschrieben, wann und für wie lange EOP-Berichte und Nachrichtenverfolgungsdaten verfügbar sind.

****

|Berichttyp|Daten verfügbar für (Rückwirkungsfrist)|Wartezeit|
|---|---|---|
|Zusammenfassungsberichte zum E-Mail-Schutz|90 Tage|Die Aggregation von Nachrichtendaten ist meistens innerhalb von 24 bis 48 Stunden abgeschlossen. Kleinere inkrementelle, aggregierte Änderungen können bis zu 5 Tage lang auftreten.|
|Detailberichte zum E-Mail-Schutz|90 Tage|Bei Detaildaten, die weniger als 7 Tage alt sind, sollten Daten innerhalb von 24 Stunden erscheinen, sind aber möglicherweise erst 48 Stunden später abgeschlossen. Einige kleinere schrittweise Änderungen können bis zu 5 Tagen dauern. <p> Zum Anzeigen von Detailberichten für Nachrichten, die älter als 7 Tage sind, kann es einige Stunden dauern, bis die Ergebnisse der Nachrichtenablaufverfolgung ausgegeben werden.|
|Daten der Nachrichtenablaufverfolgung|90 Tage|Wenn Sie eine Nachrichtenverfolgung für Nachrichten starten, die weniger als 7 Tage alt sind, sollten die Nachrichten innerhalb von 5-30 Minuten erscheinen.<p> Wenn Sie eine Ablaufverfolgung für Nachrichten ausführen, die älter als 7 Tage sind, kann es einige Stunden dauern, bis Ergebnisse ausgegeben werden.|
|

> [!NOTE]
> Datenverfügbarkeit und Latenz sind gleich, unabhängig davon, ob sie über das Admin Center oder die Remote-PowerShell angefordert werden.
