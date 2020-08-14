---
title: Gruppen Dienst Interaktionen
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Gruppen Dienst Interaktionen
ms.openlocfilehash: 9632debf1bc6fdd2fce061a4c535906410700175
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662659"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="86e1f-103">Gruppen Dienst Interaktionen</span><span class="sxs-lookup"><span data-stu-id="86e1f-103">Groups services interactions</span></span>

<span data-ttu-id="86e1f-104">Microsoft 365 Groups stellt eine allgemeine Struktur für eine Reihe von Diensten und Arbeitslasten innerhalb der Microsoft 365-Plattform bereit, um eine verbundene Benutzeroberfläche für Endbenutzer zu bieten.</span><span class="sxs-lookup"><span data-stu-id="86e1f-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="86e1f-105">In seinem Kern besteht eine Microsoft 365-Gruppe, die Folgendes bereitstellt:</span><span class="sxs-lookup"><span data-stu-id="86e1f-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="86e1f-106">Eine Möglichkeit zum Verwalten der Mitgliedschaft (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="86e1f-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="86e1f-107">Ein Ort, an dem Messaging und Unterhaltungen stattfinden (Exchange-Postfach, Microsoft Teams, jammern)</span><span class="sxs-lookup"><span data-stu-id="86e1f-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="86e1f-108">Platz für Dateien, die gespeichert werden sollen (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="86e1f-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="86e1f-109">Ein Kalender für die Planung (Exchange)</span><span class="sxs-lookup"><span data-stu-id="86e1f-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="86e1f-110">Ein Notizbuch zum Erfassen von Notizen (OneNote)</span><span class="sxs-lookup"><span data-stu-id="86e1f-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="86e1f-111">Zum Zeitpunkt der Gruppenerstellung wird auch eine Reihe von anderen Ressourcen bereitgestellt, die jedoch erst sichtbar sind, wenn Sie zum ersten Mal aus dem Dienst abgerufen wurden:</span><span class="sxs-lookup"><span data-stu-id="86e1f-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="86e1f-112">Ein Board für die Verwaltung von Gruppenaufgaben (Planer)</span><span class="sxs-lookup"><span data-stu-id="86e1f-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="86e1f-113">Ein Arbeitsbereich für die Berichterstellung (Power BI)</span><span class="sxs-lookup"><span data-stu-id="86e1f-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="86e1f-114">Ein Bereich für freigegebene Videos (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="86e1f-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="86e1f-115">Ein Bereich für freigegebene Formulare (Formulare)</span><span class="sxs-lookup"><span data-stu-id="86e1f-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="86e1f-116">In Microsoft 365 können andere Dienste mit Microsoft 365-Gruppen interagieren, um zusätzliche Funktionen und Funktionen für Gruppenmitglieder bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="86e1f-117">Beispiele hierfür sind:</span><span class="sxs-lookup"><span data-stu-id="86e1f-117">Examples of this include:</span></span>

- <span data-ttu-id="86e1f-118">Power Apps für apps</span><span class="sxs-lookup"><span data-stu-id="86e1f-118">Power Apps for apps</span></span>
- <span data-ttu-id="86e1f-119">Power Automation für Workflows</span><span class="sxs-lookup"><span data-stu-id="86e1f-119">Power Automate for workflows</span></span>
- <span data-ttu-id="86e1f-120">Project im Internet und Roadmap für Wasserfall basierte Projektverwaltung</span><span class="sxs-lookup"><span data-stu-id="86e1f-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="86e1f-121">Teams für kanalbasierte Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="86e1f-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="86e1f-122">Jammern für Interessengemeinschaften</span><span class="sxs-lookup"><span data-stu-id="86e1f-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="86e1f-123">Benutzerinteraktionen mit Gruppen</span><span class="sxs-lookup"><span data-stu-id="86e1f-123">User interactions with groups</span></span>

<span data-ttu-id="86e1f-124">Microsoft 365-Gruppen können von einer Vielzahl von Schnittstellen sowohl von Administratoren als auch von Endbenutzern erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="86e1f-125">Administrative Erfahrungen</span><span class="sxs-lookup"><span data-stu-id="86e1f-125">Administrative experiences</span></span>

<span data-ttu-id="86e1f-126">Administratoren können Microsoft 365-Gruppen aus mehreren der Arbeits Auslastungs-Admin Center, Befehlszeilenschnittstellen, die Skripts unterstützen, sowie von benutzerdefinierten apps, die mit der Graph-API interagieren, erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="86e1f-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="86e1f-127">Die einzige Ausnahme hiervon sind Jammer Gruppen, die innerhalb der Jammer-Weboberfläche erstellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="86e1f-128">**Verwandte Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="86e1f-128">**Related settings**</span></span>

<span data-ttu-id="86e1f-129">In den verschiedenen administrativen Schnittstellen, die Gruppeneinstellungen verwalten können, gibt es mehrere Überschneidungen, die Sie beachten sollten.</span><span class="sxs-lookup"><span data-stu-id="86e1f-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="86e1f-130">**Microsoft 365 Admin Center**</span><span class="sxs-lookup"><span data-stu-id="86e1f-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="86e1f-131">Im Microsoft 365 Admin Center ist Gastzugriff auf Gruppen standardmäßig aktiviert, ebenso wie die Möglichkeit, Besitzern das Hinzufügen von Gästen zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="86e1f-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="86e1f-132">In diesem Admin Center stehen keine weiteren Steuerelemente auf Organisationsebene für Gruppen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="86e1f-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="86e1f-133">**Azure AD Admin Center**</span><span class="sxs-lookup"><span data-stu-id="86e1f-133">**Azure AD admin center**</span></span>

<span data-ttu-id="86e1f-134">Das Azure AD Admin Center bietet Steuerelemente, um festzustellen, ob Benutzergruppen erstellen oder Besitzer in Azure-Portalen zuweisen können, sowie Ablauf-und Benennungsrichtlinien Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="86e1f-135">Das Admin Center bietet auch eine Reihe von Kontrollmaßnahmen für Gast Einladungen, die über das Microsoft 365 Admin Center hinausgehen, beispielsweise die Möglichkeit zu begrenzen, ob nicht-Besitzer auch Gäste einladen können.</span><span class="sxs-lookup"><span data-stu-id="86e1f-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="86e1f-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="86e1f-136">**SharePoint**</span></span>

<span data-ttu-id="86e1f-137">SharePoint-Websites werden mit den Sicherheitsgruppen "Besitzer", "Mitglied" und "Besucher" erstellt, wobei die ersten beiden mit Ihren Microsoft 365-Gruppen Kollegen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="86e1f-138">Während die Mitgliedschaft für SharePoint Online Websites in der Regel von der zugeordneten Microsoft 365-Gruppe verwaltet wird, handelt es sich nicht um eine bidirektionale Beziehung.</span><span class="sxs-lookup"><span data-stu-id="86e1f-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="86e1f-139">Alle Änderungen an der Mitgliedschaft auf der Microsoft 365-Gruppenebene spiegeln sich in SharePoint wider, wenn sich die Mitgliedschaft in der SharePoint-Gruppe jedoch ändert, wird dies nicht in der Microsoft 365-Gruppe widergespiegelt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="86e1f-140">Benutzeroberflächen</span><span class="sxs-lookup"><span data-stu-id="86e1f-140">User experiences</span></span>

<span data-ttu-id="86e1f-141">Endbenutzer können Gruppen aus mehreren der Dienste in Microsoft 365 erstellen, und in anderen können Sie nur für eine Gruppe freigeben.</span><span class="sxs-lookup"><span data-stu-id="86e1f-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="86e1f-142">Die folgenden Dienste ermöglichen die Erstellung von Gruppen durch Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="86e1f-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="86e1f-143">Outlook Planner-Projekt für den SharePoint-Stream von Microsoft Teams jammern</span><span class="sxs-lookup"><span data-stu-id="86e1f-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="86e1f-144">**Einschränkung der Gruppenerstellung**</span><span class="sxs-lookup"><span data-stu-id="86e1f-144">**Restriction of group creation**</span></span>

<span data-ttu-id="86e1f-145">Ein allgemeiner Ansatz zur Steuerung der Ausbreitung von Teams besteht darin, zu begrenzen, welche Benutzer diese erstellen können.</span><span class="sxs-lookup"><span data-stu-id="86e1f-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="86e1f-146">Dies kann nur durch Einschränken der Gruppenerstellung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="86e1f-147">Dies wirkt sich auf die Möglichkeit aus, Gruppen aus anderen Diensten zu erstellen, die für Endbenutzer möglicherweise erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="86e1f-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="86e1f-148">Microsoft 365-Gruppen unterstützen nicht die Möglichkeit, die Erstellung von Gruppen für einige apps oder Dienste einzuschränken, während Sie von anderen Benutzern zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="86e1f-149">Die Einschränkungen bei der Gruppenerstellung sind zwischen apps und Diensten unterschiedlich:</span><span class="sxs-lookup"><span data-stu-id="86e1f-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="86e1f-150">APP oder Dienst</span><span class="sxs-lookup"><span data-stu-id="86e1f-150">App or service</span></span>|<span data-ttu-id="86e1f-151">Umgebung</span><span class="sxs-lookup"><span data-stu-id="86e1f-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="86e1f-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="86e1f-152">Outlook</span></span>|<span data-ttu-id="86e1f-153">**Neue Gruppen** Option wird aus dem Menü "neu" auf der Seite "Personen" entfernt</span><span class="sxs-lookup"><span data-stu-id="86e1f-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="86e1f-154">Planner</span><span class="sxs-lookup"><span data-stu-id="86e1f-154">Planner</span></span>|<span data-ttu-id="86e1f-155">In **neuem Plan** wird erklärt, dass die Gruppenerstellung deaktiviert wurde und das Hinzufügen des Plans zu einer vorhandenen Gruppe angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="86e1f-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="86e1f-156">Projekt für das Internet und Roadmap</span><span class="sxs-lookup"><span data-stu-id="86e1f-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="86e1f-157">Im Menü **Gruppe erstellen** wird erklärt, dass die Gruppenerstellung eingeschränkt ist und eine vorhandene Gruppe verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="86e1f-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="86e1f-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="86e1f-158">SharePoint</span></span>|<span data-ttu-id="86e1f-159">Weiterhin in der Lage, eine Teamwebsite zu erstellen, die nicht mit einer Gruppe verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="86e1f-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="86e1f-160">Stream</span><span class="sxs-lookup"><span data-stu-id="86e1f-160">Stream</span></span>|<span data-ttu-id="86e1f-161">Die Option **Gruppieren** wird nicht unter dem **Menü Erstellen**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="86e1f-162">Teams</span><span class="sxs-lookup"><span data-stu-id="86e1f-162">Teams</span></span>|<span data-ttu-id="86e1f-163">Der Benutzer kann kein Team mit einer neuen Gruppe erstellen, aber trotzdem ein Team erstellen, das eine vorhandene Gruppe verwendet.</span><span class="sxs-lookup"><span data-stu-id="86e1f-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="86e1f-164">**Die Schaltfläche Team erstellen** wird durch **Team erstellen aus einer Gruppe**ersetzt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="86e1f-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="86e1f-165">Yammer</span></span>|<span data-ttu-id="86e1f-166">**Die Option "Gruppe erstellen** " wird aus der Navigation der Hauptgruppen/Communitys entfernt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="86e1f-167">Dienst Interaktionen mit Gruppen</span><span class="sxs-lookup"><span data-stu-id="86e1f-167">Services interactions with groups</span></span>

<span data-ttu-id="86e1f-168">Auf dem Poster "Groups in Microsoft 365" finden Sie Informationen zu unterschiedlichen Gruppentypen, zu deren Erstellung und Verwaltung sowie zu einigen Governance-Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="86e1f-169">[![Miniaturbild für Gruppen-Infografik](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="86e1f-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="86e1f-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="86e1f-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="86e1f-171">Die folgende Tabelle enthält eine Übersicht über die Interaktionen von Microsoft 365-Gruppen mit verschiedenen Diensten:</span><span class="sxs-lookup"><span data-stu-id="86e1f-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="86e1f-172">Produkt</span><span class="sxs-lookup"><span data-stu-id="86e1f-172">Product</span></span>|<span data-ttu-id="86e1f-173">Features</span><span class="sxs-lookup"><span data-stu-id="86e1f-173">Features</span></span>|<span data-ttu-id="86e1f-174">Übernimmt der Dienst</span><span class="sxs-lookup"><span data-stu-id="86e1f-174">Does the service</span></span><br><span data-ttu-id="86e1f-175">ohne Gruppe vorhanden?</span><span class="sxs-lookup"><span data-stu-id="86e1f-175">exist without a group?</span></span>|<span data-ttu-id="86e1f-176">Kann der Dienst</span><span class="sxs-lookup"><span data-stu-id="86e1f-176">Can the service</span></span><br><span data-ttu-id="86e1f-177">Gruppe erstellen?</span><span class="sxs-lookup"><span data-stu-id="86e1f-177">create a group?</span></span>|<span data-ttu-id="86e1f-178">Löscht das</span><span class="sxs-lookup"><span data-stu-id="86e1f-178">Does deleting the</span></span><br><span data-ttu-id="86e1f-179">Instanz löschen der Gruppe?</span><span class="sxs-lookup"><span data-stu-id="86e1f-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="86e1f-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="86e1f-180">Azure AD</span></span>|<span data-ttu-id="86e1f-181">Mitgliedschaft, gruppensteuerelemente, Gäste</span><span class="sxs-lookup"><span data-stu-id="86e1f-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="86e1f-182">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-182">Yes</span></span>|<span data-ttu-id="86e1f-183">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-183">Yes</span></span>|<span data-ttu-id="86e1f-184">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-184">Yes</span></span>|
|<span data-ttu-id="86e1f-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="86e1f-185">Exchange</span></span>|<span data-ttu-id="86e1f-186">Kalender, Postfach</span><span class="sxs-lookup"><span data-stu-id="86e1f-186">Calendar, mailbox</span></span>|<span data-ttu-id="86e1f-187">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-187">Yes</span></span>|<span data-ttu-id="86e1f-188">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-188">Yes</span></span>|<span data-ttu-id="86e1f-189">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-189">Yes</span></span>|
|<span data-ttu-id="86e1f-190">Formulare</span><span class="sxs-lookup"><span data-stu-id="86e1f-190">Forms</span></span>|<span data-ttu-id="86e1f-191">Formular</span><span class="sxs-lookup"><span data-stu-id="86e1f-191">Form</span></span>|<span data-ttu-id="86e1f-192">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-192">Yes</span></span>|<span data-ttu-id="86e1f-193">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-193">No</span></span>|<span data-ttu-id="86e1f-194">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-194">No</span></span>|
|<span data-ttu-id="86e1f-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="86e1f-195">OneNote</span></span>|<span data-ttu-id="86e1f-196">Notizbuch</span><span class="sxs-lookup"><span data-stu-id="86e1f-196">Notebook</span></span>|<span data-ttu-id="86e1f-197">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-197">Yes</span></span>|<span data-ttu-id="86e1f-198">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-198">No</span></span>|<span data-ttu-id="86e1f-199">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-199">No</span></span>|
|<span data-ttu-id="86e1f-200">Planner</span><span class="sxs-lookup"><span data-stu-id="86e1f-200">Planner</span></span>|<span data-ttu-id="86e1f-201">Aufgaben Ausschuss</span><span class="sxs-lookup"><span data-stu-id="86e1f-201">Task board</span></span>|<span data-ttu-id="86e1f-202">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-202">No</span></span>|<span data-ttu-id="86e1f-203">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-203">Yes</span></span>|<span data-ttu-id="86e1f-204">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-204">Yes</span></span>|
|<span data-ttu-id="86e1f-205">Power apps-App</span><span class="sxs-lookup"><span data-stu-id="86e1f-205">Power Apps app</span></span>|<span data-ttu-id="86e1f-206">App</span><span class="sxs-lookup"><span data-stu-id="86e1f-206">App</span></span>|<span data-ttu-id="86e1f-207">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-207">Yes</span></span>|<span data-ttu-id="86e1f-208">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-208">No</span></span>|<span data-ttu-id="86e1f-209">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-209">No</span></span>|
|<span data-ttu-id="86e1f-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="86e1f-210">Power Automate</span></span>|<span data-ttu-id="86e1f-211">Workflow</span><span class="sxs-lookup"><span data-stu-id="86e1f-211">Workflow</span></span>|<span data-ttu-id="86e1f-212">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-212">Yes</span></span>|<span data-ttu-id="86e1f-213">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-213">No</span></span>|<span data-ttu-id="86e1f-214">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-214">No</span></span>|
|<span data-ttu-id="86e1f-215">Power BI (klassisch)</span><span class="sxs-lookup"><span data-stu-id="86e1f-215">Power BI (classic)</span></span>|<span data-ttu-id="86e1f-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="86e1f-216">Workspace</span></span>|<span data-ttu-id="86e1f-217">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-217">No</span></span>|<span data-ttu-id="86e1f-218">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-218">Yes</span></span>|<span data-ttu-id="86e1f-219">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-219">Yes</span></span>|
|<span data-ttu-id="86e1f-220">Power BI (neu)</span><span class="sxs-lookup"><span data-stu-id="86e1f-220">Power BI (new)</span></span>|<span data-ttu-id="86e1f-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="86e1f-221">Workspace</span></span>|<span data-ttu-id="86e1f-222">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-222">Yes</span></span>|<span data-ttu-id="86e1f-223">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-223">No</span></span>|<span data-ttu-id="86e1f-224">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-224">Yes</span></span>|
|<span data-ttu-id="86e1f-225">Project für das Web</span><span class="sxs-lookup"><span data-stu-id="86e1f-225">Project for the web</span></span>|<span data-ttu-id="86e1f-226">Projektplan</span><span class="sxs-lookup"><span data-stu-id="86e1f-226">Project plan</span></span>|<span data-ttu-id="86e1f-227">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-227">Yes</span></span>|<span data-ttu-id="86e1f-228">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-228">Yes</span></span>|<span data-ttu-id="86e1f-229">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-229">No</span></span>|
|<span data-ttu-id="86e1f-230">Roadmap</span><span class="sxs-lookup"><span data-stu-id="86e1f-230">Roadmap</span></span>|<span data-ttu-id="86e1f-231">Roadmap</span><span class="sxs-lookup"><span data-stu-id="86e1f-231">Roadmap</span></span>|<span data-ttu-id="86e1f-232">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-232">Yes</span></span>|<span data-ttu-id="86e1f-233">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-233">Yes</span></span>|<span data-ttu-id="86e1f-234">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-234">No</span></span>|
|<span data-ttu-id="86e1f-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="86e1f-235">SharePoint</span></span>|<span data-ttu-id="86e1f-236">Website</span><span class="sxs-lookup"><span data-stu-id="86e1f-236">Site</span></span>|<span data-ttu-id="86e1f-237">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-237">Yes</span></span>|<span data-ttu-id="86e1f-238">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-238">Yes</span></span>|<span data-ttu-id="86e1f-239">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-239">Yes</span></span>|
|<span data-ttu-id="86e1f-240">Stream</span><span class="sxs-lookup"><span data-stu-id="86e1f-240">Stream</span></span>|<span data-ttu-id="86e1f-241">Kanal, Video</span><span class="sxs-lookup"><span data-stu-id="86e1f-241">Channel, video</span></span>|<span data-ttu-id="86e1f-242">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-242">Yes</span></span>|<span data-ttu-id="86e1f-243">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-243">Yes</span></span>|<span data-ttu-id="86e1f-244">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-244">Yes</span></span>|
|<span data-ttu-id="86e1f-245">Teams</span><span class="sxs-lookup"><span data-stu-id="86e1f-245">Teams</span></span>|<span data-ttu-id="86e1f-246">Team</span><span class="sxs-lookup"><span data-stu-id="86e1f-246">Team</span></span>|<span data-ttu-id="86e1f-247">Nein</span><span class="sxs-lookup"><span data-stu-id="86e1f-247">No</span></span>|<span data-ttu-id="86e1f-248">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-248">Yes</span></span>|<span data-ttu-id="86e1f-249">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-249">Yes</span></span>|
|<span data-ttu-id="86e1f-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="86e1f-250">Yammer</span></span>|<span data-ttu-id="86e1f-251">Group</span><span class="sxs-lookup"><span data-stu-id="86e1f-251">Group</span></span>|<span data-ttu-id="86e1f-252">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-252">Yes</span></span>|<span data-ttu-id="86e1f-253">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-253">Yes</span></span>|<span data-ttu-id="86e1f-254">Ja</span><span class="sxs-lookup"><span data-stu-id="86e1f-254">Yes</span></span>|

<span data-ttu-id="86e1f-255">Während die obige Tabelle eine allgemeine Übersicht über die Gruppeninteraktionen mit Microsoft 365-Diensten bietet, gibt es eine Reihe von Nuancen und Feinheiten, die Sie verstehen sollten.</span><span class="sxs-lookup"><span data-stu-id="86e1f-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="86e1f-256">In den folgenden Abschnitten werden die spezifischen Arbeitsauslastungen und ihre Interaktionen mit Gruppen eingehend untersucht.</span><span class="sxs-lookup"><span data-stu-id="86e1f-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="86e1f-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="86e1f-257">Azure AD</span></span>

<span data-ttu-id="86e1f-258">Azure AD stellt die zugrunde liegenden Identitäts Verwaltungsfunktionen in Microsoft 365 bereit.</span><span class="sxs-lookup"><span data-stu-id="86e1f-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="86e1f-259">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="86e1f-260">Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="86e1f-260">Group membership</span></span>
- <span data-ttu-id="86e1f-261">Benennungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="86e1f-261">Naming policy</span></span>
- <span data-ttu-id="86e1f-262">Ablaufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="86e1f-262">Expiration policy</span></span>
- <span data-ttu-id="86e1f-263">Gäste</span><span class="sxs-lookup"><span data-stu-id="86e1f-263">Guests</span></span>
- <span data-ttu-id="86e1f-264">Einschränkung der Gruppenerstellung</span><span class="sxs-lookup"><span data-stu-id="86e1f-264">Restriction of Group creation</span></span>

<span data-ttu-id="86e1f-265">**Kann Azure AD eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="86e1f-266">Ja, Microsoft 365-Gruppen können aus Azure AD entweder über das Administrations Webportal, über PowerShell oder Graph-API erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="86e1f-267">**Gibt es Azure AD ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="86e1f-268">Ja, Azure AD führt eine große Anzahl von Diensten aus, die keinen Bezug zu Microsoft 365-Gruppen haben.</span><span class="sxs-lookup"><span data-stu-id="86e1f-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="86e1f-269">Jede Microsoft 365-Gruppe wird als Objekt in Azure AD dargestellt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="86e1f-270">**Kann es mehrere Instanzen von Azure AD pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="86e1f-271">Nein, es gibt nur eine Instanz von Azure AD.</span><span class="sxs-lookup"><span data-stu-id="86e1f-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="86e1f-272">**Können Azure AD mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="86e1f-273">Ja, da Azure Ad die zugrunde liegende Plattform ist, die den Gruppen Mitgliedschaftsdienst bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="86e1f-274">**Kann die Zuordnung von Azure AD zu einer Gruppe geändert werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="86e1f-275">Nein, Azure AD ist die zugrunde liegende Plattform, auf der Gruppen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="86e1f-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="86e1f-276">**Löscht die Instanz gelöscht die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="86e1f-277">Durch das Löschen der Gruppe in Azure AD werden relevante gruppenbezogene Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="86e1f-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="86e1f-278">Teams</span><span class="sxs-lookup"><span data-stu-id="86e1f-278">Teams</span></span>

<span data-ttu-id="86e1f-279">Teams ist ein Chat-zentrierter Arbeitsbereich zur Verbesserung der Zusammenarbeit, indem eine singuläre Schnittstelle für die Interaktion mit einer Vielzahl von Microsoft-und Drittanbieterdiensten bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="86e1f-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="86e1f-280">Wenn ein Team erstellt wird, werden standardmäßig das Postfach und der Kalender, die der Microsoft 365-Gruppe zugeordnet sind, sowohl in der globalen Adressliste in Exchange als auch in Outlook ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="86e1f-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="86e1f-281">Dies kann manuell von einem Administrator außer Kraft gesetzt werden, wenn der Benutzer sowohl Outlook als auch Teams in derselben Microsoft 365-Gruppe verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="86e1f-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="86e1f-282">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="86e1f-283">Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="86e1f-283">Conversations</span></span>
- <span data-ttu-id="86e1f-284">Kanäle & Registerkarten</span><span class="sxs-lookup"><span data-stu-id="86e1f-284">Channels & tabs</span></span>
- <span data-ttu-id="86e1f-285">Meetings</span><span class="sxs-lookup"><span data-stu-id="86e1f-285">Meetings</span></span>

<span data-ttu-id="86e1f-286">**Können Teams eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="86e1f-287">Ja, mit dem Erstellen eines neuen Teams wird eine neue Microsoft 365-Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="86e1f-288">Es ist auch möglich, ein Team für eine vorhandene Gruppe zu erstellen, die derzeit nicht über eine Gruppe verfügt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="86e1f-289">**Gibt es Teams ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="86e1f-290">Nein, es ist nicht möglich, dass ein Team ohne Gruppe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="86e1f-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="86e1f-291">**Kann es mehrere Teams pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="86e1f-292">Nein, die Beziehung zwischen einem Team und einer Gruppe beträgt 1:1.</span><span class="sxs-lookup"><span data-stu-id="86e1f-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="86e1f-293">**Kann ein Team mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-294">Nein, das Team selbst kann nur einer einzelnen Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="86e1f-295">**Kann sich die Zuordnung eines Teams mit einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="86e1f-296">Nein, das Team kann immer nur der Gruppe zugeordnet werden, der es ursprünglich zugeordnet war.</span><span class="sxs-lookup"><span data-stu-id="86e1f-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="86e1f-297">**Löscht das Team das Löschen der Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="86e1f-298">Ja, durch das Löschen des Teams in Microsoft Teams werden die Gruppe, die gruppenbezogenen Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="86e1f-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="86e1f-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="86e1f-299">Exchange</span></span>

<span data-ttu-id="86e1f-300">Exchange Online bietet Messaging-, Kalender-, Kontakt-und zugehörige Funktionen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="86e1f-301">Im Kontext einer Gruppe wird nur eine einzelne Ressource zugeordnet – im Gegensatz zu einer ganzen Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="86e1f-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="86e1f-302">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="86e1f-303">Postfach und Kalender</span><span class="sxs-lookup"><span data-stu-id="86e1f-303">Mailbox and calendar</span></span>
- <span data-ttu-id="86e1f-304">E-Mail-Funktion für alle Gruppenmitglieder</span><span class="sxs-lookup"><span data-stu-id="86e1f-304">Ability to email all Group members</span></span>
- <span data-ttu-id="86e1f-305">Speicherung von Microsoft Teams-Kanal Unterhaltungen für eDiscovery-Zwecke, planerische Kommentare</span><span class="sxs-lookup"><span data-stu-id="86e1f-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="86e1f-306">**Kann Exchange eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="86e1f-307">Ja, es ist möglich, eine Gruppe sowohl aus dem Exchange Online Admin Center als auch aus Outlook zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="86e1f-308">Sie können auch Exchange-Verteilerlisten in Microsoft 365-Gruppen umwandeln.</span><span class="sxs-lookup"><span data-stu-id="86e1f-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="86e1f-309">**Existiert Exchange ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="86e1f-310">Ja, Exchange Online stellt eine Reihe von Diensten bereit, einschließlich freigegebener Postfächer und Kalender ohne Gruppenzuordnung.</span><span class="sxs-lookup"><span data-stu-id="86e1f-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="86e1f-311">**Kann es mehrere Instanzen von Exchange-Postfächern oder Kalendern pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="86e1f-312">Nein, es kann nur ein einzelnes Exchange Online Postfach und ein einzelner Kalender für eine Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="86e1f-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="86e1f-313">**Können Exchange-Postfächer und Kalender mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-314">Nein, das Postfach und der Kalender weisen eine 1:1-Beziehung mit der Gruppe auf.</span><span class="sxs-lookup"><span data-stu-id="86e1f-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="86e1f-315">Es ist möglich, das Postfach für andere Benutzer oder Gruppen freizugeben, allerdings wird dadurch keine Form von Dienstzuordnungen hergestellt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="86e1f-316">**Kann die Zuordnung des Exchange-Postfachs oder des Kalenders mit einer Gruppe geändert werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="86e1f-317">Nein, das Postfach und der Kalender können nicht in eine andere Gruppe geändert werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="86e1f-318">Der Inhalt kann jedoch in Outlook oder mithilfe eines Drittanbietertools von einem Postfach in ein anderes verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="86e1f-319">**Wird durch das Löschen des Postfachs die Gruppe gelöscht?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="86e1f-320">Ja, durch das Löschen des Postfachs in Exchange werden sowohl die Gruppe als auch die gruppenbezogenen Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="86e1f-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="86e1f-321">Formulare</span><span class="sxs-lookup"><span data-stu-id="86e1f-321">Forms</span></span>

<span data-ttu-id="86e1f-322">Formulare bieten webbasierte Umfragen und Quiz.</span><span class="sxs-lookup"><span data-stu-id="86e1f-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="86e1f-323">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="86e1f-324">Besitz von Formularen</span><span class="sxs-lookup"><span data-stu-id="86e1f-324">Ownership of forms</span></span>

<span data-ttu-id="86e1f-325">**Können Formulare eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="86e1f-326">Nein, Formulare können keine Gruppe erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="86e1f-327">**Gibt es Formulare ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="86e1f-328">Ja, Umfragen und Quiz können direkt im Konto eines Endbenutzers erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="86e1f-329">**Kann es mehrere Formulare pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="86e1f-330">Ja, es kann mehrere Formulare geben, die einer Gruppe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="86e1f-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="86e1f-331">**Können Formulare mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-332">Nein, ein Formular kann nur einer einzelnen Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="86e1f-333">**Kann sich die Zuordnung eines Formulars zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="86e1f-334">Nein, wenn ein Formular einer Gruppe zugeordnet ist (entweder direkt in erstellt oder von einer Person übertragen wurde), kann es nicht in eine andere Gruppe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="86e1f-335">**Wird durch das Löschen des Formulars die Gruppe gelöscht?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="86e1f-336">Nein, es ist nicht möglich, eine Gruppe aus der Formularschnittstelle zu löschen, sondern nur einzelne Formulare.</span><span class="sxs-lookup"><span data-stu-id="86e1f-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="86e1f-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="86e1f-337">OneNote</span></span>

<span data-ttu-id="86e1f-338">OneNote ist eine digitale Notebook-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="86e1f-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="86e1f-339">Das OneNote-Notizbuch, das mit einer Gruppe erstellt wurde, ist eine Datei in der zugeordneten SharePoint-Website und nicht ein mit der Gruppe verbundener Dienst.</span><span class="sxs-lookup"><span data-stu-id="86e1f-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="86e1f-340">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="86e1f-341">Freigegebenes Notizbuch (in der SharePoint-Bibliothek mit Gruppenzuordnung gespeichert)</span><span class="sxs-lookup"><span data-stu-id="86e1f-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="86e1f-342">**Kann OneNote eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="86e1f-343">Nein, die OneNote-Anwendung kann keine Gruppe erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="86e1f-344">**Gibt es OneNote-Notizbücher ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="86e1f-345">Ja, Notizbücher können direkt in OneDrive oder an anderen freigegebenen Speicherorten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="86e1f-346">**Kann es mehrere OneNote-Notizbücher pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="86e1f-347">Ja, ein Notizbuch wird standardmäßig erstellt, andere können hinzugefügt werden, allerdings wird jeder Link zu OneNote von gruppenbezogenen Diensten immer an das Standardnotizbuch weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="86e1f-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="86e1f-348">**Kann ein OneNote-Notizbuch mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-349">Nein, das Notizbuch wird in der mit der Gruppe verknüpften SharePoint-Website Bibliothek gespeichert und mit verschiedenen Schnittstellen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="86e1f-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="86e1f-350">Sie kann jedoch für andere Gruppen auf die gleiche Weise freigegeben werden, wie Sie für einzelne Personen freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="86e1f-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="86e1f-351">**Kann die Verbindung des Notizbuchs mit einer Gruppe geändert werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="86e1f-352">Nein, das Notizbuch selbst ist der Gruppe zugeordnet und kann direkt über andere Gruppen verbundene Dienste aufgerufen werden, der Inhalt kann jedoch in der OneNote-Anwendung von einem Notizbuch in ein anderes verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="86e1f-353">**Löscht das Notizbuch das Löschen der Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="86e1f-354">Nein, wenn das OneNote-Notizbuch jedoch gelöscht wird, sind möglicherweise fehlerhafte Links in einigen der Gruppen zugeordneten Dienste vorhanden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="86e1f-355">Planner</span><span class="sxs-lookup"><span data-stu-id="86e1f-355">Planner</span></span>

<span data-ttu-id="86e1f-356">Planner ist ein einfacher Verwaltungsdienst für Gruppenaufgaben.</span><span class="sxs-lookup"><span data-stu-id="86e1f-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="86e1f-357">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="86e1f-358">Vorstand für die Verwaltung von Gruppenaufgaben</span><span class="sxs-lookup"><span data-stu-id="86e1f-358">Board for managing group tasks</span></span>

<span data-ttu-id="86e1f-359">**Kann Planner eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="86e1f-360">Ja, bei der Erstellung eines Plans wird eine neue Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="86e1f-361">**Besteht ein Planer-Motherboard ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="86e1f-362">Nein, ein Plan muss einer Gruppe zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="86e1f-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="86e1f-363">**Kann es mehrere Pläne pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="86e1f-364">Ja, es kann mehrere Pläne pro Gruppe geben.</span><span class="sxs-lookup"><span data-stu-id="86e1f-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="86e1f-365">**Kann ein Plan mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-366">Nein, ein Plan basiert ausschließlich auf der Gruppenmitgliedschaft, um den Zugriff zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="86e1f-367">**Kann sich die Zuordnung eines Plans zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="86e1f-368">Nein, beim Kopieren eines Plans wird jedoch eine neue Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="86e1f-369">Eine Gruppe, die von einer anderen Anwendung erstellt wurde, wird für einen Benutzer nicht automatisch in Planner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="86e1f-370">Um zunächst auf das Motherboard zugreifen zu können, müssen Sie es aus einer anderen gruppenbasierten Schnittstelle wie Outlook öffnen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="86e1f-371">**Löscht der Plan das Löschen der Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="86e1f-372">Ja, durch das Löschen des Plans werden die Gruppe und die gruppenbezogenen Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="86e1f-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="86e1f-373">Power-Apps</span><span class="sxs-lookup"><span data-stu-id="86e1f-373">Power Apps</span></span>

<span data-ttu-id="86e1f-374">Power-Apps bieten eine Leinwand für die APP-Entwicklung ohne Code.</span><span class="sxs-lookup"><span data-stu-id="86e1f-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="86e1f-375">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="86e1f-376">Apps können für eine Gruppe freigegeben werden, die ausgeführt und geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="86e1f-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="86e1f-377">**Können Power apps eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="86e1f-378">Nein, Power Apps können keine Microsoft 365-Gruppe erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="86e1f-379">**Gibt es Power-apps ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="86e1f-380">Ja, Apps können in Power Apps erstellt und innerhalb des Creators-Kontos gespeichert werden, bis Sie freigegeben oder veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="86e1f-381">**Kann es mehrere apps pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="86e1f-382">Ja, es können mehrere Apps für eine Gruppe freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="86e1f-383">**Können apps mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-384">Ja, eine APP kann für mehrere Gruppen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="86e1f-385">**Kann sich die Zuordnung einer APP mit einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="86e1f-386">Ja, da die Zuordnung zwischen Power apps und einer Microsoft 365-Gruppe nur gemeinsam genutzt wird – die APP befindet sich immer noch beim Creator.</span><span class="sxs-lookup"><span data-stu-id="86e1f-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86e1f-387">[Für Gruppen muss die Sicherheit aktiviert sein, damit Apps für Sie freigegeben werden können](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="86e1f-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="86e1f-388">**Löscht die APP das Löschen der Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="86e1f-389">Nein, die apps sind nicht mit der anderen Gruppe verbunden, als für Sie freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="86e1f-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="86e1f-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="86e1f-390">Power Automate</span></span>

<span data-ttu-id="86e1f-391">Power Automation (früher bekannt als Microsoft Flow) bietet Workflows und Automatisierungs Dienste.</span><span class="sxs-lookup"><span data-stu-id="86e1f-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="86e1f-392">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="86e1f-393">Workflows können für eine Gruppe freigegeben werden, die ausgeführt und geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="86e1f-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="86e1f-394">**Kann Power Automation eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="86e1f-395">Nein, Power Automation kann keine Microsoft 365-Gruppe im Kontext einer Verbindung mit einem erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="86e1f-396">Es ist jedoch möglich, einen Fluss zu erstellen, der verschiedene Vorgänge wie das Erstellen einer Azure AD Sicherheitsgruppe oder das Aktualisieren der Mitgliedschaft einer Microsoft 365-Gruppe ausführt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="86e1f-397">**Gibt es Flüsse ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="86e1f-398">Ja, Flows können innerhalb von Power Automation erstellt und innerhalb des Creators-Kontos gespeichert werden, bis Sie freigegeben oder veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="86e1f-399">**Kann es mehrere Flows pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="86e1f-400">Ja, es können mehrere Flows für eine Gruppe freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="86e1f-401">**Kann ein Flow mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-402">Ja, ein Fluss kann für mehrere Gruppen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="86e1f-403">**Kann sich die Zuordnung eines Flows mit einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="86e1f-404">Ja, da die Verbindung zwischen Power Automation und einer Microsoft 365-Gruppe nur gemeinsam genutzt wird – der Fluss befindet sich immer noch bei dem Ersteller.</span><span class="sxs-lookup"><span data-stu-id="86e1f-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="86e1f-405">**Wird durch Löschen eines Flows die Gruppe gelöscht?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="86e1f-406">Nein, wie Power-apps sind die Flows nicht mit der anderen Gruppe verbunden, als Sie für Sie freigegeben hat.</span><span class="sxs-lookup"><span data-stu-id="86e1f-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="86e1f-407">Power BI (klassisch)</span><span class="sxs-lookup"><span data-stu-id="86e1f-407">Power BI (classic)</span></span>

<span data-ttu-id="86e1f-408">Power BI bietet interaktive datengesteuerte Dashboards und Berichte.</span><span class="sxs-lookup"><span data-stu-id="86e1f-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="86e1f-409">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="86e1f-410">Daten Berichte</span><span class="sxs-lookup"><span data-stu-id="86e1f-410">Data reporting</span></span>

<span data-ttu-id="86e1f-411">**Kann Power BI eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="86e1f-412">Ja, durch das Erstellen eines klassischen Arbeitsbereichs wird eine Microsoft 365-Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="86e1f-413">**Gibt es einen Power BI Classic-Arbeitsbereich ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="86e1f-414">Nein, [ein klassischer Arbeitsbereich in Power BI muss einer Gruppe zugeordnet sein](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="86e1f-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="86e1f-415">**Kann es mehrere Power BI-Arbeitsbereiche pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="86e1f-416">Nein, die Beziehung zwischen einem klassischen Arbeitsbereich und einer Gruppe beträgt 1:1.</span><span class="sxs-lookup"><span data-stu-id="86e1f-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="86e1f-417">**Kann ein Arbeitsbereich mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-418">Technisch gesehen Nein, während der klassische Arbeitsbereich mit der Gruppe erstellt wird, können die Inhalte außerhalb der Gruppe mit Benutzern und Sicherheitsgruppen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="86e1f-419">**Kann die Zuordnung des Arbeitsbereichs zu einer Gruppe geändert werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="86e1f-420">Nein, der klassische Arbeitsbereich selbst ist der Gruppe zugeordnet, der Inhalt kann jedoch in der Power BI-Schnittstelle von einem Arbeitsbereich in einen anderen verschoben werden oder indem Inhalt lokal exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="86e1f-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="86e1f-421">**Wird durch Löschen des Arbeitsbereichs die Gruppe gelöscht?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="86e1f-422">Ja, durch das Löschen des Arbeitsbereichs in Power BI werden Gruppen Dienste und Inhalte gelöscht, die Gruppen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="86e1f-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="86e1f-423">Power BI (neu)</span><span class="sxs-lookup"><span data-stu-id="86e1f-423">Power BI (new)</span></span>

<span data-ttu-id="86e1f-424">Power BI bietet interaktive datengesteuerte Dashboards und Berichte.</span><span class="sxs-lookup"><span data-stu-id="86e1f-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="86e1f-425">Während das Erstellen eines neuen Arbeitsbereichs in Power BI keine Microsoft 365-Gruppe erstellt, wird durch Erstellen einer Gruppe auf andere Weise ein neuer (nicht klassischer) Arbeitsbereich in Power BI erstellt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="86e1f-426">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="86e1f-427">Daten Berichte</span><span class="sxs-lookup"><span data-stu-id="86e1f-427">Data reporting</span></span>

<span data-ttu-id="86e1f-428">**Kann Power BI eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="86e1f-429">Nein, es ist nicht möglich, eine Microsoft 365-Gruppe aus der neuen Power BI-Schnittstelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="86e1f-430">**Gibt es den neuen Power BI-Arbeitsbereich ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="86e1f-431">Ja, es ist möglich, dass in Power BI Berichte und Arbeitsbereiche erstellt werden, die nicht mit Microsoft 365-Gruppen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="86e1f-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="86e1f-432">**Kann es mehrere Arbeitsbereiche pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="86e1f-433">Ja, [mehrere Arbeitsbereiche, die von Power BI erstellt wurden, können für eine einzelne Gruppe freigegeben werden](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="86e1f-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="86e1f-434">**Kann ein Arbeitsbereich mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-435">Nein, ein von Power BI erstellter Arbeitsbereich kann nur einer einzelnen Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="86e1f-436">**Kann sich die Zuordnung eines Arbeitsbereichs mit einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="86e1f-437">Ja und Nein.</span><span class="sxs-lookup"><span data-stu-id="86e1f-437">Yes and no.</span></span> <span data-ttu-id="86e1f-438">Ein von Power BI erstellter Arbeitsbereich kann nur einer einzelnen Gruppe gleichzeitig zugeordnet werden, kann die Zuordnung jedoch jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="86e1f-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="86e1f-439">Ein Arbeitsbereich, der in Power BI von einer Gruppe erstellt wurde, ist dieser Gruppe dauerhaft zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="86e1f-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="86e1f-440">**Wird durch Löschen des Arbeitsbereichs die Gruppe gelöscht?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="86e1f-441">Ja, durch das Löschen des Arbeitsbereichs in Power BI werden die Gruppe und die gruppenbezogenen Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="86e1f-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="86e1f-442">Project für das Web</span><span class="sxs-lookup"><span data-stu-id="86e1f-442">Project for the web</span></span>

<span data-ttu-id="86e1f-443">Project für das Internet bietet die Möglichkeit zum Erstellen von Projektplänen, Gantt-Diagrammen und Roadmaps.</span><span class="sxs-lookup"><span data-stu-id="86e1f-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="86e1f-444">Für Gruppen bereitgestellte Hauptfeatures.</span><span class="sxs-lookup"><span data-stu-id="86e1f-444">Key features provided to groups.</span></span>

- <span data-ttu-id="86e1f-445">Projektpläne</span><span class="sxs-lookup"><span data-stu-id="86e1f-445">Project plans</span></span>

<span data-ttu-id="86e1f-446">**Kann Project für das Internet eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="86e1f-447">Ja, es ist möglich, eine neue Microsoft 365-Gruppe direkt aus Project für das Internet zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="86e1f-448">**Gibt es Projekte ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="86e1f-449">Ja, Projekte können vorhanden sein, ohne einer Microsoft 365-Gruppe zugeordnet zu sein, jedoch erfordert die Zuweisung von Aufgaben eine Gruppenzuordnung.</span><span class="sxs-lookup"><span data-stu-id="86e1f-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="86e1f-450">**Kann es mehrere Projekte pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="86e1f-451">Ja, es ist möglich, mehrere Projekte in einer einzelnen Gruppe zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="86e1f-452">**Kann Project mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-453">Nein, ein Projekt kann nur einer einzelnen Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="86e1f-454">**Kann sich die Zuordnung eines Projekts mit einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="86e1f-455">Nein, wenn die Zuordnung mit einer Gruppe hergestellt wird, kann Sie nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="86e1f-456">**Löscht das Löschen des Projekts die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="86e1f-457">Nein, wenn das Projekt in Project für das Internet gelöscht wird, wird die Gruppe nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="86e1f-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="86e1f-458">Roadmap</span><span class="sxs-lookup"><span data-stu-id="86e1f-458">Roadmap</span></span>

<span data-ttu-id="86e1f-459">Roadmap bietet die Möglichkeit zum Erstellen von Projekt-Roadmaps mit Project für das Internet und Project online.</span><span class="sxs-lookup"><span data-stu-id="86e1f-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="86e1f-460">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="86e1f-461">Projekt-Roadmaps</span><span class="sxs-lookup"><span data-stu-id="86e1f-461">Project roadmaps</span></span>

<span data-ttu-id="86e1f-462">**Kann Roadmap eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="86e1f-463">Ja, es ist möglich, eine neue Microsoft 365-Gruppe direkt aus der Roadmap zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="86e1f-464">**Gibt es eine Roadmap ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="86e1f-465">Ja, Roadmaps können vorhanden sein, ohne einer Microsoft 365-Gruppe zugeordnet zu sein, allerdings erfordert die Freigabe der Roadmap eine Gruppenzuordnung.</span><span class="sxs-lookup"><span data-stu-id="86e1f-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="86e1f-466">**Kann es mehrere Roadmaps pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="86e1f-467">Ja, es ist möglich, mehrere Roadmaps mit einer einzelnen Gruppe zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="86e1f-468">**Kann eine Roadmap mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-469">Nein, eine Roadmap kann nur einer einzelnen Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="86e1f-470">**Kann sich die Zuordnung einer Roadmap zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="86e1f-471">Nein, wenn die Zuordnung mit einer Gruppe hergestellt wird, kann Sie nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="86e1f-472">**Wird durch das Löschen der Roadmap die Gruppe gelöscht?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="86e1f-473">Nein, durch das Löschen der Roadmap wird die Gruppe nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="86e1f-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="86e1f-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="86e1f-474">SharePoint</span></span>

<span data-ttu-id="86e1f-475">SharePoint ist eine webbasierte Content Management-Plattform, die unter anderem Speicherdienste für eine Reihe von Microsoft 365-Diensten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="86e1f-476">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="86e1f-477">Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="86e1f-477">Document library</span></span>
- <span data-ttu-id="86e1f-478">Bibliothek zum Speichern des OneNote-Notizbuchs</span><span class="sxs-lookup"><span data-stu-id="86e1f-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="86e1f-479">Speichern von wiki-Dateien für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86e1f-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="86e1f-480">**Kann SharePoint eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="86e1f-481">Ja, durch das Erstellen einer Teamwebsite in SharePoint wird standardmäßig eine Microsoft 365-Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="86e1f-482">Es ist auch möglich, eine Gruppe und optional ein Team für eine vorhandene Website zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="86e1f-483">**Sind SharePoint-Websites ohne Gruppe vorhanden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="86e1f-484">Ja, SharePoint bietet eine Reihe nicht Gruppen zugeordneter Dienste und Websites wie Kommunikation und Hub-Websites.</span><span class="sxs-lookup"><span data-stu-id="86e1f-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="86e1f-485">**Kann es mehrere Standorte pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="86e1f-486">Nein, es kann nur einen einzelnen Standort pro Gruppe geben.</span><span class="sxs-lookup"><span data-stu-id="86e1f-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="86e1f-487">Private Kanäle in Microsoft Teams verwenden zusätzliche Websites, die nicht mit der Gruppe verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="86e1f-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="86e1f-488">**Können Websites mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-489">Technisch gesehen Nein, aber während eine Website mit einer Gruppe erstellt wird, können die Inhalte für andere Gruppen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="86e1f-490">**Kann sich die Zuordnung einer Website zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="86e1f-491">Nein, die Website selbst ist der Gruppe zugeordnet, der Inhalt kann jedoch von einer Website in eine andere innerhalb der SharePoint-Benutzeroberfläche verschoben werden, indem Inhalte lokal exportiert werden oder ein Drittanbietertool verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="86e1f-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="86e1f-492">**Löscht die Website gelöscht die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="86e1f-493">Ja, durch das Löschen der Website in SharePoint werden Gruppen-und gruppenbezogene Dienste und Inhalte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="86e1f-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="86e1f-494">Stream</span><span class="sxs-lookup"><span data-stu-id="86e1f-494">Stream</span></span>

<span data-ttu-id="86e1f-495">Microsoft Stream ist eine Plattform für Video Hosting und-Freigaben.</span><span class="sxs-lookup"><span data-stu-id="86e1f-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="86e1f-496">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="86e1f-497">Video Speicher</span><span class="sxs-lookup"><span data-stu-id="86e1f-497">Video storage</span></span>
- <span data-ttu-id="86e1f-498">Teams-Besprechungsaufzeichnung</span><span class="sxs-lookup"><span data-stu-id="86e1f-498">Teams meeting recording</span></span>
- <span data-ttu-id="86e1f-499">Video Kanäle</span><span class="sxs-lookup"><span data-stu-id="86e1f-499">Video channels</span></span>

<span data-ttu-id="86e1f-500">**Kann Stream eine Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="86e1f-501">Ja, es ist möglich, eine neue Microsoft 365-Gruppe direkt aus dem Datenstrom zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="86e1f-502">**Gibt es Datenstrom ohne Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="86e1f-503">Ja, Videokanäle und Videos können in Stream vorhanden sein, ohne einer Gruppe zugeordnet zu sein.</span><span class="sxs-lookup"><span data-stu-id="86e1f-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="86e1f-504">**Kann es mehrere Videos und Kanäle pro Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="86e1f-505">Ja, in jeder Gruppe kann es mehrere Videos und Kanäle geben.</span><span class="sxs-lookup"><span data-stu-id="86e1f-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="86e1f-506">**Kann ein Video oder Kanal mehreren Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="86e1f-507">Ja, während ein Video oder Kanal mit einer Gruppe erstellt wird, kann es für andere Gruppen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="86e1f-508">**Kann sich die Zuordnung zu einer Gruppe ändern?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="86e1f-509">Ja und Nein; Videos im Datenstrom befinden sich im Besitz des ursprünglichen Uploaders oder der Besprechungsaufzeichnung und können daher jeder Gruppe zugeordnet werden, Videokanäle können jedoch nur der Gruppe zugeordnet werden, in der Sie ursprünglich erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="86e1f-510">**Löscht das Löschen von Videos oder Kanälen die Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="86e1f-511">Nein, durch das Löschen von Videos oder Kanälen wird die Gruppe nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="86e1f-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="86e1f-512">Durch das Löschen der Gruppe selbst in Stream werden jedoch gruppenbezogene Dienste und Inhalte gelöscht, mit Ausnahme der tatsächlichen Videos.</span><span class="sxs-lookup"><span data-stu-id="86e1f-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="86e1f-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="86e1f-513">Yammer</span></span>

<span data-ttu-id="86e1f-514">Jammern ist eine Enterprise-Plattform für soziale Netzwerke, die das Engagement der Community innerhalb und zwischen Organisationen fördern soll.</span><span class="sxs-lookup"><span data-stu-id="86e1f-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="86e1f-515">Durch das Erstellen einer Community (früher als "Group" bezeichnet) in jammern wird ein Postfach erstellt, das derzeit jedoch nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="86e1f-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="86e1f-516">Eine Microsoft 365-Gruppe, die mit "jammern" verknüpft ist, kann nicht mit einem Team in Microsoft Teams verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="86e1f-517">**Für Gruppen bereitgestellte wichtige Features**</span><span class="sxs-lookup"><span data-stu-id="86e1f-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="86e1f-518">Unterhaltungsbereich</span><span class="sxs-lookup"><span data-stu-id="86e1f-518">Conversation area</span></span>

<span data-ttu-id="86e1f-519">**Kann jammern eine Microsoft 365-Gruppe erstellen?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="86e1f-520">Ja, beim Erstellen einer neuen Gruppe in "jammern" wird eine neue Microsoft 365-Gruppe erstellt, wenn die Plattformen verbunden sind und der Benutzer die Möglichkeit hat, eine Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="86e1f-521">Eine Jammer Gruppe mit zugeordneter Microsoft 365-Gruppe kann nicht in einer anderen Schnittstelle oder einem anderen Dienst als "jammern" erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="86e1f-522">**Gibt es eine Jammer Gruppe ohne Microsoft 365-Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="86e1f-523">Ja, es ist möglich, eine Jammer Gruppe ohne Microsoft 365-Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e1f-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="86e1f-524">Wenn die Jammer Plattform nicht mit Microsoft 365-Gruppen verbunden ist oder Benutzer nicht in der Lage sind, eine Microsoft 365-Gruppe zu erstellen, werden Jammer Gruppen ohne Microsoft 365 Group Association erstellt.</span><span class="sxs-lookup"><span data-stu-id="86e1f-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="86e1f-525">**Kann es mehrere Jammer Gruppen pro Microsoft 365-Gruppe geben?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="86e1f-526">Nein, die Beziehung zwischen einer Jammer Gruppe und einer Microsoft 365-Gruppe lautet 1:1.</span><span class="sxs-lookup"><span data-stu-id="86e1f-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="86e1f-527">**Kann eine Jammer Gruppe mehreren Microsoft 365-Gruppen zugeordnet werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="86e1f-528">Nein, die Gruppe "jammern" kann nur einer einzelnen Microsoft 365-Gruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="86e1f-529">Es ist möglich, dass Beiträge für andere Jammer Gruppen freigegeben oder verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="86e1f-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="86e1f-530">**Kann die Zuordnung einer Jammer Gruppe zu einer Microsoft 365-Gruppe geändert werden?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="86e1f-531">Nein, die Gruppe "jammern" kann immer nur der Microsoft 365-Gruppe zugeordnet werden, der Sie ursprünglich zugeordnet war.</span><span class="sxs-lookup"><span data-stu-id="86e1f-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="86e1f-532">**Löscht die Gruppe "jammern" die Microsoft 365-Gruppe?**</span><span class="sxs-lookup"><span data-stu-id="86e1f-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="86e1f-533">Ja, durch das Löschen der Gruppe in "jammern" werden die zugehörigen Dienste und Inhalte von Microsoft Group und Group gelöscht.</span><span class="sxs-lookup"><span data-stu-id="86e1f-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

