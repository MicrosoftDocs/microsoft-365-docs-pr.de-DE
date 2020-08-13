---
title: Vorgehensweise Melden von falsch positiven oder falschen negativen Ergebnissen in Office 365 automatischen Untersuchung und Antwort
description: Wurde von Office 365 Advanced Threat Protection etwas übersehen oder falsch erkannt? Hier erfahren Sie, wie Sie falsch positive Ergebnisse oder falsch negative Informationen zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Auslöser, Aktion, Korrektur, falsch positiv, falsch negativ
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 826d8561ba0c9618f21458493416b7dbd75af9e1
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656861"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="1abfa-105">Vorgehensweise Melden von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen</span><span class="sxs-lookup"><span data-stu-id="1abfa-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="1abfa-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1abfa-106">**Applies to:**</span></span>
- <span data-ttu-id="1abfa-107">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1abfa-107">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="1abfa-108">Haben [automatisierte Funktionen für die Untersuchung und Reaktion (Air) Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) vermissen oder fälschlicherweise etwas erkannt?</span><span class="sxs-lookup"><span data-stu-id="1abfa-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="1abfa-109">Es gibt Schritte, die Sie ausführen können, um es zu beheben.</span><span class="sxs-lookup"><span data-stu-id="1abfa-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="1abfa-110">Sie können:</span><span class="sxs-lookup"><span data-stu-id="1abfa-110">You can:</span></span>
- <span data-ttu-id="1abfa-111">[Melden einer falsch positiven/negativen Meldung an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="1abfa-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="1abfa-112">[Passen Sie Ihre Benachrichtigungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) an (falls erforderlich); und</span><span class="sxs-lookup"><span data-stu-id="1abfa-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="1abfa-113">[Rückgängigmachen von Korrekturaktionen, die ausgeführt wurden](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="1abfa-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="1abfa-114">Verwenden Sie diesen Artikel als Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="1abfa-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="1abfa-115">Melden einer falsch positiven/negativen Meldung an Microsoft zur Analyse</span><span class="sxs-lookup"><span data-stu-id="1abfa-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="1abfa-116">Wenn Office 365 eine e-Mail-Nachricht, eine e-Mail-Anlage, eine URL in einer e-Mail-Nachricht oder eine URL in einer Office-Datei verpasst haben, können Sie [mutmaßliche Spam, Phishing, URLs und Dateien für die Office 365 Überprüfung an Microsoft übermitteln](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span><span class="sxs-lookup"><span data-stu-id="1abfa-116">If Office 365 AIR missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="1abfa-117">Sie können [eine Datei auch zur Malware Analyse an Microsoft übermitteln](https://www.microsoft.com/wdsi/filesubmission).</span><span class="sxs-lookup"><span data-stu-id="1abfa-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="1abfa-118">Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden</span><span class="sxs-lookup"><span data-stu-id="1abfa-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="1abfa-119">Wenn eine Warnung durch eine legitime Verwendung ausgelöst wird oder die Warnung ungenau ist, können Sie [Warnungen im Cloud-App-Sicherheitsportal verwalten](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="1abfa-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="1abfa-120">Wenn Ihre Organisation neben Office 365 auch [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) verwendet und eine Datei, eine IP-Adresse, eine URL oder eine Domäne als Schadsoftware auf einem Gerät behandelt wird, können Sie [einen benutzerdefinierten Indikator mit der Aktion "zulassen" für Ihr Gerät erstellen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="1abfa-120">If your organization is using [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="1abfa-121">Rückgängigmachen einer Korrekturaktion</span><span class="sxs-lookup"><span data-stu-id="1abfa-121">Undo a remediation action</span></span>

<span data-ttu-id="1abfa-122">In den meisten Fällen, wenn eine Korrekturaktion für eine e-Mail-Nachricht, eine e-Mail-Anlage oder eine URL ausgeführt wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheits Betriebsteam die Korrekturaktion rückgängig machen und Schritte Unternehmen, um zu verhindern, dass das falsch positive Ergebnis wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="1abfa-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="1abfa-123">Sie können entweder [Threat Explorer](#undo-an-action-using-threat-explorer) oder die [Registerkarte Aktionen für eine Untersuchung](#undo-an-action-using-the-actions-tab-for-an-investigation) verwenden, um eine Aktion rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="1abfa-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1abfa-124">Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen, bevor Sie versuchen, die folgenden Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1abfa-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="1abfa-125">Rückgängigmachen einer Aktion mit dem Bedrohungs-Explorer</span><span class="sxs-lookup"><span data-stu-id="1abfa-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="1abfa-126">Mit Threat Explorer kann Ihr Sicherheits Betriebsteam eine von einer Aktion betroffene e-Mail-Nachricht finden und die Aktion möglicherweise rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="1abfa-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

****

|<span data-ttu-id="1abfa-127">Szenario</span><span class="sxs-lookup"><span data-stu-id="1abfa-127">Scenario</span></span>|<span data-ttu-id="1abfa-128">Rückgängig-Optionen</span><span class="sxs-lookup"><span data-stu-id="1abfa-128">Undo Options</span></span>|<span data-ttu-id="1abfa-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1abfa-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="1abfa-130">Eine e-Mail-Nachricht wurde an den Junk-e-Mail-Ordner eines Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="1abfa-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="1abfa-131">-Verschiebt die Nachricht in den Ordner "Gelöschte Elemente" des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1abfa-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="1abfa-132">-Verschieben der Nachricht in den Posteingang des Benutzers</span><span class="sxs-lookup"><span data-stu-id="1abfa-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="1abfa-133">-Nachricht löschen</span><span class="sxs-lookup"><span data-stu-id="1abfa-133">- Delete the message</span></span>|[<span data-ttu-id="1abfa-134">Suchen und untersuchen schädlicher e-Mails, die in Office 365 bereitgestellt wurden</span><span class="sxs-lookup"><span data-stu-id="1abfa-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered)|
|<span data-ttu-id="1abfa-135">Eine e-Mail-Nachricht oder eine Datei wurde unter Quarantäne gestellt</span><span class="sxs-lookup"><span data-stu-id="1abfa-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="1abfa-136">-Freigeben der e-Mail oder Datei</span><span class="sxs-lookup"><span data-stu-id="1abfa-136">- Release the email or file</span></span> <br/><span data-ttu-id="1abfa-137">-Löschen der e-Mail oder Datei</span><span class="sxs-lookup"><span data-stu-id="1abfa-137">- Delete the email or file</span></span>|[<span data-ttu-id="1abfa-138">Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365</span><span class="sxs-lookup"><span data-stu-id="1abfa-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="1abfa-139">Rückgängigmachen einer Aktion mithilfe der Registerkarte "Aktionen" für eine Untersuchung</span><span class="sxs-lookup"><span data-stu-id="1abfa-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="1abfa-140">Im Wartungscenter können Sie Korrekturaktionen sehen, die ausgeführt wurden, und die Aktion möglicherweise rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="1abfa-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="1abfa-141">Gehen Sie zu [https://protection.office.com](https://protection.office.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="1abfa-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="1abfa-142">Dadurch gelangen Sie zum Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="1abfa-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="1abfa-143">Wechseln Sie zu **Threat Management**  >  **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="1abfa-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="1abfa-144">Wählen Sie in der Liste der Untersuchungen das Symbol **in neuem Fenster öffnen** neben der ID eines Elements aus.</span><span class="sxs-lookup"><span data-stu-id="1abfa-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="1abfa-145">Klicken Sie auf die Registerkarte **Aktionen** .</span><span class="sxs-lookup"><span data-stu-id="1abfa-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="1abfa-146">Wählen Sie ein Element mit dem Status **abgeschlossen**aus, und suchen Sie in der Spalte **Entscheidung** nach einem Link, beispielsweise **genehmigt**.</span><span class="sxs-lookup"><span data-stu-id="1abfa-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="1abfa-147">Dadurch wird ein Flyout mit weiteren Details zur Aktion geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1abfa-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="1abfa-148">Um die Aktion rückgängig zu machen, wählen Sie **Korrektur löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="1abfa-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1abfa-149">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="1abfa-149">Related articles</span></span>

[<span data-ttu-id="1abfa-150">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1abfa-150">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="1abfa-151">Erste Schritte mit der automatisierten Untersuchung und Reaktion (Air) in Office 365</span><span class="sxs-lookup"><span data-stu-id="1abfa-151">Get started using Automated investigation and response (AIR) in Office 365</span></span>](office-365-air.md)
