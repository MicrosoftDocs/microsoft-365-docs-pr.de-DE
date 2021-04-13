---
title: Verwalten, wie und wo Microsoft Defender Antivirus Updates empfängt
description: Verwalten Sie die Fallbackreihenfolge, wie Microsoft Defender Antivirus Schutzupdates erhält.
keywords: Updates, Sicherheitsgrundwerte, Schutz, Fallbackreihenfolge, ADL, MMPC, UNC, Dateipfad, Freigabe, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 77f3c4f478e2124010445bacfe2c10c5810ed480
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690401"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>Verwalten der Quellen für Microsoft Defender Antivirus-Schutzupdates

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

Es ist wichtig, Ihren Antivirenschutz auf dem neuesten Stand zu halten. Es gibt zwei Komponenten zum Verwalten von Schutzupdates für Microsoft Defender Antivirus: 
- *Wo* die Updates heruntergeladen werden; und 
- *Wenn* Updates heruntergeladen und angewendet werden. 

In diesem Artikel wird beschrieben, wie Sie angeben, von wo Updates heruntergeladen werden sollen (dies wird auch als Fallbackreihenfolge bezeichnet). Unter [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md) topic finden Sie eine Übersicht über die Funktionsweise von Updates und die Konfiguration anderer Aspekte von Updates (z. B. planen von Updates).

> [!IMPORTANT]
> Microsoft Defender Antivirus Security Intelligence Updates werden über Windows Update zugestellt, und ab Montag, dem 21. Oktober 2019, werden alle Sicherheitsintelligenzupdates ausschließlich sha-2 signiert. Ihre Geräte müssen aktualisiert werden, um SHA-2 zu unterstützen, um Ihre Sicherheitsintelligenz zu aktualisieren. Weitere Informationen finden Sie unter [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).  


<a id="fallback-order"></a>

## <a name="fallback-order"></a>Fallbackreihenfolge

In der Regel konfigurieren Sie Endpunkte so, dass Updates von einer primären Quelle gefolgt von anderen Quellen in der Reihenfolge ihrer Priorität basierend auf Ihrer Netzwerkkonfiguration einzeln heruntergeladen werden. Updates werden aus Quellen in der angegebenen Reihenfolge erhalten. Wenn keine Quelle verfügbar ist, wird die nächste Quelle in der Liste sofort verwendet.

Wenn Updates veröffentlicht werden, wird eine gewisse Logik angewendet, um die Größe des Updates zu minimieren. In den meisten Fällen werden nur die Unterschiede zwischen dem aktuellen Update und dem aktuell installierten Update (das als Delta bezeichnet wird) auf dem Gerät heruntergeladen und angewendet. Die Größe des Deltas hängt jedoch von zwei Hauptfaktoren ab:
- Das Alter des letzten Updates auf dem Gerät; und 
- Die Quelle, die zum Herunterladen und Anwenden von Updates verwendet wird. 

Je älter die Updates auf einem Endpunkt sind, desto größer ist der Download. Sie müssen jedoch auch die Downloadhäufigkeit berücksichtigen. Ein häufigerer Aktualisierungszeitplan kann zu einer höheren Netzwerkauslastung führen, während ein weniger häufigerer Zeitplan zu größeren Dateigrößen pro Download führen kann. 

Es gibt fünf Speicherorte, an denen Sie angeben können, wo ein Endpunkt Updates abrufen soll: 

