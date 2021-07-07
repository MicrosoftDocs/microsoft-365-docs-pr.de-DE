---
title: Funktionstests auf der Testbasis
description: Details zum Testen Ihrer Anwendung mit Ihren vorhandenen automatisierten Funktionstests
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322848"
---
# <a name="functional-testing"></a><span data-ttu-id="5c039-103">Funktionstests</span><span class="sxs-lookup"><span data-stu-id="5c039-103">Functional testing</span></span>

<span data-ttu-id="5c039-104">Als Softwareanbieter können Sie jetzt benutzerdefinierte Funktionstests mithilfe des Testframeworks Ihrer Wahl durchführen – über das Self-Serve Test Base für M365-Portal.</span><span class="sxs-lookup"><span data-stu-id="5c039-104">As a software vendor, you can now perform custom functional tests, using the test framework of your choice - via the self-serve Test Base for M365 portal.</span></span> 

<span data-ttu-id="5c039-105">Als wir den Dienst zum ersten Mal gestartet haben, haben wir die Out-of-Box-Tests angeboten, bei denen es sich um eine vordefinierte Gruppe von Tests handelt, die durch standardisierte Skripts gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="5c039-105">When we initially launched the service, we offered the Out-of-box tests, which is a pre-defined set of tests driven through standardized scripting.</span></span> <span data-ttu-id="5c039-106">Dies konnte jedoch für viele unabhängige Softwareanbieter (Independent Software Vendors, ISVs) keine vollständige Testabdeckung erzielen.</span><span class="sxs-lookup"><span data-stu-id="5c039-106">This, however, could not achieve full test coverage for many Independent Software Vendors (ISVs).</span></span> 

<span data-ttu-id="5c039-107">Daher bieten wir als Reaktion auf Ihr Feedback unseren ISVs die Möglichkeit, automatisierte Funktionstests hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="5c039-107">Hence, in response to your feedback, we are providing our ISVs with the ability to upload automated functional tests.</span></span>

<span data-ttu-id="5c039-108">Führen Sie die folgenden Schritte aus, um dieses Feature zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="5c039-108">To use this feature, follow the steps below:</span></span>

1. <span data-ttu-id="5c039-109">Hochladen Sie Ihre Dateien (Binärdateien, Abhängigkeiten und Skripts) als einzelnes .zip-Paket.</span><span class="sxs-lookup"><span data-stu-id="5c039-109">Upload your files (binaries, dependencies and scripts) as a single .zip package.</span></span>
2. <span data-ttu-id="5c039-110">Wählen Sie aus, ob Sie die virtuellen Testcomputer (VMs) an verschiedenen Ausführungspunkten neu starten möchten.</span><span class="sxs-lookup"><span data-stu-id="5c039-110">Choose if you want to reboot the test Virtual Machines (VMs) at various points of execution.</span></span>
3. <span data-ttu-id="5c039-111">Verwalten sie die verfügbaren Optionen für Ihre Skripts.</span><span class="sxs-lookup"><span data-stu-id="5c039-111">Manage available options for your scripts.</span></span>
4. <span data-ttu-id="5c039-112">Wählen Sie aus, wann das Windows Update während der Ausführung auf dem virtuellen Computer angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c039-112">Choose when to apply the Windows update on the VM during execution.</span></span>

<span data-ttu-id="5c039-113">Detaillierte Beschreibungen der obigen Schritte sind unten hervorgehoben:</span><span class="sxs-lookup"><span data-stu-id="5c039-113">Detailed descriptions of the above steps are highlighted below:</span></span>

<span data-ttu-id="5c039-114">**Hochladen eines Funktionstestpakets**</span><span class="sxs-lookup"><span data-stu-id="5c039-114">**Upload a functional test package**</span></span>

<span data-ttu-id="5c039-115">To get started, navigate to the Hochladen page, select Hochladen new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure.</span><span class="sxs-lookup"><span data-stu-id="5c039-115">To get started, navigate to the Upload page, select Upload new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure.</span></span> <span data-ttu-id="5c039-116">Von dort aus:</span><span class="sxs-lookup"><span data-stu-id="5c039-116">From there:</span></span>

