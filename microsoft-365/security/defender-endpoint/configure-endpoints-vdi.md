---
title: Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)
description: Stellen Sie das Konfigurationspaket auf dem VDI-Gerät (Virtual Desktop Infrastructure) bereit, damit es in den Microsoft Defender für Endpunktdienst integriert ist.
keywords: Virtual Desktop Infrastructure (VDI)-Gerät konfigurieren, vdi, Geräteverwaltung, Microsoft Defender für Endpunkt konfigurieren, Endpunkte
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
ms.openlocfilehash: d09967a18848365702f52f65a7f0624d2b2ae3d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843210"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- VDI-Geräte (Virtual Desktop Infrastructure)
- Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)

Defender für Endpunkt unterstützt das Onboarding von nicht persistenten VDI-Sitzungen. 


Beim Onboarding von VDIs können Probleme auftreten. Nachfolgend sind typische Herausforderungen für dieses Szenario aufgeführt:

- Sofortiges frühes Onboarding einer kurzlebigen Sitzung, die vor der tatsächlichen Bereitstellung in Defender für Endpunkt integriert werden muss.
- Der Gerätename wird in der Regel für neue Sitzungen wiederverwendet.

VDI-Geräte können im Defender für Endpunkt-Portal als eine der folgenden Optionen angezeigt werden:

- Einzelner Eintrag für jedes Gerät.

  > [!NOTE]
  > In diesem Fall muss *derselbe* Gerätename konfiguriert werden, wenn die Sitzung erstellt wird, z. B. mithilfe einer unbeaufsichtigten Antwortdatei.

- Mehrere Einträge für jedes Gerät – einer für jede Sitzung.

Die folgenden Schritte führen Sie durch das Onboarding von VDI-Geräten und heben die Schritte für einzelne und mehrere Einträge hervor.

>[!WARNING]
> In Umgebungen mit geringen Ressourcenkonfigurationen kann das VDI-Startverfahren das Onboarding des Defender für Endpunkt-Sensors verlangsamen. 


### <a name="for-windows-10-or-windows-server-2019"></a>For Windows 10 or Windows Server 2019

