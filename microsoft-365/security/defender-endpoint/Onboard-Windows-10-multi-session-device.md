---
title: Onboarden von Windows 10-Geräten für mehrere Sitzungen in Windows Virtual Desktop
description: Weitere Informationen finden Sie in diesem Artikel zum Onboarding von Windows 10-Geräten mit mehreren Sitzungen in Windows Virtual Desktop
keywords: Windows Virtual Desktop, WVD, microsoft defender, endpoint, onboard
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
ms.openlocfilehash: 0ef80e2aaccbf25a79083c2f95ea7399e30ea651
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764317"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a>Onboarden von Windows 10-Geräten für mehrere Sitzungen in Windows Virtual Desktop 
6 Minuten zu lesen 

Gilt für: 
- Windows 10 multi-session running on Windows Virtual Desktop (WVD) 

Microsoft Defender for Endpoint unterstützt die Überwachung von VDI- und Windows Virtual Desktop-Sitzungen. Je nach Den Anforderungen Ihrer Organisation müssen Sie möglicherweise VDI- oder Windows Virtual Desktop-Sitzungen implementieren, um Ihren Mitarbeitern den Zugriff auf Unternehmensdaten und Apps von einem nicht verwalteten Gerät, Remotespeicherort oder ähnlichem Szenario zu unterstützen. Mit Microsoft Defender for Endpoint können Sie diese virtuellen Computer auf anomale Aktivitäten überwachen.

 ## <a name="before-you-begin"></a>Bevor Sie beginnen
Machen Sie sich mit den [Überlegungen für nicht persistente VDI vertraut.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1) Windows [Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) bietet zwar keine Nichtpersistenzoptionen, bietet jedoch Möglichkeiten zur Verwendung eines goldenen Windows-Images, das zum Bereitstellen neuer Hosts und erneut bereitgestellter Computer verwendet werden kann. Dies erhöht die Unbeständigkeit in der Umgebung und wirkt sich somit auf die Einträge aus, die im Microsoft Defender for Endpoint-Portal erstellt und verwaltet werden, wodurch die Sichtbarkeit für Ihre Sicherheitsanalysten potenziell reduziert wird.

> [!NOTE]
> Je nach Wahl der Onboardingmethode können Geräte im Microsoft Defender for Endpoint-Portal wie folgt angezeigt werden: 
> - Einzelner Eintrag für jeden virtuellen Desktop 
> - Mehrere Einträge für jeden virtuellen Desktop 

Microsoft empfiehlt das Onboarding von Windows Virtual Desktop als einzelnen Eintrag pro virtuellem Desktop. Dadurch wird sichergestellt, dass sich die Untersuchungserfahrung im Microsoft Defender Endpoint-Portal im Kontext eines Geräts befindet, das auf dem Computernamen basiert. Organisationen, die häufig WVD-Hosts löschen und erneut bereitstellen, sollten die Verwendung dieser Methode in Betracht ziehen, da dadurch verhindert wird, dass mehrere Objekte für denselben Computer im Microsoft Defender for Endpoint-Portal erstellt werden. Dies kann bei der Untersuchung von Vorfällen zu Verwirrung führen. Für Testumgebungen oder nicht flüchtige Umgebungen können Sie eine andere Auswahl auswählen. 

Microsoft empfiehlt das Hinzufügen des Microsoft Defender for Endpoint-Onboardingskripts zum goldenen WVD-Image. Auf diese Weise können Sie sicher sein, dass dieses Onboardingskript sofort beim ersten Start ausgeführt wird. Es wird beim ersten Start auf allen WVD-Computern, die aus dem goldenen WVD-Image bereitgestellt werden, als Startskript ausgeführt. Wenn Sie jedoch eines der Katalogbilder ohne Änderung verwenden, platzieren Sie das Skript an einem freigegebenen Speicherort, und rufen Sie es entweder aus einer lokalen oder einer Domänengruppenrichtlinie auf. 

> [!NOTE]
> Die Platzierung und Konfiguration des Startskripts für das VDI-Onboarding im goldenen WVD-Image konfiguriert es als Startskript, das beim Starten der WVD ausgeführt wird. Es wird NICHT empfohlen, das tatsächliche goldene WVD-Image zu integrieren. Eine weitere Überlegung ist die Methode, mit der das Skript ausgeführt wird. Sie sollte so früh wie möglich im Start-/Bereitstellungsprozess ausgeführt werden, um die Zeit zwischen dem Computer, der für den Empfang von Sitzungen verfügbar ist, und dem Onboarding des Geräts an den Dienst zu reduzieren. In den folgenden Szenarien 1 & 2 wird dies berücksichtigt.

### <a name="scenarios"></a>Szenarien
Es gibt mehrere Möglichkeiten zum Onboarding eines WVD-Hostcomputers:

- Führen Sie das Skript während des Startvorgangs im goldenen Bild (oder von einem freigegebenen Speicherort) aus.
- Verwenden Sie ein Verwaltungstool, um das Skript auszuführen.

#### <a name="scenario-1-using-local-group-policy"></a>*Szenario 1: Verwenden der lokalen Gruppenrichtlinie*
In diesem Szenario muss das Skript in einem goldenen Bild platziert werden und verwendet lokale Gruppenrichtlinien, um frühzeitig im Startvorgang ausgeführt zu werden.

Verwenden Sie die Anweisungen unter [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).

Befolgen Sie die Anweisungen für einen einzelnen Eintrag für jedes Gerät.

