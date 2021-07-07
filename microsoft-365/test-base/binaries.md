---
title: Hochladen Anwendungsbinärdateien
description: Erste Schritte mit der Testbasis für M365
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
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322818"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a><span data-ttu-id="a8692-103">Schritt 3: Hochladen Ihrer Binärdateien, Abhängigkeiten und Skripts</span><span class="sxs-lookup"><span data-stu-id="a8692-103">Step 3: Upload your binaries, dependencies, and scripts</span></span>

<span data-ttu-id="a8692-104">Auf dieser Registerkarte laden Sie ein einzelnes ZIP-Paket hoch, das Ihre Binärdateien, Abhängigkeiten und Skripts enthält, die zum Ausführen Ihrer Testsuite verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8692-104">On this tab, you will upload a single zip package containing your binaries, dependencies and scripts used to run your test suite.</span></span>

## <a name="upload-package-zip-file"></a><span data-ttu-id="a8692-105">Hochladen Zip-Paketdatei</span><span class="sxs-lookup"><span data-stu-id="a8692-105">Upload package zip file</span></span>

![Hochladen Ihrer Binärdateien](Media/AddBinaries.png)

  - <span data-ttu-id="a8692-107">Hochgeladene Abhängigkeiten können Testframeworks, Skriptmodule oder Daten enthalten, auf die zum Ausführen Ihrer Anwendung oder von Testfällen zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a8692-107">Uploaded dependencies can include test frameworks, scripting engines or data that will be accessed to run your application or test cases.</span></span> <span data-ttu-id="a8692-108">Sie können z. B. Selenium und ein Webdriver-Installationsprogramm hochladen, um browserbasierte Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a8692-108">For example, you can upload Selenium and a webdriver installer to help run browser-based tests.</span></span>
  - <span data-ttu-id="a8692-109">Es empfiehlt sich, sicherzustellen, dass Ihre Skriptaktivitäten modular gehalten werden, d. h.</span><span class="sxs-lookup"><span data-stu-id="a8692-109">It is best practice to ensure your script activities are kept modular i.e.</span></span> 
    - <span data-ttu-id="a8692-110">Das ```Install``` Skript führt nur Installationsvorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="a8692-110">The ```Install``` script only performs install operations.</span></span>
    - <span data-ttu-id="a8692-111">Das ```Launch``` Skript startet nur die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a8692-111">The ```Launch``` script only launches the application.</span></span>
    - <span data-ttu-id="a8692-112">Das ```Close``` Skript schließt nur die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a8692-112">The ```Close``` script only closes the application.</span></span>
    - <span data-ttu-id="a8692-113">Das optionale ```Uninstall``` Skript deinstalliert nur die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a8692-113">The optional ```Uninstall``` script only uninstalls the application.</span></span>

<span data-ttu-id="a8692-114">**Derzeit unterstützt das Portal nur PowerShell-Skripts.**</span><span class="sxs-lookup"><span data-stu-id="a8692-114">**Currently, the portal only supports PowerShell scripts.**</span></span>


## <a name="next-steps"></a><span data-ttu-id="a8692-115">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a8692-115">Next steps</span></span> 

<span data-ttu-id="a8692-116">Fahren Sie mit dem nächsten Artikel fort, um zu Schritt 4: **Legen Sie Ihre Testaufgaben fest.**</span><span class="sxs-lookup"><span data-stu-id="a8692-116">Advance to the next article to go onto Step 4: **Set your Test Tasks**.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="a8692-117">Zurück</span><span class="sxs-lookup"><span data-stu-id="a8692-117">Go back</span></span>](uploadApplication.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="a8692-118">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="a8692-118">Next step</span></span>](testtask.md)

