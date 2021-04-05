---
title: Microsoft Defender ATP für Linux-Ressourcen
ms.reviewer: ''
description: Beschreibt Ressourcen für Microsoft Defender ATP für Linux, einschließlich der Deinstallation, der Erfassung von Diagnoseprotokollen, CLI-Befehlen und bekannten Problemen mit dem Produkt.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a4f2324bc47bdee38e1cdeed1e21b5f9063e9a5c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587064"
---
# <a name="resources"></a>Ressourcen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>Sammeln von Diagnoseinformationen

Wenn Sie ein Problem reproduzieren können, erhöhen Sie zuerst die Protokollierungsstufe, führen Sie das System für einige Zeit aus, und stellen Sie dann die Protokollierungsstufe auf die Standardeinstellung wieder dar.

1. Erhöhen des Protokollierungsgrads:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Reproduzieren Sie das Problem.

3. Führen Sie den folgenden Befehl aus, um die Protokolle von Defender for Endpoint zu sichern. Die Dateien werden in einem ZIP-Archiv gespeichert.

   ```bash
   sudo mdatp diagnostic create
   ```

    Mit diesem Befehl wird auch der Dateipfad zur Sicherung gedruckt, nachdem der Vorgang erfolgreich war:

   ```Output
   Diagnostic file created: <path to file>
   ```

4. Protokollierungsstufe wiederherstellen:

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>Probleme bei der Protokollinstallation

Wenn während der Installation ein Fehler auftritt, wird vom Installationsprogramm nur ein allgemeiner Fehler gemeldet.

Das detaillierte Protokoll wird in `/var/log/microsoft/mdatp_install.log` gespeichert. Wenn während der Installation Probleme auftreten, senden Sie uns diese Datei, damit wir die Ursache diagnostizieren können.

## <a name="uninstall"></a>Uninstall

Es gibt verschiedene Möglichkeiten, Defender for Endpoint für Linux zu deinstallieren. Wenn Sie ein Konfigurationstool wie "Puppet" verwenden, befolgen Sie die Anweisungen zur Paketentinstallation für das Konfigurationstool.

### <a name="manual-uninstallation"></a>Manuelle Deinstallation

- `sudo yum remove mdatp` für RHEL und variants(CentOS und Oracle Linux).
- `sudo zypper remove mdatp` für SLES und Varianten.
- `sudo apt-get purge mdatp` für Ubuntu- und Debian-Systeme.

## <a name="configure-from-the-command-line"></a>Konfigurieren über die Befehlszeile

Wichtige Aufgaben, z. B. das Steuern von Produkteinstellungen und das Auslösen von Bedarfsscans, können über die Befehlszeile ausgeführt werden.

### <a name="global-options"></a>Globale Optionen

Standardmäßig gibt das Befehlszeilentool das Ergebnis im lesbaren Format aus. Darüber hinaus unterstützt das Tool auch die Ausgabe des Ergebnisses als JSON, was für Automatisierungsszenarien nützlich ist. Um die Ausgabe in JSON zu ändern, übergeben Sie `--output json` an einen der folgenden Befehle.

### <a name="supported-commands"></a>Unterstützte Befehle

In der folgenden Tabelle sind Befehle für einige der gängigsten Szenarien aufgeführt. Führen `mdatp help` Sie das Terminal aus, um die vollständige Liste der unterstützten Befehle anzuzeigen.

