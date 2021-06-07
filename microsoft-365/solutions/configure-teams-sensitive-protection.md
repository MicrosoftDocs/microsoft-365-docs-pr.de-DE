---
title: Teams für den Schutz vertraulicher Daten konfigurieren
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: Hier erfahren Sie, wie Sie Teams bereitstellen, in denen vertrauliche Daten geschützt sind.
ms.openlocfilehash: a3f715cb05ad1d5acf3c93c58959f12ebec46978
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788342"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="5a370-103">Teams für den Schutz vertraulicher Daten konfigurieren</span><span class="sxs-lookup"><span data-stu-id="5a370-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="5a370-104">In diesem Artikel sehen wir uns das Einrichten eines Teams an, in dem vertrauliche Daten geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="5a370-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="5a370-105">Bevor Sie die Schritte in diesem Artikel ausführen, müssen Sie die Schritte unter [Bereitstellen von Microsoft Teams mit Basisschutz ](configure-teams-baseline-protection.md) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="5a370-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="5a370-106">Die "Vertraulich"-Stufe bietet den folgenden zusätzlichen Schutz gegenüber der Basisstufe:</span><span class="sxs-lookup"><span data-stu-id="5a370-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="5a370-p102">Eine Vertraulichkeitsbezeichnung für das Team, die es Ihnen ermöglicht, die Gastfreigabe ein- oder auszuschalten und den Zugriff auf SharePoint-Inhalte für nicht verwaltete Geräte auf die Webebene zu beschränken. Diese Bezeichnung kann auch zum klassifizieren von Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a370-p102">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices. This label can also be used to classify files.</span></span>
- <span data-ttu-id="5a370-109">Einen restriktiveren standardmäßigen Freigabe-Linktyp</span><span class="sxs-lookup"><span data-stu-id="5a370-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="5a370-110">Nur Teambesitzer können private Kanäle erstellen.</span><span class="sxs-lookup"><span data-stu-id="5a370-110">Only team owners can create private channels.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="5a370-111">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="5a370-111">Video demonstration</span></span>

<span data-ttu-id="5a370-112">Schauen Sie sich dieses Video an, um eine exemplarische Vorgehensweise für die in diesem Artikel beschriebenen Verfahren zu finden.</span><span class="sxs-lookup"><span data-stu-id="5a370-112">Watch this video for a walkthrough of the procedures described in this article.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NMS6]

## <a name="guest-sharing"></a><span data-ttu-id="5a370-113">Gastfreigabe</span><span class="sxs-lookup"><span data-stu-id="5a370-113">Guest sharing</span></span>

<span data-ttu-id="5a370-114">Je nach Art des Unternehmens ist möglicherweise die Gastfreigabe für Teams erforderlich, in denen vertrauliche Daten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="5a370-114">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="5a370-115">Wenn Sie die Zusammenarbeit mit Personen außerhalb Ihrer Organisation in einem solchen Team planen, empfiehlt es sich, die Gastfreigabe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5a370-115">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="5a370-116">Microsoft 365 umfasst eine Vielzahl von Sicherheits- und Compliance-Features, um vertrauliche Inhalte sicher freigeben zu können.</span><span class="sxs-lookup"><span data-stu-id="5a370-116">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="5a370-117">Dies ist in der Regel eine sicherere Option als das direkte Senden von Inhalten an Personen außerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="5a370-117">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="5a370-118">Details zur sicheren Freigabe für Gäste finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="5a370-118">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="5a370-119">Begrenzen der versehentlichen Gefährdung von Dateien bei der Freigabe für Personen außerhalb Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="5a370-119">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="5a370-120">Erstellen einer sicheren Gastfreigabeumgebung</span><span class="sxs-lookup"><span data-stu-id="5a370-120">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="5a370-121">Für das Zulassen oder Blockieren des Gastfreigabe verwenden wir eine Kombination aus einer Vertraulichkeitsbezeichnung für das Team und Steuerelementen für die Freigabe auf Team- und Websiteebene für die zugeordnete SharePoint-Website, die beide später behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5a370-121">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="5a370-122">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="5a370-122">Sensitivity labels</span></span>

