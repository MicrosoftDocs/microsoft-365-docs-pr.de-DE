---
title: Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender-Portal
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
description: Erfahren Sie, wie Sie E-Mail-Sicherheitsberichte für Ihre Organisation finden und verwenden. E-Mail-Sicherheitsberichte sind im Microsoft 365 Defender-Portal verfügbar.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d46aec8601d19234eed8682955ffef27b7e9b467
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985205"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="579b2-104">Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="579b2-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="579b2-105">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="579b2-105">**Applies to**</span></span>
- [<span data-ttu-id="579b2-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="579b2-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="579b2-107">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="579b2-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="579b2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="579b2-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="579b2-109">Im Microsoft 365 Defender-Portal finden Sie eine Vielzahl von Berichten, <https://security.microsoft.com> mit denen Sie sehen können, wie E-Mail-Sicherheitsfeatures wie Antispam, Antischadsoftware und Verschlüsselungsfunktionen in Microsoft 365 Ihre Organisation schützen.</span><span class="sxs-lookup"><span data-stu-id="579b2-109">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="579b2-110">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im Microsoft 365 Defender-Portal anzeigen, indem Sie zu  \> **E-Mail-Berichte &** \> **ZusammenarbeitS-E-Mail & Zusammenarbeitsberichte wechseln.**</span><span class="sxs-lookup"><span data-stu-id="579b2-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="579b2-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="579b2-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Seite "E-Mail & Berichte zur Zusammenarbeit" im Microsoft 365 Defender-Portal](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="579b2-113">Einige der Berichte auf der Seite **"E-Mail & Zusammenarbeitsberichte"** erfordern Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="579b2-113">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="579b2-114">Informationen zu diesen Berichten finden Sie unter Anzeigen von [Defender für Office 365-Berichten im Microsoft 365 Defender-Portal.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-114">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="579b2-115">Berichte, die sich auf den Nachrichtenfluss beziehen, befinden sich jetzt im Exchange Admin Center (EAC).</span><span class="sxs-lookup"><span data-stu-id="579b2-115">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="579b2-116">Weitere Informationen zu diesen Berichten finden Sie unter [Nachrichtenflussberichte im neuen Exchange Admin Center.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="579b2-116">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="579b2-117">Bericht "Kompromittierte Benutzer"</span><span class="sxs-lookup"><span data-stu-id="579b2-117">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="579b2-118">Dieser Bericht ist in Microsoft 365-Organisationen mit Exchange Online-Postfächern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="579b2-118">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="579b2-119">Es ist nicht in eigenständigen Exchange Online Protection (EOP)-Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="579b2-119">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="579b2-120">Der Bericht **"Kompromittierte Benutzer"** zeigt die Anzahl der Benutzerkonten an, die innerhalb der letzten 7 Tage als **verdächtig** oder **eingeschränkt** markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="579b2-120">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="579b2-121">Konten in einem dieser Zustände sind problematisch oder sogar kompromittiert.</span><span class="sxs-lookup"><span data-stu-id="579b2-121">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="579b2-122">Bei häufiger Verwendung können Sie den Bericht verwenden, um Spitzen und sogar Trends in verdächtigen oder eingeschränkten Konten zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="579b2-122">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="579b2-123">Weitere Informationen zu kompromittierten Benutzern finden Sie unter [Antworten auf ein kompromittiertes E-Mail-Konto.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-123">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget "Kompromittierte Benutzer" auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/compromised-users-report-widget.png)

<span data-ttu-id="579b2-125">In der Aggregatansicht werden Daten für die letzten 90 Tage und in der Detailansicht Daten für die letzten 30 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="579b2-125">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="579b2-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="579b2-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="579b2-127">Klicken Sie auf **kompromittierte Benutzer** auf **Details anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="579b2-127">On **Compromised users**, click **View details**.</span></span> <span data-ttu-id="579b2-128">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="579b2-128">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="579b2-129">Nachdem Sie auf **"Details anzeigen"** geklickt haben, können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="579b2-129">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="579b2-130">**Datum (UTC):** **Startdatum** und **Enddatum.**</span><span class="sxs-lookup"><span data-stu-id="579b2-130">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="579b2-131">**Aktivität:**</span><span class="sxs-lookup"><span data-stu-id="579b2-131">**Activity**:</span></span>
  - <span data-ttu-id="579b2-132">**Verdächtig:** Das Benutzerkonto hat verdächtige E-Mails gesendet und besteht das Risiko, dass das Senden von E-Mails eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="579b2-132">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="579b2-133">**Eingeschränkt:** Das Benutzerkonto wurde aufgrund von hochgradig verdächtigen Mustern am Senden von E-Mails gehindert.</span><span class="sxs-lookup"><span data-stu-id="579b2-133">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="579b2-134">Wenn Sie die Filterung abgeschlossen haben, klicken Sie auf **"Übernehmen"** oder **"Abbrechen".**</span><span class="sxs-lookup"><span data-stu-id="579b2-134">When you're finished filtering, click **Apply** or **Cancel**.</span></span>

![Berichtsansicht im Bericht "Kompromittierte Benutzer"](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="579b2-136">In der Tabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="579b2-136">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="579b2-137">**Erstellungszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="579b2-137">**Creation time**</span></span>
- <span data-ttu-id="579b2-138">**Benutzer-ID**</span><span class="sxs-lookup"><span data-stu-id="579b2-138">**User ID**</span></span>
- <span data-ttu-id="579b2-139">**Action**</span><span class="sxs-lookup"><span data-stu-id="579b2-139">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="579b2-140">Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="579b2-140">Exchange transport rule report</span></span>

<span data-ttu-id="579b2-141">Der **Exchange-Transportregelbericht** zeigt die Auswirkungen von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) auf ein- und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="579b2-141">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="579b2-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="579b2-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="579b2-143">Klicken Sie in **der Exchange-Transportregel** auf **Details anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="579b2-143">On **Exchange transport rule**, click **View details**.</span></span> <span data-ttu-id="579b2-144">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="579b2-144">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/transport-rule-report-widget.png)

<span data-ttu-id="579b2-146">Nachdem Sie auf **"Details anzeigen"** geklickt haben, sind die folgenden Diagramme und Daten verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-146">After you click **View details**, the following charts and data are available:</span></span>

- <span data-ttu-id="579b2-147">**Anzeigen von Daten nach Exchange-Transportregeln** \> **Diagrammstrukturplan nach Richtung:** Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von Nachrichtenflussregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="579b2-147">**View data by Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>