1.  Öffnen Sie das VDI-Konfigurationspaket .zip Datei (*WindowsDefenderATPOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben. Sie können das Paket auch von [Microsoft Defender Security Center](https://securitycenter.windows.com/)abrufen:

    1.  Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding** aus.

    1. Wählen Sie Windows 10 als Betriebssystem aus.

    1.  Wählen Sie im Feld **"Bereitstellungsmethode"** **VDI-Onboardingskripts für nicht persistente Endpunkte aus.**

    1. Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.

2. Kopieren Sie die Dateien aus dem Ordner "WindowsDefenderATPOnboardingPackage", die aus der .zip-Datei extrahiert wurden, in das `golden/master` Bild unter dem `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` Pfad. 

    1. Wenn Sie keinen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie "WindowsDefenderATPOnboardingScript.cmd".

    1. Wenn Sie einen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie sowohl Onboard-NonPersistentMachine.ps1 als auch WindowsDefenderATPOnboardingScript.cmd.
    
    > [!NOTE]
    > Wenn der Ordner nicht angezeigt `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` wird, ist er möglicherweise ausgeblendet. Sie müssen die Option **"Ausgeblendete Dateien und Ordner anzeigen"** im Datei-Explorer auswählen.

3. Öffnen Sie ein Lokales Gruppenrichtlinien-Editor-Fenster, und navigieren Sie zum Start von **Computerkonfiguration**  >  **Windows Einstellungen**  >  **Skripts.**  >  

   > [!NOTE]
   > Domänengruppenrichtlinien können auch für das Onboarding nicht persistenter VDI-Geräte verwendet werden.

4. Je nachdem, welche Methode Sie implementieren möchten, führen Sie die entsprechenden Schritte aus:

   - Für einen einzelnen Eintrag für jedes Gerät:
   
     Wählen Sie die Registerkarte **"PowerShell-Skripts"** aus, und klicken Sie dann auf **"Hinzufügen"** (Windows Explorer direkt in dem Pfad geöffnet wird, in den Sie das Onboardingskript zuvor kopiert haben). Navigieren Sie zum Onboarding des PowerShell-Skripts. `Onboard-NonPersistentMachine.ps1` Es ist nicht erforderlich, die andere Datei anzugeben, da sie automatisch ausgelöst wird.
   
   - Für mehrere Einträge für jedes Gerät:
   
     Wählen Sie die Registerkarte **"Skripts"** aus, und klicken Sie dann auf **"Hinzufügen"** (Windows Explorer direkt in dem Pfad geöffnet wird, in den Sie das Onboardingskript zuvor kopiert haben). Navigieren Sie zum Onboarding-Bash-Skript. `WindowsDefenderATPOnboardingScript.cmd`

5. Testen Sie Ihre Lösung:

   1. Erstellen Sie einen Pool mit einem Gerät.
      
   1. Melden Sie sich am Gerät an.
      
   1. Abmelden vom Gerät.

   1. Melden Sie sich mit einem anderen Benutzer am Gerät an.
      
   1. Je nachdem, welche Methode Sie implementieren möchten, führen Sie die entsprechenden Schritte aus:
   
      - Für einen einzelnen Eintrag für jedes Gerät: 
    
        Überprüfen Sie nur einen Eintrag in Microsoft Defender Security Center.

      - Für mehrere Einträge für jedes Gerät: 
       
        Überprüfen Sie mehrere Einträge in Microsoft Defender Security Center.

6. Klicken Sie im Navigationsbereich auf **"Geräteliste".**

7. Verwenden Sie die Suchfunktion, indem Sie den Gerätenamen eingeben und **"Gerät"** als Suchtyp auswählen.


## <a name="for-downlevel-skus"></a>Für Vorgänger-SKUs

> [!NOTE]
> Die folgende Registrierung ist nur relevant, wenn das Ziel darin besteht, einen "einzelnen Eintrag für jedes Gerät" zu erzielen.

1. Legen Sie den Registrierungswert auf:

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    oder mithilfe der Befehlszeile:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. Folgen Sie dem [Server-Onboarding-Prozess.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016) 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Aktualisieren von VDI-Images (Non-Persistent Virtual Desktop Infrastructure)
Als bewährte Methode empfehlen wir die Verwendung von Offlinewartungstools zum Patchen von goldenen/Master-Images.<br>
Sie können z. B. die folgenden Befehle verwenden, um ein Update zu installieren, während das Bild offline bleibt:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Weitere Informationen zu DISM-Befehlen und zur Offlinewartung finden Sie in den folgenden Artikeln:
- [Ändern eines Windows-Images mithilfe von DISM](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM-Imageverwaltung Command-Line Optionen](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Verringern der Größe der Komponente Store in einem Offline-Windows-Image](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Wenn die Offlinewartung für Ihre nicht persistente VDI-Umgebung keine geeignete Option ist, sollten die folgenden Schritte ausgeführt werden, um Konsistenz und Sensorintegrität sicherzustellen:

1. Führen Sie nach dem Start des Masterimages für online servicing or patching ein Offboarding-Skript aus, um den Defender für Endpunkt-Sensor zu deaktivieren. Weitere Informationen finden Sie unter [Offboarding von Geräten mithilfe eines lokalen Skripts.](configure-endpoints-script.md#offboard-devices-using-a-local-script)

2. Stellen Sie sicher, dass der Sensor beendet wird, indem Sie den folgenden Befehl in einem CMD-Fenster ausführen:

   ```console
   sc query sense
   ```

3. Dienst das Image nach Bedarf.

4. Führen Sie die folgenden Befehle mit PsExec.exe aus (die heruntergeladen werden https://download.sysinternals.com/files/PSTools.zip) können, um die Inhalte des Cyberordners zu bereinigen, die der Sensor seit dem Start möglicherweise angesammelt hat:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Versiegeln Sie das Gold-Master-Bild erneut wie gewohnt.

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien](configure-endpoints-gp.md)
- [Onboarding von Windows 10 Geräten mithilfe von Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](configure-endpoints-mdm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](configure-endpoints-script.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten](troubleshoot-onboarding.md)
