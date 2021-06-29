---
title: Planen eines Updates von Microsoft Defender für Endpunkt (Linux)
description: Erfahren Sie, wie Sie ein Update von Microsoft Defender für Endpunkt (Linux) planen, um die Ressourcen Ihrer Organisation besser zu schützen.
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
ms.openlocfilehash: 7ebb37e80cae0e9dd70d01600c47bd1459c122c3
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194901"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>Planen eines Updates von Microsoft Defender für Endpunkt (Linux)

Informationen zum Ausführen eines Updates auf Microsoft Defender für Endpunkt unter Linux finden Sie unter [Bereitstellen von Updates für Microsoft Defender für Endpunkt unter Linux.](/microsoft-365/security/defender-endpoint/linux-updates)

Linux (und Unix) verfügen über ein Tool namens **Crontab** (ähnlich wie Task Scheduler), um geplante Aufgaben ausführen zu können.

## <a name="pre-requisite"></a>Voraussetzungen

> [!NOTE]
> Führen Sie den folgenden Befehl aus, um eine Liste aller Zeitzonen abzurufen: `timedatectl list-timezones`<br>
> Beispiele für Zeitzonen: <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>So legen Sie den Cron-Auftrag fest
Verwenden Sie die folgenden Befehle:

**So sichern Sie Crontabeinträge**

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> Where 201118 == YYMMDD

> [!TIP]
> Führen Sie dies vor dem Bearbeiten oder Entfernen aus. <br>

So bearbeiten Sie die Crontab und fügen einen neuen Auftrag als Stammbenutzer hinzu: <br>
`sudo crontab -e`

> [!NOTE]
> Der Standard-Editor ist VIM.

Möglicherweise wird Folgendes angezeigt:

0.../etc/opt/microsoft/mdatp/logrorate.sh

Und

02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log

Siehe ["Planen von Scans mit Microsoft Defender für Endpunkt (Linux)](linux-schedule-scan-atp.md)

Drücken Sie "Einfügen".

Fügen Sie die folgenden Einträge hinzu:

CRON_TZ=America/Los_Angeles

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>! RHEL und Varianten (CentOS und Oracle Linux)

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a>! SLES und Varianten

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a>! Ubuntu- und Ubuntu-Systeme

`0 6 * * sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> In den obigen Beispielen legen wir sie auf 00 Minuten, 6 Uhr (Stunde im 24-Stunden-Format), jeden Tag des Monats, jeden Monat und sonntags fest. [$(date + \% d) -le 15] == Wird nur ausgeführt, wenn sie gleich oder kleiner als der 15. Tag (3. Woche) ist. Dies bedeutet, dass sie jeden 3. Sonntag(7) des Monats um 6:00 Uhr ausgeführt wird. Pacific (UTC -8).

Drücken Sie "Esc"

Geben Sie ":wq" mit den doppelten Anführungszeichen ein.

> [!NOTE]
> w == write, q == quit

Geben Sie zum Anzeigen Ihrer Cron-Aufträge `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="Aktualisieren von Defender für Endpunkt unter Linux":::

So überprüfen Sie die Ausführung von Cron-Aufträgen: `sudo grep mdatp /var/log/cron`

So überprüfen Sie die mdatp_cron_job.log `sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Für Diejenigen, die Ansible, Theater oder Diess verwenden

Verwenden Sie die folgenden Befehle:
### <a name="to-set-cron-jobs-in-ansible"></a>So legen Sie Cron-Aufträge in Ansible fest

`cron – Manage cron.d and crontab entries`

Weitere Informationen finden Sie unter [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html).

### <a name="to-set-crontabs-in-chef"></a>So legen Sie Crontabs in "Hobby" fest
`cron resource`

Weitere Informationen finden Sie unter [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/).

### <a name="to-set-cron-jobs-in-puppet"></a>So legen Sie Cron-Aufträge in "Überbauung" fest
Ressourcentyp: cron

Weitere Informationen finden Sie unter [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html).

Automatisieren mit "Aufarbeitung": Cron-Aufträge und geplante Aufgaben

Weitere Informationen finden Sie unter [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/).

## <a name="additional-information"></a>Weitere Informationen

**So erhalten Sie Hilfe zu Crontab**

`man crontab`

**So rufen Sie eine Liste der Crontab-Datei des aktuellen Benutzers ab**

`crontab -l`

**So rufen Sie eine Liste der Crontab-Datei eines anderen Benutzers ab**

`crontab -u username -l`

**So sichern Sie Crontabeinträge**

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> Führen Sie dies vor dem Bearbeiten oder Entfernen aus. <br>

**So stellen Sie Crontabeinträge wieder her**

`crontab /var/tmp/cron_backup.dat`

**So bearbeiten Sie die Crontab und fügen einen neuen Auftrag als Stammbenutzer hinzu**

`sudo crontab -e`

**So bearbeiten Sie die Crontab und fügen einen neuen Auftrag hinzu**

`crontab -e`

**So bearbeiten Sie die Crontabeinträge anderer Benutzer**

`crontab -u username -e`

**So entfernen Sie alle Crontab-Einträge**

`crontab -r`

**So entfernen Sie die Crontabeinträge anderer Benutzer**

`crontab -u username -r`

**Erläuterung**

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

