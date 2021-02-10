---
title: Wiederherstellen nach einem Ransomware-Angriff
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365-Administratoren können erfahren, wie sie sich nach einem Ransomware-Angriff wiederherstellen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b834adb3d9ba5f85984e09b4bb1e4b48673c32f2
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166903"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="21c16-103">Wiederherstellen nach einem Ransomware-Angriff in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="21c16-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="21c16-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="21c16-104">**Applies to**</span></span>
- [<span data-ttu-id="21c16-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="21c16-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="21c16-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="21c16-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="21c16-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21c16-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="21c16-108">Auch wenn Sie alle Vorsichtsmaßnahmen ergreifen, um Ihre Organisation zu schützen, können Sie dennoch einem [Ransomwareangriff zum Opfer fallen.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="21c16-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="21c16-109">Ransomware ist groß im Geschäft, und die Angriffe sind sehr ausgefeilt.</span><span class="sxs-lookup"><span data-stu-id="21c16-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="21c16-110">Die Schritte in diesem Artikel bieten Ihnen die beste Möglichkeit, Daten wiederhergestellt und die interne Verbreitung der Infektion zu beenden.</span><span class="sxs-lookup"><span data-stu-id="21c16-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="21c16-111">Bevor Sie beginnen, sollten Sie die folgenden Punkte beachten:</span><span class="sxs-lookup"><span data-stu-id="21c16-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="21c16-112">Es gibt keine Garantie dafür, dass die Zahlung des Lösegelds den Zugriff auf Ihre Dateien zurückerfordert.</span><span class="sxs-lookup"><span data-stu-id="21c16-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="21c16-113">Tatsächlich kann die Zahlung des Lösegelds Sie zu einem Ziel für mehr Ransomware machen.</span><span class="sxs-lookup"><span data-stu-id="21c16-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="21c16-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span><span class="sxs-lookup"><span data-stu-id="21c16-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="21c16-115">Es wird außerdem empfohlen, den Ransomware-Angriff wie weiter unten in diesem Artikel beschrieben an Strafverfolgungsbehörden, Websites für Betrugsberichte und Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="21c16-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="21c16-116">Es ist wichtig, dass Sie schnell auf den Angriff und dessen Folgen reagieren.</span><span class="sxs-lookup"><span data-stu-id="21c16-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="21c16-117">Je länger Sie warten, desto weniger wahrscheinlich ist es, dass Sie die betroffenen Daten wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="21c16-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="21c16-118">Schritt 1: Überprüfen der Sicherungen</span><span class="sxs-lookup"><span data-stu-id="21c16-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="21c16-119">Wenn Sie über Offlinesicherungen verfügen,  können Sie wahrscheinlich die verschlüsselten Daten wiederherstellen, nachdem Sie die Ransomwarenutzlast (Schadsoftware) aus Ihrer Umgebung entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="21c16-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="21c16-120">Wenn Sie keine Sicherungen haben oder ihre Sicherungen auch von der Ransomware betroffen waren, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="21c16-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="21c16-121">Schritt 2: Deaktivieren Exchange ActiveSync und #A0</span><span class="sxs-lookup"><span data-stu-id="21c16-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="21c16-122">Der wichtigste Punkt dabei ist, die Verbreitung der Datenverschlüsselung durch Ransomware zu stoppen.</span><span class="sxs-lookup"><span data-stu-id="21c16-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="21c16-123">Wenn Sie E-Mails als Ziel der Ransomware-Verschlüsselung vermuten, deaktivieren Sie vorübergehend den Benutzerzugriff auf Postfächer.</span><span class="sxs-lookup"><span data-stu-id="21c16-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="21c16-124">Exchange ActiveSync synchronisiert Daten zwischen Geräten und Exchange Online-Postfächern.</span><span class="sxs-lookup"><span data-stu-id="21c16-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="21c16-125">Informationen zum Exchange ActiveSync für ein Postfach finden Sie unter Deaktivieren von Exchange ActiveSync für Benutzer [in Exchange Online.](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="21c16-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="21c16-126">Informationen zum Deaktivieren anderer Arten von Zugriff auf ein Postfach finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="21c16-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="21c16-127">[Aktivieren oder Deaktivieren von MAPI für ein Postfach.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="21c16-127">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="21c16-128">Aktivieren oder Deaktivieren des POP3- oder IMAP4-Zugriffs für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="21c16-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="21c16-129">Das Anhalten der #A0 schützt Ihre Clouddaten vor der Aktualisierung durch potenziell infizierte Geräte.</span><span class="sxs-lookup"><span data-stu-id="21c16-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="21c16-130">Weitere Informationen finden Sie unter "Anhalten und Fortsetzen [der Synchronisierung in OneDrive".](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)</span><span class="sxs-lookup"><span data-stu-id="21c16-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="21c16-131">Schritt 3: Entfernen der Schadsoftware von den betroffenen Geräten</span><span class="sxs-lookup"><span data-stu-id="21c16-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="21c16-132">Führen Sie einen vollständigen, aktuellen Antivirenscan auf allen verdächtigen Computern und Geräten aus, um die Nutzlast zu erkennen und zu entfernen, die der Ransomware zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="21c16-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="21c16-133">Vergessen Sie nicht, Geräte zu überprüfen, die Daten synchronisieren, oder die Ziele zugeordneter Netzlaufwerke.</span><span class="sxs-lookup"><span data-stu-id="21c16-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="21c16-134">Sie können [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) oder (für ältere Clients) [Microsoft Security Essentials.](https://www.microsoft.com/download/details.aspx?id=5201)</span><span class="sxs-lookup"><span data-stu-id="21c16-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="21c16-135">Eine Alternative, die Ihnen auch beim Entfernen von Ransomware oder Schadsoftware hilft, ist das Tool zum [Entfernen bösartiger Software (Malicious Software Removal Tool, MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="21c16-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="21c16-136">Wenn diese Optionen nicht funktionieren, können Sie Windows Defender [Offline](https://support.microsoft.com/help/17466) versuchen oder Probleme beim Erkennen und Entfernen von [Schadsoftware beheben.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="21c16-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="21c16-137">Schritt 4: Wiederherstellen von Dateien auf einem bereinigten Computer oder Gerät</span><span class="sxs-lookup"><span data-stu-id="21c16-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="21c16-138">Nachdem Sie den vorherigen Schritt abgeschlossen haben, um die Nutzlast von Ransomware aus Ihrer Umgebung zu entfernen (was die Ransomware daran hindern wird, Ihre Dateien zu verschlüsseln oder zu entfernen), können Sie den Dateiverlauf [in](https://support.microsoft.com/help/17128) Windows 10 und Windows 8.1 oder System Protection in Windows 7 verwenden, um ihre lokalen Dateien und Ordner wiederhergestellt zu versuchen.</span><span class="sxs-lookup"><span data-stu-id="21c16-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="21c16-139">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="21c16-139">**Notes**:</span></span>

- <span data-ttu-id="21c16-140">Einige Ransomware verschlüsselt oder löscht auch die Sicherungsversionen, sodass Sie den Dateiverlauf oder Systemschutz nicht zum Wiederherstellen von Dateien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="21c16-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="21c16-141">In diesem Fall müssen Sie Sicherungen auf externen Laufwerken oder Geräten verwenden, die nicht von ransomware oder OneDrive betroffen waren, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="21c16-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="21c16-142">Wenn ein Ordner mit OneDrive synchronisiert wird und Sie nicht die neueste Version von Windows verwenden, gibt es möglicherweise einige Einschränkungen bei der Verwendung des Dateiverlaufs.</span><span class="sxs-lookup"><span data-stu-id="21c16-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="21c16-143">Schritt 5: Wiederherstellen Ihrer Dateien in OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="21c16-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="21c16-144">Mit der Wiederherstellung von Dateien in OneDrive for Business können Sie Ihr gesamtes OneDrive innerhalb der letzten 30 Tage auf einen früheren Zeitpunkt wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="21c16-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="21c16-145">Weitere Informationen finden Sie unter ["Wiederherstellen Ihres OneDrive".](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="21c16-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="21c16-146">Schritt 6: Wiederherstellen gelöschter E-Mails</span><span class="sxs-lookup"><span data-stu-id="21c16-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="21c16-147">In dem seltenen Fall, dass die Ransomware alle Ihre E-Mails gelöscht hat, können Sie wahrscheinlich die gelöschten Elemente wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="21c16-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="21c16-148">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="21c16-148">For more information, see:</span></span>

- [<span data-ttu-id="21c16-149">Wiederherstellen von gelöschten Nachrichten im Postfach eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="21c16-149">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="21c16-150">Wiederherstellen gelöschter Elemente in Outlook für Windows</span><span class="sxs-lookup"><span data-stu-id="21c16-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="21c16-151">Schritt 7: Erneutes Aktivieren Exchange ActiveSync und #A0</span><span class="sxs-lookup"><span data-stu-id="21c16-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="21c16-152">Nachdem Sie Ihre Computer und Geräte bereinigt und Ihre Daten wiederhergestellt haben, können Sie die zuvor in Schritt 2 deaktivierte Exchange ActiveSync- und #A0 [erneut aktivieren.](#step-2-disable-exchange-activesync-and-onedrive-sync)</span><span class="sxs-lookup"><span data-stu-id="21c16-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="21c16-153">Schritt 8 (optional): Blockieren der #A0 für bestimmte Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="21c16-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="21c16-154">Nach der Wiederherstellung können Sie verhindern, dass OneDrive for #A0 die Dateitypen synchronisieren, die von dieser Ransomware betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="21c16-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="21c16-155">Weitere Informationen finden Sie unter ["Set-SPOTenantSyncClientRestriction".](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="21c16-155">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="21c16-156">Melden des Angriffs</span><span class="sxs-lookup"><span data-stu-id="21c16-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="21c16-157">Wenden Sie sich an die Strafverfolgung</span><span class="sxs-lookup"><span data-stu-id="21c16-157">Contact law enforcement</span></span>

<span data-ttu-id="21c16-158">Sie sollten sich an Ihre lokalen oder Bundesbehörden wenden.</span><span class="sxs-lookup"><span data-stu-id="21c16-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="21c16-159">Wenn Sie sich z. B. in den USA befinden, können Sie sich an das lokale Bzw. [ic3-](http://www.ic3.gov/complaint/default.aspx) oder geheime [Dienstanbieter](https://www.fbi.gov/contact-us/field) [(Secret Service, IC3) wenden.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="21c16-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="21c16-160">Übermitteln eines Berichts an die Website zur Berichterstellung über Betrug in Ihrem Land</span><span class="sxs-lookup"><span data-stu-id="21c16-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="21c16-161">Websites für betrugsberichterstattung bieten Informationen dazu, wie Sie Betrug verhindern und vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="21c16-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="21c16-162">Sie bieten auch Mechanismen, um zu melden, ob Sie Opfer von Betrug wurden.</span><span class="sxs-lookup"><span data-stu-id="21c16-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="21c16-163">Australien: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="21c16-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="21c16-164">Kanada: [Kanadisches Anti-Betrugs-Center](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="21c16-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="21c16-165">Frankreich: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="21c16-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="21c16-166">Deutschland: [Zur Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="21c16-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="21c16-167">Irland: [AnÌ Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="21c16-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="21c16-168">Neuseeland: [Betrügerischer Verbraucherschutz](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="21c16-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="21c16-169">Vereinigtes Königreich: [Betrugsaktion](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="21c16-169">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="21c16-170">Vereinigte Staaten: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="21c16-170">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="21c16-171">If your country isn't listed, ask your local or federal law enforcement agencies.</span><span class="sxs-lookup"><span data-stu-id="21c16-171">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="21c16-172">Senden von E-Mail-Nachrichten an Microsoft</span><span class="sxs-lookup"><span data-stu-id="21c16-172">Submit email messages to Microsoft</span></span>

<span data-ttu-id="21c16-173">Sie können Phishingnachrichten, die Ransomware enthalten, mithilfe einer von mehreren Methoden melden.</span><span class="sxs-lookup"><span data-stu-id="21c16-173">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="21c16-174">Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="21c16-174">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="21c16-175">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="21c16-175">See also</span></span>

- [<span data-ttu-id="21c16-176">Ransomware</span><span class="sxs-lookup"><span data-stu-id="21c16-176">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="21c16-177">Antwort auf Ransomware – um zu bezahlen oder nicht zu bezahlen?</span><span class="sxs-lookup"><span data-stu-id="21c16-177">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="21c16-178">Norsk Weiter reagiert mit Transparenz auf Ransomware-Angriffe.</span><span class="sxs-lookup"><span data-stu-id="21c16-178">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="21c16-179">#A0 und Wiederherstellung Ihrer Dateien in OneDrive</span><span class="sxs-lookup"><span data-stu-id="21c16-179">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="21c16-180">Microsoft Security Intelligence Report</span><span class="sxs-lookup"><span data-stu-id="21c16-180">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="21c16-181">Aktivieren oder Deaktivieren von Makros in Office-Dateien</span><span class="sxs-lookup"><span data-stu-id="21c16-181">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="21c16-182">Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="21c16-182">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="21c16-183">Ein würdiges Upgrade: Sicherheit der nächsten Generation unter Windows 10 ist vertrauenswürdig gegen Ransomware-Angriffe im Jahr 2017</span><span class="sxs-lookup"><span data-stu-id="21c16-183">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="21c16-184">No mas, Samas: Was ist in diesem Modus von Ransomware?</span><span class="sxs-lookup"><span data-stu-id="21c16-184">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="21c16-185">Locky malware, locky to avoid it</span><span class="sxs-lookup"><span data-stu-id="21c16-185">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="21c16-186">MSRT Juli 2016: Cerber Ransomware</span><span class="sxs-lookup"><span data-stu-id="21c16-186">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="21c16-187">Die drei Haupte der Cerberus-like Cerber Ransomware</span><span class="sxs-lookup"><span data-stu-id="21c16-187">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="21c16-188">Troldesh Ransomware, beeinflusst durch (den) Da Vinci-Code</span><span class="sxs-lookup"><span data-stu-id="21c16-188">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
