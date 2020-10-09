---
title: Isoliertes Team für ein streng geheimes Projekt der Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
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
ms.openlocfilehash: 16d10f5d6e5b5939172c02746c9324eb20b6987e
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399489"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="29b86-103">Isoliertes Team für ein streng geheimes Projekt der Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="29b86-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="29b86-104">Nach einem externen Geschäftsführer ordnete der CEO von Contoso die Entwicklung einer neuen Produkt-und Dienst Suite an, die die Gewinne von Contoso in den nächsten fünf Jahren verdoppeln könnte.</span><span class="sxs-lookup"><span data-stu-id="29b86-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="29b86-105">Das streng geheime Projekt zur Entwicklung des Geschäfts-, Ingenieur-und Marktplans wurde mit dem Namen **Project 2X** und den wichtigsten Mitarbeitern im gesamten Unternehmen rekrutiert.</span><span class="sxs-lookup"><span data-stu-id="29b86-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="29b86-106">Die Zeitrahmen für Forschung und Entwicklung waren eng, was bedeutete, dass die Zusammenarbeit effizient sein und für sichere Besprechungen, laufende Unterhaltungen und Dateispeicherung sorgen musste.</span><span class="sxs-lookup"><span data-stu-id="29b86-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="29b86-107">Die daraus resultierenden Lieferumfänge für Project 2X Warengeschäfts Pläne, Produkt-und Engineering-Spezifikationen sowie Marketingmaterialien und-Zeitpläne in Form von Word-, Excel-und PowerPoint-Dateien.</span><span class="sxs-lookup"><span data-stu-id="29b86-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="29b86-108">Der Zugriff auf diese Dateien erfolgte aufgrund Ihrer sensiblen Eigenschaften wie folgt:</span><span class="sxs-lookup"><span data-stu-id="29b86-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="29b86-109">Beschränkt auf Project 2X-Teammitglieder und Führungskräfte.</span><span class="sxs-lookup"><span data-stu-id="29b86-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="29b86-110">Verschlüsselt und mit Berechtigungen geschützt, um den Zugriff nur für Project 2X-Teammitglieder und Führungskräfte zu ermöglichen, auch wenn die Dateien außerhalb der gesicherten Ordner verteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="29b86-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="29b86-111">Contoso-IT-Mitarbeiter haben ein [Team mit Sicherheitsisolierung](secure-teams-security-isolation.md) für Project 2X und diese Schritte verwendet.</span><span class="sxs-lookup"><span data-stu-id="29b86-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="29b86-112">Schritt 1: Erstellen eines privaten Teams</span><span class="sxs-lookup"><span data-stu-id="29b86-112">Step 1: Created a private team</span></span>

