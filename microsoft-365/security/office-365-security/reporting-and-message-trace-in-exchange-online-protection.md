---
title: Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection
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
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie mehr über Berichte und Problembehandlungstools, die Microsoft Exchange Online Protection (EoP)-Administratoren zur Verfügung stehen.
ms.openlocfilehash: 44b4223b4310a2de1d90f99f8a7af23cc6054f94
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034380"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection

Microsoft Exchange Online Protection (EOP) bietet viele verschiedene Berichte an, mit deren Hilfe Sie den allgemeinen Status und die Integrität Ihrer Organisation ermitteln können. Außerdem gibt es Tools, mit denen Sie die Problembehebung für bestimmte Ereignisse (wenn beispielsweise eine Nachricht nicht beim gewünschten Empfänger ankommt) durchführen können, sowie Überwachungsberichte zur Einhaltung von Vorschriften.

## <a name="usage-reports"></a>Verwendungsberichte

**Microsoft 365 Groups-Aktivität**: Anzeigen von Informationen zur Anzahl von Microsoft 365-Gruppen, die erstellt und verwendet werden.

**E-Mail-Aktivität**: Anzeigen von Informationen zur Anzahl der gesendeten, empfangenen und eingelesenen Nachrichten in ihrer gesamten Organisation und von bestimmten Benutzern.

**E-Mail-App-Nutzung**: Anzeigen von Informationen zu den verwendeten e-Mail-apps Diese umfassen die Gesamtzahl der Verbindungen für die einzelnen Apps und die Versionen von Outlook, die eine Verbindung herstellen.

**Postfachnutzung**: Anzeigen von Informationen zu verwendetem Speicher, Kontingent Verbrauch, Elementanzahl und letzter Aktivität (Sende-oder Leseaktivität) für Postfächer.

Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Microsoft 365-Berichte im Admin Center-Microsoft 365-Gruppen](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [Microsoft 365-Berichte im Admin Center-e-Mail-Aktivität](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [Microsoft 365-Berichte im Admin Center-Nutzung von e-Mail-apps](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [Microsoft 365-Berichte im Admin Center-Postfachnutzung](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Security & Compliance Reports im Microsoft 365 Admin Center

Diese erweiterten Berichte bieten eine interaktive Berichterstellung für EOP-Administratoren, die Zusammenfassungsinformationen und das Anzeigen von Detailinformationen umfasst.

**Advanced Threat Protection (ATP)**: Hier finden Sie Informationen über sichere Links und sichere Anlagen, die Teil von ATP sind.

**EoP**: Anzeigen von Informationen zu Malwareerkennungen, gefälschten e-Mails, Spamerkennungen und dem Nachrichtenfluss zu und von Ihrer Organisation.

[Anzeigen von Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Benutzerdefinierte Berichte mit Microsoft Graph

Programmgesteuertes Erstellen von Berichten, die im Microsoft 365 Admin Center mithilfe von Microsoft Graph verfügbar sind. Lesen Sie die Unterthemen zum [Arbeiten mit Office 365 Verwendungsberichten in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).

## <a name="custom-reports-using-microsoft-graph"></a>Benutzerdefinierte Berichte mit Microsoft Graph

Programmgesteuertes Erstellen von Berichten. Siehe [Übersicht über Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="message-trace"></a>Nachrichtenablaufverfolgung

Ermöglicht das Nachverfolgen von E-Mails auf dem Weg durch EOP. Sie können ermitteln, ob eine E-Mail vom Dienst empfangen, abgelehnt, zurückgestellt oder zugestellt wurde. Außerdem werden die Aktionen der Nachricht gezeigt, bevor diese ihren finalen Status erreicht hat.

Mit diesen Informationen können Sie in effizienter Weise Fragen der Benutzer beantworten, Probleme mit dem Nachrichtenfluss behandeln und Richtlinienänderungen überprüfen und müssen seltener den technischen Support um Unterstützung bitten.

Siehe [Ablaufverfolgung einer e-Mail-Nachricht](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)

## <a name="audit-logging"></a>Überwachungsprotokollierung

Verfolgt bestimmte Änderungen durch Administratoren Ihrer Organisation. Diese Berichte können Sie zum Behandeln von Konfigurationsproblemen sowie zum Ermitteln der Ursache von Sicherheits- oder Kompatibilitätsproblemen heranziehen. Siehe [Überwachungsberichte in EoP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Meldung und Verfügbarkeit und Latenz Nachrichtenverfolgungsdaten

In der folgenden Tabelle wird beschrieben, wann und für wie lange EOP-Berichte und Nachrichtenverfolgungsdaten verfügbar sind.

||||
|:-----|:-----|:-----|
|**Berichttyp**|**Daten verfügbar für (Rückwirkungsfrist)**|**Latenz**|
|Zusammenfassungsberichte zum E-Mail-Schutz|90 Tage|Die Aggregation von Nachrichtendaten ist meistens innerhalb von 24 bis 48 Stunden abgeschlossen. Kleinere inkrementelle, aggregierte Änderungen können bis zu 5 Tage lang auftreten.|
|Detailberichte zum E-Mail-Schutz|90 Tage|Bei Detaildaten, die weniger als 7 Tage alt sind, sollten Daten innerhalb von 24 Stunden erscheinen, sind aber möglicherweise erst 48 Stunden später abgeschlossen. Einige kleinere schrittweise Änderungen können bis zu 5 Tagen dauern. <br/><br/> Zum Anzeigen von Detailberichten für Nachrichten, die älter als 7 Tage sind, kann es einige Stunden dauern, bis die Ergebnisse der Nachrichtenablaufverfolgung ausgegeben werden.|
|Daten der Nachrichtenablaufverfolgung|90 Tage|Wenn Sie eine Nachrichtenverfolgung für Nachrichten starten, die weniger als 7 Tage alt sind, sollten die Nachrichten innerhalb von 5-30 Minuten erscheinen.<br/><br/> Wenn Sie eine Ablaufverfolgung für Nachrichten ausführen, die älter als 7 Tage sind, kann es einige Stunden dauern, bis Ergebnisse ausgegeben werden.|

> [!NOTE]
> Datenverfügbarkeit und-Wartezeit sind identisch, unabhängig davon, ob Sie über das Microsoft 365 Admin Center oder Remote-PowerShell angefordert werden.
