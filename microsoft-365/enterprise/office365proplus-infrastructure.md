---
title: 'Phase 4: Microsoft 365 Apps for Enterprise'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Die Schritte zur Bereitstellung der Microsoft 365 Apps for Enterprise-Infrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: 5143ef8872a7ebd119e77c6148288828a39e20d9
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011947"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="33e43-103">Phase 4: Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="33e43-103">Phase 4: Microsoft 365 Apps for enterprise</span></span>

![Phase 4: Microsoft 365 Apps for Enterprise](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="33e43-105">*Dies gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise und Microsoft 365 Education.*</span><span class="sxs-lookup"><span data-stu-id="33e43-105">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="33e43-106">Microsoft 365 Enterprise enthält Microsoft 365 Apps for Enterprise, die Abonnementversion von Office.</span><span class="sxs-lookup"><span data-stu-id="33e43-106">Microsoft 365 Enterprise includes Microsoft 365 Apps for enterprise, the subscription version of Office.</span></span> <span data-ttu-id="33e43-107">Wie Office 2019 enthält auch Microsoft 365 Apps for Enterprise alle Office-Anwendungen, und diese Anwendungen werden direkt auf Ihren Clientgeräten installiert.</span><span class="sxs-lookup"><span data-stu-id="33e43-107">Like Office 2019, Microsoft 365 Apps for enterprise includes all the Office applications, and those applications are installed directly on your client devices.</span></span> <span data-ttu-id="33e43-108">Anders als bei Office 2019 wird Microsoft 365 Apps for Enterprise regelmäßig mit neuen Features aktualisiert und verfügt über ein benutzerbasiertes Lizenzierungsmodell, das Benutzern ermöglicht, Office auf mehreren Geräten zu installieren.</span><span class="sxs-lookup"><span data-stu-id="33e43-108">Unlike Office 2019, Microsoft 365 Apps for enterprise is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on multiple devices.</span></span> <span data-ttu-id="33e43-109">Weitere Einzelheiten erfahren Sie unter [Info zu Microsoft 365 Apps for Enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="33e43-109">For more details, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="33e43-p102">In dieser Phase stellen Sie Microsoft 365 Apps for Enterprise im Rahmen von Microsoft 365 Enterprise auf Clientgeräten bereit. Zusätzlich zur vorliegenden Anleitung empfehlen wir die Verwendung von [Microsoft FastTrack](https://fasttrack.microsoft.com/office) bei der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="33e43-p102">In this phase, you deploy Microsoft 365 Apps for enterprise to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft FastTrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="33e43-112">Wenn Sie bereits Microsoft 365 Apps for Enterprise bereitgestellt haben, lesen Sie bitte den Abschnitt zu den [Beendigungskriterien](office365proplus-exit-criteria.md) für diese Phase, um sicherzustellen, dass sie die erforderlichen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="33e43-112">If you already have Microsoft 365 Apps for enterprise deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="33e43-113">Weitere Informationen, um Windows 10 Enterprise und Microsoft 365 Apps for Enterprise zusammen bereitzustellen, finden Sie unter [Bereitstellungscenter für Desktop](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="33e43-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="33e43-114">Schritt 1: Bewerten der Umgebung</span><span class="sxs-lookup"><span data-stu-id="33e43-114">Step 1: Assess your environment</span></span>

<span data-ttu-id="33e43-p103">Befolgen Sie vor der Bereitstellung von Microsoft 365 Apps for Enterprise die Anleitungen unter [Bewerten der Umgebung und Anforderungen für die Bereitstellung von Microsoft 365 Apps for Enterprise](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps). Diese Bewertung schließt die Systemanforderungen, Details zu Ihren Clientgeräten (z. B. Architekturen und erforderliche Sprachen), Lizenzierungsanforderungen, Netzwerkfunktion und Anwendungskompatibilität ein. Das Abschließen der Bewertung unterstützt Sie bei der grundlegenden Entscheidungsfindung im Rahmen der Planung Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="33e43-p103">Before deploying Microsoft 365 Apps for enterprise, follow the guidance in [Assess your environment and requirements for deploying Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="33e43-118">Schritt 2: Planen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="33e43-118">Step 2: Plan your deployment</span></span>

<span data-ttu-id="33e43-p104">Befolgen Sie nach dem Bewerten Ihrer Umgebung die Anleitungen unter [Planen der Bereitstellung von Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps), um einen Bereitstellungsplan zu erstellen. Dieser Plan schließt die folgenden Entscheidungen ein:</span><span class="sxs-lookup"><span data-stu-id="33e43-p104">After assessing your environment, follow the guidance in [Plan your deployment of Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="33e43-121">Bereitstellen von Office, einschließlich dem zu verwendenden Tool (z. B. Microsoft Endpoint Configuration Manager oder Office-Bereitstellungstool) und dem Ort, von dem aus Office installiert werden soll</span><span class="sxs-lookup"><span data-stu-id="33e43-121">How to deploy Office, including what tool to use (such as Microsoft Endpoint Configuration Manager or the Office Deployment Tool) and where to install Office from</span></span>
- <span data-ttu-id="33e43-122">Verwalten von Updates für Office</span><span class="sxs-lookup"><span data-stu-id="33e43-122">How to manage updates to Office</span></span>
- <span data-ttu-id="33e43-123">Zu verwendende Updatekanäle (Updatekanäle für Office steuern, wie häufig die Benutzer Updates von Funktionen in ihren Office-Anwendungen erhalten)</span><span class="sxs-lookup"><span data-stu-id="33e43-123">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="33e43-124">Zu verwendende Office-Installationspakete und -Bereitstellungsgruppen, darunter die zu installierenden Office-Anwendungen und Sprachen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="33e43-124">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="33e43-125">Der Artikel zum [Planen](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) enthält die bewährten Methoden für alle diese Optionen, darunter die Verwaltung der Bereitstellung, Verwaltung der Updates, Definition der Installationspakete und Erstellung von Bereitstellungsgruppen.</span><span class="sxs-lookup"><span data-stu-id="33e43-125">The [planning article](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="33e43-126">Schritt 3: Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="33e43-126">Step 3: Deploy</span></span>

<span data-ttu-id="33e43-127">Wählen Sie basierend auf Ihrem Bereitstellungsplan die Methode für die Bereitstellung aus:</span><span class="sxs-lookup"><span data-stu-id="33e43-127">Based on your deployment plan, choose how you want to deploy:</span></span>

- <span data-ttu-id="33e43-128">**[Bereitstellen von Microsoft 365 Apps mit Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** Verwalten der Bereitstellung mit Configuration Manager und Herunterladen und Bereitstellen von Office über Verteilungspunkte in Ihrem Netzwerk</span><span class="sxs-lookup"><span data-stu-id="33e43-128">**[Deploy Microsoft 365 Apps with Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="33e43-129">**[Bereitstellen von Microsoft 365 Apps über die Cloud](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** Verwalten der Bereitstellung mit dem Office-Bereitstellungstool und direktes Installieren von Office über das Office-CDN auf Clientgeräten</span><span class="sxs-lookup"><span data-stu-id="33e43-129">**[Deploy Microsoft 365 Apps from the cloud](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="33e43-130">**[Installieren von Microsoft 365 Apps for Enterprise über das Office-Portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Verwalten der Bereitstellung im Office-Portal und direktes Installieren von Office auf Clientgeräten über das Portal durch Benutzer</span><span class="sxs-lookup"><span data-stu-id="33e43-130">**[Self-install Microsoft 365 Apps for enterprise from the Office portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="33e43-p105">Viele Organisationen verwenden für unterschiedliche Benutzer eine Kombination aus diesen Optionen. Eine Organisation kann z. B. Configuration Manager verwenden, um Office für die meisten Benutzer bereitzustellen, einer kleinen Gruppe von Mitarbeitern, die nicht häufig mit dem internen Netzwerk verbunden sind, jedoch ermöglichen, Office selbst zu installieren.</span><span class="sxs-lookup"><span data-stu-id="33e43-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="33e43-p106">Wenn Ihre Organisation Configuration Manager verwendet, wird empfohlen, ein Upgrade auf Current Branch durchzuführen und auf die aktuelle Version zu aktualisieren. Weitere Informationen finden Sie unter [Welchen Branch von Configuration Manager sollte ich verwenden?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use).</span><span class="sxs-lookup"><span data-stu-id="33e43-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="33e43-135">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="33e43-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="33e43-136">Erfahren Sie, wie die Experten bei Microsoft [Updates für Microsoft 365 Apps for Enterprise bereitstellen und verwalten](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span><span class="sxs-lookup"><span data-stu-id="33e43-136">Learn how the experts at Microsoft are [deploying and managing updates for Microsoft 365 Apps for enterprise](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="33e43-137">Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird</span><span class="sxs-lookup"><span data-stu-id="33e43-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="33e43-138">Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber repräsentatives multinationales Unternehmen [Microsoft 365 Apps for Enterprise bereitgestellt hat](contoso-o365pp.md).</span><span class="sxs-lookup"><span data-stu-id="33e43-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Microsoft 365 Apps for enterprise](contoso-o365pp.md).</span></span>

![Die Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="33e43-140">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="33e43-140">Next step</span></span>

[<span data-ttu-id="33e43-141">Beendigungskriterien für die Infrastruktur von Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="33e43-141">Microsoft 365 Apps for enterprise infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
