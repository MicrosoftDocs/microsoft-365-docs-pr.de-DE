---
title: Gruppen von Dienstinteraktionen
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Gruppen von Dienstinteraktionen
ms.openlocfilehash: 331c30c86481b1729251c685de2d663fb14f390b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921024"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="65020-103">Gruppen von Dienstinteraktionen</span><span class="sxs-lookup"><span data-stu-id="65020-103">Groups services interactions</span></span>

<span data-ttu-id="65020-104">Microsoft 365-Gruppen bieten eine allgemeine Struktur für eine Reihe von Diensten und Workloads innerhalb der Microsoft 365-Plattform, um endbenutzern eine verbundene Benutzererfahrung zu bieten.</span><span class="sxs-lookup"><span data-stu-id="65020-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="65020-105">Im Kern ist eine Microsoft 365-Gruppe vorhanden, um:</span><span class="sxs-lookup"><span data-stu-id="65020-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="65020-106">Eine Möglichkeit zum Verwalten der Mitgliedschaft (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="65020-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="65020-107">Ein Ort, an dem Nachrichten und Unterhaltungen stattfinden (Exchange-Postfach, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="65020-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="65020-108">Ein Ort, an dem Dateien gespeichert werden sollen (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="65020-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="65020-109">Ein Kalender für die Planung (Exchange)</span><span class="sxs-lookup"><span data-stu-id="65020-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="65020-110">Ein Notizbuch zum Aufzeichnen von Notizen (OneNote)</span><span class="sxs-lookup"><span data-stu-id="65020-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="65020-111">Zum Zeitpunkt der Gruppenerstellung werden auch eine Reihe anderer Ressourcen bereitgestellt, die jedoch erst angezeigt werden, wenn erstmals über den Dienst auf sie zugegriffen wird:</span><span class="sxs-lookup"><span data-stu-id="65020-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="65020-112">Ein Board zum Verwalten von Gruppenaufgaben (Planner)</span><span class="sxs-lookup"><span data-stu-id="65020-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="65020-113">Ein Arbeitsbereich für die Berichterstellung (Power BI)</span><span class="sxs-lookup"><span data-stu-id="65020-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="65020-114">Ein Bereich für freigegebene Videos (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="65020-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="65020-115">Ein Bereich für freigegebene Formulare (Formulare)</span><span class="sxs-lookup"><span data-stu-id="65020-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="65020-116">In Microsoft 365 können andere Dienste mit Microsoft 365-Gruppen interagieren, um gruppenmitgliedern zusätzliche Funktionen und Funktionen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="65020-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="65020-117">Beispiele hierfür sind:</span><span class="sxs-lookup"><span data-stu-id="65020-117">Examples of this include:</span></span>

- <span data-ttu-id="65020-118">Power Apps für Apps</span><span class="sxs-lookup"><span data-stu-id="65020-118">Power Apps for apps</span></span>
- <span data-ttu-id="65020-119">Power Automate für Workflows</span><span class="sxs-lookup"><span data-stu-id="65020-119">Power Automate for workflows</span></span>
- <span data-ttu-id="65020-120">Projekt im Web und Roadmap für wasserfallbasiertes Projektmanagement</span><span class="sxs-lookup"><span data-stu-id="65020-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="65020-121">Teams für kanalbasierte Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="65020-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="65020-122">Yammer für Communitys von Interesse</span><span class="sxs-lookup"><span data-stu-id="65020-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="65020-123">Benutzerinteraktionen mit Gruppen</span><span class="sxs-lookup"><span data-stu-id="65020-123">User interactions with groups</span></span>

<span data-ttu-id="65020-124">Microsoft 365-Gruppen können über eine Vielzahl von Schnittstellen erstellt und verwaltet werden, sowohl von Administratoren als auch von Endbenutzern.</span><span class="sxs-lookup"><span data-stu-id="65020-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="65020-125">Verwaltungserfahrungen</span><span class="sxs-lookup"><span data-stu-id="65020-125">Administrative experiences</span></span>

<span data-ttu-id="65020-126">Administratoren können Microsoft 365-Gruppen aus mehreren Workload Admin Centern, Befehlszeilenschnittstellen, die Skripting unterstützen, sowie benutzerdefinierte Apps, die mit der Graph-API interagieren, erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="65020-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="65020-127">Die einzige Ausnahme bilden Yammer Gruppen, die innerhalb der Yammer erstellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="65020-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="65020-128">**Verwandte Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="65020-128">**Related settings**</span></span>

<span data-ttu-id="65020-129">In den verschiedenen administrativen Schnittstellen, die Gruppeneinstellungen verwalten können, gibt es mehrere Überschneidungen, die Sie beachten sollten.</span><span class="sxs-lookup"><span data-stu-id="65020-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="65020-130">**Microsoft 365 Admin Center**</span><span class="sxs-lookup"><span data-stu-id="65020-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="65020-131">Im Microsoft 365 Admin Center ist der Gastzugriff auf Gruppen standardmäßig aktiviert, ebenso wie die Möglichkeit, Besitzern das Hinzufügen von Gästen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="65020-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="65020-132">In diesem Admin Center sind keine weiteren Steuerelemente auf Organisationsebene für Gruppen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="65020-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="65020-133">**Azure AD Admin Center**</span><span class="sxs-lookup"><span data-stu-id="65020-133">**Azure AD admin center**</span></span>

<span data-ttu-id="65020-134">Das Azure AD Admin Center bietet Steuerungen darüber, ob Benutzer Gruppen erstellen oder Besitzer in Azure-Portalen zuweisen können, sowie Ablauf- und Benennungsrichtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="65020-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="65020-135">Das Admin Center bietet auch eine Reihe von Steuerungsmaßnahmen für Gasteinladungen, die über die des Microsoft 365 Admin Centers hinausgehen, z. B. die Möglichkeit, zu begrenzen, ob Nichtbesitzer auch Gäste einladen können.</span><span class="sxs-lookup"><span data-stu-id="65020-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="65020-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="65020-136">**SharePoint**</span></span>

<span data-ttu-id="65020-137">SharePoint-Websites werden mit Sicherheitsgruppen für Besitzer, Mitglieder und Besucher erstellt, und die ersten beiden übereinstimmen mit ihren Microsoft 365-Gruppen..</span><span class="sxs-lookup"><span data-stu-id="65020-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="65020-138">Während die Mitgliedschaft für SharePoint Online-Websites im Allgemeinen von der zugeordneten Microsoft 365-Gruppe verwaltet wird, handelt es sich nicht um eine bidirektionale Beziehung.</span><span class="sxs-lookup"><span data-stu-id="65020-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="65020-139">Alle Änderungen an der Mitgliedschaft auf Microsoft 365-Gruppenebene werden in SharePoint widerspiegelt. Wenn die Mitgliedschaft in der SharePoint-Gruppe geändert wird, wird dies jedoch nicht in der Microsoft 365-Gruppe wider.</span><span class="sxs-lookup"><span data-stu-id="65020-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="65020-140">Benutzererfahrungen</span><span class="sxs-lookup"><span data-stu-id="65020-140">User experiences</span></span>

<span data-ttu-id="65020-141">Endbenutzer können Gruppen aus mehreren Diensten in Microsoft 365 und in anderen Gruppen nur für eine Gruppe freigeben.</span><span class="sxs-lookup"><span data-stu-id="65020-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="65020-142">Die folgenden Dienste ermöglichen das Erstellen von Gruppen durch Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="65020-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="65020-143">Outlook Planner Project for the web SharePoint Stream Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="65020-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="65020-144">**Einschränkung der Gruppenerstellung**</span><span class="sxs-lookup"><span data-stu-id="65020-144">**Restriction of group creation**</span></span>

<span data-ttu-id="65020-145">Ein gängiger Ansatz zum Steuern der Aussiedelung von Teams besteht in der Beschränkung, welche Benutzer sie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="65020-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="65020-146">Dies kann nur durch Einschränken der Erstellung von Gruppen geschehen.</span><span class="sxs-lookup"><span data-stu-id="65020-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="65020-147">Dies wirkt sich auf die Möglichkeit aus, Gruppen aus anderen Diensten zu erstellen, wo dies für Endbenutzer erforderlich sein kann.</span><span class="sxs-lookup"><span data-stu-id="65020-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="65020-148">Microsoft 365-Gruppen unterstützt nicht die Möglichkeit, die Erstellung von Gruppen aus einigen Apps oder Diensten einzuschränken und dies von anderen zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="65020-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="65020-149">Die Erfahrung der Gruppenerstellungseinschränkung variiert zwischen Apps und Diensten:</span><span class="sxs-lookup"><span data-stu-id="65020-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="65020-150">App oder Dienst</span><span class="sxs-lookup"><span data-stu-id="65020-150">App or service</span></span>|<span data-ttu-id="65020-151">Umgebung</span><span class="sxs-lookup"><span data-stu-id="65020-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="65020-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="65020-152">Outlook</span></span>|<span data-ttu-id="65020-153">**Neue Gruppenoption** wird aus dem Menü Neu auf der Personenseite entfernt.</span><span class="sxs-lookup"><span data-stu-id="65020-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="65020-154">Planner</span><span class="sxs-lookup"><span data-stu-id="65020-154">Planner</span></span>|<span data-ttu-id="65020-155">**Neuer Plan** erläutert, dass die Gruppenerstellung deaktiviert wurde, und bietet an, den Plan einer vorhandenen Gruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="65020-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="65020-156">Projekt für das Web und Roadmap</span><span class="sxs-lookup"><span data-stu-id="65020-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="65020-157">**Im Menü** Gruppen erstellen wird erläutert, dass die Gruppenerstellung eingeschränkt ist, und es wird vorgeschlagen, eine vorhandene Gruppe zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="65020-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="65020-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="65020-158">SharePoint</span></span>|<span data-ttu-id="65020-159">Weiterhin in der Lage, eine Teamwebsite zu erstellen, die nicht mit einer Gruppe verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="65020-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="65020-160">Stream</span><span class="sxs-lookup"><span data-stu-id="65020-160">Stream</span></span>|<span data-ttu-id="65020-161">Die Option **"Gruppe"** wird nicht im Menü **Erstellen angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="65020-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="65020-162">Teams</span><span class="sxs-lookup"><span data-stu-id="65020-162">Teams</span></span>|<span data-ttu-id="65020-163">Der Benutzer kann kein Team mit einer neuen Gruppe erstellen, aber dennoch ein Team erstellen, das eine vorhandene Gruppe verwendet.</span><span class="sxs-lookup"><span data-stu-id="65020-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="65020-164">**Erstellen einer Teamschaltfläche** wird durch **Team aus einer Gruppe erstellen ersetzt.**</span><span class="sxs-lookup"><span data-stu-id="65020-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="65020-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="65020-165">Yammer</span></span>|<span data-ttu-id="65020-166">**Erstellen einer Gruppenoption** wird aus der Hauptnavigation gruppen/communities entfernt.</span><span class="sxs-lookup"><span data-stu-id="65020-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="65020-167">Diensteinteraktionen mit Gruppen</span><span class="sxs-lookup"><span data-stu-id="65020-167">Services interactions with groups</span></span>

<span data-ttu-id="65020-168">Informationen zu unterschiedlichen Gruppentypen, wie diese erstellt und verwaltet werden, sowie einige Empfehlungen zur Steuerung finden Sie auf dem Poster Gruppen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65020-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="65020-169">[![Miniaturbild für Gruppen-Infografik](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="65020-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="65020-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="65020-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="65020-171">Die folgende Tabelle enthält eine Übersicht über die Interaktionen von Microsoft 365-Gruppen mit verschiedenen Diensten:</span><span class="sxs-lookup"><span data-stu-id="65020-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="65020-172">Produkt</span><span class="sxs-lookup"><span data-stu-id="65020-172">Product</span></span>|<span data-ttu-id="65020-173">Features</span><span class="sxs-lookup"><span data-stu-id="65020-173">Features</span></span>|<span data-ttu-id="65020-174">Führt den Dienst aus</span><span class="sxs-lookup"><span data-stu-id="65020-174">Does the service</span></span><br><span data-ttu-id="65020-175">ohne Gruppe vorhanden?</span><span class="sxs-lookup"><span data-stu-id="65020-175">exist without a group?</span></span>|<span data-ttu-id="65020-176">Kann der Dienst</span><span class="sxs-lookup"><span data-stu-id="65020-176">Can the service</span></span><br><span data-ttu-id="65020-177">Eine Gruppe erstellen?</span><span class="sxs-lookup"><span data-stu-id="65020-177">create a group?</span></span>|<span data-ttu-id="65020-178">Löscht die</span><span class="sxs-lookup"><span data-stu-id="65020-178">Does deleting the</span></span><br><span data-ttu-id="65020-179">Instanz die Gruppe löschen?</span><span class="sxs-lookup"><span data-stu-id="65020-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="65020-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="65020-180">Azure AD</span></span>|<span data-ttu-id="65020-181">Mitgliedschaft, Gruppensteuerelemente, Gäste</span><span class="sxs-lookup"><span data-stu-id="65020-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="65020-182">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-182">Yes</span></span>|<span data-ttu-id="65020-183">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-183">Yes</span></span>|<span data-ttu-id="65020-184">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-184">Yes</span></span>|
|<span data-ttu-id="65020-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="65020-185">Exchange</span></span>|<span data-ttu-id="65020-186">Kalender, Postfach</span><span class="sxs-lookup"><span data-stu-id="65020-186">Calendar, mailbox</span></span>|<span data-ttu-id="65020-187">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-187">Yes</span></span>|<span data-ttu-id="65020-188">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-188">Yes</span></span>|<span data-ttu-id="65020-189">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-189">Yes</span></span>|
|<span data-ttu-id="65020-190">Formulare</span><span class="sxs-lookup"><span data-stu-id="65020-190">Forms</span></span>|<span data-ttu-id="65020-191">Formular</span><span class="sxs-lookup"><span data-stu-id="65020-191">Form</span></span>|<span data-ttu-id="65020-192">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-192">Yes</span></span>|<span data-ttu-id="65020-193">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-193">No</span></span>|<span data-ttu-id="65020-194">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-194">No</span></span>|
|<span data-ttu-id="65020-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="65020-195">OneNote</span></span>|<span data-ttu-id="65020-196">Notizbuch</span><span class="sxs-lookup"><span data-stu-id="65020-196">Notebook</span></span>|<span data-ttu-id="65020-197">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-197">Yes</span></span>|<span data-ttu-id="65020-198">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-198">No</span></span>|<span data-ttu-id="65020-199">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-199">No</span></span>|
|<span data-ttu-id="65020-200">Planner</span><span class="sxs-lookup"><span data-stu-id="65020-200">Planner</span></span>|<span data-ttu-id="65020-201">Task Board</span><span class="sxs-lookup"><span data-stu-id="65020-201">Task board</span></span>|<span data-ttu-id="65020-202">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-202">No</span></span>|<span data-ttu-id="65020-203">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-203">Yes</span></span>|<span data-ttu-id="65020-204">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-204">Yes</span></span>|
|<span data-ttu-id="65020-205">Power Apps-App</span><span class="sxs-lookup"><span data-stu-id="65020-205">Power Apps app</span></span>|<span data-ttu-id="65020-206">App</span><span class="sxs-lookup"><span data-stu-id="65020-206">App</span></span>|<span data-ttu-id="65020-207">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-207">Yes</span></span>|<span data-ttu-id="65020-208">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-208">No</span></span>|<span data-ttu-id="65020-209">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-209">No</span></span>|
|<span data-ttu-id="65020-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="65020-210">Power Automate</span></span>|<span data-ttu-id="65020-211">Workflow</span><span class="sxs-lookup"><span data-stu-id="65020-211">Workflow</span></span>|<span data-ttu-id="65020-212">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-212">Yes</span></span>|<span data-ttu-id="65020-213">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-213">No</span></span>|<span data-ttu-id="65020-214">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-214">No</span></span>|
|<span data-ttu-id="65020-215">Power BI (klassisch)</span><span class="sxs-lookup"><span data-stu-id="65020-215">Power BI (classic)</span></span>|<span data-ttu-id="65020-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="65020-216">Workspace</span></span>|<span data-ttu-id="65020-217">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-217">No</span></span>|<span data-ttu-id="65020-218">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-218">Yes</span></span>|<span data-ttu-id="65020-219">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-219">Yes</span></span>|
|<span data-ttu-id="65020-220">Power BI (neu)</span><span class="sxs-lookup"><span data-stu-id="65020-220">Power BI (new)</span></span>|<span data-ttu-id="65020-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="65020-221">Workspace</span></span>|<span data-ttu-id="65020-222">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-222">Yes</span></span>|<span data-ttu-id="65020-223">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-223">No</span></span>|<span data-ttu-id="65020-224">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-224">Yes</span></span>|
|<span data-ttu-id="65020-225">Project für das Web</span><span class="sxs-lookup"><span data-stu-id="65020-225">Project for the web</span></span>|<span data-ttu-id="65020-226">Projektplan</span><span class="sxs-lookup"><span data-stu-id="65020-226">Project plan</span></span>|<span data-ttu-id="65020-227">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-227">Yes</span></span>|<span data-ttu-id="65020-228">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-228">Yes</span></span>|<span data-ttu-id="65020-229">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-229">No</span></span>|
|<span data-ttu-id="65020-230">Roadmap</span><span class="sxs-lookup"><span data-stu-id="65020-230">Roadmap</span></span>|<span data-ttu-id="65020-231">Roadmap</span><span class="sxs-lookup"><span data-stu-id="65020-231">Roadmap</span></span>|<span data-ttu-id="65020-232">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-232">Yes</span></span>|<span data-ttu-id="65020-233">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-233">Yes</span></span>|<span data-ttu-id="65020-234">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-234">No</span></span>|
|<span data-ttu-id="65020-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="65020-235">SharePoint</span></span>|<span data-ttu-id="65020-236">Website</span><span class="sxs-lookup"><span data-stu-id="65020-236">Site</span></span>|<span data-ttu-id="65020-237">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-237">Yes</span></span>|<span data-ttu-id="65020-238">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-238">Yes</span></span>|<span data-ttu-id="65020-239">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-239">Yes</span></span>|
|<span data-ttu-id="65020-240">Stream</span><span class="sxs-lookup"><span data-stu-id="65020-240">Stream</span></span>|<span data-ttu-id="65020-241">Kanal, Video</span><span class="sxs-lookup"><span data-stu-id="65020-241">Channel, video</span></span>|<span data-ttu-id="65020-242">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-242">Yes</span></span>|<span data-ttu-id="65020-243">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-243">Yes</span></span>|<span data-ttu-id="65020-244">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-244">Yes</span></span>|
|<span data-ttu-id="65020-245">Teams</span><span class="sxs-lookup"><span data-stu-id="65020-245">Teams</span></span>|<span data-ttu-id="65020-246">Team</span><span class="sxs-lookup"><span data-stu-id="65020-246">Team</span></span>|<span data-ttu-id="65020-247">Nein</span><span class="sxs-lookup"><span data-stu-id="65020-247">No</span></span>|<span data-ttu-id="65020-248">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-248">Yes</span></span>|<span data-ttu-id="65020-249">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-249">Yes</span></span>|
|<span data-ttu-id="65020-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="65020-250">Yammer</span></span>|<span data-ttu-id="65020-251">Group</span><span class="sxs-lookup"><span data-stu-id="65020-251">Group</span></span>|<span data-ttu-id="65020-252">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-252">Yes</span></span>|<span data-ttu-id="65020-253">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-253">Yes</span></span>|<span data-ttu-id="65020-254">Ja</span><span class="sxs-lookup"><span data-stu-id="65020-254">Yes</span></span>|

<span data-ttu-id="65020-255">Während die obige Tabelle einen umfassenden Überblick über Gruppeninteraktionen mit Microsoft 365-Diensten bietet, sollten Sie eine Reihe von Nuancen und Feinheiten verstehen.</span><span class="sxs-lookup"><span data-stu-id="65020-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="65020-256">In den folgenden Abschnitten werden die spezifischen Arbeitsauslastungen und deren Interaktionen mit Gruppen genauer beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65020-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="65020-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="65020-257">Azure AD</span></span>

<span data-ttu-id="65020-258">Azure AD bietet die zugrunde liegenden Identitätsverwaltungsfunktionen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65020-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="65020-259">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="65020-260">Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="65020-260">Group membership</span></span>
- <span data-ttu-id="65020-261">Benennungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="65020-261">Naming policy</span></span>
- <span data-ttu-id="65020-262">Ablaufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="65020-262">Expiration policy</span></span>
- <span data-ttu-id="65020-263">Gäste</span><span class="sxs-lookup"><span data-stu-id="65020-263">Guests</span></span>
- <span data-ttu-id="65020-264">Einschränkung der Gruppenerstellung</span><span class="sxs-lookup"><span data-stu-id="65020-264">Restriction of Group creation</span></span>

<span data-ttu-id="65020-265">**Kann Azure AD eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="65020-266">Ja, Microsoft 365-Gruppen können aus Azure AD entweder über das Verwaltungswebportal, über PowerShell oder graph-API erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="65020-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="65020-267">**Gibt es Azure AD ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="65020-268">Ja, Azure AD führt eine große Anzahl von Diensten aus, die keinen Bezug zu Microsoft 365-Gruppen haben.</span><span class="sxs-lookup"><span data-stu-id="65020-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="65020-269">Jede Microsoft 365-Gruppe wird in Azure AD als Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="65020-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="65020-270">**Gibt es mehrere Instanzen von Azure AD pro Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="65020-271">Nein, es gibt nur eine Instanz von Azure AD.</span><span class="sxs-lookup"><span data-stu-id="65020-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="65020-272">**Kann Azure AD mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="65020-273">Ja, da Azure AD die zugrunde liegende Plattform ist, die den Gruppenmitgliedschaftsdienst bietet.</span><span class="sxs-lookup"><span data-stu-id="65020-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="65020-274">**Kann sich die Zuordnung von Azure AD zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="65020-275">Nein, Azure AD ist die zugrunde liegende Plattform, auf der Gruppen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="65020-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="65020-276">**Löscht das Löschen der Instanz die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="65020-277">Wenn Sie die Gruppe in Azure AD löschen, werden relevante gruppenverkn nente Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="65020-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="65020-278">Teams</span><span class="sxs-lookup"><span data-stu-id="65020-278">Teams</span></span>

<span data-ttu-id="65020-279">Teams ist ein chatzentrierter Arbeitsbereich, der die Zusammenarbeit verbessern soll, indem eine einzigartige Schnittstelle für die Interaktion mit einer Vielzahl von Microsoft- und Drittanbieterdiensten zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="65020-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="65020-280">Wenn ein Team erstellt wird, werden das Der Microsoft 365-Gruppe zugeordnete Postfach und der Kalender standardmäßig sowohl in der globalen Adressliste in Exchange als auch in Outlook ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="65020-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="65020-281">Dies kann manuell von einem Administrator überschrieben werden, wenn der Benutzer Outlook und Teams in derselben Microsoft 365-Gruppe verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="65020-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="65020-282">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="65020-283">Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="65020-283">Conversations</span></span>
- <span data-ttu-id="65020-284">Kanäle & Registerkarten</span><span class="sxs-lookup"><span data-stu-id="65020-284">Channels & tabs</span></span>
- <span data-ttu-id="65020-285">Besprechungen</span><span class="sxs-lookup"><span data-stu-id="65020-285">Meetings</span></span>

<span data-ttu-id="65020-286">**Kann Teams eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="65020-287">Ja, durch das Erstellen eines neuen Teams wird eine neue Microsoft 365-Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="65020-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="65020-288">Es ist auch möglich, ein Team für eine vorhandene Gruppe zu erstellen, die derzeit nicht über ein Team verfügt.</span><span class="sxs-lookup"><span data-stu-id="65020-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="65020-289">**Gibt es Teams ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="65020-290">Nein, es ist nicht möglich, dass ein Team ohne eine Gruppe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="65020-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="65020-291">**Kann es mehrere Teams pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="65020-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="65020-292">Nein, die Beziehung zwischen einem Team und einer Gruppe ist 1:1.</span><span class="sxs-lookup"><span data-stu-id="65020-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="65020-293">**Kann ein Team mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-294">Nein, das Team selbst kann nur einer einzelnen Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="65020-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="65020-295">**Kann sich die Zuordnung eines Teams zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="65020-296">Nein, das Team kann nur der Gruppe zugeordnet werden, der es ursprünglich zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="65020-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="65020-297">**Löscht das Löschen des Teams die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="65020-298">Ja, das Löschen des Teams in Microsoft Teams löscht die Gruppe, die gruppenverkn nenen Dienste und den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="65020-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="65020-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="65020-299">Exchange</span></span>

<span data-ttu-id="65020-300">Exchange Online bietet Messaging-, Kalender-, Kontakt- und zugehörige Funktionen.</span><span class="sxs-lookup"><span data-stu-id="65020-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="65020-301">Im Kontext einer Gruppe wird nur eine einzelne Ressource zugeordnet – im Gegensatz zu einer gesamten Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="65020-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="65020-302">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="65020-303">Postfach und Kalender</span><span class="sxs-lookup"><span data-stu-id="65020-303">Mailbox and calendar</span></span>
- <span data-ttu-id="65020-304">Möglichkeit, alle Gruppenmitglieder per E-Mail zu senden</span><span class="sxs-lookup"><span data-stu-id="65020-304">Ability to email all Group members</span></span>
- <span data-ttu-id="65020-305">Speichern von Teams-Kanalunterhaltungen für eDiscovery-Zwecke, Planner-Kommentare</span><span class="sxs-lookup"><span data-stu-id="65020-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="65020-306">**Kann Exchange eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="65020-307">Ja, es ist möglich, eine Gruppe aus dem Exchange Online Admin Center sowie aus Outlook zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="65020-308">Sie können auch Exchange-Verteilerlisten in Microsoft 365-Gruppen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="65020-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="65020-309">**Gibt es Exchange ohne Eine Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="65020-310">Ja, Exchange Online stellt eine Reihe von Diensten, einschließlich freigegebener Postfächer und Kalender, ohne gruppenverbundene Dienste zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="65020-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="65020-311">**Gibt es mehrere Instanzen von Exchange-Postfächern oder Kalendern pro Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="65020-312">Nein, es kann nur ein einzelnes Exchange Online-Postfach und ein einzelner Kalender für eine Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="65020-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="65020-313">**Können Exchange-Postfächer und -Kalender mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-314">Nein, das Postfach und der Kalender haben eine 1:1-Beziehung mit der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="65020-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="65020-315">Es ist möglich, das Postfach für andere Benutzer oder Gruppen zu teilen, es wird jedoch keine Form der Dienst zuordnung erstellt.</span><span class="sxs-lookup"><span data-stu-id="65020-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="65020-316">**Kann sich die Zuordnung des Exchange-Postfachs oder Kalenders zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="65020-317">Nein, das Postfach und der Kalender können nicht in eine andere Gruppe geändert werden.</span><span class="sxs-lookup"><span data-stu-id="65020-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="65020-318">Der Inhalt kann jedoch innerhalb von Outlook oder mithilfe eines Drittanbietertools von einem Postfach in ein anderes verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="65020-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="65020-319">**Löscht das Löschen des Postfachs die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="65020-320">Ja, durch das Löschen des Postfachs in Exchange werden die Gruppe sowie gruppenverkn nnte Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="65020-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="65020-321">Formulare</span><span class="sxs-lookup"><span data-stu-id="65020-321">Forms</span></span>

<span data-ttu-id="65020-322">Formulare bieten webbasierte Umfragen und Quizfragen.</span><span class="sxs-lookup"><span data-stu-id="65020-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="65020-323">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="65020-324">Besitz von Formularen</span><span class="sxs-lookup"><span data-stu-id="65020-324">Ownership of forms</span></span>

<span data-ttu-id="65020-325">**Können Formulare eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="65020-326">Nein, Forms kann keine Gruppe erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="65020-327">**Sind Formulare ohne Gruppe vorhanden?**</span><span class="sxs-lookup"><span data-stu-id="65020-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="65020-328">Ja, Umfragen und Quiz können direkt im Konto eines Endbenutzers erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="65020-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="65020-329">**Gibt es mehrere Formulare pro Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="65020-330">Ja, einer Gruppe können mehrere Formulare zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="65020-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="65020-331">**Können Formulare mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-332">Nein, ein Formular kann nur einer einzelnen Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="65020-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="65020-333">**Kann sich die Zuordnung eines Formulars zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="65020-334">Nein, sobald ein Formular einer Gruppe zugeordnet ist (entweder direkt innerhalb erstellt oder von einer Person übertragen) kann es nicht in eine andere Gruppe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="65020-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="65020-335">**Löscht das Löschen des Formulars die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="65020-336">Nein, es ist nicht möglich, eine Gruppe aus der Forms-Schnittstelle zu löschen, sondern nur einzelne Formulare.</span><span class="sxs-lookup"><span data-stu-id="65020-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="65020-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="65020-337">OneNote</span></span>

<span data-ttu-id="65020-338">OneNote ist eine digitale Notizbuchanwendung.</span><span class="sxs-lookup"><span data-stu-id="65020-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="65020-339">Das mit einer Gruppe erstellte OneNote-Notizbuch ist eine Datei auf der zugeordneten SharePoint-Website und nicht ein mit einer Gruppe verbundener Dienst.</span><span class="sxs-lookup"><span data-stu-id="65020-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="65020-340">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="65020-341">Freigegebenes Notizbuch (gespeichert in der mit der Gruppe verknüpften SharePoint-Bibliothek)</span><span class="sxs-lookup"><span data-stu-id="65020-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="65020-342">**Kann OneNote eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="65020-343">Nein, die OneNote-Anwendung kann keine Gruppe erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="65020-344">**Sind OneNote-Notizbücher ohne Gruppe vorhanden?**</span><span class="sxs-lookup"><span data-stu-id="65020-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="65020-345">Ja, Notizbücher können direkt in OneDrive oder an anderen freigegebenen Speicherorten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="65020-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="65020-346">**Gibt es mehrere OneNote-Notizbücher pro Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="65020-347">Ja, ein Notizbuch wird standardmäßig erstellt, und andere können hinzugefügt werden. Jeder Link zu OneNote von gruppenverknüpfungen Diensten wird jedoch immer zum Standardnotizbuch verwendet.</span><span class="sxs-lookup"><span data-stu-id="65020-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="65020-348">**Kann ein OneNote-Notizbuch mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-349">Nein, das Notizbuch wird in der gruppenverknüpften SharePoint-Websitebibliothek gespeichert und über verschiedene Schnittstellen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="65020-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="65020-350">Sie kann jedoch auf die gleiche Weise für andere Gruppen freigegeben werden, wie sie für Einzelpersonen freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="65020-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="65020-351">**Kann sich die Zuordnung des Notizbuchs zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="65020-352">Nein, das Notizbuch selbst ist der Gruppe zugeordnet und kann direkt von anderen gruppengebundenen Diensten aus zugegriffen werden. Der Inhalt kann jedoch innerhalb der OneNote-Anwendung von einem Notizbuch in ein anderes verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="65020-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="65020-353">**Löscht das Löschen des Notizbuchs die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="65020-354">Nein, wenn das OneNote-Notizbuch jedoch gelöscht wird, gibt es möglicherweise beschädigte Links in einigen der gruppenverknüpfungen Dienste.</span><span class="sxs-lookup"><span data-stu-id="65020-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="65020-355">Planner</span><span class="sxs-lookup"><span data-stu-id="65020-355">Planner</span></span>

<span data-ttu-id="65020-356">Planner ist ein einfacher Gruppenaufgabeverwaltungsdienst.</span><span class="sxs-lookup"><span data-stu-id="65020-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="65020-357">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="65020-358">Board für die Verwaltung von Gruppenaufgaben</span><span class="sxs-lookup"><span data-stu-id="65020-358">Board for managing group tasks</span></span>

<span data-ttu-id="65020-359">**Kann Planner eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="65020-360">Ja, beim Erstellen eines Plans wird eine neue Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="65020-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="65020-361">**Gibt es ein Planner-Board ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="65020-362">Nein, ein Plan muss einer Gruppe zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="65020-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="65020-363">**Gibt es mehrere Pläne pro Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="65020-364">Ja, es können mehrere Pläne pro Gruppe möglich sein.</span><span class="sxs-lookup"><span data-stu-id="65020-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="65020-365">**Kann ein Plan mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-366">Nein, ein Plan basiert ausschließlich auf der Gruppenmitgliedschaft, um den Zugriff zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="65020-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="65020-367">**Kann sich die Zuordnung eines Plans zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="65020-368">Nein, beim Kopieren eines Plans wird jedoch eine neue Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="65020-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="65020-369">Eine von einer anderen Anwendung erstellte Gruppe wird für einen Benutzer nicht automatisch in Planner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65020-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="65020-370">Für den anfänglichen Zugriff auf das Board müssen sie es über eine andere gruppenbasierte Schnittstelle wie Outlook öffnen.</span><span class="sxs-lookup"><span data-stu-id="65020-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="65020-371">**Löscht das Löschen des Plans die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="65020-372">Ja, beim Löschen des Plans werden die gruppen- und gruppenverkn nenten Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="65020-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="65020-373">Power-Apps</span><span class="sxs-lookup"><span data-stu-id="65020-373">Power Apps</span></span>

<span data-ttu-id="65020-374">Power Apps bietet einen Canvas für die App-Entwicklung ohne Code.</span><span class="sxs-lookup"><span data-stu-id="65020-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="65020-375">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="65020-376">Apps können für eine Gruppe freigegeben werden, die ausgeführt und geändert werden soll</span><span class="sxs-lookup"><span data-stu-id="65020-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="65020-377">**Kann Power Apps eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="65020-378">Nein, Power Apps kann keine Microsoft 365-Gruppe erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="65020-379">**Gibt es Power Apps ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="65020-380">Ja, apps can be created within Power Apps and reside within the creators account until shared or published.</span><span class="sxs-lookup"><span data-stu-id="65020-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="65020-381">**Gibt es mehrere Apps pro Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="65020-382">Ja, es können mehrere Apps für eine Gruppe freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="65020-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="65020-383">**Können Apps mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-384">Ja, eine App kann für mehrere Gruppen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="65020-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="65020-385">**Kann sich die Zuordnung einer App zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="65020-386">Ja, da die Zuordnung zwischen Power Apps und einer Microsoft 365-Gruppe nur geteilt wird – die App befindet sich weiterhin beim Ersteller.</span><span class="sxs-lookup"><span data-stu-id="65020-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65020-387">[Gruppen müssen für die Sicherheit aktiviert sein, bevor Apps für sie freigegeben werden können.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="65020-387">[Groups must be security enabled before apps can be shared with them](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="65020-388">**Löscht das Löschen der App die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="65020-389">Nein, die Apps sind nicht mit der Gruppe verbunden, es sei denn, sie werden für sie freigegeben.</span><span class="sxs-lookup"><span data-stu-id="65020-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="65020-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="65020-390">Power Automate</span></span>

<span data-ttu-id="65020-391">Power Automate (früher als Microsoft Flow bezeichnet) bietet Workflows und Automatisierungsdienste.</span><span class="sxs-lookup"><span data-stu-id="65020-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="65020-392">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="65020-393">Workflows können für eine Gruppe freigegeben werden, die ausgeführt und geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="65020-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="65020-394">**Kann Power Automate eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="65020-395">Nein, Power Automate kann keine Microsoft 365-Gruppe im Kontext einer zugeordneten Gruppe erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="65020-396">Es ist jedoch möglich, einen Fluss zu erstellen, der verschiedene Vorgänge ausführt, z. B. das Erstellen einer Azure AD-Sicherheitsgruppe oder das Aktualisieren der Mitgliedschaft in einer Microsoft 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="65020-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="65020-397">**Gibt es Flüsse ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="65020-398">Ja, Flüsse können innerhalb von Power Automate erstellt werden und sich innerhalb des Erstellerkontos befinden, bis sie freigegeben oder veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="65020-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="65020-399">**Kann es mehrere Flüsse pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="65020-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="65020-400">Ja, es können mehrere Flüsse für eine Gruppe freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="65020-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="65020-401">**Kann ein Fluss mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-402">Ja, ein Fluss kann für mehrere Gruppen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="65020-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="65020-403">**Kann sich die Zuordnung eines Fluss zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="65020-404">Ja, da die Zuordnung zwischen Power Automate und einer Microsoft 365-Gruppe nur gemeinsam verwendet wird – der Fluss befindet sich weiterhin beim Ersteller.</span><span class="sxs-lookup"><span data-stu-id="65020-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="65020-405">**Löscht das Löschen eines Datenflusses die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="65020-406">Nein, wie Power Apps sind die Flüsse nicht mit der Gruppe verbunden, es sei denn, sie werden für sie freigegeben.</span><span class="sxs-lookup"><span data-stu-id="65020-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="65020-407">Power BI (klassisch)</span><span class="sxs-lookup"><span data-stu-id="65020-407">Power BI (classic)</span></span>

<span data-ttu-id="65020-408">Power BI bietet interaktive datengesteuerte Dashboards und Berichte.</span><span class="sxs-lookup"><span data-stu-id="65020-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="65020-409">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="65020-410">Datenberichte</span><span class="sxs-lookup"><span data-stu-id="65020-410">Data reporting</span></span>

<span data-ttu-id="65020-411">**Kann Power BI eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="65020-412">Ja, beim Erstellen eines klassischen Arbeitsbereichs wird eine Microsoft 365-Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="65020-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="65020-413">**Gibt es einen klassischen Power BI-Arbeitsbereich ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="65020-414">Nein, [ein klassischer Arbeitsbereich in Power BI muss einer Gruppe zugeordnet sein.](/power-bi/collaborate-share/service-collaborate-power-bi-workspace)</span><span class="sxs-lookup"><span data-stu-id="65020-414">No, [a classic workspace in Power BI must be associated with a group](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="65020-415">**Gibt es mehrere Power BI-Arbeitsbereiche pro Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="65020-416">Nein, die Beziehung zwischen einem klassischen Arbeitsbereich und einer Gruppe ist 1:1.</span><span class="sxs-lookup"><span data-stu-id="65020-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="65020-417">**Kann ein Arbeitsbereich mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-418">Technisch nein, während der klassische Arbeitsbereich mit der Gruppe erstellt wird, können die Inhalte außerhalb der Gruppe für Benutzer und Sicherheitsgruppen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="65020-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="65020-419">**Kann sich die Zuordnung des Arbeitsbereichs zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="65020-420">Nein, der klassische Arbeitsbereich selbst ist der Gruppe zugeordnet, der Inhalt kann jedoch innerhalb der Power BI-Schnittstelle oder durch lokales Exportieren von Inhalten von einem Arbeitsbereich in einen anderen verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="65020-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="65020-421">**Löscht das Löschen des Arbeitsbereichs die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="65020-422">Ja, beim Löschen des Arbeitsbereichs in Power BI werden Gruppen- und gruppenverkn nente Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="65020-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="65020-423">Power BI (neu)</span><span class="sxs-lookup"><span data-stu-id="65020-423">Power BI (new)</span></span>

<span data-ttu-id="65020-424">Power BI bietet interaktive datengesteuerte Dashboards und Berichte.</span><span class="sxs-lookup"><span data-stu-id="65020-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="65020-425">Während das Erstellen eines neuen Arbeitsbereichs in Power BI keine Microsoft 365-Gruppe erstellt, erstellt das Erstellen einer Gruppe auf andere Weise einen neuen (nicht klassischen) Arbeitsbereich in Power BI.</span><span class="sxs-lookup"><span data-stu-id="65020-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="65020-426">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="65020-427">Datenberichte</span><span class="sxs-lookup"><span data-stu-id="65020-427">Data reporting</span></span>

<span data-ttu-id="65020-428">**Kann Power BI eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="65020-429">Nein, es ist nicht möglich, eine Microsoft 365-Gruppe über die neue Power BI-Schnittstelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="65020-430">**Gibt es den neuen Power BI-Arbeitsbereich ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="65020-431">Ja, es ist möglich, Berichte und Arbeitsbereiche in Power BI zu erstellen, die nicht Microsoft 365-Gruppen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="65020-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="65020-432">**Kann es mehrere Arbeitsbereiche pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="65020-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="65020-433">Ja, mehrere von Power BI erstellte [Arbeitsbereiche können für eine einzelne Gruppe freigegeben werden.](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)</span><span class="sxs-lookup"><span data-stu-id="65020-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="65020-434">**Kann ein Arbeitsbereich mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-435">Nein, ein von Power BI erstellter Arbeitsbereich kann nur einer einzelnen Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="65020-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="65020-436">**Kann sich die Zuordnung eines Arbeitsbereichs zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="65020-437">Ja und Nein.</span><span class="sxs-lookup"><span data-stu-id="65020-437">Yes and no.</span></span> <span data-ttu-id="65020-438">Ein von Power BI erstellter Arbeitsbereich kann immer nur einer einzelnen Gruppe zugeordnet werden, kann die Zuordnung jedoch jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="65020-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="65020-439">Ein arbeitsbereich, der in Power BI von einer Gruppe erstellt wurde, ist dieser Gruppe dauerhaft zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="65020-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="65020-440">**Löscht das Löschen des Arbeitsbereichs die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="65020-441">Ja, durch löschen des Arbeitsbereichs in Power BI werden die gruppen- und gruppenverkn nenten Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="65020-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="65020-442">Project für das Web</span><span class="sxs-lookup"><span data-stu-id="65020-442">Project for the web</span></span>

<span data-ttu-id="65020-443">Project for the web bietet die Möglichkeit, Projektpläne, Gantt-Diagramme und Roadmaps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="65020-444">Wichtige Features, die Gruppen zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="65020-444">Key features provided to groups.</span></span>

- <span data-ttu-id="65020-445">Projektpläne</span><span class="sxs-lookup"><span data-stu-id="65020-445">Project plans</span></span>

<span data-ttu-id="65020-446">**Kann Project for the web eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="65020-447">Ja, es ist möglich, eine neue Microsoft 365-Gruppe direkt aus Project für das Web zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="65020-448">**Sind Projekte ohne Gruppe vorhanden?**</span><span class="sxs-lookup"><span data-stu-id="65020-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="65020-449">Ja, Projekte können vorhanden sein, ohne einer Microsoft 365-Gruppe zugeordnet zu werden, die Zuweisung von Aufgaben erfordert jedoch eine Gruppenzuordnung.</span><span class="sxs-lookup"><span data-stu-id="65020-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="65020-450">**Gibt es mehrere Projekte pro Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="65020-451">Ja, es ist möglich, mehrere Projekte in einer einzelnen Gruppe zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="65020-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="65020-452">**Kann Projekt mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-453">Nein, ein Projekt kann nur einer einzelnen Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="65020-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="65020-454">**Kann sich die Zuordnung eines Projekts zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="65020-455">Nein, sobald die Zuordnung zu einer Gruppe eingerichtet wurde, kann sie sich nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="65020-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="65020-456">**Löscht das Löschen des Projekts die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="65020-457">Nein, das Löschen des Projekts in Project für das Web löscht die Gruppe nicht.</span><span class="sxs-lookup"><span data-stu-id="65020-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="65020-458">Roadmap</span><span class="sxs-lookup"><span data-stu-id="65020-458">Roadmap</span></span>

<span data-ttu-id="65020-459">Roadmap bietet die Möglichkeit, Projektpläne mit Project für das Web und Project Online zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="65020-460">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="65020-461">Projekt-Roadmaps</span><span class="sxs-lookup"><span data-stu-id="65020-461">Project roadmaps</span></span>

<span data-ttu-id="65020-462">**Kann roadmap eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="65020-463">Ja, es ist möglich, eine neue Microsoft 365-Gruppe direkt aus der Roadmap zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="65020-464">**Gibt es Roadmap ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="65020-465">Ja, Roadmaps können vorhanden sein, ohne einer Microsoft 365-Gruppe zugeordnet zu werden, die Freigabe der Roadmap erfordert jedoch eine Gruppenverbundung.</span><span class="sxs-lookup"><span data-stu-id="65020-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="65020-466">**Gibt es mehrere Roadmaps pro Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="65020-467">Ja, es ist möglich, mehrere Roadmaps mit einer einzelnen Gruppe zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="65020-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="65020-468">**Kann eine Roadmap mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-469">Nein, eine Roadmap kann nur einer einzelnen Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="65020-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="65020-470">**Kann sich die Zuordnung einer Roadmap zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="65020-471">Nein, sobald die Zuordnung zu einer Gruppe eingerichtet wurde, kann sie sich nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="65020-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="65020-472">**Löscht das Löschen der Roadmap die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="65020-473">Nein, beim Löschen der Roadmap wird die Gruppe nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="65020-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="65020-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="65020-474">SharePoint</span></span>

<span data-ttu-id="65020-475">SharePoint ist eine webbasierte Inhaltsverwaltungsplattform, die unter anderem Speicherdienste für eine Reihe von Microsoft 365-Diensten bietet.</span><span class="sxs-lookup"><span data-stu-id="65020-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="65020-476">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="65020-477">Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="65020-477">Document library</span></span>
- <span data-ttu-id="65020-478">Bibliothek zum Speichern von OneNote-Notizbüchern</span><span class="sxs-lookup"><span data-stu-id="65020-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="65020-479">Speichern von Teams-Wiki-Dateien</span><span class="sxs-lookup"><span data-stu-id="65020-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="65020-480">**Kann SharePoint eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="65020-481">Ja, das Erstellen einer Teamwebsite in SharePoint erstellt standardmäßig eine Microsoft 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="65020-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="65020-482">Es ist auch möglich, eine Gruppe und optional ein Team für eine vorhandene Website zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="65020-483">**Gibt es SharePoint-Websites ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="65020-484">Ja, SharePoint bietet eine Reihe von Nicht-Gruppen zugeordneten Diensten und Websites, z. B. Kommunikations- und Hubwebsites.</span><span class="sxs-lookup"><span data-stu-id="65020-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="65020-485">**Kann es mehrere Websites pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="65020-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="65020-486">Nein, es kann nur eine einzelne Website pro Gruppe vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="65020-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="65020-487">Private Kanäle in Teams verwenden zusätzliche Websites, die nicht mit der Gruppe verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="65020-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="65020-488">**Können Websites mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-489">Technisch nein, aber während eine Website mit einer Gruppe erstellt wird, kann der Inhalt für andere Gruppen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="65020-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="65020-490">**Kann sich die Zuordnung einer Website zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="65020-491">Nein, die Website selbst ist der Gruppe zugeordnet, der Inhalt kann jedoch innerhalb der SharePoint-Schnittstelle von einer Website auf eine andere verschoben werden, indem Inhalte lokal exportiert oder ein Drittanbietertool verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="65020-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="65020-492">**Löscht das Löschen der Website die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="65020-493">Ja, wenn Sie die Website in SharePoint löschen, werden Gruppen- und Gruppen zugeordnete Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="65020-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="65020-494">Stream</span><span class="sxs-lookup"><span data-stu-id="65020-494">Stream</span></span>

<span data-ttu-id="65020-495">Microsoft Stream ist eine Videohosting- und Freigabeplattform.</span><span class="sxs-lookup"><span data-stu-id="65020-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="65020-496">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="65020-497">Videospeicherung</span><span class="sxs-lookup"><span data-stu-id="65020-497">Video storage</span></span>
- <span data-ttu-id="65020-498">Aufzeichnung von Teams-Besprechungen</span><span class="sxs-lookup"><span data-stu-id="65020-498">Teams meeting recording</span></span>
- <span data-ttu-id="65020-499">Videokanäle</span><span class="sxs-lookup"><span data-stu-id="65020-499">Video channels</span></span>

<span data-ttu-id="65020-500">**Kann Stream eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="65020-501">Ja, es ist möglich, eine neue Microsoft 365-Gruppe direkt aus Stream zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="65020-502">**Gibt es Stream ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="65020-503">Ja, Videokanäle und Videos können in Stream vorhanden sein, ohne einer Gruppe zugeordnet zu werden.</span><span class="sxs-lookup"><span data-stu-id="65020-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="65020-504">**Gibt es mehrere Videos und Kanäle pro Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="65020-505">Ja, es können mehrere Videos und Kanäle in jeder Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="65020-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="65020-506">**Kann ein Video oder kanal mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="65020-507">Ja, während ein Video oder Kanal mit einer Gruppe erstellt wird, kann es für andere Gruppen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="65020-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="65020-508">**Kann sich die Zuordnung zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="65020-509">Ja und Nein; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can be associated with the group they were originally created in.</span><span class="sxs-lookup"><span data-stu-id="65020-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="65020-510">**Löscht das Löschen von Videos oder Kanälen die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="65020-511">Nein, das Löschen von Videos oder Kanälen löscht die Gruppe nicht.</span><span class="sxs-lookup"><span data-stu-id="65020-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="65020-512">Durch das Löschen der Gruppe selbst in Stream werden jedoch gruppen zugeordnete Dienste und Inhalte gelöscht, mit Ausnahme der tatsächlichen Videos.</span><span class="sxs-lookup"><span data-stu-id="65020-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="65020-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="65020-513">Yammer</span></span>

<span data-ttu-id="65020-514">Yammer ist eine soziale Plattform für Unternehmen, die das Engagement der Community innerhalb und zwischen Organisationen fördert.</span><span class="sxs-lookup"><span data-stu-id="65020-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="65020-515">Das Erstellen einer Community (früher als "Gruppe" bezeichnet) in Yammer erstellt ein Postfach, wird aber derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="65020-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="65020-516">Eine Microsoft 365-Gruppe, die einem Yammer zugeordnet ist, kann nicht mit einem Team in Microsoft Teams verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65020-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="65020-517">**Wichtige Features für Gruppen**</span><span class="sxs-lookup"><span data-stu-id="65020-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="65020-518">Unterhaltungsbereich</span><span class="sxs-lookup"><span data-stu-id="65020-518">Conversation area</span></span>

<span data-ttu-id="65020-519">**Können Yammer Microsoft 365-Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="65020-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="65020-520">Ja, das Erstellen einer neuen Gruppe in Yammer erstellt eine neue Microsoft 365-Gruppe, wenn die Plattformen verbunden sind und der Benutzer die Möglichkeit hat, eine Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="65020-521">Eine Yammer der zugeordneten Microsoft 365-Gruppe kann nicht in einer anderen Schnittstelle oder einem Dienst als in Yammer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="65020-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="65020-522">**Ist eine Yammer ohne Microsoft 365-Gruppe vorhanden?**</span><span class="sxs-lookup"><span data-stu-id="65020-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="65020-523">Ja, es ist möglich, eine Yammer ohne Microsoft 365-Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65020-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="65020-524">Wenn die Yammer-Plattform nicht mit Microsoft 365-Gruppen verbunden ist oder Benutzer nicht in der Lage sind, eine Microsoft 365-Gruppe zu erstellen, werden Yammer-Gruppen ohne Microsoft 365-Gruppen zuordnung erstellt.</span><span class="sxs-lookup"><span data-stu-id="65020-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="65020-525">**Gibt es mehrere Yammer gruppen pro Microsoft 365-Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="65020-526">Nein, die Beziehung zwischen einer Yammer und einer Microsoft 365-Gruppe ist 1:1.</span><span class="sxs-lookup"><span data-stu-id="65020-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="65020-527">**Kann eine Yammer mehreren Microsoft 365-Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="65020-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="65020-528">Nein, die Yammer kann nur einer einzelnen Microsoft 365-Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="65020-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="65020-529">Es ist möglich, dass Beiträge für andere Benutzergruppen freigegeben oder Yammer werden.</span><span class="sxs-lookup"><span data-stu-id="65020-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="65020-530">**Kann sich Yammer Zuordnung einer Gruppe mit einer Microsoft 365-Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="65020-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="65020-531">Nein, die Yammer kann nur der Microsoft 365-Gruppe zugeordnet werden, der sie ursprünglich zugeordnet war.</span><span class="sxs-lookup"><span data-stu-id="65020-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="65020-532">**Löscht das Löschen Yammer Gruppe die Microsoft 365-Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="65020-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="65020-533">Ja, durch das Löschen der Gruppe in Yammer werden verwandte Microsoft-Gruppen- und gruppenbezogene Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="65020-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="65020-534">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="65020-534">Related topics</span></span>

[<span data-ttu-id="65020-535">Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="65020-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="65020-536">Erstellen eines Plans für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="65020-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)