- <span data-ttu-id="579b2-148">**Anzeigen von Daten nach Exchange-Transportregeln** \> **Diagrammstrukturplan nach Schweregrad:** Dieses Diagramm zeigt die Anzahl der Meldungen mit **hohem,** **mittlerem und** **mittlerem Schweregrad.**</span><span class="sxs-lookup"><span data-stu-id="579b2-148">**View data by Exchange transport rules** \> **Chart breakdown by Severity**: This chart shows the number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="579b2-149">Sie legen den Schweregrad als Aktion in der Regel fest (**Überwachen Sie diese Regel mit Schweregrad** oder _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="579b2-149">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="579b2-150">Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="579b2-150">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="579b2-151">**Anzeigen von Daten nach DLP-Exchange-Transportregeln** \> **Diagrammstrukturplan nach Richtung:** Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von DLP-Nachrichtenflussregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="579b2-151">**View data by DLP Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

- <span data-ttu-id="579b2-152">**Anzeigen von Daten nach DLP-Exchange-Transportregeln** \> **Diagrammaufschlüsselung nach Schweregrad:** Diese Ansicht zeigt die Anzahl der Nachrichten mit **hohem Schweregrad,** **mittlerem Schweregrad** und **niedrigem Schweregrad,** die von DLP-Nachrichtenflussregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="579b2-152">**View data by DLP Exchange transport rules** \> **Chart breakdown by Severity**: This view shows the number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="579b2-153">Für die **Auswahl von Daten nach Exchange-Transportregeln werden** die folgenden Informationen in der Detailtabelle unterhalb des Diagramms angezeigt:</span><span class="sxs-lookup"><span data-stu-id="579b2-153">For **View data by Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="579b2-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="579b2-154">**Date**</span></span>
- <span data-ttu-id="579b2-155">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="579b2-155">**Transport rule**</span></span>
- <span data-ttu-id="579b2-156">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="579b2-156">**Subject**</span></span>
- <span data-ttu-id="579b2-157">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="579b2-157">**Sender address**</span></span>
- <span data-ttu-id="579b2-158">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="579b2-158">**Recipient address**</span></span>
- <span data-ttu-id="579b2-159">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="579b2-159">**Severity**</span></span>
- <span data-ttu-id="579b2-160">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="579b2-160">**Direction**</span></span>

<span data-ttu-id="579b2-161">Für die **Auswahl von Daten nach DLP Exchange-Transportregeln** werden die folgenden Informationen in der Detailtabelle unterhalb des Diagramms angezeigt:</span><span class="sxs-lookup"><span data-stu-id="579b2-161">For **View data by DLP Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="579b2-162">**Date**</span><span class="sxs-lookup"><span data-stu-id="579b2-162">**Date**</span></span>
- <span data-ttu-id="579b2-163">**DLP-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="579b2-163">**DLP policy**</span></span>
- <span data-ttu-id="579b2-164">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="579b2-164">**Transport rule**</span></span>
- <span data-ttu-id="579b2-165">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="579b2-165">**Subject**</span></span>
- <span data-ttu-id="579b2-166">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="579b2-166">**Sender address**</span></span>
- <span data-ttu-id="579b2-167">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="579b2-167">**Recipient address**</span></span>
- <span data-ttu-id="579b2-168">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="579b2-168">**Severity**</span></span>
- <span data-ttu-id="579b2-169">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="579b2-169">**Direction**</span></span>

<span data-ttu-id="579b2-170">Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="579b2-170">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="579b2-171">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="579b2-171">**Start date** and **End date**</span></span>
- <span data-ttu-id="579b2-172">**Richtung:** **Ausgehend** und **Eingehend**</span><span class="sxs-lookup"><span data-stu-id="579b2-172">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="579b2-173">**Schweregrad:** **Hoher,** **mittlerer und** niedriger **Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="579b2-173">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

![Berichtsansicht im Exchange-Transportregelbericht](../../media/transport-rule-report-report-view.png)

## <a name="mailflow-status-report"></a><span data-ttu-id="579b2-175">E-Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="579b2-175">Mailflow status report</span></span>

<span data-ttu-id="579b2-176">Der **E-Mailflow-Statusbericht** ist ein intelligenter Bericht, der Informationen zu eingehenden und ausgehenden E-Mails, Spamerkennungen, Schadsoftware, als "gut" identifizierten E-Mails und Informationen zu E-Mails anzeigt, die am Edge zugelassen oder blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="579b2-176">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="579b2-177">Dies ist der einzige Bericht, der Edgeschutzinformationen enthält, und zeigt an, wie viele E-Mails blockiert werden, bevor sie zur Auswertung durch Exchange Online Protection (EOP) in den Dienst zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="579b2-177">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="579b2-178">Es ist wichtig zu verstehen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="579b2-178">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="579b2-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="579b2-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="579b2-180">Klicken Sie in der **Mailflow-Statuszusammenfassung** auf **Details anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="579b2-180">On **Mailflow status summary**, click **View details**.</span></span> <span data-ttu-id="579b2-181">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="579b2-181">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Nachrichtenflussstatus-Zusammenfassungs-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="579b2-183">Typansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="579b2-183">Type view for the Mailflow status report</span></span>

<span data-ttu-id="579b2-184">Wenn Sie den Bericht  öffnen, ist standardmäßig die Registerkarte Typ ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="579b2-184">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="579b2-185">Standardmäßig enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="579b2-185">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="579b2-186">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="579b2-186">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="579b2-187">**E-Mail-Richtung:**</span><span class="sxs-lookup"><span data-stu-id="579b2-187">**Mail direction**:</span></span>
  - <span data-ttu-id="579b2-188">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="579b2-188">**Inbound**</span></span>
  - <span data-ttu-id="579b2-189">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="579b2-189">**Outbound**</span></span>
  - <span data-ttu-id="579b2-190">**Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="579b2-190">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="579b2-191">absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von **ein-** und **ausgehend** gezählt)</span><span class="sxs-lookup"><span data-stu-id="579b2-191">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="579b2-192">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="579b2-192">**Type**:</span></span>
  - <span data-ttu-id="579b2-193">**Gute E-Mails**</span><span class="sxs-lookup"><span data-stu-id="579b2-193">**Good mail**</span></span>
  - <span data-ttu-id="579b2-194">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="579b2-194">**Malware**</span></span>
  - <span data-ttu-id="579b2-195">**Spam**</span><span class="sxs-lookup"><span data-stu-id="579b2-195">**Spam**</span></span>
  - <span data-ttu-id="579b2-196">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="579b2-196">**Edge protection**</span></span>
  - <span data-ttu-id="579b2-197">**Regelnachrichten**</span><span class="sxs-lookup"><span data-stu-id="579b2-197">**Rule messages**</span></span>
  - <span data-ttu-id="579b2-198">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="579b2-198">**Phishing email**</span></span>
- <span data-ttu-id="579b2-199">**Domäne:** **Alle**</span><span class="sxs-lookup"><span data-stu-id="579b2-199">**Domain**: **All**</span></span>

<span data-ttu-id="579b2-200">Das Diagramm ist nach den **Type-Werten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="579b2-200">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="579b2-201">Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="579b2-201">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="579b2-202">Die Datentabelle enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="579b2-202">The data table contains the following information:</span></span>

- <span data-ttu-id="579b2-203">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="579b2-203">**Direction**</span></span>
- <span data-ttu-id="579b2-204">**Typ**</span><span class="sxs-lookup"><span data-stu-id="579b2-204">**Type**</span></span>
- <span data-ttu-id="579b2-205">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="579b2-205">**24 hours**</span></span>
- <span data-ttu-id="579b2-206">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="579b2-206">**3 days**</span></span>
- <span data-ttu-id="579b2-207">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="579b2-207">**7 days**</span></span>
- <span data-ttu-id="579b2-208">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="579b2-208">**15 days**</span></span>
- <span data-ttu-id="579b2-209">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="579b2-209">**30 days**</span></span>

