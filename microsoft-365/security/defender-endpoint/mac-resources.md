---
title: Ressourcen für Microsoft Defender ATP für Mac
description: Ressourcen für Microsoft Defender ATP für Mac, einschließlich der Deinstallation, der Erfassung von Diagnoseprotokollen, CLI-Befehlen und bekannten Problemen mit dem Produkt.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 37d31fe93a849871e7da92fff521b6a75beac531
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187637"
---
# <a name="resources-for-microsoft-defender-for-endpoint-for-mac"></a>Ressourcen für Microsoft Defender for Endpoint für Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>Sammeln von Diagnoseinformationen

Wenn Sie ein Problem reproduzieren können, erhöhen Sie die Protokollierungsstufe, führen Sie das System für einige Zeit aus, und stellen Sie den Protokollierungsgrad auf den Standardwert wieder dar.

1. Erhöhen des Protokollierungsgrads:

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. Reproduzieren des Problems

3. Führen `sudo mdatp diagnostic create` Sie aus, um die Microsoft Defender for Endpoint-Protokolle zu sichern. Die Dateien werden in einem ZIP-Archiv gespeichert. Mit diesem Befehl wird auch der Dateipfad zur Sicherung gedruckt, nachdem der Vorgang erfolgreich war.

   > [!TIP]
   > Diagnoseprotokolle werden standardmäßig in `/Library/Application Support/Microsoft/Defender/wdavdiag/` gespeichert. Um das Verzeichnis zu ändern, in dem Diagnoseprotokolle gespeichert werden, übergeben Sie an den folgenden Befehl, und ersetzen Sie durch `--path [directory]` `[directory]` das gewünschte Verzeichnis.

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. Protokollierungsstufe wiederherstellen:

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>Probleme bei der Protokollierung der Installation

Wenn während der Installation ein Fehler auftritt, wird vom Installationsprogramm nur ein allgemeiner Fehler gemeldet.

Das detaillierte Protokoll wird in `/Library/Logs/Microsoft/mdatp/install.log` gespeichert. Wenn während der Installation Probleme auftreten, senden Sie uns diese Datei, damit wir die Ursache diagnostizieren können.

## <a name="uninstalling"></a>Deinstallieren

Es gibt verschiedene Möglichkeiten, Microsoft Defender for Endpoint für Mac zu deinstallieren. Beachten Sie, dass die zentral verwaltete Deinstallation zwar auf JAMF verfügbar ist, aber noch nicht für Microsoft Intune verfügbar ist.

### <a name="interactive-uninstallation"></a>Interaktive Deinstallation

- Öffnen **Sie finder > Applications**. Klicken Sie mit der rechten Maustaste **auf Microsoft Defender ATP > In Papierkorb verschieben.**

### <a name="from-the-command-line"></a>Über die Befehlszeile

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a>Konfigurieren über die Befehlszeile

Wichtige Aufgaben, z. B. das Steuern von Produkteinstellungen und das Auslösen von Bedarfsscans, können über die Befehlszeile ausgeführt werden:

|Gruppe        |Szenario                                   |Befehl                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|Konfiguration|Aktivieren/Deaktivieren des Echtzeitschutzes           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|Konfiguration|Aktivieren/Deaktivieren des Cloudschutzes               |`mdatp config cloud --value [enabled/disabled]`                                   |
|Konfiguration|Aktivieren/Deaktivieren der Produktdiagnose            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|Konfiguration|Aktivieren/Deaktivieren der automatischen Beispielübermittlung    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|Konfiguration|Hinzufügen eines Bedrohungsnamens zur liste der zulässigen Bedrohungen      |`mdatp threat allowed add --name [threat-name]`                                   |
|Konfiguration|Entfernen eines Bedrohungsnamens aus der liste der zulässigen Bedrohungen |`mdatp threat allowed remove --name [threat-name]`                                |
|Konfiguration|Auflisten aller zulässigen Bedrohungsnamen              |`mdatp threat allowed list`                                                       |
|Konfiguration|Aktivieren des PUA-Schutzes                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|Konfiguration|Deaktivieren des PUA-Schutzes                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|Konfiguration|Aktivieren des Überwachungsmodus für den PUA-Schutz      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|Konfiguration|Ein-/Ausschalten von passivem Modus                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|Diagnose  |Ändern der Protokollebene                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|Diagnose  |Generieren von Diagnoseprotokollen                   |`mdatp diagnostic create --path [directory]`                                      |
|Gesundheitswesen       |Überprüfen des Produktzustands                 |`mdatp health`                                                                    |
|Gesundheitswesen       |Suchen nach einem spefic-Produktattribut       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|Schutz   |Überprüfen eines Pfads                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|Schutz   |Schnellscan durchführen                            |`mdatp scan quick`                                                                |
|Schutz   |Durchführen einer vollständigen Überprüfung                             |`mdatp scan full`                                                                 |
|Schutz   |Abbrechen einer laufenden Überprüfung bei Bedarf           |`mdatp scan cancel`                                                               |
|Schutz   |Anfordern eines Security Intelligence-Updates     |`mdatp definitions update`                                                        |
|EDR          |Fügen Sie dem Gerät ein Gruppentag hinzu. EDR-Tags werden zum Verwalten von Gerätegruppen verwendet. Weitere Informationen finden Sie unter https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups |`mdatp edr tag set --name GROUP --value [name]` |
|EDR          |Entfernen des Gruppentags vom Gerät               |`mdatp edr tag remove --tag-name [name]`                                          |
|EDR          |Hinzufügen von Gruppen-ID                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a>Aktivieren der automatischen Vervollständigung

Führen Sie zum Aktivieren der autocompletion in bash den folgenden Befehl aus, und starten Sie die Terminalsitzung neu:

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

So aktivieren Sie die automatische Vervollständigung in zsh:

- Überprüfen Sie, ob die automatische Vervollständigung auf Ihrem Gerät aktiviert ist:

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- Wenn der vorangehende Befehl keine Ausgabe erzeugt, können Sie die automatische Vervollständigung mithilfe des folgenden Befehls aktivieren:

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- Führen Sie die folgenden Befehle aus, um die automatische Kompletion für Microsoft Defender for Endpoint für Mac zu aktivieren und die Terminalsitzung neu zu starten:

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>Microsoft Defender for Endpoint-Quarantäneverzeichnis des Clients

`/Library/Application Support/Microsoft/Defender/quarantine/` enthält die Dateien, die von isoliert `mdatp` werden. Die Dateien sind nach der Threat TrackingId benannt. Die aktuellen trackingIds wird mit `mdatp threat list` angezeigt.

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Informationen zum Microsoft Defender for Endpoint-Portal

[Die EDR-Funktionen](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)für macOS sind nun im Microsoft Defender for Endpoint-Blog eingetroffen und bieten detaillierte Anleitungen dazu, was Sie in Microsoft Defender for Endpoint Security Center erwarten können.