<span data-ttu-id="29b86-113">Um zunächst den Zugriff auf die zugrunde liegende SharePoint-Website für das Team zu schützen, haben die IT-Administratoren von Contoso die [empfohlenen SharePoint-Zugriffsrichtlinien](../security/office-365-security/sharepoint-file-access-policies.md)konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="29b86-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="29b86-114">Als nächstes hat ein IT-Administrator von Contoso ein neues privates Team namens "Project 2X" erstellt und die Benutzerkonten von Project 2X-Mitarbeitern als Mitglieder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="29b86-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="29b86-115">Außerdem haben Sie das Team so konfiguriert, dass nur Projekt-2X-Teambesitzer private Kanäle erstellen können.</span><span class="sxs-lookup"><span data-stu-id="29b86-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="29b86-116">Informationen zu den Konfigurationsdetails finden Sie unter [Erstellen eines privaten Teams](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="29b86-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="29b86-117">Schritt 2: Erstellen einer Sensitivitäts Bezeichnung für das Team des Projekts 2x</span><span class="sxs-lookup"><span data-stu-id="29b86-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="29b86-118">Contoso-Administratoren haben eine neue Sensitivitäts Bezeichnung mit dem Namen " **Project 2X** " erstellt, die:</span><span class="sxs-lookup"><span data-stu-id="29b86-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="29b86-119">Aktivierte Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="29b86-119">Enabled encryption.</span></span>
- <span data-ttu-id="29b86-120">Zulässige Co-Author Berechtigungen für das Projekt 2X Microsoft 365 Group.</span><span class="sxs-lookup"><span data-stu-id="29b86-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="29b86-121">Zulässige Viewer-Berechtigungen für die Führungskräfte Gruppe.</span><span class="sxs-lookup"><span data-stu-id="29b86-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="29b86-122">Blockierter Zugriff auf nicht verwaltete Geräte.</span><span class="sxs-lookup"><span data-stu-id="29b86-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="29b86-123">Dateien im Abschnitt " **Dokumente** " der zugrunde liegenden Project 2X SharePoint-Website wurden durch Folgendes geschützt:</span><span class="sxs-lookup"><span data-stu-id="29b86-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="29b86-124">Die Websiteberechtigungen, die nur vollständige Berechtigungen für Mitglieder des Projekts 2X Microsoft 365 Group und Leseberechtigungen für die Führungskräfte Gruppe gewähren.</span><span class="sxs-lookup"><span data-stu-id="29b86-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="29b86-125">Die Bezeichnung "Project 2X Sensitivity" mit Verschlüsselung und Berechtigungen, die mit der Datei transportiert werden, wenn Sie von der Website verschoben oder kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="29b86-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="29b86-126">Informationen zu den Konfigurationsdetails finden Sie unter [Create a Sensitivity Label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="29b86-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="29b86-127">Schritt 3: Konfigurieren der zugrunde liegenden SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="29b86-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="29b86-128">Um zunächst den Zugriff auf die zugrunde liegende SharePoint-Website für das Team zu schützen, haben die IT-Administratoren von Contoso die [empfohlenen SharePoint-Zugriffsrichtlinien](../security/office-365-security/sharepoint-file-access-policies.md)konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="29b86-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="29b86-129">Als nächstes haben Sie zusätzliche Berechtigungseinstellungen für die Website konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="29b86-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="29b86-130">So verhindern Sie, dass Mitglieder von Project 2X-Gruppen Zugriff auf die Website freigeben.</span><span class="sxs-lookup"><span data-stu-id="29b86-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="29b86-131">Informationen zu den Konfigurationsdetails finden Sie unter [SharePoint-Einstellungen für ein Team mit Sicherheitsisolierung](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="29b86-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="29b86-132">Für Leseberechtigungen für die Führungskräfte Gruppe.</span><span class="sxs-lookup"><span data-stu-id="29b86-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="29b86-133">Als nächstes haben Sie zusätzliche Berechtigungseinstellungen für die Website konfiguriert, um zu verhindern, dass Mitglieder von Project 2X-Gruppen Zugriff auf die Website freigeben.</span><span class="sxs-lookup"><span data-stu-id="29b86-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="29b86-134">Wenn private Kanäle für das Projekt 2X erstellt wurden, hat der Gruppenbesitzer die Option "Gast Freigabe" deaktiviert und den standardmäßigen Freigabe Link auf den Wert " **bestimmte Personen** " festgelegt.</span><span class="sxs-lookup"><span data-stu-id="29b86-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="29b86-135">Hier ist die resultierende Konfiguration des Project 2X-Teams mit Sicherheitsisolierung.</span><span class="sxs-lookup"><span data-stu-id="29b86-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![Die resultierende Konfiguration des Project 2X-Teams](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="29b86-137">Schritt 4: geschulte Project 2X-Teammitglieder</span><span class="sxs-lookup"><span data-stu-id="29b86-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="29b86-138">Contoso-Sicherheitsmitarbeiter haben die Teammitglieder des Projekts 2X in einem obligatorischen Kurs geschult, der Sie durchschritten hat:</span><span class="sxs-lookup"><span data-stu-id="29b86-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="29b86-139">Wie Sie auf das neue Project 2X-Team zugreifen, Besprechungen und Chats verwenden und wie Sie an Team Dateien zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="29b86-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="29b86-140">Erstellen neuer Dateien im Team und Hochladen neuer Dateien, die lokal erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="29b86-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="29b86-141">Vorgehensweise Beschriften von Dateien mit der Sensitivitäts Bezeichnung Project 2x.</span><span class="sxs-lookup"><span data-stu-id="29b86-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="29b86-142">Eine Demonstration der Art und Weise, wie die Bezeichnung des Projekts 2X eine Datei schützt, auch wenn Sie das Team verlässt.</span><span class="sxs-lookup"><span data-stu-id="29b86-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="29b86-143">Das Endergebnis war eine sichere Umgebung, in der Project 2X-Teammitglieder in einer sicheren Umgebung für Chats, Besprechungen und Dateien zusammengearbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="29b86-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="29b86-144">Im folgenden finden Sie ein Beispiel für eine Datei, die in der zugrunde liegenden Project 2X-Website gespeichert ist, wobei die Sensitivitäts Bezeichnung Project 2X zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="29b86-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Ein Beispiel für eine Datei, die in der zugrunde liegenden Project 2X-Website gespeichert ist](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="29b86-146">In einigen Fällen haben Project 2X-Teammitglieder Dateien heruntergeladen, die von der Bezeichnung "Project 2X" auf ein lokales Laufwerk für die Offlinearbeit geschützt wurden.</span><span class="sxs-lookup"><span data-stu-id="29b86-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="29b86-147">Nachdem Sie jedoch beim Öffnen zur Eingabe von Anmeldeinformationen aufgefordert wurden, wurde der Fehler erkannt und gelöscht.</span><span class="sxs-lookup"><span data-stu-id="29b86-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="29b86-148">Aufgrund der Zusammenarbeitsumgebung von Teams und der Sicherheitsfeatures von Microsoft 365 wurden die Details von Project 2X für die Dauer des Projekts vertraulich behandelt.</span><span class="sxs-lookup"><span data-stu-id="29b86-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="29b86-149">Contoso kündigte seine Pläne an und ist dabei, die neuen Produkte und Dienstleistungen zur Freude seiner Kunden und Investoren und zum Leidwesen seiner Konkurrenten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="29b86-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="29b86-150">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="29b86-150">Next step</span></span>

<span data-ttu-id="29b86-151">[Stellen Sie ein Team mit Sicherheitsisolierung](secure-teams-security-isolation.md) in Ihrer Organisation bereit.</span><span class="sxs-lookup"><span data-stu-id="29b86-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

