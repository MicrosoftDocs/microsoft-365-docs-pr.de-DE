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
description: Microsoft Exchange Online Protection (EOP) bietet viele verschiedene Berichte an, mit deren Hilfe Sie den allgemeinen Status und die Integrität Ihrer Organisation ermitteln können. Außerdem gibt es Tools, mit denen Sie die Problembehebung für bestimmte Ereignisse (wenn beispielsweise eine Nachricht nicht beim gewünschten Empfänger ankommt) durchführen können, sowie Überwachungsberichte zur Einhaltung von Vorschriften. In der folgenden Tabelle sind die für EOP-Administratoren verfügbaren Berichte und Problembehandlungstools beschrieben.
ms.openlocfilehash: 282fd032e73ccb8217801a575f6029dbd9fadc9c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598552"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="5578d-105">Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5578d-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="5578d-106">Microsoft Exchange Online Protection (EOP) bietet viele verschiedene Berichte an, mit deren Hilfe Sie den allgemeinen Status und die Integrität Ihrer Organisation ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="5578d-106">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="5578d-107">Außerdem gibt es Tools, mit denen Sie die Problembehebung für bestimmte Ereignisse (wenn beispielsweise eine Nachricht nicht beim gewünschten Empfänger ankommt) durchführen können, sowie Überwachungsberichte zur Einhaltung von Vorschriften.</span><span class="sxs-lookup"><span data-stu-id="5578d-107">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="5578d-108">Verwendungsberichte</span><span class="sxs-lookup"><span data-stu-id="5578d-108">Usage reports</span></span>

<span data-ttu-id="5578d-109">**Office 365 Groups-Aktivität**: dient zum Anzeigen von Informationen zur Anzahl der Office 365 Gruppen, die erstellt und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5578d-109">**Office 365 groups activity**: View information about the number of Office 365 groups that are created and used.</span></span>

<span data-ttu-id="5578d-110">**E-Mail-Aktivität**: Anzeigen von Informationen zur Anzahl der gesendeten, empfangenen und eingelesenen Nachrichten in ihrer gesamten Organisation und von bestimmten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="5578d-110">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="5578d-111">**E-Mail-App-Nutzung**: Anzeigen von Informationen zu den verwendeten e-Mail-apps</span><span class="sxs-lookup"><span data-stu-id="5578d-111">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="5578d-112">Diese umfassen die Gesamtzahl der Verbindungen für die einzelnen Apps und die Versionen von Outlook, die eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="5578d-112">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="5578d-113">**Postfachnutzung**: Anzeigen von Informationen zu verwendetem Speicher, Kontingent Verbrauch, Elementanzahl und letzter Aktivität (Sende-oder Leseaktivität) für Postfächer.</span><span class="sxs-lookup"><span data-stu-id="5578d-113">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="5578d-114">Weitere Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="5578d-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="5578d-115">Office 365-Berichte im Admin Center – Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="5578d-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="5578d-116">Office 365-Berichte im Admin Center - E-Mail-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="5578d-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [<span data-ttu-id="5578d-117">Office 365-Berichte im Admin Center - Nutzung der E-Mail-Apps</span><span class="sxs-lookup"><span data-stu-id="5578d-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="5578d-118">Office 365-Berichte im Admin Center - Postfachnutzung</span><span class="sxs-lookup"><span data-stu-id="5578d-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="5578d-119">Security #a0 Compliance Reports im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="5578d-119">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="5578d-120">Diese erweiterten Berichte bieten eine interaktive Berichterstellung für EOP-Administratoren, die Zusammenfassungsinformationen und das Anzeigen von Detailinformationen umfasst.</span><span class="sxs-lookup"><span data-stu-id="5578d-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="5578d-121">**Advanced Threat Protection (ATP)**: Hier finden Sie Informationen über sichere Links und sichere Anlagen, die Teil von ATP sind.</span><span class="sxs-lookup"><span data-stu-id="5578d-121">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="5578d-122">**EoP**: Anzeigen von Informationen zu Malwareerkennungen, gefälschten e-Mails, Spamerkennungen und dem Nachrichtenfluss zu und von Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="5578d-122">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="5578d-123">Anzeigen von Berichten für Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5578d-123">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="5578d-124">Benutzerdefinierte Berichte mit Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="5578d-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="5578d-125">Programmgesteuertes Erstellen von Berichten, die im Microsoft 365 Admin Center mithilfe von Microsoft Graph verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5578d-125">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph.</span></span> <span data-ttu-id="5578d-126">Lesen Sie die Unterthemen zum [Arbeiten mit Office 365 Verwendungsberichten in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="5578d-126">See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="5578d-127">Benutzerdefinierte Berichte mit Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="5578d-127">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="5578d-128">Programmgesteuertes Erstellen von Berichten.</span><span class="sxs-lookup"><span data-stu-id="5578d-128">Programmatically create reports.</span></span> <span data-ttu-id="5578d-129">Siehe [Übersicht über Microsoft Graph](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="5578d-129">See [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="message-trace"></a><span data-ttu-id="5578d-130">Nachrichtenablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="5578d-130">Message trace</span></span>