<span data-ttu-id="5a370-123">Für den Schutz auf Vertraulichkeitsebene werden wir eine Vertraulichkeitsbezeichnung verwenden, um das Team zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="5a370-123">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="5a370-124">Diese Bezeichnung kann auch verwendet werden, um einzelne Dateien in diesem oder anderen Teams oder an anderen Speicherorten wie SharePoint oder OneDrive zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="5a370-124">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="5a370-125">Als ersten Schritt müssen Sie Vertraulichkeitsbezeichnungen für Microsoft Teams aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5a370-125">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="5a370-126">Weitere Informationen finden Sie unter [Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Office 365-Gruppen und SharePoint-Websites](../compliance/sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="5a370-126">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="5a370-127">Wenn Sie in Ihrer Organisation bereits über Vertraulichkeitsbezeichnungen verfügen, überlegen Sie, wie sich diese Bezeichnung in Ihre allgemeine Bezeichnungsstrategie einfügt.</span><span class="sxs-lookup"><span data-stu-id="5a370-127">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="5a370-128">Sie können den Namen oder die Einstellungen bei Bedarf an die Anforderungen Ihrer Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="5a370-128">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="5a370-129">Sobald Sie Vertraulichkeitsbezeichnungen für Microsoft Teams aktiviert haben, besteht der nächste Schritt darin, die erforderliche Bezeichnung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5a370-129">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="5a370-130">Erstellen einer Vertraulichkeitsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="5a370-130">To create a sensitivity label</span></span>
1. <span data-ttu-id="5a370-131">Öffnen Sie das [Microsoft 365 Compliance Center](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5a370-131">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="5a370-132">Klicken Sie unter **Lösungen** auf **Informationsschutz**.</span><span class="sxs-lookup"><span data-stu-id="5a370-132">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="5a370-133">Klicken Sie auf **Bezeichnung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5a370-133">Click **Create a label**.</span></span>
4. <span data-ttu-id="5a370-134">Weisen Sie der Bezeichnung einen Namen zu.</span><span class="sxs-lookup"><span data-stu-id="5a370-134">Give the label a name.</span></span> <span data-ttu-id="5a370-135">Wir empfehlen **Vertraulich**, Sie können aber auch einen anderen Namen auswählen, falls dieser bereits verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5a370-135">We suggest **Sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="5a370-136">Fügen Sie einen Namen und eine Beschreibung hinzu, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5a370-136">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="5a370-137">Wählen Sie auf der Seite **Definieren des Bereichs für diese Bezeichnung** die Option **Dateien & E-Mails** und **Gruppen & Websites** aus und klicken Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5a370-137">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="5a370-138">Klicken Sie auf der Seite **Auswählen der Schutzeinstellungen für Dateien und E-Mails** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5a370-138">On the **Choose protection settings for files and emails** page, click **Next**.</span></span>
8. <span data-ttu-id="5a370-139">Klicken Sie auf der Seite *Automatische Bezeichnung für Dateien und E-Mails* auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5a370-139">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
9. <span data-ttu-id="5a370-140">Wählen Sie auf der Seite **Definieren der Schutzeinstellungen für Gruppen und Websites** die Option **Einstellungen für Datenschutz und den Zugriff externer Benutzer** und **Einstellungen für Gerätezugriff und externe Freigabe** aus und klicken Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5a370-140">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
10. <span data-ttu-id="5a370-141">Wählen Sie auf der Seite **Definieren von Einstellungen für Datenschutz und den Zugriff externer Benutzer** unter **Datenschutz** die Option **Privat** aus.</span><span class="sxs-lookup"><span data-stu-id="5a370-141">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
11. <span data-ttu-id="5a370-142">Wenn Sie Gastzugriffe zulassen wollen, wählen Sie unter **Externer Benutzerzugriff** die Option **Zulassen, dass Microsoft 365-Gruppenbesitzer Personen außerhalb Ihrer Organisation als Gäste zur Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5a370-142">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
12. <span data-ttu-id="5a370-143">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5a370-143">Click **Next**.</span></span>
13. <span data-ttu-id="5a370-144">Wählen Sie auf der Seite **Definieren der Einstellungen für externe Freigabe und Gerätezugriff** die Option **Steuerung der externen Freigabe aus bezeichneten SharePoint-Websites**.</span><span class="sxs-lookup"><span data-stu-id="5a370-144">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
14. <span data-ttu-id="5a370-145">Wählen Sie unter **Inhalt kann geteilt werden mit** die Option **Neue und bestehende Gäste**, wenn Sie den Gastzugriff erlauben wollen, oder anderenfalls **Nur Personen in Ihrer Organisation**.</span><span class="sxs-lookup"><span data-stu-id="5a370-145">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
15. <span data-ttu-id="5a370-146">Wählen Sie unter **Zugriff von nicht verwalteten Geräten** die Option **Eingeschränkten, reinen Webzugriff zulassen**.</span><span class="sxs-lookup"><span data-stu-id="5a370-146">Under **Access from unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
16. <span data-ttu-id="5a370-147">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5a370-147">Click **Next**.</span></span>
17. <span data-ttu-id="5a370-148">Klicken Sie auf der Seite **Automatisches Bezeichnen von Datenbank-Spalten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5a370-148">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
18. <span data-ttu-id="5a370-149">Klicken Sie auf **Bezeichnung erstellen** und anschließend auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="5a370-149">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="5a370-150">Nachdem Sie die Bezeichnung erstellt haben, müssen Sie sie für die Benutzer veröffentlichen, die sie verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="5a370-150">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="5a370-151">Zum Schutz vertraulicher Daten werden die Bezeichnungen für alle Benutzer verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="5a370-151">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="5a370-152">Die Bezeichnung wird im Microsoft 365 Compliance Center auf der Seite **Schutz von Daten** auf der Registerkarte **Bezeichnungsrichtlinien** veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="5a370-152">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="5a370-153">Wenn bereits eine Richtlinie vorhanden ist, die für alle Benutzer gilt, fügen Sie diese Bezeichnung zu dieser Richtlinie hinzu.</span><span class="sxs-lookup"><span data-stu-id="5a370-153">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="5a370-154">Wenn Sie eine neue Richtlinie erstellen müssen, lesen Sie [Veröffentlichen von Vertraulichkeitsbezeichnungen durch Erstellen einer Bezeichnungsrichtlinie](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="5a370-154">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="5a370-155">Ein Team erstellen</span><span class="sxs-lookup"><span data-stu-id="5a370-155">Create a team</span></span>

<span data-ttu-id="5a370-156">Weitere Konfigurationsschritte für das Vertraulichkeitsszenario erfolgen auf der SharePoint-Website, die dem Team zugeordnet ist. Deshalb besteht der nächste Schritt darin, ein Team zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5a370-156">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="5a370-157">So erstellen Sie ein Team für vertrauliche Informationen</span><span class="sxs-lookup"><span data-stu-id="5a370-157">To create a team for sensitive information</span></span>
1. <span data-ttu-id="5a370-158">Klicken Sie in Microsoft Teams auf der linken Seite auf **Teams** und dann unten in der Teamliste auf **Einem Team beitreten oder ein Team erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5a370-158">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="5a370-159">Klicken Sie auf **Team erstellen** (erste Karte, obere linke Ecke).</span><span class="sxs-lookup"><span data-stu-id="5a370-159">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="5a370-160">Wählen Sie **Neuerstellen eines Teams**.</span><span class="sxs-lookup"><span data-stu-id="5a370-160">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="5a370-161">Wählen Sie in der Liste **Vertraulichkeit** die **Vertraulichkeitsbezeichnung** aus, die Sie soeben erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="5a370-161">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="5a370-162">Klicken Sie unter **Datenschutz** auf **Privat**.</span><span class="sxs-lookup"><span data-stu-id="5a370-162">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="5a370-163">Geben Sie einen Namen für die Gruppe ein, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5a370-163">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="5a370-164">Fügen Sie Benutzer zu dem Team hinzu, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="5a370-164">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="5a370-165">Einstellungen für private Kanäle</span><span class="sxs-lookup"><span data-stu-id="5a370-165">Private channel settings</span></span>

<span data-ttu-id="5a370-166">Auf dieser Ebene wird die Möglichkeit der Erstellung privater Kanäle auf Teambesitzer eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="5a370-166">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="5a370-167">So schränken Sie die Erstellung privater Kanäle ein</span><span class="sxs-lookup"><span data-stu-id="5a370-167">To restrict private channel creation</span></span>
1. <span data-ttu-id="5a370-168">Klicken Sie im Team auf **Weitere Optionen** und dann auf **Team verwalten**.</span><span class="sxs-lookup"><span data-stu-id="5a370-168">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="5a370-169">Erweitern Sie auf der Registerkarte **Einstellungen** den Eintrag **Mitgliedsberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="5a370-169">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="5a370-170">Deaktivieren Sie das Kontrollkästchen **Mitglieder können private Kanäle erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5a370-170">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="5a370-171">Sie können auch [Teams-Richtlinien](/MicrosoftTeams/teams-policies) verwenden, um zu steuern, wer private Kanäle erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="5a370-171">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="5a370-172">SharePoint-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5a370-172">SharePoint settings</span></span>

<span data-ttu-id="5a370-173">Jedes Mal, wenn Sie ein neues Team mit der Vertraulichkeitsbezeichnung erstellen, müssen Sie in SharePoint zwei Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="5a370-173">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="5a370-174">Aktualisieren Sie die Gastfreigabeeinstellungen für die Website im SharePoint Online Admin Center, um den standardmäßigen Freigabelink auf *Bestimmte Personen* zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5a370-174">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="5a370-175">Aktualisieren Sie die Website-Freigabeeinstellungen auf der Website selbst, um zu verhindern, dass Mitglieder die Website freigeben.</span><span class="sxs-lookup"><span data-stu-id="5a370-175">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="5a370-176">Einstellungen des Standardfreigabelinks der Website</span><span class="sxs-lookup"><span data-stu-id="5a370-176">Site default sharing link settings</span></span>

<span data-ttu-id="5a370-177">So aktualisieren Sie den Standardfreigabelinktyp der Website</span><span class="sxs-lookup"><span data-stu-id="5a370-177">To update the site default sharing link type</span></span>

1. <span data-ttu-id="5a370-178">Öffnen Sie das [SharePoint Admin Center](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="5a370-178">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="5a370-179">Klicken Sie unter **Websites** auf **Aktive Websites**.</span><span class="sxs-lookup"><span data-stu-id="5a370-179">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="5a370-180">Klicken Sie auf die dem Team zugeordnete Website.</span><span class="sxs-lookup"><span data-stu-id="5a370-180">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="5a370-181">Klicken Sie auf der Registerkarte **Richtlinien** unter **Externe Freigabe** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5a370-181">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="5a370-182">Deaktivieren Sie unter "Standardmäßiger Freigabe-Linktyp" das Kontrollkästchen **Identisch mit der Einstellung auf Organisationsebene**, und wählen Sie **Bestimmte Personen (nur die Personen, die der Benutzer angibt)** aus.</span><span class="sxs-lookup"><span data-stu-id="5a370-182">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
6. <span data-ttu-id="5a370-183">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5a370-183">Click **Save**.</span></span>

<span data-ttu-id="5a370-184">Wenn Sie dies als Teil des Teamerstellungsprozesses in Form eines Skripts festlegen möchten, können Sie [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) mit dem Parametern `-DefaultSharingLinkType Direct` verwenden, um den Standardfreigabelink in *Bestimmte Personen* zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5a370-184">If you want to script this as part of your team creation process, you can use [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) with the `-DefaultSharingLinkType Direct` parameter to change the default sharing link to *Specific people*.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="5a370-185">Private Kanäle</span><span class="sxs-lookup"><span data-stu-id="5a370-185">Private channels</span></span>

<span data-ttu-id="5a370-186">Wenn Sie dem Team private Kanäle hinzufügen, erstellt jeder private Kanal eine neue SharePoint-Website mit den Standardeinstellungen für die Freigabe.</span><span class="sxs-lookup"><span data-stu-id="5a370-186">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="5a370-187">Diese Websites werden im SharePoint Admin Center nicht angezeigt, daher müssen Sie das Cmdlet "Set-SPOSite PowerShell" verwenden, um die Gast-Freigabeeinstellungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5a370-187">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="5a370-188">Freigabeeinstellungen für Websites</span><span class="sxs-lookup"><span data-stu-id="5a370-188">Site sharing settings</span></span>

<span data-ttu-id="5a370-189">Um sicherzustellen, dass die SharePoint-Website nicht mit Personen geteilt wird, die nicht Mitglieder des Teams sind, schränken Sie die Freigabe auf die Besitzer ein.</span><span class="sxs-lookup"><span data-stu-id="5a370-189">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="5a370-190">So beschränken Sie die Websitefreigabe auf die Besitzer</span><span class="sxs-lookup"><span data-stu-id="5a370-190">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="5a370-191">Gehen Sie in Teams zur Registerkarte **Allgemein** des Teams, das Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5a370-191">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="5a370-192">Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.</span><span class="sxs-lookup"><span data-stu-id="5a370-192">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="5a370-193">Klicken Sie auf die drei Punkte "(…)" und dann auf **In SharePoint öffnen**.</span><span class="sxs-lookup"><span data-stu-id="5a370-193">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="5a370-194">Klicken Sie in der Symbolleiste der zugrunde liegenden SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="5a370-194">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="5a370-195">Klicken Sie im Bereich **Websiteberechtigungen** unter **Websitefreigabe** auf **Ändern, wie Mitglieder teilen können**.</span><span class="sxs-lookup"><span data-stu-id="5a370-195">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="5a370-196">Wählen Sie unter **Freigabeberechtigungen** die Option **Websitebesitzer und -mitglieder sowie Personen mit Bearbeitungsberechtigungen können Dateien und Ordner freigeben, aber nur Websitebesitzer können die Website freigeben**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5a370-196">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="5a370-197">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a370-197">See Also</span></span>

[<span data-ttu-id="5a370-198">Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen und deren Richtlinien</span><span class="sxs-lookup"><span data-stu-id="5a370-198">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
