---
title: E-Mail-Sicherheitsberichte anzeigen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die E-Mail-Sicherheitsberichte finden und verwenden, die im Microsoft 365 Defender-Portal verfügbar sind.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3dcf533c232a89adf0dc1ff3fcc7c2ca4fc5d8f
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022936"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="079a5-103">Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="079a5-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="079a5-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="079a5-104">**Applies to**</span></span>
- [<span data-ttu-id="079a5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="079a5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="079a5-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="079a5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="079a5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="079a5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="079a5-108">Im Microsoft 365 Defender-Portal finden Sie eine Vielzahl von Berichten, <https://security.microsoft.com> mit denen Sie sehen können, wie E-Mail-Sicherheitsfeatures wie Antispam, Antischadsoftware und Verschlüsselungsfunktionen in Microsoft 365 Ihre Organisation schützen.</span><span class="sxs-lookup"><span data-stu-id="079a5-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="079a5-109">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im Microsoft 365 Defender-Portal anzeigen, indem Sie zu  \> **E-Mail-Berichte &** \> **ZusammenarbeitS-E-Mail & Zusammenarbeitsberichte wechseln.**</span><span class="sxs-lookup"><span data-stu-id="079a5-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="079a5-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="079a5-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Seite "E-Mail & Berichte zur Zusammenarbeit" im Microsoft 365 Defender-Portal](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="079a5-112">Einige der Berichte auf der Seite **"E-Mail & Zusammenarbeitsberichte"** erfordern Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="079a5-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="079a5-113">Informationen zu diesen Berichten finden Sie unter Anzeigen von [Defender für Office 365-Berichten im Microsoft 365 Defender-Portal.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="079a5-114">Berichte, die sich auf den Nachrichtenfluss beziehen, befinden sich jetzt im Exchange Admin Center (EAC).</span><span class="sxs-lookup"><span data-stu-id="079a5-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="079a5-115">Weitere Informationen zu diesen Berichten finden Sie unter [Nachrichtenflussberichte im neuen Exchange Admin Center.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="079a5-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="079a5-116">Bericht "Kompromittierte Benutzer"</span><span class="sxs-lookup"><span data-stu-id="079a5-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="079a5-117">Dieser Bericht ist in Microsoft 365-Organisationen mit Exchange Online-Postfächern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="079a5-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="079a5-118">Es ist nicht in eigenständigen Exchange Online Protection (EOP)-Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="079a5-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="079a5-119">Der Bericht **"Kompromittierte Benutzer"** zeigt die Anzahl der Benutzerkonten an, die innerhalb der letzten 7 Tage als **verdächtig** oder **eingeschränkt** markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="079a5-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="079a5-120">Konten in einem dieser Zustände sind problematisch oder sogar kompromittiert.</span><span class="sxs-lookup"><span data-stu-id="079a5-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="079a5-121">Bei häufiger Verwendung können Sie den Bericht verwenden, um Spitzen und sogar Trends in verdächtigen oder eingeschränkten Konten zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="079a5-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="079a5-122">Weitere Informationen zu kompromittierten Benutzern finden Sie unter [Antworten auf ein kompromittiertes E-Mail-Konto.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget "Kompromittierte Benutzer" auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/compromised-users-report-widget.png)

<span data-ttu-id="079a5-124">In der Aggregatansicht werden Daten für die letzten 90 Tage und in der Detailansicht Daten für die letzten 30 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="079a5-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="079a5-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports.**</span><span class="sxs-lookup"><span data-stu-id="079a5-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="079a5-126">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** **kompromittierte Benutzer,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="079a5-127">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="079a5-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="079a5-128">Auf der Seite **"Kompromittierte Benutzer"** können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="079a5-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="079a5-129">**Datum (UTC):** **Startdatum** und **Enddatum.**</span><span class="sxs-lookup"><span data-stu-id="079a5-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="079a5-130">**Aktivität:**</span><span class="sxs-lookup"><span data-stu-id="079a5-130">**Activity**:</span></span>
  - <span data-ttu-id="079a5-131">**Verdächtig:** Das Benutzerkonto hat verdächtige E-Mails gesendet und besteht das Risiko, dass das Senden von E-Mails eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="079a5-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="079a5-132">**Eingeschränkt:** Das Benutzerkonto wurde aufgrund von hochgradig verdächtigen Mustern am Senden von E-Mails gehindert.</span><span class="sxs-lookup"><span data-stu-id="079a5-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="079a5-133">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![Berichtsansicht im Bericht "Kompromittierte Benutzer"](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="079a5-135">In der Detailtabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="079a5-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="079a5-136">**Erstellungszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="079a5-136">**Creation time**</span></span>
- <span data-ttu-id="079a5-137">**Benutzer-ID**</span><span class="sxs-lookup"><span data-stu-id="079a5-137">**User ID**</span></span>
- <span data-ttu-id="079a5-138">**Action**</span><span class="sxs-lookup"><span data-stu-id="079a5-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="079a5-139">Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-139">Exchange transport rule report</span></span>

<span data-ttu-id="079a5-140">Der **Exchange-Transportregelbericht** zeigt die Auswirkungen von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) auf ein- und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="079a5-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="079a5-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports.**</span><span class="sxs-lookup"><span data-stu-id="079a5-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="079a5-142">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** die **Exchange-Transportregel,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="079a5-143">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="079a5-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/transport-rule-report-widget.png)

<span data-ttu-id="079a5-145">Auf der Seite **"Exchange-Transportregelbericht"** werden die verfügbaren Diagramme und Daten in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="079a5-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="079a5-146">Diagrammstrukturplan nach Richtung</span><span class="sxs-lookup"><span data-stu-id="079a5-146">Chart breakdown by Direction</span></span>

