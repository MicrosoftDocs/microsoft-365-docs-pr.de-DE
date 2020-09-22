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
ms.openlocfilehash: 86f4e18430324ed95f036f93746d826225ec3b2f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196399"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="5cd56-103">Berichterstellung und Nachrichtenablaufverfolgung in EoP</span><span class="sxs-lookup"><span data-stu-id="5cd56-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5cd56-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer bietet EoP viele verschiedene Berichte, mit denen Sie den Gesamtstatus und die Integrität Ihrer Organisation ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="5cd56-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="5cd56-105">Außerdem gibt es Tools, mit denen Sie die Problembehebung für bestimmte Ereignisse (wenn beispielsweise eine Nachricht nicht beim gewünschten Empfänger ankommt) durchführen können, sowie Überwachungsberichte zur Einhaltung von Vorschriften.</span><span class="sxs-lookup"><span data-stu-id="5cd56-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="5cd56-106">Verwendungsberichte</span><span class="sxs-lookup"><span data-stu-id="5cd56-106">Usage reports</span></span>

<span data-ttu-id="5cd56-107">**Microsoft 365 Groups-Aktivität**: Anzeigen von Informationen zur Anzahl von Microsoft 365-Gruppen, die erstellt und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5cd56-107">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="5cd56-108">**E-Mail-Aktivität**: Anzeigen von Informationen zur Anzahl der gesendeten, empfangenen und eingelesenen Nachrichten in ihrer gesamten Organisation und von bestimmten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="5cd56-108">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="5cd56-109">**E-Mail-App-Nutzung**: Anzeigen von Informationen zu den verwendeten e-Mail-apps</span><span class="sxs-lookup"><span data-stu-id="5cd56-109">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="5cd56-110">Diese umfassen die Gesamtzahl der Verbindungen für die einzelnen Apps und die Versionen von Outlook, die eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="5cd56-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="5cd56-111">**Postfachnutzung**: Anzeigen von Informationen zu verwendetem Speicher, Kontingent Verbrauch, Elementanzahl und letzter Aktivität (Sende-oder Leseaktivität) für Postfächer.</span><span class="sxs-lookup"><span data-stu-id="5cd56-111">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="5cd56-112">Weitere Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="5cd56-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="5cd56-113">Microsoft 365-Berichte im Admin Center-Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="5cd56-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="5cd56-114">Microsoft 365-Berichte im Admin Center-e-Mail-Aktivität</span><span class="sxs-lookup"><span data-stu-id="5cd56-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="5cd56-115">Microsoft 365-Berichte im Admin Center-Nutzung von e-Mail-apps</span><span class="sxs-lookup"><span data-stu-id="5cd56-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="5cd56-116">Microsoft 365-Berichte im Admin Center-Postfachnutzung</span><span class="sxs-lookup"><span data-stu-id="5cd56-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="5cd56-117">Security & Compliance Reports im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="5cd56-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="5cd56-118">Diese erweiterten Berichte bieten eine interaktive Berichterstellung für EOP-Administratoren, die Zusammenfassungsinformationen und das Anzeigen von Detailinformationen umfasst.</span><span class="sxs-lookup"><span data-stu-id="5cd56-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="5cd56-119">**Advanced Threat Protection (ATP)**: Hier finden Sie Informationen über sichere Links und sichere Anlagen, die Teil von ATP sind.</span><span class="sxs-lookup"><span data-stu-id="5cd56-119">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="5cd56-120">**EoP**: Anzeigen von Informationen zu Malwareerkennungen, gefälschten e-Mails, Spamerkennungen und dem Nachrichtenfluss zu und von Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="5cd56-120">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="5cd56-121">Anzeigen von Berichten für Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5cd56-121">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="5cd56-122">Benutzerdefinierte Berichte mit Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="5cd56-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="5cd56-123">Programmgesteuertes Erstellen von Berichten, die im Admin Center mithilfe von Microsoft Graph verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5cd56-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="5cd56-124">Weitere Informationen finden Sie unter [Übersicht über Microsoft Graph](https://docs.microsoft.com/graph/overview) und [Arbeiten mit Office 365 Nutzungsberichten in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="5cd56-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="5cd56-125">Nachrichtenablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="5cd56-125">Message trace</span></span>

