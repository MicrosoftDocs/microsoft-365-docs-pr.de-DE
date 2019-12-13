---
title: Bereitstellen von Teams für drei Schutzebenen für Dateien
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Erstellen und Konfigurieren von Teams mit Microsoft Teams für verschiedene Ebenen des Informationsschutzes für Dateien.
ms.openlocfilehash: 3b90a1b084f7cd7e56d1d6448d74a7d2c2469a4d
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971823"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="fdada-103">Bereitstellen von Teams für drei Schutzebenen für Dateien</span><span class="sxs-lookup"><span data-stu-id="fdada-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="fdada-104">Verwenden Sie die Schritte in diesem Artikel, um Richtlinien für grundlegende, vertrauliche und streng vertrauliche Teams zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="fdada-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential teams.</span></span> <span data-ttu-id="fdada-105">Weitere Informationen zu diesen drei Schutzebenen finden Sie unter [Sichern von Dateien in Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fdada-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>

## <a name="baseline-teams"></a><span data-ttu-id="fdada-106">Grundlegende Teams</span><span class="sxs-lookup"><span data-stu-id="fdada-106">Baseline teams</span></span>

<span data-ttu-id="fdada-107">Der grundlegende Schutz enthält jeweils öffentliche und private Teams.</span><span class="sxs-lookup"><span data-stu-id="fdada-107">Baseline protection includes both public and private teams.</span></span> <span data-ttu-id="fdada-108">Öffentliche Teams können von allen Benutzern in der Organisation ermittelt werden und alle haben Zugriff auf diese.</span><span class="sxs-lookup"><span data-stu-id="fdada-108">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="fdada-109">Nur Mitglieder der Office 365-Gruppe, die mit dem Team verknüpft sind, können die privaten Websites ermitteln und auf diese zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fdada-109">Private sites can only be discovered and accessed by members of the Office 365 group associated with the team.</span></span> <span data-ttu-id="fdada-110">Bei diesen beiden Typen von Teams können Mitglieder die Website mit anderen Benutzern teilen.</span><span class="sxs-lookup"><span data-stu-id="fdada-110">Both of these types of teams allow members to share the site with others.</span></span>

### <a name="public"></a><span data-ttu-id="fdada-111">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="fdada-111">Public</span></span>

<span data-ttu-id="fdada-112">Befolgen Sie die Anweisungen in [diesem Artikel](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b), um ein grundlegendes Team mit öffentlichem Zugriff und öffentlichen Berechtigungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fdada-112">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with public access and permissions.</span></span>

<span data-ttu-id="fdada-113">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fdada-113">Here is your resulting configuration.</span></span>

![Grundlegender Schutz für ein öffentliches Team.](../media/baseline-public-team.png)

### <a name="private"></a><span data-ttu-id="fdada-115">Privat</span><span class="sxs-lookup"><span data-stu-id="fdada-115">Private</span></span>

<span data-ttu-id="fdada-116">Befolgen Sie die Anweisungen in [diesem Artikel](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b), um ein grundlegendes Team mit privatem Zugriff und privaten Berechtigungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fdada-116">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with private access and permissions.</span></span>

<span data-ttu-id="fdada-117">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fdada-117">Here is your resulting configuration.</span></span>

![Grundlegender Schutz für ein privates Team.](../media/baseline-private-team.png)

## <a name="sensitive-teams"></a><span data-ttu-id="fdada-119">Vertrauliche Teams</span><span class="sxs-lookup"><span data-stu-id="fdada-119">Sensitive teams</span></span>

<span data-ttu-id="fdada-120">Für ein vertrauliches Team beginnen Sie mit dem [Erstellen eines privaten Teams](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="fdada-120">For a sensitive team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="fdada-121">Als Nächstes konfigurieren Sie die zugrunde liegende SharePoint-Website, um die Freigabe durch Teammitglieder zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="fdada-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1. <span data-ttu-id="fdada-122">Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.</span><span class="sxs-lookup"><span data-stu-id="fdada-122">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="fdada-123">Klicken Sie auf die drei Punkte "(…)" und dann auf **In SharePoint öffnen**.</span><span class="sxs-lookup"><span data-stu-id="fdada-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="fdada-124">Klicken Sie in der Symbolleiste der zugrunde liegenden SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="fdada-124">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="fdada-125">Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="fdada-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="fdada-126">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fdada-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="fdada-127">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fdada-127">Here is your resulting configuration.</span></span>

![Schutz vertraulicher Daten für ein Team.](../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a><span data-ttu-id="fdada-129">Streng vertrauliche Teams</span><span class="sxs-lookup"><span data-stu-id="fdada-129">Highly confidential teams</span></span>

<span data-ttu-id="fdada-130">Für ein streng vertrauliches Team beginnen Sie mit dem [Erstellen eines privaten Teams](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="fdada-130">With a highly confidential team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="fdada-131">Als Nächstes konfigurieren Sie die zugrunde liegende SharePoint-Website, um die Freigabe durch Teammitglieder und das Anfordern von Zugriff von Nicht-Mitgliedern des Teams zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="fdada-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1. <span data-ttu-id="fdada-132">Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.</span><span class="sxs-lookup"><span data-stu-id="fdada-132">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="fdada-133">Klicken Sie auf die drei Punkte "(…)" und dann auf **In SharePoint öffnen**.</span><span class="sxs-lookup"><span data-stu-id="fdada-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="fdada-134">Klicken Sie in der Symbolleiste der zugrunde liegenden SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="fdada-134">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="fdada-135">Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="fdada-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="fdada-136">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus.</span><span class="sxs-lookup"><span data-stu-id="fdada-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

6. <span data-ttu-id="fdada-137">Deaktivieren Sie **Zugriffsanforderungen zulassen**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fdada-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="fdada-138">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fdada-138">Here is your resulting configuration.</span></span>

![Schutz von streng vertraulichen Daten für ein Team.](../media/highly-confidential-team.png)

## <a name="next-step"></a><span data-ttu-id="fdada-140">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="fdada-140">Next step</span></span>

[<span data-ttu-id="fdada-141">Schützen von Dateien in Teams mit Aufbewahrungsbezeichnungen und Schutz vor Datenverlust (DLP)</span><span class="sxs-lookup"><span data-stu-id="fdada-141">Protect files in teams with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="fdada-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdada-142">See also</span></span>

[<span data-ttu-id="fdada-143">Sichern von Dateien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fdada-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)

[<span data-ttu-id="fdada-144">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="fdada-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
