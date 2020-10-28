---
title: Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Stellen Sie das Konfigurationspaket auf dem VDI-Gerät (Virtual Desktop Infrastructure) so bereit, dass es auf dem Microsoft 365 Endpoint Data Loss Prevention-Dienst implementiert ist.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769416"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)

**Gilt für:**
- [Microsoft 365 Endpunkt-Datenverlust Verhinderung (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

- VDI-Geräte (Virtual Desktop Infrastructure)

>[!WARNING]
> Microsoft 365 Endpoint Data Loss Prevention-Unterstützung für Windows Virtual Desktop unterstützt Szenarien für einzelne Sitzungen. Szenarien mit mehreren Sitzungen auf dem virtuellen Windows-Desktop werden derzeit nicht unterstützt.

## <a name="onboard-vdi-devices"></a>Onboard-VDI-Geräte

Microsoft 365 Endpoint Data Loss Prevention unterstützt das Onboarding von nicht persistenten VDI-Sitzungen. 

>[!Note]
>Um nicht persistente VDI-Sitzungen an Bord zu können, müssen sich VDI-Geräte auf Windows 10 1809 oder höher befinden.

Beim Onboarding von VDIs kann es zu Problemen kommen. Im folgenden werden typische Herausforderungen für dieses Szenario dargestellt:

- Sofortiges frühes Onboarding einer kurzlebigen Sitzung, die vor der eigentlichen Einrichtung auf Microsoft 365-Endpunkt Verhinderung von Datenverlust onboarded sein muss.
- Der Gerätename wird normalerweise für neue Sitzungen wieder verwendet.

VDI-Geräte können im Microsoft 365 Compliance Center als Folgendes angezeigt werden:

- Einzelner Eintrag für jedes Gerät.  
Beachten Sie, dass in diesem Fall *derselbe* Gerätename beim Erstellen der Sitzung konfiguriert werden muss, beispielsweise mithilfe einer unbeaufsichtigten Antwortdatei.
- Mehrere Einträge für jedes Gerät – eins für jede Sitzung.

Die folgenden Schritte werden Sie durch das Onboarding von VDI-Geräten führen und die Schritte für einzelne und mehrere Einträge hervorheben.

>[!WARNING]
> Bei Umgebungen mit niedrigen Ressourcen Konfigurationen kann das VDI-Startverfahren das Onboarding von Microsoft 365-Endpunkt Datenverlust verlangsamen. 

1.  Öffnen Sie die ZIP-Datei des VDI-Konfigurationspakets ( *DeviceCompliancePackage.zip* ), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben.

2.  Wählen Sie im Navigationsbereich die Option **Einstellungen** für das  >  **Onboarding von Geräten** aus  >  **Onboarding** .

3. Wählen Sie im Feld **Bereitstellungsmethode** die Option **VDI-Onboarding-Skripts für nicht persistente Endpunkte** aus.

5. Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.

6. Kopieren Sie die Dateien aus dem DeviceCompliancePackage-Ordner, der aus der ZIP-Datei extrahiert wurde, in das `golden/master` Bild unter dem Pfad `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

7. Wenn Sie keinen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie DeviceComplianceOnboardingScript. cmd.

8. Wenn Sie einen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie sowohl Onboard-NonPersistentMachine.ps1 als auch DeviceComplianceOnboardingScript. cmd.
    
    > [!NOTE]
    > Wenn der Ordner nicht angezeigt wird `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` , ist er möglicherweise ausgeblendet. Sie müssen im Datei-Explorer die Option **Ausgeblendete Dateien und Ordner anzeigen** auswählen.

9. Öffnen Sie ein lokales Gruppenrichtlinien-Editor Fenster, und navigieren Sie zu **Computer Konfiguration**  >  **Windows-Einstellungs**  >  **Skripts**  >  **Startup** .

   > [!NOTE]
   > Domänengruppenrichtlinien können auch für das Onboarding nicht persistenter VDI-Geräte verwendet werden.

4. Je nach der Methode, die Sie implementieren möchten, führen Sie die entsprechenden Schritte aus:

   **Für einzelne Einträge für jedes Gerät**
   
   Wählen Sie die Registerkarte **PowerShell-Skripts** aus, und klicken Sie dann auf **Hinzufügen** (Windows Explorer wird direkt in dem Pfad geöffnet, in dem Sie das Onboarding-Skript zuvor kopiert haben). Navigieren Sie zum Onboarding PowerShell `Onboard-NonPersistentMachine.ps1` -Skript.
   
   **Für mehrere Einträge für jedes Gerät** :
   
   Wählen Sie die Registerkarte **Skripts** aus, und klicken Sie dann auf **Hinzufügen** (Windows Explorer wird direkt im Pfad geöffnet, in dem Sie das Onboarding-Skript zuvor kopiert haben). Navigieren Sie zum Onboarding bash `DeviceComplianceOnboardingScript.cmd` -Skript.

5. Testen Sie Ihre Lösung:

   1. Erstellen Sie einen Pool mit einem Gerät.
      
   1. Bei Gerät anmelden.
      
   1. Abmelden vom Gerät.

   1. Melden Sie sich mit einem anderen Benutzer an einem Gerät an.
      
   1. **Für einzelne Einträge für jedes Gerät** : Überprüfen Sie nur einen Eintrag im Microsoft Defender Security Center.<br>
      **Für mehrere Einträge für jedes Gerät** : Überprüfen Sie mehrere Einträge im Sicherheits Center von Microsoft Defender.

6. Klicken Sie im Navigationsbereich auf **Geräteliste** .

7. Verwenden Sie die Suchfunktion, indem Sie den Gerätenamen eingeben und als Suchtyp **Gerät** auswählen.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Aktualisieren von VDI-Images (Non-persistent Virtual Desktop Infrastructure)
Als bewährte Methode wird empfohlen, Offline-Wartungstools zu verwenden, um Golden/Master-Images zu patchen.<br>
Beispielsweise können Sie die folgenden Befehle verwenden, um ein Update zu installieren, während das Bild offline bleibt:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Weitere Informationen zu DISM-Befehlen und zur Offlinewartung finden Sie in den folgenden Artikeln:
- [Ändern eines Windows-Abbilds mithilfe von DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Command-Line Optionen für DISM-Bildverwaltung](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Verringern der Größe des Komponenten Speichers in einem Windows-Offline Abbild](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Wenn die Offlinewartung keine geeignete Option für Ihre nicht persistente VDI-Umgebung ist, müssen die folgenden Schritte ausgeführt werden, um die Konsistenz und die Integrität des Sensors sicherzustellen:

1. Nachdem Sie das Masterabbild für Onlinewartung oder Patching gestartet haben, führen Sie ein offboarding-Skript aus, um den Microsoft 365-Endpunkt für die Datenverlust-Verhinderung zu deaktivieren. Weitere Informationen finden Sie unter [extern-Geräte mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).

2. Stellen Sie sicher, dass der Sensor angehalten wird, indem Sie den folgenden Befehl in einem cmd-Fenster ausführen:

   ```console
   sc query sense
   ```

3. Dienst das Bild nach Bedarf.

4. Führen Sie die folgenden Befehle mit PsExec.exe aus https://download.sysinternals.com/files/PSTools.zip) , um die Inhalte des Cyber-Ordners, die der Sensor seit dem Start möglicherweise angesammelt hat, zu bereinigen:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Schließen Sie das Goldene/Master-Bild wie gewohnt erneut an.

## <a name="related-topics"></a>Verwandte Themen
- [Integrierte Windows 10-Geräte mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)
- [Onboard-Windows 10-Geräte mit Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte](dlp-configure-endpoints-mdm.md)
- [Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md)
- [Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