<span data-ttu-id="5c039-117">Registerkarte 1– Geben Sie grundlegende Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="5c039-117">Tab 1 - Enter basic information.</span></span> <span data-ttu-id="5c039-118">Geben Sie den Namen und die Version Ihrer Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="5c039-118">Provide the name and version of your application.</span></span> <span data-ttu-id="5c039-119">Wählen Sie in der Testoption Typ die Option ```Functional tests``` aus.</span><span class="sxs-lookup"><span data-stu-id="5c039-119">In the Type of test option, select ```Functional tests```.</span></span> 

<span data-ttu-id="5c039-120">*Beachten Sie, dass die Out-of-Box (OOB)-Option standardmäßig erforderlich ist.*</span><span class="sxs-lookup"><span data-stu-id="5c039-120">*Note that the Out-of-Box (OOB) option is required by default.*</span></span>


![Wählen Sie die Registerkarte "Funktionale Tests" aus.](Media/functional_testing_tab1.png)

<span data-ttu-id="5c039-122">Registerkarte 2 – Hochladen die Komponenten Ihres Pakets, indem Sie eine ZIP-Datei mit Ihrem gesamten Test hochladen (Binärdateien, Abhängigkeiten, Skripts usw.).</span><span class="sxs-lookup"><span data-stu-id="5c039-122">Tab 2 - Upload the components of your package by uploading a zip file with your entire test (binaries, dependencies, scripts etc).</span></span> 

<span data-ttu-id="5c039-123">Weitere Informationen finden Sie unter aka.ms/usl-package-outline.</span><span class="sxs-lookup"><span data-stu-id="5c039-123">See aka.ms/usl-package-outline for details.</span></span> <span data-ttu-id="5c039-124">(Hinweis: Sowohl die out-of-Box-Testskripts als auch die Funktionalen Testinhalte sollten in derselben ZIP-Datei platziert werden.)</span><span class="sxs-lookup"><span data-stu-id="5c039-124">(Note: Both the Out-of-Box test scripts and the Functional test contents should be placed into the same zip file).</span></span> <span data-ttu-id="5c039-125">Derzeit ist die Dateigröße auf 2 GB beschränkt.</span><span class="sxs-lookup"><span data-stu-id="5c039-125">Currently, the file size is limited to 2GB.</span></span>

<span data-ttu-id="5c039-126">Registerkarte 3 – Konfigurieren sie die out-of-Box- und funktionalen Testaufgaben.</span><span class="sxs-lookup"><span data-stu-id="5c039-126">Tab 3 - Configure the Out-of-Box and Functional test tasks.</span></span> <span data-ttu-id="5c039-127">Wählen Sie hier die Pfade zu den PowerShell-Skripts aus, die Ihre Anwendung (für Out-of-Box) installieren, starten, schließen und deinstallieren, sowie die Pfade zu allen benutzerdefinierten Skripts, um Ihren Funktionstest durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="5c039-127">Here, choose the path(s) to the PowerShell scripts that will install, launch, close, and uninstall your application (for Out-of-Box) as well as the path(s) to all your custom scripts to perform your functional test.</span></span> <span data-ttu-id="5c039-128">**(Hinweis: Ein Skript zum Deinstallieren Der Anwendung ist optional).**</span><span class="sxs-lookup"><span data-stu-id="5c039-128">**(Note: A script to uninstall your application is optional).**</span></span>

<span data-ttu-id="5c039-129">Derzeit können Sie zwischen 1 und 8 Skripts für Ihre Funktionstests hochladen.</span><span class="sxs-lookup"><span data-stu-id="5c039-129">Currently, you can upload between 1 and 8 scripts for your functional tests.</span></span> <span data-ttu-id="5c039-130">(Kommentieren Sie diesen Beitrag bitte, wenn Sie weitere Skripts benötigen!)</span><span class="sxs-lookup"><span data-stu-id="5c039-130">(Kindly comment on this post if you need more scripts!)</span></span>

![Hochladen bis zu 8 Skripts mit Funktionstests](Media/functional_testing_tab3.png)

<span data-ttu-id="5c039-132">(Optional) Konfigurieren Sie einen Neustart nach der Installation.</span><span class="sxs-lookup"><span data-stu-id="5c039-132">(Optional) Configure a restart after installation.</span></span> <span data-ttu-id="5c039-133">Einige Anwendungen erfordern einen Neustart nach der Installation.</span><span class="sxs-lookup"><span data-stu-id="5c039-133">Some applications require a restart after installation.</span></span> 

