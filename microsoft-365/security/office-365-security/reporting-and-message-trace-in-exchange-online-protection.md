---
title: Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) bietet viele verschiedene Berichte an, mit deren Hilfe Sie den allgemeinen Status und die Integrität Ihrer Organisation ermitteln können. Außerdem gibt es Tools, mit denen Sie die Problembehebung für bestimmte Ereignisse (wenn beispielsweise eine Nachricht nicht beim gewünschten Empfänger ankommt) durchführen können, sowie Überwachungsberichte zur Einhaltung von Vorschriften. In der folgenden Tabelle sind die für EOP-Administratoren verfügbaren Berichte und Problembehandlungstools beschrieben.
ms.openlocfilehash: 81b4ce3d22fbf33dc2f22a4b0a73a3459b1874ee
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441412"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection

Microsoft Exchange Online Protection (EOP) bietet viele verschiedene Berichte an, mit deren Hilfe Sie den allgemeinen Status und die Integrität Ihrer Organisation ermitteln können. Außerdem gibt es Tools, mit denen Sie die Problembehebung für bestimmte Ereignisse (wenn beispielsweise eine Nachricht nicht beim gewünschten Empfänger ankommt) durchführen können, sowie Überwachungsberichte zur Einhaltung von Vorschriften.

## <a name="usage-reports"></a>Verwendungsberichte

**Office 365 Groups-Aktivität**: dient zum Anzeigen von Informationen zur Anzahl der Office 365 Gruppen, die erstellt und verwendet werden.

**E-Mail-Aktivität**: Anzeigen von Informationen zur Anzahl der gesendeten, empfangenen und eingelesenen Nachrichten in ihrer gesamten Organisation und von bestimmten Benutzern.

**E-Mail-App-Nutzung**: Anzeigen von Informationen zu den verwendeten e-Mail-apps Diese umfassen die Gesamtzahl der Verbindungen für die einzelnen Apps und die Versionen von Outlook, die eine Verbindung herstellen.

**Postfachnutzung**: Anzeigen von Informationen zu verwendetem Speicher, Kontingent Verbrauch, Elementanzahl und letzter Aktivität (Sende-oder Leseaktivität) für Postfächer.

Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Office 365 von Berichten im Admin Center – Office 365 Gruppen](https://go.microsoft.com/fwlink/p/?linkid=861610)

- [Office 365-Berichte im Admin Center - E-Mail-Aktivitäten](https://go.microsoft.com/fwlink/p/?linkid=859706)

- [Office 365-Berichte im Admin Center - Nutzung der E-Mail-Apps](https://go.microsoft.com/fwlink/p/?linkid=859707)

- [Office 365-Berichte im Admin Center - Postfachnutzung](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Security #a0 Compliance Reports im Microsoft 365 Admin Center

Diese erweiterten Berichte bieten eine interaktive Berichterstellung für EOP-Administratoren, die Zusammenfassungsinformationen und das Anzeigen von Detailinformationen umfasst.

**Advanced Threat Protection (ATP)**: Hier finden Sie Informationen über sichere Links und sichere Anlagen, die Teil von ATP sind.

**EoP**: Anzeigen von Informationen zu Malwareerkennungen, gefälschten e-Mails, Spamerkennungen und dem Nachrichtenfluss zu und von Ihrer Organisation.

[Anzeigen der Berichte zu Advanced Threat Protection und Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=852409)

## <a name="custom-reports-using-microsoft-graph"></a>Benutzerdefinierte Berichte mit Microsoft Graph

Programmgesteuertes Erstellen von Berichten, die im Microsoft 365 Admin Center mithilfe von Microsoft Graph verfügbar sind siehe Unterthemen [Arbeiten mit Office 365 Verwendungsberichten in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)

## <a name="custom-reports-using-reporting-web-services"></a>Benutzerdefinierte Berichte mit Berichtswebdiensten

Programmgesteuertes Erstellen von Berichten aus den verfügbaren Exchange Online Protection PowerShell Reporting-Cmdlets mithilfe der Rest/ODATA2-Abfrage Filterung.

Siehe [Office 365 Berichts Webdienste](https://go.microsoft.com/fwlink/p/?LinkId=279926)

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
