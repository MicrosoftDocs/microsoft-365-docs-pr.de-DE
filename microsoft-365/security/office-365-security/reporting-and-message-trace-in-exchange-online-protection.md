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
description: In diesem Artikel erfahren Sie mehr über Berichte und Problembehandlungstools, die für Microsoft Exchange Online (EOP)-Administratoren verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae55ded9d907754161813c9f7bfa7eeb14c558a8
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625029"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="277c4-103">Berichterstellung und Nachrichtenverfolgung in EOP</span><span class="sxs-lookup"><span data-stu-id="277c4-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="277c4-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="277c4-104">**Applies to**</span></span>
- [<span data-ttu-id="277c4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="277c4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="277c4-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="277c4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="277c4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="277c4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="277c4-108">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer bietet EOP viele verschiedene Berichte, mit denen Sie den Allgemeinen Status und die Integrität Ihrer Organisation bestimmen können.</span><span class="sxs-lookup"><span data-stu-id="277c4-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="277c4-109">Außerdem gibt es Tools, mit denen Sie die Problembehebung für bestimmte Ereignisse (wenn beispielsweise eine Nachricht nicht beim gewünschten Empfänger ankommt) durchführen können, sowie Überwachungsberichte zur Einhaltung von Vorschriften.</span><span class="sxs-lookup"><span data-stu-id="277c4-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="277c4-110">Verwendungsberichte</span><span class="sxs-lookup"><span data-stu-id="277c4-110">Usage reports</span></span>

<span data-ttu-id="277c4-111">**Microsoft 365:** Anzeigen von Informationen zur Anzahl der Microsoft 365, die erstellt und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="277c4-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="277c4-112">**E-Mail-Aktivität**: Anzeigen von Informationen zur Anzahl der gesendeten, empfangenen und gelesenen Nachrichten in Ihrer gesamten Organisation und von bestimmten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="277c4-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="277c4-113">**E-Mail-App-Nutzung:** Anzeigen von Informationen zu den verwendeten E-Mail-Apps.</span><span class="sxs-lookup"><span data-stu-id="277c4-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="277c4-114">Diese umfassen die Gesamtzahl der Verbindungen für die einzelnen Apps und die Versionen von Outlook, die eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="277c4-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="277c4-115">**Postfachnutzung**: Anzeigen von Informationen zu verwendeten Speicher, Kontingentverbrauch, Elementanzahl und letzten Aktivitäten (Senden oder Lesen von Aktivitäten) für Postfächer.</span><span class="sxs-lookup"><span data-stu-id="277c4-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="277c4-116">Weitere Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="277c4-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="277c4-117">Microsoft 365 Berichte im Admin Center – Microsoft 365 Gruppen</span><span class="sxs-lookup"><span data-stu-id="277c4-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](../../admin/activity-reports/office-365-groups.md)

- [<span data-ttu-id="277c4-118">Microsoft 365 Berichte im Admin Center – E-Mail-Aktivität</span><span class="sxs-lookup"><span data-stu-id="277c4-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](../../admin/activity-reports/email-activity.md)

- [<span data-ttu-id="277c4-119">Microsoft 365 Berichte im Admin Center – Verwendung von E-Mail-Apps</span><span class="sxs-lookup"><span data-stu-id="277c4-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](../../admin/activity-reports/email-apps-usage.md)

- [<span data-ttu-id="277c4-120">Microsoft 365 Berichte im Admin Center – Postfachverwendung</span><span class="sxs-lookup"><span data-stu-id="277c4-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="277c4-121">Sicherheitsberichte & Complianceberichte im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="277c4-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="277c4-122">Diese erweiterten Berichte bieten eine interaktive Berichterstellung für EOP-Administratoren, die Zusammenfassungsinformationen und das Anzeigen von Detailinformationen umfasst.</span><span class="sxs-lookup"><span data-stu-id="277c4-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="277c4-123">**Defender for Office 365**: Anzeigen von Informationen zu sicheren Links und sicheren Anlagen, die Teil von Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="277c4-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="277c4-124">**EOP**: Anzeigen von Informationen zu Schadsoftwareerkennungen, Spoofing-E-Mails, Spamerkennungen und E-Mail-Fluss zu und von Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="277c4-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="277c4-125">Anzeigen von Berichten für Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="277c4-125">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="277c4-126">Benutzerdefinierte Berichte mit Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="277c4-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="277c4-127">Programmgesteuertes Erstellen von Berichten, die im Admin Center verfügbar sind, mithilfe von Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="277c4-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="277c4-128">Weitere Informationen finden Sie unter [Overview of Microsoft Graph](/graph/overview) and Working with Office 365 usage reports in Microsoft [Graph](/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="277c4-128">For more information, see [Overview of Microsoft Graph](/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="277c4-129">Nachrichtenablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="277c4-129">Message trace</span></span>

<span data-ttu-id="277c4-p104">Ermöglicht das Nachverfolgen von E-Mails auf dem Weg durch EOP. Sie können ermitteln, ob eine E-Mail vom Dienst empfangen, abgelehnt, zurückgestellt oder zugestellt wurde. Außerdem werden die Aktionen der Nachricht gezeigt, bevor diese ihren finalen Status erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="277c4-p104">Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="277c4-133">Mit diesen Informationen können Sie in effizienter Weise Fragen der Benutzer beantworten, Probleme mit dem Nachrichtenfluss behandeln und Richtlinienänderungen überprüfen und müssen seltener den technischen Support um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="277c4-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="277c4-134">Weitere Informationen finden Sie unter Nachrichtenverfolgung [im Security & Compliance Center](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="277c4-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="277c4-135">Überwachungsprotokollierung</span><span class="sxs-lookup"><span data-stu-id="277c4-135">Audit logging</span></span>

<span data-ttu-id="277c4-136">Verfolgt bestimmte Änderungen durch Administratoren Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="277c4-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="277c4-137">Diese Berichte können Sie zum Behandeln von Konfigurationsproblemen sowie zum Ermitteln der Ursache von Sicherheits- oder Kompatibilitätsproblemen heranziehen.</span><span class="sxs-lookup"><span data-stu-id="277c4-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="277c4-138">Weitere [Informationen finden Sie unter Überwachung](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)von Berichten in Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="277c4-138">See [Auditing reports in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="277c4-139">Meldung und Verfügbarkeit und Latenz Nachrichtenverfolgungsdaten</span><span class="sxs-lookup"><span data-stu-id="277c4-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="277c4-140">In der folgenden Tabelle wird beschrieben, wann und für wie lange EOP-Berichte und Nachrichtenverfolgungsdaten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="277c4-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="277c4-141">Berichttyp</span><span class="sxs-lookup"><span data-stu-id="277c4-141">Report type</span></span>|<span data-ttu-id="277c4-142">Daten verfügbar für (Rückwirkungsfrist)</span><span class="sxs-lookup"><span data-stu-id="277c4-142">Data available for (look back period)</span></span>|<span data-ttu-id="277c4-143">Latency</span><span class="sxs-lookup"><span data-stu-id="277c4-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="277c4-144">Zusammenfassungsberichte zum E-Mail-Schutz</span><span class="sxs-lookup"><span data-stu-id="277c4-144">Mail protection summary reports</span></span>|<span data-ttu-id="277c4-145">90 Tage</span><span class="sxs-lookup"><span data-stu-id="277c4-145">90 days</span></span>|<span data-ttu-id="277c4-p106">Die Aggregation von Nachrichtendaten ist meistens innerhalb von 24 bis 48 Stunden abgeschlossen. Kleinere inkrementelle, aggregierte Änderungen können bis zu 5 Tage lang auftreten.</span><span class="sxs-lookup"><span data-stu-id="277c4-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="277c4-148">Detailberichte zum E-Mail-Schutz</span><span class="sxs-lookup"><span data-stu-id="277c4-148">Mail protection detail reports</span></span>|<span data-ttu-id="277c4-149">90 Tage</span><span class="sxs-lookup"><span data-stu-id="277c4-149">90 days</span></span>|<span data-ttu-id="277c4-p107">Bei Detaildaten, die weniger als 7 Tage alt sind, sollten Daten innerhalb von 24 Stunden erscheinen, sind aber möglicherweise erst 48 Stunden später abgeschlossen. Einige kleinere schrittweise Änderungen können bis zu 5 Tagen dauern.</span><span class="sxs-lookup"><span data-stu-id="277c4-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="277c4-152">Zum Anzeigen von Detailberichten für Nachrichten, die älter als 7 Tage sind, kann es einige Stunden dauern, bis die Ergebnisse der Nachrichtenablaufverfolgung ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="277c4-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="277c4-153">Daten der Nachrichtenablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="277c4-153">Message trace data</span></span>|<span data-ttu-id="277c4-154">90 Tage</span><span class="sxs-lookup"><span data-stu-id="277c4-154">90 days</span></span>|<span data-ttu-id="277c4-155">Wenn Sie eine Nachrichtenverfolgung für Nachrichten starten, die weniger als 7 Tage alt sind, sollten die Nachrichten innerhalb von 5-30 Minuten erscheinen.</span><span class="sxs-lookup"><span data-stu-id="277c4-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="277c4-156">Wenn Sie eine Ablaufverfolgung für Nachrichten ausführen, die älter als 7 Tage sind, kann es einige Stunden dauern, bis Ergebnisse ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="277c4-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="277c4-157">Datenverfügbarkeit und Latenz sind identisch, unabhängig davon, ob sie über das Admin Center oder die Remote-PowerShell angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="277c4-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>