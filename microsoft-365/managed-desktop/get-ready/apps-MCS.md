---
title: Arbeiten mit Microsoft Consulting Services
description: Vorbereitung und die folgenden Schritte für die Arbeit mit MCS zum Packen Ihrer Apps
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, Apps, MCS, Verpacken
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841423"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="a37b2-104">Arbeiten mit Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="a37b2-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="a37b2-105">Sie können sich mit Microsoft Consulting Services (MCS) in Verbindung setzen, um Ihre Apps für die Verwendung mit Microsoft Managed Desktop zu packen.</span><span class="sxs-lookup"><span data-stu-id="a37b2-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="a37b2-106">Wenden Sie sich an Ihren Kontomitarbeiter, um mcS zu kontaktieren und den Umfang Ihres spezifischen App-Paketprojekts zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="a37b2-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="a37b2-107">Rollen und Zuständigkeiten</span><span class="sxs-lookup"><span data-stu-id="a37b2-107">Roles and responsibilities</span></span>

<span data-ttu-id="a37b2-108">Um mit MCS-App-Paketen arbeiten zu **können, müssen Sie die folgenden Elemente bereitstellen:**</span><span class="sxs-lookup"><span data-stu-id="a37b2-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="a37b2-109">Die Quellinstallationsdateien (z. B. setup.exe oder MSI).</span><span class="sxs-lookup"><span data-stu-id="a37b2-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="a37b2-110">Die Installationsanweisungen, in der Details zum Aussehen der endgültigen Installation angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a37b2-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="a37b2-111">Sollte es beispielsweise eine Desktopverknüpfung für die App geben?</span><span class="sxs-lookup"><span data-stu-id="a37b2-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="a37b2-112">Wie sollte die Sichtbarkeit der App sein?</span><span class="sxs-lookup"><span data-stu-id="a37b2-112">What should the app's visibility be?</span></span> <span data-ttu-id="a37b2-113">Sollte die App eine Verbindung mit einem Server herstellen, und wenn ja, welcher?</span><span class="sxs-lookup"><span data-stu-id="a37b2-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="a37b2-114">Weitere Informationen finden Sie in der [Anforderungsvorlage zum Packen von Anwendungen.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)</span><span class="sxs-lookup"><span data-stu-id="a37b2-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="a37b2-115">Sie müssen eigene Akzeptanztests durchführen, um zu überprüfen, ob die App so funktioniert, wie sie in Ihrer Umgebung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="a37b2-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="a37b2-116">**MCS kümmert sich um die folgenden Aktionen:**</span><span class="sxs-lookup"><span data-stu-id="a37b2-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="a37b2-117">Überprüfen, ob die App in der Microsoft Managed Desktop-Umgebung verboten oder eingeschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="a37b2-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="a37b2-118">Testen der Installation, des Startes und der Deinstallation der App, um die Kompatibilität mit Windows 10 sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="a37b2-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="a37b2-119">Wenn MCS ein Kompatibilitätsproblem entdeckt, wird die App zur Problembehebung an das [Desktop App Assure-Programm](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) übergabet.</span><span class="sxs-lookup"><span data-stu-id="a37b2-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="a37b2-120">Packen der App nach Ihrer Spezifikation und anschließendes Testen der App-Bereitstellung mithilfe von Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="a37b2-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="a37b2-121">Zeitplan für die App-Übermittlung</span><span class="sxs-lookup"><span data-stu-id="a37b2-121">App delivery schedule</span></span>

<span data-ttu-id="a37b2-122">Starten Sie den Verpackungsprozess, indem Sie die App-Informationen in das Microsoft Managed Desktop-Portal hochladen.</span><span class="sxs-lookup"><span data-stu-id="a37b2-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="a37b2-123">Das Verpackungsteam überprüft jeden Donnerstag neue Übermittlungen.</span><span class="sxs-lookup"><span data-stu-id="a37b2-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="a37b2-124">Nach überprüfung und Verpackung werden die verpackten Apps am folgenden Freitag zugestellt.</span><span class="sxs-lookup"><span data-stu-id="a37b2-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="a37b2-125">Bis zu fünf Apps pro Woche können gepackt werden, um zu starten, aber der Dienst kann an Ihre Anforderungen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="a37b2-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![kalender showing app inflow on a Thursday (the 21st in this example), media validation the next day, packaging on the following Monday (the 25th), and app delivery on the subsequent Friday (the 29th)](../../media/MCS-cal.png)

<span data-ttu-id="a37b2-127">Sie werden benachrichtigt, nachdem die App zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a37b2-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="a37b2-128">An diesem Punkt haben Sie 21 Tage Zeit, um Akzeptanztests durchzuführen und die Arbeit im Microsoft Managed Desktop Portal zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="a37b2-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="a37b2-129">Wenn Sie während der Akzeptanztests probleme mit der App feststellen, lehnen Sie die App im Microsoft Managed Desktop-Portal ab, und Sie werden per E-Mail mit einem MCS-Packager verbunden, um das Problem zu verstehen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="a37b2-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="a37b2-130">Testen von Konten und Umgebungen</span><span class="sxs-lookup"><span data-stu-id="a37b2-130">Testing accounts and environment</span></span>

<span data-ttu-id="a37b2-131">Damit das Paketteam die Migration zu Microsoft Intune abschließen kann, sollten Sie bestimmte Berechtigungen bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="a37b2-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="a37b2-132">Zugriff auf die App-Bereitstellungsfunktionen von Microsoft Intune, damit der Packager die App hinzufügen und zuweisen kann</span><span class="sxs-lookup"><span data-stu-id="a37b2-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="a37b2-133">Testgruppen, Benutzerkonten und Lizenzen für die Paketer, um die Apps testen zu können</span><span class="sxs-lookup"><span data-stu-id="a37b2-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="a37b2-134">MCS verwendet diese Berechtigungen, um die folgenden Aktionen durchzuführen:</span><span class="sxs-lookup"><span data-stu-id="a37b2-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="a37b2-135">Sicherstellen, dass die App auf einem virtuellen Computer funktioniert, der für Microsoft Managed Desktop konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="a37b2-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="a37b2-136">Hochladen der App in Microsoft Intune für die Bereitstellung für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="a37b2-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="a37b2-137">Ohne diese Berechtigungen kann MCS vorankommen, die Anwendungen können jedoch nicht in Ihre Umgebung hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="a37b2-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


