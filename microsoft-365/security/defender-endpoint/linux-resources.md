---
title: Microsoft Defender für Endpunkt unter Linux-Ressourcen
ms.reviewer: ''
description: Beschreibt Ressourcen für Microsoft Defender für Endpunkt unter Linux, einschließlich der Deinstallation, der Erfassung von Diagnoseprotokollen, CLI-Befehlen und bekannten Problemen mit dem Produkt.
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aaf9c0a8eef4e050ca034d1aee69d24c5adb909d
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930367"
---
# <a name="resources"></a>Ressourcen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>Sammeln von Diagnoseinformationen

Wenn Sie ein Problem reproduzieren können, erhöhen Sie zunächst die Protokollierungsstufe, führen Sie das System für einige Zeit aus, und stellen Sie dann die Protokollierungsstufe auf die Standardeinstellung wieder her.

1. Erhöhen Sie die Protokollierungsstufe:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Reproduzieren Sie das Problem.

3. Führen Sie den folgenden Befehl aus, um die Protokolle von Defender für Endpunkt zu sichern. Die Dateien werden in einem .zip Archiv gespeichert.

   ```bash
   sudo mdatp diagnostic create
   ```

    Dieser Befehl gibt auch den Dateipfad zur Sicherung aus, nachdem der Vorgang erfolgreich war:

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

## <a name="log-installation-issues"></a>Protokollieren von Installationsproblemen

Wenn während der Installation ein Fehler auftritt, meldet das Installationsprogramm nur einen allgemeinen Fehler.

Das detaillierte Protokoll wird in `/var/log/microsoft/mdatp/install.log` gespeichert.
Wenn während der Installation Probleme auftreten, senden Sie uns diese Datei, damit wir Ihnen bei der Diagnose der Ursache helfen können.

## <a name="uninstall"></a>Deinstallieren

Es gibt mehrere Möglichkeiten, Defender für Endpunkt unter Linux zu deinstallieren. Wenn Sie ein Konfigurationstool wie Vertrauenswürdige verwenden, befolgen Sie die Anweisungen zum Deinstallationspaket für das Konfigurationstool.

### <a name="manual-uninstallation"></a>Manuelle Deinstallation

- `sudo yum remove mdatp` für RHEL und Varianten (CentOS und Oracle Linux).
- `sudo zypper remove mdatp` für SLES und Varianten.
- `sudo apt-get purge mdatp` für Ubuntu- und Ubuntu-Systeme.

## <a name="configure-from-the-command-line"></a>Konfigurieren über die Befehlszeile

Wichtige Aufgaben, z. B. das Steuern von Produkteinstellungen und das Auslösen von Scans bei Bedarf, können über die Befehlszeile ausgeführt werden.

### <a name="global-options"></a>Globale Optionen

Standardmäßig gibt das Befehlszeilentool das Ergebnis in einem lesbaren Format aus. Darüber hinaus unterstützt das Tool auch die Ausgabe des Ergebnisses als JSON, was für Automatisierungsszenarien nützlich ist. Um die Ausgabe in JSON zu ändern, übergeben Sie `--output json` einen der folgenden Befehle.

### <a name="supported-commands"></a>Unterstützte Befehle

