---
title: Arbeiten mit Microsoft Consulting Services
description: Vorbereitung und Schritte zur Zusammenarbeit mit MCS zum Verpacken Ihrer Apps
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
ms.openlocfilehash: 7a967f5e4b2678b55ed87f2eaa68590703c55805
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840886"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="b6684-104">Arbeiten mit Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="b6684-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="b6684-105">Sie können mit Microsoft Consulting Services (MCS) zusammenarbeiten, um Ihre Apps für die Verwendung mit Microsoft Managed Desktop zu verpacken.</span><span class="sxs-lookup"><span data-stu-id="b6684-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="b6684-106">Wenden Sie sich an MCS, um genaue Details zu erhalten, und wenden Sie sich an Ihren Kontomitarbeiter, um Ihr spezifisches App-Paketprojekt zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="b6684-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="b6684-107">Rollen und Zuständigkeiten</span><span class="sxs-lookup"><span data-stu-id="b6684-107">Roles and responsibilities</span></span>

<span data-ttu-id="b6684-108">Zum Arbeiten mit MCS-App-Paketen **müssen Sie die folgenden Elemente bereitstellen:**</span><span class="sxs-lookup"><span data-stu-id="b6684-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="b6684-109">Die Quellinstallationsprogrammdateien (z. B. setup.exe oder .msi).</span><span class="sxs-lookup"><span data-stu-id="b6684-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="b6684-110">In den Installationsanweisungen werden Details zum Aussehen der endgültigen Installation angegeben.</span><span class="sxs-lookup"><span data-stu-id="b6684-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="b6684-111">Sollte es beispielsweise eine Desktopverknüpfung zur App geben?</span><span class="sxs-lookup"><span data-stu-id="b6684-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="b6684-112">Wie sollte die Sichtbarkeit der App sein?</span><span class="sxs-lookup"><span data-stu-id="b6684-112">What should the app's visibility be?</span></span> <span data-ttu-id="b6684-113">Sollte die App eine Verbindung mit einem Server herstellen und wenn ja, welcher?</span><span class="sxs-lookup"><span data-stu-id="b6684-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="b6684-114">Ausführliche Informationen finden Sie in der [Anforderungsvorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)zum Packen von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b6684-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="b6684-115">Sie müssen Ihre eigenen Akzeptanztests durchführen, um zu überprüfen, ob die App in Ihrer Umgebung wie erforderlich funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b6684-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="b6684-116">**MCS übernimmt die folgenden Aktionen:**</span><span class="sxs-lookup"><span data-stu-id="b6684-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="b6684-117">Überprüfen, ob die App in der Microsoft Managed Desktop-Umgebung verboten oder eingeschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="b6684-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="b6684-118">Testen der Installation, des Startes und der Deinstallation der App, um die Kompatibilität mit Windows 10 sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="b6684-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="b6684-119">Wenn MCS ein Kompatibilitätsproblem feststellt, wird die App zur Behebung an das [App Assure-Programm](/fasttrack/products-and-capabilities#app-assure) übergeben.</span><span class="sxs-lookup"><span data-stu-id="b6684-119">If MCS discovers a compatibility issue, they will hand off the app to the [App Assure](/fasttrack/products-and-capabilities#app-assure) program for remediation.</span></span>
- <span data-ttu-id="b6684-120">Packen Sie die App nach Ihren Spezifikationen, und testen Sie dann die App-Bereitstellung mithilfe von Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="b6684-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="b6684-121">Zeitplan für die App-Übermittlung</span><span class="sxs-lookup"><span data-stu-id="b6684-121">App delivery schedule</span></span>

<span data-ttu-id="b6684-122">Starten Sie den Verpackungsvorgang, indem Sie die App-Informationen in das Microsoft Managed Desktop-Portal hochladen.</span><span class="sxs-lookup"><span data-stu-id="b6684-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="b6684-123">Das Verpackungsteam überprüft jeden Donnerstag neue Übermittlungen.</span><span class="sxs-lookup"><span data-stu-id="b6684-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="b6684-124">Nach der Überprüfung und Verpackung werden die verpackten Apps am folgenden Freitag übermittelt.</span><span class="sxs-lookup"><span data-stu-id="b6684-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="b6684-125">Bis zu fünf Apps pro Woche können für den Start gepackt werden, aber der Dienst kann entsprechend Ihren Anforderungen skaliert werden.</span><span class="sxs-lookup"><span data-stu-id="b6684-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![Kalender mit App-Zufluss an einem Donnerstag (21. in diesem Beispiel), Medienüberprüfung am nächsten Tag, Verpacken am folgenden Montag (25.) und App-Zustellung am nachfolgenden Freitag (29.)](../../media/MCS-cal.png)

<span data-ttu-id="b6684-127">Sie werden benachrichtigt, nachdem die App übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="b6684-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="b6684-128">An diesem Punkt haben Sie 21 Tage Zeit, um Akzeptanztests durchzuführen und die Arbeit im Microsoft Managed Desktop Portal zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="b6684-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="b6684-129">Wenn Sie während der Annahmetests ein Problem mit der App feststellen, weisen Sie die App im Microsoft Managed Desktop-Portal zurück, und Sie werden per E-Mail mit einem MCS-Packager verbunden, um das Problem zu verstehen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b6684-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="b6684-130">Testen von Konten und Umgebung</span><span class="sxs-lookup"><span data-stu-id="b6684-130">Testing accounts and environment</span></span>

<span data-ttu-id="b6684-131">Damit das Verpackungsteam die Migration zu Microsoft Intune abschließen kann, empfehlen wir Ihnen, bestimmte Berechtigungen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="b6684-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>

- <span data-ttu-id="b6684-132">Zugriff auf die App-Bereitstellungsfunktionen Microsoft Intune für den Packager zum Hinzufügen und Zuweisen der App</span><span class="sxs-lookup"><span data-stu-id="b6684-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span>
- <span data-ttu-id="b6684-133">Testen von Gruppen, Benutzerkonten und Lizenzen für die Packager, um die Apps testen zu können</span><span class="sxs-lookup"><span data-stu-id="b6684-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="b6684-134">MCS verwendet diese Berechtigungen, um die folgenden Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="b6684-134">MCS will use those permissions to perform the following actions:</span></span>

- <span data-ttu-id="b6684-135">Sicherstellen, dass die App auf einem virtuellen Computer funktioniert, der für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="b6684-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
- <span data-ttu-id="b6684-136">Hochladen der App in Microsoft Intune für die Bereitstellung für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="b6684-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="b6684-137">Ohne diese Berechtigungen ist es möglich, dass MCS vorwärts geht, aber sie können die Anwendungen nicht in Ihre Umgebung hochladen.</span><span class="sxs-lookup"><span data-stu-id="b6684-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>
