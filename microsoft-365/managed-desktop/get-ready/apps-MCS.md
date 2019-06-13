---
title: Arbeiten mit Microsoft Consulting Services
description: Vorbereitung und Schritte zur Zusammenarbeit mit MCS zum Verpacken Ihrer Apps
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, apps, MCS, Packaging
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 39a5102d045d9ed79b631a3b477bd1c72dea76de
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "34918726"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="7f91e-104">Arbeiten mit Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="7f91e-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="7f91e-105">Sie können sich mit Microsoft Consulting Services (MCS) beschäftigen, um Ihre apps für die Verwendung mit Microsoft Managed Desktop zu verpacken.</span><span class="sxs-lookup"><span data-stu-id="7f91e-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="7f91e-106">Um genaue Details zu erhalten, wenden Sie sich an Ihren Konto Vertreter, um Kontakt mit MCS aufzunehmen und Ihr spezielles App-Paket Projekt zu besprechen.</span><span class="sxs-lookup"><span data-stu-id="7f91e-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="7f91e-107">Rollen und Verantwortlichkeiten</span><span class="sxs-lookup"><span data-stu-id="7f91e-107">Roles and responsibilities</span></span>

<span data-ttu-id="7f91e-108">Um mit MCS App Packaging arbeiten zu können, **müssen Sie diese Elemente bereitstellen**:</span><span class="sxs-lookup"><span data-stu-id="7f91e-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="7f91e-109">Die Quellinstallationsdateien (beispielsweise Setup. exe oder. msi).</span><span class="sxs-lookup"><span data-stu-id="7f91e-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="7f91e-110">Die Installationsanweisungen, in denen Details zum Aussehen der endgültigen Installation angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7f91e-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="7f91e-111">Soll beispielsweise eine Desktopverknüpfung mit der app vorhanden sein?</span><span class="sxs-lookup"><span data-stu-id="7f91e-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="7f91e-112">Was sollte die APP-Sichtbarkeit sein?</span><span class="sxs-lookup"><span data-stu-id="7f91e-112">What should the app's visibility be?</span></span> <span data-ttu-id="7f91e-113">Sollte sich die APP mit einem Server verbinden und wenn ja, welche?</span><span class="sxs-lookup"><span data-stu-id="7f91e-113">Should the app connect to a server and if so, which one?</span></span> <!--For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx). -->
- <span data-ttu-id="7f91e-114">Sie müssen ihre eigenen Akzeptanztests durchführen, um sicherzustellen, dass die APP so funktioniert, wie Sie Sie in Ihrer Umgebung benötigen.</span><span class="sxs-lookup"><span data-stu-id="7f91e-114">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="7f91e-115">**Diese Aktionen werden von MCS übernommen:**</span><span class="sxs-lookup"><span data-stu-id="7f91e-115">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="7f91e-116">Überprüfen, ob die app in der Microsoft Managed Desktop-Umgebung verboten oder eingeschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="7f91e-116">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="7f91e-117">Testen der Installation, des Starts und der Deinstallation der APP, um die Kompatibilität mit Windows 10 sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="7f91e-117">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="7f91e-118">Wenn MCS ein Kompatibilitätsproblem feststellt, wird die APP an das Programm für die Desktop-App zur Verfügung gestellt, um die Korrektur zu [gewährleisten](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) .</span><span class="sxs-lookup"><span data-stu-id="7f91e-118">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="7f91e-119">Verpacken der app in ihrer Spezifikation und Testen der APP-Bereitstellung mithilfe von Microsoft InTune.</span><span class="sxs-lookup"><span data-stu-id="7f91e-119">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="7f91e-120">Zeitplan für die APP-Zustellung</span><span class="sxs-lookup"><span data-stu-id="7f91e-120">App delivery schedule</span></span>

<span data-ttu-id="7f91e-121">Starten Sie den Verpackungsprozess, indem Sie die APP-Informationen in das Microsoft Managed Desktop Portal hochladen.</span><span class="sxs-lookup"><span data-stu-id="7f91e-121">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="7f91e-122">Das Packaging-Team prüft jeden Donnerstag neue Übermittlungen.</span><span class="sxs-lookup"><span data-stu-id="7f91e-122">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="7f91e-123">Nach Überprüfung und Verpackung werden die gepackten apps am nächsten Freitag ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="7f91e-123">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="7f91e-124">Es können bis zu fünf apps pro Woche gepackt werden, aber der Dienst kann entsprechend Ihren Anforderungen skaliert werden.</span><span class="sxs-lookup"><span data-stu-id="7f91e-124">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![Kalender mit App-Review, Verpackung und Zustellungsdatum](images/MCS-cal.png)

<span data-ttu-id="7f91e-126">Sobald die APP zugestellt wurde, werden Sie benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="7f91e-126">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="7f91e-127">An diesem Ort haben Sie 21 Tage Zeit, um Akzeptanztests durchzuführen und sich bei der Arbeit im Microsoft Managed Desktop Portal abzumelden.</span><span class="sxs-lookup"><span data-stu-id="7f91e-127">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="7f91e-128">Wenn Sie während der Akzeptanztests ein Problem mit der APP entdecken, lehnen Sie die APP im Microsoft Managed Desktop Portal ab, und Sie werden über e-Mail mit einem MCS-paketor verbunden, um das Problem zu verstehen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="7f91e-128">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="7f91e-129">Testen von Konten und Umgebung</span><span class="sxs-lookup"><span data-stu-id="7f91e-129">Testing accounts and environment</span></span>

<span data-ttu-id="7f91e-130">Damit das Packaging-Team die Migration zu Microsoft InTune abgeschlossen hat, wird empfohlen, bestimmte Berechtigungen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="7f91e-130">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="7f91e-131">Zugriff auf die APP-Bereitstellungsfunktionen von Microsoft InTune für den Paket Besitzer zum Hinzufügen und Zuweisen der APP</span><span class="sxs-lookup"><span data-stu-id="7f91e-131">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="7f91e-132">Testgruppen, Benutzerkonten und Lizenzen für die Packager, um die Apps testen zu können</span><span class="sxs-lookup"><span data-stu-id="7f91e-132">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="7f91e-133">MCS verwendet diese Berechtigungen, um die folgenden Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="7f91e-133">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="7f91e-134">Sicherstellen, dass die APP auf dem für Microsoft Managed Desktop konfigurierten virtuellen Computer funktioniert</span><span class="sxs-lookup"><span data-stu-id="7f91e-134">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="7f91e-135">Hochladen der APP an Microsoft InTune für die Bereitstellung für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="7f91e-135">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="7f91e-136">Ohne diese Berechtigungen ist es für MCS möglich, sich vorwärts zu bewegen, aber die Anwendungen können nicht in Ihre Umgebung hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="7f91e-136">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