- [Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows Server Update Service](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [Netzwerkdateifreigabe](#unc-share)
- [Sicherheitsintelligenzupdates](https://www.microsoft.com/en-us/wdsi/defenderupdates) für Microsoft Defender Antivirus und andere Antischalware von Microsoft (Ihre Richtlinie und Registrierung kann als Microsoft Center zum Schutz vor Malware (MMPC)-Sicherheitsintelligenz, ihren früheren Namen, aufgeführt sein.)

Um ein optimales Schutzniveau sicherzustellen, ermöglicht Microsoft Update schnelle Versionen, was häufig kleinere Downloads bedeutet. Die Updatesquellen Windows Server Update Service, Microsoft Endpoint Configuration Manager und Microsoft Security Intelligence liefern weniger häufige Updates. Daher kann das Delta größer sein, was zu größeren Downloads führt. 

> [!IMPORTANT]
> Wenn Sie Microsoft Security Intelligence-Seitenupdates nach Windows Server Update Service oder Microsoft Update als Ausweichquelle festgelegt haben, werden Updates nur aus Sicherheitsintelligenzupdates heruntergeladen, wenn das aktuelle Update als veraltet angesehen wird. [](https://www.microsoft.com/security/portal/definitions/adl.aspx) (Standardmäßig sind dies sieben aufeinander folgende Tage, an dem keine Updates vom Windows Server Update Service oder von Microsoft Update-Diensten angewendet werden können).
> Sie können jedoch die Anzahl der Tage festlegen, bevor der Schutz [als veraltet gemeldet wird.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)<p>
> Ab Montag, 21. Oktober 2019, werden Sicherheitsintelligenzupdates ausschließlich sha-2 signiert. Geräte müssen aktualisiert werden, um SHA-2 zu unterstützen, um die neuesten Sicherheitsintelligenzupdates zu erhalten. Weitere Informationen finden Sie unter [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).

Jede Quelle verfügt über typische Szenarien, die davon abhängen, wie Ihr Netzwerk konfiguriert ist, zusätzlich dazu, wie oft Updates veröffentlicht werden, wie in der folgenden Tabelle beschrieben:

|Speicherort | Beispielszenario |
|---|---|
|Windows Server Update Service | Sie verwenden Windows Server Update Service, um Updates für Ihr Netzwerk zu verwalten.|
|Microsoft Update | Sie möchten, dass Ihre Endpunkte eine direkte Verbindung mit Microsoft Update herstellen. Dies kann für Endpunkte nützlich sein, die unregelmäßig eine Verbindung mit Ihrem Unternehmensnetzwerk herstellen, oder wenn Sie den Windows Server Update Service nicht zum Verwalten Ihrer Updates verwenden.|
|Dateifreigabe | Sie verfügen über nicht mit dem Internet verbundene Geräte (z. B. VMs). Sie können Ihren mit dem Internet verbundenen VM-Host verwenden, um die Updates auf eine Netzwerkfreigabe herunterzuladen, von der die virtuellen Computer die Updates abrufen können. Im [VDI-Bereitstellungshandbuch](deployment-vdi-microsoft-defender-antivirus.md) erfahren Sie, wie Dateifreigaben in VDI-Umgebungen (Virtual Desktop Infrastructure) verwendet werden können.|
|Microsoft Endpoint Manager | Sie verwenden Microsoft Endpoint Manager, um Ihre Endpunkte zu aktualisieren.|
|Sicherheitsintelligenzupdates für Microsoft Defender Antivirus und andere Microsoft-Antischammsoftware (früher als MMPC bezeichnet) |[Stellen Sie sicher, dass Ihre Geräte aktualisiert werden, um SHA-2 zu unterstützen.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus) Microsoft Defender Antivirus Security Intelligence-Updates werden über Windows Update zugestellt, und ab Montag, dem 21. Oktober 2019, werden Sicherheitsintelligenzupdates ausschließlich sha-2 signiert. <br/>Laden Sie die neuesten Schutzupdates aufgrund einer kürzlichen Infektion herunter oder helfen Sie bei der Bereitstellung eines starken Basisimages für [die VDI-Bereitstellung.](deployment-vdi-microsoft-defender-antivirus.md) Diese Option sollte im Allgemeinen nur als endgültige Fallbackquelle und nicht als primäre Quelle verwendet werden. Es wird nur verwendet, wenn Updates für eine bestimmte Anzahl von Tagen nicht von Windows Server Update Service oder Microsoft Update [heruntergeladen werden können.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)|

Sie können die Reihenfolge verwalten, in der Aktualisierungsquellen mit Gruppenrichtlinien, Microsoft Endpoint Configuration Manager, PowerShell-Cmdlets und WMI verwendet werden.

> [!IMPORTANT]
> Wenn Sie Windows Server Update Service als Downloadspeicherort festlegen, müssen Sie die Updates genehmigen, unabhängig vom Verwaltungstool, das Sie zum Angeben des Speicherorts verwenden. Sie können eine automatische Genehmigungsregel mit Windows Server Update Service einrichten, was nützlich sein kann, wenn Updates mindestens einmal am Tag eintreffen. Weitere Informationen finden Sie unter [Synchronisieren von Endpunktschutzupdates im eigenständigen Windows Server Update Service](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).

In den Verfahren in diesem Artikel wird zunächst beschrieben, wie  Sie die Reihenfolge festlegen und dann die Dateifreigabeoption einrichten, wenn Sie sie aktiviert haben.

## <a name="use-group-policy-to-manage-the-update-location"></a>Verwenden von Gruppenrichtlinien zum Verwalten des Updatespeicherorts

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**

4. Erweitern Sie die Struktur auf **Windows-> Windows Defender > Signaturupdates,** und konfigurieren Sie die folgenden Einstellungen:

   1.  Doppelklicken Sie auf **die Einstellung Die Reihenfolge der Quellen** für das Herunterladen von Sicherheitsintelligenzupdates definieren, und legen Sie die Option auf Aktiviert **fest.**

   2.  Geben Sie die Reihenfolge der Quellen ein, getrennt durch eine einzelne Pipe, z. B.: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` , wie im folgenden Screenshot gezeigt.

   ![Screenshot der Gruppenrichtlinieneinstellung, die die Reihenfolge der Quellen auflistet](images/defender/wdav-order-update-sources.png)

   3. Klicken Sie auf **OK**. Dadurch wird die Reihenfolge der Schutzupdatequellen festgelegt.

   4. Doppelklicken Sie auf die Einstellung **Dateifreigaben für das Herunterladen von** Sicherheitsintelligenzupdates definieren, und legen Sie die Option auf **Aktiviert fest.**

   5. Geben Sie die Dateifreigabequelle ein. Wenn Sie über mehrere Quellen verfügen, geben Sie jede Quelle in der zu verwendenden Reihenfolge ein, getrennt durch eine einzelne Pipe. Verwenden [Sie die Standard-UNC-Notation,](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) um den Pfad zu verwenden, z. B.: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` .  Wenn Sie keine Pfade eingeben, wird diese Quelle übersprungen, wenn der virtuelle Computer Updates herunterlädet.

   6. Klicken Sie auf **OK**. Dadurch wird die Reihenfolge der Dateifreigaben festgelegt, wenn auf diese Quelle in der Gruppenrichtlinieneinstellung Definieren der Reihenfolge der **Quellen...** verwiesen wird.

> [!NOTE]
> Für Windows 10, Versionen 1703 bis einschließlich 1809, ist der Richtlinienpfad Windows-Komponenten **> Microsoft Defender Antivirus >** Signaturupdates für Windows 10, Version 1903, der Richtlinienpfad ist **Windows-Komponenten > Microsoft Defender Antivirus > Security Intelligence Updates**

## <a name="use-configuration-manager-to-manage-the-update-location"></a>Verwenden von Configuration Manager zum Verwalten des Updatespeicherorts

Weitere Informationen zum Konfigurieren von Microsoft Endpoint Manager (current branch) finden Sie unter [Configure Security Intelligence Updates for Endpoint Protection.](/configmgr/protect/deploy-use/endpoint-definition-updates)


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>Verwenden von PowerShell-Cmdlets zum Verwalten des Updatespeicherorts

Verwenden Sie die folgenden PowerShell-Cmdlets, um die Updatereihenfolge zu festlegen.

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
Weitere Informationen finden Sie in den folgenden Artikeln:
- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender-Cmdlets](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>Verwalten des Updatespeicherorts mithilfe von Windows Management Instruction (WMI)

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

Weitere Informationen finden Sie in den folgenden Artikeln:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>Verwalten des Updatespeicherorts mithilfe von Mobile Device Management (MDM)

Weitere Informationen zum Konfigurieren von MDM finden Sie unter [Policy CSP - Defender/SignatureUpdateFallbackOrder.](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder)

## <a name="what-if-were-using-a-third-party-vendor"></a>Was passiert, wenn wir einen Drittanbieter verwenden?

In diesem Artikel wird beschrieben, wie Sie Updates für Microsoft Defender Antivirus konfigurieren und verwalten. Drittanbieter können jedoch verwendet werden, um diese Aufgaben auszuführen. 

Angenommen, Contoso hat Fabrikam für die Verwaltung ihrer Sicherheitslösung eingestellt, die Microsoft Defender Antivirus umfasst. Fabrikam verwendet in der Regel [die Windows-Verwaltungsinstrumentierung,](./use-wmi-microsoft-defender-antivirus.md) [PowerShell-Cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md)oder die [Windows-Befehlszeile,](./command-line-arguments-microsoft-defender-antivirus.md) um Patches und Updates zu bereitstellen. 

> [!NOTE]
> Microsoft teste keine Drittanbieterlösungen für die Verwaltung von Microsoft Defender Antivirus.

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a>Erstellen einer UNC-Freigabe für Sicherheitsintelligenzupdates

Richten Sie eine Netzwerkdateifreigabe (UNC/zugeordnetes Laufwerk) ein, um Sicherheitsintelligenzupdates mithilfe einer geplanten Aufgabe vom MMPC-Standort herunterzuladen.

1. Erstellen Sie auf dem System, auf dem Sie die Freigabe bereitstellen und die Updates herunterladen möchten, einen Ordner, in dem Sie das Skript speichern.
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. Erstellen Sie den Ordner, in dem Sie die Signaturupdates speichern.
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. Laden Sie das PowerShell-Skript von [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4.](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)

4. Klicken Sie **auf Manuell herunterladen**.

5. Klicken **Sie auf Die unformatierte nupkg-Datei herunterladen.**

6. Extrahieren Sie die Datei.

7. Kopieren Sie die Datei SignatureDownloadCustomTask.ps1 ordner, den Sie zuvor erstellt haben, C:\Tool\PS-Scripts\ .

8. Verwenden Sie die Befehlszeile, um den geplanten Vorgang zu einrichten.
    > [!NOTE]
    > Es gibt zwei Arten von Updates: vollständig und delta.
   - Für x64 delta:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - Für x64 full:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - Für x86 delta:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - Für x86 vollständig:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

    > [!NOTE]
    > Wenn die geplanten Vorgänge erstellt werden, finden Sie diese im Aufgabenplaner unter Microsoft\Windows\Windows Defender
9. Führen Sie die einzelnen Aufgaben manuell aus, und überprüfen Sie, ob Daten (mpam-d.exe, mpam-fe.exe und nis_full.exe) in den folgenden Ordnern enthalten sind (Möglicherweise haben Sie unterschiedliche Speicherorte ausgewählt):

   - C:\Temp\TempSigs\x86
   - C:\Temp\TempSigs\x64

   Wenn der geplante Vorgang fehlschlägt, führen Sie die folgenden Befehle aus:

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86″
    ```
    > [!NOTE]
    > Probleme können auch aufgrund der Ausführungsrichtlinie auftreten.
    
10. Erstellen Sie eine Freigabe, die auf C:\Temp\TempSigs (z. B. \\ server\updates) verweisen soll.
    > [!NOTE]
    > Authentifizierte Benutzer müssen mindestens über "Lesezugriff" verfügen.
11. Legen Sie den Freigabespeicherort in der Richtlinie auf die Freigabe.

    > [!NOTE]
    > Fügen Sie den Ordner x64 (oder x86) nicht im Pfad hinzu. Der mpcmdrun.exe wird automatisch hinzugefügt.

## <a name="related-articles"></a>Verwandte Artikel

- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Verwalten ereignisbasierter erzwungener Updates](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Verwalten von Updates für mobile Geräte und VMs](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)