<span data-ttu-id="5cd56-p104">Ermöglicht das Nachverfolgen von E-Mails auf dem Weg durch EOP. Sie können ermitteln, ob eine E-Mail vom Dienst empfangen, abgelehnt, zurückgestellt oder zugestellt wurde. Außerdem werden die Aktionen der Nachricht gezeigt, bevor diese ihren finalen Status erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="5cd56-p104">Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="5cd56-129">Mit diesen Informationen können Sie in effizienter Weise Fragen der Benutzer beantworten, Probleme mit dem Nachrichtenfluss behandeln und Richtlinienänderungen überprüfen und müssen seltener den technischen Support um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="5cd56-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="5cd56-130">Siehe [Nachrichtenablaufverfolgung im Security & Compliance Center](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="5cd56-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="5cd56-131">Überwachungsprotokollierung</span><span class="sxs-lookup"><span data-stu-id="5cd56-131">Audit logging</span></span>

<span data-ttu-id="5cd56-132">Verfolgt bestimmte Änderungen durch Administratoren Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="5cd56-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="5cd56-133">Diese Berichte können Sie zum Behandeln von Konfigurationsproblemen sowie zum Ermitteln der Ursache von Sicherheits- oder Kompatibilitätsproblemen heranziehen.</span><span class="sxs-lookup"><span data-stu-id="5cd56-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="5cd56-134">Siehe [Überwachungsberichte in EoP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="5cd56-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="5cd56-135">Meldung und Verfügbarkeit und Latenz Nachrichtenverfolgungsdaten</span><span class="sxs-lookup"><span data-stu-id="5cd56-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="5cd56-136">In der folgenden Tabelle wird beschrieben, wann und für wie lange EOP-Berichte und Nachrichtenverfolgungsdaten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5cd56-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="5cd56-137">Berichttyp</span><span class="sxs-lookup"><span data-stu-id="5cd56-137">Report type</span></span>|<span data-ttu-id="5cd56-138">Daten verfügbar für (Rückwirkungsfrist)</span><span class="sxs-lookup"><span data-stu-id="5cd56-138">Data available for (look back period)</span></span>|<span data-ttu-id="5cd56-139">Wartezeit</span><span class="sxs-lookup"><span data-stu-id="5cd56-139">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="5cd56-140">Zusammenfassungsberichte zum E-Mail-Schutz</span><span class="sxs-lookup"><span data-stu-id="5cd56-140">Mail protection summary reports</span></span>|<span data-ttu-id="5cd56-141">90 Tage</span><span class="sxs-lookup"><span data-stu-id="5cd56-141">90 days</span></span>|<span data-ttu-id="5cd56-p106">Die Aggregation von Nachrichtendaten ist meistens innerhalb von 24 bis 48 Stunden abgeschlossen. Kleinere inkrementelle, aggregierte Änderungen können bis zu 5 Tage lang auftreten.</span><span class="sxs-lookup"><span data-stu-id="5cd56-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="5cd56-144">Detailberichte zum E-Mail-Schutz</span><span class="sxs-lookup"><span data-stu-id="5cd56-144">Mail protection detail reports</span></span>|<span data-ttu-id="5cd56-145">90 Tage</span><span class="sxs-lookup"><span data-stu-id="5cd56-145">90 days</span></span>|<span data-ttu-id="5cd56-p107">Bei Detaildaten, die weniger als 7 Tage alt sind, sollten Daten innerhalb von 24 Stunden erscheinen, sind aber möglicherweise erst 48 Stunden später abgeschlossen. Einige kleinere schrittweise Änderungen können bis zu 5 Tagen dauern.</span><span class="sxs-lookup"><span data-stu-id="5cd56-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="5cd56-148">Zum Anzeigen von Detailberichten für Nachrichten, die älter als 7 Tage sind, kann es einige Stunden dauern, bis die Ergebnisse der Nachrichtenablaufverfolgung ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5cd56-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="5cd56-149">Daten der Nachrichtenablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="5cd56-149">Message trace data</span></span>|<span data-ttu-id="5cd56-150">90 Tage</span><span class="sxs-lookup"><span data-stu-id="5cd56-150">90 days</span></span>|<span data-ttu-id="5cd56-151">Wenn Sie eine Nachrichtenverfolgung für Nachrichten starten, die weniger als 7 Tage alt sind, sollten die Nachrichten innerhalb von 5-30 Minuten erscheinen.</span><span class="sxs-lookup"><span data-stu-id="5cd56-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="5cd56-152">Wenn Sie eine Ablaufverfolgung für Nachrichten ausführen, die älter als 7 Tage sind, kann es einige Stunden dauern, bis Ergebnisse ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5cd56-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="5cd56-153">Die Verfügbarkeit und Wartezeit von Daten ist identisch, unabhängig davon, ob Sie über das Admin Center oder Remote-PowerShell angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="5cd56-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
