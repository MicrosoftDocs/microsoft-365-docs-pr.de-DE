---
title: Manuelle Bereitstellung von Microsoft Defender für Endpunkt auf macOS
description: Installieren Sie Microsoft Defender für Endpunkt auf macOS manuell über die Befehlszeile.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, mac, Installation, bereitstellen, Deinstallation, Intune, Jamf, macOS, Catalina, Mojave, High Sierra
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
ms.openlocfilehash: d8458f1bacc6577d83878a94c24e649371d90038
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935329"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-on-macos"></a>Manuelle Bereitstellung von Microsoft Defender für Endpunkt auf macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Dieses Thema beschreibt, wie Sie Microsoft Defender für Endpunkt auf macOS manuell bereitstellen. Für eine erfolgreiche Bereitstellung müssen alle folgenden Schritte abgeschlossen sein:
- [Herunterladen der Installations- und Onboarding-Pakete](#download-installation-and-onboarding-packages)
- [Anwendungsinstallation (macOS 10.15 und ältere Versionen)](#application-installation-macos-1015-and-older-versions)
- [Anwendungsinstallation (macOS 11 und neuere Versionen)](#application-installation-macos-11-and-newer-versions)
- [Clientkonfiguration](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>Voraussetzungen und Systemanforderungen

Beachten Sie vor dem Start [die Hauptseite „Microsoft Defender für Endpunkt auf macOS“](microsoft-defender-endpoint-mac.md) für eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.

## <a name="download-installation-and-onboarding-packages"></a>Herunterladen der Installations- und Onboarding-Pakete

Laden Sie die Installations- und Onboarding-Pakete vom Microsoft Defender Security Center herunter:

1. Gehen Sie im Microsoft Defender Security Center zu **Einstellungen > Geräteverwaltung > Onboarding**.
2. Legen Sie das Betriebssystem im Abschnitt 1 der Seite auf **macOS** fest, und die Bereitstellungsmethode auf **Lokales Skript**.
3. Wählen Sie im Abschnitt 2 der Seite die Option **Installationspaket herunterladen**. Speichern Sie es in einem lokalen Verzeichnis unter „wdav.pkg“.
4. Wählen Sie im Abschnitt 2 der Seite die Option **Onboarding-Paket herunterladen**. Speichern Sie es im gleichen Verzeichnis als „WindowsDefenderATPOnboardingPackage.zip“.

    ![Screenshot des Microsoft Defender Security Center](images/atp-portal-onboarding-page.png)

5. Bestätigen Sie in einer Eingabeaufforderung, dass Sie die zwei Dateien besitzen.
    
## <a name="application-installation-macos-1015-and-older-versions"></a>Anwendungsinstallation (macOS 10.15 und ältere Versionen)

Um den Prozess abzuschließen, benötigen Sie Administratorberechtigungen auf dem Gerät.

1. Navigieren Sie in „Finder“ zur heruntergeladenen Datei „wdav.pkg“ und öffnen Sie diese.

    ![App-Installation – Screenshot 1](images/mdatp-28-appinstall.png)

2. Wählen Sie **Fortfahren** aus, stimmen Sie den Lizenzbedingungen zu, und geben Sie das Kennwort ein, wenn Sie aufgefordert werden.

    ![App-Installation – Screenshot 2](images/mdatp-29-appinstalllogin.png)

   > [!IMPORTANT]
   > Sie werden aufgefordert, der Installation eines Treibers von Microsoft zuzustimmen (entweder „Systemerweiterung blockiert“ oder „Installation ist am Warten“ oder beides. Die Installation des Treibers muss erlaubt werden.

   ![App-Installation – Screenshot 3](images/mdatp-30-systemextension.png)

3. Wählen Sie **Sicherheitseinstellungen öffnen** oder **Sicherheitseinstellungen öffnen > Sicherheit & Datenschutz** aus. Wählen Sie **Zulassen** aus:

    ![Screenshot des Sicherheits- und Datenschutzfensters](images/mdatp-31-securityprivacysettings.png)

   Der Installationsvorgang wird fortgesetzt.

   > [!CAUTION]
   > Wenn Sie **Zulassen** nicht auswählen, wird die Installation nach 5 Minuten fortgesetzt. Microsoft Defender für Endpunkt wird geladen, aber einige Features, beispielsweise der Echtzeitschutz, werden deaktiviert sein. Weitere Informationen zur Behebung dieses Problems finden Sie unter [Problembehandlung von Kernel-Erweiterungsproblemen](mac-support-kext.md).

> [!NOTE]
> MacOS kann bei der ersten Installation von Microsoft Defender für Endpunkt einen Neustart des Geräts anfordern. Der Echtzeitschutz wird nicht verfügbar sein, bis das Gerät neu gestartet wurde.

## <a name="application-installation-macos-11-and-newer-versions"></a>Anwendungsinstallation (macOS 11 und neuere Versionen)

Um den Prozess abzuschließen, benötigen Sie Administratorberechtigungen auf dem Gerät.

1. Navigieren Sie in „Finder“ zur heruntergeladenen Datei „wdav.pkg“ und öffnen Sie diese.

    ![App-Installation – Screenshot 4](images/big-sur-install-1.png)

2. Wählen Sie **Fortfahren** aus, stimmen Sie den Lizenzbedingungen zu, und geben Sie das Kennwort ein, wenn Sie aufgefordert werden.

3. Am Ende des Installationsvorgangs werden Sie aufgefordert, die vom Produkt verwendeten Systemerweiterungen zu genehmigen. Wählen Sie **Sicherheitseinstellungen öffnen** aus.

    ![Genehmigung der Systemerweiterung](images/big-sur-install-2.png)

4. Wählen Sie im Fenster **Sicherheit & Datenschutz** die Option **Zulassen** aus.

    ![Systemerweiterung – Sicherheitseinstellungen 1](images/big-sur-install-3.png)

5. Wiederholen Sie die Schritte 3 & 4 für alle Systemerweiterungen, die mit Microsoft Defender für Endpunkt auf Mac geliefert wurden.

6. Als Teil der Funktionen zur Endpunkterkennung und -reaktion untersucht Microsoft Defender für Endpunkt auf Mac den Socket-Datenverkehr und meldet diese Informationen an das Microsoft Defender Security Center-Portal. Wenn Sie aufgefordert werden, Microsoft Defender für Endpunkt die Berechtigungen für das Filtern des Netzwerkdatenverkehrs zu gewähren, wählen Sie **Zulassen** aus.

    ![Systemerweiterung – Sicherheitseinstellungen 2](images/big-sur-install-4.png)

7. Öffnen Sie **Systemeinstellungen** > **Sicherheit & Datenschutz** und navigieren Sie zur Registerkarte **Datenschutz**. Gewähren Sie die Berechtigung **Vollständiger Disk-Zugriff** für **Microsoft Defender ATP** und **Microsoft Defender ATP Endpunkt-Sicherheitserweiterung**.

    ![Vollständiger Disk-Zugriff](images/big-sur-install-5.png)

## <a name="client-configuration"></a>Clientkonfiguration

1. Kopieren Sie die Dateien „wdav.pkg“ und „MicrosoftDefenderATPOnboardingMacOs.py“ auf das Gerät, auf dem Sie Microsoft Defender für Endpunkt auf macOS bereitstellen.

    Das Clientgerät ist nicht mit org_id verbunden. Beachten Sie, dass das *org_id*-Attribut nur Leerzeichen enthält.

    ```bash
    mdatp health --field org_id
    ```

2. Führen Sie das Python-Skript aus, um die Konfigurationsdatei zu installieren:

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. Bestätigen Sie, dass das Gerät jetzt mit Ihrer Organisation verbunden ist und eine gültige Organisations-ID meldet:

    ```bash
    mdatp health --field org_id
    ```

    Nach der Installation sehen Sie das Symbol von Microsoft Defender auf der Statusleiste von macOS in der oberen rechten Ecke.
    
    > [!div class="mx-imgBorder"]
    > ![Microsoft Defender-Symbol in der Statusleiste – Screenshot](images/mdatp-icon-bar.png)


## <a name="how-to-allow-full-disk-access"></a>So erlauben Sie den vollständigen Disk-Zugriff

> [!CAUTION]
> macOS 10.15 (Catalina) enthält neue Sicherheits- und Datenschutzerweiterungen. Ab dieser Version sind Anwendungen standardmäßig nicht in der Lage, ohne ausdrückliche Zustimmung auf bestimmte Speicherorte auf dem Disk zuzugreifen (wie Dokumente, Downloads, Desktop usw.). Wenn diese Zustimmung nicht vorhanden ist, kann Microsoft Defender für Endpunkt Ihr Gerät nicht vollständig schützen.

1. Um die Zustimmung zu gewähren, öffnen Sie **Systemeinstellungen** > **Sicherheit & Datenschutz** > **Datenschutz** > **Vollständiger Disk-Zugriff**. Klicken Sie auf das Schlosssymbol, um die Änderungen vorzunehmen (unten im Dialogfeld). Wählen Sie Microsoft Defender für Endpunkt aus.

2. Führen Sie einen AV-Erkennungstest durch, um zu überprüfen, ob das Gerät ordnungsgemäß eingebunden ist und dem Dienst Bericht erstattet. Führen Sie die folgenden Schritte auf dem neu eingebundenen Gerät durch:

    1. Stellen Sie sicher, dass der Echtzeitschutz aktiviert ist (gekennzeichnet durch ein Ergebnis von 1 beim Ausführen des folgenden Befehls):

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. Öffnen Sie ein Terminal-Fenster. Kopieren Sie den folgenden Befehl und führen Sie ihn aus:

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. Die Datei sollte von Defender für Endpunkt auf Mac in Quarantäne gestellt worden sein. Verwenden Sie den folgenden Befehl, um alle entdeckten Bedrohungen aufzulisten:

        ```bash
        mdatp threat list
        ```

3. Führen Sie einen EDR-Erkennungstest durch, um zu überprüfen, ob das Gerät ordnungsgemäß eingebunden ist und dem Dienst Bericht erstattet. Führen Sie die folgenden Schritte auf dem neu eingebundenen Gerät durch:

   1. In Ihrem Browser wie z. B. Microsoft Edge für Mac oder Safari.

   1. Laden Sie MDATP MacOS DIY.zip von https://aka.ms/mdatpmacosdiy herunter und extrahieren Sie die Daten.

      Möglicherweise werden Sie aufgefordert:

      > Wollen Sie Downloads auf „mdatpclientanalyzer.blob.core.windows.net“ zulassen?<br/>
      > Sie können unter „Websites-Einstellungen“ ändern, welche Websites Dateien herunterladen dürfen.

4. Klicken Sie auf **Zulassen**.

5. Öffnen Sie **Downloads**.

6. Sie sollten **MDATP MacOS DIY** sehen.

   > [!TIP]
   > Wenn Sie dies doppelklicken, erhalten Sie die folgende Nachricht:
   > 
   > > **„MDATP MacOS DIY“ kann nicht geöffnet werden, da der Entwickler nicht verifiziert werden kann.**<br/>
   > > MacOS kann nicht bestätigen, dass diese App frei von Schadsoftware ist.<br/>
   > > **\[In den Papierkorb verschieben\]** **\[Abbrechen\]** 
  
7. Klicken Sie auf **Abbrechen**.

8. Klicken Sie mit der rechten Maustaste auf **MDATP MacOS DIY**, und klicken Sie dann auf **Öffnen**. 

    Das System sollte die folgende Nachricht anzeigen:

    > **macOS kann den Entwickler von **MDATP MacOS DIY** nicht verifizieren. Sind Sie sicher, dass Sie die Datei öffnen wollen?**<br/>
    > Wenn Sie diese App öffnen, überschreiben Sie die Systemsicherheit, was dazu führen kann, dass Ihr Computer und Ihre persönlichen Daten Schadsoftware ausgesetzt sind, die Ihren Mac beschädigen oder Ihre Privatsphäre gefährden können.

10. Klicken Sie auf **Öffnen**.

    Das System sollte die folgende Nachricht anzeigen:

    > Microsoft Defender für Endpunkt – macOS EDR DIY-Testdatei<br/>
    > Die zugehörige Warnung wird im MDATP-Portal verfügbar sein.

11. Klicken Sie auf **Öffnen**.

    Nach einigen Minuten sollte eine Warnung mit Namen „macOS EDR-Testwarnung“ ausgelöst werden.

12. Wechseln Sie zum Microsoft Defender Security Center (https://SecurityCenter.microsoft.com).

13. Gehen Sie zur Warteschlange der Warnungen.

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="Beispiel für eine macOS EDR-Testwarnung, die Schweregrad, Kategorie, Erkennungsquelle und ein eingeklapptes Aktionsmenü anzeigt.":::
    
    Schauen Sie sich die Warnungsdetails und die Gerätezeitachse an, und führen Sie die normalen Untersuchungsschritte durch.

## <a name="logging-installation-issues"></a>Protokollierung von Installationsproblemen

Weitere Informationen zum Auffinden des automatisch generierten Protokolls, das vom Installationsprogramm beim Auftreten eines Fehlers erstellt wird, finden Sie unter [Protokollierung von Installationsproblemen](mac-resources.md#logging-installation-issues).

## <a name="uninstallation"></a>Deinstallation

Details zum Entfernen von Microsoft Defender für Endpunkt auf macOS von Clientgeräten finden Sie unter [Deinstallation](mac-resources.md#uninstalling).
