---
title: Arbeiten mit Microsoft Consulting Services
description: Vorbereitung und schritte für die Arbeit mit MCS zum Packen Ihrer Apps
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1441ca3305a5f3e5a83ddd5e1547812f08d7d96b
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445696"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="29d39-104">Arbeiten mit Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="29d39-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="29d39-105">Sie können sich mit Microsoft Consulting Services (MCS) in Verbindung setzen, um Ihre Apps für die Verwendung mit Microsoft Managed Desktop zu packen.</span><span class="sxs-lookup"><span data-stu-id="29d39-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="29d39-106">Um genaue Details zu erhalten, arbeiten Sie mit Ihrem Kontomitarbeiter zusammen, um MCS zu kontaktieren und Ihr spezifisches App-Packprojekt zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="29d39-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="29d39-107">Rollen und Zuständigkeiten</span><span class="sxs-lookup"><span data-stu-id="29d39-107">Roles and responsibilities</span></span>

<span data-ttu-id="29d39-108">Um mit mcS-App-Paketen zu arbeiten, **müssen Sie die folgenden Elemente bereitstellen:**</span><span class="sxs-lookup"><span data-stu-id="29d39-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="29d39-109">Die Quellinstallationsdateien (z. B. setup.exe oder MSI).</span><span class="sxs-lookup"><span data-stu-id="29d39-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="29d39-110">Die Installationsanweisungen, in der Details zum Aussehen der endgültigen Installation angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="29d39-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="29d39-111">Soll es beispielsweise eine Desktopverknüpfung zur App geben?</span><span class="sxs-lookup"><span data-stu-id="29d39-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="29d39-112">Wie sollte die Sichtbarkeit der App sein?</span><span class="sxs-lookup"><span data-stu-id="29d39-112">What should the app's visibility be?</span></span> <span data-ttu-id="29d39-113">Sollte die App eine Verbindung mit einem Server herstellen, und falls ja, welcher?</span><span class="sxs-lookup"><span data-stu-id="29d39-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="29d39-114">Weitere Informationen finden Sie in der [Anwendungs packanforderungsvorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="29d39-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="29d39-115">Sie müssen eigene Akzeptanztests durchführen, um sicherzustellen, dass die App so funktioniert, wie sie in Ihrer Umgebung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="29d39-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="29d39-116">**MCS kümmert sich um die folgenden Aktionen:**</span><span class="sxs-lookup"><span data-stu-id="29d39-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="29d39-117">Überprüfen, ob die App in der Microsoft Managed Desktop-Umgebung verboten oder eingeschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="29d39-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="29d39-118">Testen der Installation, des Startens und der Deinstallation der App, um die Kompatibilität mit Windows 10 sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="29d39-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="29d39-119">Wenn MCS ein Kompatibilitätsproblem entdeckt, wird die App zur Behebung an das [App Assure-Programm](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure) weitergebe.</span><span class="sxs-lookup"><span data-stu-id="29d39-119">If MCS discovers a compatibility issue, they will hand off the app to the [App Assure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure) program for remediation.</span></span>
- <span data-ttu-id="29d39-120">Packen Sie die App nach Ihrer Spezifikation, und testen Sie dann die App-Bereitstellung mithilfe von Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="29d39-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="29d39-121">Zeitplan für die App-Zustellung</span><span class="sxs-lookup"><span data-stu-id="29d39-121">App delivery schedule</span></span>

<span data-ttu-id="29d39-122">Starten Sie den Packvorgang, indem Sie die App-Informationen in das Microsoft Managed Desktop-Portal hochladen.</span><span class="sxs-lookup"><span data-stu-id="29d39-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="29d39-123">Das Packteam überprüft jeden Donnerstag neue Übermittlungen.</span><span class="sxs-lookup"><span data-stu-id="29d39-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="29d39-124">Nach überprüfung und Verpackung werden die verpackten Apps am folgenden Freitag zugestellt.</span><span class="sxs-lookup"><span data-stu-id="29d39-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="29d39-125">Bis zu fünf Apps pro Woche können zum Starten verpackt werden, aber der Dienst kann nach Ihren Anforderungen skaliert werden.</span><span class="sxs-lookup"><span data-stu-id="29d39-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![Kalender mit dem App-Zufluss an einem Donnerstag (dem 21. in diesem Beispiel), der Medienüberprüfung am nächsten Tag, dem Verpacken am folgenden Montag (dem 25.) und der App-Zustellung am folgenden Freitag (dem 29.)](../../media/MCS-cal.png)

<span data-ttu-id="29d39-127">Sie werden benachrichtigt, sobald die App zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="29d39-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="29d39-128">An diesem Punkt haben Sie 21 Tage Zeit, Um Akzeptanztests durchzuführen und die Arbeit im Microsoft Managed Desktop-Portal zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="29d39-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="29d39-129">Wenn Sie während der Annahmetests probleme mit der App feststellen, lehnen Sie die App im Microsoft Managed Desktop-Portal ab, und Sie werden per E-Mail mit einem MCS-Paketer verbunden, um das Problem zu verstehen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="29d39-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="29d39-130">Testen von Konten und Umgebung</span><span class="sxs-lookup"><span data-stu-id="29d39-130">Testing accounts and environment</span></span>

<span data-ttu-id="29d39-131">Damit das Paketteam die Migration zu Microsoft Intune abschließen kann, wird empfohlen, bestimmte Berechtigungen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="29d39-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="29d39-132">Zugriff auf die App-Bereitstellungsfunktionen von Microsoft Intune, damit der Paketer die App hinzufügen und zuweisen kann</span><span class="sxs-lookup"><span data-stu-id="29d39-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="29d39-133">Testen von Gruppen, Benutzerkonten und Lizenzen für die Paketierer, um die Apps testen zu können</span><span class="sxs-lookup"><span data-stu-id="29d39-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="29d39-134">MCS verwendet diese Berechtigungen, um die folgenden Aktionen durchzuführen:</span><span class="sxs-lookup"><span data-stu-id="29d39-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="29d39-135">Sicherstellen, dass die App auf einem virtuellen Computer funktioniert, der für Microsoft Managed Desktop konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="29d39-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="29d39-136">Hochladen der App in Microsoft Intune für die Bereitstellung für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="29d39-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="29d39-137">Ohne diese Berechtigungen kann MCS vorwärts gehen, die Anwendungen können jedoch nicht in Ihre Umgebung hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="29d39-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>
