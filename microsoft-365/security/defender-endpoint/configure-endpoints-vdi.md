---
title: Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)
description: Stellen Sie das Konfigurationspaket auf einem Virtuellen Desktopinfrastrukturgerät (Virtual Desktop Infrastructure, VDI) so sicher, dass es in Microsoft Defender ATP den Dienst integrierte.
keywords: Konfigurieren von Virtual Desktop Infrastructure (VDI)-Geräten, vdi, Geräteverwaltung, Konfigurieren von Windows ATP-Endpunkten, Konfigurieren von Microsoft Defender für Endpunkte
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: bf1e706562db06064409cb7cf11441d048ef8db6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445286"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Virtual Desktop Infrastructure (VDI)-Geräte
- Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)

Defender for Endpoint unterstützt das nicht persistente Onboarding von VDI-Sitzungen. 


Beim Onboarding von VDIs kann es zu herausforderungen kommen. Es folgen typische Herausforderungen für dieses Szenario:

- Sofortiges frühzeitiges Onboarding einer kurzlebigen Sitzung, die vor der tatsächlichen Bereitstellung in Defender for Endpoint onboardiert werden muss.
- Der Gerätename wird in der Regel für neue Sitzungen wiederverwendet.

VDI-Geräte können im Defender for Endpoint-Portal wie folgt angezeigt werden:

- Einzelner Eintrag für jedes Gerät.

  > [!NOTE]
  > In diesem Fall muss derselbe *Gerätename* beim Erstellen der Sitzung konfiguriert werden, z. B. mithilfe einer unbeaufsichtigten Antwortdatei.

- Mehrere Einträge für jedes Gerät – einer für jede Sitzung.

Die folgenden Schritte führen Sie durch das Onboarding von VDI-Geräten und zeigen Schritte für einzelne und mehrere Einträge an.

>[!WARNING]
> In Umgebungen mit geringen Ressourcenkonfigurationen kann das Onboarding des Defender for Endpoint-Sensors durch die VDI-Startprozedur verlangsamt werden. 


### <a name="for-windows-10-or-windows-server-2019"></a>Für Windows 10 oder Windows Server 2019

1.  Öffnen Sie die ZIP-Datei des VDI-Konfigurationspakets (*WindowsDefenderATPOnboardingPackage.zip*), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben. Sie können das Paket auch über [das Microsoft Defender Security Center erhalten:](https://securitycenter.windows.com/)

    1.  Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding aus.**

    1. Wählen Sie Windows 10 als Betriebssystem aus.

    1.  Wählen Sie **im Feld Bereitstellungsmethode** die Option **VDI-Onboardingskripts für nicht persistente Endpunkte aus.**

    1. Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.

2. Kopieren Sie die Dateien aus dem Ordner WindowsDefenderATPOnboardingPackage aus der ZIP-Datei in das Bild `golden/master` unter dem Pfad `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

    1. Wenn Sie keinen einzigen Eintrag für jedes Gerät implementieren, kopieren Sie WindowsDefenderATPOnboardingScript.cmd.

    1. Wenn Sie einen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie Onboard-NonPersistentMachine.ps1 windowsDefenderATPOnboardingScript.cmd.
    
    > [!NOTE]
    > Wenn der Ordner nicht angezeigt `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` wird, wird er möglicherweise ausgeblendet. Sie müssen die Option  Ausgeblendete Dateien und Ordner anzeigen im Datei-Explorer auswählen.

3. Öffnen Sie ein Fenster des Editors für lokale Gruppenrichtlinien, und navigieren Sie zu **Computerkonfiguration**  >  **Windows-Einstellungen**  >  **Skripts**  >  **starten**.

   > [!NOTE]
   > Domänengruppenrichtlinien können auch zum Onboarding nicht persistenter VDI-Geräte verwendet werden.

4. Führen Sie in Abhängigkeit von der Methode, die Sie implementieren möchten, die entsprechenden Schritte aus:

   - Für einen einzelnen Eintrag für jedes Gerät:
   
     Wählen Sie **die Registerkarte PowerShell-Skripts** aus, und klicken Sie dann auf Hinzufügen **(Windows** Explorer wird direkt im Pfad geöffnet, in den Sie das Onboardingskript zuvor kopiert haben). Navigieren Sie zum Onboarding des PowerShell-Skripts `Onboard-NonPersistentMachine.ps1` . Die andere Datei muss nicht angegeben werden, da sie automatisch ausgelöst wird.
   
   - Für mehrere Einträge für jedes Gerät:
   
     Wählen Sie **die Registerkarte Skripts** aus, und klicken Sie dann auf **Hinzufügen** (Windows Explorer wird direkt im Pfad geöffnet, in den Sie das Onboardingskript zuvor kopiert haben). Navigieren Sie zum Onboarding-Bash-Skript `WindowsDefenderATPOnboardingScript.cmd` .

5. Testen Sie Ihre Lösung:

   1. Erstellen Sie einen Pool mit einem Gerät.
      
   1. Bei Gerät anmeldet.
      
   1. Abmelden vom Gerät.

   1. Bei einem anderen Benutzer am Gerät anmeldet.
      
   1. Führen Sie in Abhängigkeit von der Methode, die Sie implementieren möchten, die entsprechenden Schritte aus:
   
      - Für einen einzelnen Eintrag für jedes Gerät: 
    
        Überprüfen Sie nur einen Eintrag im Microsoft Defender Security Center.

      - Für mehrere Einträge für jedes Gerät: 
       
        Überprüfen Sie mehrere Einträge im Microsoft Defender Security Center.

6. Klicken **Sie im** Navigationsbereich auf Geräteliste.

7. Verwenden Sie die Suchfunktion, indem Sie den Gerätenamen eingeben und **Gerät als** Suchtyp auswählen.


## <a name="for-downlevel-skus"></a>Für skUs auf Abwärtsebene

> [!NOTE]
> Die folgende Registrierung ist nur relevant, wenn es darum geht, einen "einzelnen Eintrag für jedes Gerät" zu erreichen.

1. Legen Sie den Registrierungswert auf:

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    oder verwenden Sie die Befehlszeile:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. Folgen Sie [dem Server-Onboarding-Prozess.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016) 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Aktualisieren von nicht persistenten VDI-Images (Virtual Desktop Infrastructure)
Als bewährte Methode wird die Verwendung von Offlinewartungstools zum Patchen von Golden/Master-Images empfohlen.<br>
Sie können z. B. die folgenden Befehle verwenden, um ein Update zu installieren, während das Image offline bleibt:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Weitere Informationen zu DISM-Befehlen und zur Offlinewartung finden Sie in den folgenden Artikeln:
- [Ändern eines Windows-Images mithilfe von DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM Image Management Command-Line Optionen](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Verringern der Größe des Komponentenspeichers in einem Offline-Windows-Image](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Wenn die Offlinewartung keine praktikable Option für Ihre nicht persistente VDI-Umgebung ist, sollten die folgenden Schritte ausgeführt werden, um Konsistenz und Sensorintehigkeit sicherzustellen:

1. Führen Sie nach dem Start des Masterimages für die Onlinewartung oder das Patchen ein offboarding-Skript aus, um den Defender for Endpoint-Sensor zu deaktivieren. Weitere Informationen finden Sie unter [Offboardgeräte mit einem lokalen Skript](configure-endpoints-script.md#offboard-devices-using-a-local-script).

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
- [Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien](configure-endpoints-gp.md)
- [Onboarding von Windows 10-Geräten mithilfe von Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](configure-endpoints-mdm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](configure-endpoints-script.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint](troubleshoot-onboarding.md)
