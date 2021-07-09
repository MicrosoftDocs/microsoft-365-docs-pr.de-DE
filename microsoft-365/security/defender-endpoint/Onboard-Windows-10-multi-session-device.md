---
title: Onboarden von Windows 10-Geräten für mehrere Sitzungen in Windows Virtual Desktop
description: Weitere Informationen zum Onboarding von Windows 10 Geräten mit mehreren Sitzungen in Windows Virtual Desktop finden Sie in diesem Artikel.
keywords: Windows Virtual Desktop, WVD, Microsoft Defender, Endpunkt, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9114a825ad011f0b2a17cea4929ab2a09bfa2172
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339478"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a>Onboarden von Windows 10-Geräten für mehrere Sitzungen in Windows Virtual Desktop 
6 Minuten zu lesen 

Gilt für: 
- Windows 10 multi-session running on Windows Virtual Desktop (WVD) 

Microsoft Defender für Endpunkt unterstützt die Überwachung von VDI- und Windows Virtual Desktop-Sitzungen. Je nach den Anforderungen Ihrer Organisation müssen Sie möglicherweise VDI- oder Windows Virtual Desktop-Sitzungen implementieren, damit Ihre Mitarbeiter über ein nicht verwaltetes Gerät, einen Remotestandort oder ein ähnliches Szenario auf Unternehmensdaten und Apps zugreifen können. Mit Microsoft Defender für Endpunkt können Sie diese virtuellen Computer auf anomale Aktivitäten überwachen.

 ## <a name="before-you-begin"></a>Bevor Sie beginnen
Machen Sie sich mit den [Überlegungen für nicht persistente VDI](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)vertraut. [Während Windows Virtual Desktop](/azure/virtual-desktop/overview) keine Nichtpersistenzoptionen bereitstellt, bietet es möglichkeiten, ein goldenen Windows-Image zu verwenden, das zum Bereitstellen neuer Hosts und zum erneuten Bereitstellen von Computern verwendet werden kann. Dies erhöht die Aufmerksamkeit in der Umgebung und wirkt sich daher darauf aus, welche Einträge im Microsoft Defender für Endpunkt-Portal erstellt und verwaltet werden, wodurch die Sichtbarkeit für Ihre Sicherheitsanalysten möglicherweise reduziert wird.

> [!NOTE]
> Je nachdem, welche Onboardingmethode Sie auswählen, können Geräte im Microsoft Defender für Endpunkt-Portal als eine der folgenden Optionen angezeigt werden: 
> - Einzelner Eintrag für jeden virtuellen Desktop 
> - Mehrere Einträge für jeden virtuellen Desktop 

Microsoft empfiehlt, Windows virtuellen Desktop als einzelnen Eintrag pro virtuellem Desktop zu integrieren. Dadurch wird sichergestellt, dass sich die Untersuchung im Microsoft Defender Endpoint-Portal im Kontext eines Geräts basierend auf dem Computernamen befindet. Organisationen, die häufig WVD-Hosts löschen und erneut bereitstellen, sollten die Verwendung dieser Methode dringend in Betracht ziehen, da sie verhindert, dass mehrere Objekte für denselben Computer im Microsoft Defender für Endpunkt-Portal erstellt werden. Dies kann bei der Untersuchung von Vorfällen zu Verwirrung führen. Für Testumgebungen oder nicht veränderliche Umgebungen können Sie sich für eine andere Auswahl entscheiden. 

Microsoft empfiehlt das Hinzufügen des Microsoft Defender für Endpunkt-Onboarding-Skripts zum goldenen WVD-Image. Auf diese Weise können Sie sicher sein, dass dieses Onboardingskript sofort beim ersten Start ausgeführt wird. Es wird als Startskript beim ersten Start auf allen WVD-Computern ausgeführt, die vom goldenen WVD-Image bereitgestellt werden. Wenn Sie jedoch eines der Katalogbilder ohne Änderung verwenden, platzieren Sie das Skript an einem freigegebenen Speicherort, und rufen Sie es aus der lokalen oder Domänengruppenrichtlinie auf. 

