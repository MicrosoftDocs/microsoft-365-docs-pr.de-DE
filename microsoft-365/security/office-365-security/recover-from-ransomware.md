---
title: Wiederherstellen nach einem Ransomware-Angriff
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Office 365 Administratoren erfahren, wie Sie nach einem Ransomware-Angriff wiederherstellen können.
ms.openlocfilehash: 04cfd2f2417b0c2e084a88f9ee156521339b18c4
ms.sourcegitcommit: e47694dedf7e213167d3d979a44c07c668bba543
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41932371"
---
# <a name="recover-from-a-ransomware-attack-in-office-365"></a><span data-ttu-id="65909-103">Wiederherstellen nach einem Ransomware-Angriff in Office 365</span><span class="sxs-lookup"><span data-stu-id="65909-103">Recover from a ransomware attack in Office 365</span></span>

<span data-ttu-id="65909-104">Selbst wenn Sie alle Vorkehrungen treffen, um Ihre Office 365 Organisation zu schützen, können Sie dennoch einem [Ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) -Angriff zum Opfer fallen.</span><span class="sxs-lookup"><span data-stu-id="65909-104">Even if you take every precaution to protect your Office 365 organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="65909-105">Ransomware ist ein großes Unternehmen, und die Angriffe werden überprüfen anspruchsvoll.</span><span class="sxs-lookup"><span data-stu-id="65909-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="65909-106">Die Schritte in diesem Thema bieten Ihnen die beste Möglichkeit zum Wiederherstellen von Daten, die von der Ransomware verschlüsselt wurden, und helfen, die Ausbreitung der Infektion in Ihrer Office 365 Organisation zu beenden.</span><span class="sxs-lookup"><span data-stu-id="65909-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your Office 365 organization.</span></span> <span data-ttu-id="65909-107">Bevor Sie beginnen, sollten Sie die folgenden Punkte beachten:</span><span class="sxs-lookup"><span data-stu-id="65909-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="65909-108">Es gibt keine Garantie, dass durch das bezahlen des Lösegelds der Zugriff auf Ihre Dateien zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="65909-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="65909-109">Tatsächlich können Sie mit dem Lösegeld ein Ziel für mehr Ransomware machen.</span><span class="sxs-lookup"><span data-stu-id="65909-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="65909-110">Wenn Sie bereits bezahlt haben, aber Ihre Dateien erfolgreich wiederherstellen konnten, ohne die Auflösung des Angreifers zu verwenden, sollten Sie Ihre Bank anrufen, um zu prüfen, ob Sie die Transaktion blockieren kann.</span><span class="sxs-lookup"><span data-stu-id="65909-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="65909-111">Außerdem wird empfohlen, dass Sie den Ransomware-Angriff an Strafverfolgungs-, Scam-berichterstellungswebsites und Microsoft melden, wie weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65909-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="65909-112">Es ist sehr wichtig, dass Sie schnell auf den Angriff und seine Konsequenzen reagieren.</span><span class="sxs-lookup"><span data-stu-id="65909-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="65909-113">Je länger Sie warten, desto wahrscheinlicher ist es, dass Sie die betroffenen Daten wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="65909-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="65909-114">Schritt 1: Überprüfen der Sicherungen</span><span class="sxs-lookup"><span data-stu-id="65909-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="65909-115">Wenn Sie Offlinesicherungen haben, können Sie die verschlüsselten Daten möglicherweise wiederherstellen, **nachdem** Sie die Ransomware-Nutzlast (Schadsoftware) aus Ihrer Umgebung entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="65909-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="65909-116">Wenn Sie keine Sicherungen haben oder Ihre Sicherungen auch von der Ransomware betroffen sind, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="65909-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="65909-117">Schritt 2: Deaktivieren der ActiveSync-und OneDrive-Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="65909-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="65909-118">Der entscheidende Punkt ist, dass die Verbreitung der Datenverschlüsselung durch das Ransomware gestoppt wird.</span><span class="sxs-lookup"><span data-stu-id="65909-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="65909-119">Wenn Sie vermuten, dass e-Mail ein Ziel ist, sollten Sie den Benutzer Zugriff auf Postfächer vorübergehend deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="65909-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="65909-120">Exchange ActiveSync wird von mobilen Geräten zum Synchronisieren von Daten zwischen dem Gerät und dem Exchange Online Postfach verwendet.</span><span class="sxs-lookup"><span data-stu-id="65909-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="65909-121">Informationen zum Deaktivieren von ActiveSync für ein Postfach finden Sie unter [Deaktivieren von Exchange ActiveSync für Benutzer in Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="65909-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span></span>

