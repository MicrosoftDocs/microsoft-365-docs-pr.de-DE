---
title: Sammeln von Diagnosedaten für update compliance and Windows Defender Microsoft Defender Antivirus
description: Verwenden eines Tools zum Sammeln von Daten zur Problembehandlung von Problemen mit der Updatekonformität bei Verwendung des Microsoft Defender Antivirus Assessment-Add-Ins
keywords: Problembehandlung, Fehler, Behebung, Updatekonformität, Oms, Monitor, Bericht, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3975a18c2986ac7766664194a6d4b80ee1a503b1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690484"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a><span data-ttu-id="71f97-104">Sammeln von Diagnosedaten zur Updatekonformität für die Microsoft Defender AV-Bewertung</span><span class="sxs-lookup"><span data-stu-id="71f97-104">Collect Update Compliance diagnostic data for Microsoft Defender AV Assessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="71f97-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="71f97-105">**Applies to:**</span></span>

- [<span data-ttu-id="71f97-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="71f97-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="71f97-107">In diesem Artikel wird beschrieben, wie Sie Diagnosedaten sammeln, die von Microsoft-Support- und Engineeringteams verwendet werden können, um Probleme zu beheben, die möglicherweise auftreten, wenn Sie den Abschnitt Microsoft Defender AV Assessment im Update Compliance-Add-In verwenden.</span><span class="sxs-lookup"><span data-stu-id="71f97-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender AV Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="71f97-108">Bevor Sie diesen Prozess versuchen, stellen Sie sicher, dass Sie die Problembehandlung für [Microsoft Defender Antivirus](troubleshoot-reporting.md)gelesen haben, alle erforderlichen Voraussetzungen erfüllt haben und alle anderen vorgeschlagenen Schritte zur Problembehandlung ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="71f97-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="71f97-109">Rufen Sie auf mindestens zwei Geräten, die nicht in update compliance berichten oder angezeigt werden, die Cab-Diagnosedatei ab, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="71f97-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="71f97-110">Öffnen Sie eine Administratorversion der Eingabeaufforderung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="71f97-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="71f97-111">a.</span><span class="sxs-lookup"><span data-stu-id="71f97-111">a.</span></span> <span data-ttu-id="71f97-112">Öffnen Sie das **Startmenü.**</span><span class="sxs-lookup"><span data-stu-id="71f97-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="71f97-113">b.</span><span class="sxs-lookup"><span data-stu-id="71f97-113">b.</span></span> <span data-ttu-id="71f97-114">Geben **Sie cmd ein.**</span><span class="sxs-lookup"><span data-stu-id="71f97-114">Type **cmd**.</span></span> <span data-ttu-id="71f97-115">Klicken Sie mit der rechten Maustaste **auf Eingabeaufforderung,** und klicken **Sie auf Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="71f97-115">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="71f97-116">c.</span><span class="sxs-lookup"><span data-stu-id="71f97-116">c.</span></span> <span data-ttu-id="71f97-117">Geben Sie Administratoranmeldeinformationen ein, oder genehmigen Sie die Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="71f97-117">Enter administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="71f97-118">Navigieren Sie zum Windows Defender Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="71f97-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="71f97-119">Der Standardwert ist `C:\Program Files\Windows Defender`.</span><span class="sxs-lookup"><span data-stu-id="71f97-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="71f97-120">Geben Sie den folgenden Befehl ein, und drücken Sie dann die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="71f97-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="71f97-121">Es wird eine CAB-Datei generiert, die verschiedene Diagnoseprotokolle enthält.</span><span class="sxs-lookup"><span data-stu-id="71f97-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="71f97-122">Der Speicherort der Datei wird in der Ausgabe in der Eingabeaufforderung angegeben.</span><span class="sxs-lookup"><span data-stu-id="71f97-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="71f97-123">Standardmäßig ist der Speicherort `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="71f97-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="71f97-124">Kopieren Sie diese CAB-Dateien an einen Speicherort, auf den vom Microsoft-Support zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="71f97-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="71f97-125">Ein Beispiel könnte ein kennwortgeschützter OneDrive-Ordner sein, den Sie für uns freigeben können.</span><span class="sxs-lookup"><span data-stu-id="71f97-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="71f97-126">Senden Sie eine E-Mail mithilfe der E-Mail-Vorlage update <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">compliance</a>support, und füllen Sie die Vorlage mit den folgenden Informationen aus:</span><span class="sxs-lookup"><span data-stu-id="71f97-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="71f97-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71f97-127">See also</span></span>

- [<span data-ttu-id="71f97-128">Problembehandlung Windows Defender Microsoft Defender Antivirus-Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="71f97-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)