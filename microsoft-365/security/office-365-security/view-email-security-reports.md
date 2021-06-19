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
ms.openlocfilehash: ad5a9f0d87902deb1985daebfa61cd733d22cbec
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029577"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="0c173-103">Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="0c173-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0c173-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="0c173-104">**Applies to**</span></span>
- [<span data-ttu-id="0c173-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0c173-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0c173-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="0c173-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0c173-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c173-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0c173-108">Im Microsoft 365 Defender-Portal finden Sie eine Vielzahl von Berichten, <https://security.microsoft.com> mit denen Sie sehen können, wie E-Mail-Sicherheitsfeatures wie Antispam, Antischadsoftware und Verschlüsselungsfunktionen in Microsoft 365 Ihre Organisation schützen.</span><span class="sxs-lookup"><span data-stu-id="0c173-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="0c173-109">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im Microsoft 365 Defender-Portal anzeigen, indem Sie zu  \> **E-Mail-Berichte &** \> **ZusammenarbeitS-E-Mail & Zusammenarbeitsberichte wechseln.**</span><span class="sxs-lookup"><span data-stu-id="0c173-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0c173-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="0c173-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Seite "E-Mail & Berichte zur Zusammenarbeit" im Microsoft 365 Defender-Portal](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="0c173-112">Einige der Berichte auf der Seite **"E-Mail & Zusammenarbeitsberichte"** erfordern Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c173-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="0c173-113">Informationen zu diesen Berichten finden Sie unter Anzeigen von [Defender für Office 365-Berichten im Microsoft 365 Defender-Portal.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="0c173-114">Berichte, die sich auf den Nachrichtenfluss beziehen, befinden sich jetzt im Exchange Admin Center (EAC).</span><span class="sxs-lookup"><span data-stu-id="0c173-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="0c173-115">Weitere Informationen zu diesen Berichten finden Sie unter [Nachrichtenflussberichte im neuen Exchange Admin Center.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="0c173-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="0c173-116">Bericht "Kompromittierte Benutzer"</span><span class="sxs-lookup"><span data-stu-id="0c173-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="0c173-117">Dieser Bericht ist in Microsoft 365-Organisationen mit Exchange Online-Postfächern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c173-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="0c173-118">Es ist nicht in eigenständigen Exchange Online Protection (EOP)-Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c173-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="0c173-119">Der Bericht **"Kompromittierte Benutzer"** zeigt die Anzahl der Benutzerkonten an, die innerhalb der letzten 7 Tage als **verdächtig** oder **eingeschränkt** markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0c173-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="0c173-120">Konten in einem dieser Zustände sind problematisch oder sogar kompromittiert.</span><span class="sxs-lookup"><span data-stu-id="0c173-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="0c173-121">Bei häufiger Verwendung können Sie den Bericht verwenden, um Spitzen und sogar Trends in verdächtigen oder eingeschränkten Konten zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="0c173-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="0c173-122">Weitere Informationen zu kompromittierten Benutzern finden Sie unter [Antworten auf ein kompromittiertes E-Mail-Konto.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget "Kompromittierte Benutzer" auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/compromised-users-report-widget.png)

<span data-ttu-id="0c173-124">In der Aggregatansicht werden Daten für die letzten 90 Tage und in der Detailansicht Daten für die letzten 30 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c173-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="0c173-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports.**</span><span class="sxs-lookup"><span data-stu-id="0c173-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0c173-126">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** **kompromittierte Benutzer,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="0c173-127">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="0c173-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="0c173-128">Auf der Seite **"Kompromittierte Benutzer"** können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="0c173-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="0c173-129">**Datum (UTC):** **Startdatum** und **Enddatum.**</span><span class="sxs-lookup"><span data-stu-id="0c173-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="0c173-130">**Aktivität:**</span><span class="sxs-lookup"><span data-stu-id="0c173-130">**Activity**:</span></span>
  - <span data-ttu-id="0c173-131">**Verdächtig:** Das Benutzerkonto hat verdächtige E-Mails gesendet und besteht das Risiko, dass das Senden von E-Mails eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="0c173-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="0c173-132">**Eingeschränkt:** Das Benutzerkonto wurde aufgrund von hochgradig verdächtigen Mustern am Senden von E-Mails gehindert.</span><span class="sxs-lookup"><span data-stu-id="0c173-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="0c173-133">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![Berichtsansicht im Bericht "Kompromittierte Benutzer"](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="0c173-135">In der Detailtabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="0c173-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="0c173-136">**Erstellungszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="0c173-136">**Creation time**</span></span>
- <span data-ttu-id="0c173-137">**Benutzer-ID**</span><span class="sxs-lookup"><span data-stu-id="0c173-137">**User ID**</span></span>
- <span data-ttu-id="0c173-138">**Action**</span><span class="sxs-lookup"><span data-stu-id="0c173-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="0c173-139">Exchange-Transportregelbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-139">Exchange transport rule report</span></span>

<span data-ttu-id="0c173-140">Der **Exchange-Transportregelbericht** zeigt die Auswirkungen von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) auf ein- und ausgehende Nachrichten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="0c173-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="0c173-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports.**</span><span class="sxs-lookup"><span data-stu-id="0c173-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0c173-142">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** die **Exchange-Transportregel,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="0c173-143">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="0c173-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Exchange-Transportregel-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/transport-rule-report-widget.png)

<span data-ttu-id="0c173-145">Auf der Seite **"Exchange-Transportregelbericht"** werden die verfügbaren Diagramme und Daten in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0c173-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="0c173-146">Diagrammstrukturplan nach Richtung</span><span class="sxs-lookup"><span data-stu-id="0c173-146">Chart breakdown by Direction</span></span>

![Richtungsansicht für Exchange-Transportregeln im Exchange-Transportregelbericht](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="0c173-148">Wenn Sie **die Diagrammstrukturstruktur nach Richtung** auswählen, sind die folgenden Diagramme verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="0c173-149">**Anzeigen von Daten nach Exchange-Transportregeln:** Die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von Nachrichtenflussregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="0c173-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="0c173-150">**Anzeigen von Daten nach DLP Exchange-Transportregeln:** Die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von DLP-Nachrichtenflussregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="0c173-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="0c173-151">Die folgenden Informationen werden in der Detailtabelle unterhalb des Diagramms angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0c173-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="0c173-152">**Date**</span><span class="sxs-lookup"><span data-stu-id="0c173-152">**Date**</span></span>
- <span data-ttu-id="0c173-153">**DLP-Richtlinie** (**Nur Daten nach DLP-Exchange-Transportregeln anzeigen)**</span><span class="sxs-lookup"><span data-stu-id="0c173-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="0c173-154">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="0c173-154">**Transport rule**</span></span>
- <span data-ttu-id="0c173-155">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="0c173-155">**Subject**</span></span>
- <span data-ttu-id="0c173-156">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="0c173-156">**Sender address**</span></span>
- <span data-ttu-id="0c173-157">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="0c173-157">**Recipient address**</span></span>
- <span data-ttu-id="0c173-158">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="0c173-158">**Severity**</span></span>
- <span data-ttu-id="0c173-159">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="0c173-159">**Direction**</span></span>

<span data-ttu-id="0c173-160">Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="0c173-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="0c173-161">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-162">**Richtung:** **Ausgehend** und **Eingehend**</span><span class="sxs-lookup"><span data-stu-id="0c173-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="0c173-163">**Schweregrad:** **Hoher,** **mittlerer und** niedriger **Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="0c173-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="0c173-164">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="0c173-165">Diagrammstrukturplan nach Schweregrad</span><span class="sxs-lookup"><span data-stu-id="0c173-165">Chart breakdown by Severity</span></span>

![Schweregradansicht für Exchange-Transportregeln im Exchange-Transportregelbericht](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="0c173-167">Wenn Sie **die Diagrammstrukturstruktur nach Schweregrad** auswählen, sind die folgenden Diagramme verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="0c173-168">**Anzeigen von Daten nach Exchange-Transportregeln:** Die Anzahl der Nachrichten mit **hohem,** **mittlerem und** **mittlerem Schweregrad.**</span><span class="sxs-lookup"><span data-stu-id="0c173-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="0c173-169">Sie legen den Schweregrad als Aktion in der Regel fest (**Überwachen Sie diese Regel mit Schweregrad** oder _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="0c173-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="0c173-170">Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="0c173-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="0c173-171">**Anzeigen von Daten nach DLP Exchange-Transportregeln:** Die Anzahl der Nachrichten mit **hohem Schweregrad,** **mittlerem Schweregrad** und **niedrigem Schweregrad,** die von DLP-Nachrichtenflussregeln betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="0c173-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="0c173-172">Die folgenden Informationen werden in der Detailtabelle unterhalb des Diagramms angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0c173-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="0c173-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="0c173-173">**Date**</span></span>
- <span data-ttu-id="0c173-174">**DLP-Richtlinie** (**Nur Daten nach DLP-Exchange-Transportregeln anzeigen)**</span><span class="sxs-lookup"><span data-stu-id="0c173-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="0c173-175">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="0c173-175">**Transport rule**</span></span>
- <span data-ttu-id="0c173-176">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="0c173-176">**Subject**</span></span>
- <span data-ttu-id="0c173-177">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="0c173-177">**Sender address**</span></span>
- <span data-ttu-id="0c173-178">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="0c173-178">**Recipient address**</span></span>
- <span data-ttu-id="0c173-179">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="0c173-179">**Severity**</span></span>
- <span data-ttu-id="0c173-180">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="0c173-180">**Direction**</span></span>

<span data-ttu-id="0c173-181">Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="0c173-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="0c173-182">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-183">**Richtung:** **Ausgehend** und **Eingehend**</span><span class="sxs-lookup"><span data-stu-id="0c173-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="0c173-184">**Schweregrad:** **Hoher,** **mittlerer und** niedriger **Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="0c173-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="0c173-185">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="0c173-186">Weiterleitungsbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="0c173-187">Der **Weiterleitungsbericht** ist jetzt im EAC verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c173-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="0c173-188">Weitere Informationen finden Sie unter [Bericht über automatisch weitergeleitete Nachrichten im neuen EAC.](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)</span><span class="sxs-lookup"><span data-stu-id="0c173-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="0c173-189">E-Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-189">Mailflow status report</span></span>

<span data-ttu-id="0c173-190">Der **E-Mailflow-Statusbericht** ist ein intelligenter Bericht, der Informationen zu eingehenden und ausgehenden E-Mails, Spamerkennungen, Schadsoftware, als "gut" identifizierten E-Mails und Informationen zu E-Mails anzeigt, die am Edge zugelassen oder blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="0c173-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="0c173-191">Dies ist der einzige Bericht, der Edgeschutzinformationen enthält, und zeigt an, wie viele E-Mails blockiert werden, bevor sie zur Auswertung durch Exchange Online Protection (EOP) in den Dienst zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="0c173-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="0c173-192">Es ist wichtig zu verstehen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="0c173-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="0c173-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports.**</span><span class="sxs-lookup"><span data-stu-id="0c173-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0c173-194">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** die Zusammenfassung des **E-Mail-Flussstatus,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="0c173-195">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="0c173-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Nachrichtenflussstatus-Zusammenfassungs-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="0c173-197">Typansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-197">Type view for the Mailflow status report</span></span>

![Typansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-type-view.png)

<span data-ttu-id="0c173-199">Auf der Seite **E-Mailflow-Statusbericht** ist die Registerkarte Typ standardmäßig ausgewählt. </span><span class="sxs-lookup"><span data-stu-id="0c173-199">On the **Mailflow status report** page, the **Type** tab is selected by default.</span></span> <span data-ttu-id="0c173-200">Standardmäßig enthält diese Ansicht ein Diagramm und eine Detailtabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="0c173-200">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="0c173-201">**Datum (UTC)** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="0c173-201">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="0c173-202">**E-Mail-Richtung:**</span><span class="sxs-lookup"><span data-stu-id="0c173-202">**Mail direction**:</span></span>
  - <span data-ttu-id="0c173-203">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="0c173-203">**Inbound**</span></span>
  - <span data-ttu-id="0c173-204">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="0c173-204">**Outbound**</span></span>
  - <span data-ttu-id="0c173-205">**Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="0c173-205">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="0c173-206">absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von **ein-** und **ausgehend** gezählt)</span><span class="sxs-lookup"><span data-stu-id="0c173-206">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="0c173-207">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="0c173-207">**Type**:</span></span>
  - <span data-ttu-id="0c173-208">**Gute E-Mails**</span><span class="sxs-lookup"><span data-stu-id="0c173-208">**Good mail**</span></span>
  - <span data-ttu-id="0c173-209">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="0c173-209">**Malware**</span></span>
  - <span data-ttu-id="0c173-210">**Spam**</span><span class="sxs-lookup"><span data-stu-id="0c173-210">**Spam**</span></span>
  - <span data-ttu-id="0c173-211">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="0c173-211">**Edge protection**</span></span>
  - <span data-ttu-id="0c173-212">**Regelnachrichten**</span><span class="sxs-lookup"><span data-stu-id="0c173-212">**Rule messages**</span></span>
  - <span data-ttu-id="0c173-213">**Phishing-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="0c173-213">**Phishing email**</span></span>
- <span data-ttu-id="0c173-214">**Domäne:** **Alle**</span><span class="sxs-lookup"><span data-stu-id="0c173-214">**Domain**: **All**</span></span>

<span data-ttu-id="0c173-215">Das Diagramm ist nach den **Type-Werten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="0c173-215">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="0c173-216">Sie können diese Filter ändern, indem Sie auf **"Filter"** klicken.</span><span class="sxs-lookup"><span data-stu-id="0c173-216">You can change these filters by clicking **Filter**.</span></span>

<span data-ttu-id="0c173-217">Die folgenden Informationen werden in der Detailtabelle unterhalb des Diagramms angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0c173-217">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="0c173-218">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="0c173-218">**Direction**</span></span>
- <span data-ttu-id="0c173-219">**Typ**</span><span class="sxs-lookup"><span data-stu-id="0c173-219">**Type**</span></span>
- <span data-ttu-id="0c173-220">**24 Stunden**</span><span class="sxs-lookup"><span data-stu-id="0c173-220">**24 hours**</span></span>
- <span data-ttu-id="0c173-221">**3 Tage**</span><span class="sxs-lookup"><span data-stu-id="0c173-221">**3 days**</span></span>
- <span data-ttu-id="0c173-222">**7 Tage**</span><span class="sxs-lookup"><span data-stu-id="0c173-222">**7 days**</span></span>
- <span data-ttu-id="0c173-223">**15 Tage**</span><span class="sxs-lookup"><span data-stu-id="0c173-223">**15 days**</span></span>
- <span data-ttu-id="0c173-224">**30 Tage**</span><span class="sxs-lookup"><span data-stu-id="0c173-224">**30 days**</span></span>

<span data-ttu-id="0c173-225">Wenn Sie auf **"Kategorie auswählen"** klicken, um weitere Details zu erhalten, können Sie aus den folgenden Werten auswählen:</span><span class="sxs-lookup"><span data-stu-id="0c173-225">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="0c173-226">**Phishing-E-Mail:** Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="0c173-226">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="0c173-227">**Schadsoftware in E-Mails:** Diese Auswahl führt Sie zum [Bedrohungsschutzstatusbericht.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="0c173-227">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="0c173-228">**Spamerkennungen:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="0c173-228">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="0c173-229">**Edge blockierter Spam:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="0c173-229">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="0c173-230">Exportieren aus der Typansicht</span><span class="sxs-lookup"><span data-stu-id="0c173-230">Export from Type view</span></span>

<span data-ttu-id="0c173-231">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="0c173-231">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="0c173-232">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="0c173-232">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="0c173-233">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="0c173-233">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0c173-234">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="0c173-234">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="0c173-235">Richtungsansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-235">Direction view for the Mailflow status report</span></span>

![Richtungsansicht im E-Mailflow-Statusbericht](../../media/mail-flow-status-report-direction-view.png)

<span data-ttu-id="0c173-237">Wenn Sie auf die Registerkarte **"Richtung"** klicken, werden die gleichen Standardfilter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c173-237">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="0c173-238">Das Diagramm ist nach **Richtungswerten** organisiert.</span><span class="sxs-lookup"><span data-stu-id="0c173-238">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="0c173-239">Sie können diese Filter ändern, indem Sie auf **"Filter"** klicken.</span><span class="sxs-lookup"><span data-stu-id="0c173-239">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="0c173-240">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c173-240">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="0c173-241">Die Detailtabelle enthält dieselben Informationen aus der **Typansicht.**</span><span class="sxs-lookup"><span data-stu-id="0c173-241">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="0c173-242">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span><span class="sxs-lookup"><span data-stu-id="0c173-242">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="0c173-243">Exportieren aus der Richtungsansicht</span><span class="sxs-lookup"><span data-stu-id="0c173-243">Export from Direction view</span></span>

<span data-ttu-id="0c173-244">Für die Detailansicht können Sie nur Daten für einen Tag exportieren.</span><span class="sxs-lookup"><span data-stu-id="0c173-244">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="0c173-245">Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="0c173-245">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="0c173-246">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="0c173-246">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0c173-247">Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="0c173-247">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="0c173-248">Trichteransicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="0c173-249">Die **Trichteransicht** zeigt Ihnen, wie die E-Mail-Bedrohungsschutzfeatures von Microsoft eingehende und ausgehende E-Mails in Ihrer Organisation filtern.</span><span class="sxs-lookup"><span data-stu-id="0c173-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="0c173-250">Es enthält Details zur Gesamtzahl der E-Mails und dazu, wie sich die konfigurierten Bedrohungsschutzfeatures, einschließlich Edgeschutz, Antischadsoftware, Antiphishing, Antispam und Antispoofing, auf diese Anzahl auswirken.</span><span class="sxs-lookup"><span data-stu-id="0c173-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

![Trichteransicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-funnel-view.png)

<span data-ttu-id="0c173-252">Wenn Sie auf die Registerkarte **"Trichter"** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Detailtabelle, die mit den folgenden Filtern konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="0c173-252">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="0c173-253">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="0c173-253">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="0c173-254">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="0c173-254">**Direction**:</span></span>
  - <span data-ttu-id="0c173-255">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="0c173-255">**Inbound**</span></span>
  - <span data-ttu-id="0c173-256">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="0c173-256">**Outbound**</span></span>
  - <span data-ttu-id="0c173-257">**Organisationsintern:** Diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden; d. h. Absender abc@domain.com sendet an Empfänger xyz@domain.com (separat von Ein- und Ausgehend gezählt).</span><span class="sxs-lookup"><span data-stu-id="0c173-257">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="0c173-258">Die Aggregatansicht und die Detailtabellenansicht ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="0c173-258">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="0c173-259">Sie können diese Filter ändern, indem Sie auf **"Filter"** klicken.</span><span class="sxs-lookup"><span data-stu-id="0c173-259">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="0c173-260">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c173-260">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="0c173-261">Dieses Diagramm zeigt die E-Mail-Anzahl nach:</span><span class="sxs-lookup"><span data-stu-id="0c173-261">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="0c173-262">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="0c173-262">**Total email**</span></span>
- <span data-ttu-id="0c173-263">**E-Mail nach Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="0c173-263">**Email after edge protection**</span></span>
- <span data-ttu-id="0c173-264">**E-Mail nach Transportregel** (Nachrichtenflussregel)</span><span class="sxs-lookup"><span data-stu-id="0c173-264">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="0c173-265">**E-Mail nach Antischadsoftware, Dateireputation, Dateitypblockierung**</span><span class="sxs-lookup"><span data-stu-id="0c173-265">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="0c173-266">**E-Mail nach Antiphishing, URL-Reputation, Markenidentitätswechsel, Antispoofing**</span><span class="sxs-lookup"><span data-stu-id="0c173-266">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="0c173-267">**E-Mails nach Antispam, Massenfilterung von E-Mails**</span><span class="sxs-lookup"><span data-stu-id="0c173-267">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="0c173-268">**E-Mail nach Benutzer- und Domänenidentitätswechsel**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c173-268">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="0c173-269">**E-Mail nach Datei- und URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c173-269">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="0c173-270">**E-Mails, die nach der Zustellung als gutartig erkannt wurden (URL-Click-Time-Schutz)**</span><span class="sxs-lookup"><span data-stu-id="0c173-270">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="0c173-271"><sup>\*</sup>Nur Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="0c173-271"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="0c173-272">Um die von EOP oder Defender gefilterte E-Mail für Office 365 separat anzuzeigen, klicken Sie auf den Wert in der Diagrammlegende.</span><span class="sxs-lookup"><span data-stu-id="0c173-272">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="0c173-273">Die Detailtabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="0c173-273">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="0c173-274">**Date**</span><span class="sxs-lookup"><span data-stu-id="0c173-274">**Date**</span></span>
- <span data-ttu-id="0c173-275">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="0c173-275">**Total email**</span></span>
- <span data-ttu-id="0c173-276">**Edgeschutz**</span><span class="sxs-lookup"><span data-stu-id="0c173-276">**Edge protection**</span></span>
- <span data-ttu-id="0c173-277">**Antischadsoftware, Dateireputation, Dateitypblock:**</span><span class="sxs-lookup"><span data-stu-id="0c173-277">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="0c173-278">**Dateizuruf:** Nachrichten, die aufgrund der Identifizierung einer angefügten Datei von anderen Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="0c173-278">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="0c173-279">**Dateitypblock:** Nachrichten, die aufgrund des typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="0c173-279">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="0c173-280">**Antiphishing, URL-Zuverlässigkeit, Markenidentitätswechsel, Antispoofing:**</span><span class="sxs-lookup"><span data-stu-id="0c173-280">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="0c173-281">**URL-Zuverlässigkeit:** Nachrichten, die aufgrund der Identifizierung der URL von anderen Microsoft-Kunden gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="0c173-281">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="0c173-282">**Markenidentitätswechsel:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die von bekannten Absendern als Absender imitiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0c173-282">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="0c173-283">**Antispoofing:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die versucht, eine Domäne zu spoofen, zu der der Empfänger gehört, oder einer Domäne, die der Absender der Nachricht nicht besitzt.</span><span class="sxs-lookup"><span data-stu-id="0c173-283">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="0c173-284">**Antispam, Massen-E-Mail-Filterung:**</span><span class="sxs-lookup"><span data-stu-id="0c173-284">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="0c173-285">**Massen-E-Mail-Filterung:** Nachrichten, die basierend auf dem BCL-Schwellenwert (Bulk Complain Level) in einer Antispamrichtlinie gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="0c173-285">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="0c173-286">**Benutzer- und Domänenidentitätswechsel (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="0c173-286">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="0c173-287">**Benutzeridentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, einen Benutzer (Nachrichtensender) zu imitieren, der in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0c173-287">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="0c173-288">**Domänenidentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, eine Domäne zu imitieren, die in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0c173-288">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="0c173-289">**Datei- und URL-Detonation (Defender für Office 365):**</span><span class="sxs-lookup"><span data-stu-id="0c173-289">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="0c173-290">**Dateidetonation:** Nachrichten, die nach einer Safe Anlagenrichtlinie gefiltert sind.</span><span class="sxs-lookup"><span data-stu-id="0c173-290">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="0c173-291">**URL-Detonation:** Nachricht, gefiltert nach einer Safe-Verknüpfungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="0c173-291">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="0c173-292">**Schutz nach der Zustellung und ZAP (ATP) oder ZAP (EOP):** Automatische Nullstunde-Bereinigung (ZAP) für Schadsoftware, Spam und Phishing.</span><span class="sxs-lookup"><span data-stu-id="0c173-292">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="0c173-293">Wenn Sie eine Zeile in der Detailtabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c173-293">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="0c173-294">Exportieren aus der Trichteransicht</span><span class="sxs-lookup"><span data-stu-id="0c173-294">Export from Funnel view</span></span>

<span data-ttu-id="0c173-295">Nachdem Sie unter **"Optionen"** auf **"Exportieren"** geklickt haben, können Sie einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="0c173-295">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="0c173-296">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="0c173-296">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="0c173-297">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="0c173-297">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="0c173-298">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .**</span><span class="sxs-lookup"><span data-stu-id="0c173-298">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="0c173-299">Daten für die aktuellen Filter werden in eine .csv Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="0c173-299">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="0c173-300">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="0c173-300">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0c173-301">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="0c173-301">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="0c173-302">Tech-Ansicht für den Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="0c173-303">Die **Tech-Ansicht** ähnelt der **Trichteransicht** und bietet detailliertere Details für die konfigurierten Funktionen zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="0c173-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="0c173-304">Im Diagramm können Sie sehen, wie Nachrichten in den verschiedenen Phasen des Bedrohungsschutzes kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0c173-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="0c173-305">Wenn Sie standardmäßig auf die Registerkarte **"Tech-Ansicht"** klicken, enthält diese Ansicht ein Diagramm und eine Detailtabelle, die mit den folgenden Filtern konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="0c173-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="0c173-306">**Datum:** Die letzten 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="0c173-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="0c173-307">**Richtung:**</span><span class="sxs-lookup"><span data-stu-id="0c173-307">**Direction**:</span></span>
  - <span data-ttu-id="0c173-308">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="0c173-308">**Inbound**</span></span>
  - <span data-ttu-id="0c173-309">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="0c173-309">**Outbound**</span></span>
  - <span data-ttu-id="0c173-310">**Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h.</span><span class="sxs-lookup"><span data-stu-id="0c173-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="0c173-311">absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von eingehenden und ausgehenden Zählungen)</span><span class="sxs-lookup"><span data-stu-id="0c173-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="0c173-312">Die Aggregatansicht und die Detailtabellenansicht ermöglichen eine Filterung von 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="0c173-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="0c173-313">Sie können diese Filter ändern, indem Sie auf **"Filter"** klicken.</span><span class="sxs-lookup"><span data-stu-id="0c173-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="0c173-314">Es werden dieselben Filter aus der **Typansicht** verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c173-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="0c173-315">Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:</span><span class="sxs-lookup"><span data-stu-id="0c173-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="0c173-316">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="0c173-316">**Total email**</span></span>
- <span data-ttu-id="0c173-317">**Edge zulassen** und **Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="0c173-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="0c173-318">**Transportregel zulassen** und **Transportregel gefiltert** (Nachrichtenflussregeln)</span><span class="sxs-lookup"><span data-stu-id="0c173-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="0c173-319">**Keine Schadsoftware,** **Safe Erkennung von Anlagen** und Erkennung von <sup>\*</sup> **Antischadsoftwaremodulen**</span><span class="sxs-lookup"><span data-stu-id="0c173-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="0c173-320">**Keine Phishing-,** **DMARC-Fehler,** **Identitätswechselerkennung,** <sup>\*</sup> **Spooferkennung** und **Phishing-Erkennung**</span><span class="sxs-lookup"><span data-stu-id="0c173-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="0c173-321">**Keine Erkennung mit URL-Detonation** und **URL-Detonationserkennung**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c173-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="0c173-322">**Keine Spam-** und  **Spamnachrichten**</span><span class="sxs-lookup"><span data-stu-id="0c173-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="0c173-323">**Nicht böswillige E-Mails,** **Safe-Links-Erkennung** <sup>\*</sup> und **ZAP**</span><span class="sxs-lookup"><span data-stu-id="0c173-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="0c173-324"><sup>\*</sup>Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="0c173-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="0c173-325">Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, können Sie die Anzahl der Nachrichten in dieser Kategorie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0c173-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="0c173-326">Die Detailtabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="0c173-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="0c173-327">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="0c173-327">**Date (UTC)**</span></span>
- <span data-ttu-id="0c173-328">**E-Mail-Gesamtanzahl**</span><span class="sxs-lookup"><span data-stu-id="0c173-328">**Total email**</span></span>
- <span data-ttu-id="0c173-329">**Edge gefiltert**</span><span class="sxs-lookup"><span data-stu-id="0c173-329">**Edge filtered**</span></span>
- <span data-ttu-id="0c173-330">**Regelnachrichten:** Nachrichten, die aufgrund von Nachrichtenflussregeln gefiltert wurden (auch als Transportregeln bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="0c173-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="0c173-331">**Antischadsoftwaremodul**, **Safe** <sup>\*</sup> Anlagen:</span><span class="sxs-lookup"><span data-stu-id="0c173-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="0c173-332">**DMARC, Identitätswechsel,** <sup>\*</sup> **Spoofing**, **Phishing gefiltert:**</span><span class="sxs-lookup"><span data-stu-id="0c173-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="0c173-333">**DMARC:** Nachrichten, die aufgrund eines Fehlers bei der DMARC-Authentifizierungsprüfung gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="0c173-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="0c173-334">**ERKENNUNG DER URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c173-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="0c173-335">**Antispam gefiltert**</span><span class="sxs-lookup"><span data-stu-id="0c173-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="0c173-336">**ZAP entfernt**</span><span class="sxs-lookup"><span data-stu-id="0c173-336">**ZAP removed**</span></span>
- <span data-ttu-id="0c173-337">**Erkennung durch Safe Links**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c173-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="0c173-338"><sup>\*</sup>Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="0c173-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="0c173-339">Wenn Sie eine Zeile in der Detailtabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c173-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="0c173-340">Exportieren aus der Tech-Ansicht</span><span class="sxs-lookup"><span data-stu-id="0c173-340">Export from Tech view</span></span>

<span data-ttu-id="0c173-341">Wenn Sie auf **"Exportieren"** klicken, können Sie unter **"Optionen"** einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="0c173-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="0c173-342">**Zusammenfassung (mit Daten für die letzten 90 Tage)**</span><span class="sxs-lookup"><span data-stu-id="0c173-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="0c173-343">**Details (mit Daten für die letzten 30 Tage)**</span><span class="sxs-lookup"><span data-stu-id="0c173-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="0c173-344">Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .**</span><span class="sxs-lookup"><span data-stu-id="0c173-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="0c173-345">Daten für die aktuellen Filter werden in eine .csv Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="0c173-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="0c173-346">Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="0c173-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0c173-347">Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="0c173-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Tech-Ansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="0c173-349">Bericht über Schadsoftwareerkennungen</span><span class="sxs-lookup"><span data-stu-id="0c173-349">Malware detections report</span></span>

<span data-ttu-id="0c173-350">Der Bericht über **Schadsoftwareerkennungen** enthält Informationen zu Schadsoftwareerkennungen in eingehenden und ausgehenden E-Mail-Nachrichten (von Exchange Online Protection oder EOP erkannte Schadsoftware).</span><span class="sxs-lookup"><span data-stu-id="0c173-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="0c173-351">Weitere Informationen zum Schutz vor Schadsoftware in EOP finden Sie unter [Antischadsoftwareschutz in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="0c173-352">Der Aggregatansichtsfilter lässt 90 Tage zu, während der Detailtabellenfilter nur 10 Tage zulässt.</span><span class="sxs-lookup"><span data-stu-id="0c173-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="0c173-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="0c173-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0c173-354">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** nach Schadsoftware, die **in E-Mails erkannt wurde,** und klicken Sie dann auf **Details anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="0c173-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="0c173-355">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="0c173-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Schadsoftwareerkennungen im E-Mail-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/malware-detections-widget.png)

<span data-ttu-id="0c173-357">Auf der Berichtsseite **für Schadsoftwareerkennungen** können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="0c173-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="0c173-358">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-359">**Richtung:** **Ein-** und **Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="0c173-359">**Direction**: **Inbound** and **Outbound**</span></span>

![Berichtsansicht im Bericht "Schadsoftwareerkennung in E-Mail"](../../media/malware-detections-report-view.png)

<span data-ttu-id="0c173-361">In der Detailtabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="0c173-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="0c173-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="0c173-362">**Date**</span></span>
- <span data-ttu-id="0c173-363">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="0c173-363">**Sender address**</span></span>
- <span data-ttu-id="0c173-364">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="0c173-364">**Recipient address**</span></span>
- <span data-ttu-id="0c173-365">**Nachrichten-ID:** Verfügbar im **Nachrichten-ID-Kopfzeilenfeld** im Nachrichtenkopf und sollte eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="0c173-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="0c173-366">Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (beachten Sie die spitzen Klammern).</span><span class="sxs-lookup"><span data-stu-id="0c173-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="0c173-367">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="0c173-367">**Subject**</span></span>
- <span data-ttu-id="0c173-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="0c173-368">**Filename**</span></span>
- <span data-ttu-id="0c173-369">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="0c173-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="0c173-370">E-Mail-Latenzbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-370">Mail latency report</span></span>

<span data-ttu-id="0c173-371">Der **E-Mail-Latenzbericht** in Defender für Office 365 enthält Informationen zur E-Mail-Zustellungs- und Detonationslatenz in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="0c173-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="0c173-372">Weitere Informationen finden Sie im [E-Mail-Latenzbericht.](view-reports-for-mdo.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="0c173-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="0c173-373">Spamerkennungsbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="0c173-374">Der **Spamerkennungsbericht** wird schließlich entfernt.</span><span class="sxs-lookup"><span data-stu-id="0c173-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="0c173-375">Die gleichen Informationen sind im [Bedrohungsschutzstatusbericht](#threat-protection-status-report)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c173-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="0c173-376">Bericht über Spooferkennungen</span><span class="sxs-lookup"><span data-stu-id="0c173-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="0c173-377">Der verbesserte Bericht über Spooferkennungen, wie in diesem Artikel beschrieben, befindet sich in der Vorschau, kann geändert werden und ist nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c173-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="0c173-378">Die ältere Version des Berichts zeigt nur **gute E-Mails** und **"Als Spam abgefangen"** an.</span><span class="sxs-lookup"><span data-stu-id="0c173-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="0c173-379">Der Bericht **"Spooferkennungen"** enthält Informationen zu Nachrichten, die aufgrund von Spoofing blockiert oder zugelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="0c173-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="0c173-380">Weitere Informationen zum Spoofing finden Sie unter [Antispoofingschutz in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="0c173-381">Die Aggregatansicht des Berichts lässt 45 Tage Filterung <sup>\*</sup> zu, während die Detailansicht nur zehn Tage Filterung zulässt.</span><span class="sxs-lookup"><span data-stu-id="0c173-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="0c173-382"><sup>\*</sup> Schließlich können Sie die Filterung bis zu 90 Tage verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c173-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="0c173-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="0c173-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0c173-384">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** **nach Spooferkennungen,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="0c173-385">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="0c173-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Spooferkennungs-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/spoof-detections-widget.png)

<span data-ttu-id="0c173-387">Das Diagramm zeigt die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="0c173-387">The chart shows the following information:</span></span>

- <span data-ttu-id="0c173-388">**bestehen**</span><span class="sxs-lookup"><span data-stu-id="0c173-388">**Pass**</span></span>
- <span data-ttu-id="0c173-389">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="0c173-389">**Fail**</span></span>
- <span data-ttu-id="0c173-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="0c173-390">**SoftPass**</span></span>
- <span data-ttu-id="0c173-391">**Keine**</span><span class="sxs-lookup"><span data-stu-id="0c173-391">**None**</span></span>
- <span data-ttu-id="0c173-392">**Other**</span><span class="sxs-lookup"><span data-stu-id="0c173-392">**Other**</span></span>

<span data-ttu-id="0c173-393">Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, können Sie sehen, wie viele gefälschte Nachrichten erkannt wurden und warum.</span><span class="sxs-lookup"><span data-stu-id="0c173-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="0c173-394">Auf der Seite **"Spoof-E-Mail-Bericht"** können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="0c173-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="0c173-395">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-396">**Ergebnis:**</span><span class="sxs-lookup"><span data-stu-id="0c173-396">**Result**:</span></span>
  - <span data-ttu-id="0c173-397">**bestehen**</span><span class="sxs-lookup"><span data-stu-id="0c173-397">**Pass**</span></span>
  - <span data-ttu-id="0c173-398">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="0c173-398">**Fail**</span></span>
  - <span data-ttu-id="0c173-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="0c173-399">**SoftPass**</span></span>
  - <span data-ttu-id="0c173-400">**Keine**</span><span class="sxs-lookup"><span data-stu-id="0c173-400">**None**</span></span>
  - <span data-ttu-id="0c173-401">**Other**</span><span class="sxs-lookup"><span data-stu-id="0c173-401">**Other**</span></span>
- <span data-ttu-id="0c173-402">**Spooftyp:** **Intern** und **extern**</span><span class="sxs-lookup"><span data-stu-id="0c173-402">**Spoof type**: **Internal** and **External**</span></span>

![Seite "Spoof-E-Mail-Bericht" im Microsoft 365 Defender-Portal](../../media/spoof-detections-report-page.png)

<span data-ttu-id="0c173-404">In der Detailtabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="0c173-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="0c173-405">**Date**</span><span class="sxs-lookup"><span data-stu-id="0c173-405">**Date**</span></span>
- <span data-ttu-id="0c173-406">**Gefälschter Benutzer**</span><span class="sxs-lookup"><span data-stu-id="0c173-406">**Spoofed user**</span></span>
- <span data-ttu-id="0c173-407">**Senden der Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="0c173-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="0c173-408">**Spooftyp**</span><span class="sxs-lookup"><span data-stu-id="0c173-408">**Spoof type**</span></span>
- <span data-ttu-id="0c173-409">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="0c173-409">**Result**</span></span>
- <span data-ttu-id="0c173-410">**Ergebniscode**</span><span class="sxs-lookup"><span data-stu-id="0c173-410">**Result code**</span></span>
- <span data-ttu-id="0c173-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="0c173-411">**SPF**</span></span>
- <span data-ttu-id="0c173-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="0c173-412">**DKIM**</span></span>
- <span data-ttu-id="0c173-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="0c173-413">**DMARC**</span></span>
- <span data-ttu-id="0c173-414">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="0c173-414">**Message count**</span></span>

<span data-ttu-id="0c173-415">Weitere Informationen zu Ergebniscodes für die zusammengesetzte Authentifizierung finden Sie unter [Antispam-Nachrichtenkopfzeilen in Microsoft 365.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="0c173-416">Übermittlungsbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-416">Submissions report</span></span>

<span data-ttu-id="0c173-417">Der **Bericht "Übermittlungen"** enthält Informationen zu Elementen, die Administratoren microsoft zur Analyse gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="0c173-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="0c173-418">Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="0c173-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="0c173-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0c173-420">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** **nach Übermittlungen,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="0c173-421">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/adminSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="0c173-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="0c173-422">Wenn Sie im Microsoft 365 Defender Portal zu [Administratorübermittlungen](admin-submission.md)wechseln möchten, klicken Sie auf **"Zu Übermittlungen wechseln".**</span><span class="sxs-lookup"><span data-stu-id="0c173-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Übermittlungs-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/submissions-report-widget.png)

<span data-ttu-id="0c173-424">Das Diagramm zeigt die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="0c173-424">The chart shows the following information:</span></span>

- <span data-ttu-id="0c173-425">**Ausstehend**</span><span class="sxs-lookup"><span data-stu-id="0c173-425">**Pending**</span></span>
- <span data-ttu-id="0c173-426">**Abgeschlossen**</span><span class="sxs-lookup"><span data-stu-id="0c173-426">**Completed**</span></span>

<span data-ttu-id="0c173-427">Auf der Seite **"Übermittlungen"** können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="0c173-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="0c173-428">**Gemeldetes Datum**: **Startzeit** und **Endzeit**</span><span class="sxs-lookup"><span data-stu-id="0c173-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="0c173-429">**Übermittlungstyp:**</span><span class="sxs-lookup"><span data-stu-id="0c173-429">**Submission type**:</span></span>
  - <span data-ttu-id="0c173-430">**E-Mail**</span><span class="sxs-lookup"><span data-stu-id="0c173-430">**Email**</span></span>
  - <span data-ttu-id="0c173-431">**URL**</span><span class="sxs-lookup"><span data-stu-id="0c173-431">**URL**</span></span>
  - <span data-ttu-id="0c173-432">**Datei**</span><span class="sxs-lookup"><span data-stu-id="0c173-432">**File**</span></span>
- <span data-ttu-id="0c173-433">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="0c173-433">**Submission ID**</span></span>
- <span data-ttu-id="0c173-434">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="0c173-434">**Network Message ID**</span></span>
- <span data-ttu-id="0c173-435">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0c173-435">**Sender**</span></span>
- <span data-ttu-id="0c173-436">**Name**</span><span class="sxs-lookup"><span data-stu-id="0c173-436">**Name**</span></span>
- <span data-ttu-id="0c173-437">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="0c173-437">**Submitted by**</span></span>
- <span data-ttu-id="0c173-438">**Grund für die Übermittlung:**</span><span class="sxs-lookup"><span data-stu-id="0c173-438">**Reason for submitting**:</span></span>
  - <span data-ttu-id="0c173-439">**Kein Junk**</span><span class="sxs-lookup"><span data-stu-id="0c173-439">**Not junk**</span></span>
  - <span data-ttu-id="0c173-440">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="0c173-440">**Phish**</span></span>
  - <span data-ttu-id="0c173-441">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="0c173-441">**Malware**</span></span>
  - <span data-ttu-id="0c173-442">**Spam**</span><span class="sxs-lookup"><span data-stu-id="0c173-442">**Spam**</span></span>
- <span data-ttu-id="0c173-443">**Status des erneuten Scannens:**</span><span class="sxs-lookup"><span data-stu-id="0c173-443">**Rescan status**:</span></span>
  - <span data-ttu-id="0c173-444">**Ausstehend**</span><span class="sxs-lookup"><span data-stu-id="0c173-444">**Pending**</span></span>
  - <span data-ttu-id="0c173-445">**Abgeschlossen**</span><span class="sxs-lookup"><span data-stu-id="0c173-445">**Completed**</span></span>

<span data-ttu-id="0c173-446">Die Detailtabelle unterhalb des Diagramms zeigt die gleichen Informationen und verfügt über die gleichen **Gruppen-** oder **Anpassungsspaltenoptionen** wie auf der Registerkarte **"Für Analyse übermittelt"** unter **"E-Mail &** \> **Übermittlungen zur** Zusammenarbeit".</span><span class="sxs-lookup"><span data-stu-id="0c173-446">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="0c173-447">Weitere Informationen finden Sie unter [Anzeigen von Administratorübermittlungen an Microsoft.](admin-submission.md#view-admin-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="0c173-447">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Übermittlungsberichtsseite im Microsoft 365 Defender Portal](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="0c173-449">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-449">Threat protection status report</span></span>

<span data-ttu-id="0c173-450">Der **Statusbericht zum Bedrohungsschutz** ist sowohl in EOP als auch in Defender für Office 365 verfügbar. Die Berichte enthalten jedoch unterschiedliche Daten.</span><span class="sxs-lookup"><span data-stu-id="0c173-450">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="0c173-451">EOP-Kunden können z. B. Informationen zu schadsoftware anzeigen, die in E-Mails erkannt wurde, aber keine Informationen zu schädlichen Dateien, die von [Safe Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c173-451">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="0c173-452">Der Bericht enthält die Anzahl der E-Mail-Nachrichten mit schädlichen Inhalten, z. B. Dateien oder Websiteadressen (URLs), die vom Antischadsoftwaremodul blockiert wurden, Zap [(Zero-Hour Auto Purge)](zero-hour-auto-purge.md)und Defender für Office 365 Features wie [Safe Links,](safe-links.md)Safe Anlagen und [Identitätswechselschutzfeatures in Antiphishingrichtlinien.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) [](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-452">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="0c173-453">Anhand dieser Informationen können Sie Trends erkennen oder ermitteln, ob Die Unternehmensrichtlinien angepasst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0c173-453">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="0c173-454">**Hinweis:** Es ist wichtig zu wissen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="0c173-454">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="0c173-455">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="0c173-455">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0c173-456">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** den **Status des Bedrohungsschutzes,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-456">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="0c173-457">Um direkt zum Bericht zu wechseln, öffnen Sie eine der folgenden URLs:</span><span class="sxs-lookup"><span data-stu-id="0c173-457">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="0c173-458">Defender für Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="0c173-458">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="0c173-459">Eop: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="0c173-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Bedrohungsschutzstatus-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="0c173-461">Standardmäßig werden im Diagramm Daten für die letzten 7 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c173-461">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="0c173-462">Wenn Sie auf der Seite **"Statusbericht zum Bedrohungsschutz"** auf **"Filtern"** klicken, können Sie einen Zeitraum von 90 Tagen auswählen (Testabonnements sind möglicherweise auf 30 Tage begrenzt).</span><span class="sxs-lookup"><span data-stu-id="0c173-462">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="0c173-463">Die Detailtabelle ermöglicht das Filtern für 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="0c173-463">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="0c173-464">Die verfügbaren Ansichten werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0c173-464">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="0c173-465">Anzeigen von Daten nach Übersicht</span><span class="sxs-lookup"><span data-stu-id="0c173-465">View data by Overview</span></span>

![Übersichtsansicht im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="0c173-467">In der Ansicht **"Ansichtsdaten nach Übersicht"** werden die folgenden Erkennungsinformationen im Diagramm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0c173-467">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="0c173-468">**E-Mail-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="0c173-468">**Email malware**</span></span>
- <span data-ttu-id="0c173-469">**E-Mail-Phishing**</span><span class="sxs-lookup"><span data-stu-id="0c173-469">**Email phish**</span></span>
- <span data-ttu-id="0c173-470">**Inhalts-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="0c173-470">**Content malware**</span></span>

<span data-ttu-id="0c173-471">Unterhalb des Diagramms ist keine Detailtabelle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c173-471">No details table is available below the chart.</span></span>

<span data-ttu-id="0c173-472">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-472">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0c173-473">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-473">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-474">**Erkennung:** **E-Mail-Schadsoftware,** **E-Mail-Phishing** oder **Inhalts-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="0c173-474">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="0c173-475">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="0c173-475">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0c173-476">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="0c173-476">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0c173-477">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-477">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0c173-478">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="0c173-478">**Direction**</span></span>
- <span data-ttu-id="0c173-479">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="0c173-479">**Domain**</span></span>
- <span data-ttu-id="0c173-480">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="0c173-480">**Policy type**</span></span>

<span data-ttu-id="0c173-481">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-481">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="0c173-482">Anzeigen von Daten nach E-Mail-Phishing \> und Diagrammstrukturplan nach Erkennungstechnologie</span><span class="sxs-lookup"><span data-stu-id="0c173-482">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Ansicht der Erkennungstechnologie für Phishing-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="0c173-484">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span><span class="sxs-lookup"><span data-stu-id="0c173-484">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="0c173-485">**URL malicious reputation:** <sup>\*</sup> Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span><span class="sxs-lookup"><span data-stu-id="0c173-485">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="0c173-486">**Erweiterter Filter:** Phishingsignale basierend auf maschinellem Lernen.</span><span class="sxs-lookup"><span data-stu-id="0c173-486">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="0c173-487">**Allgemeiner Filter:** Phishingsignale basierend auf Analystenregeln.</span><span class="sxs-lookup"><span data-stu-id="0c173-487">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="0c173-488">**Organisationsinternes Spoofing:** Der Absender versucht, die Empfängerdomäne zu spoofen.</span><span class="sxs-lookup"><span data-stu-id="0c173-488">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="0c173-489">**Spoofing externer Domäne:** Der Absender versucht, eine andere Domäne zu spoofen.</span><span class="sxs-lookup"><span data-stu-id="0c173-489">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="0c173-490">**Spoofing von DMARC:** DMARC-Authentifizierungsfehler bei Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="0c173-490">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="0c173-491">**Identitätswechselmarke:** Identitätswechsel bekannter Marken basierend auf Absendern.</span><span class="sxs-lookup"><span data-stu-id="0c173-491">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="0c173-492">**Erkennung durch gemischte Analysen**</span><span class="sxs-lookup"><span data-stu-id="0c173-492">**Mixed analysis detection**</span></span>
- <span data-ttu-id="0c173-493">**Datei-Reputation**</span><span class="sxs-lookup"><span data-stu-id="0c173-493">**File reputation**</span></span>
- <span data-ttu-id="0c173-494">**Fingerabdruckübereinstimmung**</span><span class="sxs-lookup"><span data-stu-id="0c173-494">**Fingerprint matching**</span></span>
- <span data-ttu-id="0c173-495">**Zuverlässigkeit der URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c173-495">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="0c173-496">**URL-Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c173-496">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="0c173-497">**Identitätswechselbenutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c173-497">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="0c173-498">**Identitätswechseldomäne:** <sup>\*</sup> Identitätswechsel von Domänen, die der Kunde besitzt oder definiert.</span><span class="sxs-lookup"><span data-stu-id="0c173-498">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="0c173-499">**Identitätswechsel bei der Postfachintelligenz:** <sup>\*</sup> Identitätswechsel von Benutzern, die vom Administrator definiert oder durch die Postfachintelligenz gelernt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c173-499">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="0c173-500">**Dateidetonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c173-500">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="0c173-501">**Kampagne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c173-501">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="0c173-502">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-502">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0c173-503">**Date**</span><span class="sxs-lookup"><span data-stu-id="0c173-503">**Date**</span></span>
- <span data-ttu-id="0c173-504">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="0c173-504">**Subject**</span></span>
- <span data-ttu-id="0c173-505">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0c173-505">**Sender**</span></span>
- <span data-ttu-id="0c173-506">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="0c173-506">**Recipients**</span></span>
- <span data-ttu-id="0c173-507">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="0c173-507">**Detected by**</span></span>
- <span data-ttu-id="0c173-508">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="0c173-508">**Delivery Status**</span></span>
- <span data-ttu-id="0c173-509">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="0c173-509">**Source of Compromise**</span></span>
- <span data-ttu-id="0c173-510">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0c173-510">**Tags**</span></span>

<span data-ttu-id="0c173-511">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-511">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0c173-512">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-512">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-513">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="0c173-513">**Detection**</span></span>
- <span data-ttu-id="0c173-514">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="0c173-514">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0c173-515">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="0c173-515">**Direction**</span></span>
- <span data-ttu-id="0c173-516">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="0c173-516">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0c173-517">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-517">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0c173-518">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="0c173-518">**Domain**</span></span>
- <span data-ttu-id="0c173-519">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="0c173-519">**Policy type**</span></span>
- <span data-ttu-id="0c173-520">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="0c173-520">**Policy name** (details table only)</span></span>
- <span data-ttu-id="0c173-521">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="0c173-521">**Recipients**</span></span>

<span data-ttu-id="0c173-522">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-522">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="0c173-523">Anzeigen von Daten nach \> E-Mail-Schadsoftware und Diagrammstrukturplan nach Erkennungstechnologie</span><span class="sxs-lookup"><span data-stu-id="0c173-523">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Ansicht der Erkennungstechnologie für Schadsoftware im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="0c173-525">In der **Ansicht Ansichtsdaten nach E-Mail-Schadsoftware \>** und **Diagrammstrukturplan nach Erkennungstechnologie** werden die folgenden Informationen im Diagramm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0c173-525">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="0c173-526">**Dateidetonation:** <sup>\*</sup> Erkennung durch Safe Anlagen.</span><span class="sxs-lookup"><span data-stu-id="0c173-526">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="0c173-527">**Zuverlässigkeit der Dateidetonation:** <sup>\*</sup> Alle bösartigen Dateireputationen, die von Defender für Office 365 Detonationen generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0c173-527">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="0c173-528">**Datei-Reputation**</span><span class="sxs-lookup"><span data-stu-id="0c173-528">**File reputation**</span></span>
- <span data-ttu-id="0c173-529">**Antischadsoftwaremodul:** <sup>\*</sup> Erkennung von Antischadsoftwaremodulen.</span><span class="sxs-lookup"><span data-stu-id="0c173-529">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="0c173-530">Dateitypblock für **Antischadsoftwarerichtlinie:** Hierbei handelt es sich um E-Mail-Nachrichten, die aufgrund des in der Nachricht identifizierten Typs bösartiger Dateien herausgefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="0c173-530">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="0c173-531">**URL-Reputation als schädlich eingestuft**</span><span class="sxs-lookup"><span data-stu-id="0c173-531">**URL malicious reputation**</span></span>
- <span data-ttu-id="0c173-532">**URL-Detonation**</span><span class="sxs-lookup"><span data-stu-id="0c173-532">**URL detonation**</span></span>
- <span data-ttu-id="0c173-533">**Reputation der URL-Detonation**</span><span class="sxs-lookup"><span data-stu-id="0c173-533">**URL detonation reputation**</span></span>
- <span data-ttu-id="0c173-534">**Kampagnen**</span><span class="sxs-lookup"><span data-stu-id="0c173-534">**Campaign**</span></span>

<span data-ttu-id="0c173-535">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-535">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0c173-536">**Date**</span><span class="sxs-lookup"><span data-stu-id="0c173-536">**Date**</span></span>
- <span data-ttu-id="0c173-537">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="0c173-537">**Subject**</span></span>
- <span data-ttu-id="0c173-538">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0c173-538">**Sender**</span></span>
- <span data-ttu-id="0c173-539">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="0c173-539">**Recipients**</span></span>
- <span data-ttu-id="0c173-540">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="0c173-540">**Detected by**</span></span>
- <span data-ttu-id="0c173-541">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="0c173-541">**Delivery Status**</span></span>
- <span data-ttu-id="0c173-542">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="0c173-542">**Source of Compromise**</span></span>
- <span data-ttu-id="0c173-543">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0c173-543">**Tags**</span></span>

<span data-ttu-id="0c173-544">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-544">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0c173-545">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-545">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-546">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="0c173-546">**Detection**</span></span>
- <span data-ttu-id="0c173-547">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="0c173-547">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0c173-548">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="0c173-548">**Direction**</span></span>
- <span data-ttu-id="0c173-549">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="0c173-549">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0c173-550">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-550">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0c173-551">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="0c173-551">**Domain**</span></span>
- <span data-ttu-id="0c173-552">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="0c173-552">**Policy type**</span></span>
- <span data-ttu-id="0c173-553">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="0c173-553">**Policy name** (details table only)</span></span>
- <span data-ttu-id="0c173-554">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="0c173-554">**Recipients**</span></span>

<span data-ttu-id="0c173-555">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-555">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="0c173-556">Diagrammaufschlüsselung nach Richtlinientyp und Anzeigen von Daten nach E-Mail-Phishing \> oder Anzeigen von Daten durch E-Mail-Schadsoftware \></span><span class="sxs-lookup"><span data-stu-id="0c173-556">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Richtlinientypansicht für Phishing-E-Mails oder Schadsoftware-E-Mails im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="0c173-558">In der **Diagrammaufschlüsselung nach Richtlinientyp** und **Anzeigen von Daten nach E-Mail-Phishing \>** oder **Anzeigen von Daten nach E-Mail-Schadsoftwareansichten \>** werden die folgenden Informationen in den Diagrammen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0c173-558">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="0c173-559">**Antischadsoftware**</span><span class="sxs-lookup"><span data-stu-id="0c173-559">**Anti-malware**</span></span>
- <span data-ttu-id="0c173-560">**Safe Anlagen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c173-560">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="0c173-561">**Antiphishing**</span><span class="sxs-lookup"><span data-stu-id="0c173-561">**Anti-phish**</span></span>
- <span data-ttu-id="0c173-562">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="0c173-562">**Anti-spam**</span></span>
- <span data-ttu-id="0c173-563">**Nachrichtenflussregel** (auch als Transportregel bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="0c173-563">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="0c173-564">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="0c173-564">**Others**</span></span>

<span data-ttu-id="0c173-565">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-565">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0c173-566">**Date**</span><span class="sxs-lookup"><span data-stu-id="0c173-566">**Date**</span></span>
- <span data-ttu-id="0c173-567">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="0c173-567">**Subject**</span></span>
- <span data-ttu-id="0c173-568">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0c173-568">**Sender**</span></span>
- <span data-ttu-id="0c173-569">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="0c173-569">**Recipients**</span></span>
- <span data-ttu-id="0c173-570">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="0c173-570">**Detected by**</span></span>
- <span data-ttu-id="0c173-571">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="0c173-571">**Delivery Status**</span></span>
- <span data-ttu-id="0c173-572">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="0c173-572">**Source of Compromise**</span></span>
- <span data-ttu-id="0c173-573">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0c173-573">**Tags**</span></span>

<span data-ttu-id="0c173-574">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0c173-575">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-575">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-576">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="0c173-576">**Detection**</span></span>
- <span data-ttu-id="0c173-577">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="0c173-577">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0c173-578">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="0c173-578">**Direction**</span></span>
- <span data-ttu-id="0c173-579">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="0c173-579">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0c173-580">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-580">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0c173-581">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="0c173-581">**Domain**</span></span>
- <span data-ttu-id="0c173-582">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="0c173-582">**Policy type**</span></span>
- <span data-ttu-id="0c173-583">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="0c173-583">**Policy name** (details table only)</span></span>
- <span data-ttu-id="0c173-584">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="0c173-584">**Recipients**</span></span>

<span data-ttu-id="0c173-585">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-585">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="0c173-586">Diagrammaufschlüsselung nach Zustellungsstatus und Anzeigen von Daten nach E-Mail-Phishing \> oder Anzeigen von Daten durch E-Mail-Schadsoftware \></span><span class="sxs-lookup"><span data-stu-id="0c173-586">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Übermittlungsstatusansicht für Phishing-E-Mails und Schadsoftware-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="0c173-588">In der **Diagrammaufschlüsselung nach Übermittlungsstatus** und **Anzeigen von Daten nach E-Mail-Phishing \>** oder **Anzeigen von Daten nach E-Mail-Schadsoftwareansichten \>** werden die folgenden Informationen in den Diagrammen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0c173-588">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="0c173-589">**Gehostetes Postfach: Posteingang**</span><span class="sxs-lookup"><span data-stu-id="0c173-589">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="0c173-590">**Gehostetes Postfach: Junk**</span><span class="sxs-lookup"><span data-stu-id="0c173-590">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="0c173-591">**Gehostetes Postfach: Benutzerdefinierter Ordner**</span><span class="sxs-lookup"><span data-stu-id="0c173-591">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="0c173-592">**Gehostetes Postfach: Gelöschte Elemente**</span><span class="sxs-lookup"><span data-stu-id="0c173-592">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="0c173-593">**Weitergeleitet**</span><span class="sxs-lookup"><span data-stu-id="0c173-593">**Forwarded**</span></span>
- <span data-ttu-id="0c173-594">**Lokaler Server: Bereitgestellt**</span><span class="sxs-lookup"><span data-stu-id="0c173-594">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="0c173-595">**Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="0c173-595">**Quarantine**</span></span>
- <span data-ttu-id="0c173-596">**Übermittlung fehlgeschlagen**</span><span class="sxs-lookup"><span data-stu-id="0c173-596">**Delivery failed**</span></span>
- <span data-ttu-id="0c173-597">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="0c173-597">**Dropped**</span></span>

<span data-ttu-id="0c173-598">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-598">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0c173-599">**Date**</span><span class="sxs-lookup"><span data-stu-id="0c173-599">**Date**</span></span>
- <span data-ttu-id="0c173-600">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="0c173-600">**Subject**</span></span>
- <span data-ttu-id="0c173-601">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0c173-601">**Sender**</span></span>
- <span data-ttu-id="0c173-602">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="0c173-602">**Recipients**</span></span>
- <span data-ttu-id="0c173-603">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="0c173-603">**Detected by**</span></span>
- <span data-ttu-id="0c173-604">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="0c173-604">**Delivery Status**</span></span>
- <span data-ttu-id="0c173-605">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="0c173-605">**Source of Compromise**</span></span>
- <span data-ttu-id="0c173-606">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0c173-606">**Tags**</span></span>

<span data-ttu-id="0c173-607">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-607">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0c173-608">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-608">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-609">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="0c173-609">**Detection**</span></span>
- <span data-ttu-id="0c173-610">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="0c173-610">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0c173-611">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="0c173-611">**Direction**</span></span>
- <span data-ttu-id="0c173-612">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="0c173-612">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0c173-613">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-613">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0c173-614">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="0c173-614">**Domain**</span></span>
- <span data-ttu-id="0c173-615">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="0c173-615">**Policy type**</span></span>
- <span data-ttu-id="0c173-616">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="0c173-616">**Policy name** (details table only)</span></span>
- <span data-ttu-id="0c173-617">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="0c173-617">**Recipients**</span></span>

<span data-ttu-id="0c173-618">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-618">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="0c173-619">Anzeigen von Daten nach \> Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="0c173-619">View data by Content \> Malware</span></span>

![Ansicht "Inhalts-Schadsoftware" im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="0c173-621">In der Ansicht **"Daten nach \> Inhalts-Schadsoftware** anzeigen" werden die folgenden Informationen im Diagramm für Microsoft Defender für Office 365 Organisationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0c173-621">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="0c173-622">**Antischadsoftwaremodul:** Schädliche Dateien, die in SharePoint, OneDrive und Microsoft Teams von der [integrierten Virenerkennung in Microsoft 365](virus-detection-in-spo.md)erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="0c173-622">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="0c173-623">**Dateidetonation:** Schädliche Dateien, die von [Safe Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="0c173-623">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="0c173-624">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-624">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0c173-625">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-625">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-626">**Standort**</span><span class="sxs-lookup"><span data-stu-id="0c173-626">**Location**</span></span>
- <span data-ttu-id="0c173-627">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="0c173-627">**Detected by**</span></span>
- <span data-ttu-id="0c173-628">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="0c173-628">**Malware name**</span></span>

<span data-ttu-id="0c173-629">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-629">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0c173-630">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-630">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-631">**Erkennung:** **Antischadsoftwaremodul** oder **Dateidetonation**</span><span class="sxs-lookup"><span data-stu-id="0c173-631">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="0c173-632">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-632">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="0c173-633">Anzeigen von Daten nach Systemüberschreibung</span><span class="sxs-lookup"><span data-stu-id="0c173-633">View data by System override</span></span>

![Ansicht "Nachrichtenüberschreibung" im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="0c173-635">In der Ansicht **"Ansichtsdaten nach Systemüberschreibung"** werden die folgenden Informationen zum Außerkraftsetzungsgrund im Diagramm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0c173-635">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="0c173-636">**Lokales Überspringen**</span><span class="sxs-lookup"><span data-stu-id="0c173-636">**On-premises skip**</span></span>
- <span data-ttu-id="0c173-637">**IP zulassen**</span><span class="sxs-lookup"><span data-stu-id="0c173-637">**IP allow**</span></span>
- <span data-ttu-id="0c173-638">**Exchange E-Mail-Transportregel** (Nachrichtenflussregel)</span><span class="sxs-lookup"><span data-stu-id="0c173-638">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="0c173-639">**Zulässige Absender in der Organisation**</span><span class="sxs-lookup"><span data-stu-id="0c173-639">**Organization allowed senders**</span></span>
- <span data-ttu-id="0c173-640">**Zulässige Domänen der Organisation**</span><span class="sxs-lookup"><span data-stu-id="0c173-640">**Organization allowed domains**</span></span>
- <span data-ttu-id="0c173-641">**ZAP nicht aktiviert**</span><span class="sxs-lookup"><span data-stu-id="0c173-641">**ZAP not enabled**</span></span>
- <span data-ttu-id="0c173-642">**Junk-E-Mail-Ordner nicht aktiviert**</span><span class="sxs-lookup"><span data-stu-id="0c173-642">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="0c173-643">**Benutzer Safe Absender**</span><span class="sxs-lookup"><span data-stu-id="0c173-643">**User Safe Sender**</span></span>
- <span data-ttu-id="0c173-644">**Safe Domäne des Benutzers**</span><span class="sxs-lookup"><span data-stu-id="0c173-644">**User Safe Domain**</span></span>

<span data-ttu-id="0c173-645">In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-645">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0c173-646">**Date**</span><span class="sxs-lookup"><span data-stu-id="0c173-646">**Date**</span></span>
- <span data-ttu-id="0c173-647">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="0c173-647">**Subject**</span></span>
- <span data-ttu-id="0c173-648">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0c173-648">**Sender**</span></span>
- <span data-ttu-id="0c173-649">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="0c173-649">**Recipients**</span></span>
- <span data-ttu-id="0c173-650">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="0c173-650">**Detected by**</span></span>
- <span data-ttu-id="0c173-651">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="0c173-651">**Delivery Status**</span></span>
- <span data-ttu-id="0c173-652">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="0c173-652">**Source of Compromise**</span></span>
- <span data-ttu-id="0c173-653">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0c173-653">**Tags**</span></span>

<span data-ttu-id="0c173-654">Wenn Sie auf **"Filter"** klicken, sind die folgenden Filter verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0c173-654">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0c173-655">**Datum (UTC)** **Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="0c173-655">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0c173-656">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="0c173-656">**Detection**</span></span>
- <span data-ttu-id="0c173-657">**Geschützt durch:** **MDO** (Defender für Office 365) oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="0c173-657">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0c173-658">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="0c173-658">**Direction**</span></span>
- <span data-ttu-id="0c173-659">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="0c173-659">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0c173-660">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-660">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0c173-661">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="0c173-661">**Domain**</span></span>
- <span data-ttu-id="0c173-662">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="0c173-662">**Policy type**</span></span>
- <span data-ttu-id="0c173-663">**Richtlinienname** (nur Detailtabelle)</span><span class="sxs-lookup"><span data-stu-id="0c173-663">**Policy name** (details table only)</span></span>
- <span data-ttu-id="0c173-664">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="0c173-664">**Recipients**</span></span>

<span data-ttu-id="0c173-665">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-665">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="0c173-666"><sup>\*</sup>Nur Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="0c173-666"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="0c173-667">Bericht über häufigste Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="0c173-667">Top malware report</span></span>

<span data-ttu-id="0c173-668">Der **Bericht "Häufigste Schadsoftware"** zeigt die verschiedenen Arten von Schadsoftware, die vom [Schutz vor Schadsoftware in EOP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c173-668">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="0c173-669">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="0c173-669">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0c173-670">Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** nach **der top-Schadsoftware,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-670">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="0c173-671">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="0c173-671">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Das am häufigsten verwendete Malware-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/top-malware-report-widget.png)

<span data-ttu-id="0c173-673">Wenn Sie den Mauszeiger über einen Wedge im Kreisdiagramm bewegen, sehen Sie den Namen einer Art von Schadsoftware und wie viele Nachrichten als Schadsoftware erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c173-673">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="0c173-674">Auf der Seite **"Häufigste Schadsoftwarebericht"** wird eine größere Version des Kreisdiagramms auf der Berichtsseite angezeigt. Die Detailtabelle unterhalb des Diagramms enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="0c173-674">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="0c173-675">**Häufigste Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="0c173-675">**Top malware**</span></span>
- <span data-ttu-id="0c173-676">**Count**</span><span class="sxs-lookup"><span data-stu-id="0c173-676">**Count**</span></span>

<span data-ttu-id="0c173-677">Wenn Sie auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="0c173-677">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Ansicht des Berichts über häufigste Schadsoftware](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="0c173-679">URL-Bedrohungsschutzbericht</span><span class="sxs-lookup"><span data-stu-id="0c173-679">URL threat protection report</span></span>

<span data-ttu-id="0c173-680">Der **URL-Bedrohungsschutzbericht** ist nur in Microsoft Defender für Office 365 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c173-680">The **URL threat protection report** is available only in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="0c173-681">Weitere Informationen finden Sie unter [URL Threat Protection Report](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="0c173-681">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="0c173-682">Bericht über vom Benutzer gemeldete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="0c173-682">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c173-683">Damit der Bericht über **vom Benutzer gemeldete Nachrichten** ordnungsgemäß funktioniert, muss die **Überwachungsprotokollierung** für Ihre Microsoft 365 Umgebung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="0c173-683">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="0c173-684">Dies geschieht in der Regel von einer Person, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0c173-684">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="0c173-685">Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren Microsoft 365 Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-685">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="0c173-686">Der Bericht **"Vom Benutzer gemeldete Nachrichten"** enthält Informationen zu E-Mail-Nachrichten, die Benutzer mithilfe des [Add-Ins "Nachricht melden"](enable-the-report-message-add-in.md) oder des [Add-Ins "Phishing melden"](enable-the-report-phish-add-in.md)als Junk, Phishingversuche oder gute E-Mails gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="0c173-686">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="0c173-687">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="0c173-687">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0c173-688">Suchen Sie auf der Seite **"E-Mail & Berichte zur Zusammenarbeit"** **nach den vom Benutzer gemeldeten Nachrichten,** und klicken Sie dann auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-688">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="0c173-689">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="0c173-689">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="0c173-690">Wenn Sie im Microsoft 365 Defender Portal zu [Administratorübermittlungen](admin-submission.md)wechseln möchten, klicken Sie auf **"Zu Übermittlungen wechseln".**</span><span class="sxs-lookup"><span data-stu-id="0c173-690">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Vom Benutzer gemeldete Nachrichten-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/user-reported-messages-widget.png)

<span data-ttu-id="0c173-692">Auf der Seite **"Vom Benutzer gemeldete Nachrichten"** können Sie sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filtern"** klicken und einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:</span><span class="sxs-lookup"><span data-stu-id="0c173-692">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="0c173-693">**Gemeldetes Datum**: **Startzeit** und **Endzeit**</span><span class="sxs-lookup"><span data-stu-id="0c173-693">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="0c173-694">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="0c173-694">**Reported by**</span></span>
- <span data-ttu-id="0c173-695">**E-Mail-Betreff**</span><span class="sxs-lookup"><span data-stu-id="0c173-695">**Email subject**</span></span>
- <span data-ttu-id="0c173-696">**Gemeldete ID der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="0c173-696">**Message reported ID**</span></span>
- <span data-ttu-id="0c173-697">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="0c173-697">**Network Message ID**</span></span>
- <span data-ttu-id="0c173-698">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0c173-698">**Sender**</span></span>
- <span data-ttu-id="0c173-699">**Gemeldeter Grund**</span><span class="sxs-lookup"><span data-stu-id="0c173-699">**Reported reason**</span></span>
  - <span data-ttu-id="0c173-700">**Kein Junk**</span><span class="sxs-lookup"><span data-stu-id="0c173-700">**Not junk**</span></span>
  - <span data-ttu-id="0c173-701">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="0c173-701">**Phish**</span></span>
  - <span data-ttu-id="0c173-702">**Spam**</span><span class="sxs-lookup"><span data-stu-id="0c173-702">**Spam**</span></span>
- <span data-ttu-id="0c173-703">**Phishing-Simulation:** **Ja** oder **Nein**</span><span class="sxs-lookup"><span data-stu-id="0c173-703">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="0c173-704">Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="0c173-704">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="0c173-705">Klicken Sie zum Gruppieren der Einträge auf **"Gruppieren",** und wählen Sie einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="0c173-705">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="0c173-706">**Keine**</span><span class="sxs-lookup"><span data-stu-id="0c173-706">**None**</span></span>
- <span data-ttu-id="0c173-707">**Grund**</span><span class="sxs-lookup"><span data-stu-id="0c173-707">**Reason**</span></span>
- <span data-ttu-id="0c173-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0c173-708">**Sender**</span></span>
- <span data-ttu-id="0c173-709">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="0c173-709">**Reported by**</span></span>
- <span data-ttu-id="0c173-710">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="0c173-710">**Rescan result**</span></span>
- <span data-ttu-id="0c173-711">**Phishing-Simulation**</span><span class="sxs-lookup"><span data-stu-id="0c173-711">**Phish simulation**</span></span>

![Bericht über vom Benutzer gemeldete Nachrichten](../../media/user-reported-messages-report.png)

<span data-ttu-id="0c173-713">In der Detailtabelle unterhalb des Diagramms sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="0c173-713">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="0c173-714">**E-Mail-Betreff**</span><span class="sxs-lookup"><span data-stu-id="0c173-714">**Email subject**</span></span>
- <span data-ttu-id="0c173-715">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="0c173-715">**Reported by**</span></span>
- <span data-ttu-id="0c173-716">**Gemeldetes Datum**</span><span class="sxs-lookup"><span data-stu-id="0c173-716">**Date reported**</span></span>
- <span data-ttu-id="0c173-717">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0c173-717">**Sender**</span></span>
- <span data-ttu-id="0c173-718">**Gemeldeter Grund**</span><span class="sxs-lookup"><span data-stu-id="0c173-718">**Reported reason**</span></span>
- <span data-ttu-id="0c173-719">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="0c173-719">**Rescan result**</span></span>
- <span data-ttu-id="0c173-720">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0c173-720">**Tags**</span></span>

<span data-ttu-id="0c173-721">Um eine Nachricht zur Analyse an Microsoft zu übermitteln, wählen Sie den Nachrichteneintrag aus der Tabelle aus, klicken Sie auf **"Zur Analyse an Microsoft übermitteln",** und wählen Sie dann einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="0c173-721">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="0c173-722">**Bericht sauber**</span><span class="sxs-lookup"><span data-stu-id="0c173-722">**Report clean**</span></span>
- <span data-ttu-id="0c173-723">**Melden von Phishing**</span><span class="sxs-lookup"><span data-stu-id="0c173-723">**Report phishing**</span></span>
- <span data-ttu-id="0c173-724">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="0c173-724">**Report malware**</span></span>
- <span data-ttu-id="0c173-725">**Spam melden**'</span><span class="sxs-lookup"><span data-stu-id="0c173-725">**Report spam**'</span></span>
- <span data-ttu-id="0c173-726">**Untersuchung auslösen** (Defender für Office 365)</span><span class="sxs-lookup"><span data-stu-id="0c173-726">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="0c173-727">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="0c173-727">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="0c173-728">Um die in diesem Artikel beschriebenen Berichte anzuzeigen und zu verwenden, müssen Sie Mitglied einer der folgenden Rollengruppen im Microsoft 365 Defender Portal sein:</span><span class="sxs-lookup"><span data-stu-id="0c173-728">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="0c173-729">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="0c173-729">**Organization Management**</span></span>
- <span data-ttu-id="0c173-730">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="0c173-730">**Security Administrator**</span></span>
- <span data-ttu-id="0c173-731">**Sicherheitsleseberechtigter**</span><span class="sxs-lookup"><span data-stu-id="0c173-731">**Security Reader**</span></span>
- <span data-ttu-id="0c173-732">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="0c173-732">**Global Reader**</span></span>

<span data-ttu-id="0c173-733">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-733">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="0c173-734">**Hinweis:** Das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center bietet Benutzern die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c173-734">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0c173-735">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0c173-735">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="0c173-736">Was geschieht, wenn in den Berichten keine Daten angezeigt werden?</span><span class="sxs-lookup"><span data-stu-id="0c173-736">What if the reports aren't showing data?</span></span>

<span data-ttu-id="0c173-737">Wenn in Ihren Berichten keine Daten angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="0c173-737">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="0c173-738">Weitere Informationen finden Sie unter ["Schutz vor Bedrohungen".](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="0c173-738">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c173-739">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0c173-739">Related topics</span></span>

[<span data-ttu-id="0c173-740">Antispam- und Antischadsoftwareschutz in EOP</span><span class="sxs-lookup"><span data-stu-id="0c173-740">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="0c173-741">Intelligente Berichte und Einblicke im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="0c173-741">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="0c173-742">Anzeigen von Nachrichtenflussberichten im Microsoft 365 Defender Portal</span><span class="sxs-lookup"><span data-stu-id="0c173-742">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="0c173-743">Anzeigen von Berichten für Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="0c173-743">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