<span data-ttu-id="5578d-p106">Ermöglicht das Nachverfolgen von E-Mails auf dem Weg durch EOP. Sie können ermitteln, ob eine E-Mail vom Dienst empfangen, abgelehnt, zurückgestellt oder zugestellt wurde. Außerdem werden die Aktionen der Nachricht gezeigt, bevor diese ihren finalen Status erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="5578d-p106">Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="5578d-134">Mit diesen Informationen können Sie in effizienter Weise Fragen der Benutzer beantworten, Probleme mit dem Nachrichtenfluss behandeln und Richtlinienänderungen überprüfen und müssen seltener den technischen Support um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="5578d-134">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="5578d-135">Siehe [Ablaufverfolgung einer e-Mail-Nachricht](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span><span class="sxs-lookup"><span data-stu-id="5578d-135">See [Trace an email message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span></span>

## <a name="audit-logging"></a><span data-ttu-id="5578d-136">Überwachungsprotokollierung</span><span class="sxs-lookup"><span data-stu-id="5578d-136">Audit logging</span></span>

<span data-ttu-id="5578d-137">Verfolgt bestimmte Änderungen durch Administratoren Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="5578d-137">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="5578d-138">Diese Berichte können Sie zum Behandeln von Konfigurationsproblemen sowie zum Ermitteln der Ursache von Sicherheits- oder Kompatibilitätsproblemen heranziehen.</span><span class="sxs-lookup"><span data-stu-id="5578d-138">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="5578d-139">Siehe [Überwachungsberichte in EoP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="5578d-139">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="5578d-140">Meldung und Verfügbarkeit und Latenz Nachrichtenverfolgungsdaten</span><span class="sxs-lookup"><span data-stu-id="5578d-140">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="5578d-141">In der folgenden Tabelle wird beschrieben, wann und für wie lange EOP-Berichte und Nachrichtenverfolgungsdaten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5578d-141">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="5578d-142">**Berichttyp**</span><span class="sxs-lookup"><span data-stu-id="5578d-142">**Report type**</span></span>|<span data-ttu-id="5578d-143">**Daten verfügbar für (Rückwirkungsfrist)**</span><span class="sxs-lookup"><span data-stu-id="5578d-143">**Data available for (look back period)**</span></span>|<span data-ttu-id="5578d-144">**Latenz**</span><span class="sxs-lookup"><span data-stu-id="5578d-144">**Latency**</span></span>|
|<span data-ttu-id="5578d-145">Zusammenfassungsberichte zum E-Mail-Schutz</span><span class="sxs-lookup"><span data-stu-id="5578d-145">Mail protection summary reports</span></span>|<span data-ttu-id="5578d-146">90 Tage</span><span class="sxs-lookup"><span data-stu-id="5578d-146">90 days</span></span>|<span data-ttu-id="5578d-p108">Die Aggregation von Nachrichtendaten ist meistens innerhalb von 24 bis 48 Stunden abgeschlossen. Kleinere inkrementelle, aggregierte Änderungen können bis zu 5 Tage lang auftreten.</span><span class="sxs-lookup"><span data-stu-id="5578d-p108">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="5578d-149">Detailberichte zum E-Mail-Schutz</span><span class="sxs-lookup"><span data-stu-id="5578d-149">Mail protection detail reports</span></span>|<span data-ttu-id="5578d-150">90 Tage</span><span class="sxs-lookup"><span data-stu-id="5578d-150">90 days</span></span>|<span data-ttu-id="5578d-p109">Bei Detaildaten, die weniger als 7 Tage alt sind, sollten Daten innerhalb von 24 Stunden erscheinen, sind aber möglicherweise erst 48 Stunden später abgeschlossen. Einige kleinere schrittweise Änderungen können bis zu 5 Tagen dauern.</span><span class="sxs-lookup"><span data-stu-id="5578d-p109">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="5578d-153">Zum Anzeigen von Detailberichten für Nachrichten, die älter als 7 Tage sind, kann es einige Stunden dauern, bis die Ergebnisse der Nachrichtenablaufverfolgung ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5578d-153">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="5578d-154">Daten der Nachrichtenablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="5578d-154">Message trace data</span></span>|<span data-ttu-id="5578d-155">90 Tage</span><span class="sxs-lookup"><span data-stu-id="5578d-155">90 days</span></span>|<span data-ttu-id="5578d-156">Wenn Sie eine Nachrichtenverfolgung für Nachrichten starten, die weniger als 7 Tage alt sind, sollten die Nachrichten innerhalb von 5-30 Minuten erscheinen.</span><span class="sxs-lookup"><span data-stu-id="5578d-156">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="5578d-157">Wenn Sie eine Ablaufverfolgung für Nachrichten ausführen, die älter als 7 Tage sind, kann es einige Stunden dauern, bis Ergebnisse ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5578d-157">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|

> [!NOTE]
> <span data-ttu-id="5578d-158">Datenverfügbarkeit und-Wartezeit sind identisch, unabhängig davon, ob Sie über das Microsoft 365 Admin Center oder Remote-PowerShell angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="5578d-158">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span>
