---
title: Microsoft Defender für Endpunkt unter Linux
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Linux installiert und verwendet wird.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Linux, Installation, bereitstellen, Deinstallation, entinstallation, ansible, linux, redhat, ubuntu, git, sles, suse, centos
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
ms.openlocfilehash: 4175d3bedff86dc7f8cdafc1ff2366ca1c9cffc4
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893740"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender für Endpunkt unter Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In diesem Thema wird beschrieben, wie Sie Microsoft Defender für Endpunkt unter Linux installieren, konfigurieren, aktualisieren und verwenden.

> [!CAUTION]
> Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Microsoft Defender für Endpunkt unter Linux führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Nebeneffekten. Wenn der Schutz nicht von Microsoft stammender Endpunkte eine absolute Anforderung in Ihrer Umgebung ist, können Sie nach der Konfiguration der Antivirenfunktionen für die Ausführung im [passiven Modus](linux-preferences.md#enable--disable-passive-mode)weiterhin die Funktionen von Defender für Endpunkt unter Linux EDR nutzen.

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>So installieren Sie Microsoft Defender für Endpunkt unter Linux

### <a name="prerequisites"></a>Voraussetzungen

- Zugriff auf das Microsoft Defender Security Center-Portal
- Linux-Verteilung mithilfe des [systemierten](https://systemd.io/) System-Managers
- Anfängererfahrung in Linux- und BASH-Skripting
- Administratorrechte auf dem Gerät (bei manueller Bereitstellung)

> [!NOTE]
>  Microsoft Defender für Endpunkt unter Linux-Agent ist unabhängig vom [OMS-Agent.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent) Microsoft Defender für Endpunkt basiert auf einer eigenen unabhängigen Telemetriepipeline.
> 
> Microsoft Defender für Endpunkt unter Linux ist noch nicht in Azure Security Center integriert.



### <a name="installation-instructions"></a>Installationsanweisungen

Es gibt mehrere Methoden und Bereitstellungstools, mit denen Sie Microsoft Defender für Endpunkt unter Linux installieren und konfigurieren können.

Im Allgemeinen müssen Sie die folgenden Schritte ausführen:

- Stellen Sie sicher, dass Sie über ein Microsoft Defender für Endpunkt-Abonnement verfügen und Zugriff auf das [Microsoft Defender für Endpunkt-Portal](microsoft-defender-security-center.md)haben.
- Stellen Sie Microsoft Defender für Endpunkt unter Linux mithilfe einer der folgenden Bereitstellungsmethoden bereit:
  - Das Befehlszeilentool:
    - [Manuelle Bereitstellung](linux-install-manually.md)
  - Verwaltungstools von Drittanbietern:
    - [Bereitstellen mithilfe des Konfigurationsverwaltungstools für die Konfiguration von "Durchbauen"](linux-install-with-puppet.md)
    - [Bereitstellen mithilfe des Ansible-Konfigurationsverwaltungstools](linux-install-with-ansible.md)

Wenn Installationsfehler auftreten, finden Sie informationen zur [Problembehandlung von Installationsfehlern in Microsoft Defender für Endpunkt unter Linux.](linux-support-install.md)



### <a name="system-requirements"></a>Systemanforderungen

- Unterstützte Linux-Serververteilungen und x64-Versionen (AMD64/EM64T):

  - Red Hat Enterprise Linux 7.2 oder höher
  - CentOS 7.2 oder höher
  - Ubuntu 16.04 LTS oder höher LTS
  - Ubuntu 9 oder höher
  - SUSE Linux Enterprise Server 12 oder höher
  - Oracle Linux 7.2 oder höher

    > [!NOTE]
    > Verteilungen und Versionen, die nicht explizit aufgeführt sind, werden nicht unterstützt (auch wenn sie von den offiziell unterstützten Distributionen abgeleitet sind).


- Minimale Kernelversion 3.10.0-327

- Die `fanotify` Kerneloption muss aktiviert sein.

  > [!CAUTION]
  > Das parallele Ausführen von Defender für Endpunkt unter Linux mit anderen `fanotify` -basierten Sicherheitslösungen wird nicht unterstützt. Dies kann zu unvorhersehbaren Ergebnissen führen, z. B. zum Hängen des Betriebssystems.

- Speicherplatz: 1 GB

- /opt/microsoft/mdatp/sbin/wdavdaemon erfordert eine ausführbare Berechtigung. Weitere Informationen finden Sie unter "Sicherstellen, dass der Daemon über ausführbare Berechtigungen verfügt" in [der Problembehandlung von Installationsproblemen für Microsoft Defender für Endpunkt unter Linux.](/microsoft-365/security/defender-endpoint/linux-support-install)

- Kerne: mindestens 2, 4 bevorzugt

- Arbeitsspeicher: mindestens 1 GB, 4 bevorzugt

    > [!NOTE]
    > Stellen Sie sicher, dass Sie über freien Speicherplatz in /var verfügen.

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

Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder Ihre Firewall konfigurieren, um ausgehende Verbindungen zwischen ihm und Ihren Endpunkten zuzulassen.

- Überwachungsframework ( `auditd` ) muss aktiviert sein.
  > [!NOTE]
  > Systemereignisse, die von Regeln erfasst werden, die hinzugefügt `/etc/audit/rules.d/` werden, werden `audit.log` (n) hinzugefügt und können sich auf die Hostüberwachung und die Upstreamsammlung auswirken. Ereignisse, die von Microsoft Defender für Endpunkt unter Linux hinzugefügt wurden, werden mit `mdatp` Schlüssel gekennzeichnet.

### <a name="network-connections"></a>Netzwerkverbindungen

In der folgenden herunterladbaren Tabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit denen ihr Netzwerk eine Verbindung herstellen kann. Sie sollten sicherstellen, dass keine Firewall- oder Netzwerkfilterregeln vorhanden sind, die den Zugriff auf diese URLs verweigern würden. Falls vorhanden, müssen Sie möglicherweise eine *Zulassungsregel* speziell für sie erstellen.

| Kalkulationstabelle der Domänenliste | Beschreibung |
|:-----|:-----|
|![Miniaturbild für Microsoft Defender für Endpunkt-URLs-Tabellenkalkulation](images/mdatp-urls.png)<br/>  | Kalkulationstabelle für bestimmte DNS-Einträge für Dienststandorte, geografische Standorte und Das Betriebssystem. <br><br>[Laden Sie das Arbeitsblatt hier herunter.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> Eine spezifischere URL-Liste finden Sie unter [Konfigurieren von Proxy- und Internetverbindungseinstellungen.](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)

Defender für Endpunkt kann einen Proxyserver mithilfe der folgenden Ermittlungsmethoden ermitteln:
- Transparenter Proxy
- Manuelle Konfiguration statischer Proxys

Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist. Für transparente Proxys ist keine zusätzliche Konfiguration für Defender für Endpunkt erforderlich. Führen Sie für statischen Proxy die Schritte in [manual Static Proxy Configuration](linux-static-proxy-configuration.md)aus.

> [!WARNING]
> PAC-, WPAD- und authentifizierte Proxys werden nicht unterstützt. Stellen Sie sicher, dass nur ein statischer oder ein transparenter Proxy verwendet wird.
>
> SSL-Überprüfungs- und -Abfangproxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt. Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Defender für Endpunkt unter Linux direkt an die relevanten URLs ohne Interception zu übergeben. Das Hinzufügen des Interception-Zertifikats zum globalen Speicher lässt keine Interception zu.

Informationen zur Problembehandlung finden Sie unter [Behandeln von Problemen mit der Cloudkonnektivität für Microsoft Defender für Endpunkt unter Linux.](linux-support-connectivity.md)

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>Aktualisieren von Microsoft Defender für Endpunkt unter Linux

Microsoft veröffentlicht regelmäßig Softwareupdates, um Leistung, Sicherheit und neue Features zu verbessern. Informationen zum Aktualisieren von Microsoft Defender für Endpunkt unter Linux finden Sie unter [Bereitstellen von Updates für Microsoft Defender für Endpunkt unter Linux.](linux-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>So konfigurieren Sie Microsoft Defender für Endpunkt unter Linux

Anleitungen zum Konfigurieren des Produkts in Unternehmensumgebungen finden Sie unter Festlegen von [Einstellungen für Microsoft Defender für Endpunkt unter Linux.](linux-preferences.md)

## <a name="resources"></a>Ressourcen

- Weitere Informationen zur Protokollierung, Deinstallation oder anderen Themen finden Sie unter [Ressourcen.](linux-resources.md)
