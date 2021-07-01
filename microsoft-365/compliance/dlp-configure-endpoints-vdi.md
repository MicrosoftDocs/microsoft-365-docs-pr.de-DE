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
description: Stellen Sie das Konfigurationspaket auf einem VDI-Gerät (Virtual Desktop Infrastructure) bereit, damit es in den Microsoft 365 Endpunkt-Dienst zur Verhinderung von Datenverlust integriert ist.
ms.openlocfilehash: 64d9bfed3d1d5600b5843c697e894577f83527fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226875"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)

**Gilt für:**
- [Microsoft 365 Verhinderung von Datenverlust am Endpunkt (Endpoint Data Loss Prevention, DLP)](./endpoint-dlp-learn-about.md)

- VDI-Geräte (Virtual Desktop Infrastructure)

> [!WARNING]
> Microsoft 365 Endpunkt-DLP-Unterstützung für Windows Virtual Desktop unterstützt Szenarien mit einzelnen Sitzungen. Szenarien mit mehreren Sitzungen auf Windows Virtual Desktop werden derzeit nicht unterstützt.

## <a name="onboard-vdi-devices"></a>Onboarding von VDI-Geräten

Microsoft 365 Die Verhinderung von Datenverlust am Endpunkt unterstützt nicht persistentes VDI-Sitzungs-Onboarding.

> [!NOTE]
> Um nicht persistente VDI-Sitzungen zu integrieren, müssen sich VDI-Geräte auf Windows 10 1809 oder höher befinden.

Beim Onboarding von VDIs können Probleme auftreten. Nachfolgend sind typische Herausforderungen für dieses Szenario aufgeführt:

- Sofortiges frühes Onboarding einer kurzlebigen Sitzung, die vor der tatsächlichen Bereitstellung in Microsoft 365 Verhinderung von Datenverlust am Endpunkt integriert werden muss.
- Der Gerätename wird in der Regel für neue Sitzungen wiederverwendet.

VDI-Geräte können im Microsoft 365 Compliance Center als eine der folgenden Optionen angezeigt werden:

- Einzelner Eintrag für jedes Gerät.
Beachten Sie, dass in diesem Fall *derselbe* Gerätename konfiguriert werden muss, wenn die Sitzung erstellt wird, z. B. mithilfe einer unbeaufsichtigten Antwortdatei.
- Mehrere Einträge für jedes Gerät – einer für jede Sitzung.

Die folgenden Schritte führen Sie durch das Onboarding von VDI-Geräten und heben die Schritte für einzelne und mehrere Einträge hervor.

> [!WARNING]
> In Umgebungen mit geringen Ressourcenkonfigurationen kann die VDI-Startprozedur das Onboarding der Microsoft 365 Verhinderung von Datenverlust am Endpunkt verlangsamen.

1. Öffnen Sie das VDI-Konfigurationspaket .zip Datei (*DeviceCompliancePackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben.

2. Wählen Sie im Navigationsbereich **Einstellungen** Onboarding des  >  **Geräts**  >  aus.

3. Wählen Sie im Feld **"Bereitstellungsmethode"** **VDI-Onboardingskripts für nicht persistente Endpunkte aus.**

4. Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.

5. Kopieren Sie die Dateien aus dem Ordner "DeviceCompliancePackage" aus der .zip-Datei in das `golden/master` Bild unter dem `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` Pfad.

6. Wenn Sie keinen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie "DeviceComplianceOnboardingScript.cmd".

7. Wenn Sie einen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie sowohl Onboard-NonPersistentMachine.ps1 als auch DeviceComplianceOnboardingScript.cmd.

    > [!NOTE]
    > Wenn der Ordner nicht angezeigt `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` wird, ist er möglicherweise ausgeblendet. Sie müssen die Option **"Ausgeblendete Dateien und Ordner anzeigen"** im Datei-Explorer auswählen.

8. Öffnen Sie ein Fenster "Editor für lokale Gruppenrichtlinien", und navigieren Sie zum Start von **"Computerkonfiguration**  >  **Windows Einstellungen**  >  **Skripts".**  >  

   > [!NOTE]
   > Domänengruppenrichtlinien können auch für das Onboarding nicht persistenter VDI-Geräte verwendet werden.

9. Je nachdem, welche Methode Sie implementieren möchten, führen Sie die entsprechenden Schritte aus:

   **Für einen einzelnen Eintrag für jedes Gerät**

   Wählen Sie die Registerkarte **PowerShell-Skripts** aus, und klicken Sie dann auf **"Hinzufügen"** (Windows Explorer direkt in dem Pfad geöffnet wird, in den Sie das Onboardingskript zuvor kopiert haben). Navigieren Sie zum Onboarding des PowerShell-Skripts. `Onboard-NonPersistentMachine.ps1`

   **Für mehrere Einträge für jedes Gerät:**

   Wählen Sie die Registerkarte **"Skripts"** aus, und klicken Sie dann auf **"Hinzufügen"** (Windows Explorer direkt in dem Pfad geöffnet wird, in den Sie das Onboardingskript zuvor kopiert haben). Navigieren Sie zum Onboarding-Bash-Skript. `DeviceComplianceOnboardingScript.cmd`

10. Testen Sie Ihre Lösung:
    1. Erstellen Sie einen Pool mit einem Gerät.
    1. Melden Sie sich am Gerät an.
    1. Abmelden vom Gerät.
    1. Melden Sie sich mit einem anderen Benutzer am Gerät an.
    1. **Für einen einzelnen Eintrag für jedes Gerät:** Überprüfen Sie nur einen Eintrag in Microsoft Defender Security Center.
       **Für mehrere Einträge für jedes Gerät:** Überprüfen Sie mehrere Einträge in Microsoft Defender Security Center.

11. Klicken Sie im Navigationsbereich auf **"Geräteliste".**

12. Verwenden Sie die Suchfunktion, indem Sie den Gerätenamen eingeben und **"Gerät"** als Suchtyp auswählen.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Aktualisieren von VDI-Images (Non-Persistent Virtual Desktop Infrastructure)

Als bewährte Methode empfehlen wir die Verwendung von Offlinewartungstools zum Patchen von goldenen/Master-Images.

Sie können z. B. die folgenden Befehle verwenden, um ein Update zu installieren, während das Bild offline bleibt:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Weitere Informationen zu DISM-Befehlen und zur Offlinewartung finden Sie in den folgenden Artikeln:

- [Ändern eines Windows Bilds mit DISM](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM-Imageverwaltung Command-Line Optionen](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Verringern der Größe der Komponente Store in einem Offline-Windows-Image](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Wenn die Offlinewartung für Ihre nicht persistente VDI-Umgebung keine geeignete Option ist, sollten die folgenden Schritte ausgeführt werden, um Konsistenz und Sensorintegrität sicherzustellen:

1. Führen Sie nach dem Starten des Masterimages für online servicing or patching ein Offboarding-Skript aus, um den Microsoft 365 Endpunkt-Sensor zur Verhinderung von Datenverlust zu deaktivieren. Weitere Informationen finden Sie unter [Offboarding von Geräten mithilfe eines lokalen Skripts.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)

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

- [Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)
- [Onboarding von Windows 10 Geräten mithilfe von Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](dlp-configure-endpoints-mdm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender Advanced Threat Protection](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
