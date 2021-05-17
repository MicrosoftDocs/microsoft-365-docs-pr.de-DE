---
title: Isoliertes Team für ein geheimes Projekt der Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
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
description: 'Zusammenfassung: Wie Contoso ein Team mit Sicherheitsisolation für ein geheimes Projekt verwendet hat, um eine neue Suite von Produkten und Diensten zu entwickeln.'
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029016"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="85bf3-103">Isoliertes Team für ein geheimes Projekt der Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="85bf3-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="85bf3-104">Nach einer offsite der Geschäftsleitung hat der CEO von Contoso die Entwicklung einer neuen Suite von Produkten und Diensten bestellt, die den Gewinn von Contoso in den nächsten fünf Jahren verdoppeln könnte.</span><span class="sxs-lookup"><span data-stu-id="85bf3-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="85bf3-105">Das geheime Projekt zur Entwicklung des Geschäfts-, Engineering- und Marktplans wurde **Project 2X** genannt, und wichtige Mitarbeiter im gesamten Unternehmen wurden eingestellt.</span><span class="sxs-lookup"><span data-stu-id="85bf3-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="85bf3-106">Die Zeitachsen für Forschung und Entwicklung waren eng, was bedeutete, dass die Zusammenarbeit effizient sein und für sichere Besprechungen, laufende Unterhaltungen und Dateispeicherung sorgen musste.</span><span class="sxs-lookup"><span data-stu-id="85bf3-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="85bf3-107">Die resultierenden Ergebnisse für Project 2X waren Geschäftspläne, Produkt- und technische Spezifikationen sowie Marketingmaterialien und Zeitpläne in Form von Word-, Excel- und PowerPoint-Dateien.</span><span class="sxs-lookup"><span data-stu-id="85bf3-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="85bf3-108">Aufgrund ihrer vertraulichen Art war der Zugriff auf diese Dateien wie die folgenden:</span><span class="sxs-lookup"><span data-stu-id="85bf3-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="85bf3-109">Beschränkt auf Project 2X-Teammitglieder und leitende Führungskräfte.</span><span class="sxs-lookup"><span data-stu-id="85bf3-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="85bf3-110">Verschlüsselt und mit Berechtigungen geschützt, um zugriff nur auf Project 2X-Teammitglieder und leitende Führungskräfte zu ermöglichen, auch wenn die Dateien außerhalb ihrer gesicherten Ordner verteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="85bf3-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="85bf3-111">Contoso-IT-Mitarbeiter verwendeten ein Team mit [Sicherheitsisolation](secure-teams-security-isolation.md) für Project 2X und diese Schritte.</span><span class="sxs-lookup"><span data-stu-id="85bf3-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="85bf3-112">Schritt 1: Erstellen eines privaten Teams</span><span class="sxs-lookup"><span data-stu-id="85bf3-112">Step 1: Created a private team</span></span>

