---
title: Arbeiten mit Microsoft Consulting Services
description: Vorbereitung und Schritte zur Zusammenarbeit mit MCS zum Verpacken Ihrer Apps
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, apps, MCS, Packaging
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d2a6c09e1bcb84885e607d133c14e26e08e3c621
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530163"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="396d3-104">Arbeiten mit Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="396d3-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="396d3-105">Sie können sich mit Microsoft Consulting Services (MCS) beschäftigen, um Ihre apps für die Verwendung mit Microsoft Managed Desktop zu verpacken.</span><span class="sxs-lookup"><span data-stu-id="396d3-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="396d3-106">Um genaue Details zu erhalten, wenden Sie sich an Ihren Konto Vertreter, um Kontakt mit MCS aufzunehmen und Ihr spezielles App-Paket Projekt zu besprechen.</span><span class="sxs-lookup"><span data-stu-id="396d3-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="396d3-107">Rollen und Zuständigkeiten</span><span class="sxs-lookup"><span data-stu-id="396d3-107">Roles and responsibilities</span></span>

<span data-ttu-id="396d3-108">Um mit MCS App Packaging arbeiten zu können, **müssen Sie diese Elemente bereitstellen**:</span><span class="sxs-lookup"><span data-stu-id="396d3-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="396d3-109">Die Quellinstallationsdateien (beispielsweise setup.exe oder MSI).</span><span class="sxs-lookup"><span data-stu-id="396d3-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="396d3-110">Die Installationsanweisungen, in denen Details zum Aussehen der endgültigen Installation angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="396d3-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="396d3-111">Soll beispielsweise eine Desktopverknüpfung mit der app vorhanden sein?</span><span class="sxs-lookup"><span data-stu-id="396d3-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="396d3-112">Was sollte die APP-Sichtbarkeit sein?</span><span class="sxs-lookup"><span data-stu-id="396d3-112">What should the app's visibility be?</span></span> <span data-ttu-id="396d3-113">Sollte sich die APP mit einem Server verbinden und wenn ja, welche?</span><span class="sxs-lookup"><span data-stu-id="396d3-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="396d3-114">Ausführliche Informationen finden Sie in der [Vorlage "Application Packaging Request](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)".</span><span class="sxs-lookup"><span data-stu-id="396d3-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="396d3-115">Sie müssen ihre eigenen Akzeptanztests durchführen, um sicherzustellen, dass die APP so funktioniert, wie Sie Sie in Ihrer Umgebung benötigen.</span><span class="sxs-lookup"><span data-stu-id="396d3-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="396d3-116">**Diese Aktionen werden von MCS übernommen:**</span><span class="sxs-lookup"><span data-stu-id="396d3-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="396d3-117">Überprüfen, ob die app in der Microsoft Managed Desktop-Umgebung verboten oder eingeschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="396d3-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="396d3-118">Testen der Installation, des Starts und der Deinstallation der APP, um die Kompatibilität mit Windows 10 sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="396d3-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="396d3-119">Wenn MCS ein Kompatibilitätsproblem feststellt, wird die APP an das Programm für die Desktop-App zur Verfügung gestellt, um die Korrektur zu [gewährleisten](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) .</span><span class="sxs-lookup"><span data-stu-id="396d3-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="396d3-120">Verpacken der app in ihrer Spezifikation und Testen der APP-Bereitstellung mithilfe von Microsoft InTune.</span><span class="sxs-lookup"><span data-stu-id="396d3-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="396d3-121">Zeitplan für die APP-Zustellung</span><span class="sxs-lookup"><span data-stu-id="396d3-121">App delivery schedule</span></span>

<span data-ttu-id="396d3-122">Starten Sie den Verpackungsprozess, indem Sie die APP-Informationen in das Microsoft Managed Desktop Portal hochladen.</span><span class="sxs-lookup"><span data-stu-id="396d3-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="396d3-123">Das Packaging-Team prüft jeden Donnerstag neue Übermittlungen.</span><span class="sxs-lookup"><span data-stu-id="396d3-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="396d3-124">Nach Überprüfung und Verpackung werden die gepackten apps am nächsten Freitag ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="396d3-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="396d3-125">Es können bis zu fünf apps pro Woche gepackt werden, aber der Dienst kann entsprechend Ihren Anforderungen skaliert werden.</span><span class="sxs-lookup"><span data-stu-id="396d3-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![Kalender mit App-Zufluss an einem Donnerstag (dem 21. in diesem Beispiel), Medienüberprüfung am nächsten Tag, Verpacken am folgenden Montag (25.) und App-Zustellung am darauffolgenden Freitag (29.)](../../media/MCS-cal.png)

<span data-ttu-id="396d3-127">Sobald die APP zugestellt wurde, werden Sie benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="396d3-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="396d3-128">An diesem Ort haben Sie 21 Tage Zeit, um Akzeptanztests durchzuführen und sich bei der Arbeit im Microsoft Managed Desktop Portal abzumelden.</span><span class="sxs-lookup"><span data-stu-id="396d3-128">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="396d3-129">Wenn Sie während der Akzeptanztests ein Problem mit der APP entdecken, lehnen Sie die APP im Microsoft Managed Desktop Portal ab, und Sie werden über e-Mail mit einem MCS-paketor verbunden, um das Problem zu verstehen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="396d3-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="396d3-130">Testen von Konten und Umgebung</span><span class="sxs-lookup"><span data-stu-id="396d3-130">Testing accounts and environment</span></span>

<span data-ttu-id="396d3-131">Damit das Packaging-Team die Migration zu Microsoft InTune abgeschlossen hat, wird empfohlen, bestimmte Berechtigungen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="396d3-131">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="396d3-132">Zugriff auf die APP-Bereitstellungsfunktionen von Microsoft InTune für den Paket Besitzer zum Hinzufügen und Zuweisen der APP</span><span class="sxs-lookup"><span data-stu-id="396d3-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="396d3-133">Testgruppen, Benutzerkonten und Lizenzen für die Packager, um die Apps testen zu können</span><span class="sxs-lookup"><span data-stu-id="396d3-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="396d3-134">MCS verwendet diese Berechtigungen, um die folgenden Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="396d3-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="396d3-135">Sicherstellen, dass die APP auf dem für Microsoft Managed Desktop konfigurierten virtuellen Computer funktioniert</span><span class="sxs-lookup"><span data-stu-id="396d3-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="396d3-136">Hochladen der APP an Microsoft InTune für die Bereitstellung für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="396d3-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="396d3-137">Ohne diese Berechtigungen ist es für MCS möglich, sich vorwärts zu bewegen, aber die Anwendungen können nicht in Ihre Umgebung hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="396d3-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


