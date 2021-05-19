---
title: Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center
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
description: Erfahren Sie, wie Sie E-Mail-Sicherheitsberichte für Ihre Organisation finden und verwenden. E-Mail-Sicherheitsberichte sind im Security & Compliance Center verfügbar.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11fe6fd76d21b2dbd7a3e651d40efaa79f675a43
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52531028"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="23545-104">Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="23545-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="23545-105">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="23545-105">**Applies to**</span></span>
- [<span data-ttu-id="23545-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="23545-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="23545-107">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="23545-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="23545-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23545-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="23545-109">Im Security & Compliance [Center](https://protection.office.com) stehen verschiedene Berichte zur Verfügung, mit deren Hilfe Sie sehen können, wie E-Mail-Sicherheitsfeatures wie Antispam-, Anschmierungs- und Verschlüsselungsfunktionen in Microsoft 365 Ihre Organisation schützen.</span><span class="sxs-lookup"><span data-stu-id="23545-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="23545-110">Wenn Sie über die [erforderlichen Berechtigungen verfügen,](#what-permissions-are-needed-to-view-these-reports)können Sie diese Berichte im Security & Compliance Center anzeigen, indem Sie zu **Reports** \> **Dashboard gehen.**</span><span class="sxs-lookup"><span data-stu-id="23545-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="23545-111">Öffnen Sie , um direkt zum Dashboard Berichte zu <https://protection.office.com/insightdashboard> wechseln.</span><span class="sxs-lookup"><span data-stu-id="23545-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="23545-113">Bericht "Gefährdete Benutzer"</span><span class="sxs-lookup"><span data-stu-id="23545-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="23545-114">Dieser Bericht ist in Microsoft 365 organisationen mit Exchange Online verfügbar.</span><span class="sxs-lookup"><span data-stu-id="23545-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="23545-115">Sie ist in eigenständigen Organisationen Exchange Online Protection (EOP) nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="23545-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="23545-116">Der **Bericht "Gefährdete** Benutzer" zeigt die Anzahl  der  Benutzerkonten an, die innerhalb der letzten 7 Tage als verdächtig oder eingeschränkt gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="23545-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="23545-117">Konten in einem dieser Zustände sind problematisch oder sogar gefährdet.</span><span class="sxs-lookup"><span data-stu-id="23545-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="23545-118">Bei häufiger Verwendung können Sie den Bericht verwenden, um Spitzen und sogar Trends in verdächtigen oder eingeschränkten Konten zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="23545-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="23545-119">Weitere Informationen zu gefährdeten Benutzern finden Sie unter [Antworten auf ein gefährdetes E-Mail-Konto](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="23545-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget "Gefährdete Benutzer" im Dashboard "Berichte"](../../media/compromised-users-report-widget.png)

<span data-ttu-id="23545-121">Die Aggregatansicht zeigt Daten für die letzten 90 Tage an, und die Detailansicht zeigt Daten für die letzten 30 Tage an.</span><span class="sxs-lookup"><span data-stu-id="23545-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="23545-122">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen \>  Sie **Gefährdete Benutzer aus.**</span><span class="sxs-lookup"><span data-stu-id="23545-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="23545-123">Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=CompromisedUsers> wechseln.</span><span class="sxs-lookup"><span data-stu-id="23545-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="23545-124">Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **Filter klicken** und einen oder mehrere der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="23545-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="23545-125">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="23545-126">**Verdächtig:** Das Benutzerkonto hat verdächtige E-Mails gesendet und riskiert, dass das Senden von E-Mails eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="23545-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="23545-127">**Eingeschränkt:** Das Benutzerkonto wurde aufgrund hochgradig verdächtiger Muster vom Senden von E-Mails eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="23545-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Berichtsansicht im Bericht "Gefährdete Benutzer"](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="23545-129">Wenn Sie auf **Detailtabelle anzeigen klicken,** sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="23545-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="23545-130">**Erstellungszeit**</span><span class="sxs-lookup"><span data-stu-id="23545-130">**Creation time**</span></span>
- <span data-ttu-id="23545-131">**Benutzer-ID**</span><span class="sxs-lookup"><span data-stu-id="23545-131">**User ID**</span></span>
- <span data-ttu-id="23545-132">**Action**</span><span class="sxs-lookup"><span data-stu-id="23545-132">**Action**</span></span>

<span data-ttu-id="23545-133">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="23545-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="23545-134">Verschlüsselungsbericht</span><span class="sxs-lookup"><span data-stu-id="23545-134">Encryption report</span></span>

<span data-ttu-id="23545-135">Der **Verschlüsselungsbericht ist** in EOP verfügbar (Abonnements mit Postfächern in Exchange Online oder eigenständigem EOP ohne Exchange Online Postfächer).</span><span class="sxs-lookup"><span data-stu-id="23545-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="23545-136">Das Sicherheitsteam Ihrer Organisation kann informationen in diesem Bericht verwenden, um Muster zu identifizieren und Richtlinien proaktiv für vertrauliche E-Mail-Nachrichten anzuwenden oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="23545-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="23545-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="23545-137">For example:</span></span>

- <span data-ttu-id="23545-138">Wenn eine hohe Anzahl von von Benutzern verschlüsselten E-Mail-Nachrichten angezeigt wird, sollten Sie eine Verschlüsselungsrichtlinie hinzufügen, um die Verschlüsselung für bestimmte Verwendungsfälle zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="23545-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="23545-139">Weitere Informationen finden Sie unter [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="23545-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="23545-140">Wenn Eine Reihe von Verschlüsselungsvorlagen verfügbar ist, aber niemand sie verwendet, können Sie untersuchen, ob Benutzer Featureschulungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="23545-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="23545-141">Die Aggregatansicht ermöglicht das Filtern für die letzten 90 Tage, während die Detailansicht das Filtern für 10 Tage zulässt.</span><span class="sxs-lookup"><span data-stu-id="23545-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="23545-142">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln **Sie** zu Berichtsdashboard, und wählen \>  Sie **Verschlüsselungsbericht aus.**</span><span class="sxs-lookup"><span data-stu-id="23545-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="23545-143">Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=EncryptionReport> wechseln.</span><span class="sxs-lookup"><span data-stu-id="23545-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="23545-144">Weitere Informationen zur Verschlüsselung finden Sie unter [E-Mail-Verschlüsselung in Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="23545-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="23545-145">Berichtsansicht für den Verschlüsselungsbericht</span><span class="sxs-lookup"><span data-stu-id="23545-145">Report view for the Encryption report</span></span>

<span data-ttu-id="23545-146">Sie können die folgenden Filter im Diagramm verwenden:</span><span class="sxs-lookup"><span data-stu-id="23545-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="23545-147">**Daten nach anzeigen: Nachrichtenverschlüsselungsbericht** und **Aufschlüsseln nach: Verschlüsselungsmethode**: Die folgenden Verschlüsselungsmethoden sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="23545-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="23545-148">**Verschlüsselung nach Benutzer**</span><span class="sxs-lookup"><span data-stu-id="23545-148">**Encryption by user**</span></span>
  - <span data-ttu-id="23545-149">**Verschlüsselung nach Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="23545-149">**Encryption by policy**</span></span>

  <span data-ttu-id="23545-150">Wenn Sie auf **Filter** klicken, können Sie das Diagramm mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="23545-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="23545-151">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="23545-152">Verschlüsselungsmethode.</span><span class="sxs-lookup"><span data-stu-id="23545-152">Encryption method.</span></span>
  - <span data-ttu-id="23545-153">Verschlüsselungsvorlage.</span><span class="sxs-lookup"><span data-stu-id="23545-153">Encryption template.</span></span>

- <span data-ttu-id="23545-154">**Daten nach anzeigen: Nachrichtenverschlüsselungsbericht** und **Aufschlüsseln nach: Verschlüsselungsvorlage**: Die folgenden Verschlüsselungsmethoden sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="23545-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="23545-155">**Nicht weiterleiten**</span><span class="sxs-lookup"><span data-stu-id="23545-155">**Do not forward**</span></span>
  - <span data-ttu-id="23545-156">**Nur verschlüsseln**</span><span class="sxs-lookup"><span data-stu-id="23545-156">**Encrypt only**</span></span>
  - <span data-ttu-id="23545-157">**OME previous**</span><span class="sxs-lookup"><span data-stu-id="23545-157">**OME previous**</span></span>
  - <span data-ttu-id="23545-158">**Custom**</span><span class="sxs-lookup"><span data-stu-id="23545-158">**Custom**</span></span>

  <span data-ttu-id="23545-159">Wenn Sie auf **Filter** klicken, können Sie das Diagramm mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="23545-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="23545-160">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="23545-161">Verschlüsselungsmethode</span><span class="sxs-lookup"><span data-stu-id="23545-161">Encryption method</span></span>
  - <span data-ttu-id="23545-162">Verschlüsselungsvorlage</span><span class="sxs-lookup"><span data-stu-id="23545-162">Encryption template</span></span>

- <span data-ttu-id="23545-163">**Daten anzeigen nach: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span><span class="sxs-lookup"><span data-stu-id="23545-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="23545-164">Wenn Sie auf **Filter** klicken, können Sie ein **Startdatum und** **ein Enddatum auswählen.**</span><span class="sxs-lookup"><span data-stu-id="23545-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="23545-165">Detailtabelle für den Verschlüsselungsbericht</span><span class="sxs-lookup"><span data-stu-id="23545-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="23545-166">Wenn Sie auf **Detailtabelle anzeigen klicken,** hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich angeschaut haben:</span><span class="sxs-lookup"><span data-stu-id="23545-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="23545-167">**Aufschlüsseln nach: Verschlüsselungsmethode oder** **Aufschlüsseln nach: Verschlüsselungsvorlage**: Die folgenden Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23545-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="23545-168">**Date**</span><span class="sxs-lookup"><span data-stu-id="23545-168">**Date**</span></span>
  - <span data-ttu-id="23545-169">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="23545-169">**Sender address**</span></span>
  - <span data-ttu-id="23545-170">**Verschlüsselungsvorlage**</span><span class="sxs-lookup"><span data-stu-id="23545-170">**Encryption template**</span></span>
  - <span data-ttu-id="23545-171">**Verschlüsselungsmethode**</span><span class="sxs-lookup"><span data-stu-id="23545-171">**Encryption method**</span></span>
  - <span data-ttu-id="23545-172">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="23545-172">**Recipient address**</span></span>
  - <span data-ttu-id="23545-173">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="23545-173">**Subject**</span></span>

- <span data-ttu-id="23545-174">**Daten anzeigen nach: Top 5 recipient domains**:</span><span class="sxs-lookup"><span data-stu-id="23545-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="23545-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="23545-175">**Date**</span></span>
  - <span data-ttu-id="23545-176">**Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="23545-176">**Recipient domain**</span></span>
  - <span data-ttu-id="23545-177">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="23545-177">**Message count**</span></span>

<span data-ttu-id="23545-178">Wenn Sie in **einer** Detailtabelle auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="23545-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="23545-179">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="23545-180">Verschlüsselungsmethode</span><span class="sxs-lookup"><span data-stu-id="23545-180">Encryption method</span></span>
- <span data-ttu-id="23545-181">Verschlüsselungsvorlage</span><span class="sxs-lookup"><span data-stu-id="23545-181">Encryption template</span></span>

<span data-ttu-id="23545-182">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="23545-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="23545-183">E-Mailflow-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="23545-183">Mailflow status report</span></span>

<span data-ttu-id="23545-184">Der **Mailflow-Statusbericht** enthält Informationen zu Schadsoftware, Spam, Phishing und blockierten Edgenachrichten.</span><span class="sxs-lookup"><span data-stu-id="23545-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="23545-185">Weitere Informationen finden Sie unter [Mailflow-Statusbericht](view-mail-flow-reports.md#mailflow-status-report).</span><span class="sxs-lookup"><span data-stu-id="23545-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="23545-186">Schadsoftwareerkennungen im E-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="23545-186">Malware detections in email report</span></span>

<span data-ttu-id="23545-187">Die **Schadsoftwareerkennungen im** E-Mail-Bericht zeigen Informationen zu Schadsoftwareerkennungen in eingehenden und ausgehenden E-Mail-Nachrichten (Schadsoftware, die von Exchange Online Protection oder EOP erkannt wird).</span><span class="sxs-lookup"><span data-stu-id="23545-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="23545-188">Weitere Informationen zum Schutz vor Schadsoftware in EOP finden Sie unter [An malware protection in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="23545-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="23545-189">Der Aggregatansichtsfilter lässt 90 Tage zu, während der Detailtabelle-Filter nur 10 Tage zulässt.</span><span class="sxs-lookup"><span data-stu-id="23545-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="23545-190">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen Sie \>  **Schadsoftwareerkennungen in E-Mail aus.**</span><span class="sxs-lookup"><span data-stu-id="23545-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="23545-191">Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=MalwareDetections> wechseln.</span><span class="sxs-lookup"><span data-stu-id="23545-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Schadsoftwareerkennungen im E-Mail-Widget im Dashboard "Berichte"](../../media/malware-detections-widget.png)

<span data-ttu-id="23545-193">Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **Filter klicken** und folgende Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="23545-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="23545-194">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="23545-195">**Eingehendes**</span><span class="sxs-lookup"><span data-stu-id="23545-195">**Inbound**</span></span>
- <span data-ttu-id="23545-196">**Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="23545-196">**Outbound**</span></span>

![Berichtsansicht im Bericht zur Erkennung von Schadsoftware im E-Mail-Bericht](../../media/malware-detections-report-view.png)

<span data-ttu-id="23545-198">Wenn Sie auf **Detailtabelle anzeigen klicken,** sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="23545-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="23545-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="23545-199">**Date**</span></span>
- <span data-ttu-id="23545-200">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="23545-200">**Sender address**</span></span>
- <span data-ttu-id="23545-201">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="23545-201">**Recipient address**</span></span>
- <span data-ttu-id="23545-202">**Nachrichten-ID**: Im **Kopfzeilenfeld Message-ID** im Nachrichtenkopf verfügbar und sollte eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="23545-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="23545-203">Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (beachten Sie die eckigen Klammern).</span><span class="sxs-lookup"><span data-stu-id="23545-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="23545-204">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="23545-204">**Subject**</span></span>
- <span data-ttu-id="23545-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="23545-205">**Filename**</span></span>
- <span data-ttu-id="23545-206">**Schadsoftwarename**</span><span class="sxs-lookup"><span data-stu-id="23545-206">**Malware name**</span></span>

<span data-ttu-id="23545-207">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="23545-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="23545-208">Bericht über die E-Mail-Latenz</span><span class="sxs-lookup"><span data-stu-id="23545-208">Mail latency report</span></span>

<span data-ttu-id="23545-209">Der **Bericht über die E-Mail-Latenz** enthält Informationen zur E-Mail-Zustellung und Detonationslatenz in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="23545-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="23545-210">Weitere Informationen finden Sie unter [E-Mail-Latenzbericht](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="23545-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="23545-211">Gesendeter und empfangener E-Mail-Bericht</span><span class="sxs-lookup"><span data-stu-id="23545-211">Sent and received email report</span></span>

<span data-ttu-id="23545-212">Der **Bericht Gesendete und** empfangene E-Mail enthält Informationen zu Schadsoftware, Spam, Nachrichtenflussregeln (auch als Transportregeln bezeichnet) und erweiterten Schadsoftwareerkennungen, nachdem E-Mails in den Dienst eingeflossen sind.</span><span class="sxs-lookup"><span data-stu-id="23545-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="23545-213">Weitere Informationen finden Sie unter [Gesendeter und empfangener E-Mail-Bericht](view-mail-flow-reports.md#sent-and-received-email-report).</span><span class="sxs-lookup"><span data-stu-id="23545-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="23545-214">Spamerkennungsbericht</span><span class="sxs-lookup"><span data-stu-id="23545-214">Spam detections report</span></span>

<span data-ttu-id="23545-215">Der **Bericht "Spamerkennungen"** zeigt Spam-E-Mail-Nachrichten an, die von EOP blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="23545-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="23545-216">Nachrichten werden einzeln gezählt, nicht pro Empfänger.</span><span class="sxs-lookup"><span data-stu-id="23545-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="23545-217">Wenn beispielsweise dieselbe Spamnachricht an 100 Empfänger in Ihrer Organisation gesendet wurde, zählt sie als eine Nachricht.</span><span class="sxs-lookup"><span data-stu-id="23545-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="23545-218">Die Aggregatansicht ermöglicht eine Filterung von 90 Tagen, während die Detailtabelle eine Filterung von 10 Tagen zulässt.</span><span class="sxs-lookup"><span data-stu-id="23545-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="23545-219">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen \>  Sie **Spamerkennungen aus.**</span><span class="sxs-lookup"><span data-stu-id="23545-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="23545-220">Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=SpamDetections> wechseln.</span><span class="sxs-lookup"><span data-stu-id="23545-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget "Spamerkennungen" im Dashboard "Berichte"](../../media/spam-detections-report-widget.png)

<span data-ttu-id="23545-222">Weitere Informationen zum Antispamschutz finden Sie unter [Antispamschutz in EOP](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="23545-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="23545-223">Berichtsansicht für den Bericht "Spamerkennungen"</span><span class="sxs-lookup"><span data-stu-id="23545-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="23545-224">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="23545-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="23545-225">**Aufbrechen nach: Aktion**: Die folgenden Ereignistypen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23545-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="23545-226">**Gefilterte Spaminhalte**</span><span class="sxs-lookup"><span data-stu-id="23545-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="23545-227">**Spam-IP-Block**</span><span class="sxs-lookup"><span data-stu-id="23545-227">**Spam IP block**</span></span>
  - <span data-ttu-id="23545-228">**Spam-Umschlagblock**</span><span class="sxs-lookup"><span data-stu-id="23545-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="23545-229">**Spam-DBEB-Filter:** Verzeichnisbasierte Edgeblockierung (DBEB)</span><span class="sxs-lookup"><span data-stu-id="23545-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="23545-230">Wenn Sie den Mauszeiger auf einen Tag (Datenpunkt) im Diagramm zeigen, können Sie sehen, wie viele Elemente an diesem Tag blockiert wurden und wie diese Elemente kategorisiert sind.</span><span class="sxs-lookup"><span data-stu-id="23545-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Aktionsansicht im Bericht "Spamerkennungen"](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="23545-232">**Aufbrechen nach: Richtung**: Die folgenden Wegbeschreibungen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23545-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="23545-233">**Eingehendes**</span><span class="sxs-lookup"><span data-stu-id="23545-233">**Inbound**</span></span>
  - <span data-ttu-id="23545-234">**Ausgehend**</span><span class="sxs-lookup"><span data-stu-id="23545-234">**Outbound**</span></span>

  ![Richtungsansicht im Bericht "Spamerkennungen"](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="23545-236">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="23545-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="23545-237">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="23545-238">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="23545-238">Direction values</span></span>
- <span data-ttu-id="23545-239">Ereignistypwerte</span><span class="sxs-lookup"><span data-stu-id="23545-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="23545-240">Detailtabelle für den Bericht "Spamerkennungen"</span><span class="sxs-lookup"><span data-stu-id="23545-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="23545-241">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23545-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="23545-242">**Date**</span><span class="sxs-lookup"><span data-stu-id="23545-242">**Date**</span></span>
- <span data-ttu-id="23545-243">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="23545-243">**Sender address**</span></span>
- <span data-ttu-id="23545-244">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="23545-244">**Recipient address**</span></span>
- <span data-ttu-id="23545-245">**Ereignistyp**</span><span class="sxs-lookup"><span data-stu-id="23545-245">**Event type**</span></span>
- <span data-ttu-id="23545-246">**Action**</span><span class="sxs-lookup"><span data-stu-id="23545-246">**Action**</span></span>
- <span data-ttu-id="23545-247">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="23545-247">**Subject**</span></span>

<span data-ttu-id="23545-248">Wenn Sie in **einer** Detailtabelle auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="23545-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="23545-249">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="23545-250">Richtungswerte</span><span class="sxs-lookup"><span data-stu-id="23545-250">Direction values</span></span>
- <span data-ttu-id="23545-251">Ereignistypwerte</span><span class="sxs-lookup"><span data-stu-id="23545-251">Event type values</span></span>

<span data-ttu-id="23545-252">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="23545-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="23545-253">Bericht über Spooferkennungen</span><span class="sxs-lookup"><span data-stu-id="23545-253">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="23545-254">Der bericht über verbesserte Spooferkennungen, wie in diesem Artikel beschrieben, befindet sich in Vorschau, kann geändert werden und ist nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="23545-254">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="23545-255">In der älteren Version des Berichts wurden nur gute **E-Mails und** **Als Spam erwischt gezeigt.**</span><span class="sxs-lookup"><span data-stu-id="23545-255">The older version of the report showed only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="23545-256">Der **Bericht "Spooferkennungen"** enthält Informationen zu Nachrichten, die aufgrund von Spoofing blockiert oder zugelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="23545-256">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="23545-257">Weitere Informationen zum Spoofing finden Sie unter [Anti-Spoofing Protection in EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="23545-257">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="23545-258">Die aggregierte Ansicht des Berichts ermöglicht eine Filterung von 45 Tagen, während die Detailansicht nur zehn <sup>\*</sup> Tage Filterung zulässt.</span><span class="sxs-lookup"><span data-stu-id="23545-258">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="23545-259"><sup>\*</sup> Schließlich können Sie bis zu 90 Tage Filterung verwenden.</span><span class="sxs-lookup"><span data-stu-id="23545-259"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="23545-260">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen Sie \>  **Spooferkennungen aus.**</span><span class="sxs-lookup"><span data-stu-id="23545-260">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="23545-261">Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=SpoofMailReport> wechseln.</span><span class="sxs-lookup"><span data-stu-id="23545-261">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widget "Spooferkennungen" im Dashboard "Berichte"](../../media/spoof-detections-widget.png)

<span data-ttu-id="23545-263">Wenn Sie den Mauszeiger auf einen Tag (Datenpunkt) im Diagramm zeigen, können Sie sehen, wie viele gefälschte Nachrichten erkannt wurden und warum.</span><span class="sxs-lookup"><span data-stu-id="23545-263">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="23545-264">Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **Filter klicken** und einen oder mehrere der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="23545-264">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="23545-265">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-265">**Start date** and **End date**</span></span>

- <span data-ttu-id="23545-266">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="23545-266">**Result**</span></span>
  - <span data-ttu-id="23545-267">**Pass**</span><span class="sxs-lookup"><span data-stu-id="23545-267">**Pass**</span></span>
  - <span data-ttu-id="23545-268">**Fail**</span><span class="sxs-lookup"><span data-stu-id="23545-268">**Fail**</span></span>
  - <span data-ttu-id="23545-269">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="23545-269">**SoftPass**</span></span>
  - <span data-ttu-id="23545-270">**Keine**</span><span class="sxs-lookup"><span data-stu-id="23545-270">**None**</span></span>
  - <span data-ttu-id="23545-271">**Other**</span><span class="sxs-lookup"><span data-stu-id="23545-271">**Other**</span></span>

- <span data-ttu-id="23545-272">**Spooftyp**: **Intern** und **Extern**</span><span class="sxs-lookup"><span data-stu-id="23545-272">**Spoof type**: **Internal** and **External**</span></span>

![Berichtsansicht im Bericht "Spooferkennungen"](../../media/spoof-detections-report-view.png)

<span data-ttu-id="23545-274">Wenn Sie auf **Detailtabelle anzeigen klicken,** sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="23545-274">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="23545-275">**Date**</span><span class="sxs-lookup"><span data-stu-id="23545-275">**Date**</span></span>
- <span data-ttu-id="23545-276">**Spoofed user**</span><span class="sxs-lookup"><span data-stu-id="23545-276">**Spoofed user**</span></span>
- <span data-ttu-id="23545-277">**Senden von Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="23545-277">**Sending infrastructure**</span></span>
- <span data-ttu-id="23545-278">**Spooftyp**</span><span class="sxs-lookup"><span data-stu-id="23545-278">**Spoof type**</span></span>
- <span data-ttu-id="23545-279">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="23545-279">**Result**</span></span>
- <span data-ttu-id="23545-280">**Ergebniscode**</span><span class="sxs-lookup"><span data-stu-id="23545-280">**Result code**</span></span>
- <span data-ttu-id="23545-281">**SPF**</span><span class="sxs-lookup"><span data-stu-id="23545-281">**SPF**</span></span>
- <span data-ttu-id="23545-282">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="23545-282">**DKIM**</span></span>
- <span data-ttu-id="23545-283">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="23545-283">**DMARC**</span></span>
- <span data-ttu-id="23545-284">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="23545-284">**Message count**</span></span>

<span data-ttu-id="23545-285">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="23545-285">To go back to the report view, click **View report**.</span></span>

<span data-ttu-id="23545-286">Weitere Informationen zu Ergebniscodes für die zusammengesetzte Authentifizierung finden Sie unter [Antispamnachrichtenkopfzeilen in Microsoft 365](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="23545-286">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="23545-287">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="23545-287">Threat protection status report</span></span>

<span data-ttu-id="23545-288">Der **Statusbericht zum** Bedrohungsschutz ist sowohl in EOP als auch in Microsoft Defender für Office 365; Die Berichte enthalten jedoch unterschiedliche Daten.</span><span class="sxs-lookup"><span data-stu-id="23545-288">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="23545-289">Beispielsweise können EOP-Kunden Informationen zu Schadsoftware anzeigen, die in E-Mails erkannt wurden, aber keine Informationen zu schädlichen Dateien, die von sicheren Anlagen für [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="23545-289">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="23545-290">Der Bericht enthält die Anzahl von E-Mail-Nachrichten mit schädlichem Inhalt, z. B. Dateien oder Websiteadressen (URLs), die vom Antiksoftwaremodul blockiert wurden, zap [(Zero-Hour Auto Purge)](zero-hour-auto-purge.md)und Defender für Office 365-Features wie sichere [Links,](safe-links.md)sichere [Anlagen](safe-attachments.md)und [Antiphishing.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="23545-290">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="23545-291">Sie können diese Informationen verwenden, um Trends zu identifizieren oder zu bestimmen, ob Organisationsrichtlinien anpassungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="23545-291">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="23545-292">**Hinweis:** Es ist wichtig zu wissen, dass eine Nachricht, wenn sie an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="23545-292">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="23545-293">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** \> **Berichtsdashboard,** und wählen Sie **Bedrohungsschutzstatus aus.**</span><span class="sxs-lookup"><span data-stu-id="23545-293">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="23545-294">Öffnen Sie eine der folgenden URLs, um direkt zum Bericht zu wechseln:</span><span class="sxs-lookup"><span data-stu-id="23545-294">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="23545-295">Microsoft Defender für Office 365:<https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="23545-295">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="23545-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="23545-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Bedrohungsschutzstatus-Widget im Dashboard "Berichte"](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="23545-298">Standardmäßig zeigt das Diagramm Daten für die letzten 7 Tage an.</span><span class="sxs-lookup"><span data-stu-id="23545-298">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="23545-299">Wenn Sie auf **Filter** klicken, können Sie einen Datumsbereich von 90 Tagen auswählen (Testabonnements können auf 30 Tage beschränkt sein).</span><span class="sxs-lookup"><span data-stu-id="23545-299">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="23545-300">Die Detailtabelle ermöglicht das Filtern für 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="23545-300">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="23545-301">Berichtsansicht für den Statusbericht zum Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="23545-301">Report view for the Threat protection status report</span></span>

<span data-ttu-id="23545-302">Die folgenden Ansichten sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="23545-302">The following views are available:</span></span>

- <span data-ttu-id="23545-303">**Daten anzeigen nach: Übersicht**: Die folgenden Erkennungsinformationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23545-303">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="23545-304">**E-Mail-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="23545-304">**Email malware**</span></span>
  - <span data-ttu-id="23545-305">**E-Mail-Phish**</span><span class="sxs-lookup"><span data-stu-id="23545-305">**Email phish**</span></span>
  - <span data-ttu-id="23545-306">**Schadsoftware für Inhalte**</span><span class="sxs-lookup"><span data-stu-id="23545-306">**Content malware**</span></span>

  ![Übersichtsansicht im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="23545-308">**Anzeigen von Daten nach: Content \> Schadsoftware**<sup>1</sup>: Die folgenden Informationen werden für Microsoft Defender für Office 365 angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23545-308">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="23545-309">**An malware engine:** Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="23545-309">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="23545-310">**Dateidetonation:** Schädliche Dateien, die von sicheren Anlagen für SharePoint, OneDrive [und Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="23545-310">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![Ansicht von Schadsoftware für Inhalte im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="23545-312">**Daten anzeigen nach: Message Override**: Die folgenden Informationen zum Außerkraftsetzungsgrund werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23545-312">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="23545-313">**Lokales Überspringen**</span><span class="sxs-lookup"><span data-stu-id="23545-313">**On-premises skip**</span></span>
  - <span data-ttu-id="23545-314">**IP Allow**</span><span class="sxs-lookup"><span data-stu-id="23545-314">**IP Allow**</span></span>
  - <span data-ttu-id="23545-315">**Nachrichtenflussregel**</span><span class="sxs-lookup"><span data-stu-id="23545-315">**Mail flow rule**</span></span>
  - <span data-ttu-id="23545-316">**Absender zulassen**</span><span class="sxs-lookup"><span data-stu-id="23545-316">**Sender allow**</span></span>
  - <span data-ttu-id="23545-317">**Domänen zulassen**</span><span class="sxs-lookup"><span data-stu-id="23545-317">**Domain allow**</span></span>
  - <span data-ttu-id="23545-318">**ZAP nicht aktiviert**</span><span class="sxs-lookup"><span data-stu-id="23545-318">**ZAP not enabled**</span></span>
  - <span data-ttu-id="23545-319">**Junk-E-Mail-Ordner nicht aktiviert**</span><span class="sxs-lookup"><span data-stu-id="23545-319">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="23545-320">**Sicherer Absender des Benutzers**</span><span class="sxs-lookup"><span data-stu-id="23545-320">**User Safe Sender**</span></span>
  - <span data-ttu-id="23545-321">**Benutzersichere Domäne**</span><span class="sxs-lookup"><span data-stu-id="23545-321">**User Safe Domain**</span></span>

  ![Nachrichtenüberschreibungsansicht im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="23545-323">**Unterlegen nach: Erkennungstechnologie und** **Daten anzeigen nach: E-Mail-Phish \>**: Die folgenden Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23545-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="23545-324">**ATP-generierte URL-Reputation**<sup>1:</sup>Schadsoftware-URL-Reputation, die von Defender für Office 365 detonationen in anderen Microsoft 365 generiert wird.</span><span class="sxs-lookup"><span data-stu-id="23545-324">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="23545-325">**Erweiterter Phishfilter:** Phishingsignale basierend auf maschinellem Lernen.</span><span class="sxs-lookup"><span data-stu-id="23545-325">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="23545-326">**Antis spoof – DMARC-Fehler:** Fehler bei der DMARC-Authentifizierung für Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="23545-326">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="23545-327">**Antis spoof - organisationsintern:** Der Absender versucht, die Empfängerdomäne zu spoofen.</span><span class="sxs-lookup"><span data-stu-id="23545-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="23545-328">**Antis spoof - externe Domäne:** Der Absender versucht, eine andere Domäne zu spoofen.</span><span class="sxs-lookup"><span data-stu-id="23545-328">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="23545-329">**Markenwechsel: Identitätswechsel** bekannter Marken basierend auf Absendern.</span><span class="sxs-lookup"><span data-stu-id="23545-329">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="23545-330">**Domänenwechsel**<sup>1:</sup>Identitätswechsel von Domänen, die der Kunde besitzt oder definiert.</span><span class="sxs-lookup"><span data-stu-id="23545-330">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="23545-331">**EOP-URL-Reputation:** Bösartige URL-Reputation.</span><span class="sxs-lookup"><span data-stu-id="23545-331">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="23545-332">**Allgemeiner Phishingfilter:** Phishingsignale basierend auf Analystenregeln.</span><span class="sxs-lookup"><span data-stu-id="23545-332">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="23545-333">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="23545-333">**Others**</span></span>
  - <span data-ttu-id="23545-334">**Phish ZAP**<sup>2:</sup>Automatisches Löschen von Phishingnachrichten in null Stunden.</span><span class="sxs-lookup"><span data-stu-id="23545-334">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="23545-335">**URL-Detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23545-335">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="23545-336">**Benutzerwechsel**<sup>1:</sup>Identitätswechsel von Benutzern, die vom Administrator definiert oder über Postfachintelligenz gelernt wurden.</span><span class="sxs-lookup"><span data-stu-id="23545-336">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Erkennungstechnologieansicht für Phishing-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="23545-338">**Unterlegen nach: Erkennungstechnologie und** **Daten anzeigen nach: E-Mail-Schadsoftware \>**: Die folgenden Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23545-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="23545-339">**ATP-generierte Dateire** reputation <sup>1:</sup>Alle von Defender generierte Schaddateire reputation für Office 365 Detonationen.</span><span class="sxs-lookup"><span data-stu-id="23545-339">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="23545-340">**An malware engine**<sup>1</sup>: Detection from anti-malware engines.</span><span class="sxs-lookup"><span data-stu-id="23545-340">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="23545-341">**Dateitypblock für** An malware-Richtlinien: Dies sind E-Mail-Nachrichten, die aufgrund der in der Nachricht identifizierten Bösartigen Datei herausgefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="23545-341">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="23545-342">**Dateidetonation**<sup>1:</sup>Erkennung durch sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="23545-342">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="23545-343">**Schädliche Datei reputation**</span><span class="sxs-lookup"><span data-stu-id="23545-343">**Malicious file reputation**</span></span>
  - <span data-ttu-id="23545-344">**Schadsoftware ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23545-344">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="23545-345">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="23545-345">**Others**</span></span>

  ![Erkennungstechnologieansicht für Schadsoftware im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="23545-347">**Aufbrechen nach: Richtlinientyp und** Daten **anzeigen nach: E-Mail-Phish \>** oder Daten anzeigen **nach: E-Mail-Schadsoftware \>**: Die folgenden Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23545-347">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="23545-348">**An malware**</span><span class="sxs-lookup"><span data-stu-id="23545-348">**Anti-malware**</span></span>
  - <span data-ttu-id="23545-349">**Sichere Anlagen**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23545-349">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="23545-350">**Antiphish**</span><span class="sxs-lookup"><span data-stu-id="23545-350">**Anti-phish**</span></span>
  - <span data-ttu-id="23545-351">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="23545-351">**Anti-spam**</span></span>
  - <span data-ttu-id="23545-352">**Nachrichtenflussregel** (auch als Transportregel bekannt)</span><span class="sxs-lookup"><span data-stu-id="23545-352">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="23545-353">**Sonstige**</span><span class="sxs-lookup"><span data-stu-id="23545-353">**Others**</span></span>

  ![Richtlinientypansicht für Phishing-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="23545-355">**Unterlegen Nach: Zustellungsstatus und** Daten anzeigen **nach: E-Mail-Phish \>** oder Daten anzeigen **nach: E-Mail-Schadsoftware \>**: Die folgenden Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23545-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="23545-356">**Zustellung fehlgeschlagen**</span><span class="sxs-lookup"><span data-stu-id="23545-356">**Delivery failed**</span></span>
  - <span data-ttu-id="23545-357">**Dropped**</span><span class="sxs-lookup"><span data-stu-id="23545-357">**Dropped**</span></span>
  - <span data-ttu-id="23545-358">**Weitergeleitet**</span><span class="sxs-lookup"><span data-stu-id="23545-358">**Forwarded**</span></span>
  - <span data-ttu-id="23545-359">**Gehostetes Postfach: Benutzerdefinierter Ordner**</span><span class="sxs-lookup"><span data-stu-id="23545-359">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="23545-360">**Gehostetes Postfach: Gelöschte Elemente**</span><span class="sxs-lookup"><span data-stu-id="23545-360">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="23545-361">**Gehostetes Postfach: Posteingang**</span><span class="sxs-lookup"><span data-stu-id="23545-361">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="23545-362">**Gehostetes Postfach: Junk**</span><span class="sxs-lookup"><span data-stu-id="23545-362">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="23545-363">**On-premises server: Delivered**</span><span class="sxs-lookup"><span data-stu-id="23545-363">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="23545-364">**Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="23545-364">**Quarantine**</span></span>

  ![Zustellungsstatusansicht für Phishing-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="23545-366"><sup>1</sup> Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="23545-366"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="23545-367"><sup>2 Zap</sup> (Zero-Hour Auto Purge) ist in eigenständigem EOP nicht verfügbar (funktioniert nur in Exchange Online Postfächern).</span><span class="sxs-lookup"><span data-stu-id="23545-367"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="23545-368">Wenn Sie auf **Filter klicken,** hängen die verfügbaren Filter vom Diagramm ab, das Sie sich angeschaut haben:</span><span class="sxs-lookup"><span data-stu-id="23545-368">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="23545-369">Für **Daten anzeigen nach: Content \> Malware** können Sie den Bericht nach **Start-** und **Enddatum** und **Erkennungswert** ändern.</span><span class="sxs-lookup"><span data-stu-id="23545-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="23545-370">Für **View data by: Message Override** können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="23545-370">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="23545-371">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-371">**Start date** and **End date**</span></span>
  - <span data-ttu-id="23545-372">**Override Reason**</span><span class="sxs-lookup"><span data-stu-id="23545-372">**Override Reason**</span></span>
  - <span data-ttu-id="23545-373">**Tag**: Filtern Sie die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="23545-373">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="23545-374">Weitere Informationen zu Benutzertags finden Sie unter [User tags](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="23545-374">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="23545-375">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="23545-375">**Domain**</span></span>

- <span data-ttu-id="23545-376">Für alle anderen Ansichten können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="23545-376">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="23545-377">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-377">**Start date** and **End date**</span></span>
  - <span data-ttu-id="23545-378">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="23545-378">**Detection**</span></span>
  - <span data-ttu-id="23545-379">**Geschützt durch**: **ATP** oder **EOP**</span><span class="sxs-lookup"><span data-stu-id="23545-379">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="23545-380">**Tag**: Filtern Sie die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="23545-380">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="23545-381">Weitere Informationen zu Benutzertags finden Sie unter [User tags](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="23545-381">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="23545-382">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="23545-382">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="23545-383">Detailtabelle für den Statusbericht zum Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="23545-383">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="23545-384">Wenn Sie auf **Detailtabelle anzeigen klicken,** hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich angeschaut haben:</span><span class="sxs-lookup"><span data-stu-id="23545-384">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="23545-385">**Daten anzeigen nach: Übersicht**: Es ist keine **Schaltfläche Details anzeigen der Tabelle** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="23545-385">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="23545-386">**Anzeigen von Daten nach: Content \> Schadsoftware**:</span><span class="sxs-lookup"><span data-stu-id="23545-386">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="23545-387">**Date**</span><span class="sxs-lookup"><span data-stu-id="23545-387">**Date**</span></span>
  - <span data-ttu-id="23545-388">**Ort**</span><span class="sxs-lookup"><span data-stu-id="23545-388">**Location**</span></span>
  - <span data-ttu-id="23545-389">**Geleitet von**</span><span class="sxs-lookup"><span data-stu-id="23545-389">**Directed by**</span></span>
  - <span data-ttu-id="23545-390">**Schadsoftwarename**</span><span class="sxs-lookup"><span data-stu-id="23545-390">**Malware name**</span></span>

  <span data-ttu-id="23545-391">Wenn Sie **in** dieser Ansicht auf Filter klicken, können Sie den Bericht nach **Startdatum,** **Enddatum** und **Erkennungswert** ändern.</span><span class="sxs-lookup"><span data-stu-id="23545-391">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="23545-392">**Daten anzeigen nach: Message Override**:</span><span class="sxs-lookup"><span data-stu-id="23545-392">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="23545-393">**Date**</span><span class="sxs-lookup"><span data-stu-id="23545-393">**Date**</span></span>
  - <span data-ttu-id="23545-394">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="23545-394">**Subject**</span></span>
  - <span data-ttu-id="23545-395">**Sender**</span><span class="sxs-lookup"><span data-stu-id="23545-395">**Sender**</span></span>
  - <span data-ttu-id="23545-396">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="23545-396">**Recipients**</span></span>
  - <span data-ttu-id="23545-397">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="23545-397">**Detected by**</span></span>
  - <span data-ttu-id="23545-398">**Override Reason**</span><span class="sxs-lookup"><span data-stu-id="23545-398">**Override Reason**</span></span>
  - <span data-ttu-id="23545-399">**Quelle des Kompromisses**</span><span class="sxs-lookup"><span data-stu-id="23545-399">**Source of Compromise**</span></span>
  - <span data-ttu-id="23545-400">**Tags**</span><span class="sxs-lookup"><span data-stu-id="23545-400">**Tags**</span></span>

  <span data-ttu-id="23545-401">Wenn Sie **in** dieser Ansicht auf Filter klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="23545-401">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="23545-402">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-402">**Start date** and **End date**</span></span>
  - <span data-ttu-id="23545-403">**Override Reason**</span><span class="sxs-lookup"><span data-stu-id="23545-403">**Override Reason**</span></span>
  - <span data-ttu-id="23545-404">**Tag**: Filtern Sie die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="23545-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="23545-405">Weitere Informationen zu Benutzertags finden Sie unter [User tags](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="23545-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="23545-406">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="23545-406">**Domain**</span></span>
  - <span data-ttu-id="23545-407">**Empfänger (Beachten** Sie, dass diese filterbare Eigenschaft nur in der Detailtabelle verfügbar ist)</span><span class="sxs-lookup"><span data-stu-id="23545-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="23545-408">Alle anderen Diagramme:</span><span class="sxs-lookup"><span data-stu-id="23545-408">All other charts:</span></span>

  - <span data-ttu-id="23545-409">**Date**</span><span class="sxs-lookup"><span data-stu-id="23545-409">**Date**</span></span>
  - <span data-ttu-id="23545-410">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="23545-410">**Subject**</span></span>
  - <span data-ttu-id="23545-411">**Sender**</span><span class="sxs-lookup"><span data-stu-id="23545-411">**Sender**</span></span>
  - <span data-ttu-id="23545-412">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="23545-412">**Recipients**</span></span>
  - <span data-ttu-id="23545-413">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="23545-413">**Detected by**</span></span>
  - <span data-ttu-id="23545-414">**Zustellungsstatus**</span><span class="sxs-lookup"><span data-stu-id="23545-414">**Delivery Status**</span></span>
  - <span data-ttu-id="23545-415">**Quelle des Kompromisses**</span><span class="sxs-lookup"><span data-stu-id="23545-415">**Source of Compromise**</span></span>
  - <span data-ttu-id="23545-416">**Tags**</span><span class="sxs-lookup"><span data-stu-id="23545-416">**Tags**</span></span>

  <span data-ttu-id="23545-417">Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:</span><span class="sxs-lookup"><span data-stu-id="23545-417">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="23545-418">**Startdatum** und **Enddatum**</span><span class="sxs-lookup"><span data-stu-id="23545-418">**Start date** and **End date**</span></span>
  - <span data-ttu-id="23545-419">**Erkennung**</span><span class="sxs-lookup"><span data-stu-id="23545-419">**Detection**</span></span>
  - <span data-ttu-id="23545-420">**Geschützt durch**: **Defender for Office 365** or **EOP**</span><span class="sxs-lookup"><span data-stu-id="23545-420">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="23545-421">**Tag**: Filtern Sie die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten).</span><span class="sxs-lookup"><span data-stu-id="23545-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="23545-422">Weitere Informationen zu Benutzertags finden Sie unter [User tags](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="23545-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="23545-423">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="23545-423">**Domain**</span></span>
  - <span data-ttu-id="23545-424">**Empfänger (Beachten** Sie, dass diese filterbare Eigenschaft nur in der Detailtabelle verfügbar ist)</span><span class="sxs-lookup"><span data-stu-id="23545-424">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="23545-425">Bericht über die beste Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="23545-425">Top malware report</span></span>

<span data-ttu-id="23545-426">Der **Bericht "Top Malware"** zeigt die verschiedenen Arten von Schadsoftware, die vom Schutz vor Schadsoftware [in EOP erkannt wurden.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="23545-426">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="23545-427">Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, \>  und wählen Sie Top **malware aus.**</span><span class="sxs-lookup"><span data-stu-id="23545-427">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="23545-428">Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=TopMalware> wechseln.</span><span class="sxs-lookup"><span data-stu-id="23545-428">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Top malware widget in the Reports dashboard](../../media/top-malware-report-widget.png)

<span data-ttu-id="23545-430">Wenn Sie auf einen Keil im Kreisdiagramm zeigen, sehen Sie den Namen einer Art Schadsoftware und die Anzahl der Nachrichten, die als Schadsoftware erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="23545-430">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Ansicht der besten Schadsoftwareberichtsansicht](../../media/top-malware-report-view.png)

<span data-ttu-id="23545-432">Wenn Sie auf **Detailtabelle anzeigen klicken,** sehen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="23545-432">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="23545-433">**Am besten schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="23545-433">**Top malware**</span></span>
- <span data-ttu-id="23545-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="23545-434">**Count**</span></span>

<span data-ttu-id="23545-435">Wenn Sie **in** der Berichtsansicht oder Detailtabelle auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="23545-435">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="23545-436">BERICHT zum Schutz vor URL-Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="23545-436">URL threat protection report</span></span>

<span data-ttu-id="23545-437">Der **Bericht zum Schutz vor URL-Bedrohungen** ist in Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="23545-437">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="23545-438">Weitere Informationen finden Sie unter [URL Threat Protection Report](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="23545-438">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="23545-439">Bericht über von Benutzern gemeldete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="23545-439">User-reported messages report</span></span>

<span data-ttu-id="23545-440">Der **Bericht** "Von Benutzern gemeldete Nachrichten" enthält Informationen zu E-Mail-Nachrichten, die Benutzer mithilfe des [Add-Ins](enable-the-report-message-add-in.md) "Nachricht melden" oder "Phishing-Add-In melden" als Junk- oder Phishingversuche oder gute [E-Mails gemeldet haben.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="23545-440">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="23545-441">Details sind für jede Nachricht verfügbar, einschließlich des Zustellungsgrunds, einer solchen Spamrichtlinienausnahme oder nachrichtenflussregel, die für Ihre Organisation konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="23545-441">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="23545-442">Um Details anzuzeigen, wählen Sie ein Element in der Liste Benutzerberichte aus, und zeigen Sie die Informationen dann auf den Registerkarten **Zusammenfassung** und **Details** an.</span><span class="sxs-lookup"><span data-stu-id="23545-442">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![Im User-Reported Nachrichtenbericht werden Nachrichten angezeigt, die von Benutzern als Junk und nicht als Junk oder Phishing bezeichnet werden.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="23545-444">Gehen Sie zum Anzeigen dieses Berichts im [Security & Compliance Center](https://protection.office.com)wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="23545-444">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="23545-445">Wechseln Sie zu **Bedrohungsverwaltungsdashboard** \>  \> **Von Benutzern gemeldete Nachrichten**.</span><span class="sxs-lookup"><span data-stu-id="23545-445">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="23545-446">Wechseln Sie zu **Bedrohungsverwaltung** \> **Überprüfen** \> **von Vom Benutzer gemeldeten Nachrichten**.</span><span class="sxs-lookup"><span data-stu-id="23545-446">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![Wählen Sie im Security & Compliance Center die Option Bedrohungsverwaltung \> Überprüfen von Vom Benutzer \> gemeldeten Nachrichten](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="23545-448">Damit der Bericht über vom Benutzer gemeldete Nachrichten ordnungsgemäß **funktioniert,** muss die Überwachungsprotokollierung für Ihre Umgebung Office 365 werden.</span><span class="sxs-lookup"><span data-stu-id="23545-448">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="23545-449">Dies wird in der Regel von einer Person durchgeführt, der die Rolle Überwachungsprotokolle in der Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="23545-449">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="23545-450">Weitere Informationen finden Sie unter [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="23545-450">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="23545-451">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="23545-451">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="23545-452">Um die in diesem Artikel beschriebenen Berichte anzeigen und verwenden zu können, müssen Sie Mitglied einer der folgenden Rollengruppen im Security & Compliance Center sein:</span><span class="sxs-lookup"><span data-stu-id="23545-452">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="23545-453">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="23545-453">**Organization Management**</span></span>
- <span data-ttu-id="23545-454">**Sicherheitsadministrator**</span><span class="sxs-lookup"><span data-stu-id="23545-454">**Security Administrator**</span></span>
- <span data-ttu-id="23545-455">**Security Reader**</span><span class="sxs-lookup"><span data-stu-id="23545-455">**Security Reader**</span></span>
- <span data-ttu-id="23545-456">**Globaler Leser**</span><span class="sxs-lookup"><span data-stu-id="23545-456">**Global Reader**</span></span>

<span data-ttu-id="23545-457">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="23545-457">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="23545-458">**Hinweis**: Das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center bietet Benutzern die erforderlichen Berechtigungen im Security & Compliance _Center_ und Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23545-458">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="23545-459">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="23545-459">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="23545-460">Was passiert, wenn in den Berichten keine Daten angezeigt werden?</span><span class="sxs-lookup"><span data-stu-id="23545-460">What if the reports aren't showing data?</span></span>

<span data-ttu-id="23545-461">Wenn in Ihren Berichten keine Daten angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="23545-461">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="23545-462">Weitere Informationen finden Sie unter [Protect against threats](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="23545-462">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="23545-463">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="23545-463">Related topics</span></span>

[<span data-ttu-id="23545-464">Antispam- und Schutz vor Schadsoftware in EOP</span><span class="sxs-lookup"><span data-stu-id="23545-464">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="23545-465">Intelligente Berichte und Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="23545-465">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="23545-466">Anzeigen von Nachrichtenflussberichten im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="23545-466">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="23545-467">Anzeigen von Berichten für Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="23545-467">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