<span data-ttu-id="85bf3-113">Um zunächst den Zugriff auf die zugrunde liegende SharePoint für das Team zu schützen, haben Contoso-IT-Administratoren die empfohlenen [Zugriffsrichtlinien SharePoint konfiguriert.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="85bf3-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="85bf3-114">Als Nächstes hat ein Contoso-IT-Administrator ein neues privates Team mit dem Namen Project 2X erstellt und die Benutzerkonten von Project 2X-Mitarbeitern als Mitglieder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="85bf3-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="85bf3-115">Sie haben das Team auch so konfiguriert, dass nur Project 2X-Teambesitzer private Kanäle erstellen können.</span><span class="sxs-lookup"><span data-stu-id="85bf3-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="85bf3-116">Die Konfigurationsdetails finden Sie unter [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="85bf3-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="85bf3-117">Schritt 2: Erstellen einer Vertraulichkeitsbezeichnung für das Project 2X-Team</span><span class="sxs-lookup"><span data-stu-id="85bf3-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="85bf3-118">Contoso-Administratoren haben eine neue Vertraulichkeitsbezeichnung namens **Project 2X erstellt,** die:</span><span class="sxs-lookup"><span data-stu-id="85bf3-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="85bf3-119">Aktivierte Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="85bf3-119">Enabled encryption.</span></span>
- <span data-ttu-id="85bf3-120">Zulässige Co-Author für die Project 2X-Microsoft 365 Gruppe.</span><span class="sxs-lookup"><span data-stu-id="85bf3-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="85bf3-121">Zulässige Viewer-Berechtigungen für die Gruppe "Senior Leadership".</span><span class="sxs-lookup"><span data-stu-id="85bf3-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="85bf3-122">Blockierter Zugriff auf nicht verwaltete Geräte.</span><span class="sxs-lookup"><span data-stu-id="85bf3-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="85bf3-123">Dateien im Abschnitt **Dokumente** der zugrunde liegenden Project 2X-SharePoint wurden durch:</span><span class="sxs-lookup"><span data-stu-id="85bf3-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="85bf3-124">Die Websiteberechtigungen, die nur vollständige Berechtigungen für Mitglieder der gruppe Project 2X Microsoft 365 und Leseberechtigungen für die Gruppe "Senior Leadership" zulassen.</span><span class="sxs-lookup"><span data-stu-id="85bf3-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="85bf3-125">Die Project 2X-Vertraulichkeitsbezeichnung mit Verschlüsselung und Berechtigungen, die mit der Datei reisen, wenn sie von der Website verschoben oder kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="85bf3-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="85bf3-126">Die Konfigurationsdetails finden Sie unter [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="85bf3-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="85bf3-127">Schritt 3: Konfigurieren der zugrunde liegenden SharePoint Website</span><span class="sxs-lookup"><span data-stu-id="85bf3-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="85bf3-128">Um zunächst den Zugriff auf die zugrunde liegende SharePoint für das Team zu schützen, haben Contoso-IT-Administratoren die empfohlenen [Zugriffsrichtlinien SharePoint konfiguriert.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="85bf3-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="85bf3-129">Als Nächstes konfigurierten sie zusätzliche Berechtigungseinstellungen für die Website:</span><span class="sxs-lookup"><span data-stu-id="85bf3-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="85bf3-130">Um zu Project, dass 2X-Gruppenmitglieder den Zugriff auf die Website freigeben.</span><span class="sxs-lookup"><span data-stu-id="85bf3-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="85bf3-131">Die Konfigurationsdetails finden Sie [unter SharePoint einstellungen für ein Team mit Sicherheitsisolation](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="85bf3-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="85bf3-132">For Read permissions for the Senior Leadership group.</span><span class="sxs-lookup"><span data-stu-id="85bf3-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="85bf3-133">Als Nächstes konfigurierten sie zusätzliche Berechtigungseinstellungen für die Website, um zu verhindern, dass Project 2X-Gruppenmitglieder den Zugriff auf die Website freigeben.</span><span class="sxs-lookup"><span data-stu-id="85bf3-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="85bf3-134">Als private Kanäle für die Project 2X erstellt wurden, deaktivierte der Gruppenbesitzer die Gastfreigabe, und der Standardfreigabelink wurde auf den Wert **Spezifische Personen** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="85bf3-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="85bf3-135">Hier sehen Sie die resultierende Konfiguration des Project 2X-Teams mit Sicherheitsisolation.</span><span class="sxs-lookup"><span data-stu-id="85bf3-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![Die resultierende Konfiguration des Project 2X-Teams](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="85bf3-137">Schritt 4: Geschulte Project 2X-Teammitglieder</span><span class="sxs-lookup"><span data-stu-id="85bf3-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="85bf3-138">Contoso-Sicherheitsmitarbeiter haben die Project 2X-Teammitglieder in einem obligatorischen Kurs geschult, der sie durch schritt:</span><span class="sxs-lookup"><span data-stu-id="85bf3-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="85bf3-139">So greifen Sie auf das neue Project 2X-Team zu, verwenden Sie Besprechungen und Chats und wie Sie an Teamdateien zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="85bf3-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="85bf3-140">Hier erfahren Sie, wie Sie neue Dateien im Team erstellen und neue lokal erstellte Dateien hochladen.</span><span class="sxs-lookup"><span data-stu-id="85bf3-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="85bf3-141">So beschriften Sie Dateien mit Project 2X-Vertraulichkeitsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="85bf3-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="85bf3-142">Eine Demonstration, wie Project 2X-Bezeichnung eine Datei schützt, auch wenn sie das Team verlässt.</span><span class="sxs-lookup"><span data-stu-id="85bf3-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="85bf3-143">Das Endergebnis war eine sichere Umgebung, in der Project 2X Teammitglieder in einer sicheren Umgebung für Chats, Besprechungen und Dateien zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="85bf3-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="85bf3-144">Hier ist ein Beispiel für eine Datei, die auf der zugrunde liegenden Project 2X-Website gespeichert ist, der die Project 2X-Vertraulichkeitsbezeichnung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="85bf3-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Ein Beispiel für eine Datei, die auf der zugrunde liegenden Project 2X-Website gespeichert ist](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="85bf3-146">In einigen Fällen haben Project 2X-Teammitglieder Dateien heruntergeladen, die durch die Project 2X-Bezeichnung geschützt sind, auf ein lokales Laufwerk für die Offlinearbeit.</span><span class="sxs-lookup"><span data-stu-id="85bf3-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="85bf3-147">Nachdem sie jedoch beim Öffnen zur Eingabe von Anmeldeinformationen aufgefordert wurden, erkannten sie ihren Fehler und löschten sie.</span><span class="sxs-lookup"><span data-stu-id="85bf3-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="85bf3-148">Aufgrund der Umgebung für die Zusammenarbeit von Teams und der Sicherheitsfeatures von Microsoft 365 wurden die Details von Project 2X für die Dauer des Projekts geheim gehalten.</span><span class="sxs-lookup"><span data-stu-id="85bf3-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="85bf3-149">Contoso hat seine Pläne angekündigt und ist dabei, die neuen Produkte und Dienstleistungen zur Freude seiner Kunden und Investoren und zum Unförmlich der Konkurrenten zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="85bf3-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="85bf3-150">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="85bf3-150">Next step</span></span>

<span data-ttu-id="85bf3-151">[Bereitstellen eines Teams mit Sicherheitsisolation](secure-teams-security-isolation.md) in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="85bf3-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

