---
title: Isoliertes Team für ein streng geheimes Projekt der Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Zusammenfassung: Hier erfahren Sie, wie Contoso ein Team mit Sicherheitsisolation für ein streng geheimes Projekt verwendet, um eine neue Produkt-und Dienst Suite zu entwickeln.'
ms.openlocfilehash: f7b38a7ef43cdb50b46f3e37f855f490dc32cfdf
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521625"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="a1da1-103">Isoliertes Team für ein streng geheimes Projekt der Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="a1da1-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="a1da1-104">Nach einem externen Geschäftsführer ordnete der CEO von Contoso die Entwicklung einer neuen Produkt-und Dienst Suite an, die die Gewinne von Contoso in den nächsten fünf Jahren verdoppeln könnte.</span><span class="sxs-lookup"><span data-stu-id="a1da1-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="a1da1-105">Das streng geheime Projekt zur Entwicklung des Geschäfts-, Ingenieur-und Marktplans wurde mit dem Namen **Project 2X** und den wichtigsten Mitarbeitern im gesamten Unternehmen rekrutiert.</span><span class="sxs-lookup"><span data-stu-id="a1da1-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="a1da1-106">Die Zeitrahmen für Forschung und Entwicklung waren eng, was bedeutete, dass die Zusammenarbeit effizient sein und für sichere Besprechungen, laufende Unterhaltungen und Dateispeicherung sorgen musste.</span><span class="sxs-lookup"><span data-stu-id="a1da1-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="a1da1-107">Die daraus resultierenden Lieferumfänge für Project 2X Warengeschäfts Pläne, Produkt-und Engineering-Spezifikationen sowie Marketingmaterialien und-Zeitpläne in Form von Word-, Excel-und PowerPoint-Dateien.</span><span class="sxs-lookup"><span data-stu-id="a1da1-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="a1da1-108">Der Zugriff auf diese Dateien erfolgte aufgrund Ihrer sensiblen Eigenschaften wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a1da1-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="a1da1-109">Beschränkt auf Project 2X-Teammitglieder.</span><span class="sxs-lookup"><span data-stu-id="a1da1-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="a1da1-110">Verschlüsselt und mit Berechtigungen geschützt, um den Zugriff nur für Project 2X-Teammitglieder zu gewähren, auch wenn die Dateien außerhalb der gesicherten Ordner verteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="a1da1-110">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="a1da1-111">Contoso-IT-Mitarbeiter haben ein [Team mit Sicherheitsisolierung](secure-teams-security-isolation.md) für Project 2X und diese Schritte verwendet.</span><span class="sxs-lookup"><span data-stu-id="a1da1-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="a1da1-112">Schritt 1: Erstellen eines privaten Teams</span><span class="sxs-lookup"><span data-stu-id="a1da1-112">Step 1: Created a private team</span></span>

