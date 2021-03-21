---
title: Behandeln von AzCopy in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Behandeln von Fehlern für Azure AzCopy beim Laden von Nicht-Office 365-Daten zur Fehlerbehebung in Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919291"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="ee373-103">Behandeln von AzCopy in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ee373-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="ee373-104">Beim Laden von Nicht-Microsoft 365-Daten oder Dokumenten zur Fehlerbehebung in Advanced eDiscovery stellt die Benutzeroberfläche einen Azure AzCopy-Befehl bereit, der Parameter mit dem Speicherort der Dateien, die Sie hochladen möchten, und dem Azure-Speicherort enthält, in den die Dateien hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="ee373-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="ee373-105">Um Ihre Dokumente hochzuladen, kopieren Sie diesen Befehl und führen ihn dann in einer Eingabeaufforderung auf Dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="ee373-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="ee373-106">Der folgende Screenshot zeigt ein Beispiel für einen AzCopy-Befehl:</span><span class="sxs-lookup"><span data-stu-id="ee373-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Hochladen von Nicht-Microsoft 365-Dateien](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="ee373-108">Normalerweise funktioniert der bereitgestellte Befehl, wenn Sie ihn ausführen.</span><span class="sxs-lookup"><span data-stu-id="ee373-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="ee373-109">Es kann jedoch Fälle gibt, in denen der angezeigte Befehl nicht erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ee373-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="ee373-110">Hier sind einige mögliche Gründe.</span><span class="sxs-lookup"><span data-stu-id="ee373-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="ee373-111">Die unterstützte Version von AzCopy wird nicht auf dem lokalen Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ee373-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="ee373-112">Zu diesem Zeitpunkt müssen Sie AzCopy v8.1 verwenden, um Nicht-Microsoft 365-Daten in Advanced eDiscovery zu laden.</span><span class="sxs-lookup"><span data-stu-id="ee373-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="ee373-113">Der Befehl AzCopy, der auf  der Seite Dateien hochladen angezeigt wird, der im vorherigen Screenshot angezeigt wird, gibt einen Fehler zurück, wenn Sie AzCopy v8.1 nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee373-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="ee373-114">Informationen zur Installation dieser Version finden Sie [unter Übertragen von Daten mit azCopy v8.1 unter Windows](/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="ee373-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="ee373-115">AzCopy ist nicht auf dem lokalen Computer oder nicht am Standardspeicherort installiert</span><span class="sxs-lookup"><span data-stu-id="ee373-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="ee373-116">Wenn AzCopy nicht installiert oder an einem anderen Speicherort als dem Standardinstallationsspeicherort (d. h. ) installiert ist, wird möglicherweise der folgende Fehler angezeigt, wenn Sie den `%ProgramFiles(x86)%` Befehl AzCopy ausführen:</span><span class="sxs-lookup"><span data-stu-id="ee373-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="ee373-117">Das System kann den angegebenen Pfad nicht finden.</span><span class="sxs-lookup"><span data-stu-id="ee373-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="ee373-118">Wenn AzCopy nicht auf dem lokalen Computer installiert ist, finden Sie Installationsinformationen unter Übertragen von Daten mit [azCopy v8.1 unter Windows](/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="ee373-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="ee373-119">Stellen Sie sicher, dass sie am Standardspeicherort installiert wird.</span><span class="sxs-lookup"><span data-stu-id="ee373-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="ee373-120">Wenn AzCopy installiert ist, aber an einem anderen Speicherort als dem Standardspeicherort installiert ist, können Sie den Befehl kopieren, in eine Textdatei einfügen und dann den Pfad zum Speicherort ändern, an dem AzCopy installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ee373-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="ee373-121">Wenn sich Azcopy beispielsweise in befindet, können Sie den ersten Teil des Befehls in `%ProgramFiles%` `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` ändern.</span><span class="sxs-lookup"><span data-stu-id="ee373-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="ee373-122">Nachdem Sie diese Änderung geändert haben, kopieren Sie sie aus der Textdatei, und führen Sie sie dann als Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="ee373-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="ee373-123">Wenn AzCopy an einem anderen Speicherort als dem Standardinstallationsspeicherort installiert ist, sollten Sie es deinstallieren und dann erneut am Standardspeicherort installieren.</span><span class="sxs-lookup"><span data-stu-id="ee373-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="ee373-124">Dies wird dazu beitragen, dieses Problem in Zukunft zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="ee373-124">This will help prevent this issue in the future.</span></span>