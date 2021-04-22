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
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Planen von Scans mit Microsoft Defender for Endpoint (Linux)

Informationen zum Ausführen einer Überprüfung für Linux finden Sie unter [Supported Commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).

Linux (und Unix) verfügen über ein Tool namens **"crontab"** (ähnlich wie Task Scheduler), um geplante Aufgaben ausführen zu können.

## <a name="pre-requisite"></a>Voraussetzungen

> [!NOTE]
> Führen Sie den folgenden Befehl aus, um eine Liste aller Zeitzonen zu erhalten: `timedatectl list-timezones`<br>
> Beispiele für Zeitzonen:
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>So legen Sie den Auftrag "Cron"
Verwenden Sie die folgenden Befehle:

**So sichern Sie "crontab"-Einträge**

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> Where 200919 == YRMMDD

> [!TIP]
> Gehen Sie dazu vor dem Bearbeiten oder Entfernen vor. <br>

So bearbeiten Sie die crontab, und fügen Sie einen neuen Auftrag als Stammbenutzer hinzu: <br>
`sudo crontab -e`

> [!NOTE]
> Der Standardeditor ist VIM.

Möglicherweise sehen Sie:

0 * * * /etc/opt/microsoft/mdatp/logrorate.sh

Drücken Sie "Insert"

Fügen Sie die folgenden Einträge hinzu:

CRON_TZ=Amerika/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log

> [!NOTE]
>In diesem Beispiel haben wir ihn auf 00 Minuten, 2:00 Uhr, festgelegt. (Stunde im 24-Stunden-Format), jeden Tag des Monats, jeden Monat, samstags. Dies bedeutet, dass sie samstags um 2:00 Uhr ausgeführt wird. Pazifik (UTC –8).

Drücken Sie "Esc"

Geben Sie ":wq" ohne doppelte Anführungszeichen ein.

> [!NOTE]
> w == write, q == quit

Geben Sie ein, um Ihre aufträge für krümmungsaufträge anzeigen `sudo crontab -l`

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

**So überprüfen Sie die Ausgeführten von krümmungsauftragen**

`sudo grep mdatp /var/log/cron`

**So überprüfen Sie mdatp_cron_job.log**

`sudo nano mdatp_cron_job.log`

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

+—————- Minute (Werte: 0 – 59) (Sonderzeichen: , – * /)  <br>
| +————- Stunde (Werte: 0 – 23) (Sonderzeichen: , – * /) <br>
| | +———- (Werte: 1 – 31) (Sonderzeichen: , – * / L W C)  <br>
| | | +——- Monat (Werte: 1 – 12) (Sonderzeichen: ,- * / )  <br>
| | | | +- Wochentag (Werte: 0 – 6) (Sonntag=0 oder 7) (Sonderzeichen: , – * / L W C) <br>
| | | | |*****-Befehl ausgeführt werden


