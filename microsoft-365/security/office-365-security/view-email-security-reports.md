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
ms.openlocfilehash: bb7570722fcc957ca86d68f6b42ef254578d7bd7
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930321"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="1ada2-104">Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="1ada2-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1ada2-105">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="1ada2-105">**Applies to**</span></span>
- [<span data-ttu-id="1ada2-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1ada2-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1ada2-107">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="1ada2-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1ada2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ada2-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1ada2-109">Im [Microsoft 365 Defender-Portal](https://security.microsoft.com) stehen eine Vielzahl von Berichten zur Verfügung, mit denen Sie sehen können, wie E-Mail-Sicherheitsfeatures wie Antispam, Antischadsoftware und Verschlüsselungsfunktionen in Microsoft 365 Ihre Organisation schützen.</span><span class="sxs-lookup"><span data-stu-id="1ada2-109">A variety of reports are available in the [Microsoft 365 Defender portal](https://security.microsoft.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="1ada2-110">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im Microsoft 365 Defender-Portal anzeigen, indem Sie zu  \> **E-Mail-Berichte &** \> **Zusammenarbeit E-Mail & Zusammenarbeitsberichte wechseln.**</span><span class="sxs-lookup"><span data-stu-id="1ada2-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="1ada2-111">Um direkt zum Berichtsdashboard zu wechseln, öffnen Sie <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="1ada2-111">To go directly to the Reports dashboard, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Berichtsdashboard im Microsoft 365 Defender-Portal](../../media/email-collaboration-reports.png)

## <a name="compromised-users-report"></a><span data-ttu-id="1ada2-113">Bericht "Kompromittierte Benutzer"</span><span class="sxs-lookup"><span data-stu-id="1ada2-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="1ada2-114">Dieser Bericht ist in Microsoft 365 Organisationen mit Exchange Online Postfächern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1ada2-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="1ada2-115">Es ist in eigenständigen Exchange Online Protection (EOP)-Organisationen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1ada2-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="1ada2-116">Der Bericht **"Kompromittierte Benutzer"** zeigt die Anzahl der Benutzerkonten an, die innerhalb der letzten 7 Tage als **verdächtig** oder **eingeschränkt** markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="1ada2-117">Konten in einem dieser Zustände sind problematisch oder sogar kompromittiert.</span><span class="sxs-lookup"><span data-stu-id="1ada2-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="1ada2-118">Bei häufiger Verwendung können Sie den Bericht verwenden, um Spitzen und sogar Trends in verdächtigen oder eingeschränkten Konten zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="1ada2-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="1ada2-119">Weitere Informationen zu kompromittierten Benutzern finden Sie unter [Antworten auf ein kompromittiertes E-Mail-Konto.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget "Kompromittierte Benutzer" im Dashboard "Berichte"](../../media/compromised-users-report-widget.png)

<span data-ttu-id="1ada2-121">In der Aggregatansicht werden Daten für die letzten 90 Tage und in der Detailansicht Daten für die letzten 30 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ada2-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="1ada2-122">Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **"E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte",** und klicken Sie unter **"Kompromittierte Benutzer"** auf **"Details anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="1ada2-122">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Compromised users**.</span></span> <span data-ttu-id="1ada2-123">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="1ada2-123">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="1ada2-124">Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **Filter** klicken und einen oder mehrere der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="1ada2-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="1ada2-125">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="1ada2-126">**Verdächtig:** Das Benutzerkonto hat verdächtige E-Mails gesendet und besteht das Risiko, dass das Senden von E-Mails eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="1ada2-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="1ada2-127">**Eingeschränkt:** Das Benutzerkonto wurde aufgrund von hochgradig verdächtigen Mustern am Senden von E-Mails gehindert.</span><span class="sxs-lookup"><span data-stu-id="1ada2-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Berichtsansicht im Bericht "Kompromittierte Benutzer"](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="1ada2-129">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Details angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="1ada2-130">**Erstellungszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="1ada2-130">**Creation time**</span></span>
- <span data-ttu-id="1ada2-131">**Benutzer-ID**</span><span class="sxs-lookup"><span data-stu-id="1ada2-131">**User ID**</span></span>
- <span data-ttu-id="1ada2-132">**Action**</span><span class="sxs-lookup"><span data-stu-id="1ada2-132">**Action**</span></span>

<span data-ttu-id="1ada2-133">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="1ada2-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="1ada2-134">Verschlüsselungsbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-134">Encryption report</span></span>

<span data-ttu-id="1ada2-135">Der **Verschlüsselungsbericht** ist in EOP verfügbar (Abonnements mit Postfächern in Exchange Online oder eigenständiger EOP ohne Exchange Online Postfächer).</span><span class="sxs-lookup"><span data-stu-id="1ada2-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="1ada2-136">Das Sicherheitsteam Ihrer Organisation kann die Informationen in diesem Bericht verwenden, um Muster zu identifizieren und Richtlinien für vertrauliche E-Mail-Nachrichten proaktiv anzuwenden oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="1ada2-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="1ada2-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1ada2-137">For example:</span></span>

- <span data-ttu-id="1ada2-138">Wenn eine hohe Anzahl von E-Mail-Nachrichten von Benutzern verschlüsselt wird, möchten Sie möglicherweise eine Verschlüsselungsrichtlinie hinzufügen, um die Verschlüsselung für bestimmte Anwendungsfälle zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="1ada2-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="1ada2-139">Weitere Informationen finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="1ada2-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="1ada2-140">Wenn Sie über eine Reihe von Verschlüsselungsvorlagen verfügen, die jedoch nicht verwendet werden, können Sie untersuchen, ob Benutzer eine Featureschulung benötigen.</span><span class="sxs-lookup"><span data-stu-id="1ada2-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="1ada2-141">Die Aggregatansicht ermöglicht das Filtern für die letzten 90 Tage, während die Detailansicht das Filtern für 10 Tage zulässt.</span><span class="sxs-lookup"><span data-stu-id="1ada2-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="1ada2-142">Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **"E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte",** und klicken Sie auf **"Details anzeigen"** unter **"Verschlüsselungsbericht".**</span><span class="sxs-lookup"><span data-stu-id="1ada2-142">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Encryption report**.</span></span> <span data-ttu-id="1ada2-143">Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="1ada2-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="1ada2-144">Weitere Informationen zur Verschlüsselung finden Sie unter [E-Mail-Verschlüsselung in Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="1ada2-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="1ada2-145">Berichtsansicht für den Verschlüsselungsbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-145">Report view for the Encryption report</span></span>

<span data-ttu-id="1ada2-146">Sie können die folgenden Filter für das Diagramm verwenden:</span><span class="sxs-lookup"><span data-stu-id="1ada2-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="1ada2-147">**Anzeigen von Daten nach: Nachrichtenverschlüsselungsbericht** und **Aufschlüsselung nach: Verschlüsselungsmethode:** Die folgenden Verschlüsselungsmethoden sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="1ada2-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="1ada2-148">**Verschlüsselung nach Benutzer**</span><span class="sxs-lookup"><span data-stu-id="1ada2-148">**Encryption by user**</span></span>
  - <span data-ttu-id="1ada2-149">**Verschlüsselung nach Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="1ada2-149">**Encryption by policy**</span></span>

  <span data-ttu-id="1ada2-150">Wenn Sie auf **"Filter"** klicken, können Sie das Diagramm mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="1ada2-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="1ada2-151">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1ada2-152">Verschlüsselungsmethode.</span><span class="sxs-lookup"><span data-stu-id="1ada2-152">Encryption method.</span></span>
  - <span data-ttu-id="1ada2-153">Verschlüsselungsvorlage.</span><span class="sxs-lookup"><span data-stu-id="1ada2-153">Encryption template.</span></span>

- <span data-ttu-id="1ada2-154">**Anzeigen von Daten nach: Nachrichtenverschlüsselungsbericht** und **Aufschlüsselung nach: Verschlüsselungsvorlage:** Die folgenden Verschlüsselungsmethoden sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="1ada2-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="1ada2-155">**Nicht weiterleiten**</span><span class="sxs-lookup"><span data-stu-id="1ada2-155">**Do not forward**</span></span>
  - <span data-ttu-id="1ada2-156">**Nur verschlüsseln**</span><span class="sxs-lookup"><span data-stu-id="1ada2-156">**Encrypt only**</span></span>
  - <span data-ttu-id="1ada2-157">**Vorheriges OME**</span><span class="sxs-lookup"><span data-stu-id="1ada2-157">**OME previous**</span></span>
  - <span data-ttu-id="1ada2-158">**Custom**</span><span class="sxs-lookup"><span data-stu-id="1ada2-158">**Custom**</span></span>

  <span data-ttu-id="1ada2-159">Wenn Sie auf **"Filter"** klicken, können Sie das Diagramm mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="1ada2-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="1ada2-160">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1ada2-161">Verschlüsselungsmethode</span><span class="sxs-lookup"><span data-stu-id="1ada2-161">Encryption method</span></span>
  - <span data-ttu-id="1ada2-162">Verschlüsselungsvorlage</span><span class="sxs-lookup"><span data-stu-id="1ada2-162">Encryption template</span></span>

- <span data-ttu-id="1ada2-163">**Anzeigen von Daten nach: Top 5 recipient domains:** This view shows a pie chart with sent message counts for the top 5 recipient domains.</span><span class="sxs-lookup"><span data-stu-id="1ada2-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="1ada2-164">Wenn Sie auf **Filter** klicken, können Sie ein **Start-** und **Enddatum** auswählen.</span><span class="sxs-lookup"><span data-stu-id="1ada2-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="1ada2-165">Detailtabellenansicht für den Verschlüsselungsbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="1ada2-166">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich ansehen:</span><span class="sxs-lookup"><span data-stu-id="1ada2-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1ada2-167">**Unterschlüsselung nach: Verschlüsselungsmethode** oder **Aufschlüsselung nach: Verschlüsselungsvorlage:** Die folgenden Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="1ada2-168">**Date**</span><span class="sxs-lookup"><span data-stu-id="1ada2-168">**Date**</span></span>
  - <span data-ttu-id="1ada2-169">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="1ada2-169">**Sender address**</span></span>
  - <span data-ttu-id="1ada2-170">**Verschlüsselungsvorlage**</span><span class="sxs-lookup"><span data-stu-id="1ada2-170">**Encryption template**</span></span>
  - <span data-ttu-id="1ada2-171">**Verschlüsselungsmethode**</span><span class="sxs-lookup"><span data-stu-id="1ada2-171">**Encryption method**</span></span>
  - <span data-ttu-id="1ada2-172">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="1ada2-172">**Recipient address**</span></span>
  - <span data-ttu-id="1ada2-173">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="1ada2-173">**Subject**</span></span>

- <span data-ttu-id="1ada2-174">**Anzeigen von Daten nach: Top 5 Empfängerdomänen:**</span><span class="sxs-lookup"><span data-stu-id="1ada2-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="1ada2-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="1ada2-175">**Date**</span></span>
  - <span data-ttu-id="1ada2-176">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="1ada2-176">**Recipient domain**</span></span>
  - <span data-ttu-id="1ada2-177">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="1ada2-177">**Message count**</span></span>

<span data-ttu-id="1ada2-178">Wenn Sie in einer Detailtabellenansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="1ada2-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1ada2-179">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="1ada2-180">Verschlüsselungsmethode</span><span class="sxs-lookup"><span data-stu-id="1ada2-180">Encryption method</span></span>
- <span data-ttu-id="1ada2-181">Verschlüsselungsvorlage</span><span class="sxs-lookup"><span data-stu-id="1ada2-181">Encryption template</span></span>

<span data-ttu-id="1ada2-182">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="1ada2-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="1ada2-183">E-Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-183">Mailflow status report</span></span>

<span data-ttu-id="1ada2-184">Der **E-Mailflow-Statusbericht** enthält Informationen zu Schadsoftware, Spam, Phishing und blockierten Edgenachrichten.</span><span class="sxs-lookup"><span data-stu-id="1ada2-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="1ada2-185">Weitere Informationen finden Sie im [Mailflow-Statusbericht.](view-mail-flow-reports.md#mailflow-status-report)</span><span class="sxs-lookup"><span data-stu-id="1ada2-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="1ada2-186">Schadsoftwareerkennungen im E-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-186">Malware detections in email report</span></span>

<span data-ttu-id="1ada2-187">Der Bericht über **Schadsoftwareerkennungen in E-Mails** enthält Informationen zu Schadsoftwareerkennungen in eingehenden und ausgehenden E-Mail-Nachrichten (von Exchange Online Protection oder EOP erkannte Schadsoftware).</span><span class="sxs-lookup"><span data-stu-id="1ada2-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="1ada2-188">Weitere Informationen zum Schutz vor Schadsoftware in EOP finden Sie unter [Antischadsoftwareschutz in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="1ada2-189">Der Aggregatansichtsfilter lässt 90 Tage zu, während der Detailtabellenfilter nur 10 Tage zulässt.</span><span class="sxs-lookup"><span data-stu-id="1ada2-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="1ada2-190">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** Email \> **& collaboration** Email & collaboration \> **reports** and click **View details** under **Malware detected in email**.</span><span class="sxs-lookup"><span data-stu-id="1ada2-190">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Malware detected in email**.</span></span> <span data-ttu-id="1ada2-191">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="1ada2-191">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Schadsoftwareerkennungen im E-Mail-Widget im Berichtsdashboard](../../media/malware-detections-widget.png)

<span data-ttu-id="1ada2-193">Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filter"** klicken und Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="1ada2-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="1ada2-194">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="1ada2-195">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="1ada2-195">**Inbound**</span></span>
- <span data-ttu-id="1ada2-196">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="1ada2-196">**Outbound**</span></span>

![Berichtsansicht im Bericht "Schadsoftwareerkennung in E-Mail"](../../media/malware-detections-report-view.png)

<span data-ttu-id="1ada2-198">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Details angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="1ada2-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="1ada2-199">**Date**</span></span>
- <span data-ttu-id="1ada2-200">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="1ada2-200">**Sender address**</span></span>
- <span data-ttu-id="1ada2-201">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="1ada2-201">**Recipient address**</span></span>
- <span data-ttu-id="1ada2-202">**Nachrichten-ID:** Verfügbar im **Nachrichten-ID-Kopfzeilenfeld** im Nachrichtenkopf und sollte eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="1ada2-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="1ada2-203">Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (beachten Sie die spitzen Klammern).</span><span class="sxs-lookup"><span data-stu-id="1ada2-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="1ada2-204">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="1ada2-204">**Subject**</span></span>
- <span data-ttu-id="1ada2-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="1ada2-205">**Filename**</span></span>
- <span data-ttu-id="1ada2-206">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="1ada2-206">**Malware name**</span></span>

<span data-ttu-id="1ada2-207">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="1ada2-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="1ada2-208">E-Mail-Latenzbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-208">Mail latency report</span></span>

<span data-ttu-id="1ada2-209">Der **E-Mail-Latenzbericht** enthält Informationen zur E-Mail-Zustellungs- und Detonationslatenz in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="1ada2-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="1ada2-210">Weitere Informationen finden Sie im [E-Mail-Latenzbericht.](view-reports-for-mdo.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="1ada2-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="1ada2-211">Gesendeter und empfangener E-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-211">Sent and received email report</span></span>

<span data-ttu-id="1ada2-212">Der Bericht **"Gesendete und empfangene E-Mails"** enthält Informationen zu Schadsoftware, Spam, Nachrichtenflussregeln (auch als Transportregeln bezeichnet) und erweiterte Schadsoftwareerkennungen, nachdem E-Mails in den Dienst gelangt sind.</span><span class="sxs-lookup"><span data-stu-id="1ada2-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="1ada2-213">Weitere Informationen finden Sie unter ["Gesendete und empfangene E-Mail-Berichte".](view-mail-flow-reports.md#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="1ada2-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="1ada2-214">Spamerkennungsbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-214">Spam detections report</span></span>

<span data-ttu-id="1ada2-215">Der **Spamerkennungsbericht** zeigt Spam-E-Mail-Nachrichten an, die von EOP blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="1ada2-216">Nachrichten werden einzeln gezählt, nicht pro Empfänger.</span><span class="sxs-lookup"><span data-stu-id="1ada2-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="1ada2-217">Wenn die gleiche Spamnachricht beispielsweise an 100 Empfänger in Ihrer Organisation gesendet wurde, zählt sie als eine Nachricht.</span><span class="sxs-lookup"><span data-stu-id="1ada2-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="1ada2-218">Die Aggregatansicht ermöglicht das Filtern von 90 Tagen, während die Detailtabelle das Filtern von 10 Tagen zulässt.</span><span class="sxs-lookup"><span data-stu-id="1ada2-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="1ada2-219">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** Email \> **& collaboration** Email & collaboration \> **reports** and click **View details** under Spam **detections**.</span><span class="sxs-lookup"><span data-stu-id="1ada2-219">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click click **View details** under **Spam detections**.</span></span> <span data-ttu-id="1ada2-220">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="1ada2-220">To go directly to the report, open <https://security.microsoft.com/reports/SpamDetections>.</span></span>

![Spamerkennungs-Widget im Dashboard "Berichte"](../../media/spam-detections-report-widget.png)

<span data-ttu-id="1ada2-222">Weitere Informationen zum Antispamschutz finden Sie unter [Antispamschutz in EOP.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="1ada2-223">Berichtsansicht für den Spamerkennungsbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="1ada2-224">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="1ada2-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="1ada2-225">**Unterschlüsselung nach: Aktion:** Die folgenden Ereignistypen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="1ada2-226">**Gefilterter Spaminhalt**</span><span class="sxs-lookup"><span data-stu-id="1ada2-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="1ada2-227">**Spam-IP-Blockierung**</span><span class="sxs-lookup"><span data-stu-id="1ada2-227">**Spam IP block**</span></span>
  - <span data-ttu-id="1ada2-228">**Spam-Umschlagblock**</span><span class="sxs-lookup"><span data-stu-id="1ada2-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="1ada2-229">**Spam-DBEB-Filter:** Verzeichnisbasierte Edgeblockierung (DBEB)</span><span class="sxs-lookup"><span data-stu-id="1ada2-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="1ada2-230">Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, können Sie sehen, wie viele Elemente an diesem Tag blockiert wurden und wie diese Elemente kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Aktionsansicht im Spamerkennungsbericht](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="1ada2-232">**Aufschlüsseln nach: Richtung:** Die folgenden Richtungen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="1ada2-233">**Eingehende**</span><span class="sxs-lookup"><span data-stu-id="1ada2-233">**Inbound**</span></span>
  - <span data-ttu-id="1ada2-234">**Ausgehende**</span><span class="sxs-lookup"><span data-stu-id="1ada2-234">**Outbound**</span></span>

  ![Richtungsansicht im Spamerkennungsbericht](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="1ada2-236">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="1ada2-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1ada2-237">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="1ada2-238">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="1ada2-238">Direction values</span></span>
- <span data-ttu-id="1ada2-239">Ereignistypwerte</span><span class="sxs-lookup"><span data-stu-id="1ada2-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="1ada2-240">Detailtabellenansicht für den Spamerkennungsbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="1ada2-241">Wenn Sie in einer Berichtsansicht auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="1ada2-242">**Date**</span><span class="sxs-lookup"><span data-stu-id="1ada2-242">**Date**</span></span>
- <span data-ttu-id="1ada2-243">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="1ada2-243">**Sender address**</span></span>
- <span data-ttu-id="1ada2-244">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="1ada2-244">**Recipient address**</span></span>
- <span data-ttu-id="1ada2-245">**Ereignistyp**</span><span class="sxs-lookup"><span data-stu-id="1ada2-245">**Event type**</span></span>
- <span data-ttu-id="1ada2-246">**Action**</span><span class="sxs-lookup"><span data-stu-id="1ada2-246">**Action**</span></span>
- <span data-ttu-id="1ada2-247">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="1ada2-247">**Subject**</span></span>

<span data-ttu-id="1ada2-248">Wenn Sie in einer Detailtabelle auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="1ada2-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1ada2-249">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="1ada2-250">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="1ada2-250">Direction values</span></span>
- <span data-ttu-id="1ada2-251">Ereignistypwerte</span><span class="sxs-lookup"><span data-stu-id="1ada2-251">Event type values</span></span>

<span data-ttu-id="1ada2-252">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="1ada2-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="1ada2-253">Bericht über Spooferkennungen</span><span class="sxs-lookup"><span data-stu-id="1ada2-253">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="1ada2-254">Der verbesserte Bericht über Spooferkennungen, wie in diesem Artikel beschrieben, befindet sich in der Vorschau, kann geändert werden und ist nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1ada2-254">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="1ada2-255">In der älteren Version des Berichts wurden nur **"Gute E-Mails"** und **"Als Spam abgefangen"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ada2-255">The older version of the report showed only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="1ada2-256">Der Bericht **"Spooferkennungen"** enthält Informationen zu Nachrichten, die aufgrund von Spoofing blockiert oder zugelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-256">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="1ada2-257">Weitere Informationen zum Spoofing finden Sie unter [Antispoofingschutz in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-257">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="1ada2-258">Die Aggregatansicht des Berichts lässt 45 Tage Filterung <sup>\*</sup> zu, während die Detailansicht nur zehn Tage Filterung zulässt.</span><span class="sxs-lookup"><span data-stu-id="1ada2-258">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="1ada2-259"><sup>\*</sup> Schließlich können Sie die Filterung bis zu 90 Tage verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-259"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="1ada2-260">Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte,** und klicken Sie unter **Spoofing-Erkennungen** auf **Details anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="1ada2-260">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Spoof detections**.</span></span> <span data-ttu-id="1ada2-261">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="1ada2-261">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReport>.</span></span>

![Widget "Spooferkennungen" im Dashboard "Berichte"](../../media/spoof-detections-widget.png)

<span data-ttu-id="1ada2-263">Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, können Sie sehen, wie viele gefälschte Nachrichten erkannt wurden und warum.</span><span class="sxs-lookup"><span data-stu-id="1ada2-263">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="1ada2-264">Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **Filter** klicken und einen oder mehrere der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="1ada2-264">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="1ada2-265">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-265">**Start date** and **End date**</span></span>

- <span data-ttu-id="1ada2-266">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="1ada2-266">**Result**</span></span>
  - <span data-ttu-id="1ada2-267">**bestehen**</span><span class="sxs-lookup"><span data-stu-id="1ada2-267">**Pass**</span></span>
  - <span data-ttu-id="1ada2-268">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="1ada2-268">**Fail**</span></span>
  - <span data-ttu-id="1ada2-269">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="1ada2-269">**SoftPass**</span></span>
  - <span data-ttu-id="1ada2-270">**Keine**</span><span class="sxs-lookup"><span data-stu-id="1ada2-270">**None**</span></span>
  - <span data-ttu-id="1ada2-271">**Other**</span><span class="sxs-lookup"><span data-stu-id="1ada2-271">**Other**</span></span>

- <span data-ttu-id="1ada2-272">**Spooftyp:** **Intern** und **extern**</span><span class="sxs-lookup"><span data-stu-id="1ada2-272">**Spoof type**: **Internal** and **External**</span></span>

![Berichtsansicht im Bericht über Spooferkennungen](../../media/spoof-detections-report-view.png)

<span data-ttu-id="1ada2-274">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Details angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-274">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="1ada2-275">**Date**</span><span class="sxs-lookup"><span data-stu-id="1ada2-275">**Date**</span></span>
- <span data-ttu-id="1ada2-276">**Gefälschter Benutzer**</span><span class="sxs-lookup"><span data-stu-id="1ada2-276">**Spoofed user**</span></span>
- <span data-ttu-id="1ada2-277">**Senden der Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="1ada2-277">**Sending infrastructure**</span></span>
- <span data-ttu-id="1ada2-278">**Spooftyp**</span><span class="sxs-lookup"><span data-stu-id="1ada2-278">**Spoof type**</span></span>
- <span data-ttu-id="1ada2-279">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="1ada2-279">**Result**</span></span>
- <span data-ttu-id="1ada2-280">**Ergebniscode**</span><span class="sxs-lookup"><span data-stu-id="1ada2-280">**Result code**</span></span>
- <span data-ttu-id="1ada2-281">**SPF**</span><span class="sxs-lookup"><span data-stu-id="1ada2-281">**SPF**</span></span>
- <span data-ttu-id="1ada2-282">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="1ada2-282">**DKIM**</span></span>
- <span data-ttu-id="1ada2-283">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="1ada2-283">**DMARC**</span></span>
- <span data-ttu-id="1ada2-284">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="1ada2-284">**Message count**</span></span>

<span data-ttu-id="1ada2-285">Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="1ada2-285">To go back to the report view, click **View report**.</span></span>

<span data-ttu-id="1ada2-286">Weitere Informationen zu Ergebniscodes für die zusammengesetzte Authentifizierung finden Sie unter [Antispam-Nachrichtenkopfzeilen in Microsoft 365](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="1ada2-286">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="1ada2-287">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-287">Threat protection status report</span></span>

<span data-ttu-id="1ada2-288">Der **Statusbericht zum Bedrohungsschutz** ist sowohl in EOP als auch in Microsoft Defender für Office 365 verfügbar. Die Berichte enthalten jedoch unterschiedliche Daten.</span><span class="sxs-lookup"><span data-stu-id="1ada2-288">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="1ada2-289">EOP-Kunden können z. B. Informationen zu Schadsoftware anzeigen, die in E-Mails erkannt wurde, aber keine Informationen zu schädlichen Dateien, die von [sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-289">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="1ada2-290">Der Bericht enthält die Anzahl der E-Mail-Nachrichten mit schädlichen Inhalten, z. B. Dateien oder Websiteadressen (URLs), die vom Antischadsoftwaremodul blockiert wurden, Zap [(Zero-Hour Auto Purge)](zero-hour-auto-purge.md)und Defender für Office 365 Features wie [sichere Links,](safe-links.md) [sichere Anlagen](safe-attachments.md)und [Antiphishing.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-290">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="1ada2-291">Anhand dieser Informationen können Sie Trends erkennen oder ermitteln, ob Die Unternehmensrichtlinien angepasst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1ada2-291">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="1ada2-292">**Hinweis:** Es ist wichtig zu wissen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="1ada2-292">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="1ada2-293">Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte,** und klicken Sie auf Details unter **Bedrohungsschutzstatus** **anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="1ada2-293">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Threat protection status**.</span></span> <span data-ttu-id="1ada2-294">Um direkt zum Bericht zu wechseln, öffnen Sie eine der folgenden URLs:</span><span class="sxs-lookup"><span data-stu-id="1ada2-294">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="1ada2-295">Microsoft Defender für Office 365:<https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="1ada2-295">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="1ada2-296">Eop: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="1ada2-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Bedrohungsschutzstatus-Widget im Dashboard "Berichte"](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="1ada2-298">Standardmäßig werden im Diagramm Daten für die letzten 7 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ada2-298">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="1ada2-299">Wenn Sie auf **"Filter"** klicken, können Sie einen Zeitraum von 90 Tagen auswählen (Testabonnements sind möglicherweise auf 30 Tage begrenzt).</span><span class="sxs-lookup"><span data-stu-id="1ada2-299">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="1ada2-300">Die Detailtabellenansicht ermöglicht das Filtern für 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="1ada2-300">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="1ada2-301">Berichtsansicht für den Bedrohungsschutzstatusbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-301">Report view for the Threat protection status report</span></span>

<span data-ttu-id="1ada2-302">Die folgenden Ansichten sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="1ada2-302">The following views are available:</span></span>

- <span data-ttu-id="1ada2-303">**Anzeigen von Daten nach: Übersicht:** Die folgenden Erkennungsinformationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-303">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="1ada2-304">**E-Mail-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="1ada2-304">**Email malware**</span></span>
  - <span data-ttu-id="1ada2-305">**E-Mail-Phishing**</span><span class="sxs-lookup"><span data-stu-id="1ada2-305">**Email phish**</span></span>
  - <span data-ttu-id="1ada2-306">**Inhalts-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="1ada2-306">**Content malware**</span></span>

  ![Übersichtsansicht im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="1ada2-308">**Anzeigen von Daten nach: Inhalt \> Schadsoftware**<sup>1:</sup>Die folgenden Informationen werden für Microsoft Defender für Office 365 Organisationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-308">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="1ada2-309">**Antischadsoftwaremodul:** Schädliche Dateien, die in SharePoint, OneDrive und Microsoft Teams von der [integrierten Virenerkennung in Microsoft 365](virus-detection-in-spo.md)erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-309">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="1ada2-310">**Dateidetonation:** Schädliche Dateien, die von [sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-310">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![Ansicht "Inhalts-Schadsoftware" im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="1ada2-312">**Anzeigen von Daten nach: Nachrichtenüberschreibung:** Die folgenden Informationen zum Außerkraftsetzungsgrund werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-312">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="1ada2-313">**Lokales Überspringen**</span><span class="sxs-lookup"><span data-stu-id="1ada2-313">**On-premises skip**</span></span>
  - <span data-ttu-id="1ada2-314">**IP zulassen**</span><span class="sxs-lookup"><span data-stu-id="1ada2-314">**IP Allow**</span></span>
  - <span data-ttu-id="1ada2-315">**Nachrichtenflussregel**</span><span class="sxs-lookup"><span data-stu-id="1ada2-315">**Mail flow rule**</span></span>
  - <span data-ttu-id="1ada2-316">**Absender zulassen**</span><span class="sxs-lookup"><span data-stu-id="1ada2-316">**Sender allow**</span></span>
  - <span data-ttu-id="1ada2-317">**Domänen zulassen**</span><span class="sxs-lookup"><span data-stu-id="1ada2-317">**Domain allow**</span></span>
  - <span data-ttu-id="1ada2-318">**ZAP nicht aktiviert**</span><span class="sxs-lookup"><span data-stu-id="1ada2-318">**ZAP not enabled**</span></span>
  - <span data-ttu-id="1ada2-319">**Junk-E-Mail-Ordner nicht aktiviert**</span><span class="sxs-lookup"><span data-stu-id="1ada2-319">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="1ada2-320">**Benutzersicherer Absender**</span><span class="sxs-lookup"><span data-stu-id="1ada2-320">**User Safe Sender**</span></span>
  - <span data-ttu-id="1ada2-321">**Benutzersichere Domäne**</span><span class="sxs-lookup"><span data-stu-id="1ada2-321">**User Safe Domain**</span></span>

  ![Ansicht "Nachrichtenüberschreibung" im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="1ada2-323">**Unterschlüsselung nach: Erkennungstechnologie** und **Anzeigen von Daten nach: E-Mail-Phishing: \>** Die folgenden Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="1ada2-324">**ATP-generierte URL-Zuverlässigkeit**<sup>1:</sup>Bösartige URL-Reputation, die von Defender für Office 365 Detonationen in anderen Microsoft 365 Kunden generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1ada2-324">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="1ada2-325">**Erweiterter Phishingfilter:** Phishingsignale basierend auf maschinellem Lernen.</span><span class="sxs-lookup"><span data-stu-id="1ada2-325">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="1ada2-326">**Antispoofing : DMARC-Fehler:** DMARC-Authentifizierungsfehler bei Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="1ada2-326">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="1ada2-327">**Antispoofing – organisationsintern:** Der Absender versucht, die Empfängerdomäne zu spoofen.</span><span class="sxs-lookup"><span data-stu-id="1ada2-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="1ada2-328">**Antispoofing – externe Domäne:** Der Absender versucht, eine andere Domäne zu spoofen.</span><span class="sxs-lookup"><span data-stu-id="1ada2-328">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="1ada2-329">**Markenidentitätswechsel:** Identitätswechsel bekannter Marken basierend auf Absendern.</span><span class="sxs-lookup"><span data-stu-id="1ada2-329">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="1ada2-330">**Domänenidentitätswechsel**<sup>1:</sup>Identitätswechsel von Domänen, die der Kunde besitzt oder definiert.</span><span class="sxs-lookup"><span data-stu-id="1ada2-330">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="1ada2-331">**EOP-URL-Zuverlässigkeit:** Böswillige URL-Reputation.</span><span class="sxs-lookup"><span data-stu-id="1ada2-331">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="1ada2-332">**Allgemeiner Phishingfilter:** Phishingsignale basierend auf Analystenregeln.</span><span class="sxs-lookup"><span data-stu-id="1ada2-332">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="1ada2-333">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="1ada2-333">**Others**</span></span>
  - <span data-ttu-id="1ada2-334">**Phishing ZAP**<sup>2:</sup>Automatische Bereinigung von Phishingnachrichten zur Nullstunde.</span><span class="sxs-lookup"><span data-stu-id="1ada2-334">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="1ada2-335">**URL-Detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1ada2-335">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="1ada2-336">**Benutzeridentitätswechsel**<sup>1:</sup>Identitätswechsel von Benutzern, die vom Administrator definiert wurden oder über die Postfachintelligenz gelernt haben.</span><span class="sxs-lookup"><span data-stu-id="1ada2-336">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Ansicht der Erkennungstechnologie für Phishing-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="1ada2-338">**Unterschlüsselung nach: Erkennungstechnologie** und **Anzeigen von Daten nach: E-Mail-Schadsoftware: \>** Die folgenden Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="1ada2-339">**ATP-generierte Dateireputation**<sup>1:</sup>Alle bösartigen Dateireputationen, die von Defender für Office 365 Detonationen generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-339">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="1ada2-340">**Antischadsoftwaremodul**<sup>1:</sup>Erkennung von Antischadsoftwaremodulen.</span><span class="sxs-lookup"><span data-stu-id="1ada2-340">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="1ada2-341">Dateitypblock für **Antischadsoftwarerichtlinie:** Hierbei handelt es sich um E-Mail-Nachrichten, die aufgrund des in der Nachricht identifizierten Typs bösartiger Dateien herausgefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-341">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="1ada2-342">**Dateidetonation**<sup>1:</sup>Erkennung durch sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="1ada2-342">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="1ada2-343">**Böswillige Dateireputation**</span><span class="sxs-lookup"><span data-stu-id="1ada2-343">**Malicious file reputation**</span></span>
  - <span data-ttu-id="1ada2-344">**Schadsoftware ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1ada2-344">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="1ada2-345">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="1ada2-345">**Others**</span></span>

  ![Ansicht der Erkennungstechnologie für Schadsoftware im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="1ada2-347">**Unterschlüsselung nach: Richtlinientyp** und **Daten anzeigen nach: E-Mail-Phishing \>** oder **Daten anzeigen nach: E-Mail-Schadsoftware: \>** Die folgenden Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-347">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="1ada2-348">**Antischadsoftware**</span><span class="sxs-lookup"><span data-stu-id="1ada2-348">**Anti-malware**</span></span>
  - <span data-ttu-id="1ada2-349">**Sichere Anlagen**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1ada2-349">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="1ada2-350">**Antiphishing**</span><span class="sxs-lookup"><span data-stu-id="1ada2-350">**Anti-phish**</span></span>
  - <span data-ttu-id="1ada2-351">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="1ada2-351">**Anti-spam**</span></span>
  - <span data-ttu-id="1ada2-352">**Nachrichtenflussregel** (auch als Transportregel bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="1ada2-352">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="1ada2-353">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="1ada2-353">**Others**</span></span>

  ![Richtlinientypansicht für Phishing-E-Mails im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="1ada2-355">**Aufschlüsseln nach: Zustellungsstatus** und **Daten anzeigen nach: E-Mail-Phishing \>** oder **Daten anzeigen nach: E-Mail-Schadsoftware: \>** Die folgenden Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="1ada2-356">**Übermittlung fehlgeschlagen**</span><span class="sxs-lookup"><span data-stu-id="1ada2-356">**Delivery failed**</span></span>
  - <span data-ttu-id="1ada2-357">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="1ada2-357">**Dropped**</span></span>
  - <span data-ttu-id="1ada2-358">**Weitergeleitet**</span><span class="sxs-lookup"><span data-stu-id="1ada2-358">**Forwarded**</span></span>
  - <span data-ttu-id="1ada2-359">**Gehostetes Postfach: Benutzerdefinierter Ordner**</span><span class="sxs-lookup"><span data-stu-id="1ada2-359">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="1ada2-360">**Gehostetes Postfach: Gelöschte Elemente**</span><span class="sxs-lookup"><span data-stu-id="1ada2-360">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="1ada2-361">**Gehostetes Postfach: Posteingang**</span><span class="sxs-lookup"><span data-stu-id="1ada2-361">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="1ada2-362">**Gehostetes Postfach: Junk**</span><span class="sxs-lookup"><span data-stu-id="1ada2-362">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="1ada2-363">**Lokaler Server: Bereitgestellt**</span><span class="sxs-lookup"><span data-stu-id="1ada2-363">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="1ada2-364">**Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="1ada2-364">**Quarantine**</span></span>

  ![Übermittlungsstatusansicht für Phishing-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="1ada2-366"><sup>1</sup> Defender nur für Office 365</span><span class="sxs-lookup"><span data-stu-id="1ada2-366"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="1ada2-367"><sup>2</sup> Zero-Hour Auto Purge (ZAP) ist in eigenständigem EOP nicht verfügbar (es funktioniert nur in Exchange Online Postfächern).</span><span class="sxs-lookup"><span data-stu-id="1ada2-367"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="1ada2-368">Wenn Sie auf **Filter** klicken, hängen die verfügbaren Filter von dem Diagramm ab, das Sie sich ansehen:</span><span class="sxs-lookup"><span data-stu-id="1ada2-368">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1ada2-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and end **date,** and the **Detection** value.</span><span class="sxs-lookup"><span data-stu-id="1ada2-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="1ada2-370">For **View data by: Message Override**, you can modify the report with the following filters:</span><span class="sxs-lookup"><span data-stu-id="1ada2-370">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1ada2-371">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-371">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1ada2-372">**Außerkraftsetzungsgrund**</span><span class="sxs-lookup"><span data-stu-id="1ada2-372">**Override Reason**</span></span>
  - <span data-ttu-id="1ada2-373">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="1ada2-373">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1ada2-374">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-374">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="1ada2-375">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="1ada2-375">**Domain**</span></span>

- <span data-ttu-id="1ada2-376">Für alle anderen Ansichten können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="1ada2-376">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1ada2-377">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-377">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1ada2-378">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="1ada2-378">**Detection**</span></span>
  - <span data-ttu-id="1ada2-379">**Geschützt durch:** **ATP** oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="1ada2-379">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="1ada2-380">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="1ada2-380">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1ada2-381">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-381">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="1ada2-382">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="1ada2-382">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="1ada2-383">Detailtabellenansicht für den Bedrohungsschutzstatusbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-383">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="1ada2-384">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich ansehen:</span><span class="sxs-lookup"><span data-stu-id="1ada2-384">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1ada2-385">**Anzeigen von Daten nach: Übersicht:** Es ist keine Schaltfläche für **die Ansichtsdetails-Tabelle** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1ada2-385">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="1ada2-386">**Anzeigen von Daten nach: Inhalt \> Schadsoftware**:</span><span class="sxs-lookup"><span data-stu-id="1ada2-386">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="1ada2-387">**Date**</span><span class="sxs-lookup"><span data-stu-id="1ada2-387">**Date**</span></span>
  - <span data-ttu-id="1ada2-388">**Standort**</span><span class="sxs-lookup"><span data-stu-id="1ada2-388">**Location**</span></span>
  - <span data-ttu-id="1ada2-389">**Weitergeleitet von**</span><span class="sxs-lookup"><span data-stu-id="1ada2-389">**Directed by**</span></span>
  - <span data-ttu-id="1ada2-390">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="1ada2-390">**Malware name**</span></span>

  <span data-ttu-id="1ada2-391">Wenn Sie in dieser Ansicht auf **Filter** klicken, können Sie den Bericht nach **Startdatum** und **Enddatum** sowie dem **Erkennungswert** ändern.</span><span class="sxs-lookup"><span data-stu-id="1ada2-391">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="1ada2-392">**Anzeigen von Daten nach: Nachrichtenüberschreibung:**</span><span class="sxs-lookup"><span data-stu-id="1ada2-392">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="1ada2-393">**Date**</span><span class="sxs-lookup"><span data-stu-id="1ada2-393">**Date**</span></span>
  - <span data-ttu-id="1ada2-394">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="1ada2-394">**Subject**</span></span>
  - <span data-ttu-id="1ada2-395">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1ada2-395">**Sender**</span></span>
  - <span data-ttu-id="1ada2-396">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="1ada2-396">**Recipients**</span></span>
  - <span data-ttu-id="1ada2-397">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="1ada2-397">**Detected by**</span></span>
  - <span data-ttu-id="1ada2-398">**Außerkraftsetzungsgrund**</span><span class="sxs-lookup"><span data-stu-id="1ada2-398">**Override Reason**</span></span>
  - <span data-ttu-id="1ada2-399">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="1ada2-399">**Source of Compromise**</span></span>
  - <span data-ttu-id="1ada2-400">**Tags**</span><span class="sxs-lookup"><span data-stu-id="1ada2-400">**Tags**</span></span>

  <span data-ttu-id="1ada2-401">Wenn Sie in dieser Ansicht auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="1ada2-401">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1ada2-402">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-402">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1ada2-403">**Außerkraftsetzungsgrund**</span><span class="sxs-lookup"><span data-stu-id="1ada2-403">**Override Reason**</span></span>
  - <span data-ttu-id="1ada2-404">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="1ada2-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1ada2-405">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="1ada2-406">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="1ada2-406">**Domain**</span></span>
  - <span data-ttu-id="1ada2-407">**Empfänger** (Beachten Sie, dass diese filterbare Eigenschaft nur in der Detailtabellenansicht verfügbar ist)</span><span class="sxs-lookup"><span data-stu-id="1ada2-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="1ada2-408">Alle anderen Diagramme:</span><span class="sxs-lookup"><span data-stu-id="1ada2-408">All other charts:</span></span>

  - <span data-ttu-id="1ada2-409">**Date**</span><span class="sxs-lookup"><span data-stu-id="1ada2-409">**Date**</span></span>
  - <span data-ttu-id="1ada2-410">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="1ada2-410">**Subject**</span></span>
  - <span data-ttu-id="1ada2-411">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1ada2-411">**Sender**</span></span>
  - <span data-ttu-id="1ada2-412">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="1ada2-412">**Recipients**</span></span>
  - <span data-ttu-id="1ada2-413">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="1ada2-413">**Detected by**</span></span>
  - <span data-ttu-id="1ada2-414">**Übermittlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="1ada2-414">**Delivery Status**</span></span>
  - <span data-ttu-id="1ada2-415">**Quelle der Kompromitt**</span><span class="sxs-lookup"><span data-stu-id="1ada2-415">**Source of Compromise**</span></span>
  - <span data-ttu-id="1ada2-416">**Tags**</span><span class="sxs-lookup"><span data-stu-id="1ada2-416">**Tags**</span></span>

  <span data-ttu-id="1ada2-417">Wenn Sie auf **"Filter"** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="1ada2-417">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1ada2-418">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="1ada2-418">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1ada2-419">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="1ada2-419">**Detection**</span></span>
  - <span data-ttu-id="1ada2-420">**Geschützt durch:** **Defender für Office 365** oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="1ada2-420">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="1ada2-421">**Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="1ada2-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1ada2-422">Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="1ada2-423">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="1ada2-423">**Domain**</span></span>
  - <span data-ttu-id="1ada2-424">**Empfänger** (Beachten Sie, dass diese filterbare Eigenschaft nur in der Detailtabellenansicht verfügbar ist)</span><span class="sxs-lookup"><span data-stu-id="1ada2-424">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="1ada2-425">Bericht über häufigste Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="1ada2-425">Top malware report</span></span>

<span data-ttu-id="1ada2-426">Der **Bericht "Häufigste Schadsoftware"** zeigt die verschiedenen Arten von Schadsoftware, die vom [Schutz vor Schadsoftware in EOP](anti-malware-protection.md)erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-426">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="1ada2-427">Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **"E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte",** und klicken Sie auf **"Details anzeigen"** unter **"Häufigste Schadsoftware".**</span><span class="sxs-lookup"><span data-stu-id="1ada2-427">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Top malware**.</span></span> <span data-ttu-id="1ada2-428">Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="1ada2-428">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Das am häufigsten verwendete Malware-Widget im Dashboard "Berichte"](../../media/top-malware-report-widget.png)

<span data-ttu-id="1ada2-430">Wenn Sie den Mauszeiger über einen Wedge im Kreisdiagramm bewegen, sehen Sie den Namen einer Art von Schadsoftware und wie viele Nachrichten als Schadsoftware erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="1ada2-430">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Ansicht des Berichts über häufigste Schadsoftware](../../media/top-malware-report-view.png)

<span data-ttu-id="1ada2-432">Wenn Sie auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Details angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ada2-432">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="1ada2-433">**Häufigste Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="1ada2-433">**Top malware**</span></span>
- <span data-ttu-id="1ada2-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="1ada2-434">**Count**</span></span>

<span data-ttu-id="1ada2-435">Wenn Sie in der Berichtsansicht oder in der Detailtabellenansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="1ada2-435">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="1ada2-436">URL-Bedrohungsschutzbericht</span><span class="sxs-lookup"><span data-stu-id="1ada2-436">URL threat protection report</span></span>

<span data-ttu-id="1ada2-437">Der **URL-Bedrohungsschutzbericht** ist in Microsoft Defender für Office 365 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1ada2-437">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="1ada2-438">Weitere Informationen finden Sie unter [URL Threat Protection Report](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="1ada2-438">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="1ada2-439">Bericht über vom Benutzer gemeldete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="1ada2-439">User reported messages report</span></span>

<span data-ttu-id="1ada2-440">Der Bericht **"Vom Benutzer gemeldete Nachrichten"** enthält Informationen zu E-Mail-Nachrichten, die Benutzer mithilfe des [Add-Ins "Nachricht melden"](enable-the-report-message-add-in.md) oder des [Add-Ins "Berichtsphishing"](enable-the-report-phish-add-in.md)als Junk- oder Phishingversuche oder als gute E-Mails gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="1ada2-440">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="1ada2-441">Details sind für jede Nachricht verfügbar, einschließlich des Grunds für die Zustellung, z. B. eine Für Ihre Organisation konfigurierte Spamrichtlinienausnahme oder E-Mail-Flussregel.</span><span class="sxs-lookup"><span data-stu-id="1ada2-441">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="1ada2-442">Wählen Sie zum Anzeigen von Details ein Element in der Benutzerberichtsliste aus, und zeigen Sie dann die Informationen auf den Registerkarten **Zusammenfassung** und Details an. </span><span class="sxs-lookup"><span data-stu-id="1ada2-442">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![Der Bericht "Vom Benutzer gemeldete Nachrichten" zeigt Nachrichten an, die als Junk-, nicht Junk- oder Phishingversuche gekennzeichnet sind.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="1ada2-444">To view this report, in the [Microsoft 365 Defender portal,](https://security.microsoft.com)go to **Reports** Email \> **& collaboration** \> **Email & collaboration reports** \> **User reported messages**.</span><span class="sxs-lookup"><span data-stu-id="1ada2-444">To view this report, in the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span>

- <span data-ttu-id="1ada2-445">Go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports** User \> **reported messages**.</span><span class="sxs-lookup"><span data-stu-id="1ada2-445">Go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** \> **User reported messages**.</span></span>

![Wählen Sie im Microsoft 365 Defender-Portal \> "Berichts-E-Mail & Zusammenarbeit \> E-Mail & Berichte zur Zusammenarbeit \> Gemeldete Benutzernachrichten" aus.](../../media/user-reported-messages.png)

> [!IMPORTANT]
> <span data-ttu-id="1ada2-447">Damit der Bericht über vom Benutzer gemeldete Nachrichten ordnungsgemäß funktioniert, muss die **Überwachungsprotokollierung** für Ihre Office 365 Umgebung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="1ada2-447">In order for the User reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="1ada2-448">Dies geschieht in der Regel von einer Person, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1ada2-448">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="1ada2-449">Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren Microsoft 365 Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-449">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="1ada2-450">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="1ada2-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="1ada2-451">Um die in diesem Artikel beschriebenen Berichte anzuzeigen und zu verwenden, müssen Sie Mitglied einer der folgenden Rollengruppen im Microsoft 365 Defender-Portal sein:</span><span class="sxs-lookup"><span data-stu-id="1ada2-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="1ada2-452">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="1ada2-452">**Organization Management**</span></span>
- <span data-ttu-id="1ada2-453">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="1ada2-453">**Security Administrator**</span></span>
- <span data-ttu-id="1ada2-454">**Sicherheitsleseberechtigter**</span><span class="sxs-lookup"><span data-stu-id="1ada2-454">**Security Reader**</span></span>
- <span data-ttu-id="1ada2-455">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="1ada2-455">**Global Reader**</span></span>

<span data-ttu-id="1ada2-456">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-456">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="1ada2-457">**Hinweis:** Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ada2-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1ada2-458">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1ada2-458">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="1ada2-459">Was geschieht, wenn in den Berichten keine Daten angezeigt werden?</span><span class="sxs-lookup"><span data-stu-id="1ada2-459">What if the reports aren't showing data?</span></span>

<span data-ttu-id="1ada2-460">Wenn in Ihren Berichten keine Daten angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="1ada2-460">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="1ada2-461">Weitere Informationen finden Sie unter ["Schutz vor Bedrohungen".](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="1ada2-461">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1ada2-462">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1ada2-462">Related topics</span></span>

[<span data-ttu-id="1ada2-463">Antispam- und Antischadsoftwareschutz in EOP</span><span class="sxs-lookup"><span data-stu-id="1ada2-463">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="1ada2-464">Intelligente Berichte und Einblicke im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="1ada2-464">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="1ada2-465">Anzeigen von Nachrichtenflussberichten im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="1ada2-465">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="1ada2-466">Anzeigen von Berichten für Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="1ada2-466">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