<span data-ttu-id="579b2-210">Wenn Sie auf **"Kategorie auswählen"** klicken, um weitere Details zu erhalten, können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="579b2-210">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="579b2-211">**Phishing-E-Mail:** Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="579b2-211">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="579b2-212">**Schadsoftware in E-Mails:** Diese Auswahl führt Sie zum [Bedrohungsschutzstatusbericht.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="579b2-212">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="579b2-213">**Spamerkennungen:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="579b2-213">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="579b2-214">**Edge blockierter Spam:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="579b2-214">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="579b2-215">Exportieren aus der Typansicht</span><span class="sxs-lookup"><span data-stu-id="579b2-215">Export from Type view</span></span>

<span data-ttu-id="579b2-216">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="579b2-216">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="579b2-217">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="579b2-217">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="579b2-218">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="579b2-218">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="579b2-219">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="579b2-219">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Typansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="579b2-221">Richtungsansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="579b2-221">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="579b2-222">Wenn Sie auf die Registerkarte **"Richtung"** klicken, werden die gleichen Standardfilter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="579b2-222">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="579b2-223">Das Diagramm ist nach **Richtungswerten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="579b2-223">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="579b2-224">Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.</span><span class="sxs-lookup"><span data-stu-id="579b2-224">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="579b2-225">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="579b2-225">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="579b2-226">Die Datentabelle enthält dieselben Informationen aus der **Typansicht.**</span><span class="sxs-lookup"><span data-stu-id="579b2-226">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="579b2-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span><span class="sxs-lookup"><span data-stu-id="579b2-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="579b2-228">Exportieren aus der Richtungsansicht</span><span class="sxs-lookup"><span data-stu-id="579b2-228">Export from Direction view</span></span>

<span data-ttu-id="579b2-229">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="579b2-229">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="579b2-230">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="579b2-230">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="579b2-231">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="579b2-231">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="579b2-232">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="579b2-232">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Richtungsansicht im E-Mailflow-Statusbericht](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="579b2-234">Trichteransicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="579b2-234">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="579b2-235">Die **Trichteransicht** zeigt Ihnen, wie die E-Mail-Bedrohungsschutzfeatures von Microsoft eingehende und ausgehende E-Mails in Ihrer Organisation filtern.</span><span class="sxs-lookup"><span data-stu-id="579b2-235">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="579b2-236">Es enthält Details zur Gesamtzahl der E-Mails und dazu, wie sich die konfigurierten Bedrohungsschutzfeatures, einschließlich Edgeschutz, Antischadsoftware, Antiphishing, Antispam und Antispoofing, auf diese Anzahl auswirken.</span><span class="sxs-lookup"><span data-stu-id="579b2-236">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="579b2-237">Wenn Sie auf die Registerkarte **"Trichter"** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="579b2-237">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="579b2-238">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="579b2-238">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="579b2-239">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="579b2-239">**Direction**:</span></span>

  - <span data-ttu-id="579b2-240">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="579b2-240">**Inbound**</span></span>
  - <span data-ttu-id="579b2-241">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="579b2-241">**Outbound**</span></span>
  - <span data-ttu-id="579b2-242">**Organisationsintern:** Diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden; d. h. Absender abc@domain.com sendet an Empfänger xyz@domain.com (separat von Ein- und Ausgehend gezählt).</span><span class="sxs-lookup"><span data-stu-id="579b2-242">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="579b2-243">Die Aggregatansicht und die Datentabellenansicht ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="579b2-243">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="579b2-244">Wenn Sie auf **"Filtern"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="579b2-244">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="579b2-245">Dieses Diagramm zeigt die E-Mail-Anzahl nach:</span><span class="sxs-lookup"><span data-stu-id="579b2-245">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="579b2-246">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="579b2-246">**Total email**</span></span>
- <span data-ttu-id="579b2-247">**E-Mail nach Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="579b2-247">**Email after edge protection**</span></span>
- <span data-ttu-id="579b2-248">**E-Mail nach Transportregel** (Nachrichtenflussregel)</span><span class="sxs-lookup"><span data-stu-id="579b2-248">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="579b2-249">**E-Mail nach Antischadsoftware, Dateireputation, Dateitypblockierung**</span><span class="sxs-lookup"><span data-stu-id="579b2-249">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="579b2-250">**E-Mail nach Antiphishing, URL-Reputation, Markenidentitätswechsel, Antispoofing**</span><span class="sxs-lookup"><span data-stu-id="579b2-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="579b2-251">**E-Mails nach Antispam, Massenfilterung von E-Mails**</span><span class="sxs-lookup"><span data-stu-id="579b2-251">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="579b2-252">**E-Mail nach Benutzer- und Domänenidentitätswechsel**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="579b2-252">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="579b2-253">**E-Mail nach Datei- und URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="579b2-253">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="579b2-254">**E-Mails, die nach der Zustellung als gutartig erkannt wurden (URL-Click-Time-Schutz)**</span><span class="sxs-lookup"><span data-stu-id="579b2-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="579b2-255"><sup>\*</sup>Nur Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="579b2-255"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="579b2-256">Um die von EOP oder Defender gefilterte E-Mail für Office 365 separat anzuzeigen, klicken Sie auf den Wert in der Diagrammlegende.</span><span class="sxs-lookup"><span data-stu-id="579b2-256">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="579b2-257">Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="579b2-257">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="579b2-258">**Date**</span><span class="sxs-lookup"><span data-stu-id="579b2-258">**Date**</span></span>
- <span data-ttu-id="579b2-259">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="579b2-259">**Total email**</span></span>
- <span data-ttu-id="579b2-260">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="579b2-260">**Edge protection**</span></span>
- <span data-ttu-id="579b2-261">**Antischadsoftware, Dateireputation, Dateitypblock:**</span><span class="sxs-lookup"><span data-stu-id="579b2-261">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="579b2-262">**Dateizuruf:** Nachrichten, die aufgrund der Identifizierung einer angefügten Datei von anderen Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="579b2-262">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="579b2-263">**Dateitypblock:** Nachrichten, die aufgrund des typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="579b2-263">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="579b2-264">**Antiphishing, URL-Zuverlässigkeit, Markenidentitätswechsel, Antispoofing:**</span><span class="sxs-lookup"><span data-stu-id="579b2-264">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="579b2-265">**URL-Zuverlässigkeit:** Nachrichten, die aufgrund der Identifizierung der URL von anderen Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="579b2-265">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="579b2-266">**Markenidentitätswechsel:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die von bekannten Absendern als Absender imitiert wurde.</span><span class="sxs-lookup"><span data-stu-id="579b2-266">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="579b2-267">**Antispoofing:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die versucht, eine Domäne zu spoofen, zu der der Empfänger gehört, oder einer Domäne, die der Absender der Nachricht nicht besitzt.</span><span class="sxs-lookup"><span data-stu-id="579b2-267">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="579b2-268">**Antispam, Massen-E-Mail-Filterung:**</span><span class="sxs-lookup"><span data-stu-id="579b2-268">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="579b2-269">**Massen-E-Mail-Filterung:** Nachrichten, die basierend auf dem BCL-Schwellenwert (Bulk Complain Level) in einer Antispamrichtlinie gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="579b2-269">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="579b2-270">**Benutzer- und Domänenidentitätswechsel (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="579b2-270">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="579b2-271">**Benutzeridentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, einen Benutzer (Nachrichtensender) zu imitieren, der in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="579b2-271">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="579b2-272">**Domänenidentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, eine Domäne zu imitieren, die in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="579b2-272">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="579b2-273">**Datei- und URL-Detonation (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="579b2-273">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="579b2-274">**Dateidetonation:** Nachrichten, die nach einer Safe Anlagenrichtlinie gefiltert sind.</span><span class="sxs-lookup"><span data-stu-id="579b2-274">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="579b2-275">**URL-Detonation:** Nachricht, gefiltert nach einer Safe-Verknüpfungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="579b2-275">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="579b2-276">**Schutz nach der Zustellung und ZAP (ATP) oder ZAP (EOP):** Automatische Nullstunde-Bereinigung (ZAP) für Schadsoftware, Spam und Phishing.</span><span class="sxs-lookup"><span data-stu-id="579b2-276">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="579b2-277">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="579b2-277">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="579b2-278">Exportieren aus der Trichteransicht</span><span class="sxs-lookup"><span data-stu-id="579b2-278">Export from Funnel view</span></span>

<span data-ttu-id="579b2-279">Nachdem Sie unter **"Optionen"** auf **"Exportieren"** geklickt haben, können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="579b2-279">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="579b2-280">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="579b2-280">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="579b2-281">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="579b2-281">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="579b2-282">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .**</span><span class="sxs-lookup"><span data-stu-id="579b2-282">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="579b2-283">Daten für die aktuellen Filter werden in eine .csv Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="579b2-283">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="579b2-284">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="579b2-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="579b2-285">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="579b2-285">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Trichteransicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="579b2-287">Tech-Ansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="579b2-287">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="579b2-288">Die **Tech-Ansicht** ähnelt der **Trichteransicht** und bietet detailliertere Details für die konfigurierten Funktionen zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="579b2-288">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="579b2-289">Im Diagramm können Sie sehen, wie Nachrichten in den verschiedenen Phasen des Bedrohungsschutzes kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="579b2-289">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="579b2-290">Wenn Sie standardmäßig auf die Registerkarte **"Tech-Ansicht"** klicken, enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="579b2-290">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="579b2-291">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="579b2-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="579b2-292">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="579b2-292">**Direction**:</span></span>

  - <span data-ttu-id="579b2-293">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="579b2-293">**Inbound**</span></span>
  - <span data-ttu-id="579b2-294">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="579b2-294">**Outbound**</span></span>
  - <span data-ttu-id="579b2-295">**Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="579b2-295">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="579b2-296">absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von eingehenden und ausgehenden Zählungen)</span><span class="sxs-lookup"><span data-stu-id="579b2-296">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="579b2-297">Die Aggregatansicht und die Datentabellenansicht ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="579b2-297">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="579b2-298">Wenn Sie auf **"Filtern"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="579b2-298">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="579b2-299">Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:</span><span class="sxs-lookup"><span data-stu-id="579b2-299">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="579b2-300">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="579b2-300">**Total email**</span></span>
- <span data-ttu-id="579b2-301">**Edge zulassen** und **Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="579b2-301">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="579b2-302">**Transportregel zulassen** und **Transportregel gefiltert** (Nachrichtenflussregeln)</span><span class="sxs-lookup"><span data-stu-id="579b2-302">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="579b2-303">**Keine Schadsoftware,** **Safe Erkennung von Anlagen** und Erkennung von <sup>\*</sup> **Antischadsoftwaremodulen**</span><span class="sxs-lookup"><span data-stu-id="579b2-303">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="579b2-304">**Keine Phishing-,** **DMARC-Fehler,** **Identitätswechselerkennung,** <sup>\*</sup> **Spooferkennung** und **Phishing-Erkennung**</span><span class="sxs-lookup"><span data-stu-id="579b2-304">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="579b2-305">**Keine Erkennung mit URL-Detonation** und **URL-Detonationserkennung**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="579b2-305">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="579b2-306">**Keine Spam-** und  **Spamnachrichten**</span><span class="sxs-lookup"><span data-stu-id="579b2-306">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="579b2-307">**Nicht böswillige E-Mails,** **Safe-Links-Erkennung** <sup>\*</sup> und **ZAP**</span><span class="sxs-lookup"><span data-stu-id="579b2-307">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="579b2-308"><sup>\*</sup>Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="579b2-308"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="579b2-309">Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, können Sie die Anzahl der Nachrichten in dieser Kategorie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="579b2-309">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="579b2-310">Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="579b2-310">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="579b2-311">**Date**</span><span class="sxs-lookup"><span data-stu-id="579b2-311">**Date**</span></span>
- <span data-ttu-id="579b2-312">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="579b2-312">**Total email**</span></span>
- <span data-ttu-id="579b2-313">**Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="579b2-313">**Edge filtered**</span></span>
- <span data-ttu-id="579b2-314">**Regelnachrichten:** Nachrichten, die aufgrund von Nachrichtenflussregeln gefiltert wurden (auch als Transportregeln bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="579b2-314">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="579b2-315">**Antischadsoftwaremodul**, **Safe** <sup>\*</sup> Anlagen:</span><span class="sxs-lookup"><span data-stu-id="579b2-315">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="579b2-316">**DMARC, Identitätswechsel,** <sup>\*</sup> **Spoofing**, **Phishing gefiltert:**</span><span class="sxs-lookup"><span data-stu-id="579b2-316">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="579b2-317">**DMARC:** Nachrichten, die aufgrund eines Fehlers bei der DMARC-Authentifizierungsprüfung gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="579b2-317">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="579b2-318">**ERKENNUNG DER URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="579b2-318">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="579b2-319">**Antispam gefiltert**</span><span class="sxs-lookup"><span data-stu-id="579b2-319">**Anti-spam filtered**</span></span>
- <span data-ttu-id="579b2-320">**ZAP entfernt**</span><span class="sxs-lookup"><span data-stu-id="579b2-320">**ZAP removed**</span></span>
- <span data-ttu-id="579b2-321">**Erkennung durch Safe Links**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="579b2-321">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="579b2-322"><sup>\*</sup>Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="579b2-322"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="579b2-323">Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="579b2-323">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="579b2-324">Exportieren aus der Tech-Ansicht</span><span class="sxs-lookup"><span data-stu-id="579b2-324">Export from Tech view</span></span>

<span data-ttu-id="579b2-325">Wenn Sie auf **"Exportieren"** klicken, können Sie unter **"Optionen"** einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="579b2-325">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="579b2-326">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="579b2-326">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="579b2-327">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="579b2-327">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="579b2-328">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .**</span><span class="sxs-lookup"><span data-stu-id="579b2-328">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="579b2-329">Daten für die aktuellen Filter werden in eine .csv Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="579b2-329">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="579b2-330">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="579b2-330">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="579b2-331">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="579b2-331">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Tech-Ansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="579b2-333">Bericht über Schadsoftwareerkennungen</span><span class="sxs-lookup"><span data-stu-id="579b2-333">Malware detections report</span></span>

<span data-ttu-id="579b2-334">Der Bericht über **Schadsoftwareerkennungen** enthält Informationen zu Schadsoftwareerkennungen in eingehenden und ausgehenden E-Mail-Nachrichten (von Exchange Online Protection oder EOP erkannte Schadsoftware).</span><span class="sxs-lookup"><span data-stu-id="579b2-334">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="579b2-335">Weitere Informationen zum Schutz vor Schadsoftware in EOP finden Sie unter [Antischadsoftwareschutz in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-335">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="579b2-336">Der Aggregatansichtsfilter lässt 90 Tage zu, während der Detailtabellenfilter nur 10 Tage zulässt.</span><span class="sxs-lookup"><span data-stu-id="579b2-336">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="579b2-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="579b2-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="579b2-338">On **Malware detected in email**, click View **details**.</span><span class="sxs-lookup"><span data-stu-id="579b2-338">On **Malware detected in email**, click **View details**.</span></span> <span data-ttu-id="579b2-339">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="579b2-339">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Schadsoftwareerkennungen im E-Mail-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/malware-detections-widget.png)

<span data-ttu-id="579b2-341">Nachdem Sie auf **"Details anzeigen"** geklickt haben, können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="579b2-341">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting:</span></span>

- <span data-ttu-id="579b2-342">**Datum:** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="579b2-342">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="579b2-343">**Richtung:** **Ein-** und **Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="579b2-343">**Direction**: **Inbound** and **Outbound**</span></span>

![Berichtsansicht im Bericht "Schadsoftwareerkennung in E-Mail"](../../media/malware-detections-report-view.png)

<span data-ttu-id="579b2-345">In der Detailtabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="579b2-345">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="579b2-346">**Date**</span><span class="sxs-lookup"><span data-stu-id="579b2-346">**Date**</span></span>
- <span data-ttu-id="579b2-347">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="579b2-347">**Sender address**</span></span>
- <span data-ttu-id="579b2-348">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="579b2-348">**Recipient address**</span></span>
- <span data-ttu-id="579b2-349">**Nachrichten-ID:** Verfügbar im **Nachrichten-ID-Kopfzeilenfeld** im Nachrichtenkopf und sollte eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="579b2-349">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="579b2-350">Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (beachten Sie die spitzen Klammern).</span><span class="sxs-lookup"><span data-stu-id="579b2-350">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="579b2-351">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="579b2-351">**Subject**</span></span>
- <span data-ttu-id="579b2-352">**Filename**</span><span class="sxs-lookup"><span data-stu-id="579b2-352">**Filename**</span></span>
- <span data-ttu-id="579b2-353">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="579b2-353">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="579b2-354">E-Mail-Latenzbericht</span><span class="sxs-lookup"><span data-stu-id="579b2-354">Mail latency report</span></span>

<span data-ttu-id="579b2-355">Der **E-Mail-Latenzbericht** in Defender für Office 365 enthält Informationen zur E-Mail-Zustellungs- und Detonationslatenz in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="579b2-355">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="579b2-356">Weitere Informationen finden Sie im [E-Mail-Latenzbericht.](view-reports-for-mdo.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="579b2-356">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="579b2-357">Spamerkennungsbericht</span><span class="sxs-lookup"><span data-stu-id="579b2-357">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="579b2-358">Der **Spamerkennungsbericht** wird am 30. Juni 2021 gelöscht.</span><span class="sxs-lookup"><span data-stu-id="579b2-358">The **Spam detections report** will go away on June 30, 2021.</span></span> <span data-ttu-id="579b2-359">Die gleichen Informationen sind im [Bedrohungsschutzstatusbericht](#threat-protection-status-report)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="579b2-359">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="579b2-360">Bericht über Spooferkennungen</span><span class="sxs-lookup"><span data-stu-id="579b2-360">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="579b2-361">Der verbesserte Bericht über Spooferkennungen, wie in diesem Artikel beschrieben, befindet sich in der Vorschau, kann geändert werden und ist nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="579b2-361">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="579b2-362">Die ältere Version des Berichts zeigt nur **gute E-Mails** und **"Als Spam abgefangen"** an.</span><span class="sxs-lookup"><span data-stu-id="579b2-362">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="579b2-363">Der Bericht **"Spooferkennungen"** enthält Informationen zu Nachrichten, die aufgrund von Spoofing blockiert oder zugelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="579b2-363">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="579b2-364">Weitere Informationen zum Spoofing finden Sie unter [Antispoofingschutz in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-364">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="579b2-365">Die Aggregatansicht des Berichts lässt 45 Tage Filterung <sup>\*</sup> zu, während die Detailansicht nur zehn Tage Filterung zulässt.</span><span class="sxs-lookup"><span data-stu-id="579b2-365">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="579b2-366"><sup>\*</sup> Schließlich können Sie die Filterung bis zu 90 Tage verwenden.</span><span class="sxs-lookup"><span data-stu-id="579b2-366"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="579b2-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="579b2-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="579b2-368">Klicken Sie bei **Spooferkennungen** auf **Details anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="579b2-368">On **Spoof detections**, click **View details**.</span></span> <span data-ttu-id="579b2-369">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="579b2-369">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Spooferkennungs-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/spoof-detections-widget.png)

<span data-ttu-id="579b2-371">Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, können Sie sehen, wie viele gefälschte Nachrichten erkannt wurden und warum.</span><span class="sxs-lookup"><span data-stu-id="579b2-371">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="579b2-372">Nachdem Sie auf **"Details anzeigen"** geklickt haben, können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="579b2-372">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="579b2-373">**Datum:** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="579b2-373">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="579b2-374">**Ergebnis:**</span><span class="sxs-lookup"><span data-stu-id="579b2-374">**Result**:</span></span>
  - <span data-ttu-id="579b2-375">**bestehen**</span><span class="sxs-lookup"><span data-stu-id="579b2-375">**Pass**</span></span>
  - <span data-ttu-id="579b2-376">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="579b2-376">**Fail**</span></span>
  - <span data-ttu-id="579b2-377">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="579b2-377">**SoftPass**</span></span>
  - <span data-ttu-id="579b2-378">**Keine**</span><span class="sxs-lookup"><span data-stu-id="579b2-378">**None**</span></span>
  - <span data-ttu-id="579b2-379">**Other**</span><span class="sxs-lookup"><span data-stu-id="579b2-379">**Other**</span></span>
- <span data-ttu-id="579b2-380">**Spooftyp:** **Intern** und **extern**</span><span class="sxs-lookup"><span data-stu-id="579b2-380">**Spoof type**: **Internal** and **External**</span></span>

![Seite "Spoof-E-Mail-Bericht" im Microsoft 365 Defender-Portal](../../media/spoof-detections-report-page.png)

<span data-ttu-id="579b2-382">In der Tabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="579b2-382">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="579b2-383">**Date**</span><span class="sxs-lookup"><span data-stu-id="579b2-383">**Date**</span></span>
- <span data-ttu-id="579b2-384">**Gefälschter Benutzer**</span><span class="sxs-lookup"><span data-stu-id="579b2-384">**Spoofed user**</span></span>
- <span data-ttu-id="579b2-385">**Senden der Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="579b2-385">**Sending infrastructure**</span></span>
- <span data-ttu-id="579b2-386">**Spooftyp**</span><span class="sxs-lookup"><span data-stu-id="579b2-386">**Spoof type**</span></span>
- <span data-ttu-id="579b2-387">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="579b2-387">**Result**</span></span>
- <span data-ttu-id="579b2-388">**Ergebniscode**</span><span class="sxs-lookup"><span data-stu-id="579b2-388">**Result code**</span></span>
- <span data-ttu-id="579b2-389">**SPF**</span><span class="sxs-lookup"><span data-stu-id="579b2-389">**SPF**</span></span>
- <span data-ttu-id="579b2-390">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="579b2-390">**DKIM**</span></span>
- <span data-ttu-id="579b2-391">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="579b2-391">**DMARC**</span></span>
- <span data-ttu-id="579b2-392">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="579b2-392">**Message count**</span></span>

<span data-ttu-id="579b2-393">Weitere Informationen zu Ergebniscodes für die zusammengesetzte Authentifizierung finden Sie unter [Antispam-Nachrichtenkopfzeilen in Microsoft 365.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-393">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="579b2-394">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="579b2-394">Threat protection status report</span></span>

<span data-ttu-id="579b2-395">Der **Bedrohungsschutzstatusbericht** ist sowohl in EOP als auch in Defender für Office 365 verfügbar. Die Berichte enthalten jedoch unterschiedliche Daten.</span><span class="sxs-lookup"><span data-stu-id="579b2-395">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="579b2-396">EOP-Kunden können z. B. Informationen zu schadsoftware anzeigen, die in E-Mails erkannt wurde, aber keine Informationen zu schädlichen Dateien, die von [Safe Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="579b2-396">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="579b2-397">Der Bericht enthält die Anzahl der E-Mail-Nachrichten mit schädlichen Inhalten, z. B. Dateien oder Websiteadressen (URLs), die vom Antischadsoftwaremodul blockiert wurden, Zap [(Zero-Hour Auto Purge)](zero-hour-auto-purge.md)und Defender für Office 365 Features wie [Safe Links,](safe-links.md)Safe Anlagen und [Identitätswechselschutzfeatures in Antiphishingrichtlinien.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) [](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-397">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="579b2-398">Anhand dieser Informationen können Sie Trends erkennen oder ermitteln, ob Die Unternehmensrichtlinien angepasst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="579b2-398">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="579b2-399">**Hinweis:** Es ist wichtig zu wissen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="579b2-399">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="579b2-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="579b2-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="579b2-401">Klicken Sie auf **"Bedrohungsschutzstatus"** auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="579b2-401">On **Threat protection status**, click **View details**.</span></span> <span data-ttu-id="579b2-402">Um direkt zum Bericht zu wechseln, öffnen Sie eine der folgenden URLs:</span><span class="sxs-lookup"><span data-stu-id="579b2-402">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="579b2-403">Defender für Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="579b2-403">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="579b2-404">Eop: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="579b2-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Bedrohungsschutzstatus-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="579b2-406">Nachdem Sie auf **"Details anzeigen"** geklickt haben, werden im Diagramm standardmäßig Daten für die letzten 7 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="579b2-406">By default, after you click **View details**, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="579b2-407">Wenn Sie auf **"Filtern"** klicken, können Sie einen Zeitraum von 90 Tagen auswählen (Testabonnements sind möglicherweise auf 30 Tage beschränkt).</span><span class="sxs-lookup"><span data-stu-id="579b2-407">If you click **Filter**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="579b2-408">Die Detailtabelle ermöglicht das Filtern für 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="579b2-408">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="579b2-409">Die verfügbaren Ansichten werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="579b2-409">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="579b2-410">Anzeigen von Daten nach Übersicht</span><span class="sxs-lookup"><span data-stu-id="579b2-410">View data by Overview</span></span>

![Übersichtsansicht im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="579b2-412">In der Ansicht **"Ansichtsdaten nach Übersicht"** werden die folgenden Erkennungsinformationen im Diagramm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="579b2-412">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="579b2-413">**E-Mail-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="579b2-413">**Email malware**</span></span>
- <span data-ttu-id="579b2-414">**E-Mail-Phishing**</span><span class="sxs-lookup"><span data-stu-id="579b2-414">**Email phish**</span></span>
- <span data-ttu-id="579b2-415">**Inhalts-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="579b2-415">**Content malware**</span></span>

<span data-ttu-id="579b2-416">Unterhalb des Diagramms ist keine Detailtabelle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="579b2-416">No details table is available below the chart.</span></span>

<span data-ttu-id="579b2-417">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-417">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="579b2-418">**Datum:** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="579b2-418">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="579b2-419">**Erkennung:** **E-Mail-Schadsoftware,** **E-Mail-Phishing** oder **Inhalts-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="579b2-419">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="579b2-420">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="579b2-420">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="579b2-421">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="579b2-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="579b2-422">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="579b2-423">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="579b2-423">**Direction**</span></span>
- <span data-ttu-id="579b2-424">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="579b2-424">**Domain**</span></span>
- <span data-ttu-id="579b2-425">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="579b2-425">**Policy type**</span></span>

<span data-ttu-id="579b2-426">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="579b2-426">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="579b2-427">Anzeigen von Daten nach E-Mail-Phishing \> und Diagrammstrukturplan nach Erkennungstechnologie</span><span class="sxs-lookup"><span data-stu-id="579b2-427">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Ansicht der Erkennungstechnologie für Phishing-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="579b2-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span><span class="sxs-lookup"><span data-stu-id="579b2-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="579b2-430">**url malicious reputation:** <sup>\*</sup> Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span><span class="sxs-lookup"><span data-stu-id="579b2-430">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="579b2-431">**Erweiterter Filter:** Phishingsignale basierend auf maschinellem Lernen.</span><span class="sxs-lookup"><span data-stu-id="579b2-431">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="579b2-432">**Allgemeiner Filter:** Phishingsignale basierend auf Analystenregeln.</span><span class="sxs-lookup"><span data-stu-id="579b2-432">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="579b2-433">**Organisationsinternes Spoofing:** Der Absender versucht, die Empfängerdomäne zu spoofen.</span><span class="sxs-lookup"><span data-stu-id="579b2-433">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="579b2-434">**Spoofing externer Domäne:** Der Absender versucht, eine andere Domäne zu spoofen.</span><span class="sxs-lookup"><span data-stu-id="579b2-434">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="579b2-435">**Spoofing von DMARC:** DMARC-Authentifizierungsfehler bei Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="579b2-435">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="579b2-436">**Identitätswechselmarke:** Identitätswechsel bekannter Marken basierend auf Absendern.</span><span class="sxs-lookup"><span data-stu-id="579b2-436">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="579b2-437">**Erkennung durch gemischte Analysen**</span><span class="sxs-lookup"><span data-stu-id="579b2-437">**Mixed analysis detection**</span></span>
- <span data-ttu-id="579b2-438">**Datei-Reputation**</span><span class="sxs-lookup"><span data-stu-id="579b2-438">**File reputation**</span></span>
- <span data-ttu-id="579b2-439">**Fingerabdruckübereinstimmung**</span><span class="sxs-lookup"><span data-stu-id="579b2-439">**Fingerprint matching**</span></span>
- <span data-ttu-id="579b2-440">**Zuverlässigkeit der URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="579b2-440">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="579b2-441">**URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="579b2-441">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="579b2-442">**Identitätswechselbenutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="579b2-442">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="579b2-443">**Identitätswechseldomäne:** <sup>\*</sup> Identitätswechsel von Domänen, die der Kunde besitzt oder definiert.</span><span class="sxs-lookup"><span data-stu-id="579b2-443">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="579b2-444">**Identitätswechsel bei der Postfachintelligenz:** <sup>\*</sup> Identitätswechsel von Benutzern, die vom Administrator definiert oder durch die Postfachintelligenz gelernt wurden.</span><span class="sxs-lookup"><span data-stu-id="579b2-444">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="579b2-445">**Dateidetonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="579b2-445">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="579b2-446">**Kampagne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="579b2-446">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="579b2-447">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-447">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="579b2-448">**Date**</span><span class="sxs-lookup"><span data-stu-id="579b2-448">**Date**</span></span>
- <span data-ttu-id="579b2-449">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="579b2-449">**Subject**</span></span>
- <span data-ttu-id="579b2-450">**Sender**</span><span class="sxs-lookup"><span data-stu-id="579b2-450">**Sender**</span></span>
- <span data-ttu-id="579b2-451">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="579b2-451">**Recipients**</span></span>
- <span data-ttu-id="579b2-452">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="579b2-452">**Detected by**</span></span>
- <span data-ttu-id="579b2-453">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="579b2-453">**Delivery Status**</span></span>
- <span data-ttu-id="579b2-454">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="579b2-454">**Source of Compromise**</span></span>
- <span data-ttu-id="579b2-455">**Tags**</span><span class="sxs-lookup"><span data-stu-id="579b2-455">**Tags**</span></span>

<span data-ttu-id="579b2-456">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-456">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="579b2-457">**Datum:** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="579b2-457">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="579b2-458">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="579b2-458">**Detection**</span></span>
- <span data-ttu-id="579b2-459">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="579b2-459">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="579b2-460">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="579b2-460">**Direction**</span></span>
- <span data-ttu-id="579b2-461">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="579b2-461">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="579b2-462">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-462">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="579b2-463">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="579b2-463">**Domain**</span></span>
- <span data-ttu-id="579b2-464">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="579b2-464">**Policy type**</span></span>
- <span data-ttu-id="579b2-465">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="579b2-465">**Policy name** (details table only)</span></span>
- <span data-ttu-id="579b2-466">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="579b2-466">**Recipients**</span></span>

<span data-ttu-id="579b2-467">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="579b2-467">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="579b2-468">Anzeigen von Daten nach \> E-Mail-Schadsoftware und Diagrammstrukturplan nach Erkennungstechnologie</span><span class="sxs-lookup"><span data-stu-id="579b2-468">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Ansicht der Erkennungstechnologie für Schadsoftware im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="579b2-470">In der **Ansicht Ansichtsdaten nach E-Mail-Schadsoftware \>** und **Diagrammstrukturplan nach Erkennungstechnologie** werden die folgenden Informationen im Diagramm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="579b2-470">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="579b2-471">**Dateidetonation:** <sup>\*</sup> Erkennung durch Safe Anlagen.</span><span class="sxs-lookup"><span data-stu-id="579b2-471">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="579b2-472">**Zuverlässigkeit der Dateidetonation:** <sup>\*</sup> Alle bösartigen Dateireputationen, die von Defender für Office 365 Detonationen generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="579b2-472">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="579b2-473">**Datei-Reputation**</span><span class="sxs-lookup"><span data-stu-id="579b2-473">**File reputation**</span></span>
- <span data-ttu-id="579b2-474">**Antischadsoftwaremodul:** <sup>\*</sup> Erkennung von Antischadsoftwaremodulen.</span><span class="sxs-lookup"><span data-stu-id="579b2-474">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="579b2-475">Dateitypblock für **Antischadsoftwarerichtlinie:** Hierbei handelt es sich um E-Mail-Nachrichten, die aufgrund des in der Nachricht identifizierten Typs bösartiger Dateien herausgefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="579b2-475">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="579b2-476">**URL-Reputation als schädlich eingestuft**</span><span class="sxs-lookup"><span data-stu-id="579b2-476">**URL malicious reputation**</span></span>
- <span data-ttu-id="579b2-477">**URL-Detonation**</span><span class="sxs-lookup"><span data-stu-id="579b2-477">**URL detonation**</span></span>
- <span data-ttu-id="579b2-478">**Reputation der URL-Detonation**</span><span class="sxs-lookup"><span data-stu-id="579b2-478">**URL detonation reputation**</span></span>
- <span data-ttu-id="579b2-479">**Kampagnen**</span><span class="sxs-lookup"><span data-stu-id="579b2-479">**Campaign**</span></span>

<span data-ttu-id="579b2-480">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-480">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="579b2-481">**Date**</span><span class="sxs-lookup"><span data-stu-id="579b2-481">**Date**</span></span>
- <span data-ttu-id="579b2-482">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="579b2-482">**Subject**</span></span>
- <span data-ttu-id="579b2-483">**Sender**</span><span class="sxs-lookup"><span data-stu-id="579b2-483">**Sender**</span></span>
- <span data-ttu-id="579b2-484">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="579b2-484">**Recipients**</span></span>
- <span data-ttu-id="579b2-485">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="579b2-485">**Detected by**</span></span>
- <span data-ttu-id="579b2-486">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="579b2-486">**Delivery Status**</span></span>
- <span data-ttu-id="579b2-487">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="579b2-487">**Source of Compromise**</span></span>
- <span data-ttu-id="579b2-488">**Tags**</span><span class="sxs-lookup"><span data-stu-id="579b2-488">**Tags**</span></span>

<span data-ttu-id="579b2-489">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-489">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="579b2-490">**Datum:** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="579b2-490">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="579b2-491">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="579b2-491">**Detection**</span></span>
- <span data-ttu-id="579b2-492">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="579b2-492">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="579b2-493">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="579b2-493">**Direction**</span></span>
- <span data-ttu-id="579b2-494">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="579b2-494">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="579b2-495">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-495">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="579b2-496">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="579b2-496">**Domain**</span></span>
- <span data-ttu-id="579b2-497">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="579b2-497">**Policy type**</span></span>
- <span data-ttu-id="579b2-498">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="579b2-498">**Policy name** (details table only)</span></span>
- <span data-ttu-id="579b2-499">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="579b2-499">**Recipients**</span></span>

<span data-ttu-id="579b2-500">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="579b2-500">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="579b2-501">Diagrammaufschlüsselung nach Richtlinientyp und Anzeigen von Daten nach E-Mail-Phishing \> oder Anzeigen von Daten durch E-Mail-Schadsoftware \></span><span class="sxs-lookup"><span data-stu-id="579b2-501">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Richtlinientypansicht für Phishing-E-Mails oder Schadsoftware-E-Mails im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="579b2-503">In der **Diagrammaufschlüsselung nach Richtlinientyp** und **Anzeigen von Daten nach E-Mail-Phishing \>** oder **Anzeigen von Daten nach E-Mail-Schadsoftwareansichten \>** werden die folgenden Informationen in den Diagrammen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="579b2-503">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="579b2-504">**Antischadsoftware**</span><span class="sxs-lookup"><span data-stu-id="579b2-504">**Anti-malware**</span></span>
- <span data-ttu-id="579b2-505">**Safe Anlagen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="579b2-505">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="579b2-506">**Antiphishing**</span><span class="sxs-lookup"><span data-stu-id="579b2-506">**Anti-phish**</span></span>
- <span data-ttu-id="579b2-507">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="579b2-507">**Anti-spam**</span></span>
- <span data-ttu-id="579b2-508">**Nachrichtenflussregel** (auch als Transportregel bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="579b2-508">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="579b2-509">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="579b2-509">**Others**</span></span>

<span data-ttu-id="579b2-510">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-510">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="579b2-511">**Date**</span><span class="sxs-lookup"><span data-stu-id="579b2-511">**Date**</span></span>
- <span data-ttu-id="579b2-512">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="579b2-512">**Subject**</span></span>
- <span data-ttu-id="579b2-513">**Sender**</span><span class="sxs-lookup"><span data-stu-id="579b2-513">**Sender**</span></span>
- <span data-ttu-id="579b2-514">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="579b2-514">**Recipients**</span></span>
- <span data-ttu-id="579b2-515">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="579b2-515">**Detected by**</span></span>
- <span data-ttu-id="579b2-516">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="579b2-516">**Delivery Status**</span></span>
- <span data-ttu-id="579b2-517">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="579b2-517">**Source of Compromise**</span></span>
- <span data-ttu-id="579b2-518">**Tags**</span><span class="sxs-lookup"><span data-stu-id="579b2-518">**Tags**</span></span>

<span data-ttu-id="579b2-519">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-519">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="579b2-520">**Datum:** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="579b2-520">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="579b2-521">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="579b2-521">**Detection**</span></span>
- <span data-ttu-id="579b2-522">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="579b2-522">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="579b2-523">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="579b2-523">**Direction**</span></span>
- <span data-ttu-id="579b2-524">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="579b2-524">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="579b2-525">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-525">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="579b2-526">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="579b2-526">**Domain**</span></span>
- <span data-ttu-id="579b2-527">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="579b2-527">**Policy type**</span></span>
- <span data-ttu-id="579b2-528">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="579b2-528">**Policy name** (details table only)</span></span>
- <span data-ttu-id="579b2-529">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="579b2-529">**Recipients**</span></span>

<span data-ttu-id="579b2-530">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="579b2-530">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="579b2-531">Diagrammaufschlüsselung nach Zustellungsstatus und Anzeigen von Daten nach E-Mail-Phishing \> oder Anzeigen von Daten durch E-Mail-Schadsoftware \></span><span class="sxs-lookup"><span data-stu-id="579b2-531">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Übermittlungsstatusansicht für Phishing-E-Mails und Schadsoftware-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="579b2-533">In der **Diagrammaufschlüsselung nach Übermittlungsstatus** und **Anzeigen von Daten nach E-Mail-Phishing \>** oder **Anzeigen von Daten nach E-Mail-Schadsoftwareansichten \>** werden die folgenden Informationen in den Diagrammen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="579b2-533">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="579b2-534">**Gehostetes Postfach: Posteingang**</span><span class="sxs-lookup"><span data-stu-id="579b2-534">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="579b2-535">**Gehostetes Postfach: Junk**</span><span class="sxs-lookup"><span data-stu-id="579b2-535">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="579b2-536">**Gehostetes Postfach: Benutzerdefinierter Ordner**</span><span class="sxs-lookup"><span data-stu-id="579b2-536">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="579b2-537">**Gehostetes Postfach: Gelöschte Elemente**</span><span class="sxs-lookup"><span data-stu-id="579b2-537">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="579b2-538">**Weitergeleitet**</span><span class="sxs-lookup"><span data-stu-id="579b2-538">**Forwarded**</span></span>
- <span data-ttu-id="579b2-539">**Lokaler Server: Bereitgestellt**</span><span class="sxs-lookup"><span data-stu-id="579b2-539">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="579b2-540">**Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="579b2-540">**Quarantine**</span></span>
- <span data-ttu-id="579b2-541">**Übermittlung fehlgeschlagen**</span><span class="sxs-lookup"><span data-stu-id="579b2-541">**Delivery failed**</span></span>
- <span data-ttu-id="579b2-542">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="579b2-542">**Dropped**</span></span>

<span data-ttu-id="579b2-543">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-543">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="579b2-544">**Date**</span><span class="sxs-lookup"><span data-stu-id="579b2-544">**Date**</span></span>
- <span data-ttu-id="579b2-545">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="579b2-545">**Subject**</span></span>
- <span data-ttu-id="579b2-546">**Sender**</span><span class="sxs-lookup"><span data-stu-id="579b2-546">**Sender**</span></span>
- <span data-ttu-id="579b2-547">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="579b2-547">**Recipients**</span></span>
- <span data-ttu-id="579b2-548">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="579b2-548">**Detected by**</span></span>
- <span data-ttu-id="579b2-549">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="579b2-549">**Delivery Status**</span></span>
- <span data-ttu-id="579b2-550">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="579b2-550">**Source of Compromise**</span></span>
- <span data-ttu-id="579b2-551">**Tags**</span><span class="sxs-lookup"><span data-stu-id="579b2-551">**Tags**</span></span>

<span data-ttu-id="579b2-552">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-552">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="579b2-553">**Datum:** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="579b2-553">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="579b2-554">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="579b2-554">**Detection**</span></span>
- <span data-ttu-id="579b2-555">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="579b2-555">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="579b2-556">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="579b2-556">**Direction**</span></span>
- <span data-ttu-id="579b2-557">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="579b2-557">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="579b2-558">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-558">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="579b2-559">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="579b2-559">**Domain**</span></span>
- <span data-ttu-id="579b2-560">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="579b2-560">**Policy type**</span></span>
- <span data-ttu-id="579b2-561">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="579b2-561">**Policy name** (details table only)</span></span>
- <span data-ttu-id="579b2-562">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="579b2-562">**Recipients**</span></span>

<span data-ttu-id="579b2-563">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="579b2-563">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="579b2-564">Anzeigen von Daten nach \> Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="579b2-564">View data by Content \> Malware</span></span>

![Ansicht "Inhalts-Schadsoftware" im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="579b2-566">In der Ansicht **"Daten nach \> Inhalts-Schadsoftware** anzeigen" werden die folgenden Informationen im Diagramm für Microsoft Defender für Office 365 Organisationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="579b2-566">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="579b2-567">**Antischadsoftwaremodul:** Schädliche Dateien, die in SharePoint, OneDrive und Microsoft Teams von der [integrierten Virenerkennung in Microsoft 365](virus-detection-in-spo.md)erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="579b2-567">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="579b2-568">**Dateidetonation:** Schädliche Dateien, die von [Safe Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="579b2-568">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="579b2-569">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-569">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="579b2-570">**Datum:** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="579b2-570">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="579b2-571">**Standort**</span><span class="sxs-lookup"><span data-stu-id="579b2-571">**Location**</span></span>
- <span data-ttu-id="579b2-572">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="579b2-572">**Detected by**</span></span>
- <span data-ttu-id="579b2-573">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="579b2-573">**Malware name**</span></span>

<span data-ttu-id="579b2-574">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="579b2-575">**Datum:** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="579b2-575">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="579b2-576">**Erkennung:** **Antischadsoftwaremodul** oder **Dateidetonation**</span><span class="sxs-lookup"><span data-stu-id="579b2-576">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="579b2-577">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="579b2-577">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="579b2-578">Anzeigen von Daten nach Systemüberschreibung</span><span class="sxs-lookup"><span data-stu-id="579b2-578">View data by System override</span></span>

![Ansicht "Nachrichtenüberschreibung" im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="579b2-580">In der Ansicht **"Ansichtsdaten nach Systemüberschreibung"** werden die folgenden Informationen zum Außerkraftsetzungsgrund im Diagramm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="579b2-580">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="579b2-581">**Lokales Überspringen**</span><span class="sxs-lookup"><span data-stu-id="579b2-581">**On-premises skip**</span></span>
- <span data-ttu-id="579b2-582">**IP zulassen**</span><span class="sxs-lookup"><span data-stu-id="579b2-582">**IP allow**</span></span>
- <span data-ttu-id="579b2-583">**Exchange E-Mail-Transportregel** (Nachrichtenflussregel)</span><span class="sxs-lookup"><span data-stu-id="579b2-583">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="579b2-584">**Zulässige Absender in der Organisation**</span><span class="sxs-lookup"><span data-stu-id="579b2-584">**Organization allowed senders**</span></span>
- <span data-ttu-id="579b2-585">**Zulässige Domänen der Organisation**</span><span class="sxs-lookup"><span data-stu-id="579b2-585">**Organization allowed domains**</span></span>
- <span data-ttu-id="579b2-586">**ZAP nicht aktiviert**</span><span class="sxs-lookup"><span data-stu-id="579b2-586">**ZAP not enabled**</span></span>
- <span data-ttu-id="579b2-587">**Junk-E-Mail-Ordner nicht aktiviert**</span><span class="sxs-lookup"><span data-stu-id="579b2-587">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="579b2-588">**Benutzer Safe Absender**</span><span class="sxs-lookup"><span data-stu-id="579b2-588">**User Safe Sender**</span></span>
- <span data-ttu-id="579b2-589">**Safe Domäne des Benutzers**</span><span class="sxs-lookup"><span data-stu-id="579b2-589">**User Safe Domain**</span></span>

<span data-ttu-id="579b2-590">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-590">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="579b2-591">**Date**</span><span class="sxs-lookup"><span data-stu-id="579b2-591">**Date**</span></span>
- <span data-ttu-id="579b2-592">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="579b2-592">**Subject**</span></span>
- <span data-ttu-id="579b2-593">**Sender**</span><span class="sxs-lookup"><span data-stu-id="579b2-593">**Sender**</span></span>
- <span data-ttu-id="579b2-594">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="579b2-594">**Recipients**</span></span>
- <span data-ttu-id="579b2-595">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="579b2-595">**Detected by**</span></span>
- <span data-ttu-id="579b2-596">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="579b2-596">**Delivery Status**</span></span>
- <span data-ttu-id="579b2-597">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="579b2-597">**Source of Compromise**</span></span>
- <span data-ttu-id="579b2-598">**Tags**</span><span class="sxs-lookup"><span data-stu-id="579b2-598">**Tags**</span></span>

<span data-ttu-id="579b2-599">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="579b2-599">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="579b2-600">**Datum:** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="579b2-600">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="579b2-601">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="579b2-601">**Detection**</span></span>
- <span data-ttu-id="579b2-602">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="579b2-602">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="579b2-603">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="579b2-603">**Direction**</span></span>
- <span data-ttu-id="579b2-604">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="579b2-604">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="579b2-605">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-605">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="579b2-606">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="579b2-606">**Domain**</span></span>
- <span data-ttu-id="579b2-607">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="579b2-607">**Policy type**</span></span>
- <span data-ttu-id="579b2-608">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="579b2-608">**Policy name** (details table only)</span></span>
- <span data-ttu-id="579b2-609">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="579b2-609">**Recipients**</span></span>

<span data-ttu-id="579b2-610">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="579b2-610">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="579b2-611"><sup>\*</sup>Nur Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="579b2-611"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="579b2-612">Bericht über häufigste Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="579b2-612">Top malware report</span></span>

<span data-ttu-id="579b2-613">Der **Bericht "Häufigste Schadsoftware"** zeigt die verschiedenen Arten von Schadsoftware, die vom [Schutz vor Schadsoftware in EOP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="579b2-613">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="579b2-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="579b2-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="579b2-615">On **Top malware**, click View **details**.</span><span class="sxs-lookup"><span data-stu-id="579b2-615">On **Top malware**, click **View details**.</span></span> <span data-ttu-id="579b2-616">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="579b2-616">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Das am häufigsten verwendete Malware-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/top-malware-report-widget.png)

<span data-ttu-id="579b2-618">Wenn Sie den Mauszeiger über einen Wedge im Kreisdiagramm bewegen, sehen Sie den Namen einer Art von Schadsoftware und wie viele Nachrichten als Schadsoftware erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="579b2-618">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="579b2-619">Nachdem Sie auf **"Details anzeigen"** geklickt haben, wird eine größere Version des Kreisdiagramms auf der Berichtsseite angezeigt. Die Detailtabelle unterhalb des Diagramms enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="579b2-619">After you click **View details**, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="579b2-620">**Häufigste Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="579b2-620">**Top malware**</span></span>
- <span data-ttu-id="579b2-621">**Count**</span><span class="sxs-lookup"><span data-stu-id="579b2-621">**Count**</span></span>

<span data-ttu-id="579b2-622">Wenn Sie auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="579b2-622">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Ansicht des Berichts über häufigste Schadsoftware](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="579b2-624">URL-Bedrohungsschutzbericht</span><span class="sxs-lookup"><span data-stu-id="579b2-624">URL threat protection report</span></span>

<span data-ttu-id="579b2-625">Der **URL-Bedrohungsschutzbericht** ist in Microsoft Defender für Office 365 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="579b2-625">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="579b2-626">Weitere Informationen finden Sie unter [URL Threat Protection Report](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="579b2-626">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="579b2-627">Bericht über vom Benutzer gemeldete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="579b2-627">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="579b2-628">Damit der Bericht über **vom Benutzer gemeldete Nachrichten** ordnungsgemäß funktioniert, muss die **Überwachungsprotokollierung** für Ihre Microsoft 365 Umgebung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="579b2-628">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="579b2-629">Dies geschieht in der Regel von einer Person, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="579b2-629">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="579b2-630">Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren Microsoft 365 Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-630">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="579b2-631">Der Bericht **"Vom Benutzer gemeldete Nachrichten"** enthält Informationen zu E-Mail-Nachrichten, die Benutzer mithilfe des [Add-Ins "Nachricht melden"](enable-the-report-message-add-in.md) oder des [Add-Ins "Phishing melden"](enable-the-report-phish-add-in.md)als Junk, Phishingversuche oder gute E-Mails gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="579b2-631">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="579b2-632">Um den Bericht im Microsoft 365 Defender-Portal anzuzeigen,  wechseln Sie zu \> **E-Mail-Berichte & Zusammenarbeit** \> **E-Mail & Berichte zur Zusammenarbeit** Von Benutzern \> **gemeldete Nachrichten.**</span><span class="sxs-lookup"><span data-stu-id="579b2-632">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span> <span data-ttu-id="579b2-633">On **User reported messages**, click View **details**.</span><span class="sxs-lookup"><span data-stu-id="579b2-633">On **User reported messages**, click **View details**.</span></span> <span data-ttu-id="579b2-634">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="579b2-634">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="579b2-635">Wenn Sie im Microsoft 365 Defender Portal zu [Administratorübermittlungen](admin-submission.md)wechseln möchten, klicken Sie auf **"Zu Übermittlungen wechseln".**</span><span class="sxs-lookup"><span data-stu-id="579b2-635">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Vom Benutzer gemeldete Nachrichten-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/user-reported-messages-widget.png)

<span data-ttu-id="579b2-637">Nachdem Sie auf **"Details anzeigen"** geklickt haben, können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="579b2-637">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="579b2-638">**Gemeldetes Datum**: **Startzeit** und **Endzeit**</span><span class="sxs-lookup"><span data-stu-id="579b2-638">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="579b2-639">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="579b2-639">**Reported by**</span></span>
- <span data-ttu-id="579b2-640">**E-Mail-Betreff**</span><span class="sxs-lookup"><span data-stu-id="579b2-640">**Email subject**</span></span>
- <span data-ttu-id="579b2-641">**Gemeldete ID der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="579b2-641">**Message reported ID**</span></span>
- <span data-ttu-id="579b2-642">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="579b2-642">**Network Message ID**</span></span>
- <span data-ttu-id="579b2-643">**Sender**</span><span class="sxs-lookup"><span data-stu-id="579b2-643">**Sender**</span></span>
- <span data-ttu-id="579b2-644">**Gemeldeter Grund**</span><span class="sxs-lookup"><span data-stu-id="579b2-644">**Reported reason**</span></span>
  - <span data-ttu-id="579b2-645">**Kein Junk**</span><span class="sxs-lookup"><span data-stu-id="579b2-645">**Not junk**</span></span>
  - <span data-ttu-id="579b2-646">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="579b2-646">**Phish**</span></span>
  - <span data-ttu-id="579b2-647">**Spam**</span><span class="sxs-lookup"><span data-stu-id="579b2-647">**Spam**</span></span>
- <span data-ttu-id="579b2-648">**Phishing-Simulation:** **Ja** oder **Nein**</span><span class="sxs-lookup"><span data-stu-id="579b2-648">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="579b2-649">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="579b2-649">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="579b2-650">Klicken Sie zum Gruppieren der Einträge auf **"Gruppieren",** und wählen Sie einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="579b2-650">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="579b2-651">**Keine**</span><span class="sxs-lookup"><span data-stu-id="579b2-651">**None**</span></span>
- <span data-ttu-id="579b2-652">**Grund**</span><span class="sxs-lookup"><span data-stu-id="579b2-652">**Reason**</span></span>
- <span data-ttu-id="579b2-653">**Sender**</span><span class="sxs-lookup"><span data-stu-id="579b2-653">**Sender**</span></span>
- <span data-ttu-id="579b2-654">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="579b2-654">**Reported by**</span></span>
- <span data-ttu-id="579b2-655">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="579b2-655">**Rescan result**</span></span>
- <span data-ttu-id="579b2-656">**Phishing-Simulation**</span><span class="sxs-lookup"><span data-stu-id="579b2-656">**Phish simulation**</span></span>

![Bericht über vom Benutzer gemeldete Nachrichten](../../media/user-reported-messages-report.png)

<span data-ttu-id="579b2-658">In der Tabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="579b2-658">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="579b2-659">**E-Mail-Betreff**</span><span class="sxs-lookup"><span data-stu-id="579b2-659">**Email subject**</span></span>
- <span data-ttu-id="579b2-660">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="579b2-660">**Reported by**</span></span>
- <span data-ttu-id="579b2-661">**Gemeldetes Datum**</span><span class="sxs-lookup"><span data-stu-id="579b2-661">**Date reported**</span></span>
- <span data-ttu-id="579b2-662">**Sender**</span><span class="sxs-lookup"><span data-stu-id="579b2-662">**Sender**</span></span>
- <span data-ttu-id="579b2-663">**Gemeldeter Grund**</span><span class="sxs-lookup"><span data-stu-id="579b2-663">**Reported reason**</span></span>
- <span data-ttu-id="579b2-664">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="579b2-664">**Rescan result**</span></span>
- <span data-ttu-id="579b2-665">**Tags**</span><span class="sxs-lookup"><span data-stu-id="579b2-665">**Tags**</span></span>

<span data-ttu-id="579b2-666">Um eine Nachricht zur Analyse an Microsoft zu übermitteln, wählen Sie den Nachrichteneintrag aus der Tabelle aus, klicken Sie auf **"Zur Analyse an Microsoft übermitteln",** und wählen Sie dann einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="579b2-666">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="579b2-667">**Bericht sauber**</span><span class="sxs-lookup"><span data-stu-id="579b2-667">**Report clean**</span></span>
- <span data-ttu-id="579b2-668">**Melden von Phishing**</span><span class="sxs-lookup"><span data-stu-id="579b2-668">**Report phishing**</span></span>
- <span data-ttu-id="579b2-669">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="579b2-669">**Report malware**</span></span>
- <span data-ttu-id="579b2-670">**Spam melden**'</span><span class="sxs-lookup"><span data-stu-id="579b2-670">**Report spam**'</span></span>
- <span data-ttu-id="579b2-671">**Untersuchung auslösen** (Defender für Office 365)</span><span class="sxs-lookup"><span data-stu-id="579b2-671">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="579b2-672">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="579b2-672">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="579b2-673">Um die in diesem Artikel beschriebenen Berichte anzuzeigen und zu verwenden, müssen Sie Mitglied einer der folgenden Rollengruppen im Microsoft 365 Defender Portal sein:</span><span class="sxs-lookup"><span data-stu-id="579b2-673">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="579b2-674">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="579b2-674">**Organization Management**</span></span>
- <span data-ttu-id="579b2-675">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="579b2-675">**Security Administrator**</span></span>
- <span data-ttu-id="579b2-676">**Sicherheitsleseberechtigter**</span><span class="sxs-lookup"><span data-stu-id="579b2-676">**Security Reader**</span></span>
- <span data-ttu-id="579b2-677">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="579b2-677">**Global Reader**</span></span>

<span data-ttu-id="579b2-678">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-678">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="579b2-679">**Hinweis:** Das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center bietet Benutzern die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="579b2-679">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="579b2-680">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="579b2-680">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="579b2-681">Was geschieht, wenn in den Berichten keine Daten angezeigt werden?</span><span class="sxs-lookup"><span data-stu-id="579b2-681">What if the reports aren't showing data?</span></span>

<span data-ttu-id="579b2-682">Wenn in Ihren Berichten keine Daten angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="579b2-682">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="579b2-683">Weitere Informationen finden Sie unter ["Schutz vor Bedrohungen".](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="579b2-683">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="579b2-684">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="579b2-684">Related topics</span></span>

[<span data-ttu-id="579b2-685">Antispam- und Antischadsoftwareschutz in EOP</span><span class="sxs-lookup"><span data-stu-id="579b2-685">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="579b2-686">Intelligente Berichte und Einblicke im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="579b2-686">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="579b2-687">Anzeigen von Nachrichtenflussberichten im Microsoft 365 Defender Portal</span><span class="sxs-lookup"><span data-stu-id="579b2-687">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="579b2-688">Anzeigen von Berichten für Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="579b2-688">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
