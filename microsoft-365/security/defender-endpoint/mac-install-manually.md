---
title: Manuelle Bereitstellung für Microsoft Defender for Endpoint unter macOS
description: Installieren Sie Microsoft Defender for Endpoint auf macOS manuell über die Befehlszeile.
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
ms.openlocfilehash: 0e8faf95df6691828558175412a1de8aa844d93f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688597"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-on-macos"></a>Manuelle Bereitstellung für Microsoft Defender for Endpoint unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In diesem Thema wird beschrieben, wie Sie Microsoft Defender for Endpoint manuell auf macOS bereitstellen. Für eine erfolgreiche Bereitstellung sind alle folgenden Schritte erforderlich:
- [Herunterladen von Installations- und Onboardingpaketen](#download-installation-and-onboarding-packages)
- [Anwendungsinstallation (macOS 10.15 und ältere Versionen)](#application-installation-macos-1015-and-older-versions)
- [Anwendungsinstallation (macOS 11 und neuere Versionen)](#application-installation-macos-11-and-newer-versions)
- [Clientkonfiguration](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>Voraussetzungen und Systemanforderungen

Bevor Sie beginnen, finden Sie auf der [Hauptseite von Microsoft Defender for Endpoint auf macOS](microsoft-defender-endpoint-mac.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.

## <a name="download-installation-and-onboarding-packages"></a>Herunterladen von Installations- und Onboardingpaketen

Laden Sie die Installations- und Onboardingpakete von Microsoft Defender Security Center herunter:

1. Wechseln Sie im Microsoft Defender Security Center zu **Einstellungen > Geräteverwaltung > Onboarding**.
2. Legen Sie in Abschnitt 1 der Seite das Betriebssystem auf **macOS** und die Deployment-Methode auf **Lokales Skript .**
3. Wählen Sie in Abschnitt 2 der Seite **Installationspaket herunterladen aus.** Speichern Sie es als wdav.pkg in einem lokalen Verzeichnis.
4. Wählen Sie in Abschnitt 2 der Seite Die Option **Onboardingpaket herunterladen aus.** Speichern Sie es WindowsDefenderATPOnboardingPackage.zip im gleichen Verzeichnis.

    ![Screenshot des Microsoft Defender Security Center](images/atp-portal-onboarding-page.png)

5. Überprüfen Sie an einer Eingabeaufforderung, ob Sie über die beiden Dateien verfügen.
    
## <a name="application-installation-macos-1015-and-older-versions"></a>Anwendungsinstallation (macOS 10.15 und ältere Versionen)

Zum Abschließen dieses Vorgangs müssen Sie über Administratorrechte auf dem Gerät verfügen.

1. Navigieren Sie zum heruntergeladenen wdav.pkg in Finder, und öffnen Sie es.

    ![Screenshot der App-Installation1](images/mdatp-28-appinstall.png)

2. Wählen **Sie Weiter** aus, stimmen Sie den Lizenzbedingungen zu, und geben Sie das Kennwort ein, wenn Sie dazu aufgefordert werden.

    ![Screenshot der App-Installation2](images/mdatp-29-appinstalllogin.png)

   > [!IMPORTANT]
   > Sie werden aufgefordert, die Installation eines Treibers von Microsoft zu erlauben (entweder "Systemerweiterung blockiert" oder "Installation ist gesperrt" oder beides. Der Treiber muss installiert werden dürfen.

   ![Screenshot der App-Installation3](images/mdatp-30-systemextension.png)

3. Wählen **Sie Open Security Preferences** oder Open System **Preferences > Security & Privacy aus.** Wählen Sie **Zulassen** aus:

    ![Screenshot des Sicherheits- und Datenschutzfensters](images/mdatp-31-securityprivacysettings.png)

   Die Installation wird fortgesetzt.

   > [!CAUTION]
   > Wenn Sie nicht zulassen **auswählen,** wird die Installation nach 5 Minuten fortgesetzt. Microsoft Defender for Endpoint wird geladen, aber einige Features, z. B. der Echtzeitschutz, werden deaktiviert. Informationen [zur Lösung dieses Problems finden](mac-support-kext.md) Sie unter Problembehandlung bei Kernelerweiterungen.

> [!NOTE]
> MacOS kann bei der ersten Installation von Microsoft Defender for Endpoint den Neustart des Geräts anfordern. Echtzeitschutz ist erst verfügbar, wenn das Gerät neu gestartet wurde.

## <a name="application-installation-macos-11-and-newer-versions"></a>Anwendungsinstallation (macOS 11 und neuere Versionen)

Zum Abschließen dieses Vorgangs müssen Sie über Administratorrechte auf dem Gerät verfügen.

1. Navigieren Sie zum heruntergeladenen wdav.pkg in Finder, und öffnen Sie es.

    ![Screenshot der App-Installation4](images/big-sur-install-1.png)

2. Wählen **Sie Weiter** aus, stimmen Sie den Lizenzbedingungen zu, und geben Sie das Kennwort ein, wenn Sie dazu aufgefordert werden.

3. Am Ende des Installationsprozesses werden Sie heraufgestuft, um die vom Produkt verwendeten Systemerweiterungen zu genehmigen. Wählen **Sie Sicherheitseinstellungen öffnen aus.**

    ![Systemerweiterungsgenehmigung](images/big-sur-install-2.png)

4. Wählen Sie **im Fenster & Datenschutz** die Option Zulassen **aus.**

    ![Sicherheitseinstellungen für Systemerweiterungen1](images/big-sur-install-3.png)

5. Wiederholen Sie die Schritte 3 & 4 für alle Systemerweiterungen, die mit Microsoft Defender for Endpoint auf Dem Mac verteilt sind.

6. Im Rahmen der Funktionen für die Endpunkterkennung und -reaktion prüft Microsoft Defender for Endpoint auf Mac den Socketdatenverkehr und meldet diese Informationen an das Microsoft Defender Security Center-Portal. Wenn Sie aufgefordert werden, Microsoft Defender for Endpoint Berechtigungen zum Filtern von Netzwerkdatenverkehr zu erteilen, wählen Sie **Zulassen aus.**

    ![Sicherheitseinstellungen für Systemerweiterungen2](images/big-sur-install-4.png)

7. Öffnen **Sie Systemeinstellungen** Sicherheit & Datenschutz, und navigieren Sie zur Registerkarte Datenschutz. Erteilen Sie Microsoft Defender ATP und Microsoft Defender ATP Endpoint Security Extension die Berechtigung "Vollständiger  >   **Datenträgerzugriff".**   

    ![Vollständiger Datenträgerzugriff](images/big-sur-install-5.png)

## <a name="client-configuration"></a>Clientkonfiguration

1. Kopieren Sie wdav.pkg und MicrosoftDefenderATPOnboardingMacOs.py auf das Gerät, auf dem Sie Microsoft Defender for Endpoint unter macOS bereitstellen.

    Das Clientgerät ist nicht mit org_id. Beachten Sie, *dass org_id-Attribut* leer ist.

    ```bash
    mdatp health --field org_id
    ```

2. Führen Sie das Python-Skript aus, um die Konfigurationsdatei zu installieren:

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. Stellen Sie sicher, dass das Gerät jetzt Ihrer Organisation zugeordnet ist, und melden Sie eine gültige Organisations-ID:

    ```bash
    mdatp health --field org_id
    ```

    Nach der Installation wird das Microsoft Defender-Symbol in der macOS-Statusleiste in der oberen rechten Ecke angezeigt.
    
    > [!div class="mx-imgBorder"]
    > ![Microsoft Defender-Symbol im Screenshot der Statusleiste](images/mdatp-icon-bar.png)


## <a name="how-to-allow-full-disk-access"></a>Zulassen des vollständigen Festplattenzugriffs

> [!CAUTION]
> macOS 10.15 (Catalina) enthält neue Sicherheits- und Datenschutzverbesserungen. Ab dieser Version können Anwendungen standardmäßig ohne ausdrückliche Zustimmung nicht auf bestimmte Speicherorte auf dem Datenträger zugreifen (z. B. Dokumente, Downloads, Desktop usw.). In Ermangelung dieser Zustimmung kann Microsoft Defender for Endpoint Ihr Gerät nicht vollständig schützen.

1. Um die Zustimmung zu erteilen, öffnen Sie **system preferences**  >  **Security & Privacy**  >  **Privacy** Full  >  **Disk Access**. Klicken Sie auf das Sperrsymbol, um Änderungen vorzunehmen (unten im Dialogfeld). Wählen Sie Microsoft Defender for Endpoint aus.

2. Führen Sie einen AV-Erkennungstest aus, um zu überprüfen, ob das Gerät ordnungsgemäß onboardiert ist, und melden Sie den Dienst. Führen Sie die folgenden Schritte auf dem neu integrierten Gerät aus:

    1. Stellen Sie sicher, dass der Echtzeitschutz aktiviert ist (wird durch ein Ergebnis von 1 davon bezeichnet, dass der folgende Befehl ausgeführt wird):

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. Öffnen Sie ein Terminalfenster. Kopieren Sie den folgenden Befehl, und führen Sie diesen aus:

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. Die Datei sollte von Defender for Endpoint für Mac isoliert worden sein. Verwenden Sie den folgenden Befehl, um alle erkannten Bedrohungen auflisten:

        ```bash
        mdatp threat list
        ```

3. Führen Sie einen EDR-Erkennungstest aus, um zu überprüfen, ob das Gerät ordnungsgemäß onboardiert ist, und melden Sie den Dienst. Führen Sie die folgenden Schritte auf dem neu integrierten Gerät aus:

   1. In Ihrem Browser wie Microsoft Edge für Mac oder Safari.

   1. Laden Sie MDATP MacOS DIY.zip aus und https://aka.ms/mdatpmacosdiy extrahieren Sie es.

      Möglicherweise werden Sie dazu aufgefordert:

      > Möchten Sie Downloads auf "mdatpclientanalyzer.blob.core.windows.net" zulassen?<br/>
      > Sie können ändern, welche Websites Dateien in den Einstellungen für Websites herunterladen können.

4. Klicken Sie **auf Zulassen**.

5. Öffnen **Sie Downloads**.

6. Sie sollten **MDATP MacOS DIY sehen.**

   > [!TIP]
   > Wenn Sie doppelklicken, erhalten Sie die folgende Meldung:
   > 
   > > **"MDATP MacOS DIY" kann nicht geöffnet werden, da der Entwickler nicht überprüft werden kann.**<br/>
   > > MacOS kann nicht überprüfen, ob diese App frei von Schadsoftware ist.<br/>
   > > **\[ Move to \] Trash** **\[ Cancel \]** 
  
7. Klicken Sie auf **Abbrechen**.

8. Klicken Sie mit der rechten **Maustaste auf MDATP MacOS DIY,** und klicken Sie dann auf **Öffnen**. 

    Das System sollte die folgende Meldung anzeigen:

    > **macOS kann den Entwickler von **MDATP MacOS DIY nicht überprüfen.** Möchten Sie es wirklich öffnen?**<br/>
    > Durch das Öffnen dieser App überschreiben Sie die Systemsicherheit, die Ihren Computer und persönliche Informationen Schadsoftware zur Verfügung stellt, die Ihren Mac beeinträchtigt oder Ihre Privatsphäre gefährdet.

10. Klicken Sie auf **Öffnen**.

    Das System sollte die folgende Meldung anzeigen:

    > Microsoft Defender ATP – MacOS EDR-HEIMWERKER-Testdatei<br/>
    > Entsprechende Warnungen sind im MDATP-Portal verfügbar.

11. Klicken Sie auf **Öffnen**.

    In ein paar Minuten sollte eine Warnung namens "macOS EDR Test Alert" ausgelöst werden.

12. Wechseln Sie zu Microsoft Defender Security Center ( https://SecurityCenter.microsoft.com) .

13. Wechseln Sie zur Warnwarteschlange.

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="Beispiel für eine macOS-EDR-Testwarnung, die den Schweregrad, die Kategorie, die Erkennungsquelle und ein reduziertes Menü mit Aktionen zeigt.":::
    
    Sehen Sie sich die Warnungsdetails und die Gerätezeitachse an, und führen Sie die regulären Untersuchungsschritte aus.

## <a name="logging-installation-issues"></a>Probleme bei der Protokollierung der Installation

Weitere [Informationen zum](mac-resources.md#logging-installation-issues) Suchen des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter Protokollierungsinstallationsprobleme.

## <a name="uninstallation"></a>Deinstallation

Weitere Informationen zum Entfernen von Microsoft Defender for Endpoint für macOS von Clientgeräten finden Sie unter [Uninstalling.](mac-resources.md#uninstalling)