![Richtungsansicht für Exchange-Transportregeln im Exchange-Transportregelbericht](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="079a5-148">Wenn Sie **die Diagrammstrukturstruktur nach Richtung** auswählen, sind die folgenden Diagramme verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="079a5-149">**Anzeigen von Daten nach Exchange-Transportregeln:** Die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von Nachrichtenflussregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="079a5-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="079a5-150">**Anzeigen von Daten nach DLP Exchange-Transportregeln:** Die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von DLP-Nachrichtenflussregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="079a5-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="079a5-151">Die folgenden Informationen werden in der Detailtabelle unterhalb des Diagramms angezeigt:</span><span class="sxs-lookup"><span data-stu-id="079a5-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="079a5-152">**Date**</span><span class="sxs-lookup"><span data-stu-id="079a5-152">**Date**</span></span>
- <span data-ttu-id="079a5-153">**DLP-Richtlinie** (**Nur Daten nach DLP-Exchange-Transportregeln anzeigen)**</span><span class="sxs-lookup"><span data-stu-id="079a5-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="079a5-154">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="079a5-154">**Transport rule**</span></span>
- <span data-ttu-id="079a5-155">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="079a5-155">**Subject**</span></span>
- <span data-ttu-id="079a5-156">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="079a5-156">**Sender address**</span></span>
- <span data-ttu-id="079a5-157">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="079a5-157">**Recipient address**</span></span>
- <span data-ttu-id="079a5-158">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="079a5-158">**Severity**</span></span>
- <span data-ttu-id="079a5-159">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="079a5-159">**Direction**</span></span>

<span data-ttu-id="079a5-160">Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="079a5-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="079a5-161">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-162">**Richtung:** **Ausgehend** und **Eingehend**</span><span class="sxs-lookup"><span data-stu-id="079a5-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="079a5-163">**Schweregrad:** **Hoher,** **mittlerer und** niedriger **Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="079a5-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="079a5-164">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="079a5-165">Diagrammstrukturplan nach Schweregrad</span><span class="sxs-lookup"><span data-stu-id="079a5-165">Chart breakdown by Severity</span></span>

![Schweregradansicht für Exchange-Transportregeln im Exchange-Transportregelbericht](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="079a5-167">Wenn Sie **die Diagrammstrukturstruktur nach Schweregrad** auswählen, sind die folgenden Diagramme verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="079a5-168">**Anzeigen von Daten nach Exchange-Transportregeln:** Die Anzahl der Nachrichten mit **hohem,** **mittlerem und** **mittlerem Schweregrad.**</span><span class="sxs-lookup"><span data-stu-id="079a5-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="079a5-169">Sie legen den Schweregrad als Aktion in der Regel fest (**Überwachen Sie diese Regel mit Schweregrad** oder _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="079a5-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="079a5-170">Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="079a5-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="079a5-171">**Anzeigen von Daten nach DLP Exchange-Transportregeln:** Die Anzahl der Nachrichten mit **hohem Schweregrad,** **mittlerem Schweregrad** und **niedrigem Schweregrad,** die von DLP-Nachrichtenflussregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="079a5-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="079a5-172">Die folgenden Informationen werden in der Detailtabelle unterhalb des Diagramms angezeigt:</span><span class="sxs-lookup"><span data-stu-id="079a5-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="079a5-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="079a5-173">**Date**</span></span>
- <span data-ttu-id="079a5-174">**DLP-Richtlinie** (**Nur Daten nach DLP-Exchange-Transportregeln anzeigen)**</span><span class="sxs-lookup"><span data-stu-id="079a5-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="079a5-175">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="079a5-175">**Transport rule**</span></span>
- <span data-ttu-id="079a5-176">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="079a5-176">**Subject**</span></span>
- <span data-ttu-id="079a5-177">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="079a5-177">**Sender address**</span></span>
- <span data-ttu-id="079a5-178">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="079a5-178">**Recipient address**</span></span>
- <span data-ttu-id="079a5-179">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="079a5-179">**Severity**</span></span>
- <span data-ttu-id="079a5-180">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="079a5-180">**Direction**</span></span>

<span data-ttu-id="079a5-181">Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="079a5-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="079a5-182">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-183">**Richtung:** **Ausgehend** und **Eingehend**</span><span class="sxs-lookup"><span data-stu-id="079a5-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="079a5-184">**Schweregrad:** **Hoher,** **mittlerer und** niedriger **Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="079a5-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="079a5-185">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="079a5-186">Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="079a5-187">Der **Weiterleitungsbericht** ist jetzt im EAC verfügbar.</span><span class="sxs-lookup"><span data-stu-id="079a5-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="079a5-188">Weitere Informationen finden Sie unter [Bericht über automatisch weitergeleitete Nachrichten im neuen EAC.](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)</span><span class="sxs-lookup"><span data-stu-id="079a5-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="079a5-189">E-Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-189">Mailflow status report</span></span>

<span data-ttu-id="079a5-190">Der **E-Mailflow-Statusbericht** ist ein intelligenter Bericht, der Informationen zu eingehenden und ausgehenden E-Mails, Spamerkennungen, Schadsoftware, als "gut" identifizierten E-Mails und Informationen zu E-Mails anzeigt, die am Edge zugelassen oder blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="079a5-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="079a5-191">Dies ist der einzige Bericht, der Edgeschutzinformationen enthält, und zeigt an, wie viele E-Mails blockiert werden, bevor sie zur Auswertung durch Exchange Online Protection (EOP) in den Dienst zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="079a5-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="079a5-192">Es ist wichtig zu verstehen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="079a5-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="079a5-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports.**</span><span class="sxs-lookup"><span data-stu-id="079a5-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="079a5-194">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** die Zusammenfassung des **E-Mail-Flussstatus,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="079a5-195">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="079a5-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Nachrichtenflussstatus-Zusammenfassungs-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="079a5-197">Typansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-197">Type view for the Mailflow status report</span></span>

<span data-ttu-id="079a5-198">Wenn Sie den Bericht  öffnen, ist standardmäßig die Registerkarte Typ ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="079a5-198">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="079a5-199">Standardmäßig enthält diese Ansicht ein Diagramm und eine Detailtabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="079a5-199">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="079a5-200">**Datum (UTC)** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="079a5-200">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="079a5-201">**E-Mail-Richtung:**</span><span class="sxs-lookup"><span data-stu-id="079a5-201">**Mail direction**:</span></span>
  - <span data-ttu-id="079a5-202">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="079a5-202">**Inbound**</span></span>
  - <span data-ttu-id="079a5-203">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="079a5-203">**Outbound**</span></span>
  - <span data-ttu-id="079a5-204">**Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="079a5-204">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="079a5-205">absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von **ein-** und **ausgehend** gezählt)</span><span class="sxs-lookup"><span data-stu-id="079a5-205">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="079a5-206">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="079a5-206">**Type**:</span></span>
  - <span data-ttu-id="079a5-207">**Gute E-Mails**</span><span class="sxs-lookup"><span data-stu-id="079a5-207">**Good mail**</span></span>
  - <span data-ttu-id="079a5-208">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="079a5-208">**Malware**</span></span>
  - <span data-ttu-id="079a5-209">**Spam**</span><span class="sxs-lookup"><span data-stu-id="079a5-209">**Spam**</span></span>
  - <span data-ttu-id="079a5-210">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="079a5-210">**Edge protection**</span></span>
  - <span data-ttu-id="079a5-211">**Regelnachrichten**</span><span class="sxs-lookup"><span data-stu-id="079a5-211">**Rule messages**</span></span>
  - <span data-ttu-id="079a5-212">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="079a5-212">**Phishing email**</span></span>
- <span data-ttu-id="079a5-213">**Domäne:** **Alle**</span><span class="sxs-lookup"><span data-stu-id="079a5-213">**Domain**: **All**</span></span>

<span data-ttu-id="079a5-214">Das Diagramm ist nach den **Type-Werten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="079a5-214">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="079a5-215">Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="079a5-215">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="079a5-216">Die folgenden Informationen werden in der Detailtabelle unterhalb des Diagramms angezeigt:</span><span class="sxs-lookup"><span data-stu-id="079a5-216">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="079a5-217">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="079a5-217">**Direction**</span></span>
- <span data-ttu-id="079a5-218">**Typ**</span><span class="sxs-lookup"><span data-stu-id="079a5-218">**Type**</span></span>
- <span data-ttu-id="079a5-219">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="079a5-219">**24 hours**</span></span>
- <span data-ttu-id="079a5-220">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="079a5-220">**3 days**</span></span>
- <span data-ttu-id="079a5-221">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="079a5-221">**7 days**</span></span>
- <span data-ttu-id="079a5-222">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="079a5-222">**15 days**</span></span>
- <span data-ttu-id="079a5-223">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="079a5-223">**30 days**</span></span>

<span data-ttu-id="079a5-224">Wenn Sie auf **"Kategorie auswählen"** klicken, um weitere Details zu erhalten, können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="079a5-224">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="079a5-225">**Phishing-E-Mail:** Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="079a5-225">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="079a5-226">**Schadsoftware in E-Mails:** Diese Auswahl führt Sie zum [Bedrohungsschutzstatusbericht.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="079a5-226">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="079a5-227">**Spamerkennungen:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="079a5-227">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="079a5-228">**Edge blockierter Spam:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="079a5-228">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="079a5-229">Exportieren aus der Typansicht</span><span class="sxs-lookup"><span data-stu-id="079a5-229">Export from Type view</span></span>

<span data-ttu-id="079a5-230">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="079a5-230">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="079a5-231">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="079a5-231">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="079a5-232">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="079a5-232">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="079a5-233">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="079a5-233">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Typansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="079a5-235">Richtungsansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-235">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="079a5-236">Wenn Sie auf die Registerkarte **"Richtung"** klicken, werden die gleichen Standardfilter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="079a5-236">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="079a5-237">Das Diagramm ist nach **Richtungswerten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="079a5-237">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="079a5-238">Sie können diese Filter ändern, indem Sie auf **"Filter"** klicken.</span><span class="sxs-lookup"><span data-stu-id="079a5-238">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="079a5-239">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="079a5-239">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="079a5-240">Die Detailtabelle enthält dieselben Informationen aus der **Typansicht.**</span><span class="sxs-lookup"><span data-stu-id="079a5-240">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="079a5-241">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span><span class="sxs-lookup"><span data-stu-id="079a5-241">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="079a5-242">Exportieren aus der Richtungsansicht</span><span class="sxs-lookup"><span data-stu-id="079a5-242">Export from Direction view</span></span>

<span data-ttu-id="079a5-243">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="079a5-243">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="079a5-244">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="079a5-244">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="079a5-245">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="079a5-245">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="079a5-246">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="079a5-246">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Richtungsansicht im E-Mailflow-Statusbericht](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="079a5-248">Trichteransicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="079a5-249">Die **Trichteransicht** zeigt Ihnen, wie die E-Mail-Bedrohungsschutzfeatures von Microsoft eingehende und ausgehende E-Mails in Ihrer Organisation filtern.</span><span class="sxs-lookup"><span data-stu-id="079a5-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="079a5-250">Es enthält Details zur Gesamtzahl der E-Mails und dazu, wie sich die konfigurierten Bedrohungsschutzfeatures, einschließlich Edgeschutz, Antischadsoftware, Antiphishing, Antispam und Antispoofing, auf diese Anzahl auswirken.</span><span class="sxs-lookup"><span data-stu-id="079a5-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="079a5-251">Wenn Sie auf die Registerkarte **"Trichter"** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Detailtabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="079a5-251">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="079a5-252">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="079a5-252">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="079a5-253">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="079a5-253">**Direction**:</span></span>
  - <span data-ttu-id="079a5-254">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="079a5-254">**Inbound**</span></span>
  - <span data-ttu-id="079a5-255">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="079a5-255">**Outbound**</span></span>
  - <span data-ttu-id="079a5-256">**Organisationsintern:** Diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden; d. h. Absender abc@domain.com sendet an Empfänger xyz@domain.com (separat von Ein- und Ausgehend gezählt).</span><span class="sxs-lookup"><span data-stu-id="079a5-256">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="079a5-257">Die Aggregatansicht und die Detailtabellenansicht ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="079a5-257">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="079a5-258">Sie können diese Filter ändern, indem Sie auf **"Filter"** klicken.</span><span class="sxs-lookup"><span data-stu-id="079a5-258">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="079a5-259">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="079a5-259">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="079a5-260">Dieses Diagramm zeigt die E-Mail-Anzahl nach:</span><span class="sxs-lookup"><span data-stu-id="079a5-260">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="079a5-261">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="079a5-261">**Total email**</span></span>
- <span data-ttu-id="079a5-262">**E-Mail nach Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="079a5-262">**Email after edge protection**</span></span>
- <span data-ttu-id="079a5-263">**E-Mail nach Transportregel** (Nachrichtenflussregel)</span><span class="sxs-lookup"><span data-stu-id="079a5-263">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="079a5-264">**E-Mail nach Antischadsoftware, Dateireputation, Dateitypblockierung**</span><span class="sxs-lookup"><span data-stu-id="079a5-264">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="079a5-265">**E-Mail nach Antiphishing, URL-Reputation, Markenidentitätswechsel, Antispoofing**</span><span class="sxs-lookup"><span data-stu-id="079a5-265">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="079a5-266">**E-Mails nach Antispam, Massenfilterung von E-Mails**</span><span class="sxs-lookup"><span data-stu-id="079a5-266">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="079a5-267">**E-Mail nach Benutzer- und Domänenidentitätswechsel**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="079a5-267">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="079a5-268">**E-Mail nach Datei- und URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="079a5-268">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="079a5-269">**E-Mails, die nach der Zustellung als gutartig erkannt wurden (URL-Click-Time-Schutz)**</span><span class="sxs-lookup"><span data-stu-id="079a5-269">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="079a5-270"><sup>\*</sup>Nur Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="079a5-270"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="079a5-271">Um die von EOP oder Defender gefilterte E-Mail für Office 365 separat anzuzeigen, klicken Sie auf den Wert in der Diagrammlegende.</span><span class="sxs-lookup"><span data-stu-id="079a5-271">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="079a5-272">Die Detailtabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="079a5-272">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="079a5-273">**Date**</span><span class="sxs-lookup"><span data-stu-id="079a5-273">**Date**</span></span>
- <span data-ttu-id="079a5-274">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="079a5-274">**Total email**</span></span>
- <span data-ttu-id="079a5-275">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="079a5-275">**Edge protection**</span></span>
- <span data-ttu-id="079a5-276">**Antischadsoftware, Dateireputation, Dateitypblock:**</span><span class="sxs-lookup"><span data-stu-id="079a5-276">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="079a5-277">**Dateizuruf:** Nachrichten, die aufgrund der Identifizierung einer angefügten Datei von anderen Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="079a5-277">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="079a5-278">**Dateitypblock:** Nachrichten, die aufgrund des typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="079a5-278">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="079a5-279">**Antiphishing, URL-Zuverlässigkeit, Markenidentitätswechsel, Antispoofing:**</span><span class="sxs-lookup"><span data-stu-id="079a5-279">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="079a5-280">**URL-Zuverlässigkeit:** Nachrichten, die aufgrund der Identifizierung der URL von anderen Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="079a5-280">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="079a5-281">**Markenidentitätswechsel:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die von bekannten Absendern als Absender imitiert wurde.</span><span class="sxs-lookup"><span data-stu-id="079a5-281">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="079a5-282">**Antispoofing:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die versucht, eine Domäne zu spoofen, zu der der Empfänger gehört, oder einer Domäne, die der Absender der Nachricht nicht besitzt.</span><span class="sxs-lookup"><span data-stu-id="079a5-282">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="079a5-283">**Antispam, Massen-E-Mail-Filterung:**</span><span class="sxs-lookup"><span data-stu-id="079a5-283">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="079a5-284">**Massen-E-Mail-Filterung:** Nachrichten, die basierend auf dem BCL-Schwellenwert (Bulk Complain Level) in einer Antispamrichtlinie gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="079a5-284">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="079a5-285">**Benutzer- und Domänenidentitätswechsel (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="079a5-285">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="079a5-286">**Benutzeridentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, einen Benutzer (Nachrichtensender) zu imitieren, der in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="079a5-286">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="079a5-287">**Domänenidentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, eine Domäne zu imitieren, die in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="079a5-287">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="079a5-288">**Datei- und URL-Detonation (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="079a5-288">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="079a5-289">**Dateidetonation:** Nachrichten, die nach einer Safe Anlagenrichtlinie gefiltert sind.</span><span class="sxs-lookup"><span data-stu-id="079a5-289">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="079a5-290">**URL-Detonation:** Nachricht, gefiltert nach einer Safe Links-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="079a5-290">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="079a5-291">**Schutz nach der Zustellung und ZAP (ATP) oder ZAP (EOP):** Automatische Nullstunde-Bereinigung (ZAP) für Schadsoftware, Spam und Phishing.</span><span class="sxs-lookup"><span data-stu-id="079a5-291">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="079a5-292">Wenn Sie eine Zeile in der Detailtabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="079a5-292">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="079a5-293">Exportieren aus der Trichteransicht</span><span class="sxs-lookup"><span data-stu-id="079a5-293">Export from Funnel view</span></span>

<span data-ttu-id="079a5-294">Nachdem Sie unter **"Optionen"** auf **"Exportieren"** geklickt haben, können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="079a5-294">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="079a5-295">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="079a5-295">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="079a5-296">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="079a5-296">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="079a5-297">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .**</span><span class="sxs-lookup"><span data-stu-id="079a5-297">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="079a5-298">Daten für die aktuellen Filter werden in eine .csv Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="079a5-298">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="079a5-299">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="079a5-299">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="079a5-300">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="079a5-300">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Trichteransicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="079a5-302">Tech-Ansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="079a5-303">Die **Tech-Ansicht** ähnelt der **Trichteransicht** und bietet detailliertere Details für die konfigurierten Funktionen zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="079a5-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="079a5-304">Im Diagramm können Sie sehen, wie Nachrichten in den verschiedenen Phasen des Bedrohungsschutzes kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="079a5-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="079a5-305">Wenn Sie standardmäßig auf die Registerkarte **"Tech-Ansicht"** klicken, enthält diese Ansicht ein Diagramm und eine Detailtabelle, die mit den folgenden Filtern konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="079a5-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="079a5-306">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="079a5-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="079a5-307">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="079a5-307">**Direction**:</span></span>
  - <span data-ttu-id="079a5-308">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="079a5-308">**Inbound**</span></span>
  - <span data-ttu-id="079a5-309">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="079a5-309">**Outbound**</span></span>
  - <span data-ttu-id="079a5-310">**Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="079a5-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="079a5-311">absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von eingehenden und ausgehenden Zählungen)</span><span class="sxs-lookup"><span data-stu-id="079a5-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="079a5-312">Die Aggregatansicht und die Detailtabellenansicht ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="079a5-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="079a5-313">Sie können diese Filter ändern, indem Sie auf **"Filter"** klicken.</span><span class="sxs-lookup"><span data-stu-id="079a5-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="079a5-314">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="079a5-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="079a5-315">Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:</span><span class="sxs-lookup"><span data-stu-id="079a5-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="079a5-316">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="079a5-316">**Total email**</span></span>
- <span data-ttu-id="079a5-317">**Edge zulassen** und **Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="079a5-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="079a5-318">**Transportregel zulassen** und **Transportregel gefiltert** (Nachrichtenflussregeln)</span><span class="sxs-lookup"><span data-stu-id="079a5-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="079a5-319">**Keine Schadsoftware,** **Safe Erkennung von Anlagen** und Erkennung von <sup>\*</sup> **Antischadsoftwaremodulen**</span><span class="sxs-lookup"><span data-stu-id="079a5-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="079a5-320">**Keine Phishing-,** **DMARC-Fehler,** **Identitätswechselerkennung,** <sup>\*</sup> **Spooferkennung** und **Phishing-Erkennung**</span><span class="sxs-lookup"><span data-stu-id="079a5-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="079a5-321">**Keine Erkennung mit URL-Detonation** und **URL-Detonationserkennung**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="079a5-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="079a5-322">**Keine Spam-** und  **Spamnachrichten**</span><span class="sxs-lookup"><span data-stu-id="079a5-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="079a5-323">**Nicht böswillige E-Mails,** **Safe-Links-Erkennung** <sup>\*</sup> und **ZAP**</span><span class="sxs-lookup"><span data-stu-id="079a5-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="079a5-324"><sup>\*</sup>Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="079a5-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="079a5-325">Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, können Sie die Anzahl der Nachrichten in dieser Kategorie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="079a5-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="079a5-326">Die Detailtabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="079a5-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="079a5-327">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="079a5-327">**Date (UTC)**</span></span>
- <span data-ttu-id="079a5-328">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="079a5-328">**Total email**</span></span>
- <span data-ttu-id="079a5-329">**Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="079a5-329">**Edge filtered**</span></span>
- <span data-ttu-id="079a5-330">**Regelnachrichten:** Nachrichten, die aufgrund von Nachrichtenflussregeln gefiltert wurden (auch als Transportregeln bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="079a5-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="079a5-331">**Antischadsoftwaremodul**, **Safe** <sup>\*</sup> Anlagen:</span><span class="sxs-lookup"><span data-stu-id="079a5-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="079a5-332">**DMARC, Identitätswechsel,** <sup>\*</sup> **Spoofing**, **Phishing gefiltert:**</span><span class="sxs-lookup"><span data-stu-id="079a5-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="079a5-333">**DMARC:** Nachrichten, die aufgrund eines Fehlers bei der DMARC-Authentifizierungsprüfung gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="079a5-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="079a5-334">**ERKENNUNG DER URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="079a5-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="079a5-335">**Antispam gefiltert**</span><span class="sxs-lookup"><span data-stu-id="079a5-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="079a5-336">**ZAP entfernt**</span><span class="sxs-lookup"><span data-stu-id="079a5-336">**ZAP removed**</span></span>
- <span data-ttu-id="079a5-337">**Erkennung durch Safe Links**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="079a5-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="079a5-338"><sup>\*</sup>Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="079a5-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="079a5-339">Wenn Sie eine Zeile in der Detailtabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="079a5-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="079a5-340">Exportieren aus der Tech-Ansicht</span><span class="sxs-lookup"><span data-stu-id="079a5-340">Export from Tech view</span></span>

<span data-ttu-id="079a5-341">Wenn Sie auf **"Exportieren"** klicken, können Sie unter **"Optionen"** einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="079a5-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="079a5-342">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="079a5-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="079a5-343">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="079a5-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="079a5-344">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .**</span><span class="sxs-lookup"><span data-stu-id="079a5-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="079a5-345">Daten für die aktuellen Filter werden in eine .csv Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="079a5-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="079a5-346">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="079a5-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="079a5-347">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="079a5-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Tech-Ansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="079a5-349">Bericht über Schadsoftwareerkennungen</span><span class="sxs-lookup"><span data-stu-id="079a5-349">Malware detections report</span></span>

<span data-ttu-id="079a5-350">Der Bericht über **Schadsoftwareerkennungen** enthält Informationen zu Schadsoftwareerkennungen in eingehenden und ausgehenden E-Mail-Nachrichten (von Exchange Online Protection oder EOP erkannte Schadsoftware).</span><span class="sxs-lookup"><span data-stu-id="079a5-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="079a5-351">Weitere Informationen zum Schutz vor Schadsoftware in EOP finden Sie unter [Antischadsoftwareschutz in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="079a5-352">Der Aggregatansichtsfilter lässt 90 Tage zu, während der Detailtabellenfilter nur 10 Tage zulässt.</span><span class="sxs-lookup"><span data-stu-id="079a5-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="079a5-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="079a5-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="079a5-354">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** nach Schadsoftware, die **in E-Mails erkannt wurde,** und klicken Sie dann auf **Details anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="079a5-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="079a5-355">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="079a5-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Schadsoftwareerkennungen im E-Mail-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/malware-detections-widget.png)

<span data-ttu-id="079a5-357">Auf der Berichtsseite **für Schadsoftwareerkennungen** können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="079a5-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="079a5-358">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-359">**Richtung:** **Ein-** und **Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="079a5-359">**Direction**: **Inbound** and **Outbound**</span></span>

![Berichtsansicht im Bericht "Schadsoftwareerkennung in E-Mail"](../../media/malware-detections-report-view.png)

<span data-ttu-id="079a5-361">In der Detailtabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="079a5-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="079a5-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="079a5-362">**Date**</span></span>
- <span data-ttu-id="079a5-363">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="079a5-363">**Sender address**</span></span>
- <span data-ttu-id="079a5-364">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="079a5-364">**Recipient address**</span></span>
- <span data-ttu-id="079a5-365">**Nachrichten-ID:** Verfügbar im **Nachrichten-ID-Kopfzeilenfeld** im Nachrichtenkopf und sollte eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="079a5-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="079a5-366">Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (beachten Sie die spitzen Klammern).</span><span class="sxs-lookup"><span data-stu-id="079a5-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="079a5-367">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="079a5-367">**Subject**</span></span>
- <span data-ttu-id="079a5-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="079a5-368">**Filename**</span></span>
- <span data-ttu-id="079a5-369">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="079a5-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="079a5-370">E-Mail-Latenzbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-370">Mail latency report</span></span>

<span data-ttu-id="079a5-371">Der **E-Mail-Latenzbericht** in Defender für Office 365 enthält Informationen zur E-Mail-Zustellungs- und Detonationslatenz, die in Ihrer Organisation aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="079a5-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="079a5-372">Weitere Informationen finden Sie im [E-Mail-Latenzbericht.](view-reports-for-mdo.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="079a5-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="079a5-373">Spamerkennungsbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="079a5-374">Der **Spamerkennungsbericht** wird schließlich entfernt.</span><span class="sxs-lookup"><span data-stu-id="079a5-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="079a5-375">Die gleichen Informationen sind im [Bedrohungsschutzstatusbericht](#threat-protection-status-report)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="079a5-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="079a5-376">Bericht über Spooferkennungen</span><span class="sxs-lookup"><span data-stu-id="079a5-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="079a5-377">Der verbesserte Bericht über Spooferkennungen, wie in diesem Artikel beschrieben, befindet sich in der Vorschau, kann geändert werden und ist nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="079a5-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="079a5-378">Die ältere Version des Berichts zeigt nur **gute E-Mails** und **"Als Spam abgefangen"** an.</span><span class="sxs-lookup"><span data-stu-id="079a5-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="079a5-379">Der Bericht **"Spooferkennungen"** enthält Informationen zu Nachrichten, die aufgrund von Spoofing blockiert oder zugelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="079a5-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="079a5-380">Weitere Informationen zum Spoofing finden Sie unter [Antispoofingschutz in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="079a5-381">Die Aggregatansicht des Berichts lässt 45 Tage Filterung <sup>\*</sup> zu, während die Detailansicht nur zehn Tage Filterung zulässt.</span><span class="sxs-lookup"><span data-stu-id="079a5-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="079a5-382"><sup>\*</sup> Schließlich können Sie die Filterung bis zu 90 Tage verwenden.</span><span class="sxs-lookup"><span data-stu-id="079a5-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="079a5-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="079a5-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="079a5-384">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** **nach Spooferkennungen,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="079a5-385">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="079a5-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Spooferkennungs-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/spoof-detections-widget.png)

<span data-ttu-id="079a5-387">Das Diagramm zeigt die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="079a5-387">The chart shows the following information:</span></span>

- <span data-ttu-id="079a5-388">**bestehen**</span><span class="sxs-lookup"><span data-stu-id="079a5-388">**Pass**</span></span>
- <span data-ttu-id="079a5-389">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="079a5-389">**Fail**</span></span>
- <span data-ttu-id="079a5-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="079a5-390">**SoftPass**</span></span>
- <span data-ttu-id="079a5-391">**Keine**</span><span class="sxs-lookup"><span data-stu-id="079a5-391">**None**</span></span>
- <span data-ttu-id="079a5-392">**Other**</span><span class="sxs-lookup"><span data-stu-id="079a5-392">**Other**</span></span>

<span data-ttu-id="079a5-393">Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, können Sie sehen, wie viele gefälschte Nachrichten erkannt wurden und warum.</span><span class="sxs-lookup"><span data-stu-id="079a5-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="079a5-394">Auf der Seite **"Spoof-E-Mail-Bericht"** können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="079a5-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="079a5-395">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-396">**Ergebnis:**</span><span class="sxs-lookup"><span data-stu-id="079a5-396">**Result**:</span></span>
  - <span data-ttu-id="079a5-397">**bestehen**</span><span class="sxs-lookup"><span data-stu-id="079a5-397">**Pass**</span></span>
  - <span data-ttu-id="079a5-398">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="079a5-398">**Fail**</span></span>
  - <span data-ttu-id="079a5-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="079a5-399">**SoftPass**</span></span>
  - <span data-ttu-id="079a5-400">**Keine**</span><span class="sxs-lookup"><span data-stu-id="079a5-400">**None**</span></span>
  - <span data-ttu-id="079a5-401">**Other**</span><span class="sxs-lookup"><span data-stu-id="079a5-401">**Other**</span></span>
- <span data-ttu-id="079a5-402">**Spooftyp:** **Intern** und **extern**</span><span class="sxs-lookup"><span data-stu-id="079a5-402">**Spoof type**: **Internal** and **External**</span></span>

![Seite "Spoof-E-Mail-Bericht" im Microsoft 365 Defender-Portal](../../media/spoof-detections-report-page.png)

<span data-ttu-id="079a5-404">In der Detailtabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="079a5-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="079a5-405">**Date**</span><span class="sxs-lookup"><span data-stu-id="079a5-405">**Date**</span></span>
- <span data-ttu-id="079a5-406">**Gefälschter Benutzer**</span><span class="sxs-lookup"><span data-stu-id="079a5-406">**Spoofed user**</span></span>
- <span data-ttu-id="079a5-407">**Senden der Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="079a5-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="079a5-408">**Spooftyp**</span><span class="sxs-lookup"><span data-stu-id="079a5-408">**Spoof type**</span></span>
- <span data-ttu-id="079a5-409">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="079a5-409">**Result**</span></span>
- <span data-ttu-id="079a5-410">**Ergebniscode**</span><span class="sxs-lookup"><span data-stu-id="079a5-410">**Result code**</span></span>
- <span data-ttu-id="079a5-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="079a5-411">**SPF**</span></span>
- <span data-ttu-id="079a5-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="079a5-412">**DKIM**</span></span>
- <span data-ttu-id="079a5-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="079a5-413">**DMARC**</span></span>
- <span data-ttu-id="079a5-414">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="079a5-414">**Message count**</span></span>

<span data-ttu-id="079a5-415">Weitere Informationen zu Ergebniscodes für die zusammengesetzte Authentifizierung finden Sie unter [Antispam-Nachrichtenkopfzeilen in Microsoft 365.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="079a5-416">Übermittlungsbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-416">Submissions report</span></span>

<span data-ttu-id="079a5-417">Der **Bericht "Übermittlungen"** enthält Informationen zu Elementen, die Administratoren microsoft zur Analyse gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="079a5-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="079a5-418">Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="079a5-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="079a5-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="079a5-420">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** **nach Übermittlungen,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="079a5-421">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/adminSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="079a5-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="079a5-422">Wenn Sie im Microsoft 365 Defender Portal zu [Administratorübermittlungen](admin-submission.md)wechseln möchten, klicken Sie auf **"Zu Übermittlungen wechseln".**</span><span class="sxs-lookup"><span data-stu-id="079a5-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Übermittlungs-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/submissions-report-widget.png)

<span data-ttu-id="079a5-424">Das Diagramm zeigt die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="079a5-424">The chart shows the following information:</span></span>

- <span data-ttu-id="079a5-425">**Ausstehend**</span><span class="sxs-lookup"><span data-stu-id="079a5-425">**Pending**</span></span>
- <span data-ttu-id="079a5-426">**Abgeschlossen**</span><span class="sxs-lookup"><span data-stu-id="079a5-426">**Completed**</span></span>

<span data-ttu-id="079a5-427">Auf der Seite **"Übermittlungen"** können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="079a5-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="079a5-428">**Gemeldetes Datum**: **Startzeit** und **Endzeit**</span><span class="sxs-lookup"><span data-stu-id="079a5-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="079a5-429">**Übermittlungstyp:** **E-Mail,** **URL** oder **Datei**</span><span class="sxs-lookup"><span data-stu-id="079a5-429">**Submission type**: **Email**, **URL**, or **File**</span></span>
- <span data-ttu-id="079a5-430">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="079a5-430">**Submission ID**</span></span>
- <span data-ttu-id="079a5-431">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="079a5-431">**Network Message ID**</span></span>
- <span data-ttu-id="079a5-432">**Sender**</span><span class="sxs-lookup"><span data-stu-id="079a5-432">**Sender**</span></span>
- <span data-ttu-id="079a5-433">**Name**</span><span class="sxs-lookup"><span data-stu-id="079a5-433">**Name**</span></span>
- <span data-ttu-id="079a5-434">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="079a5-434">**Submitted by**</span></span>
- <span data-ttu-id="079a5-435">**Grund für die Übermittlung:** **keine Junk-,** **Phishing-,** **Schadsoftware-** oder **Spam-Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="079a5-435">**Reason for submitting**: **Not junk**, **Phish**, **Malware**, or **Spam**</span></span>
- <span data-ttu-id="079a5-436">**Status des erneuten Scannens:** **Ausstehend** oder **abgeschlossen**</span><span class="sxs-lookup"><span data-stu-id="079a5-436">**Rescan status**: **Pending** or **Completed**</span></span>

<span data-ttu-id="079a5-437">Die Detailtabelle unterhalb des Diagramms zeigt die gleichen Informationen und verfügt über die gleichen **Gruppen-** oder **Anpassungsspaltenoptionen** wie auf der Registerkarte **"Für Analyse übermittelt"** unter **"E-Mail &** \> **Übermittlungen zur** Zusammenarbeit".</span><span class="sxs-lookup"><span data-stu-id="079a5-437">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="079a5-438">Weitere Informationen finden Sie unter [Anzeigen von Administratorübermittlungen an Microsoft.](admin-submission.md#view-admin-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="079a5-438">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Übermittlungsberichtsseite im Microsoft 365 Defender Portal](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="079a5-440">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-440">Threat protection status report</span></span>

<span data-ttu-id="079a5-441">Der **Statusbericht zum Bedrohungsschutz** ist sowohl in EOP als auch in Defender für Office 365 verfügbar. Die Berichte enthalten jedoch unterschiedliche Daten.</span><span class="sxs-lookup"><span data-stu-id="079a5-441">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="079a5-442">EOP-Kunden können z. B. Informationen zu schadsoftware anzeigen, die in E-Mails erkannt wurde, aber keine Informationen zu schädlichen Dateien, die von [Safe Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="079a5-442">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="079a5-443">Der Bericht enthält die Anzahl der E-Mail-Nachrichten mit schädlichen Inhalten, z. B. Dateien oder Websiteadressen (URLs), die vom Antischadsoftwaremodul blockiert wurden, Zap [(Zero-Hour Auto Purge)](zero-hour-auto-purge.md)und Defender für Office 365 Features wie [Safe Links,](safe-links.md)Safe Anlagen und [Identitätswechselschutzfeatures in Antiphishingrichtlinien.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) [](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-443">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="079a5-444">Anhand dieser Informationen können Sie Trends erkennen oder ermitteln, ob Die Unternehmensrichtlinien angepasst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="079a5-444">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="079a5-445">**Hinweis:** Es ist wichtig zu wissen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="079a5-445">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="079a5-446">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="079a5-446">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="079a5-447">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** den **Status des Bedrohungsschutzes,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-447">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="079a5-448">Um direkt zum Bericht zu wechseln, öffnen Sie eine der folgenden URLs:</span><span class="sxs-lookup"><span data-stu-id="079a5-448">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="079a5-449">Defender für Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="079a5-449">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="079a5-450">Eop: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="079a5-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Bedrohungsschutzstatus-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="079a5-452">Standardmäßig werden im Diagramm Daten für die letzten 7 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="079a5-452">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="079a5-453">Wenn Sie auf der Seite **"Statusbericht zum Bedrohungsschutz"** auf **"Filtern"** klicken, können Sie einen Zeitraum von 90 Tagen auswählen (Testabonnements sind möglicherweise auf 30 Tage begrenzt).</span><span class="sxs-lookup"><span data-stu-id="079a5-453">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="079a5-454">Die Detailtabelle ermöglicht das Filtern für 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="079a5-454">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="079a5-455">Die verfügbaren Ansichten werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="079a5-455">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="079a5-456">Anzeigen von Daten nach Übersicht</span><span class="sxs-lookup"><span data-stu-id="079a5-456">View data by Overview</span></span>

![Übersichtsansicht im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="079a5-458">In der Ansicht **"Ansichtsdaten nach Übersicht"** werden die folgenden Erkennungsinformationen im Diagramm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="079a5-458">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="079a5-459">**E-Mail-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="079a5-459">**Email malware**</span></span>
- <span data-ttu-id="079a5-460">**E-Mail-Phishing**</span><span class="sxs-lookup"><span data-stu-id="079a5-460">**Email phish**</span></span>
- <span data-ttu-id="079a5-461">**Inhalts-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="079a5-461">**Content malware**</span></span>

<span data-ttu-id="079a5-462">Unterhalb des Diagramms ist keine Detailtabelle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="079a5-462">No details table is available below the chart.</span></span>

<span data-ttu-id="079a5-463">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-463">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="079a5-464">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-464">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-465">**Erkennung:** **E-Mail-Schadsoftware,** **E-Mail-Phishing** oder **Inhalts-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="079a5-465">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="079a5-466">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="079a5-466">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="079a5-467">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="079a5-467">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="079a5-468">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-468">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="079a5-469">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="079a5-469">**Direction**</span></span>
- <span data-ttu-id="079a5-470">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="079a5-470">**Domain**</span></span>
- <span data-ttu-id="079a5-471">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="079a5-471">**Policy type**</span></span>

<span data-ttu-id="079a5-472">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-472">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="079a5-473">Anzeigen von Daten nach E-Mail-Phishing \> und Diagrammstrukturplan nach Erkennungstechnologie</span><span class="sxs-lookup"><span data-stu-id="079a5-473">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Ansicht der Erkennungstechnologie für Phishing-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="079a5-475">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span><span class="sxs-lookup"><span data-stu-id="079a5-475">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="079a5-476">**URL malicious reputation:** <sup>\*</sup> Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span><span class="sxs-lookup"><span data-stu-id="079a5-476">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="079a5-477">**Erweiterter Filter:** Phishingsignale basierend auf maschinellem Lernen.</span><span class="sxs-lookup"><span data-stu-id="079a5-477">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="079a5-478">**Allgemeiner Filter:** Phishingsignale basierend auf Analystenregeln.</span><span class="sxs-lookup"><span data-stu-id="079a5-478">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="079a5-479">**Organisationsinternes Spoofing:** Der Absender versucht, die Empfängerdomäne zu spoofen.</span><span class="sxs-lookup"><span data-stu-id="079a5-479">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="079a5-480">**Spoofing externer Domäne:** Der Absender versucht, eine andere Domäne zu spoofen.</span><span class="sxs-lookup"><span data-stu-id="079a5-480">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="079a5-481">**Spoofing von DMARC:** DMARC-Authentifizierungsfehler bei Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="079a5-481">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="079a5-482">**Identitätswechselmarke:** Identitätswechsel bekannter Marken basierend auf Absendern.</span><span class="sxs-lookup"><span data-stu-id="079a5-482">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="079a5-483">**Erkennung durch gemischte Analysen**</span><span class="sxs-lookup"><span data-stu-id="079a5-483">**Mixed analysis detection**</span></span>
- <span data-ttu-id="079a5-484">**Datei-Reputation**</span><span class="sxs-lookup"><span data-stu-id="079a5-484">**File reputation**</span></span>
- <span data-ttu-id="079a5-485">**Fingerabdruckübereinstimmung**</span><span class="sxs-lookup"><span data-stu-id="079a5-485">**Fingerprint matching**</span></span>
- <span data-ttu-id="079a5-486">**Zuverlässigkeit der URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="079a5-486">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="079a5-487">**URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="079a5-487">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="079a5-488">**Identitätswechselbenutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="079a5-488">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="079a5-489">**Identitätswechseldomäne:** <sup>\*</sup> Identitätswechsel von Domänen, die der Kunde besitzt oder definiert.</span><span class="sxs-lookup"><span data-stu-id="079a5-489">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="079a5-490">**Identitätswechsel bei der Postfachintelligenz:** <sup>\*</sup> Identitätswechsel von Benutzern, die vom Administrator definiert oder durch die Postfachintelligenz gelernt wurden.</span><span class="sxs-lookup"><span data-stu-id="079a5-490">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="079a5-491">**Dateidetonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="079a5-491">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="079a5-492">**Kampagne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="079a5-492">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="079a5-493">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-493">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="079a5-494">**Date**</span><span class="sxs-lookup"><span data-stu-id="079a5-494">**Date**</span></span>
- <span data-ttu-id="079a5-495">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="079a5-495">**Subject**</span></span>
- <span data-ttu-id="079a5-496">**Sender**</span><span class="sxs-lookup"><span data-stu-id="079a5-496">**Sender**</span></span>
- <span data-ttu-id="079a5-497">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="079a5-497">**Recipients**</span></span>
- <span data-ttu-id="079a5-498">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="079a5-498">**Detected by**</span></span>
- <span data-ttu-id="079a5-499">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="079a5-499">**Delivery Status**</span></span>
- <span data-ttu-id="079a5-500">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="079a5-500">**Source of Compromise**</span></span>
- <span data-ttu-id="079a5-501">**Tags**</span><span class="sxs-lookup"><span data-stu-id="079a5-501">**Tags**</span></span>

<span data-ttu-id="079a5-502">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-502">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="079a5-503">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-503">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-504">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="079a5-504">**Detection**</span></span>
- <span data-ttu-id="079a5-505">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="079a5-505">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="079a5-506">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="079a5-506">**Direction**</span></span>
- <span data-ttu-id="079a5-507">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="079a5-507">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="079a5-508">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-508">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="079a5-509">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="079a5-509">**Domain**</span></span>
- <span data-ttu-id="079a5-510">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="079a5-510">**Policy type**</span></span>
- <span data-ttu-id="079a5-511">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="079a5-511">**Policy name** (details table only)</span></span>
- <span data-ttu-id="079a5-512">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="079a5-512">**Recipients**</span></span>

<span data-ttu-id="079a5-513">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-513">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="079a5-514">Anzeigen von Daten nach \> E-Mail-Schadsoftware und Diagrammstrukturplan nach Erkennungstechnologie</span><span class="sxs-lookup"><span data-stu-id="079a5-514">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Ansicht der Erkennungstechnologie für Schadsoftware im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="079a5-516">In der **Ansicht Ansichtsdaten nach E-Mail-Schadsoftware \>** und **Diagrammstrukturplan nach Erkennungstechnologie** werden die folgenden Informationen im Diagramm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="079a5-516">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="079a5-517">**Dateidetonation:** <sup>\*</sup> Erkennung durch Safe Anlagen.</span><span class="sxs-lookup"><span data-stu-id="079a5-517">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="079a5-518">**Zuverlässigkeit der Dateidetonation:** <sup>\*</sup> Alle bösartigen Dateireputationen, die von Defender für Office 365 Detonationen generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="079a5-518">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="079a5-519">**Datei-Reputation**</span><span class="sxs-lookup"><span data-stu-id="079a5-519">**File reputation**</span></span>
- <span data-ttu-id="079a5-520">**Antischadsoftwaremodul:** <sup>\*</sup> Erkennung von Antischadsoftwaremodulen.</span><span class="sxs-lookup"><span data-stu-id="079a5-520">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="079a5-521">Dateitypblock für **Antischadsoftwarerichtlinie:** Hierbei handelt es sich um E-Mail-Nachrichten, die aufgrund des in der Nachricht identifizierten Typs bösartiger Dateien herausgefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="079a5-521">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="079a5-522">**URL-Reputation als schädlich eingestuft**</span><span class="sxs-lookup"><span data-stu-id="079a5-522">**URL malicious reputation**</span></span>
- <span data-ttu-id="079a5-523">**URL-Detonation**</span><span class="sxs-lookup"><span data-stu-id="079a5-523">**URL detonation**</span></span>
- <span data-ttu-id="079a5-524">**Reputation der URL-Detonation**</span><span class="sxs-lookup"><span data-stu-id="079a5-524">**URL detonation reputation**</span></span>
- <span data-ttu-id="079a5-525">**Kampagnen**</span><span class="sxs-lookup"><span data-stu-id="079a5-525">**Campaign**</span></span>

<span data-ttu-id="079a5-526">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-526">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="079a5-527">**Date**</span><span class="sxs-lookup"><span data-stu-id="079a5-527">**Date**</span></span>
- <span data-ttu-id="079a5-528">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="079a5-528">**Subject**</span></span>
- <span data-ttu-id="079a5-529">**Sender**</span><span class="sxs-lookup"><span data-stu-id="079a5-529">**Sender**</span></span>
- <span data-ttu-id="079a5-530">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="079a5-530">**Recipients**</span></span>
- <span data-ttu-id="079a5-531">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="079a5-531">**Detected by**</span></span>
- <span data-ttu-id="079a5-532">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="079a5-532">**Delivery Status**</span></span>
- <span data-ttu-id="079a5-533">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="079a5-533">**Source of Compromise**</span></span>
- <span data-ttu-id="079a5-534">**Tags**</span><span class="sxs-lookup"><span data-stu-id="079a5-534">**Tags**</span></span>

<span data-ttu-id="079a5-535">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-535">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="079a5-536">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-536">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-537">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="079a5-537">**Detection**</span></span>
- <span data-ttu-id="079a5-538">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="079a5-538">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="079a5-539">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="079a5-539">**Direction**</span></span>
- <span data-ttu-id="079a5-540">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="079a5-540">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="079a5-541">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-541">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="079a5-542">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="079a5-542">**Domain**</span></span>
- <span data-ttu-id="079a5-543">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="079a5-543">**Policy type**</span></span>
- <span data-ttu-id="079a5-544">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="079a5-544">**Policy name** (details table only)</span></span>
- <span data-ttu-id="079a5-545">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="079a5-545">**Recipients**</span></span>

<span data-ttu-id="079a5-546">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-546">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="079a5-547">Diagrammaufschlüsselung nach Richtlinientyp und Anzeigen von Daten nach E-Mail-Phishing \> oder Anzeigen von Daten durch E-Mail-Schadsoftware \></span><span class="sxs-lookup"><span data-stu-id="079a5-547">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Richtlinientypansicht für Phishing-E-Mails oder Schadsoftware-E-Mails im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="079a5-549">In der **Diagrammaufschlüsselung nach Richtlinientyp** und **Anzeigen von Daten nach E-Mail-Phishing \>** oder **Anzeigen von Daten nach E-Mail-Schadsoftwareansichten \>** werden die folgenden Informationen in den Diagrammen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="079a5-549">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="079a5-550">**Antischadsoftware**</span><span class="sxs-lookup"><span data-stu-id="079a5-550">**Anti-malware**</span></span>
- <span data-ttu-id="079a5-551">**Safe Anlagen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="079a5-551">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="079a5-552">**Antiphishing**</span><span class="sxs-lookup"><span data-stu-id="079a5-552">**Anti-phish**</span></span>
- <span data-ttu-id="079a5-553">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="079a5-553">**Anti-spam**</span></span>
- <span data-ttu-id="079a5-554">**Nachrichtenflussregel** (auch als Transportregel bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="079a5-554">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="079a5-555">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="079a5-555">**Others**</span></span>

<span data-ttu-id="079a5-556">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-556">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="079a5-557">**Date**</span><span class="sxs-lookup"><span data-stu-id="079a5-557">**Date**</span></span>
- <span data-ttu-id="079a5-558">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="079a5-558">**Subject**</span></span>
- <span data-ttu-id="079a5-559">**Sender**</span><span class="sxs-lookup"><span data-stu-id="079a5-559">**Sender**</span></span>
- <span data-ttu-id="079a5-560">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="079a5-560">**Recipients**</span></span>
- <span data-ttu-id="079a5-561">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="079a5-561">**Detected by**</span></span>
- <span data-ttu-id="079a5-562">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="079a5-562">**Delivery Status**</span></span>
- <span data-ttu-id="079a5-563">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="079a5-563">**Source of Compromise**</span></span>
- <span data-ttu-id="079a5-564">**Tags**</span><span class="sxs-lookup"><span data-stu-id="079a5-564">**Tags**</span></span>

<span data-ttu-id="079a5-565">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-565">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="079a5-566">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-566">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-567">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="079a5-567">**Detection**</span></span>
- <span data-ttu-id="079a5-568">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="079a5-568">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="079a5-569">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="079a5-569">**Direction**</span></span>
- <span data-ttu-id="079a5-570">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="079a5-570">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="079a5-571">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-571">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="079a5-572">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="079a5-572">**Domain**</span></span>
- <span data-ttu-id="079a5-573">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="079a5-573">**Policy type**</span></span>
- <span data-ttu-id="079a5-574">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="079a5-574">**Policy name** (details table only)</span></span>
- <span data-ttu-id="079a5-575">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="079a5-575">**Recipients**</span></span>

<span data-ttu-id="079a5-576">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-576">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="079a5-577">Diagrammaufschlüsselung nach Zustellungsstatus und Anzeigen von Daten nach E-Mail-Phishing \> oder Anzeigen von Daten durch E-Mail-Schadsoftware \></span><span class="sxs-lookup"><span data-stu-id="079a5-577">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Übermittlungsstatusansicht für Phishing-E-Mails und Schadsoftware-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="079a5-579">In der **Diagrammaufschlüsselung nach Übermittlungsstatus** und **Anzeigen von Daten nach E-Mail-Phishing \>** oder **Anzeigen von Daten nach E-Mail-Schadsoftwareansichten \>** werden die folgenden Informationen in den Diagrammen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="079a5-579">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="079a5-580">**Gehostetes Postfach: Posteingang**</span><span class="sxs-lookup"><span data-stu-id="079a5-580">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="079a5-581">**Gehostetes Postfach: Junk**</span><span class="sxs-lookup"><span data-stu-id="079a5-581">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="079a5-582">**Gehostetes Postfach: Benutzerdefinierter Ordner**</span><span class="sxs-lookup"><span data-stu-id="079a5-582">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="079a5-583">**Gehostetes Postfach: Gelöschte Elemente**</span><span class="sxs-lookup"><span data-stu-id="079a5-583">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="079a5-584">**Weitergeleitet**</span><span class="sxs-lookup"><span data-stu-id="079a5-584">**Forwarded**</span></span>
- <span data-ttu-id="079a5-585">**Lokaler Server: Bereitgestellt**</span><span class="sxs-lookup"><span data-stu-id="079a5-585">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="079a5-586">**Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="079a5-586">**Quarantine**</span></span>
- <span data-ttu-id="079a5-587">**Übermittlung fehlgeschlagen**</span><span class="sxs-lookup"><span data-stu-id="079a5-587">**Delivery failed**</span></span>
- <span data-ttu-id="079a5-588">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="079a5-588">**Dropped**</span></span>

<span data-ttu-id="079a5-589">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-589">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="079a5-590">**Date**</span><span class="sxs-lookup"><span data-stu-id="079a5-590">**Date**</span></span>
- <span data-ttu-id="079a5-591">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="079a5-591">**Subject**</span></span>
- <span data-ttu-id="079a5-592">**Sender**</span><span class="sxs-lookup"><span data-stu-id="079a5-592">**Sender**</span></span>
- <span data-ttu-id="079a5-593">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="079a5-593">**Recipients**</span></span>
- <span data-ttu-id="079a5-594">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="079a5-594">**Detected by**</span></span>
- <span data-ttu-id="079a5-595">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="079a5-595">**Delivery Status**</span></span>
- <span data-ttu-id="079a5-596">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="079a5-596">**Source of Compromise**</span></span>
- <span data-ttu-id="079a5-597">**Tags**</span><span class="sxs-lookup"><span data-stu-id="079a5-597">**Tags**</span></span>

<span data-ttu-id="079a5-598">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-598">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="079a5-599">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-599">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-600">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="079a5-600">**Detection**</span></span>
- <span data-ttu-id="079a5-601">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="079a5-601">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="079a5-602">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="079a5-602">**Direction**</span></span>
- <span data-ttu-id="079a5-603">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="079a5-603">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="079a5-604">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-604">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="079a5-605">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="079a5-605">**Domain**</span></span>
- <span data-ttu-id="079a5-606">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="079a5-606">**Policy type**</span></span>
- <span data-ttu-id="079a5-607">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="079a5-607">**Policy name** (details table only)</span></span>
- <span data-ttu-id="079a5-608">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="079a5-608">**Recipients**</span></span>

<span data-ttu-id="079a5-609">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-609">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="079a5-610">Anzeigen von Daten nach \> Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="079a5-610">View data by Content \> Malware</span></span>

![Ansicht "Inhalts-Schadsoftware" im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="079a5-612">In der Ansicht **"Daten nach \> Inhalts-Schadsoftware** anzeigen" werden die folgenden Informationen im Diagramm für Microsoft Defender für Office 365 Organisationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="079a5-612">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="079a5-613">**Antischadsoftwaremodul:** Schädliche Dateien, die in SharePoint, OneDrive und Microsoft Teams von der [integrierten Virenerkennung in Microsoft 365](virus-detection-in-spo.md)erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="079a5-613">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="079a5-614">**Dateidetonation:** Schädliche Dateien, die von [Safe Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="079a5-614">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="079a5-615">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-615">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="079a5-616">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-616">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-617">**Standort**</span><span class="sxs-lookup"><span data-stu-id="079a5-617">**Location**</span></span>
- <span data-ttu-id="079a5-618">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="079a5-618">**Detected by**</span></span>
- <span data-ttu-id="079a5-619">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="079a5-619">**Malware name**</span></span>

<span data-ttu-id="079a5-620">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-620">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="079a5-621">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-621">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-622">**Erkennung:** **Antischadsoftwaremodul** oder **Dateidetonation**</span><span class="sxs-lookup"><span data-stu-id="079a5-622">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="079a5-623">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-623">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="079a5-624">Anzeigen von Daten nach Systemüberschreibung</span><span class="sxs-lookup"><span data-stu-id="079a5-624">View data by System override</span></span>

![Ansicht "Nachrichtenüberschreibung" im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="079a5-626">In der Ansicht **"Ansichtsdaten nach Systemüberschreibung"** werden die folgenden Informationen zum Außerkraftsetzungsgrund im Diagramm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="079a5-626">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="079a5-627">**Lokales Überspringen**</span><span class="sxs-lookup"><span data-stu-id="079a5-627">**On-premises skip**</span></span>
- <span data-ttu-id="079a5-628">**IP zulassen**</span><span class="sxs-lookup"><span data-stu-id="079a5-628">**IP allow**</span></span>
- <span data-ttu-id="079a5-629">**Exchange E-Mail-Transportregel** (Nachrichtenflussregel)</span><span class="sxs-lookup"><span data-stu-id="079a5-629">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="079a5-630">**Zulässige Absender in der Organisation**</span><span class="sxs-lookup"><span data-stu-id="079a5-630">**Organization allowed senders**</span></span>
- <span data-ttu-id="079a5-631">**Zulässige Domänen der Organisation**</span><span class="sxs-lookup"><span data-stu-id="079a5-631">**Organization allowed domains**</span></span>
- <span data-ttu-id="079a5-632">**ZAP nicht aktiviert**</span><span class="sxs-lookup"><span data-stu-id="079a5-632">**ZAP not enabled**</span></span>
- <span data-ttu-id="079a5-633">**Junk-E-Mail-Ordner nicht aktiviert**</span><span class="sxs-lookup"><span data-stu-id="079a5-633">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="079a5-634">**Benutzer Safe Absender**</span><span class="sxs-lookup"><span data-stu-id="079a5-634">**User Safe Sender**</span></span>
- <span data-ttu-id="079a5-635">**Safe Domäne des Benutzers**</span><span class="sxs-lookup"><span data-stu-id="079a5-635">**User Safe Domain**</span></span>

<span data-ttu-id="079a5-636">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-636">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="079a5-637">**Date**</span><span class="sxs-lookup"><span data-stu-id="079a5-637">**Date**</span></span>
- <span data-ttu-id="079a5-638">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="079a5-638">**Subject**</span></span>
- <span data-ttu-id="079a5-639">**Sender**</span><span class="sxs-lookup"><span data-stu-id="079a5-639">**Sender**</span></span>
- <span data-ttu-id="079a5-640">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="079a5-640">**Recipients**</span></span>
- <span data-ttu-id="079a5-641">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="079a5-641">**Detected by**</span></span>
- <span data-ttu-id="079a5-642">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="079a5-642">**Delivery Status**</span></span>
- <span data-ttu-id="079a5-643">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="079a5-643">**Source of Compromise**</span></span>
- <span data-ttu-id="079a5-644">**Tags**</span><span class="sxs-lookup"><span data-stu-id="079a5-644">**Tags**</span></span>

<span data-ttu-id="079a5-645">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="079a5-645">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="079a5-646">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="079a5-646">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="079a5-647">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="079a5-647">**Detection**</span></span>
- <span data-ttu-id="079a5-648">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="079a5-648">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="079a5-649">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="079a5-649">**Direction**</span></span>
- <span data-ttu-id="079a5-650">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="079a5-650">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="079a5-651">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-651">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="079a5-652">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="079a5-652">**Domain**</span></span>
- <span data-ttu-id="079a5-653">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="079a5-653">**Policy type**</span></span>
- <span data-ttu-id="079a5-654">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="079a5-654">**Policy name** (details table only)</span></span>
- <span data-ttu-id="079a5-655">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="079a5-655">**Recipients**</span></span>

<span data-ttu-id="079a5-656">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-656">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="079a5-657"><sup>\*</sup>Nur Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="079a5-657"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="079a5-658">Bericht über häufigste Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="079a5-658">Top malware report</span></span>

<span data-ttu-id="079a5-659">Der **Bericht "Häufigste Schadsoftware"** zeigt die verschiedenen Arten von Schadsoftware, die vom [Schutz vor Schadsoftware in EOP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="079a5-659">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="079a5-660">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="079a5-660">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="079a5-661">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** nach **der top-Schadsoftware,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-661">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="079a5-662">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="079a5-662">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Das am häufigsten verwendete Malware-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/top-malware-report-widget.png)

<span data-ttu-id="079a5-664">Wenn Sie den Mauszeiger über einen Wedge im Kreisdiagramm bewegen, sehen Sie den Namen einer Art von Schadsoftware und wie viele Nachrichten als Schadsoftware erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="079a5-664">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="079a5-665">Auf der Seite **"Häufigste Schadsoftwarebericht"** wird eine größere Version des Kreisdiagramms auf der Berichtsseite angezeigt. Die Detailtabelle unterhalb des Diagramms enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="079a5-665">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="079a5-666">**Häufigste Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="079a5-666">**Top malware**</span></span>
- <span data-ttu-id="079a5-667">**Count**</span><span class="sxs-lookup"><span data-stu-id="079a5-667">**Count**</span></span>

<span data-ttu-id="079a5-668">Wenn Sie auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="079a5-668">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Ansicht des Berichts über häufigste Schadsoftware](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="079a5-670">URL-Bedrohungsschutzbericht</span><span class="sxs-lookup"><span data-stu-id="079a5-670">URL threat protection report</span></span>

<span data-ttu-id="079a5-671">Der **URL-Bedrohungsschutzbericht** ist in Microsoft Defender für Office 365 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="079a5-671">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="079a5-672">Weitere Informationen finden Sie unter [URL Threat Protection Report](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="079a5-672">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="079a5-673">Bericht über vom Benutzer gemeldete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="079a5-673">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="079a5-674">Damit der Bericht über **vom Benutzer gemeldete Nachrichten** ordnungsgemäß funktioniert, muss die **Überwachungsprotokollierung** für Ihre Microsoft 365 Umgebung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="079a5-674">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="079a5-675">Dies geschieht in der Regel von einer Person, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="079a5-675">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="079a5-676">Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren Microsoft 365 Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-676">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="079a5-677">Der Bericht **"Vom Benutzer gemeldete Nachrichten"** enthält Informationen zu E-Mail-Nachrichten, die Benutzer mithilfe des [Add-Ins "Nachricht melden"](enable-the-report-message-add-in.md) oder des [Add-Ins "Phishing melden"](enable-the-report-phish-add-in.md)als Junk, Phishingversuche oder gute E-Mails gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="079a5-677">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="079a5-678">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="079a5-678">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="079a5-679">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** **nach von Benutzern gemeldeten Nachrichten,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-679">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="079a5-680">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="079a5-680">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="079a5-681">Wenn Sie im Microsoft 365 Defender Portal zu [Administratorübermittlungen](admin-submission.md)wechseln möchten, klicken Sie auf **"Zu Übermittlungen wechseln".**</span><span class="sxs-lookup"><span data-stu-id="079a5-681">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Vom Benutzer gemeldete Nachrichten-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/user-reported-messages-widget.png)

<span data-ttu-id="079a5-683">Auf der Seite **"Vom Benutzer gemeldete Nachrichten"** können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="079a5-683">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="079a5-684">**Gemeldetes Datum**: **Startzeit** und **Endzeit**</span><span class="sxs-lookup"><span data-stu-id="079a5-684">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="079a5-685">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="079a5-685">**Reported by**</span></span>
- <span data-ttu-id="079a5-686">**E-Mail-Betreff**</span><span class="sxs-lookup"><span data-stu-id="079a5-686">**Email subject**</span></span>
- <span data-ttu-id="079a5-687">**Gemeldete ID der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="079a5-687">**Message reported ID**</span></span>
- <span data-ttu-id="079a5-688">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="079a5-688">**Network Message ID**</span></span>
- <span data-ttu-id="079a5-689">**Sender**</span><span class="sxs-lookup"><span data-stu-id="079a5-689">**Sender**</span></span>
- <span data-ttu-id="079a5-690">**Gemeldeter Grund**</span><span class="sxs-lookup"><span data-stu-id="079a5-690">**Reported reason**</span></span>
  - <span data-ttu-id="079a5-691">**Kein Junk**</span><span class="sxs-lookup"><span data-stu-id="079a5-691">**Not junk**</span></span>
  - <span data-ttu-id="079a5-692">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="079a5-692">**Phish**</span></span>
  - <span data-ttu-id="079a5-693">**Spam**</span><span class="sxs-lookup"><span data-stu-id="079a5-693">**Spam**</span></span>
- <span data-ttu-id="079a5-694">**Phishing-Simulation:** **Ja** oder **Nein**</span><span class="sxs-lookup"><span data-stu-id="079a5-694">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="079a5-695">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="079a5-695">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="079a5-696">Klicken Sie zum Gruppieren der Einträge auf **"Gruppieren",** und wählen Sie einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="079a5-696">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="079a5-697">**Keine**</span><span class="sxs-lookup"><span data-stu-id="079a5-697">**None**</span></span>
- <span data-ttu-id="079a5-698">**Grund**</span><span class="sxs-lookup"><span data-stu-id="079a5-698">**Reason**</span></span>
- <span data-ttu-id="079a5-699">**Sender**</span><span class="sxs-lookup"><span data-stu-id="079a5-699">**Sender**</span></span>
- <span data-ttu-id="079a5-700">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="079a5-700">**Reported by**</span></span>
- <span data-ttu-id="079a5-701">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="079a5-701">**Rescan result**</span></span>
- <span data-ttu-id="079a5-702">**Phishing-Simulation**</span><span class="sxs-lookup"><span data-stu-id="079a5-702">**Phish simulation**</span></span>

![Bericht über vom Benutzer gemeldete Nachrichten](../../media/user-reported-messages-report.png)

<span data-ttu-id="079a5-704">In der Detailtabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="079a5-704">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="079a5-705">**E-Mail-Betreff**</span><span class="sxs-lookup"><span data-stu-id="079a5-705">**Email subject**</span></span>
- <span data-ttu-id="079a5-706">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="079a5-706">**Reported by**</span></span>
- <span data-ttu-id="079a5-707">**Gemeldetes Datum**</span><span class="sxs-lookup"><span data-stu-id="079a5-707">**Date reported**</span></span>
- <span data-ttu-id="079a5-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="079a5-708">**Sender**</span></span>
- <span data-ttu-id="079a5-709">**Gemeldeter Grund**</span><span class="sxs-lookup"><span data-stu-id="079a5-709">**Reported reason**</span></span>
- <span data-ttu-id="079a5-710">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="079a5-710">**Rescan result**</span></span>
- <span data-ttu-id="079a5-711">**Tags**</span><span class="sxs-lookup"><span data-stu-id="079a5-711">**Tags**</span></span>

<span data-ttu-id="079a5-712">Um eine Nachricht zur Analyse an Microsoft zu übermitteln, wählen Sie den Nachrichteneintrag aus der Tabelle aus, klicken Sie auf **"Zur Analyse an Microsoft übermitteln",** und wählen Sie dann einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="079a5-712">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="079a5-713">**Bericht sauber**</span><span class="sxs-lookup"><span data-stu-id="079a5-713">**Report clean**</span></span>
- <span data-ttu-id="079a5-714">**Melden von Phishing**</span><span class="sxs-lookup"><span data-stu-id="079a5-714">**Report phishing**</span></span>
- <span data-ttu-id="079a5-715">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="079a5-715">**Report malware**</span></span>
- <span data-ttu-id="079a5-716">**Spam melden**'</span><span class="sxs-lookup"><span data-stu-id="079a5-716">**Report spam**'</span></span>
- <span data-ttu-id="079a5-717">**Untersuchung auslösen** (Defender für Office 365)</span><span class="sxs-lookup"><span data-stu-id="079a5-717">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="079a5-718">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="079a5-718">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="079a5-719">Um die in diesem Artikel beschriebenen Berichte anzuzeigen und zu verwenden, müssen Sie Mitglied einer der folgenden Rollengruppen im Microsoft 365 Defender Portal sein:</span><span class="sxs-lookup"><span data-stu-id="079a5-719">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="079a5-720">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="079a5-720">**Organization Management**</span></span>
- <span data-ttu-id="079a5-721">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="079a5-721">**Security Administrator**</span></span>
- <span data-ttu-id="079a5-722">**Sicherheitsleseberechtigter**</span><span class="sxs-lookup"><span data-stu-id="079a5-722">**Security Reader**</span></span>
- <span data-ttu-id="079a5-723">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="079a5-723">**Global Reader**</span></span>

<span data-ttu-id="079a5-724">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-724">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="079a5-725">**Hinweis:** Das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center bietet Benutzern die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="079a5-725">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="079a5-726">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="079a5-726">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="079a5-727">Was geschieht, wenn in den Berichten keine Daten angezeigt werden?</span><span class="sxs-lookup"><span data-stu-id="079a5-727">What if the reports aren't showing data?</span></span>

<span data-ttu-id="079a5-728">Wenn in Ihren Berichten keine Daten angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="079a5-728">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="079a5-729">Weitere Informationen finden Sie unter ["Schutz vor Bedrohungen".](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="079a5-729">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="079a5-730">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="079a5-730">Related topics</span></span>

[<span data-ttu-id="079a5-731">Antispam- und Antischadsoftwareschutz in EOP</span><span class="sxs-lookup"><span data-stu-id="079a5-731">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="079a5-732">Intelligente Berichte und Einblicke im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="079a5-732">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="079a5-733">Anzeigen von Nachrichtenflussberichten im Microsoft 365 Defender Portal</span><span class="sxs-lookup"><span data-stu-id="079a5-733">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="079a5-734">Anzeigen von Berichten für Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="079a5-734">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
