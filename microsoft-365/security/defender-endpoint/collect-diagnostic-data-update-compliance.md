---
title: Sammeln von Diagnosedaten für updatecompliance und Windows Defender Microsoft Defender Antivirus
description: Verwenden Sie ein Tool zum Sammeln von Daten, um Probleme mit der Updatecompliance zu beheben, wenn Sie das Microsoft Defender Antivirus Assessment-Add-In verwenden.
keywords: Troubleshoot, error, fix, update compliance, oms, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 9fbe2b624bec6bbe17bcf6bc8d3f842ba1e43ad7
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903732"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a><span data-ttu-id="c9ca7-104">Sammeln von Diagnosedaten zur Updatecompliance für Microsoft Defender Antivirus Bewertung</span><span class="sxs-lookup"><span data-stu-id="c9ca7-104">Collect update compliance diagnostic data for Microsoft Defender Antivirus assessment</span></span>


<span data-ttu-id="c9ca7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c9ca7-105">**Applies to:**</span></span>

- [<span data-ttu-id="c9ca7-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c9ca7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c9ca7-107">In diesem Artikel wird beschrieben, wie Sie Diagnosedaten sammeln, die von Microsoft-Support- und -Entwicklungsteams zur Behandlung von Problemen verwendet werden können, die bei der Verwendung des Abschnitts Microsoft Defender Antivirus Bewertung im Updatecompliance-Add-In auftreten können.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender Antivirus Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="c9ca7-108">Bevor Sie diesen Vorgang durchführen, stellen Sie sicher, dass Sie [die Problembehandlung Microsoft Defender Antivirus Berichterstellung](troubleshoot-reporting.md)gelesen haben, alle erforderlichen Voraussetzungen erfüllt und alle anderen vorgeschlagenen Schritte zur Problembehandlung ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="c9ca7-109">Rufen Sie auf mindestens zwei Geräten, die keine Berichte erstellen oder in der Updatecompliance angezeigt werden, die .cab Diagnosedatei ab, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c9ca7-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="c9ca7-110">Öffnen Sie eine Version der Eingabeaufforderung auf Administratorebene wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c9ca7-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="c9ca7-111">a.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-111">a.</span></span> <span data-ttu-id="c9ca7-112">Öffnen Sie das **Startmenü.**</span><span class="sxs-lookup"><span data-stu-id="c9ca7-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="c9ca7-113">b.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-113">b.</span></span> <span data-ttu-id="c9ca7-114">Geben Sie **cmd ein.**</span><span class="sxs-lookup"><span data-stu-id="c9ca7-114">Type **cmd**.</span></span> <span data-ttu-id="c9ca7-115">Klicken Sie mit der rechten Maustaste auf **die Eingabeaufforderung,** und wählen Sie dann **als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-115">Right-click on **Command Prompt** and then select **Run as administrator**.</span></span>

    <span data-ttu-id="c9ca7-116">c.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-116">c.</span></span> <span data-ttu-id="c9ca7-117">Geben Sie Administratoranmeldeinformationen an, oder genehmigen Sie die Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-117">Specify administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="c9ca7-118">Navigieren Sie zum Windows Defender Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="c9ca7-119">Der Standardwert ist `C:\Program Files\Windows Defender`.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="c9ca7-120">Geben Sie den folgenden Befehl ein, und drücken Sie dann die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="c9ca7-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="c9ca7-121">Es wird eine .cab Datei generiert, die verschiedene Diagnoseprotokolle enthält.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="c9ca7-122">Der Speicherort der Datei wird in der Ausgabe in der Eingabeaufforderung angegeben.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="c9ca7-123">Standardmäßig lautet der Speicherort `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="c9ca7-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="c9ca7-124">Kopieren Sie diese .cab-Dateien an einen Speicherort, auf den der Microsoft-Support zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="c9ca7-125">Ein Beispiel kann ein kennwortgeschützter OneDrive Ordner sein, den Sie für uns freigeben können.</span><span class="sxs-lookup"><span data-stu-id="c9ca7-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="c9ca7-126">Senden Sie eine E-Mail mithilfe der <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">E-Mail-Vorlage zur Updatecomplianceunterstützung,</a>und füllen Sie die Vorlage mit den folgenden Informationen aus:</span><span class="sxs-lookup"><span data-stu-id="c9ca7-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">update compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="c9ca7-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9ca7-127">See also</span></span>

- [<span data-ttu-id="c9ca7-128">Problembehandlung bei Windows Defender Microsoft Defender Antivirus Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="c9ca7-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)