<span data-ttu-id="a1da1-113">Um zunächst den Zugriff auf die zugrunde liegende SharePoint-Website für das Team zu schützen, haben die IT-Administratoren von Contoso die [empfohlenen SharePoint-Zugriffsrichtlinien](../enterprise/sharepoint-file-access-policies.md)konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a1da1-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="a1da1-114">Als nächstes hat ein IT-Administrator von Contoso ein neues privates Team namens "Project 2X" erstellt und die Benutzerkonten von Project 2X-Mitarbeitern als Mitglieder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a1da1-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="a1da1-115">Informationen zu den Konfigurationsdetails finden Sie unter [Erstellen eines privaten Teams](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="a1da1-115">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="a1da1-116">Schritt 2: Erstellen einer Sensitivitäts Bezeichnung für das Team des Projekts 2x</span><span class="sxs-lookup"><span data-stu-id="a1da1-116">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="a1da1-117">Contoso-Administratoren haben eine neue Sensitivitäts Bezeichnung mit dem Namen " **Project 2X** " erstellt, die:</span><span class="sxs-lookup"><span data-stu-id="a1da1-117">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="a1da1-118">Verschlüsselung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1da1-118">Requires encryption.</span></span>
- <span data-ttu-id="a1da1-119">Erlaubt gemeinsame Author-Berechtigungen für das Projekt 2X Microsoft 365 Group.</span><span class="sxs-lookup"><span data-stu-id="a1da1-119">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="a1da1-120">Dateien im Abschnitt " **Dokumente** " der zugrunde liegenden Project 2X SharePoint-Website wurden durch Folgendes geschützt:</span><span class="sxs-lookup"><span data-stu-id="a1da1-120">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="a1da1-121">Die Websiteberechtigungen, die nur den Zugriff auf Mitglieder der 2X Microsoft 365-Gruppe des Projekts ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a1da1-121">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="a1da1-122">Die Bezeichnung "Project 2X Sensitivity" mit Verschlüsselung und Berechtigungen, die mit der Datei transportiert werden, wenn Sie von der Website verschoben oder kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="a1da1-122">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="a1da1-123">Informationen zu den Konfigurationsdetails finden Sie unter [Create a Sensitivity Label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="a1da1-123">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="a1da1-124">Schritt 3: Konfigurieren der zugrunde liegenden SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="a1da1-124">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="a1da1-125">Um zunächst den Zugriff auf die zugrunde liegende SharePoint-Website für das Team zu schützen, haben die IT-Administratoren von Contoso die [empfohlenen SharePoint-Zugriffsrichtlinien](../enterprise/sharepoint-file-access-policies.md)konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a1da1-125">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="a1da1-126">Als nächstes haben Sie zusätzliche Berechtigungseinstellungen für die Website konfiguriert, um zu verhindern, dass Project 2X den Zugriff auf die Website freigibt.</span><span class="sxs-lookup"><span data-stu-id="a1da1-126">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site.</span></span> <span data-ttu-id="a1da1-127">Informationen zu den Konfigurationsdetails finden Sie unter [SharePoint-Einstellungen für ein Team mit Sicherheitsisolierung](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="a1da1-127">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>

<span data-ttu-id="a1da1-128">Hier ist die resultierende Konfiguration des Project 2X-Teams.</span><span class="sxs-lookup"><span data-stu-id="a1da1-128">Here is the resulting configuration of the Project 2X team.</span></span>

![Die resultierende Konfiguration des Project 2X-Teams](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="a1da1-130">Schritt 4: geschulte Project 2X-Teammitglieder</span><span class="sxs-lookup"><span data-stu-id="a1da1-130">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="a1da1-131">Contoso-Sicherheitsmitarbeiter haben die Teammitglieder des Projekts 2X in einem obligatorischen Kurs geschult, der Sie durchschritten hat:</span><span class="sxs-lookup"><span data-stu-id="a1da1-131">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="a1da1-132">Wie Sie auf das neue Project 2X-Team zugreifen, Besprechungen und Chats verwenden und wie Sie an Team Dateien zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="a1da1-132">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="a1da1-133">Erstellen neuer Dateien im Team und Hochladen neuer Dateien, die lokal erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="a1da1-133">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="a1da1-134">Ein Beispiel dafür, wie die DLP-Richtlinie verhindert, dass Dateien extern freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a1da1-134">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="a1da1-135">Vorgehensweise Beschriften von Dateien mit der Sensitivitäts Bezeichnung Project 2x.</span><span class="sxs-lookup"><span data-stu-id="a1da1-135">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="a1da1-136">Eine Demonstration der Art und Weise, wie die Bezeichnung des Projekts 2X eine Datei schützt, auch wenn Sie das Team verlässt.</span><span class="sxs-lookup"><span data-stu-id="a1da1-136">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="a1da1-137">Das Endergebnis war eine sichere Umgebung, in der Project 2X-Teammitglieder in einer sicheren Umgebung für Chats, Besprechungen und Dateien zusammengearbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="a1da1-137">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="a1da1-138">Im folgenden finden Sie ein Beispiel für eine Datei, die in der zugrunde liegenden Project 2X-Website gespeichert ist, wobei die Sensitivitäts Bezeichnung Project 2X zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="a1da1-138">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Ein Beispiel für eine Datei, die in der zugrunde liegenden Project 2X-Website gespeichert ist](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="a1da1-140">In einigen Fällen haben Project 2X-Teammitglieder Dateien heruntergeladen, die von der Bezeichnung "Project 2X" auf ein lokales Laufwerk für die Offlinearbeit geschützt wurden.</span><span class="sxs-lookup"><span data-stu-id="a1da1-140">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="a1da1-141">Nachdem Sie jedoch beim Öffnen zur Eingabe von Anmeldeinformationen aufgefordert wurden, wurde der Fehler erkannt und gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a1da1-141">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="a1da1-142">Aufgrund der Zusammenarbeitsumgebung von Teams und der Sicherheitsfeatures von Microsoft 365 wurden die Details von Project 2X für die Dauer des Projekts vertraulich behandelt.</span><span class="sxs-lookup"><span data-stu-id="a1da1-142">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="a1da1-143">Contoso kündigte seine Pläne an und ist dabei, die neuen Produkte und Dienstleistungen zur Freude seiner Kunden und Investoren und zum Leidwesen seiner Konkurrenten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a1da1-143">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="a1da1-144">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="a1da1-144">Next step</span></span>

<span data-ttu-id="a1da1-145">[Stellen Sie ein Team mit Sicherheitsisolierung](secure-teams-security-isolation.md) in Ihrer Organisation bereit.</span><span class="sxs-lookup"><span data-stu-id="a1da1-145">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

