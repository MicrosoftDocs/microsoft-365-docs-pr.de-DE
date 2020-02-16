---
title: Team für ein streng geheimes Projekt in der Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Zusammenfassung: Hier erfahren Sie, wie Contoso ein Team für streng geregelte Daten für ein streng geheimes Projekt verwendet, um eine neue Produkt-und Dienst Suite zu entwickeln.'
ms.openlocfilehash: 58d381751db3e94f35a0c1b8f7a14c191918e754
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068026"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="64d3d-103">Team für ein streng geheimes Projekt in der Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="64d3d-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="64d3d-104">Nach einem externen Geschäftsführer ordnete der CEO von Contoso die Entwicklung einer neuen Produkt-und Dienst Suite an, die die Gewinne von Contoso in den nächsten fünf Jahren verdoppeln könnte.</span><span class="sxs-lookup"><span data-stu-id="64d3d-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="64d3d-105">Das streng geheime Projekt zur Entwicklung des Geschäfts-, Ingenieur-und Marktplans wurde mit dem Namen **Project 2X** und den wichtigsten Mitarbeitern im gesamten Unternehmen rekrutiert.</span><span class="sxs-lookup"><span data-stu-id="64d3d-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="64d3d-106">Die Zeitrahmen für Forschung und Entwicklung waren eng, was bedeutete, dass die Zusammenarbeit effizient sein und für sichere Besprechungen, laufende Unterhaltungen und Dateispeicherung sorgen musste.</span><span class="sxs-lookup"><span data-stu-id="64d3d-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="64d3d-107">Die daraus resultierenden Lieferumfänge für Project 2X Warengeschäfts Pläne, Produkt-und Engineering-Spezifikationen sowie Marketingmaterialien und-Zeitpläne in Form von Word-, Excel-und PowerPoint-Dateien.</span><span class="sxs-lookup"><span data-stu-id="64d3d-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="64d3d-108">Der Zugriff auf diese Dateien erfolgte aufgrund Ihrer sensiblen Eigenschaften wie folgt:</span><span class="sxs-lookup"><span data-stu-id="64d3d-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="64d3d-109">Beschränkt auf Project 2X-Teammitglieder.</span><span class="sxs-lookup"><span data-stu-id="64d3d-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="64d3d-110">Durch eine DLP-Richtlinie (Data Loss Prevention) geschützt, um zu verhindern, dass Project 2X-Teammitglieder Sie außerhalb des Teams freigeben.</span><span class="sxs-lookup"><span data-stu-id="64d3d-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="64d3d-111">Verschlüsselt und mit Berechtigungen geschützt, um den Zugriff nur für Project 2X-Teammitglieder zu gewähren, auch wenn die Dateien außerhalb von Contoso verteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="64d3d-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="64d3d-112">Contoso-IT-Mitarbeiter haben ein [Team für hochregulierte Daten](secure-teams-highly-regulated-data-scenario.md) für Project 2X und diese Schritte verwendet.</span><span class="sxs-lookup"><span data-stu-id="64d3d-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="64d3d-113">Schritt 1: Erstellen eines privaten Teams und Sperren der zugrunde liegenden SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="64d3d-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="64d3d-114">Um den Zugriff auf die zugrunde liegende SharePoint-Website für das Team zu schützen, haben Contoso-IT-Administratoren die [empfohlenen SharePoint-Zugriffsrichtlinien](sharepoint-file-access-policies.md)konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="64d3d-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="64d3d-115">Als nächstes hat ein IT-Administrator von Contoso ein neues privates Team namens "Project 2X" erstellt und die Benutzerkonten von Project 2X-Mitarbeitern als Mitglieder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="64d3d-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="64d3d-116">Als nächstes haben Sie zusätzliche Berechtigungseinstellungen für die Website konfiguriert, um zu verhindern, dass Project 2X den Zugriff auf die Website freigibt und andere Benutzer den Zugriff auf die Website anfordern.</span><span class="sxs-lookup"><span data-stu-id="64d3d-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="64d3d-117">Informationen zu den Konfigurationsdetails finden Sie unter [SharePoint-Einstellungen für ein stark reguliertes Team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span><span class="sxs-lookup"><span data-stu-id="64d3d-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="64d3d-118">Schritt 2: Konfigurieren einer DLP-Richtlinie und des zugrunde liegenden Standorts für eine Aufbewahrungs Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="64d3d-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="64d3d-119">Zunächst wendeten Contoso-Administratoren die vorhandene **streng vertrauliche** Office 365 Aufbewahrungs Bezeichnung auf den Abschnitt **Documents** der zugrunde liegenden SharePoint-Website des Project 2X-Teams an.</span><span class="sxs-lookup"><span data-stu-id="64d3d-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="64d3d-120">Als nächstes haben Sie eine neue Office 365 DLP-Richtlinie mit dem Namen " **Project 2X** " erstellt, die:</span><span class="sxs-lookup"><span data-stu-id="64d3d-120">Next, they created a new Office 365 DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="64d3d-121">Verwendet die Office 365 Aufbewahrungs Bezeichnung mit hoher Vertraulichkeit.</span><span class="sxs-lookup"><span data-stu-id="64d3d-121">Uses the Highly Confidential Office 365 retention label.</span></span>
- <span data-ttu-id="64d3d-122">Blockiert Benutzer, wenn Sie versuchen, eine Datei im Team des Projekts 2X außerhalb von Contoso freizugeben.</span><span class="sxs-lookup"><span data-stu-id="64d3d-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="64d3d-123">Informationen zu den Konfigurationsdetails finden Sie unter [Protect Files in Teams with Retention Labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span><span class="sxs-lookup"><span data-stu-id="64d3d-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="64d3d-124">Schritt 3: Erstellen einer Office 365 Sensitivitäts Bezeichnung für das Team des Projekts 2x</span><span class="sxs-lookup"><span data-stu-id="64d3d-124">Step 3: Created an Office 365 sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="64d3d-125">Contoso-Administratoren haben eine neue Office 365 Sensitivitäts Bezeichnung " **Project 2X** " erstellt, die:</span><span class="sxs-lookup"><span data-stu-id="64d3d-125">Contoso admins created a new Office 365 sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="64d3d-126">Verschlüsselung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="64d3d-126">Requires encryption.</span></span>
- <span data-ttu-id="64d3d-127">Erlaubt gemeinsame Author-Berechtigungen für das Projekt 2X Office 365 Gruppe.</span><span class="sxs-lookup"><span data-stu-id="64d3d-127">Allows Co-Author permissions for the Project 2X Office 365 group.</span></span>