<span data-ttu-id="5c039-134">Wählen Sie ```Reboot After Execution``` auf der Registerkarte "Aufgaben" das spezifische Skript aus, wenn nach der Ausführung dieses Skripts ein Neustart durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c039-134">Select ```Reboot After Execution``` for the specific Script in the Tasks tab if you would like a restart to be conducted after the execution of that script.</span></span>

<span data-ttu-id="5c039-135">Registerkarte 4 – Wählen Sie aus, wann das Windows Update installiert wird: Die Anwendung des Windows Updatepatches wird vor einem beliebigen Skript Ihrer Wahl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5c039-135">Tab 4 - Choose when the Windows update gets installed: The application of the Windows Update patch is done before any script of your choice.</span></span> <span data-ttu-id="5c039-136">Es wird empfohlen, nach der Installation der Anwendung ein Windows Update zu installieren, um ihre anwendungsbezogenen Anwendungsszenarien imitieren zu können.</span><span class="sxs-lookup"><span data-stu-id="5c039-136">It is recommended that you install a Windows update after the application's installation to closely mimic your real-world application use scenarios.</span></span>

![Das Windows Update kann nach einem bestimmten Skript installiert werden.](Media/functional_testing_tab4.png)

<span data-ttu-id="5c039-138">Registerkarte 5 – Überprüfen und erstellen Sie das Paket.</span><span class="sxs-lookup"><span data-stu-id="5c039-138">Tab 5 - Review and create the package.</span></span> <span data-ttu-id="5c039-139">Nachdem Sie die oben aufgeführten Schritte ausgeführt haben, wählen Sie ```Create``` aus, um den Uploadvorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5c039-139">Once you have completed the steps listed above, select ```Create``` to finish the uploading process.</span></span>

<span data-ttu-id="5c039-140">Nachdem Das Paket erstellt wurde, können Sie den Überprüfungsstatus Ihres Pakets überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5c039-140">Once your package has been created, you can check the verification status of your package.</span></span>

<span data-ttu-id="5c039-141">Wir führen einen ersten Test aus, um Ihre Anwendung zu installieren, zu starten, zu schließen und zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="5c039-141">We run an initial test to install, launch, close, and uninstall your application.</span></span> <span data-ttu-id="5c039-142">Dadurch können wir überprüfen, ob Ihr Paket fehlerfrei auf unserem Dienst installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5c039-142">This allows us to verify that your package can install on our service error-free.</span></span>

<span data-ttu-id="5c039-143">Der Überprüfungsprozess kann bis zu 24 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="5c039-143">The verification process could take up to 24 hours.</span></span> <span data-ttu-id="5c039-144">Sobald die Überprüfung abgeschlossen ist, können Sie den Status im ```Manage packages``` Menü sehen. Dies wäre einer von zwei Einträgen:</span><span class="sxs-lookup"><span data-stu-id="5c039-144">Once verification is complete, you can see the status in the ```Manage packages``` menu, which would be one of two entries:</span></span>

1. <span data-ttu-id="5c039-145">Die Überprüfung ist erfolgreich: Das Paket wird automatisch mit Vorabversionen Windows Updates für die ausgewählten Betriebssystembuilds getestet.</span><span class="sxs-lookup"><span data-stu-id="5c039-145">Verification succeeds: The package will be automatically tested against pre-release Windows updates for the OS builds you selected.</span></span>
<span data-ttu-id="5c039-146">oder</span><span class="sxs-lookup"><span data-stu-id="5c039-146">or</span></span>
2. <span data-ttu-id="5c039-147">Überprüfung schlägt fehl: Sie müssen die Gründe für den Fehler untersuchen, das Problem beheben und Ihr Paket erneut hochladen.</span><span class="sxs-lookup"><span data-stu-id="5c039-147">Verification fails: You will need to investigate the reasons for the failure, fix the issue, and re-upload your package.</span></span>

<span data-ttu-id="5c039-148">Sie werden auch über das Benachrichtigungssymbol im Azure-Portal über beide Ergebnisse benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="5c039-148">You will also be notified of either outcome via the notification icon in the Azure portal.</span></span>
