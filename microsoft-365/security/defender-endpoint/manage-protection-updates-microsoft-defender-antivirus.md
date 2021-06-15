---
title: Verwalten, wie und wo Microsoft Defender Antivirus Updates empfängt
description: Verwalten Sie die Fallbackreihenfolge, wie Microsoft Defender Antivirus Schutzupdates empfängt.
keywords: Updates, Sicherheitsgrundwerte, Schutz, Fallbackreihenfolge, ADL, MMPC, UNC, Dateipfad, Freigeben, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 35873b371e773e793ae966a338150e2e5e256a42
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926031"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>Verwalten der Quellen für Updates für Microsoft Defender Antivirus-Schutz

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

Es ist wichtig, den Virenschutz auf dem neuesten Stand zu halten. Es gibt zwei Komponenten zum Verwalten von Schutzupdates für Microsoft Defender Antivirus: 
- *Wo* die Updates heruntergeladen werden; Und 
- *Wenn* Updates heruntergeladen und angewendet werden. 

In diesem Artikel wird beschrieben, wie Sie angeben, von wo Updates heruntergeladen werden sollen (dies wird auch als Fallbackreihenfolge bezeichnet). Eine Übersicht über die Funktionsweise von Updates und das Konfigurieren anderer Aspekte von Updates (z. B. Planen von Updates) finden Sie unter Verwalten Microsoft Defender Antivirus Updates und Anwenden von [Basisplänen.](manage-updates-baselines-microsoft-defender-antivirus.md)

> [!IMPORTANT]
> Microsoft Defender Antivirus Security Intelligence-Updates werden über Windows Update bereitgestellt, und ab Montag, dem 21. Oktober 2019, werden alle Security Intelligence-Updates ausschließlich SHA-2 signiert. Ihre Geräte müssen aktualisiert werden, um SHA-2 zu unterstützen, um Ihre Sicherheitsintelligenz zu aktualisieren. Weitere Informationen finden Sie unter [2019 SHA-2 Code Signing Support Requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).  


<a id="fallback-order"></a>

## <a name="fallback-order"></a>Fallbackreihenfolge

In der Regel konfigurieren Sie Endpunkte, um Updates aus einer primären Quelle, gefolgt von anderen Quellen, basierend auf Ihrer Netzwerkkonfiguration in der Reihenfolge ihrer Priorität einzeln herunterzuladen. Updates werden aus Quellen in der von Ihnen angegebenen Reihenfolge abgerufen. Wenn keine Quelle verfügbar ist, wird die nächste Quelle in der Liste sofort verwendet.

Wenn Updates veröffentlicht werden, wird eine Logik angewendet, um die Größe des Updates zu minimieren. In den meisten Fällen werden nur die Unterschiede zwischen dem neuesten Update und dem update, das derzeit auf dem Gerät installiert ist (dies wird als Delta bezeichnet) heruntergeladen und angewendet. Die Größe des Deltas hängt jedoch von zwei Hauptfaktoren ab:
- Das Alter des letzten Updates auf dem Gerät; Und 
- Die Quelle, die zum Herunterladen und Anwenden von Updates verwendet wird. 

Je älter die Updates auf einem Endpunkt sind, desto größer ist der Download. Sie müssen jedoch auch die Downloadhäufigkeit berücksichtigen. Ein häufigerer Updatezeitplan kann zu einer höheren Netzwerkauslastung führen, während ein weniger häufiger Zeitplan zu größeren Dateigrößen pro Download führen kann. 

Es gibt fünf Speicherorte, an denen Sie angeben können, wo ein Endpunkt Updates erhalten soll: 