> [!NOTE]
> Die Platzierung und Konfiguration des VDI-Onboarding-Startskripts auf dem goldenen WVD-Image konfiguriert es als Startskript, das beim Starten der WVD ausgeführt wird. Es wird NICHT empfohlen, das eigentliche WVD-Golden-Image zu integrieren. Eine weitere Überlegung ist die Methode, die zum Ausführen des Skripts verwendet wird. Es sollte so früh wie möglich im Start-/Bereitstellungsprozess ausgeführt werden, um die Zeit zwischen dem Computer, der für den Empfang von Sitzungen verfügbar ist, und dem Onboarding des Geräts in den Dienst zu reduzieren. In den folgenden Szenarien 1 & 2 wird dies berücksichtigt.

### <a name="scenarios"></a>Szenarien
Es gibt mehrere Möglichkeiten zum Onboarding eines WVD-Hostcomputers:

- Führen Sie das Skript während des Starts im goldenen Bild (oder von einem freigegebenen Speicherort) aus.
- Verwenden Sie ein Verwaltungstool, um das Skript auszuführen.

#### <a name="scenario-1-using-local-group-policy"></a>*Szenario 1: Verwenden einer lokalen Gruppenrichtlinie*
Dieses Szenario erfordert, dass das Skript in einem goldenen Image platziert wird und die lokale Gruppenrichtlinie verwendet wird, um früh im Startprozess ausgeführt zu werden.

