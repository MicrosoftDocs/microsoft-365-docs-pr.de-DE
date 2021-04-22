---
title: Planen von Scans mit Microsoft Defender for Endpoint (Linux)
description: Erfahren Sie, wie Sie eine automatische Überprüfungszeit für Microsoft Defender for Endpoint (Linux) planen, um die Ressourcen Ihrer Organisation besser zu schützen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, scans, antivirus, microsoft defender for endpoint (linux)
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
ms.openlocfilehash: f868570fccf9b30cde5f16aa8e71292fb8b09497
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933133"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="b0d75-104">Planen von Scans mit Microsoft Defender for Endpoint (Linux)</span><span class="sxs-lookup"><span data-stu-id="b0d75-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="b0d75-105">Informationen zum Ausführen einer Überprüfung für Linux finden Sie unter [Supported Commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span><span class="sxs-lookup"><span data-stu-id="b0d75-105">To run a scan for Linux, see [Supported Commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="b0d75-106">Linux (und Unix) verfügen über ein Tool namens **"crontab"** (ähnlich wie Task Scheduler), um geplante Aufgaben ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="b0d75-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="b0d75-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b0d75-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="b0d75-108">Führen Sie den folgenden Befehl aus, um eine Liste aller Zeitzonen zu erhalten: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="b0d75-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="b0d75-109">Beispiele für Zeitzonen:</span><span class="sxs-lookup"><span data-stu-id="b0d75-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="b0d75-110">So legen Sie den Auftrag "Cron"</span><span class="sxs-lookup"><span data-stu-id="b0d75-110">To set the Cron job</span></span>
<span data-ttu-id="b0d75-111">Verwenden Sie die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="b0d75-111">Use the following commands:</span></span>

<span data-ttu-id="b0d75-112">**So sichern Sie "crontab"-Einträge**</span><span class="sxs-lookup"><span data-stu-id="b0d75-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="b0d75-113">Where 200919 == YRMMDD</span><span class="sxs-lookup"><span data-stu-id="b0d75-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="b0d75-114">Gehen Sie dazu vor dem Bearbeiten oder Entfernen vor.</span><span class="sxs-lookup"><span data-stu-id="b0d75-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="b0d75-115">So bearbeiten Sie die crontab, und fügen Sie einen neuen Auftrag als Stammbenutzer hinzu:</span><span class="sxs-lookup"><span data-stu-id="b0d75-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="b0d75-116">Der Standardeditor ist VIM.</span><span class="sxs-lookup"><span data-stu-id="b0d75-116">The default editor is VIM.</span></span>

<span data-ttu-id="b0d75-117">Möglicherweise sehen Sie:</span><span class="sxs-lookup"><span data-stu-id="b0d75-117">You might see:</span></span>

<span data-ttu-id="b0d75-118">0 \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="b0d75-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="b0d75-119">Drücken Sie "Insert"</span><span class="sxs-lookup"><span data-stu-id="b0d75-119">Press “Insert”</span></span>

<span data-ttu-id="b0d75-120">Fügen Sie die folgenden Einträge hinzu:</span><span class="sxs-lookup"><span data-stu-id="b0d75-120">Add the following entries:</span></span>

<span data-ttu-id="b0d75-121">CRON_TZ=Amerika/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="b0d75-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="b0d75-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="b0d75-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="b0d75-123">In diesem Beispiel haben wir ihn auf 00 Minuten, 2:00 Uhr, festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b0d75-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="b0d75-124">(Stunde im 24-Stunden-Format), jeden Tag des Monats, jeden Monat, samstags.</span><span class="sxs-lookup"><span data-stu-id="b0d75-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="b0d75-125">Dies bedeutet, dass sie samstags um 2:00 Uhr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b0d75-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="b0d75-126">Pazifik (UTC –8).</span><span class="sxs-lookup"><span data-stu-id="b0d75-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="b0d75-127">Drücken Sie "Esc"</span><span class="sxs-lookup"><span data-stu-id="b0d75-127">Press “Esc”</span></span>

<span data-ttu-id="b0d75-128">Geben Sie ":wq" ohne doppelte Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="b0d75-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="b0d75-129">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="b0d75-129">w == write, q == quit</span></span>

<span data-ttu-id="b0d75-130">Geben Sie ein, um Ihre aufträge für krümmungsaufträge anzeigen `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="b0d75-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

<span data-ttu-id="b0d75-132">**So überprüfen Sie die Ausgeführten von krümmungsauftragen**</span><span class="sxs-lookup"><span data-stu-id="b0d75-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="b0d75-133">**So überprüfen Sie mdatp_cron_job.log**</span><span class="sxs-lookup"><span data-stu-id="b0d75-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="b0d75-134">Für diejenigen, die Ansible, Chef oder Puppet verwenden</span><span class="sxs-lookup"><span data-stu-id="b0d75-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="b0d75-135">Verwenden Sie die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="b0d75-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="b0d75-136">So legen Sie krümmte Aufträge in Ansible</span><span class="sxs-lookup"><span data-stu-id="b0d75-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="b0d75-137">Weitere Informationen finden Sie unter [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html).</span><span class="sxs-lookup"><span data-stu-id="b0d75-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="b0d75-138">So legen Sie "crontabs" in "Chef"</span><span class="sxs-lookup"><span data-stu-id="b0d75-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="b0d75-139">Weitere Informationen finden Sie unter [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/).</span><span class="sxs-lookup"><span data-stu-id="b0d75-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="b0d75-140">So legen Sie in "Puppet" "krümmte Aufträge"</span><span class="sxs-lookup"><span data-stu-id="b0d75-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="b0d75-141">Ressourcentyp: cron</span><span class="sxs-lookup"><span data-stu-id="b0d75-141">Resource Type: cron</span></span>

<span data-ttu-id="b0d75-142">Weitere Informationen finden Sie unter [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html).</span><span class="sxs-lookup"><span data-stu-id="b0d75-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="b0d75-143">Automatisieren mit "Puppet": Aufträge und geplante Aufgaben</span><span class="sxs-lookup"><span data-stu-id="b0d75-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="b0d75-144">Weitere Informationen finden Sie unter [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/).</span><span class="sxs-lookup"><span data-stu-id="b0d75-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="b0d75-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0d75-145">Additional information</span></span>

<span data-ttu-id="b0d75-146">**So erhalten Sie Hilfe zu crontab**</span><span class="sxs-lookup"><span data-stu-id="b0d75-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="b0d75-147">**So erhalten Sie eine Liste der listenbenutzerdefinierten Dateien des aktuellen Benutzers**</span><span class="sxs-lookup"><span data-stu-id="b0d75-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="b0d75-148">**So erhalten Sie eine Liste der Listendatei eines anderen Benutzers**</span><span class="sxs-lookup"><span data-stu-id="b0d75-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="b0d75-149">**So sichern Sie "crontab"-Einträge**</span><span class="sxs-lookup"><span data-stu-id="b0d75-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="b0d75-150">Gehen Sie dazu vor dem Bearbeiten oder Entfernen vor.</span><span class="sxs-lookup"><span data-stu-id="b0d75-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="b0d75-151">**So stellen Sie "crontab"-Einträge wieder auf**</span><span class="sxs-lookup"><span data-stu-id="b0d75-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="b0d75-152">**So bearbeiten Sie die Crontab, und fügen Sie einen neuen Auftrag als Stammbenutzer hinzu**</span><span class="sxs-lookup"><span data-stu-id="b0d75-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="b0d75-153">**So bearbeiten Sie die crontab, und fügen Sie einen neuen Auftrag hinzu**</span><span class="sxs-lookup"><span data-stu-id="b0d75-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="b0d75-154">**So bearbeiten Sie die Crontabeinträge anderer Benutzer**</span><span class="sxs-lookup"><span data-stu-id="b0d75-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="b0d75-155">**So entfernen Sie alle Crontabeinträge**</span><span class="sxs-lookup"><span data-stu-id="b0d75-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="b0d75-156">**So entfernen Sie die Crontabeinträge anderer Benutzer**</span><span class="sxs-lookup"><span data-stu-id="b0d75-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="b0d75-157">**Erläuterung**</span><span class="sxs-lookup"><span data-stu-id="b0d75-157">**Explanation**</span></span>

<span data-ttu-id="b0d75-158">+—————- Minute (Werte: 0 – 59) (Sonderzeichen: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="b0d75-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="b0d75-159">| +————- Stunde (Werte: 0 – 23) (Sonderzeichen: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="b0d75-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="b0d75-160">| | +———- (Werte: 1 – 31) (Sonderzeichen: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="b0d75-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="b0d75-161">| | | +——- Monat (Werte: 1 – 12) (Sonderzeichen: ,- \* / )</span><span class="sxs-lookup"><span data-stu-id="b0d75-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="b0d75-162">| | | | +- Wochentag (Werte: 0 – 6) (Sonntag=0 oder 7) (Sonderzeichen: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="b0d75-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="b0d75-163">| | | | |\*\*\*\*\*-Befehl ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="b0d75-163">| | | | |\*\*\*\*\*command to be executed</span></span>


