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
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Planen von Scans mit Microsoft Defender für Endpunkt (Linux)

Informationen zum Ausführen eines Scans für Linux finden Sie unter ["Unterstützte Befehle".](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)

Linux (und Unix) verfügen über ein Tool namens **Crontab** (ähnlich wie Task Scheduler), um geplante Aufgaben ausführen zu können.

## <a name="pre-requisite"></a>Voraussetzungen

> [!NOTE]
> Führen Sie den folgenden Befehl aus, um eine Liste aller Zeitzonen abzurufen: `timedatectl list-timezones`<br>
> Beispiele für Zeitzonen:
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>So legen Sie den Cron-Auftrag fest
Verwenden Sie die folgenden Befehle:

**So sichern Sie Crontabeinträge**

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> Where 200919 == YRMMDD

> [!TIP]
> Führen Sie dies vor dem Bearbeiten oder Entfernen aus. <br>

So bearbeiten Sie die Crontab und fügen einen neuen Auftrag als Stammbenutzer hinzu: <br>
`sudo crontab -e`

> [!NOTE]
> Der Standard-Editor ist VIM.

Möglicherweise wird Folgendes angezeigt:

0 * * * * /etc/opt/microsoft/mdatp/logrorate.sh

Drücken Sie "Einfügen".

Fügen Sie die folgenden Einträge hinzu:

CRON_TZ=America/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log

> [!NOTE]
>In diesem Beispiel haben wir es auf 00 Minuten, 2:00 Uhr, festgelegt. (Stunde im 24-Stunden-Format), jeden Tag des Monats, jeden Monat, samstags. Dies bedeutet, dass sie samstags um 2:00 Uhr ausgeführt wird. Pacific (UTC –8).

Drücken Sie "Esc"

Geben Sie ":wq" ohne doppelte Anführungszeichen ein.

> [!NOTE]
> w == write, q == quit

Geben Sie zum Anzeigen Ihrer Cron-Aufträge `sudo crontab -l`

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

**So überprüfen Sie die Ausführung von Cron-Aufträgen**

`sudo grep mdatp /var/log/cron`

**So überprüfen Sie die mdatp_cron_job.log**

`sudo nano mdatp_cron_job.log`

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

+—————- Minute (Werte: 0 – 59) (Sonderzeichen: , – * /)  <br>
| +————- Stunde (Werte: 0 – 23) (Sonderzeichen: , – * /) <br>
| | +———- Tag des Monats (Werte: 1 – 31) (Sonderzeichen: , – * / L W C)  <br>
| | | +——- Monat (Werte: 1 – 12) (Sonderzeichen: ,- * / )  <br>
| | | | +- Wochentag (Werte: 0 – 6) (Sonntag= 0 oder 7) (Sonderzeichen: , – * / L W C) <br>
auszuführende | | | | |**-Befehl


