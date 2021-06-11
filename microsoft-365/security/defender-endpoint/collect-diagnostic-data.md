---
title: Sammeln von Diagnosedaten von Microsoft Defender Antivirus
description: Verwenden eines Tools zum Sammeln von Daten zur Problembehandlung bei Microsoft Defender Antivirus
keywords: Troubleshoot, error, fix, update compliance, oms, monitor, report, Microsoft Defender av, group policy object, setting, diagnostic data
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 7686f28646135986a78b4c269e41e2fc3a70dff9
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904044"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a><span data-ttu-id="ae06e-104">Sammeln von Microsoft Defender AV-Diagnosedaten</span><span class="sxs-lookup"><span data-stu-id="ae06e-104">Collect Microsoft Defender AV diagnostic data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ae06e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ae06e-105">**Applies to:**</span></span>

- [<span data-ttu-id="ae06e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ae06e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ae06e-107">In diesem Artikel wird beschrieben, wie Sie Diagnosedaten sammeln, die von Microsoft-Support- und -Entwicklungsteams zur Behandlung von Problemen verwendet werden können, die bei der Verwendung von Microsoft Defender AV auftreten können.</span><span class="sxs-lookup"><span data-stu-id="ae06e-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you might encounter when using the Microsoft Defender AV.</span></span>

> [!NOTE]
> <span data-ttu-id="ae06e-108">Im Rahmen des Untersuchungs- oder Reaktionsprozesses können Sie ein Untersuchungspaket von einem Gerät erfassen.</span><span class="sxs-lookup"><span data-stu-id="ae06e-108">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="ae06e-109">Hier sehen Sie, wie: [Erfassen Sie untersuchungspaket von Geräten](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span><span class="sxs-lookup"><span data-stu-id="ae06e-109">Here's how: [Collect investigation package from devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="ae06e-110">Rufen Sie auf mindestens zwei Geräten, auf denen dasselbe Problem auftritt, die .cab Diagnosedatei ab, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ae06e-110">On at least two devices that are experiencing the same issue, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="ae06e-111">Öffnen Sie eine Version der Eingabeaufforderung auf Administratorebene wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ae06e-111">Open an administrator-level version of the command prompt as follows:</span></span>

    <span data-ttu-id="ae06e-112">a.</span><span class="sxs-lookup"><span data-stu-id="ae06e-112">a.</span></span> <span data-ttu-id="ae06e-113">Öffnen Sie das **Startmenü.**</span><span class="sxs-lookup"><span data-stu-id="ae06e-113">Open the **Start** menu.</span></span>

    <span data-ttu-id="ae06e-114">b.</span><span class="sxs-lookup"><span data-stu-id="ae06e-114">b.</span></span> <span data-ttu-id="ae06e-115">Geben Sie **cmd ein.**</span><span class="sxs-lookup"><span data-stu-id="ae06e-115">Type **cmd**.</span></span> <span data-ttu-id="ae06e-116">Klicken Sie mit der rechten Maustaste auf **die Eingabeaufforderung,** und wählen Sie dann **als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="ae06e-116">Right-click on **Command Prompt** and then select **Run as administrator**.</span></span>

    <span data-ttu-id="ae06e-117">c.</span><span class="sxs-lookup"><span data-stu-id="ae06e-117">c.</span></span> <span data-ttu-id="ae06e-118">Geben Sie Administratoranmeldeinformationen an, oder genehmigen Sie die Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="ae06e-118">Specify administrator credentials or approve the prompt.</span></span>

2. <span data-ttu-id="ae06e-119">Navigieren Sie zum Microsoft Defender-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ae06e-119">Navigate to the Microsoft Defender directory.</span></span> <span data-ttu-id="ae06e-120">Der Standardwert ist `C:\Program Files\Windows Defender`.</span><span class="sxs-lookup"><span data-stu-id="ae06e-120">By default, this is `C:\Program Files\Windows Defender`.</span></span>

> [!NOTE]
> <span data-ttu-id="ae06e-121">Wenn Sie eine [aktualisierte Version](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)von Microsoft Defender Platform ausführen, führen Sie dies bitte `MpCmdRun` an folgendem Speicherort aus: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="ae06e-121">If you're running an [updated Microsoft Defender Platform version](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform), please run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

3. <span data-ttu-id="ae06e-122">Geben Sie den folgenden Befehl ein, und drücken Sie dann die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="ae06e-122">Type the following command, and then press **Enter**</span></span>  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. <span data-ttu-id="ae06e-123">Es wird eine .cab Datei generiert, die verschiedene Diagnoseprotokolle enthält.</span><span class="sxs-lookup"><span data-stu-id="ae06e-123">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="ae06e-124">Der Speicherort der Datei wird in der Ausgabe in der Eingabeaufforderung angegeben.</span><span class="sxs-lookup"><span data-stu-id="ae06e-124">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="ae06e-125">Standardmäßig lautet der Speicherort `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="ae06e-125">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

> [!NOTE]
> <span data-ttu-id="ae06e-126">Um die CAB-Datei an einen anderen Pfad oder eine andere UNC-Freigabe umzuleiten, verwenden Sie den folgenden Befehl: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span><span class="sxs-lookup"><span data-stu-id="ae06e-126">To redirect the cab file to a a different path or UNC share, use the following command: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span></span>  <br/><span data-ttu-id="ae06e-127">Weitere Informationen finden Sie unter [Umleiten von Diagnosedaten an eine UNC-Freigabe.](#redirect-diagnostic-data-to-a-unc-share)</span><span class="sxs-lookup"><span data-stu-id="ae06e-127">For more information, see [Redirect diagnostic data to a UNC share](#redirect-diagnostic-data-to-a-unc-share).</span></span>

5. <span data-ttu-id="ae06e-128">Kopieren Sie diese .cab-Dateien an einen Speicherort, auf den der Microsoft-Support zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ae06e-128">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="ae06e-129">Ein Beispiel könnte ein kennwortgeschützter OneDrive Ordner sein, den Sie für uns freigeben können.</span><span class="sxs-lookup"><span data-stu-id="ae06e-129">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

> [!NOTE]
><span data-ttu-id="ae06e-130">Wenn Sie ein Problem mit der Updatecompliance haben, senden Sie eine E-Mail mithilfe der <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">E-Mail-Vorlage zur Updatecompliance-Unterstützung,</a>und füllen Sie die Vorlage mit den folgenden Informationen aus:</span><span class="sxs-lookup"><span data-stu-id="ae06e-130">If you have a problem with Update compliance, send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a><span data-ttu-id="ae06e-131">Umleiten von Diagnosedaten an eine UNC-Freigabe</span><span class="sxs-lookup"><span data-stu-id="ae06e-131">Redirect diagnostic data to a UNC share</span></span>
<span data-ttu-id="ae06e-132">Um Diagnosedaten in einem zentralen Repository zu sammeln, können Sie den SupportLogLocation-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="ae06e-132">To collect diagnostic data on a central repository, you can specify the SupportLogLocation parameter.</span></span>

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

<span data-ttu-id="ae06e-133">Kopiert die Diagnosedaten in den angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="ae06e-133">Copies the diagnostic data to the specified path.</span></span> <span data-ttu-id="ae06e-134">Wenn der Pfad nicht angegeben ist, werden die Diagnosedaten an den in der Konfiguration des Supportprotokollspeicherorts angegebenen Speicherort kopiert.</span><span class="sxs-lookup"><span data-stu-id="ae06e-134">If the path is not specified, the diagnostic data will be copied to the location specified in the Support Log Location Configuration.</span></span>

<span data-ttu-id="ae06e-135">Wenn der Parameter SupportLogLocation verwendet wird, wird eine Ordnerstruktur wie folgt im Zielpfad erstellt:</span><span class="sxs-lookup"><span data-stu-id="ae06e-135">When the SupportLogLocation parameter is used, a folder structure like as follows will be created in the destination path:</span></span>

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| <span data-ttu-id="ae06e-136">Feld</span><span class="sxs-lookup"><span data-stu-id="ae06e-136">field</span></span>  | <span data-ttu-id="ae06e-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae06e-137">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="ae06e-138">path</span><span class="sxs-lookup"><span data-stu-id="ae06e-138">path</span></span> | <span data-ttu-id="ae06e-139">Der Pfad, wie in der Befehlszeile angegeben oder aus der Konfiguration abgerufen</span><span class="sxs-lookup"><span data-stu-id="ae06e-139">The path as specified on the command line or retrieved from configuration</span></span>
| <span data-ttu-id="ae06e-140">MMDD</span><span class="sxs-lookup"><span data-stu-id="ae06e-140">MMDD</span></span> | <span data-ttu-id="ae06e-141">Monat und Tag, an dem die Diagnosedaten gesammelt wurden (z. B. 0530)</span><span class="sxs-lookup"><span data-stu-id="ae06e-141">Month and day when the diagnostic data was collected (for example, 0530)</span></span>
| <span data-ttu-id="ae06e-142">Hostname</span><span class="sxs-lookup"><span data-stu-id="ae06e-142">hostname</span></span> | <span data-ttu-id="ae06e-143">Der Hostname des Geräts, auf dem die Diagnosedaten gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="ae06e-143">The hostname of the device on which the diagnostic data was collected</span></span>
| <span data-ttu-id="ae06e-144">HHMM</span><span class="sxs-lookup"><span data-stu-id="ae06e-144">HHMM</span></span> | <span data-ttu-id="ae06e-145">Stunden und Minuten, in dem die Diagnosedaten gesammelt wurden (z. B. 1422)</span><span class="sxs-lookup"><span data-stu-id="ae06e-145">Hours and minutes when the diagnostic data was collected (for example, 1422)</span></span>

> [!NOTE]
> <span data-ttu-id="ae06e-146">Stellen Sie bei Verwendung einer Dateifreigabe sicher, dass das konto, das zum Sammeln des Diagnosepakets verwendet wird, Schreibzugriff auf die Freigabe hat.</span><span class="sxs-lookup"><span data-stu-id="ae06e-146">When using a file share please make sure that account used to collect the diagnostic package has write access to the share.</span></span>  

## <a name="specify-location-where-diagnostic-data-is-created"></a><span data-ttu-id="ae06e-147">Angeben des Speicherorts, an dem Diagnosedaten erstellt werden</span><span class="sxs-lookup"><span data-stu-id="ae06e-147">Specify location where diagnostic data is created</span></span>

<span data-ttu-id="ae06e-148">Sie können auch angeben, wo die Diagnosedatei .cab mithilfe eines Gruppenrichtlinienobjekts (Group Policy Object, GPO) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ae06e-148">You can also specify where the diagnostic .cab file will be created using a Group Policy Object (GPO).</span></span> 

1. <span data-ttu-id="ae06e-149">Öffnen Sie den Editor für lokale Gruppenrichtlinien, und suchen Sie das SupportLogLocation-Gruppenrichtlinienobjekt unter: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span><span class="sxs-lookup"><span data-stu-id="ae06e-149">Open the Local Group Policy Editor and find the SupportLogLocation GPO at: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span></span>
   
1. <span data-ttu-id="ae06e-150">Wählen Sie **den Verzeichnispfad zum Kopieren von Supportprotokolldateien** aus.</span><span class="sxs-lookup"><span data-stu-id="ae06e-150">Select **Define the directory path to copy support log files**.</span></span>

    ![Screenshot des Editors für lokale Gruppenrichtlinien](images/GPO1-SupportLogLocationDefender.png)  
        
     ![Screenshot der Einstellung zum Definieren des Pfads für Protokolldateien](images/GPO2-SupportLogLocationGPPage.png)  
3. <span data-ttu-id="ae06e-153">Wählen Sie im Richtlinien-Editor **aktiviert** aus.</span><span class="sxs-lookup"><span data-stu-id="ae06e-153">Inside the policy editor, select **Enabled**.</span></span>
       
4. <span data-ttu-id="ae06e-154">Geben Sie den Verzeichnispfad an, in den Sie die Supportprotokolldateien im Feld **"Optionen"** kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ae06e-154">Specify the directory path where you want to copy the support log files in the **Options** field.</span></span>
     <span data-ttu-id="ae06e-155">![Screenshot der benutzerdefinierten Einstellung für aktivierten Verzeichnispfad](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span><span class="sxs-lookup"><span data-stu-id="ae06e-155">![Screenshot of Enabled directory path custom setting](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span></span> 
5. <span data-ttu-id="ae06e-156">Wählen Sie **"OK"** oder **"Anwenden"** aus.</span><span class="sxs-lookup"><span data-stu-id="ae06e-156">Select **OK** or **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae06e-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae06e-157">See also</span></span>

- [<span data-ttu-id="ae06e-158">Problembehandlung bei Microsoft Defender Antivirus Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="ae06e-158">Troubleshoot Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)