|Gruppe                 |Szenario                                                |Befehl                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|Konfiguration         |Aktivieren/Deaktivieren des Echtzeitschutzes                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|Konfiguration         |Aktivieren/Deaktivieren der Verhaltensüberwachung                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|Konfiguration         |Aktivieren/Deaktivieren des Cloudschutzes                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|Konfiguration         |Aktivieren/Deaktivieren der Produktdiagnose                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|Konfiguration         |Aktivieren/Deaktivieren der automatischen Beispielübermittlung                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|Konfiguration         |Aktivieren/Deaktivieren des passiven AV-Modus                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|Konfiguration         |Hinzufügen/Entfernen eines Antivirenausschlusses für eine Dateierweiterung  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|Konfiguration         |Hinzufügen/Entfernen eines Antivirenausschlusses für eine Datei            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|Konfiguration         |Hinzufügen/Entfernen eines Antivirenausschlusses für ein Verzeichnis       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|Konfiguration         |Hinzufügen/Entfernen eines Antivirenausschlusses für einen Prozess         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|Konfiguration         |Auflisten aller Antivirenausschlüsse                           |`mdatp exclusion list`                                                 |
|Konfiguration         |Hinzufügen eines Bedrohungsnamens zur liste der zulässigen Bedrohungen                   |`mdatp threat allowed add --name [threat-name]`                        |
|Konfiguration         |Entfernen eines Bedrohungsnamens aus der liste der zulässigen Bedrohungen              |`mdatp threat allowed remove --name [threat-name]`                     |
|Konfiguration         |Auflisten aller zulässigen Bedrohungsnamen                           |`mdatp threat allowed list`                                            |
|Konfiguration         |Aktivieren des PUA-Schutzes                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|Konfiguration         |Deaktivieren des PUA-Schutzes                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|Konfiguration         |Aktivieren des Überwachungsmodus für den PUA-Schutz                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|Diagnose           |Ändern der Protokollebene                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|Diagnose           |Generieren von Diagnoseprotokollen                                |`mdatp diagnostic create --path [directory]`                           |
|Gesundheitswesen                |Überprüfen des Produktzustands                              |`mdatp health`                                                         |
|Schutz            |Überprüfen eines Pfads                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|Schutz            |Schnellscan durchführen                                         |`mdatp scan quick`                                                     |
|Schutz            |Durchführen einer vollständigen Überprüfung                                          |`mdatp scan full`                                                      |
|Schutz            |Abbrechen einer laufenden Überprüfung bei Bedarf                        |`mdatp scan cancel`                                                    |
|Schutz            |Anfordern eines Security Intelligence-Updates                  |`mdatp definitions update`                                             |
|Schutzverlauf    |Drucken des vollständigen Schutzverlaufs                       |`mdatp threat list`                                                    |
|Schutzverlauf    |Erhalten von Bedrohungsdetails                                      |`mdatp threat get --id [threat-id]`                                    |
|Quarantäneverwaltung |Auflisten aller isolierten Dateien                              |`mdatp threat quarantine list`                                         |
|Quarantäneverwaltung |Entfernen aller Dateien aus der Quarantäne                    |`mdatp threat quarantine remove-all`                                   |
|Quarantäneverwaltung |Hinzufügen einer Als Bedrohung erkannten Datei zur Quarantäne       |`mdatp threat quarantine add --id [threat-id]`                         |
|Quarantäneverwaltung |Entfernen einer als Bedrohung erkannten Datei aus der Quarantäne  |`mdatp threat quarantine remove --id [threat-id]`                      |
|Quarantäneverwaltung |Wiederherstellen einer Datei aus der Quarantäne                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|Endpunkterkennung und -reaktion |Festlegen einer frühen Vorschau (nicht verwendet)                    |`mdatp edr early-preview [enable|disable]`                             |
|Endpunkterkennung und -reaktion |Festlegen der Gruppen-ID                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|Endpunkterkennung und -reaktion |Set/Remove-Tag, nur `GROUP` unterstützt        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|Endpunkterkennung und -reaktion |Listenausschlüsse (Stamm)                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Informationen zum Microsoft Defender for Endpoint-Portal

Im Defender for Endpoint-Portal werden zwei Kategorien von Informationen angezeigt:

- Antiviruswarnungen, einschließlich:
  - Severity
  - Scantyp
  - Geräteinformationen (Hostname, Geräte-ID, Mandanten-ID, App-Version und Betriebssystemtyp)
  - Dateiinformationen (Name, Pfad, Größe und Hash)
  - Bedrohungsinformationen (Name, Typ und Status)
- Geräteinformationen, einschließlich:
  - Geräte-ID
  - Mandanten-ID
  - Version der App
  - Hostname
  - Betriebssystemtyp
  - Betriebssystemversion
  - Computermodell
  - Prozessorarchitektur
  - Gibt an, ob es sich bei dem Gerät um einen virtuellen Computer handelt

### <a name="known-issues"></a>Bekannte Probleme

- Möglicherweise wird auf der Computerinformationsseite des Microsoft Defender Security Center-Portals "Keine Sensordaten, beeinträchtigte Kommunikation" angezeigt, obwohl das Produkt wie erwartet funktioniert. Wir arbeiten daran, dieses Problem zu beheben.
- Angemeldete Benutzer werden nicht im Microsoft Defender Security Center-Portal angezeigt.
- Wenn bei der Installation von *libatomic1* in SUSE-Verteilungen ein Fehler auftritt, sollten Sie überprüfen, ob Ihr Betriebssystem registriert ist:

   ```bash
   sudo SUSEConnect --status-text
   ```
