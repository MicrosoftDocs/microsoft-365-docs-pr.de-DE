---
title: Wiederherstellen nach einem Ransomware-Angriff
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 Administratoren erfahren, wie sie sich von einem Ransomware-Angriff wiederherstellen können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 608fac50fc65f20a612b80ed151252eb2a0c2e01
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415551"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="647cd-103">Wiederherstellen von einem Ransomware-Angriff in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="647cd-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="647cd-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="647cd-104">**Applies to**</span></span>
- [<span data-ttu-id="647cd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="647cd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="647cd-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="647cd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="647cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="647cd-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="647cd-108">Auch wenn Sie alle Vorsichtsmaßnahmen ergreifen, um Ihre Organisation zu schützen, können Sie dennoch einem [Ransomware-Angriff](/windows/security/threat-protection/intelligence/ransomware-malware) zum Opfer fallen.</span><span class="sxs-lookup"><span data-stu-id="647cd-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="647cd-109">Ransomware ist ein großes Unternehmen, und die Angriffe sind sehr ausgereift.</span><span class="sxs-lookup"><span data-stu-id="647cd-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="647cd-110">Die Schritte in diesem Artikel bieten Ihnen die beste Möglichkeit, Daten wiederherzustellen und die interne Verbreitung der Infektion zu stoppen.</span><span class="sxs-lookup"><span data-stu-id="647cd-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="647cd-111">Bevor Sie beginnen, sollten Sie die folgenden Punkte beachten:</span><span class="sxs-lookup"><span data-stu-id="647cd-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="647cd-112">Es gibt keine Garantie dafür, dass die Zahlung des Lösegelds den Zugriff auf Ihre Dateien zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="647cd-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="647cd-113">Tatsächlich kann ihnen die Zahlung des Lösegelds ein Ziel für mehr Ransomware machen.</span><span class="sxs-lookup"><span data-stu-id="647cd-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="647cd-114">Wenn Sie bereits bezahlt haben, aber ohne die Lösung des Angreifers wiederhergestellt haben, wenden Sie sich an Ihre Bank, um festzustellen, ob sie die Transaktion blockieren kann.</span><span class="sxs-lookup"><span data-stu-id="647cd-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="647cd-115">Wir empfehlen außerdem, den Ransomware-Angriff an Strafverfolgungsbehörden, Websites mit Betrugsberichten und Microsoft zu melden, wie weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="647cd-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="647cd-116">Es ist wichtig, dass Sie schnell auf den Angriff und dessen Folgen reagieren.</span><span class="sxs-lookup"><span data-stu-id="647cd-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="647cd-117">Je länger Sie warten, desto unwahrscheinlicher ist es, dass Sie die betroffenen Daten wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="647cd-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="647cd-118">Schritt 1: Überprüfen Der Sicherungen</span><span class="sxs-lookup"><span data-stu-id="647cd-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="647cd-119">Wenn Sie Offlinesicherungen haben, können Sie die verschlüsselten Daten wahrscheinlich wiederherstellen, **nachdem** Sie die Ransomware-Nutzlast (Schadsoftware) aus Ihrer Umgebung entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="647cd-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="647cd-120">Wenn Sie keine Sicherungen haben oder wenn Ihre Sicherungen auch von der Ransomware betroffen waren, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="647cd-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="647cd-121">Schritt 2: Deaktivieren von Exchange ActiveSync und OneDrive-Synchronisation</span><span class="sxs-lookup"><span data-stu-id="647cd-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="647cd-122">Der wichtigste Punkt hier ist, die Verbreitung der Datenverschlüsselung durch die Ransomware zu stoppen.</span><span class="sxs-lookup"><span data-stu-id="647cd-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="647cd-123">Wenn Sie E-Mails als Ziel der Ransomware-Verschlüsselung vermuten, deaktivieren Sie vorübergehend den Benutzerzugriff auf Postfächer.</span><span class="sxs-lookup"><span data-stu-id="647cd-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="647cd-124">Exchange ActiveSync synchronisiert Daten zwischen Geräten und Exchange Online Postfächern.</span><span class="sxs-lookup"><span data-stu-id="647cd-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="647cd-125">Informationen zum Deaktivieren Exchange ActiveSync für ein Postfach finden Sie unter [So deaktivieren Sie Exchange ActiveSync für Benutzer in Exchange Online](https://support.microsoft.com/help/2795303).</span><span class="sxs-lookup"><span data-stu-id="647cd-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="647cd-126">Informationen zum Deaktivieren anderer Arten des Zugriffs auf ein Postfach finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="647cd-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="647cd-127">[Aktivieren oder Deaktivieren der MAPI für ein Postfach.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="647cd-127">[Enable or disable MAPI for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="647cd-128">Aktivieren oder Deaktivieren des POP3- oder IMAP4-Zugriffs für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="647cd-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="647cd-129">Das Anhalten OneDrive-Synchronisation schützt Ihre Clouddaten davor, von potenziell infizierten Geräten aktualisiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="647cd-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="647cd-130">Weitere Informationen finden Sie unter "Anhalten und Fortsetzen der [Synchronisierung" in OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)</span><span class="sxs-lookup"><span data-stu-id="647cd-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="647cd-131">Schritt 3: Entfernen der Schadsoftware von den betroffenen Geräten</span><span class="sxs-lookup"><span data-stu-id="647cd-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="647cd-132">Führen Sie einen vollständigen, aktuellen Antivirus-Scan auf allen verdächtigen Computern und Geräten aus, um die Nutzlast zu erkennen und zu entfernen, die der Ransomware zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="647cd-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="647cd-133">Vergessen Sie nicht, Geräte zu scannen, die Daten synchronisieren, oder die Ziele zugeordneter Netzlaufwerke.</span><span class="sxs-lookup"><span data-stu-id="647cd-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="647cd-134">Sie können [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) oder (für ältere Clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)verwenden.</span><span class="sxs-lookup"><span data-stu-id="647cd-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="647cd-135">Eine Alternative, die Ihnen auch hilft, Ransomware oder Schadsoftware zu entfernen, ist das [Tool zum Entfernen bösartiger Software (Malicious Software Removal Tool, MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="647cd-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="647cd-136">Wenn diese Optionen nicht funktionieren, können Sie [versuchen, Windows Defender Offline zu](https://support.microsoft.com/help/17466) verwenden oder [Probleme beim Erkennen und Entfernen von Schadsoftware zu beheben.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="647cd-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="647cd-137">Schritt 4: Wiederherstellen von Dateien auf einem bereinigten Computer oder Gerät</span><span class="sxs-lookup"><span data-stu-id="647cd-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="647cd-138">Nachdem Sie den vorherigen Schritt abgeschlossen haben, um die Ransomware-Nutzlast aus Ihrer Umgebung zu entfernen (wodurch die Ransomware Ihre Dateien nicht verschlüsseln oder entfernen kann), können Sie den [Dateiverlauf](https://support.microsoft.com/help/17128) in Windows 10 und Windows 8.1 oder Systemschutz in Windows 7 verwenden, um zu versuchen, Ihre lokalen Dateien und Ordner wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="647cd-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="647cd-139">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="647cd-139">**Notes**:</span></span>

- <span data-ttu-id="647cd-140">Einige Ransomware verschlüsselt oder löscht auch die Sicherungsversionen, sodass Sie den Dateiverlauf oder Systemschutz nicht zum Wiederherstellen von Dateien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="647cd-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="647cd-141">In diesem Fall müssen Sie Sicherungen auf externen Laufwerken oder Geräten verwenden, die nicht von der Ransomware oder OneDrive betroffen waren, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="647cd-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="647cd-142">Wenn ein Ordner mit OneDrive synchronisiert wird und Sie nicht die neueste Version von Windows verwenden, gibt es möglicherweise einige Einschränkungen beim Verwenden des Dateiverlaufs.</span><span class="sxs-lookup"><span data-stu-id="647cd-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="647cd-143">Schritt 5: Wiederherstellen Ihrer Dateien in Ihrem OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="647cd-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="647cd-144">Mit der Dateiwiederherstellung in OneDrive for Business können Sie ihre gesamte OneDrive innerhalb der letzten 30 Tage auf einen früheren Zeitpunkt wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="647cd-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="647cd-145">Weitere Informationen finden Sie unter [Wiederherstellen Ihres OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span><span class="sxs-lookup"><span data-stu-id="647cd-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="647cd-146">Schritt 6: Wiederherstellen gelöschter E-Mails</span><span class="sxs-lookup"><span data-stu-id="647cd-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="647cd-147">In dem seltenen Fall, dass die Ransomware alle Ihre E-Mails gelöscht hat, können Sie wahrscheinlich die gelöschten Elemente wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="647cd-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="647cd-148">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="647cd-148">For more information, see:</span></span>

- [<span data-ttu-id="647cd-149">Wiederherstellen von gelöschten Nachrichten im Postfach eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="647cd-149">Recover deleted messages in a user's mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="647cd-150">Wiederherstellen gelöschter Elemente in Outlook für Windows</span><span class="sxs-lookup"><span data-stu-id="647cd-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="647cd-151">Schritt 7: Erneutes Aktivieren von Exchange ActiveSync und OneDrive-Synchronisation</span><span class="sxs-lookup"><span data-stu-id="647cd-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="647cd-152">Nachdem Sie Ihre Computer und Geräte bereinigt und Ihre Daten wiederhergestellt haben, können Sie Exchange ActiveSync und OneDrive-Synchronisation, die Sie zuvor in [Schritt 2](#step-2-disable-exchange-activesync-and-onedrive-sync)deaktiviert haben, erneut aktivieren.</span><span class="sxs-lookup"><span data-stu-id="647cd-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="647cd-153">Schritt 8 (Optional): Blockieren OneDrive-Synchronisation für bestimmte Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="647cd-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="647cd-154">Nachdem Sie die Wiederherstellung ausgeführt haben, können Sie verhindern, dass OneDrive for Business Clients die Dateitypen synchronisieren, die von dieser Ransomware betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="647cd-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="647cd-155">Weitere Informationen finden Sie unter ["Set-SPOTenantSyncClientRestriction"](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="647cd-155">For more information, see [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="647cd-156">Melden des Angriffs</span><span class="sxs-lookup"><span data-stu-id="647cd-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="647cd-157">Kontakt mit Strafverfolgungsbehörden</span><span class="sxs-lookup"><span data-stu-id="647cd-157">Contact law enforcement</span></span>

<span data-ttu-id="647cd-158">Sie sollten sich an Ihre lokalen oder Bundesbehörden für Strafverfolgungsbehörden wenden.</span><span class="sxs-lookup"><span data-stu-id="647cd-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="647cd-159">Wenn Sie sich beispielsweise in den VEREINIGTEn Staaten befinden, können Sie sich an das [lokale FBI-Außendienst,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) oder [den Geheimen Dienst](http://www.secretservice.gov/)wenden.</span><span class="sxs-lookup"><span data-stu-id="647cd-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="647cd-160">Übermitteln eines Berichts an die Website für Betrugsberichte Ihres Landes</span><span class="sxs-lookup"><span data-stu-id="647cd-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="647cd-161">Websites für Betrugsberichte bieten Informationen dazu, wie Sie Betrug verhindern und vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="647cd-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="647cd-162">Sie bieten auch Mechanismen, um zu melden, ob Sie Opfer eines Betrugs waren.</span><span class="sxs-lookup"><span data-stu-id="647cd-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="647cd-163">Australien: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="647cd-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="647cd-164">Kanada: [Canada Anti-Fraud Center](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="647cd-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="647cd-165">Frankreich: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="647cd-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="647cd-166">Deutschland: [Doppelklicken für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="647cd-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="647cd-167">Irland: [An Bali Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="647cd-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="647cd-168">Neuseeland: [Betrug bei Verbraucherfragen](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="647cd-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="647cd-169">Schweiz [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span><span class="sxs-lookup"><span data-stu-id="647cd-169">Switzerland [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span></span>

- <span data-ttu-id="647cd-170">Vereinigtes Königreich: [Betrugsaktion](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="647cd-170">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="647cd-171">Vereinigte Staaten: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="647cd-171">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="647cd-172">Wenn Ihr Land nicht aufgeführt ist, fragen Sie Ihre lokalen oder bundeseigenen Strafverfolgungsbehörden.</span><span class="sxs-lookup"><span data-stu-id="647cd-172">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="647cd-173">Senden von E-Mail-Nachrichten an Microsoft</span><span class="sxs-lookup"><span data-stu-id="647cd-173">Submit email messages to Microsoft</span></span>

<span data-ttu-id="647cd-174">Sie können Phishingnachrichten, die Ransomware enthalten, mithilfe einer von mehreren Methoden melden.</span><span class="sxs-lookup"><span data-stu-id="647cd-174">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="647cd-175">Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="647cd-175">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="additional-ransomware-resources"></a><span data-ttu-id="647cd-176">Zusätzliche Ransomware-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="647cd-176">Additional ransomware resources</span></span>

<span data-ttu-id="647cd-177">Wichtige Brancheninformationen:</span><span class="sxs-lookup"><span data-stu-id="647cd-177">Key industry information:</span></span>

- [<span data-ttu-id="647cd-178">Übersicht über die von Menschen betriebene Ransomware</span><span class="sxs-lookup"><span data-stu-id="647cd-178">Human-operated ransomware overview</span></span>](/security/compass/human-operated-ransomware)

- [<span data-ttu-id="647cd-179">Schneller Schutz vor Ransomware und Erpressung</span><span class="sxs-lookup"><span data-stu-id="647cd-179">Rapidly protect against ransomware and extortion</span></span>](/security/compass/protect-against-ransomware)

- <span data-ttu-id="647cd-180">[Der neueste Microsoft Security Intelligence Bericht](https://www.microsoft.com/securityinsights/) (siehe Seiten 22-24)</span><span class="sxs-lookup"><span data-stu-id="647cd-180">[The latest Microsoft Security Intelligence Report](https://www.microsoft.com/securityinsights/) (see pages 22-24)</span></span>

- <span data-ttu-id="647cd-181">**Ransomware: Ein weit verbreiteter und fortlaufender Bedrohungsbericht** im **Knoten "Bedrohungsanalyse"** des Microsoft 365 Defender-Portals (siehe diese [Lizenzierungsanforderungen)](/microsoft-365/security/defender/prerequisites#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="647cd-181">**Ransomware: A pervasive and ongoing threat** report in the **Threat analytics node** of the Microsoft 365 Defender portal (see these [licensing requirements](/microsoft-365/security/defender/prerequisites#licensing-requirements))</span></span>

<span data-ttu-id="647cd-182">Microsoft 365 Schutz:</span><span class="sxs-lookup"><span data-stu-id="647cd-182">Microsoft 365 protection:</span></span>

- [<span data-ttu-id="647cd-183">Schutz vor Schadsoftware und Ransomware</span><span class="sxs-lookup"><span data-stu-id="647cd-183">Malware and ransomware protection</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [<span data-ttu-id="647cd-184">Ransomware-Erkennung und Wiederherstellung Ihrer Dateien in OneDrive</span><span class="sxs-lookup"><span data-stu-id="647cd-184">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)
- [<span data-ttu-id="647cd-185">Aktivieren oder Deaktivieren von Makros in Office Dateien</span><span class="sxs-lookup"><span data-stu-id="647cd-185">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)
- [<span data-ttu-id="647cd-186">Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365 Sicherheit</span><span class="sxs-lookup"><span data-stu-id="647cd-186">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)

<span data-ttu-id="647cd-187">Blogbeiträge des Microsoft Security-Teams:</span><span class="sxs-lookup"><span data-stu-id="647cd-187">Microsoft Security team blog posts:</span></span>

- [<span data-ttu-id="647cd-188">Ausfallsicherheit durch Das Verständnis von Cybersicherheitsrisiken: Teil 4 – Navigieren in aktuellen Bedrohungen (Mai 2021)</span><span class="sxs-lookup"><span data-stu-id="647cd-188">Becoming resilient by understanding cybersecurity risks: Part 4—navigating current threats (May 2021)</span></span>](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  <span data-ttu-id="647cd-189">Weitere Informationen finden Sie im Abschnitt **"Ransomware".**</span><span class="sxs-lookup"><span data-stu-id="647cd-189">See the **Ransomware** section.</span></span>

- [<span data-ttu-id="647cd-190">Von Menschen betriebene Ransomware-Angriffe: Ein verhindbares Notfall (März 2020)</span><span class="sxs-lookup"><span data-stu-id="647cd-190">Human-operated ransomware attacks: A preventable disaster (March 2020)</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)
- [<span data-ttu-id="647cd-191">Ransomware-Antwort – zum Bezahlen oder nicht zum Bezahlen? (Dezember 2019)</span><span class="sxs-lookup"><span data-stu-id="647cd-191">Ransomware response—to pay or not to pay? (December 2019)</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [<span data-ttu-id="647cd-192">NorskAntwort reagiert mit Transparenz auf Ransomware-Angriffe (Dezember 2019)</span><span class="sxs-lookup"><span data-stu-id="647cd-192">Norsk Hydro responds to ransomware attack with transparency (December 2019)</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
- [<span data-ttu-id="647cd-193">Ein angemessenes Upgrade: Sicherheit der nächsten Generation auf Windows 10 erweist sich 2017 als stabil gegen Ransomware-Fälle (Januar 2018)</span><span class="sxs-lookup"><span data-stu-id="647cd-193">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017 (January 2018)</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

