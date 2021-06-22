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
description: In diesem Artikel erfahren Sie mehr über Berichte und Problembehandlungstools, die administratoren Microsoft Exchange Online Protection (EOP) zur Verfügung stehen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc49a92d5fb1fb0368b14eef7524638542f38deb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054380"
---
# <a name="reporting-and-message-trace-in-eop"></a>Berichterstellung und Nachrichtenablaufverfolgung in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer bietet EOP viele verschiedene Berichte, die Ihnen helfen können, den Gesamtstatus und den Status Ihrer Organisation zu bestimmen. Außerdem gibt es Tools, mit denen Sie die Problembehebung für bestimmte Ereignisse (wenn beispielsweise eine Nachricht nicht beim gewünschten Empfänger ankommt) durchführen können, sowie Überwachungsberichte zur Einhaltung von Vorschriften.

## <a name="usage-reports"></a>Verwendungsberichte

- **Microsoft 365 Gruppenaktivität:** Zeigen Sie Informationen zur Anzahl der Microsoft 365 Gruppen an, die erstellt und verwendet werden. Weitere Informationen finden Sie unter [Microsoft 365 Berichte im Admin Center – Microsoft 365 Gruppen.](../../admin/activity-reports/office-365-groups.md)
- **E-Mail-Aktivität:** Anzeigen von Informationen über die Anzahl der gesendeten, empfangenen und gelesenen Nachrichten in Ihrer gesamten Organisation und von bestimmten Benutzern. Weitere Informationen finden Sie unter [Microsoft 365 Berichte im Admin Center – E-Mail-Aktivität.](../../admin/activity-reports/email-activity.md)
- **Nutzung von E-Mail-Apps:** Zeigen Sie Informationen zu den verwendeten E-Mail-Apps an. Dies umfasst die Gesamtzahl der Verbindungen für jede App sowie die Versionen von Outlook, die eine Verbindung herstellen. Weitere Informationen finden Sie unter [Microsoft 365 Berichte im Admin Center – Nutzung von E-Mail-Apps.](../../admin/activity-reports/email-apps-usage.md)
- **Postfachnutzung:** Anzeigen von Informationen zum verwendeten Speicher, zum Kontingentverbrauch, zur Elementanzahl und zur letzten Aktivität (Sende- oder Leseaktivität) für Postfächer. Weitere Informationen finden Sie unter [Microsoft 365 Berichte im Admin Center – Postfachnutzung.](../../admin/activity-reports/mailbox-usage.md)

## <a name="security-reports-in-the-microsoft-365-defender-portal"></a>Sicherheitsberichte im Microsoft 365 Defender-Portal

Diese erweiterten Berichte bieten eine interaktive Berichterstellung für EOP-Administratoren, die Zusammenfassungsinformationen und das Anzeigen von Detailinformationen umfasst.

- **Defender für Office 365:** Zeigen Sie Informationen zu Tresor Links und Tresor Anlagen an, die Teil von Microsoft Defender für Office 365 sind. Weitere Informationen finden Sie unter [Anzeigen von Defender für Office 365 Berichte im Microsoft 365 Defender Portal.](view-reports-for-mdo.md)
- **EOP:** Anzeigen von Informationen zu Schadsoftwareerkennungen, gefälschten E-Mails, Spamerkennungen und Nachrichtenfluss zu und von Ihrer Organisation. Weitere Informationen finden Sie unter [Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender Portal.](view-email-security-reports.md)

## <a name="custom-reports-using-microsoft-graph"></a>Benutzerdefinierte Berichte mit Microsoft Graph

Programmgesteuertes Erstellen von Berichten, die im Admin Center mithilfe von Microsoft Graph verfügbar sind. Weitere Informationen finden Sie unter [Übersicht über Microsoft Graph](/graph/overview) und Arbeiten mit Office 365 [Nutzungsberichten in Microsoft Graph.](/graph/api/resources/report)

## <a name="message-trace"></a>Nachrichtenablaufverfolgung

Ermöglicht das Nachverfolgen von E-Mails auf dem Weg durch EOP. Sie können ermitteln, ob eine E-Mail vom Dienst empfangen, abgelehnt, zurückgestellt oder zugestellt wurde. Außerdem werden die Aktionen der Nachricht gezeigt, bevor diese ihren finalen Status erreicht hat.

Mit diesen Informationen können Sie in effizienter Weise Fragen der Benutzer beantworten, Probleme mit dem Nachrichtenfluss behandeln und Richtlinienänderungen überprüfen und müssen seltener den technischen Support um Unterstützung bitten.

Siehe [Nachrichtenablaufverfolgung im Microsoft 365 Defender Portal.](message-trace-scc.md)

## <a name="audit-logging"></a>Überwachungsprotokollierung

Verfolgt bestimmte Änderungen durch Administratoren Ihrer Organisation. Diese Berichte können Sie zum Behandeln von Konfigurationsproblemen sowie zum Ermitteln der Ursache von Sicherheits- oder Kompatibilitätsproblemen heranziehen. Siehe [Überwachungsberichte in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Meldung und Verfügbarkeit und Latenz Nachrichtenverfolgungsdaten

In der folgenden Tabelle wird beschrieben, wann und für wie lange EOP-Berichte und Nachrichtenverfolgungsdaten verfügbar sind.

<br>

****

|Berichttyp|Daten verfügbar für (Rückwirkungsfrist)|Wartezeit|
|---|---|---|
|Zusammenfassungsberichte zum E-Mail-Schutz|90 Tage|Die Aggregation von Nachrichtendaten ist meistens innerhalb von 24 bis 48 Stunden abgeschlossen. Kleinere inkrementelle, aggregierte Änderungen können bis zu 5 Tage lang auftreten.|
|Detailberichte zum E-Mail-Schutz|90 Tage|Bei Detaildaten, die weniger als 7 Tage alt sind, sollten Daten innerhalb von 24 Stunden erscheinen, sind aber möglicherweise erst 48 Stunden später abgeschlossen. Einige kleinere schrittweise Änderungen können bis zu 5 Tagen dauern. <p> Zum Anzeigen von Detailberichten für Nachrichten, die älter als 7 Tage sind, kann es einige Stunden dauern, bis die Ergebnisse der Nachrichtenablaufverfolgung ausgegeben werden.|
|Daten der Nachrichtenablaufverfolgung|90 Tage|Wenn Sie eine Nachrichtenverfolgung für Nachrichten starten, die weniger als 7 Tage alt sind, sollten die Nachrichten innerhalb von 5-30 Minuten erscheinen.<p> Wenn Sie eine Ablaufverfolgung für Nachrichten ausführen, die älter als 7 Tage sind, kann es einige Stunden dauern, bis Ergebnisse ausgegeben werden.|
|

> [!NOTE]
> Datenverfügbarkeit und Latenz sind unabhängig davon, ob sie über das Admin Center oder Remote-PowerShell angefordert werden, identisch.
