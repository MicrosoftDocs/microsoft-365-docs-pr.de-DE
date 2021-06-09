---
title: Ressourcen für Microsoft Defender für Endpunkt auf mac
description: Ressourcen für Microsoft Defender für Endpunkt auf dem Mac, einschließlich der Deinstallation, der Erfassung von Diagnoseprotokollen, CLI-Befehlen und bekannten Problemen mit dem Produkt.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Mac, Installation, bereitstellen, Deinstallation, Intune, jamf, macos, aus, mojave, high sierra
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
ms.openlocfilehash: fa5d5b4470644e1ff50af46a8dd3f035cd9b3184
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842866"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>Ressourcen für Microsoft Defender für Endpunkt unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>Sammeln von Diagnoseinformationen

Wenn Sie ein Problem reproduzieren können, erhöhen Sie die Protokollierungsstufe, führen Sie das System für einige Zeit aus, und stellen Sie die Protokollierungsstufe auf die Standardeinstellung wieder her.

1. Erhöhen Sie die Protokollierungsstufe:

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. Reproduzieren des Problems

3. Führen Sie die Ausführung `sudo mdatp diagnostic create` aus, um die Microsoft Defender für Endpunkt-Protokolle zu sichern. Die Dateien werden in einem .zip Archiv gespeichert. Dieser Befehl gibt auch den Dateipfad zur Sicherung aus, nachdem der Vorgang erfolgreich war.

   > [!TIP]
   > Diagnoseprotokolle werden standardmäßig in `/Library/Application Support/Microsoft/Defender/wdavdiag/` gespeichert. Um das Verzeichnis zu ändern, in dem Diagnoseprotokolle gespeichert werden, übergeben Sie den befehl unten, und ersetzen Sie es `--path [directory]` durch das gewünschte `[directory]` Verzeichnis.

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

## <a name="logging-installation-issues"></a>Protokollieren von Installationsproblemen

Wenn während der Installation ein Fehler auftritt, meldet das Installationsprogramm nur einen allgemeinen Fehler.

Das detaillierte Protokoll wird in `/Library/Logs/Microsoft/mdatp/install.log` gespeichert. Wenn während der Installation Probleme auftreten, senden Sie uns diese Datei, damit wir Ihnen bei der Diagnose der Ursache helfen können.

## <a name="uninstalling"></a>Deinstallieren

Es gibt mehrere Möglichkeiten, Microsoft Defender für Endpunkt unter macOS zu deinstallieren. Beachten Sie, dass die zentral verwaltete Deinstallation in JAMF zwar verfügbar ist, aber noch nicht für Microsoft Intune verfügbar ist.

### <a name="interactive-uninstallation"></a>Interaktive Deinstallation

- Öffnen **Sie finder > Applications**. Klicken Sie mit der rechten Maustaste auf **Microsoft Defender für Endpunkt > In Papierkorb verschieben.**

### <a name="from-the-command-line"></a>Über die Befehlszeile

- ```sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'```

## <a name="configuring-from-the-command-line"></a>Konfigurieren über die Befehlszeile

Wichtige Aufgaben, z. B. das Steuern von Produkteinstellungen und das Auslösen von Scans bei Bedarf, können über die Befehlszeile ausgeführt werden:

|Gruppe        |Szenario                                   |Befehl                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|Konfiguration|Aktivieren/Deaktivieren des Echtzeitschutzes           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|Konfiguration|Aktivieren/Deaktivieren des Cloudschutzes               |`mdatp config cloud --value [enabled/disabled]`                                   |
|Konfiguration|Aktivieren/Deaktivieren der Produktdiagnose            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|Konfiguration|Aktivieren/Deaktivieren der automatischen Beispielübermittlung    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|Konfiguration|Hinzufügen eines Bedrohungsnamens zur Liste zugelassener Bedrohungen      |`mdatp threat allowed add --name [threat-name]`                                   |
|Konfiguration|Entfernen eines Bedrohungsnamens aus der Liste der zulässigen Bedrohungen |`mdatp threat allowed remove --name [threat-name]`                                |
|Konfiguration|Auflisten aller zulässigen Bedrohungsnamen              |`mdatp threat allowed list`                                                       |
|Konfiguration|Aktivieren des PUA-Schutzes                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|Konfiguration|Deaktivieren des PUA-Schutzes                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|Konfiguration|Aktivieren des Überwachungsmodus für PUA-Schutz      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|Konfiguration|PassiveMode aktivieren/deaktivieren                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|Diagnose  |Ändern der Protokollebene                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|Diagnose  |Generieren von Diagnoseprotokollen                   |`mdatp diagnostic create --path [directory]`                                      |
|Gesundheitswesen       |Überprüfen der Integrität des Produkts                 |`mdatp health`                                                                    |
|Gesundheitswesen       |Überprüfen auf ein spefic-Produktattribut       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|Schutz   |Scannen eines Pfads                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|Schutz   |Durchführen eines Schnellscans                            |`mdatp scan quick`                                                                |
|Schutz   |Durchführen einer vollständigen Überprüfung                             |`mdatp scan full`                                                                 |
|Schutz   |Abbrechen einer laufenden Überprüfung nach Bedarf           |`mdatp scan cancel`                                                               |
|Schutz   |Anfordern eines Security Intelligence-Updates     |`mdatp definitions update`                                                        |
|EDR          |Fügen Sie dem Gerät ein Gruppentag hinzu. EDR Tags werden für die Verwaltung von Gerätegruppen verwendet. Weitere Informationen finden Sie unter /microsoft-365/security/defender-endpoint/machine-groups |`mdatp edr tag set --name GROUP --value [name]` |
|EDR          |Gruppentag vom Gerät entfernen               |`mdatp edr tag remove --tag-name [name]`                                          |
|EDR          |Hinzufügen der Gruppen-ID                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a>So aktivieren Sie die automatische Kompletion

Um die automatische Kompletion in Bash zu aktivieren, führen Sie den folgenden Befehl aus, und starten Sie die Terminalsitzung neu:

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

So aktivieren Sie die automatische Kompletion in zsh:

- Überprüfen Sie, ob die automatische Kompletion auf Ihrem Gerät aktiviert ist:

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- Wenn der vorherige Befehl keine Ausgabe erzeugt, können Sie die automatische Kompletion mit dem folgenden Befehl aktivieren:

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- Führen Sie die folgenden Befehle aus, um die automatische Kompletion für Microsoft Defender für Endpunkt unter macOS zu aktivieren und die Terminalsitzung neu zu starten:

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>Client-Quarantäneverzeichnis für Microsoft Defender für Endpunkt

`/Library/Application Support/Microsoft/Defender/quarantine/`enthält die Dateien, die in Quarantäne gestellt werden. `mdatp` Die Dateien werden nach der Bedrohungsverfolgungs-ID benannt. Die aktuellen TrackingIds werden mit `mdatp threat list` angezeigt.

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Informationen zum Microsoft Defender für Endpunkt-Portal

[EDR Funktionen für macOS sind nun im](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)Microsoft Defender für Endpunkt-Blog angekommen und bieten detaillierte Anleitungen dazu, was Sie in Microsoft Defender für Endpoint Security Center erwarten können.
