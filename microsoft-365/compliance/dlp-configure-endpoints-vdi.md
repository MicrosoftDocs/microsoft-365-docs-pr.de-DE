---
title: Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)
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
description: Stellen Sie das Konfigurationspaket auf einem Virtuellen Desktopinfrastrukturgerät (Virtual Desktop Infrastructure, VDI) so sicher, dass es in den Microsoft 365 Endpoint Data Loss Prevention Service integrierte wird.
ms.openlocfilehash: 2a62de6c238c1f681bde8a9bf25ecd596a10d390
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917951"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)

**Gilt für:**
- [Microsoft 365 Verhinderung von Endpunktdatenverlusten (Endpoint Data Loss Prevention, DLP)](./endpoint-dlp-learn-about.md)

- Virtual Desktop Infrastructure (VDI)-Geräte

>[!WARNING]
> Microsoft 365 Unterstützung für die Verhinderung von Endpunktdatenverlusten für Windows Virtual Desktop unterstützt einzelne Sitzungsszenarien. Szenarien mit mehreren Sitzungen auf Windows Virtual Desktop werden derzeit nicht unterstützt.

## <a name="onboard-vdi-devices"></a>Onboarding von VDI-Geräten

Microsoft 365 Die Verhinderung von Endpunktdatenverlusten unterstützt das nicht persistente Onboarding von VDI-Sitzungen. 

>[!Note]
>Um nicht persistente VDI-Sitzungen zu integrieren, müssen sich VDI-Geräte auf Windows 10 1809 oder höher.

Beim Onboarding von VDIs kann es zu herausforderungen kommen. Es folgen typische Herausforderungen für dieses Szenario:

- Sofortiges frühzeitiges Onboarding einer kurzlebigen Sitzung, die vor der tatsächlichen Bereitstellung in Microsoft 365 Endpoint Data Loss Prevention onboarded werden muss.
- Der Gerätename wird in der Regel für neue Sitzungen wiederverwendet.

VDI-Geräte können im Microsoft 365 Compliance Center wie folgt angezeigt werden:

- Einzelner Eintrag für jedes Gerät.  
Beachten Sie, dass  in diesem Fall derselbe Gerätename beim Erstellen der Sitzung konfiguriert werden muss, z. B. mithilfe einer unbeaufsichtigten Antwortdatei.
- Mehrere Einträge für jedes Gerät – einer für jede Sitzung.

Die folgenden Schritte führen Sie durch das Onboarding von VDI-Geräten und zeigen Schritte für einzelne und mehrere Einträge an.

>[!WARNING]
> In Umgebungen mit geringen Ressourcenkonfigurationen kann die VDI-Startprozedur das Onboarding Microsoft 365 Endpoint Data Loss Prevention verlangsamen. 

1.  Öffnen Sie die VDI-Konfigurationspaketdatei .zip (*DeviceCompliancePackage.zip*), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben.

2.  Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding des** Geräts  >  **aus.**

3. Wählen Sie **im Feld Bereitstellungsmethode** die Option **VDI-Onboardingskripts für nicht persistente Endpunkte aus.**

5. Klicken **Sie auf Paket** herunterladen, und speichern .zip Datei.

