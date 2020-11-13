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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie mehr über Berichte und Problembehandlungstools, die Microsoft Exchange Online Protection (EoP)-Administratoren zur Verfügung stehen.
ms.openlocfilehash: 856e99e55e6b67d1d22a30e2f55f60857eb4fe75
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49020891"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="b4045-103">Berichterstellung und Nachrichtenablaufverfolgung in EoP</span><span class="sxs-lookup"><span data-stu-id="b4045-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b4045-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer bietet EoP viele verschiedene Berichte, mit denen Sie den Gesamtstatus und die Integrität Ihrer Organisation ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="b4045-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="b4045-105">Außerdem gibt es Tools, mit denen Sie die Problembehebung für bestimmte Ereignisse (wenn beispielsweise eine Nachricht nicht beim gewünschten Empfänger ankommt) durchführen können, sowie Überwachungsberichte zur Einhaltung von Vorschriften.</span><span class="sxs-lookup"><span data-stu-id="b4045-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="b4045-106">Verwendungsberichte</span><span class="sxs-lookup"><span data-stu-id="b4045-106">Usage reports</span></span>

<span data-ttu-id="b4045-107">**Microsoft 365 Groups-Aktivität** : Anzeigen von Informationen zur Anzahl von Microsoft 365-Gruppen, die erstellt und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4045-107">**Microsoft 365 groups activity** : View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="b4045-108">**E-Mail-Aktivität** : Anzeigen von Informationen zur Anzahl der gesendeten, empfangenen und eingelesenen Nachrichten in ihrer gesamten Organisation und von bestimmten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="b4045-108">**Email activity** : View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="b4045-109">**E-Mail-App-Nutzung** : Anzeigen von Informationen zu den verwendeten e-Mail-apps</span><span class="sxs-lookup"><span data-stu-id="b4045-109">**Email app usage** : View information about the email apps that are used.</span></span> <span data-ttu-id="b4045-110">Diese umfassen die Gesamtzahl der Verbindungen für die einzelnen Apps und die Versionen von Outlook, die eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="b4045-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="b4045-111">**Postfachnutzung** : Anzeigen von Informationen zu verwendetem Speicher, Kontingent Verbrauch, Elementanzahl und letzter Aktivität (Sende-oder Leseaktivität) für Postfächer.</span><span class="sxs-lookup"><span data-stu-id="b4045-111">**Mailbox usage** : View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="b4045-112">Weitere Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="b4045-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="b4045-113">Microsoft 365-Berichte im Admin Center-Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="b4045-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="b4045-114">Microsoft 365-Berichte im Admin Center-e-Mail-Aktivität</span><span class="sxs-lookup"><span data-stu-id="b4045-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="b4045-115">Microsoft 365-Berichte im Admin Center-Nutzung von e-Mail-apps</span><span class="sxs-lookup"><span data-stu-id="b4045-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="b4045-116">Microsoft 365-Berichte im Admin Center-Postfachnutzung</span><span class="sxs-lookup"><span data-stu-id="b4045-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b4045-117">Security & Compliance Reports im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="b4045-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b4045-118">Diese erweiterten Berichte bieten eine interaktive Berichterstellung für EOP-Administratoren, die Zusammenfassungsinformationen und das Anzeigen von Detailinformationen umfasst.</span><span class="sxs-lookup"><span data-stu-id="b4045-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="b4045-119">**Verteidiger für Office 365** : Anzeigen von Informationen zu sicheren Links und sicheren Anlagen, die Teil von Microsoft Defender für Office 365 sind.</span><span class="sxs-lookup"><span data-stu-id="b4045-119">**Defender for Office 365** : View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="b4045-120">**EoP** : Anzeigen von Informationen zu Malwareerkennungen, gefälschten e-Mails, Spamerkennungen und dem Nachrichtenfluss zu und von Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b4045-120">**EOP** : View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="b4045-121">Anzeigen von Berichten für Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="b4045-121">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="b4045-122">Benutzerdefinierte Berichte mit Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="b4045-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="b4045-123">Programmgesteuertes Erstellen von Berichten, die im Admin Center mithilfe von Microsoft Graph verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b4045-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="b4045-124">Weitere Informationen finden Sie unter [Übersicht über Microsoft Graph](https://docs.microsoft.com/graph/overview) und [Arbeiten mit Office 365 Nutzungsberichten in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="b4045-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="b4045-125">Nachrichtenablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="b4045-125">Message trace</span></span>

