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
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>Planen eines Updates von Microsoft Defender for Endpoint (Linux)

Informationen zum Ausführen eines Updates auf Microsoft Defender for Endpoint für Linux finden Sie unter [Deploy updates for Microsoft Defender for Endpoint for Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).

Linux (und Unix) verfügen über ein Tool namens **"crontab"** (ähnlich wie Task Scheduler), um geplante Aufgaben ausführen zu können.

## <a name="pre-requisite"></a>Voraussetzungen

> [!NOTE]
> Führen Sie den folgenden Befehl aus, um eine Liste aller Zeitzonen zu erhalten: `timedatectl list-timezones`<br>
> Beispiele für Zeitzonen: <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>So legen Sie den Auftrag "Cron"
Verwenden Sie die folgenden Befehle:

**So sichern Sie "crontab"-Einträge**

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> Where 201118 == YYMMDD

> [!TIP]
> Gehen Sie dazu vor dem Bearbeiten oder Entfernen vor. <br>

So bearbeiten Sie die crontab, und fügen Sie einen neuen Auftrag als Stammbenutzer hinzu: <br>
`sudo crontab -e`

> [!NOTE]
> Der Standardeditor ist VIM.

Möglicherweise sehen Sie:

0****/etc/opt/microsoft/mdatp/logrorate.sh

Und

02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log

Siehe [Planen von Scans mit Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)

Drücken Sie "Insert"

Fügen Sie die folgenden Einträge hinzu:

CRON_TZ=Amerika/Los_Angeles

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>! RHEL und Varianten (CentOS und Oracle Linux)

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a>! SLES und Varianten

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a>! Ubuntu- und Debian-Systeme

`06**sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> In den obigen Beispielen wird dies auf 00 Minuten, 6 Uhr (Stunde im 24-Stunden-Format), jeden Tag des Monats, jeden Monat, sonntags, festlegen. [$(date + d) -le 15] == Wird nicht ausgeführt, es sei denn, er ist gleich oder kleiner als der \% 15. Tag (3. Woche). Dies bedeutet, dass sie jeden dritten Sonntag (7) des Monats um 6:00 Uhr ausgeführt wird. Pazifik (UTC -8).

Drücken Sie "Esc"

Geben Sie ":wq" w/o die doppelten Anführungszeichen ein.

> [!NOTE]
> w == write, q == quit

Geben Sie ein, um Ihre aufträge für krümmungsaufträge anzeigen `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="aktualisieren von MDE linux":::

So überprüfen Sie die Ausgeführten von "cron"-Auftrags: `sudo grep mdatp /var/log/cron`

So überprüfen Sie mdatp_cron_job.log `sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Für diejenigen, die Ansible, Chef oder Puppet verwenden

Verwenden Sie die folgenden Befehle:
### <a name="to-set-cron-jobs-in-ansible"></a>So legen Sie krümmte Aufträge in Ansible

`cron – Manage cron.d and crontab entries`

Weitere Informationen finden Sie unter [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html).

### <a name="to-set-crontabs-in-chef"></a>So legen Sie "crontabs" in "Chef"
`cron resource`

Weitere Informationen finden Sie unter [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/).

### <a name="to-set-cron-jobs-in-puppet"></a>So legen Sie in "Puppet" "krümmte Aufträge"
Ressourcentyp: cron

Weitere Informationen finden Sie unter [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html).

Automatisieren mit "Puppet": Aufträge und geplante Aufgaben

Weitere Informationen finden Sie unter [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/).

## <a name="additional-information"></a>Weitere Informationen

**So erhalten Sie Hilfe zu crontab**

`man crontab`

**So erhalten Sie eine Liste der listenbenutzerdefinierten Dateien des aktuellen Benutzers**

`crontab -l`

**So erhalten Sie eine Liste der Listendatei eines anderen Benutzers**

`crontab -u username -l`

**So sichern Sie "crontab"-Einträge**

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> Gehen Sie dazu vor dem Bearbeiten oder Entfernen vor. <br>

**So stellen Sie "crontab"-Einträge wieder auf**

`crontab /var/tmp/cron_backup.dat`

**So bearbeiten Sie die Crontab, und fügen Sie einen neuen Auftrag als Stammbenutzer hinzu**

`sudo crontab -e`

**So bearbeiten Sie die crontab, und fügen Sie einen neuen Auftrag hinzu**

`crontab -e`

**So bearbeiten Sie die Crontabeinträge anderer Benutzer**

`crontab -u username -e`

**So entfernen Sie alle Crontabeinträge**

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