6. Kopieren Sie die Dateien aus dem Ordner DeviceCompliancePackage aus der .zip in das Bild `golden/master` unter dem Pfad `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

7. Wenn Sie keinen einzigen Eintrag für jedes Gerät implementieren, kopieren Sie DeviceComplianceOnboardingScript.cmd.

8. Wenn Sie einen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie Onboard-NonPersistentMachine.ps1 deviceComplianceOnboardingScript.cmd.
    
    > [!NOTE]
    > Wenn der Ordner nicht angezeigt `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` wird, wird er möglicherweise ausgeblendet. Sie müssen die Option  Ausgeblendete Dateien und Ordner anzeigen im Datei-Explorer auswählen.

9. Öffnen Sie ein Fenster des Editors für lokale Gruppenrichtlinien, und navigieren Sie zu **Computerkonfiguration**  >  **Windows Einstellungen**  >    >  **Skriptstart**.

   > [!NOTE]
   > Domänengruppenrichtlinien können auch zum Onboarding nicht persistenter VDI-Geräte verwendet werden.

4. Führen Sie in Abhängigkeit von der Methode, die Sie implementieren möchten, die entsprechenden Schritte aus:

   **Für einzelnen Eintrag für jedes Gerät**
   
   Wählen Sie **die Registerkarte PowerShell-Skripts** aus, und klicken Sie dann auf Hinzufügen **(Windows** Der Explorer wird direkt im Pfad geöffnet, in den Sie das Onboardingskript zuvor kopiert haben). Navigieren Sie zum Onboarding des PowerShell-Skripts `Onboard-NonPersistentMachine.ps1` .
   
   **Für mehrere Einträge für jedes Gerät:**
   
   Wählen Sie **die Registerkarte Skripts** aus, und klicken Sie dann auf Hinzufügen **(Windows** Der Explorer wird direkt im Pfad geöffnet, in den Sie das Onboardingskript zuvor kopiert haben). Navigieren Sie zum Onboarding-Bash-Skript `DeviceComplianceOnboardingScript.cmd` .

5. Testen Sie Ihre Lösung:

   1. Erstellen Sie einen Pool mit einem Gerät.
      
   1. Bei Gerät anmeldet.
      
   1. Abmelden vom Gerät.

   1. Bei einem anderen Benutzer am Gerät anmeldet.
      
   1. **Für einzelnen Eintrag für jedes Gerät:** Überprüfen Sie nur einen Eintrag in Microsoft Defender Security Center.<br>
      **Für mehrere Einträge für jedes Gerät:** Überprüfen Sie mehrere Einträge in Microsoft Defender Security Center.

6. Klicken **Sie im** Navigationsbereich auf Geräteliste.

7. Verwenden Sie die Suchfunktion, indem Sie den Gerätenamen eingeben und **Gerät als** Suchtyp auswählen.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Aktualisieren von nicht persistenten VDI-Images (Virtual Desktop Infrastructure)
Als bewährte Methode wird die Verwendung von Offlinewartungstools zum Patchen von Golden/Master-Images empfohlen.<br>
Sie können z. B. die folgenden Befehle verwenden, um ein Update zu installieren, während das Image offline bleibt:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Weitere Informationen zu DISM-Befehlen und zur Offlinewartung finden Sie in den folgenden Artikeln:
- [Ändern eines Windows mithilfe von DISM](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM Image Management Command-Line Optionen](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Verringern der Größe der Komponente Store in einem Offline-Windows Bild](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Wenn die Offlinewartung keine praktikable Option für Ihre nicht persistente VDI-Umgebung ist, sollten die folgenden Schritte ausgeführt werden, um Konsistenz und Sensorintehigkeit sicherzustellen:

1. Führen Sie nach dem Start des Masterimages für die Onlinewartung oder das Patchen ein offboarding-Skript aus, um den Microsoft 365 Endpoint Data Loss Prevention Sensor zu deaktivieren. Weitere Informationen finden Sie unter [Offboardgeräte mit einem lokalen Skript](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).

2. Stellen Sie sicher, dass der Sensor angehalten wird, indem Sie den folgenden Befehl in einem CMD-Fenster ausführen:

   ```console
   sc query sense
   ```

3. Service des Images nach Bedarf.

4. Führen Sie die folgenden Befehle mit PsExec.exe (die heruntergeladen werden können, um die Inhalte des Cyberordners zu bereinigen, die der Sensor seit dem Start möglicherweise angesammelt https://download.sysinternals.com/files/PSTools.zip) hat:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Versiegeln Sie das Golden/Master-Bild wie gewohnt erneut.

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding Windows 10 Geräte mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)
- [Onboarding Windows 10 Geräte mithilfe Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](dlp-configure-endpoints-mdm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md)
- [Problembehandlung bei Microsoft Defender Advanced Threat Protection Onboardingproblemen](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)