---
title: So planen Sie ein Update von Microsoft Defender for Endpoint (Linux)
description: Erfahren Sie, wie Sie ein Update von Microsoft Defender for Endpoint (Linux) planen, um die Ressourcen Ihrer Organisation besser zu schützen.
keywords: microsoft, defender, atp, linux, scans, antivirus, microsoft defender for endpoint (linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b4c2e4d80628dab40de9e99abb27237176b9f171
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062464"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="e34ab-104">Planen eines Updates von Microsoft Defender for Endpoint (Linux)</span><span class="sxs-lookup"><span data-stu-id="e34ab-104">Schedule an update of the Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="e34ab-105">Informationen zum Ausführen eines Updates auf Microsoft Defender for Endpoint für Linux finden Sie unter [Deploy updates for Microsoft Defender for Endpoint for Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).</span><span class="sxs-lookup"><span data-stu-id="e34ab-105">To run an update on Microsoft Defender for Endpoint for Linux, see [Deploy updates for Microsoft Defender for Endpoint for Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).</span></span>

<span data-ttu-id="e34ab-106">Linux (und Unix) verfügen über ein Tool namens **"crontab"** (ähnlich wie Task Scheduler), um geplante Aufgaben ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="e34ab-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="e34ab-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e34ab-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="e34ab-108">Führen Sie den folgenden Befehl aus, um eine Liste aller Zeitzonen zu erhalten: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="e34ab-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="e34ab-109">Beispiele für Zeitzonen:</span><span class="sxs-lookup"><span data-stu-id="e34ab-109">Examples for timezones:</span></span> <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="e34ab-110">So legen Sie den Auftrag "Cron"</span><span class="sxs-lookup"><span data-stu-id="e34ab-110">To set the Cron job</span></span>
<span data-ttu-id="e34ab-111">Verwenden Sie die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="e34ab-111">Use the following commands:</span></span>

<span data-ttu-id="e34ab-112">**So sichern Sie "crontab"-Einträge**</span><span class="sxs-lookup"><span data-stu-id="e34ab-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> <span data-ttu-id="e34ab-113">Where 201118 == YYMMDD</span><span class="sxs-lookup"><span data-stu-id="e34ab-113">Where 201118 == YYMMDD</span></span>

> [!TIP]
> <span data-ttu-id="e34ab-114">Gehen Sie dazu vor dem Bearbeiten oder Entfernen vor.</span><span class="sxs-lookup"><span data-stu-id="e34ab-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="e34ab-115">So bearbeiten Sie die crontab, und fügen Sie einen neuen Auftrag als Stammbenutzer hinzu:</span><span class="sxs-lookup"><span data-stu-id="e34ab-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="e34ab-116">Der Standardeditor ist VIM.</span><span class="sxs-lookup"><span data-stu-id="e34ab-116">The default editor is VIM.</span></span>

<span data-ttu-id="e34ab-117">Möglicherweise sehen Sie:</span><span class="sxs-lookup"><span data-stu-id="e34ab-117">You might see:</span></span>

<span data-ttu-id="e34ab-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="e34ab-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="e34ab-119">Und</span><span class="sxs-lookup"><span data-stu-id="e34ab-119">And</span></span>

<span data-ttu-id="e34ab-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="e34ab-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span></span>

<span data-ttu-id="e34ab-121">Siehe [Planen von Scans mit Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span><span class="sxs-lookup"><span data-stu-id="e34ab-121">See [Schedule scans with Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span></span>

<span data-ttu-id="e34ab-122">Drücken Sie "Insert"</span><span class="sxs-lookup"><span data-stu-id="e34ab-122">Press “Insert”</span></span>

<span data-ttu-id="e34ab-123">Fügen Sie die folgenden Einträge hinzu:</span><span class="sxs-lookup"><span data-stu-id="e34ab-123">Add the following entries:</span></span>

<span data-ttu-id="e34ab-124">CRON_TZ=Amerika/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="e34ab-124">CRON_TZ=America/Los_Angeles</span></span>

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="e34ab-125">! RHEL und Varianten (CentOS und Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="e34ab-125">!RHEL and variants (CentOS and Oracle Linux)</span></span>

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a><span data-ttu-id="e34ab-126">! SLES und Varianten</span><span class="sxs-lookup"><span data-stu-id="e34ab-126">!SLES and variants</span></span>

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a><span data-ttu-id="e34ab-127">! Ubuntu- und Debian-Systeme</span><span class="sxs-lookup"><span data-stu-id="e34ab-127">!Ubuntu and Debian systems</span></span>

`06**sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> <span data-ttu-id="e34ab-128">In den obigen Beispielen wird dies auf 00 Minuten, 6 Uhr (Stunde im 24-Stunden-Format), jeden Tag des Monats, jeden Monat, sonntags, festlegen. [$(date + d) -le 15] == Wird nicht ausgeführt, es sei denn, er ist gleich oder kleiner als der \% 15. Tag (3. Woche).</span><span class="sxs-lookup"><span data-stu-id="e34ab-128">In the examples above, we are setting it to 00 minutes, 6 a.m.(hour in 24 hour format), any day of the month, any month, on Sundays.[$(date +\%d) -le 15] == Won’t run unless it’s equal or less than the 15th day (3rd week).</span></span> <span data-ttu-id="e34ab-129">Dies bedeutet, dass sie jeden dritten Sonntag (7) des Monats um 6:00 Uhr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e34ab-129">Meaning it will run every 3rd Sundays(7) of the month at 6:00 a.m.</span></span> <span data-ttu-id="e34ab-130">Pazifik (UTC -8).</span><span class="sxs-lookup"><span data-stu-id="e34ab-130">Pacific (UTC -8).</span></span>

<span data-ttu-id="e34ab-131">Drücken Sie "Esc"</span><span class="sxs-lookup"><span data-stu-id="e34ab-131">Press “Esc”</span></span>

<span data-ttu-id="e34ab-132">Geben Sie ":wq" w/o die doppelten Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="e34ab-132">Type “:wq” w/o the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="e34ab-133">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="e34ab-133">w == write, q == quit</span></span>

<span data-ttu-id="e34ab-134">Geben Sie ein, um Ihre aufträge für krümmungsaufträge anzeigen `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="e34ab-134">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="aktualisieren von MDE linux":::

<span data-ttu-id="e34ab-136">So überprüfen Sie die Ausgeführten von "cron"-Auftrags: `sudo grep mdatp /var/log/cron`</span><span class="sxs-lookup"><span data-stu-id="e34ab-136">To inspect cron job runs: `sudo grep mdatp /var/log/cron`</span></span>

<span data-ttu-id="e34ab-137">So überprüfen Sie mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span><span class="sxs-lookup"><span data-stu-id="e34ab-137">To inspect the mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span></span>

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="e34ab-138">Für diejenigen, die Ansible, Chef oder Puppet verwenden</span><span class="sxs-lookup"><span data-stu-id="e34ab-138">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="e34ab-139">Verwenden Sie die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="e34ab-139">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="e34ab-140">So legen Sie krümmte Aufträge in Ansible</span><span class="sxs-lookup"><span data-stu-id="e34ab-140">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="e34ab-141">Weitere Informationen finden Sie unter [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html).</span><span class="sxs-lookup"><span data-stu-id="e34ab-141">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="e34ab-142">So legen Sie "crontabs" in "Chef"</span><span class="sxs-lookup"><span data-stu-id="e34ab-142">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="e34ab-143">Weitere Informationen finden Sie unter [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/).</span><span class="sxs-lookup"><span data-stu-id="e34ab-143">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="e34ab-144">So legen Sie in "Puppet" "krümmte Aufträge"</span><span class="sxs-lookup"><span data-stu-id="e34ab-144">To set cron jobs in Puppet</span></span>
<span data-ttu-id="e34ab-145">Ressourcentyp: cron</span><span class="sxs-lookup"><span data-stu-id="e34ab-145">Resource Type: cron</span></span>

<span data-ttu-id="e34ab-146">Weitere Informationen finden Sie unter [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html).</span><span class="sxs-lookup"><span data-stu-id="e34ab-146">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="e34ab-147">Automatisieren mit "Puppet": Aufträge und geplante Aufgaben</span><span class="sxs-lookup"><span data-stu-id="e34ab-147">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="e34ab-148">Weitere Informationen finden Sie unter [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/).</span><span class="sxs-lookup"><span data-stu-id="e34ab-148">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="e34ab-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e34ab-149">Additional information</span></span>

<span data-ttu-id="e34ab-150">**So erhalten Sie Hilfe zu crontab**</span><span class="sxs-lookup"><span data-stu-id="e34ab-150">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="e34ab-151">**So erhalten Sie eine Liste der listenbenutzerdefinierten Dateien des aktuellen Benutzers**</span><span class="sxs-lookup"><span data-stu-id="e34ab-151">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="e34ab-152">**So erhalten Sie eine Liste der Listendatei eines anderen Benutzers**</span><span class="sxs-lookup"><span data-stu-id="e34ab-152">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="e34ab-153">**So sichern Sie "crontab"-Einträge**</span><span class="sxs-lookup"><span data-stu-id="e34ab-153">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="e34ab-154">Gehen Sie dazu vor dem Bearbeiten oder Entfernen vor.</span><span class="sxs-lookup"><span data-stu-id="e34ab-154">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="e34ab-155">**So stellen Sie "crontab"-Einträge wieder auf**</span><span class="sxs-lookup"><span data-stu-id="e34ab-155">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="e34ab-156">**So bearbeiten Sie die Crontab, und fügen Sie einen neuen Auftrag als Stammbenutzer hinzu**</span><span class="sxs-lookup"><span data-stu-id="e34ab-156">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="e34ab-157">**So bearbeiten Sie die crontab, und fügen Sie einen neuen Auftrag hinzu**</span><span class="sxs-lookup"><span data-stu-id="e34ab-157">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="e34ab-158">**So bearbeiten Sie die Crontabeinträge anderer Benutzer**</span><span class="sxs-lookup"><span data-stu-id="e34ab-158">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="e34ab-159">**So entfernen Sie alle Crontabeinträge**</span><span class="sxs-lookup"><span data-stu-id="e34ab-159">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="e34ab-160">**So entfernen Sie die Crontabeinträge anderer Benutzer**</span><span class="sxs-lookup"><span data-stu-id="e34ab-160">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="e34ab-161">**Erläuterung**</span><span class="sxs-lookup"><span data-stu-id="e34ab-161">**Explanation**</span></span>

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