In der folgenden Tabelle sind Befehle für einige der gängigsten Szenarien aufgeführt. Führen Sie die Ausführung `mdatp help` über das Terminal aus, um die vollständige Liste der unterstützten Befehle anzuzeigen.

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
|Konfiguration         |Alle Antivirenausschlüsse auflisten                           |`mdatp exclusion list`                                                 |
|Konfiguration         |Hinzufügen eines Bedrohungsnamens zur Liste zugelassener Bedrohungen                   |`mdatp threat allowed add --name [threat-name]`                        |
|Konfiguration         |Entfernen eines Bedrohungsnamens aus der Liste der zulässigen Bedrohungen              |`mdatp threat allowed remove --name [threat-name]`                     |
|Konfiguration         |Auflisten aller zulässigen Bedrohungsnamen                           |`mdatp threat allowed list`                                            |
|Konfiguration         |Aktivieren des PUA-Schutzes                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|Konfiguration         |Deaktivieren des PUA-Schutzes                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|Konfiguration         |Aktivieren des Überwachungsmodus für PUA-Schutz                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|Diagnose           |Ändern der Protokollebene                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|Diagnose           |Generieren von Diagnoseprotokollen                                |`mdatp diagnostic create --path [directory]`                           |
|Gesundheitswesen                |Überprüfen der Integrität des Produkts                              |`mdatp health`                                                         |
|Schutz            |Scannen eines Pfads                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|Schutz            |Durchführen eines Schnellscans                                         |`mdatp scan quick`                                                     |
|Schutz            |Durchführen einer vollständigen Überprüfung                                          |`mdatp scan full`                                                      |
|Schutz            |Abbrechen einer laufenden Überprüfung nach Bedarf                        |`mdatp scan cancel`                                                    |
|Schutz            |Anfordern eines Security Intelligence-Updates                  |`mdatp definitions update`                                             |
|Schutzverlauf    |Drucken des vollständigen Schutzverlaufs                       |`mdatp threat list`                                                    |
|Schutzverlauf    |Abrufen von Bedrohungsdetails                                      |`mdatp threat get --id [threat-id]`                                    |
|Quarantäneverwaltung |Auflisten aller isolierten Dateien                              |`mdatp threat quarantine list`                                         |
|Quarantäneverwaltung |Entfernen aller Dateien aus der Quarantäne                    |`mdatp threat quarantine remove-all`                                   |
|Quarantäneverwaltung |Hinzufügen einer Datei, die als Bedrohung für die Quarantäne erkannt wurde       |`mdatp threat quarantine add --id [threat-id]`                         |
|Quarantäneverwaltung |Entfernen einer Datei, die als Bedrohung erkannt wurde, aus der Quarantäne  |`mdatp threat quarantine remove --id [threat-id]`                      |
|Quarantäneverwaltung |Wiederherstellen einer Datei aus der Quarantäne                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|Endpunkterkennung und -antwort |Festlegen der frühen Vorschau (nicht verwendet)                    |`mdatp edr early-preview [enable|disable]`                             |
|Endpunkterkennung und -antwort |Festlegen der Gruppen-ID                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|Endpunkterkennung und -antwort |Tag festlegen/entfernen, nur `GROUP` unterstützt        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|Endpunkterkennung und -antwort |Ausschlüsse auflisten (Stammverzeichnis)                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Informationen zum Microsoft Defender für Endpunkt-Portal

Im Defender für Endpunkt-Portal werden zwei Kategorien von Informationen angezeigt:

- Antivirusbenachrichtigungen, einschließlich:
  - Severity
  - Scantyp
  - Geräteinformationen (Hostname, Geräte-ID, Mandanten-ID, App-Version und Betriebssystemtyp)
  - Dateiinformationen (Name, Pfad, Größe und Hash)
  - Bedrohungsinformationen (Name, Typ und Status)
- Geräteinformationen, einschließlich:
  - Gerätebezeichner
  - Mandantenbezeichner
  - Version der App
  - Hostname
  - Betriebssystemtyp
  - Betriebssystemversion
  - Computermodell
  - Prozessorarchitektur
  - Gibt an, ob das Gerät ein virtueller Computer ist.

### <a name="known-issues"></a>Bekannte Probleme

- Möglicherweise wird auf der Computerinformationsseite des Microsoft Defender Security Center-Portals "Keine Sensordaten, beeinträchtigte Kommunikation" angezeigt, obwohl das Produkt erwartungsgemäß funktioniert. Wir arbeiten an der Behebung dieses Problems.
- Angemeldete Benutzer werden nicht im Microsoft Defender Security Center Portal angezeigt.
- Wenn bei SUSE-Verteilungen die Installation von *libatomic1* fehlschlägt, sollten Sie überprüfen, ob Ihr Betriebssystem registriert ist:

   ```bash
   sudo SUSEConnect --status-text
   ```
