---
title: Microsoft Defender für Endpunkt unter Linux
ms.reviewer: ''
description: Beschreibt, wie Sie Microsoft Defender for Endpoint unter Linux installieren und verwenden.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34274e260da2e8acc8088fcff6d324b6b31fc2ef
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935941"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender für Endpunkt unter Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In diesem Thema wird beschrieben, wie Sie Microsoft Defender for Endpoint unter Linux installieren, konfigurieren, aktualisieren und verwenden.

> [!CAUTION]
> Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern neben Microsoft Defender for Endpoint unter Linux führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Nebenwirkungen. Wenn der Schutz von Nicht-Microsoft-Endpunkten in Ihrer Umgebung eine absolute Anforderung ist, können Sie die Funktionen von Defender for Endpoint unter Linux EDR weiterhin sicher nutzen, nachdem Sie die Antivirenfunktionen so konfiguriert haben, dass sie im passiven Modus [ausgeführt werden.](linux-preferences.md#enable--disable-passive-mode)

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>Installieren von Microsoft Defender for Endpoint unter Linux

### <a name="prerequisites"></a>Voraussetzungen

- Zugriff auf das Microsoft Defender Security Center-Portal
- Linux-Verteilung mithilfe des [systemd System](https://systemd.io/) Managers
- Anfängererfahrung in Linux- und BASH-Skripting
- Administratorrechte auf dem Gerät (bei manueller Bereitstellung)

### <a name="installation-instructions"></a>Installationsanweisungen

Es gibt mehrere Methoden und Bereitstellungstools, die Sie zum Installieren und Konfigurieren von Microsoft Defender for Endpoint unter Linux verwenden können.

Im Allgemeinen müssen Sie die folgenden Schritte ausführen:

- Stellen Sie sicher, dass Sie über ein Microsoft Defender for Endpoint-Abonnement verfügen und auf das [Microsoft Defender for Endpoint-Portal zugreifen können.](microsoft-defender-security-center.md)
- Stellen Sie Microsoft Defender for Endpoint unter Linux mithilfe einer der folgenden Bereitstellungsmethoden zur Verfügung:
  - Das Befehlszeilentool:
    - [Manuelle Bereitstellung](linux-install-manually.md)
  - Verwaltungstools von Drittanbietern:
    - [Bereitstellen mit dem Tool für die Konfiguration von "Puppet"](linux-install-with-puppet.md)
    - [Bereitstellen mithilfe des Ansible Configuration Management Tools](linux-install-with-ansible.md)

Wenn Installationsfehler auft werden, finden Sie informationen unter [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).

### <a name="system-requirements"></a>Systemanforderungen

- Unterstützte Linux-Serververteilungen und -versionen:

  - Red Hat Enterprise Linux 7.2 oder höher
  - CentOS 7.2 oder höher
  - Ubuntu 16.04 LTS oder höher LTS
  - Debian 9 oder höher
  - SUSE Linux Enterprise Server 12 oder höher
  - Oracle Linux 7.2 oder höher

- Minimale Kernelversion 3.10.0-327
- Die `fanotify` Kerneloption muss aktiviert sein
  > [!CAUTION]
  > Das Ausführen von Defender for Endpoint auf Linux neben anderen -basierten Sicherheitslösungen `fanotify` wird nicht unterstützt. Dies kann zu unvorhersehbaren Ergebnissen führen, einschließlich des Aufhängens des Betriebssystems.

- Speicherplatz: 1 GB
- /opt/microsoft/mdatp/sbin/wdavdaemon erfordert ausführbare Berechtigungen. Weitere Informationen finden Sie unter "Sicherstellen, dass der Daemon über ausführbare Berechtigungen verfügt" unter [Problembehandlung](/microsoft-365/security/defender-endpoint/linux-support-install)von Installationsproblemen für Microsoft Defender for Endpoint unter Linux .
- Arbeitsspeicher: 1 GB
    > [!NOTE]
    > Stellen Sie sicher, dass Sie freien Speicherplatz in /var haben.

- Die Lösung bietet derzeit Echtzeitschutz für die folgenden Dateisystemtypen:

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder ihre Firewall so konfigurieren, dass ausgehende Verbindungen zwischen dem Dienst und Ihren Endpunkten zulässig sind.

- Das Überwachungsframework ( `auditd` ) muss aktiviert sein.
  > [!NOTE]
  > Systemereignisse, die von Regeln erfasst werden, die hinzugefügt werden, werden zu (n) hinzugefügt und können sich auf die `/etc/audit/rules.d/` `audit.log` Hostüberwachung und die Upstreamsammlung auswirken. Ereignisse, die von Microsoft Defender for Endpoint unter Linux hinzugefügt werden, werden mit dem Schlüssel `mdatp` markiert.

### <a name="network-connections"></a>Netzwerkverbindungen

In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann. Sie sollten sicherstellen, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die den Zugriff auf diese URLs verweigern würden. Falls dies derFall ist, müssen Sie möglicherweise eine *speziell* für sie zulässige Regel erstellen.

|**Tabellenkalkulation der Domänenliste**|**Beschreibung**|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme. <br><br>[Laden Sie die Tabelle hier herunter.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> Eine spezifischere URL-Liste finden Sie unter [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).

Defender for Endpoint kann einen Proxyserver mithilfe der folgenden Ermittlungsmethoden ermitteln:
- Transparenter Proxy
- Manuelle Konfiguration statischer Proxys

Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist. Für transparente Proxys ist keine zusätzliche Konfiguration für Defender for Endpoint erforderlich. Führen Sie für statischen Proxy die Schritte unter [Manuelle statische Proxykonfiguration aus.](linux-static-proxy-configuration.md)

> [!WARNING]
> PAC-, WPAD- und authentifizierte Proxys werden nicht unterstützt. Stellen Sie sicher, dass nur ein statischer oder transparenter Proxy verwendet wird.
>
> Ssl-Überprüfung und Abfangen von Proxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt. Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Defender for Endpoint unter Linux direkt an die relevanten URLs ohne Abfangen zu übergeben. Wenn Sie Ihr Abfangzertifikat zum globalen Speicher hinzufügen, ist das Abfangen nicht zulässig.

Informationen zur Problembehandlung finden Sie unter [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>Aktualisieren von Microsoft Defender for Endpoint unter Linux

Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern. Informationen zum Aktualisieren von Microsoft Defender for Endpoint unter Linux finden Sie unter [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>Konfigurieren von Microsoft Defender for Endpoint unter Linux

Anleitungen zum Konfigurieren des Produkts in Unternehmensumgebungen finden Sie unter [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).

## <a name="resources"></a>Ressourcen

- Weitere Informationen zum Protokollieren, Deinstallieren oder anderen Themen finden Sie unter [Ressourcen](linux-resources.md).