<span data-ttu-id="65909-122">Informationen zum Deaktivieren anderer Zugriffstypen auf ein Postfach finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="65909-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="65909-123">[Aktivieren oder Deaktivieren von MAPI für ein Postfach](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="65909-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="65909-124">Aktivieren oder Deaktivieren des POP3-oder IMAP4-Zugriffs für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="65909-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="65909-125">Durch das Anhalten der OneDrive-Synchronisierung können Sie verhindern, dass Ihre Cloud-Daten von potenziell infizierten Geräten aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="65909-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="65909-126">Weitere Informationen finden Sie unter [Anhalten und Fortsetzen der Synchronisierung in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="65909-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="65909-127">Schritt 3: Entfernen der Schadsoftware von den betroffenen Geräten</span><span class="sxs-lookup"><span data-stu-id="65909-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="65909-128">Führen Sie einen vollständigen Antivirus-Scan mit den neuesten Updates auf allen vermuteten Computern und Geräten aus, um die dem Ransomware zugeordnete Nutzlast zu erkennen und zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="65909-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="65909-129">Vergessen Sie nicht, Geräte, die Daten synchronisieren, oder das Ziel von zugeordneten Netzlaufwerken (diese Computer und Geräte müssen ebenfalls überprüft werden).</span><span class="sxs-lookup"><span data-stu-id="65909-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="65909-130">Sie können [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) oder (für ältere Clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)verwenden.</span><span class="sxs-lookup"><span data-stu-id="65909-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="65909-131">Eine Alternative, die Ihnen auch beim Entfernen von Ransomware oder Schadsoftware helfen wird, ist das Tool zum Entfernen [bösartiger Software (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span><span class="sxs-lookup"><span data-stu-id="65909-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="65909-132">Wenn diese Optionen nicht funktionieren, können Sie [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) ausprobieren oder [Probleme beim erkennen und Entfernen von Schadsoftware beheben](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span><span class="sxs-lookup"><span data-stu-id="65909-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="65909-133">Schritt 4: Wiederherstellen von Dateien auf einem gesäuberten Computer oder Gerät</span><span class="sxs-lookup"><span data-stu-id="65909-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="65909-134">Nachdem Sie den vorherigen Schritt ausgeführt haben, um die Ransomware-Nutzlast aus Ihrer Umgebung zu entfernen (wodurch das Verschlüsseln oder Entfernen von Dateien durch Ransomware verhindert wird), können Sie den [Dateiverlauf](https://support.microsoft.com/help/17128/windows-8-file-history) in Windows 10 und Windows 8.1 oder den System Schutz in Windows 7 verwenden, um zu versuchen, ihre lokalen Dateien und Ordner wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="65909-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128/windows-8-file-history) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="65909-135">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="65909-135">**Notes**:</span></span>

- <span data-ttu-id="65909-136">In einigen Ransomware werden auch die Sicherungsversionen verschlüsselt oder gelöscht, sodass Sie den Dateiverlauf oder den System Schutz nicht zum Wiederherstellen von Dateien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="65909-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="65909-137">In diesem Fall müssen Sie Sicherungen auf externen Laufwerken oder Geräten verwenden, die nicht von der Ransomware oder OneDrive betroffen waren, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65909-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="65909-138">Wenn ein Ordner mit OneDrive synchronisiert wird und Sie nicht die neueste Version von Windows verwenden, gibt es möglicherweise einige Einschränkungen mithilfe des Dateiverlaufs.</span><span class="sxs-lookup"><span data-stu-id="65909-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="65909-139">Schritt 5: Wiederherstellen der Dateien im OneDrive für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="65909-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="65909-140">In OneDrive für Unternehmen können Sie alle darin gespeicherten Dateien wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="65909-140">OneDrive for Business will allow you to recover any files you have stored in it.</span></span> <span data-ttu-id="65909-141">Sie haben zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="65909-141">You have two options:</span></span>

- <span data-ttu-id="65909-142">Verwenden Sie die [OneDrive-Website](https://support.office.com/article/159cad6d-d76e-4981-88ef-de6e96c93893).</span><span class="sxs-lookup"><span data-stu-id="65909-142">Use the [OneDrive website](https://support.office.com/article/159cad6d-d76e-4981-88ef-de6e96c93893).</span></span>

- <span data-ttu-id="65909-143">Wenn eine große Anzahl von Dateien betroffen war, können Sie eine Supportanforderung für eine "Websitesammlungswiederherstellung" erstellen.</span><span class="sxs-lookup"><span data-stu-id="65909-143">If a large number of files were affected, you can create a support request for a "Site Collection Restore".</span></span> <span data-ttu-id="65909-144">Diese Anforderung kann Dateien von bis zu 14 Tagen in der Vergangenheit wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="65909-144">This request can restore files from up to 14 days in the past.</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="65909-145">Schritt 6: Wiederherstellen gelöschter e-Mails</span><span class="sxs-lookup"><span data-stu-id="65909-145">Step 6: Recover deleted email</span></span>

<span data-ttu-id="65909-146">In dem seltenen Fall, dass die Ransomware alle Ihre e-Mails gelöscht hat, können Sie die gelöschten Elemente wahrscheinlich wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="65909-146">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="65909-147">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="65909-147">For more information, see:</span></span>

- [<span data-ttu-id="65909-148">Wiederherstellen von gelöschten Nachrichten im Postfach eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="65909-148">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="65909-149">Wiederherstellen gelöschter Elemente in Outlook für Windows</span><span class="sxs-lookup"><span data-stu-id="65909-149">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="65909-150">Schritt 7: Erneutes Aktivieren von Exchange ActiveSync und OneDrive Sync</span><span class="sxs-lookup"><span data-stu-id="65909-150">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="65909-151">Nachdem Sie Ihre Computer und Geräte bereinigt und Ihre Daten wiederhergestellt haben, können Sie die ActiveSync-und OneDrive-Synchronisierung erneut aktivieren, die Sie zuvor in [Schritt 2](#step-2-disable-activesync-and-onedrive-sync)deaktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="65909-151">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="65909-152">Schritt 8 (optional): Blockieren der OneDrive-Synchronisierung für bestimmte Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="65909-152">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="65909-153">Nachdem Sie sich wieder erholt haben, können Sie verhindern, dass OneDrive für Unternehmen Clients die von diesem Ransomware betroffenen Dateitypen synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="65909-153">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="65909-154">Weitere Informationen finden Sie unter [festlegen-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="65909-154">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="65909-155">Melden des Angriffs</span><span class="sxs-lookup"><span data-stu-id="65909-155">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="65909-156">Kontakt Strafverfolgungsbehörden</span><span class="sxs-lookup"><span data-stu-id="65909-156">Contact law enforcement</span></span>

<span data-ttu-id="65909-157">Wenden Sie sich an Ihre lokalen oder Bundes Strafverfolgungsbehörden.</span><span class="sxs-lookup"><span data-stu-id="65909-157">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="65909-158">Wenn Sie sich beispielsweise in den Vereinigten Staaten befinden, können Sie sich an das [FBI local Field Office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) oder [Secret Service](http://www.secretservice.gov/)wenden.</span><span class="sxs-lookup"><span data-stu-id="65909-158">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="65909-159">Senden eines Berichts an die Scam-Berichtswebsite Ihres Landes</span><span class="sxs-lookup"><span data-stu-id="65909-159">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="65909-160">Scam-berichterstellungswebsites bieten Informationen zum verhindern und vermeiden von Scams.</span><span class="sxs-lookup"><span data-stu-id="65909-160">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="65909-161">Sie bieten auch Mechanismen zum melden, wenn Sie Opfer von Betrug wurden.</span><span class="sxs-lookup"><span data-stu-id="65909-161">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="65909-162">Australien: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="65909-162">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="65909-163">Kanada: [kanadisches Betrugs](http://www.antifraudcentre-centreantifraude.ca/) Bekämpfungs Zentrum</span><span class="sxs-lookup"><span data-stu-id="65909-163">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="65909-164">Frankreich: [Agence nationale de la sécurité des Systèmes Letter](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="65909-164">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="65909-165">Deutschland: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="65909-165">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="65909-166">Irland: [an Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="65909-166">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="65909-167">Neuseeland: [Scams für Verbraucherfragen](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="65909-167">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="65909-168">Vereinigtes Königreich: [Aktions betrug](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="65909-168">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="65909-169">Vereinigte Staaten: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="65909-169">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="65909-170">Wenn Ihr Land nicht aufgeführt ist, wenden Sie sich an Ihre lokalen oder Bundes Strafverfolgungsbehörden.</span><span class="sxs-lookup"><span data-stu-id="65909-170">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="65909-171">Senden von e-Mail-Nachrichten an Microsoft</span><span class="sxs-lookup"><span data-stu-id="65909-171">Submit email messages to Microsoft</span></span>

<span data-ttu-id="65909-172">Sie können Phishing-Nachrichten melden, die Ransomware enthalten, indem Sie den Anweisungen unter [Submit Spam, Non-Spam, and Phishing Scam messages to Microsoft for Analysis](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)folgen.</span><span class="sxs-lookup"><span data-stu-id="65909-172">You can report phishing message that contain ransomware by following the instructions in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis).</span></span>

## <a name="see-also"></a><span data-ttu-id="65909-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65909-173">See also</span></span>

- [<span data-ttu-id="65909-174">Ransomware</span><span class="sxs-lookup"><span data-stu-id="65909-174">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="65909-175">Ransomware-Antwort – zu zahlen oder nicht zu zahlen?</span><span class="sxs-lookup"><span data-stu-id="65909-175">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="65909-176">Norsk Hydro reagiert auf Ransomware-Angriff mit Transparenz</span><span class="sxs-lookup"><span data-stu-id="65909-176">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="65909-177">Ransomware-Erkennung und erneutes bedecken Ihrer Dateien in OneDrive</span><span class="sxs-lookup"><span data-stu-id="65909-177">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="65909-178">Microsoft Security Intelligence-Bericht</span><span class="sxs-lookup"><span data-stu-id="65909-178">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="65909-179">Aktivieren oder Deaktivieren von Makros in Office-Dateien</span><span class="sxs-lookup"><span data-stu-id="65909-179">Enable or disable macros in Office files</span></span>](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="65909-180">Empfohlene Einstellungen für EoP und Office 365 ATP-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="65909-180">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="65909-181">Ein würdiges Upgrade: Sicherheit der nächsten Generation unter Windows 10 erweist sich als widerstandsfähig gegen Ransomware-ausbruche in 2017</span><span class="sxs-lookup"><span data-stu-id="65909-181">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="65909-182">Keine mas, Samas: Was ist in diesem Ransomware-Modus operandi?</span><span class="sxs-lookup"><span data-stu-id="65909-182">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="65909-183">Locky Schadsoftware, Lucky to Avoid IT</span><span class="sxs-lookup"><span data-stu-id="65909-183">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="65909-184">MSRT July 2016: Cerber Ransomware</span><span class="sxs-lookup"><span data-stu-id="65909-184">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="65909-185">Die drei Köpfe der Cerberus-like Cerber Ransomware</span><span class="sxs-lookup"><span data-stu-id="65909-185">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="65909-186">Troldesh Ransomware beeinflusst von (dem) da Vinci-Code</span><span class="sxs-lookup"><span data-stu-id="65909-186">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
