---
title: Planen von Scans mit Microsoft Defender für Endpunkt (Linux)
description: Erfahren Sie, wie Sie eine automatische Überprüfungszeit für Microsoft Defender für Endpunkt (Linux) planen, um die Ressourcen Ihrer Organisation besser zu schützen.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Linux, Scans, Antivirus, Microsoft Defender für Endpunkt (Linux)
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
ms.openlocfilehash: 5a4beaefb2fcc12d46cf61c22644217dce1807a6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845366"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="82009-104">Planen von Scans mit Microsoft Defender für Endpunkt (Linux)</span><span class="sxs-lookup"><span data-stu-id="82009-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="82009-105">Informationen zum Ausführen eines Scans für Linux finden Sie unter ["Unterstützte Befehle".](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)</span><span class="sxs-lookup"><span data-stu-id="82009-105">To run a scan for Linux, see [Supported Commands](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="82009-106">Linux (und Unix) verfügen über ein Tool namens **Crontab** (ähnlich wie Task Scheduler), um geplante Aufgaben ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="82009-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="82009-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="82009-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="82009-108">Führen Sie den folgenden Befehl aus, um eine Liste aller Zeitzonen abzurufen: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="82009-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="82009-109">Beispiele für Zeitzonen:</span><span class="sxs-lookup"><span data-stu-id="82009-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="82009-110">So legen Sie den Cron-Auftrag fest</span><span class="sxs-lookup"><span data-stu-id="82009-110">To set the Cron job</span></span>
<span data-ttu-id="82009-111">Verwenden Sie die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="82009-111">Use the following commands:</span></span>

<span data-ttu-id="82009-112">**So sichern Sie Crontabeinträge**</span><span class="sxs-lookup"><span data-stu-id="82009-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="82009-113">Where 200919 == YRMMDD</span><span class="sxs-lookup"><span data-stu-id="82009-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="82009-114">Führen Sie dies vor dem Bearbeiten oder Entfernen aus.</span><span class="sxs-lookup"><span data-stu-id="82009-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="82009-115">So bearbeiten Sie die Crontab und fügen einen neuen Auftrag als Stammbenutzer hinzu:</span><span class="sxs-lookup"><span data-stu-id="82009-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="82009-116">Der Standard-Editor ist VIM.</span><span class="sxs-lookup"><span data-stu-id="82009-116">The default editor is VIM.</span></span>

<span data-ttu-id="82009-117">Möglicherweise wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="82009-117">You might see:</span></span>

<span data-ttu-id="82009-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="82009-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="82009-119">Drücken Sie "Einfügen".</span><span class="sxs-lookup"><span data-stu-id="82009-119">Press “Insert”</span></span>

<span data-ttu-id="82009-120">Fügen Sie die folgenden Einträge hinzu:</span><span class="sxs-lookup"><span data-stu-id="82009-120">Add the following entries:</span></span>

<span data-ttu-id="82009-121">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="82009-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="82009-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="82009-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="82009-123">In diesem Beispiel haben wir es auf 00 Minuten, 2:00 Uhr, festgelegt.</span><span class="sxs-lookup"><span data-stu-id="82009-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="82009-124">(Stunde im 24-Stunden-Format), jeden Tag des Monats, jeden Monat, samstags.</span><span class="sxs-lookup"><span data-stu-id="82009-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="82009-125">Dies bedeutet, dass sie samstags um 2:00 Uhr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="82009-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="82009-126">Pacific (UTC –8).</span><span class="sxs-lookup"><span data-stu-id="82009-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="82009-127">Drücken Sie "Esc"</span><span class="sxs-lookup"><span data-stu-id="82009-127">Press “Esc”</span></span>

<span data-ttu-id="82009-128">Geben Sie ":wq" ohne doppelte Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="82009-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="82009-129">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="82009-129">w == write, q == quit</span></span>

<span data-ttu-id="82009-130">Geben Sie zum Anzeigen Ihrer Cron-Aufträge `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="82009-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

<span data-ttu-id="82009-132">**So überprüfen Sie die Ausführung von Cron-Aufträgen**</span><span class="sxs-lookup"><span data-stu-id="82009-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="82009-133">**So überprüfen Sie die mdatp_cron_job.log**</span><span class="sxs-lookup"><span data-stu-id="82009-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="82009-134">Für Diejenigen, die Ansible, Theater oder Diess verwenden</span><span class="sxs-lookup"><span data-stu-id="82009-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="82009-135">Verwenden Sie die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="82009-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="82009-136">So legen Sie Cron-Aufträge in Ansible fest</span><span class="sxs-lookup"><span data-stu-id="82009-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="82009-137">Weitere Informationen finden Sie unter [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html).</span><span class="sxs-lookup"><span data-stu-id="82009-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="82009-138">So legen Sie Crontabs in "Hobby" fest</span><span class="sxs-lookup"><span data-stu-id="82009-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="82009-139">Weitere Informationen finden Sie unter [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/).</span><span class="sxs-lookup"><span data-stu-id="82009-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="82009-140">So legen Sie Cron-Aufträge in "Überbauung" fest</span><span class="sxs-lookup"><span data-stu-id="82009-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="82009-141">Ressourcentyp: cron</span><span class="sxs-lookup"><span data-stu-id="82009-141">Resource Type: cron</span></span>

<span data-ttu-id="82009-142">Weitere Informationen finden Sie unter [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html).</span><span class="sxs-lookup"><span data-stu-id="82009-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="82009-143">Automatisieren mit "Aufarbeitung": Cron-Aufträge und geplante Aufgaben</span><span class="sxs-lookup"><span data-stu-id="82009-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="82009-144">Weitere Informationen finden Sie unter [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/).</span><span class="sxs-lookup"><span data-stu-id="82009-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="82009-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82009-145">Additional information</span></span>

<span data-ttu-id="82009-146">**So erhalten Sie Hilfe zu Crontab**</span><span class="sxs-lookup"><span data-stu-id="82009-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="82009-147">**So rufen Sie eine Liste der Crontab-Datei des aktuellen Benutzers ab**</span><span class="sxs-lookup"><span data-stu-id="82009-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="82009-148">**So rufen Sie eine Liste der Crontab-Datei eines anderen Benutzers ab**</span><span class="sxs-lookup"><span data-stu-id="82009-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="82009-149">**So sichern Sie Crontabeinträge**</span><span class="sxs-lookup"><span data-stu-id="82009-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="82009-150">Führen Sie dies vor dem Bearbeiten oder Entfernen aus.</span><span class="sxs-lookup"><span data-stu-id="82009-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="82009-151">**So stellen Sie Crontabeinträge wieder her**</span><span class="sxs-lookup"><span data-stu-id="82009-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="82009-152">**So bearbeiten Sie die Crontab und fügen einen neuen Auftrag als Stammbenutzer hinzu**</span><span class="sxs-lookup"><span data-stu-id="82009-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="82009-153">**So bearbeiten Sie die Crontab und fügen einen neuen Auftrag hinzu**</span><span class="sxs-lookup"><span data-stu-id="82009-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="82009-154">**So bearbeiten Sie die Crontabeinträge anderer Benutzer**</span><span class="sxs-lookup"><span data-stu-id="82009-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="82009-155">**So entfernen Sie alle Crontab-Einträge**</span><span class="sxs-lookup"><span data-stu-id="82009-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="82009-156">**So entfernen Sie die Crontabeinträge anderer Benutzer**</span><span class="sxs-lookup"><span data-stu-id="82009-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="82009-157">**Erläuterung**</span><span class="sxs-lookup"><span data-stu-id="82009-157">**Explanation**</span></span>

<span data-ttu-id="82009-158">+—————- Minute (Werte: 0 – 59) (Sonderzeichen: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="82009-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="82009-159">| +————- Stunde (Werte: 0 – 23) (Sonderzeichen: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="82009-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="82009-160">| | +———- Tag des Monats (Werte: 1 – 31) (Sonderzeichen: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="82009-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="82009-161">| | | +——- Monat (Werte: 1 – 12) (Sonderzeichen: ,- \* / )</span><span class="sxs-lookup"><span data-stu-id="82009-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="82009-162">| | | | +- Wochentag (Werte: 0 – 6) (Sonntag= 0 oder 7) (Sonderzeichen: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="82009-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="82009-163">auszuführende | | | | |\*\*-Befehl</span><span class="sxs-lookup"><span data-stu-id="82009-163">| | | | |\*\*\*\*\*command to be executed</span></span>