<span data-ttu-id="64d3d-128">Hier ist die resultierende Konfiguration des Project 2X-Teams.</span><span class="sxs-lookup"><span data-stu-id="64d3d-128">Here is the resulting configuration of the Project 2X team.</span></span>

![Die resultierende Konfiguration des Project 2X-Teams](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="64d3d-130">Dateien im Abschnitt "Dokumente" der zugrunde liegenden Project 2X SharePoint-Website wurden durch Folgendes geschützt:</span><span class="sxs-lookup"><span data-stu-id="64d3d-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="64d3d-131">Die Websiteberechtigungen, die nur den Zugriff auf Mitglieder des Projekts 2X Office 365 Gruppe ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="64d3d-131">The site permissions, which only allow access to members of the Project 2X Office 365 group.</span></span>
- <span data-ttu-id="64d3d-132">Die streng vertrauliche Aufbewahrungs Bezeichnung, die automatisch neuen Dateien zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="64d3d-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="64d3d-133">Eine DLP-Richtlinie, die die streng vertrauliche Aufbewahrungs Bezeichnung und Einstellungen verwendet, mit denen verhindert wird, dass die Datei für externe Benutzer freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="64d3d-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="64d3d-134">Die Bezeichnung "Project 2X Sensitivity" mit Verschlüsselung und Berechtigungen, die mit der Datei transportiert werden, wenn Sie von der Website verschoben oder kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="64d3d-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="64d3d-135">Im folgenden finden Sie ein Beispiel für eine Datei, die im zugrunde liegenden Projekt 2X-Standort mit der streng regulierten Aufbewahrungs Bezeichnung und der zugewiesenen 2-fachen Vertraulichkeits Bezeichnung gespeichert ist</span><span class="sxs-lookup"><span data-stu-id="64d3d-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![Ein Beispiel für eine Datei, die in der zugrunde liegenden Project 2X-Website gespeichert ist](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="64d3d-137">Schritt 4: geschulte Project 2X-Teammitglieder</span><span class="sxs-lookup"><span data-stu-id="64d3d-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="64d3d-138">Contoso-Sicherheitsmitarbeiter haben die Teammitglieder des Projekts 2X in einem obligatorischen Kurs geschult, der Sie durchschritten hat:</span><span class="sxs-lookup"><span data-stu-id="64d3d-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="64d3d-139">Wie Sie auf das neue Project 2X-Team zugreifen, Besprechungen und Chats verwenden und wie Sie an Team Dateien zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="64d3d-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="64d3d-140">Erstellen neuer Dateien im Team und Hochladen neuer Dateien, die lokal erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="64d3d-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="64d3d-141">Ein Beispiel dafür, wie die DLP-Richtlinie verhindert, dass Dateien extern freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="64d3d-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="64d3d-142">Vorgehensweise Beschriften von Dateien mit der Sensitivitäts Bezeichnung Project 2x.</span><span class="sxs-lookup"><span data-stu-id="64d3d-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="64d3d-143">Eine Demonstration der Art und Weise, wie die Bezeichnung des Projekts 2X eine Datei schützt, auch wenn Sie das Team verlässt.</span><span class="sxs-lookup"><span data-stu-id="64d3d-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="64d3d-144">Das Endergebnis war eine sichere Umgebung, in der Project 2X-Teammitglieder in einer sicheren Umgebung für Chats, Besprechungen und Dateien zusammengearbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="64d3d-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="64d3d-145">In einigen Fällen haben Project 2X-Teammitglieder Dateien heruntergeladen, die von der Bezeichnung "Project 2X" auf ein lokales Laufwerk für die Offlinearbeit geschützt wurden.</span><span class="sxs-lookup"><span data-stu-id="64d3d-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="64d3d-146">Nachdem Sie jedoch beim Öffnen zur Eingabe von Anmeldeinformationen aufgefordert wurden, wurde der Fehler erkannt und gelöscht.</span><span class="sxs-lookup"><span data-stu-id="64d3d-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="64d3d-147">Aufgrund der Zusammenarbeitsumgebung von Teams und der Sicherheitsfeatures von Microsoft 365 wurden die Details von Project 2X für die Dauer des Projekts vertraulich behandelt.</span><span class="sxs-lookup"><span data-stu-id="64d3d-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="64d3d-148">Contoso kündigte seine Pläne an und ist dabei, die neuen Produkte und Dienstleistungen zur Freude seiner Kunden und Investoren und zum Leidwesen seiner Konkurrenten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="64d3d-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="64d3d-149">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="64d3d-149">Next step</span></span>

<span data-ttu-id="64d3d-150">[Bereitstellen](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="64d3d-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="64d3d-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64d3d-151">See also</span></span>

<span data-ttu-id="64d3d-152">[Microsoft 365-Produktivitätsbibliothek](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="64d3d-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