#### <a name="scenario-2-using-domain-group-policy"></a>*Szenario 2: Verwenden von Domänengruppenrichtlinien*
In diesem Szenario wird ein zentral gelegenes Skript verwendet und mithilfe einer domänenbasierten Gruppenrichtlinie ausgeführt. Sie können das Skript auch in das goldene Bild platzieren und auf die gleiche Weise ausführen.

**Laden Sie die WindowsDefenderATPOnboardingPackage.zip aus dem Windows Defender Security Center herunter**

1. Öffnen Sie die ZIP-Datei des VDI-Konfigurationspakets (WindowsDefenderATPOnboardingPackage.zip)  

    1. Wählen Sie im Navigationsbereich des Microsoft Defender Security Center die Option **Einstellungen**  >  **Onboarding aus.** 
    1. Wählen Sie Windows 10 als Betriebssystem aus. 
    1. Wählen Sie **im Feld Bereitstellungsmethode** die Option VDI-Onboardingskripts für nicht persistente Endpunkte aus. 
    1. Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei. 

2. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den das Gerät zugreifen kann. Sie sollten über einen Ordner **namens OptionalParamsPolicy** und die **Dateien WindowsDefenderATPOnboardingScript.cmd** und **Onboard-NonPersistentMachine.ps1**.

**Verwenden der Gruppenrichtlinienverwaltungskonsole zum Ausführen des Skripts beim Starten des virtuellen Computers**

1. Öffnen Sie die Gruppenrichtlinienverwaltungskonsole (Group Policy Management Console, GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt(GPO), das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie im Gruppenrichtlinienverwaltungs-Editor zu **Einstellungen** für die \> Systemsteuerung **der** \> **Computerkonfiguration.** 

3. Klicken Sie mit der rechten Maustaste auf Geplante **Vorgänge,** klicken Sie auf **Neu,** und klicken Sie dann auf **Sofortaufgabe** (Mindestens Windows 7). 

4. Wechseln Sie im geöffneten Aufgabenfenster zur Registerkarte **Allgemein.** Klicken **Sie unter Sicherheitsoptionen** **auf Benutzer oder Gruppe ändern, und** geben Sie SYSTEM ein. Klicken **Sie auf Namen** überprüfen, und klicken Sie dann auf OK. NT AUTHORITY\SYSTEM wird als Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird. 

5. Aktivieren **Sie Ausführen, ob der Benutzer** angemeldet ist oder nicht, und aktivieren Sie das Kontrollkästchen Mit höchsten **Rechten** ausführen. 

6. Wechseln Sie zur **Registerkarte Aktionen,** und klicken Sie auf **Neu**. Stellen Sie **sicher, dass Programm starten** im Feld Aktion ausgewählt ist. Geben Sie Folgendes ein: 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   Wählen Sie dann **OK aus,** und schließen Sie alle geöffneten GPMC-Fenster.

#### <a name="scenario-3-onboarding-using-management-tools"></a>*Szenario 3: Onboarding mithilfe von Verwaltungstools*

Wenn Sie planen, Ihre Computer mithilfe eines Verwaltungstools zu verwalten, können Sie Geräte mit Microsoft Endpoint Configuration Manager integrieren.

Weitere Informationen finden Sie unter [OnboardIng Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).

> [!WARNING]
> Wenn Sie Attack Surface Reduction [Rules](attack-surface-reduction.md)verwenden möchten, beachten Sie, dass die Regel " Block process creations from[PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" nicht verwendet werden sollte, da diese Regel mit der Verwaltung über Microsoft Endpoint Configuration Manager nicht kompatibel ist. Die Regel blockiert WMI-Befehle, die der Configuration Manager-Client verwendet, um ordnungsgemäß zu funktionieren. 

> [!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um sicherzustellen, dass das Gerät ordnungsgemäß in den Dienst integrierte ist. Weitere Informationen finden Sie unter Ausführen eines Erkennungstests auf einem neu integrierten [Microsoft Defender for Endpoint-Gerät.](run-detection-test.md) 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>Markieren Ihrer Computer beim Erstellen Ihres goldenen Bilds 

Im Rahmen Ihres Onboardings sollten Sie ein Computertag festlegen, um WVD-Computer im Microsoft Security Center einfacher voneinander zu unterscheiden. Weitere Informationen finden Sie unter [Hinzufügen von Gerätetags durch Festlegen eines Registrierungsschlüsselwerts.](machine-tags.md#add-device-tags-by-setting-a-registry-key-value) 

#### <a name="other-recommended-configuration-settings"></a>Weitere empfohlene Konfigurationseinstellungen 

Beim Erstellen Ihres goldenen Bilds sollten Sie möglicherweise auch die anfänglichen Schutzeinstellungen konfigurieren. Weitere Informationen finden Sie unter [Weitere empfohlene Konfigurationseinstellungen](configure-endpoints-gp.md#other-recommended-configuration-settings). 

Wenn Sie außerdem FSlogix-Benutzerprofile verwenden, wird empfohlen, die folgenden Dateien vom Immer-On-Schutz auszuschließen: 

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

Hinweis zur Lizenzierung: Bei der Verwendung von Windows 10 Enterprise-Mehrsitzungen können Sie je nach Ihren Anforderungen entweder alle Benutzer über Microsoft Defender for Endpoint (pro Benutzer), Windows Enterprise E5, Microsoft 365 Security oder Microsoft 365 E5 lizenziert haben oder den virtuellen Computer über Azure Defender lizenziert haben.
Lizenzierungsanforderungen für Microsoft Defender für Endpunkt finden Sie unter: [Lizenzierungsanforderungen](minimum-requirements.md#licensing-requirements).