Verwenden Sie die Anweisungen unter [Onboarding der nicht persistenten VDI-Geräte (Virtual Desktop Infrastructure).](configure-endpoints-vdi.md#onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices)

Befolgen Sie die Anweisungen für einen einzelnen Eintrag für jedes Gerät.

#### <a name="scenario-2-using-domain-group-policy"></a>*Szenario 2: Verwenden von Domänengruppenrichtlinien*
In diesem Szenario wird ein zentral gespeichertes Skript verwendet und mithilfe einer domänenbasierten Gruppenrichtlinie ausgeführt. Sie können das Skript auch im goldenen Bild platzieren und auf die gleiche Weise ausführen.

**Laden Sie die datei WindowsDefenderATPOnboardingPackage.zip aus dem Windows Defender Security Center herunter.**

1. Öffnen Des VDI-Konfigurationspakets .zip Datei (WindowsDefenderATPOnboardingPackage.zip)  

    1. Wählen Sie im Navigationsbereich Microsoft Defender Security Center **Einstellungen**  >  **Onboarding** aus. 
    1. Wählen Sie Windows 10 als Betriebssystem aus. 
    1. Wählen Sie im Feld **"Bereitstellungsmethode"** VDI-Onboardingskripts für nicht persistente Endpunkte aus. 
    1. Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei. 

2. Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann. Sie sollten über einen Ordner namens **"OptionalParamsPolicy"** und die Dateien **"WindowsDefenderATPOnboardingScript.cmd"** und **Onboard-NonPersistentMachine.ps1** verfügen.

**Verwenden der Gruppenrichtlinien-Verwaltungskonsole zum Ausführen des Skripts beim Starten des virtuellen Computers**

1. Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt (Group Policy Object, GPO), das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Wechseln Sie im Gruppenrichtlinienverwaltungs-Editor zu Einstellungen der Systemsteuerung für **die Computerkonfiguration.** \>  \>  

3. Klicken Sie mit der rechten Maustaste auf **Geplante Vorgänge,** klicken Sie auf **Neu** und dann auf **"Sofortvorgang"** (mindestens Windows 7). 

4. Wechseln Sie im geöffneten Aufgabenfenster zur Registerkarte **"Allgemein".** Klicken Sie unter **"Sicherheitsoptionen"** auf **"Benutzer oder Gruppe ändern",** und geben Sie "SYSTEM" ein. Klicken Sie auf **"Namen überprüfen",** und klicken Sie dann auf "OK". NT AUTHORITY\SYSTEM wird als Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird. 

5. Wählen Sie **"Ausführen" aus, ob der Benutzer angemeldet ist oder nicht,** und aktivieren Sie das Kontrollkästchen **"Ausführen mit höchsten Berechtigungen".** 

6. Wechseln Sie zur Registerkarte **"Aktionen",** und klicken Sie auf **"Neu".** Stellen Sie sicher, dass **"Programm starten"** im Feld "Aktion" ausgewählt ist. Geben Sie Folgendes ein: 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   Wählen Sie dann **OK** aus, und schließen Sie alle geöffneten GPMC-Fenster.

#### <a name="scenario-3-onboarding-using-management-tools"></a>*Szenario 3: Onboarding mithilfe von Verwaltungstools*

Wenn Sie beabsichtigen, Ihre Computer mit einem Verwaltungstool zu verwalten, können Sie Geräte mit Microsoft Endpoint Configuration Manager integrieren.

Weitere Informationen finden Sie unter [Onboarding Windows 10 Geräte mit Configuration Manager.](configure-endpoints-sccm.md)

> [!WARNING]
> Wenn Sie die [Attack Surface Reduction-Regeln](attack-surface-reduction.md)verwenden möchten, beachten Sie, dass die Regel["Prozesserstellungen blockieren, die von PSExec- und WMI-Befehlen stammen"](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)nicht verwendet werden sollte, da diese Regel mit der Verwaltung über Microsoft Endpoint Configuration Manager nicht kompatibel ist. Die Regel blockiert WMI-Befehle, die der Configuration Manager-Client verwendet, um ordnungsgemäß zu funktionieren. 

> [!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob das Gerät ordnungsgemäß in den Dienst integriert ist. Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät.](run-detection-test.md) 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>Kennzeichnen Ihrer Computer beim Erstellen ihres goldenen Bilds 

Im Rahmen Ihres Onboardings sollten Sie erwägen, ein Computertag festzulegen, um WVD-Computer im Microsoft Security Center einfacher unterscheiden zu können. Weitere Informationen finden Sie unter [Hinzufügen von Gerätetags durch Festlegen eines Registrierungsschlüsselwerts.](machine-tags.md#add-device-tags-by-setting-a-registry-key-value) 

#### <a name="other-recommended-configuration-settings"></a>Andere empfohlene Konfigurationseinstellungen 

Beim Erstellen ihres goldenen Images sollten Sie auch die anfänglichen Schutzeinstellungen konfigurieren. Weitere Informationen finden Sie unter ["Weitere empfohlene Konfigurationseinstellungen".](configure-endpoints-gp.md#other-recommended-configuration-settings) 

Wenn Sie FSlogix-Benutzerprofile verwenden, wird außerdem empfohlen, die folgenden Dateien vom always-on-Schutz auszuschließen: 

**Ausschließen von Dateien:** 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

**Ausschließen von Prozessen:**

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a>Lizenzierungsanforderungen 

Hinweis zur Lizenzierung: Wenn Sie Windows 10 Enterprise mehrere Sitzung verwenden, können Sie je nach Ihren Anforderungen auswählen, ob alle Benutzer über Microsoft Defender für Endpunkt (pro Benutzer), Windows Enterprise E5, Microsoft 365 Security oder Microsoft 365 E5 lizenziert sind oder ob der virtuelle Computer über Azure Defender lizenziert ist.
Die Lizenzierungsanforderungen für Microsoft Defender für Endpunkt finden Sie unter: [Lizenzierungsanforderungen.](minimum-requirements.md#licensing-requirements)

#### <a name="related-links"></a>Links zu verwandten Themen

[Hinzufügen von Ausschlüssen für Microsoft Defender mithilfe von PowerShell](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-windows-defender-by-using-powershell)