- [Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows Serverupdatedienst](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [Netzwerkdateifreigabe](#unc-share)
- [Updates zur Sicherheitsintelligenz für Microsoft Defender Antivirus und andere Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates) von Microsoft (in Ihrer Richtlinie und Registrierung ist diese möglicherweise als Microsoft Center zum Schutz vor Malware (MMPC) Security Intelligence aufgeführt, der frühere Name.)

Um ein optimales Schutzniveau zu gewährleisten, ermöglicht Microsoft Update schnelle Versionen, was häufig kleinere Downloads bedeutet. Die Updatequellen Windows Server Update Service, Microsoft Endpoint Configuration Manager und Microsoft Security Intelligence bieten weniger häufige Updates. Daher kann das Delta größer sein, was zu größeren Downloads führen kann. 

> [!IMPORTANT]
> Wenn Sie [Microsoft Security Intelligence-Seitenupdates](https://www.microsoft.com/security/portal/definitions/adl.aspx) nach Windows Server Update Service oder Microsoft Update als Fallbackquelle festgelegt haben, werden Updates nur von Sicherheitsupdates heruntergeladen, wenn das aktuelle Update als veraltet gilt. (Standardmäßig sind dies sieben aufeinander folgende Tage, an denen updates von Windows Server Update Service oder Microsoft Update Services nicht angewendet werden können).)
> Sie können jedoch [die Anzahl der Tage festlegen, bevor der Schutz als veraltet gemeldet wird.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)<p>
> Ab Montag, 21. Oktober 2019, werden Security Intelligence-Updates ausschließlich SHA-2 signiert. Geräte müssen aktualisiert werden, um SHA-2 zu unterstützen, um die neuesten Security Intelligence-Updates zu erhalten. Weitere Informationen finden Sie unter [2019 SHA-2 Code Signing Support Requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).

Jede Quelle verfügt über typische Szenarien, die davon abhängen, wie Ihr Netzwerk konfiguriert ist, und wie oft updates veröffentlicht werden, wie in der folgenden Tabelle beschrieben:

|Speicherort | Beispielszenario |
|---|---|
|Windows Serverupdatedienst | Sie verwenden Windows Server Update Service, um Updates für Ihr Netzwerk zu verwalten.|
|Microsoft Update | Sie möchten, dass Ihre Endpunkte eine direkte Verbindung mit Microsoft Update herstellen. Dies kann für Endpunkte nützlich sein, die unregelmäßig eine Verbindung mit Ihrem Unternehmensnetzwerk herstellen, oder wenn Sie Windows Server Update Service nicht verwenden, um Ihre Updates zu verwalten.|
|Dateifreigabe | Sie verfügen über nicht mit dem Internet verbundene Geräte (z. B. VMs). Sie können Ihren mit dem Internet verbundenen VM-Host verwenden, um die Updates auf eine Netzwerkfreigabe herunterzuladen, von der die VMs die Updates abrufen können. Im [VDI-Bereitstellungshandbuch](deployment-vdi-microsoft-defender-antivirus.md) erfahren Sie, wie Dateifreigaben in VDI-Umgebungen (Virtual Desktop Infrastructure) verwendet werden können.|
|Microsoft Endpoint Manager | Sie verwenden Microsoft Endpoint Manager, um Ihre Endpunkte zu aktualisieren.|
|Sicherheitsupdates für Microsoft Defender Antivirus und andere Antischadsoftware von Microsoft (früher mmpc genannt) |[Stellen Sie sicher, dass Ihre Geräte aktualisiert wurden, um SHA-2 zu unterstützen.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus) Microsoft Defender Antivirus Security Intelligence-Updates werden über Windows Update bereitgestellt, und ab Montag, dem 21. Oktober 2019, werden Security Intelligence-Updates ausschließlich SHA-2 signiert. <br/>Laden Sie die neuesten Schutzupdates aufgrund einer kürzlichen Infektion herunter, oder um ein sicheres Basisimage für die [VDI-Bereitstellung](deployment-vdi-microsoft-defender-antivirus.md)bereitzustellen. Diese Option sollte in der Regel nur als endgültige Fallbackquelle und nicht als primäre Quelle verwendet werden. Es wird nur verwendet, wenn Updates für [eine bestimmte Anzahl von Tagen](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)nicht aus Windows Server Update Service oder Microsoft Update heruntergeladen werden können.|

Sie können die Reihenfolge verwalten, in der Updatequellen mit Gruppenrichtlinien, Microsoft Endpoint Configuration Manager, PowerShell-Cmdlets und WMI verwendet werden.

> [!IMPORTANT]
> Wenn Sie Windows Server Update Service als Downloadspeicherort festlegen, müssen Sie die Updates unabhängig vom Verwaltungstool genehmigen, das Sie zum Angeben des Speicherorts verwenden. Sie können eine automatische Genehmigungsregel mit Windows Server Update Service einrichten, was hilfreich sein kann, wenn Updates mindestens einmal täglich eintreffen. Weitere Informationen finden Sie unter [Synchronisieren von Endpunktschutzupdates im eigenständigen Windows Server Update Service.](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)

In den Verfahren in diesem Artikel wird zuerst beschrieben, wie die Reihenfolge festgelegt und dann die **Dateifreigabeoption** eingerichtet wird, wenn Sie sie aktiviert haben.

## <a name="use-group-policy-to-manage-the-update-location"></a>Verwenden von Gruppenrichtlinien zum Verwalten des Updatespeicherorts

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur bis **Windows Komponenten > Windows Defender > Signaturupdates,** und konfigurieren Sie die folgenden Einstellungen:

   1.  Doppelklicken Sie auf die Einstellung **"Definieren der Reihenfolge der Quellen für das Herunterladen von Sicherheitsupdates",** und legen Sie die Option auf **"Aktiviert"** fest.

   2.  Geben Sie die Reihenfolge der Quellen, getrennt durch eine einzelne Pipe, ein, z. B.: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` , wie im folgenden Screenshot dargestellt.

   ![Screenshot der Gruppenrichtlinieneinstellung, die die Reihenfolge der Quellen auflistet](images/defender/wdav-order-update-sources.png)

   3. Klicken Sie auf **OK**. Dadurch wird die Reihenfolge der Schutzaktualisierungsquellen festgelegt.

   4. Doppelklicken Sie auf die Einstellung **"Dateifreigaben zum Herunterladen von Sicherheitsupdates definieren",** und legen Sie die Option auf **"Aktiviert"** fest.

   5. Geben Sie die Dateifreigabequelle ein. Wenn Sie über mehrere Quellen verfügen, geben Sie jede Quelle in der Reihenfolge ein, in der sie verwendet werden sollen, getrennt durch ein einzelnes Pipe. Verwenden Sie [die Standard-UNC-Notation](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) zum Angeben des Pfads, z. B.: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` .  Wenn Sie keine Pfade eingeben, wird diese Quelle übersprungen, wenn der virtuelle Computer Updates herunterlädt.

   6. Klicken Sie auf **OK**. Dadurch wird die Reihenfolge der Dateifreigaben festgelegt, wenn auf diese Quelle in der Gruppenrichtlinieneinstellung **"Definieren der Reihenfolge der Quellen...** " verwiesen wird.

> [!NOTE]
> Für Windows 10, Versionen 1703 bis einschließlich 1809, lautet der Richtlinienpfad **Windows Komponenten > Microsoft Defender Antivirus > Signaturupdates** für Windows 10, Version 1903, der Richtlinienpfad ist **Windows Komponenten > Microsoft Defender Antivirus > Security Intelligence Updates**

## <a name="use-configuration-manager-to-manage-the-update-location"></a>Verwenden von Configuration Manager zum Verwalten des Updatespeicherorts

Weitere Informationen zum Konfigurieren von Microsoft Endpoint Manager (current branch) finden Sie unter Konfigurieren von [Security Intelligence Updates für Endpoint Protection.](/configmgr/protect/deploy-use/endpoint-definition-updates)


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>Verwenden von PowerShell-Cmdlets zum Verwalten des Updatespeicherorts

Verwenden Sie die folgenden PowerShell-Cmdlets, um die Updatereihenfolge festzulegen.

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
Weitere Informationen finden Sie in den folgenden Artikeln:
- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender-Cmdlets](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>Verwenden Windows Management Instruction (WMI) zum Verwalten des Updatespeicherorts

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

Weitere Informationen finden Sie in den folgenden Artikeln:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>Verwenden der mobilen Geräteverwaltung (Mobile Device Management, MDM) zum Verwalten des Updatespeicherorts

Weitere Informationen zum Konfigurieren von MDM finden Sie unter ["Richtlinien-CSP – Defender/SignatureUpdateFallbackOrder".](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder)

## <a name="what-if-were-using-a-third-party-vendor"></a>Was geschieht, wenn wir einen Drittanbieter verwenden?

In diesem Artikel wird beschrieben, wie Updates für Microsoft Defender Antivirus konfiguriert und verwaltet werden. Für diese Aufgaben können jedoch Drittanbieter verwendet werden. 

Angenommen, Contoso hat Fabrikam für die Verwaltung seiner Sicherheitslösung eingestellt, die Microsoft Defender Antivirus umfasst. Fabrikam verwendet in der Regel [Windows Verwaltungsinstrumentation,](./use-wmi-microsoft-defender-antivirus.md) [PowerShell-Cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md)oder [Windows Befehlszeile,](./command-line-arguments-microsoft-defender-antivirus.md) um Patches und Updates bereitzustellen. 

> [!NOTE]
> Microsoft teste keine Drittanbieterlösungen für die Verwaltung von Microsoft Defender Antivirus.

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a>Erstellen einer UNC-Freigabe für Security Intelligence-Updates

Richten Sie eine Netzwerkdateifreigabe (UNC/zugeordnetes Laufwerk) ein, um Sicherheitsupdates mithilfe einer geplanten Aufgabe von der MMPC-Website herunterzuladen.

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

3. Laden Sie das PowerShell-Skript aus [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)herunter.

4. Klicken Sie auf **"Manuell herunterladen".**

5. Klicken Sie auf **die unformatierte nupkg-Datei herunterladen.**

6. Extrahieren Sie die Datei.

7. Kopieren Sie die Datei SignatureDownloadCustomTask.ps1 in den zuvor erstellten Ordner C:\Tool\PS-Scripts\.

8. Verwenden Sie die Befehlszeile, um die geplante Aufgabe einzurichten.
    > [!NOTE]
    > Es gibt zwei Arten von Updates: vollständig und delta.
   - Für x64 Delta:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Für x64 vollständig:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Für x86-Delta:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Für x86 vollständig:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

    > [!NOTE]
    > Wenn die geplanten Vorgänge erstellt werden, finden Sie diese im Aufgabenplaner unter Microsoft\Windows\Windows Defender
9. Führen Sie jede Aufgabe manuell aus, und stellen Sie sicher, dass Daten (mpam-d.exe, mpam-fe.exe und nis_full.exe) in den folgenden Ordnern vorhanden sind (Möglicherweise haben Sie unterschiedliche Speicherorte ausgewählt):

   - C:\Temp\TempSigs\x86
   - C:\Temp\TempSigs\x64

   Wenn die geplante Aufgabe fehlschlägt, führen Sie die folgenden Befehle aus:

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```
    > [!NOTE]
    > Probleme können auch auf die Ausführungsrichtlinie zurückzuführen sein.
    
10. Erstellen Sie eine Freigabe, die auf C:\Temp\TempSigs verweist (z. B. \\ Server\Updates).
    > [!NOTE]
    > Authentifizierte Benutzer müssen mindestens über Lesezugriff verfügen.
11. Legen Sie den Freigabespeicherort in der Richtlinie auf die Freigabe fest.

    > [!NOTE]
    > Fügen Sie dem Pfad nicht den Ordner "x64" (oder "x86") hinzu. Der mpcmdrun.exe Prozess fügt ihn automatisch hinzu.

## <a name="related-articles"></a>Verwandte Artikel

- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Verwalten von Updates für mobile Geräte und virtuelle Computer](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