<span data-ttu-id="b4045-p104">Ermöglicht das Nachverfolgen von E-Mails auf dem Weg durch EOP. Sie können ermitteln, ob eine E-Mail vom Dienst empfangen, abgelehnt, zurückgestellt oder zugestellt wurde. Außerdem werden die Aktionen der Nachricht gezeigt, bevor diese ihren finalen Status erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="b4045-p104">Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="b4045-129">Mit diesen Informationen können Sie in effizienter Weise Fragen der Benutzer beantworten, Probleme mit dem Nachrichtenfluss behandeln und Richtlinienänderungen überprüfen und müssen seltener den technischen Support um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="b4045-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="b4045-130">Siehe [Nachrichtenablaufverfolgung im Security & Compliance Center](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="b4045-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="b4045-131">Überwachungsprotokollierung</span><span class="sxs-lookup"><span data-stu-id="b4045-131">Audit logging</span></span>

<span data-ttu-id="b4045-132">Verfolgt bestimmte Änderungen durch Administratoren Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b4045-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="b4045-133">Diese Berichte können Sie zum Behandeln von Konfigurationsproblemen sowie zum Ermitteln der Ursache von Sicherheits- oder Kompatibilitätsproblemen heranziehen.</span><span class="sxs-lookup"><span data-stu-id="b4045-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="b4045-134">Siehe [Überwachungsberichte in EoP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b4045-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="b4045-135">Meldung und Verfügbarkeit und Latenz Nachrichtenverfolgungsdaten</span><span class="sxs-lookup"><span data-stu-id="b4045-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="b4045-136">In der folgenden Tabelle wird beschrieben, wann und für wie lange EOP-Berichte und Nachrichtenverfolgungsdaten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b4045-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="b4045-137">Berichttyp</span><span class="sxs-lookup"><span data-stu-id="b4045-137">Report type</span></span>|<span data-ttu-id="b4045-138">Daten verfügbar für (Rückwirkungsfrist)</span><span class="sxs-lookup"><span data-stu-id="b4045-138">Data available for (look back period)</span></span>|<span data-ttu-id="b4045-139">Wartezeit</span><span class="sxs-lookup"><span data-stu-id="b4045-139">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="b4045-140">Zusammenfassungsberichte zum E-Mail-Schutz</span><span class="sxs-lookup"><span data-stu-id="b4045-140">Mail protection summary reports</span></span>|<span data-ttu-id="b4045-141">90 Tage</span><span class="sxs-lookup"><span data-stu-id="b4045-141">90 days</span></span>|<span data-ttu-id="b4045-p106">Die Aggregation von Nachrichtendaten ist meistens innerhalb von 24 bis 48 Stunden abgeschlossen. Kleinere inkrementelle, aggregierte Änderungen können bis zu 5 Tage lang auftreten.</span><span class="sxs-lookup"><span data-stu-id="b4045-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="b4045-144">Detailberichte zum E-Mail-Schutz</span><span class="sxs-lookup"><span data-stu-id="b4045-144">Mail protection detail reports</span></span>|<span data-ttu-id="b4045-145">90 Tage</span><span class="sxs-lookup"><span data-stu-id="b4045-145">90 days</span></span>|<span data-ttu-id="b4045-p107">Bei Detaildaten, die weniger als 7 Tage alt sind, sollten Daten innerhalb von 24 Stunden erscheinen, sind aber möglicherweise erst 48 Stunden später abgeschlossen. Einige kleinere schrittweise Änderungen können bis zu 5 Tagen dauern.</span><span class="sxs-lookup"><span data-stu-id="b4045-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="b4045-148">Zum Anzeigen von Detailberichten für Nachrichten, die älter als 7 Tage sind, kann es einige Stunden dauern, bis die Ergebnisse der Nachrichtenablaufverfolgung ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b4045-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="b4045-149">Daten der Nachrichtenablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="b4045-149">Message trace data</span></span>|<span data-ttu-id="b4045-150">90 Tage</span><span class="sxs-lookup"><span data-stu-id="b4045-150">90 days</span></span>|<span data-ttu-id="b4045-151">Wenn Sie eine Nachrichtenverfolgung für Nachrichten starten, die weniger als 7 Tage alt sind, sollten die Nachrichten innerhalb von 5-30 Minuten erscheinen.</span><span class="sxs-lookup"><span data-stu-id="b4045-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="b4045-152">Wenn Sie eine Ablaufverfolgung für Nachrichten ausführen, die älter als 7 Tage sind, kann es einige Stunden dauern, bis Ergebnisse ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b4045-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="b4045-153">Die Verfügbarkeit und Wartezeit von Daten ist identisch, unabhängig davon, ob Sie über das Admin Center oder Remote-PowerShell angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="b4045-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
