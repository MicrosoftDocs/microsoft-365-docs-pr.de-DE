---
title: 'Phase 4: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Die Schritte zur Bereitstellung der Office 365 Pro Plus-Infrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: f20435edc4cdc675d0308774eb493a67723054f4
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982766"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="ddfc2-103">Phase 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="ddfc2-103">Phase 4: Office 365 ProPlus</span></span>

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="ddfc2-104">*Dies gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise und Microsoft 365 Education.*</span><span class="sxs-lookup"><span data-stu-id="ddfc2-104">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="ddfc2-p101">Microsoft 365 Enterprise enthält Office 365 ProPlus, die Abonnementversion von Office. Wie Office 2016 umfasst Office 365 ProPlus alle Office-Anwendungen, und diese Anwendungen sind direkt auf Ihren Clientgeräten installiert sind. Im Gegensatz zu Office 2016 wird Office 365 ProPlus regelmäßig um neue Features erweitert und verfügt über ein benutzerbasiertes Lizenzierungsmodell, mit dem Benutzer Office auf bis zu 5 Geräten installieren können. Weitere Informationen finden Sie unter [Informationen zu Office 365 ProPlus im Unternehmen](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="ddfc2-p101">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office. Like Office 2016, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices. Unlike Office 2016, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on up to 5 devices. For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="ddfc2-p102">In dieser Phase stellen Sie Office 365 ProPlus auf Clientgeräten im Rahmen von Microsoft 365 Enterprise bereit. Zusätzlich zu dieser Anleitung empfehlen wir die Verwendung von [Microsoft Fastrack](https://fasttrack.microsoft.com/office) bei der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="ddfc2-p102">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="ddfc2-111">Wenn Sie bereits Office 365 ProPlus bereitgestellt haben, lesen Sie bitte den Abschnitt zu den [Beendigungskriterien](office365proplus-exit-criteria.md) für diese Phase, um sicherzustellen, dass sie die erforderlichen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ddfc2-111">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="ddfc2-112">Weitere Informationen, um Windows 10 Enterprise und Office 365 ProPlus zusammen zu erstellen, finden Sie unter [Bereitstellungscenter für Desktop](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="ddfc2-112">To deploy both Windows 10 Enterprise and Office 365 ProPlus together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="ddfc2-113">Schritt 1: Bewerten der Umgebung</span><span class="sxs-lookup"><span data-stu-id="ddfc2-113">Step 1: Assess your environment</span></span>

<span data-ttu-id="ddfc2-p103">Befolgen Sie vor der Bereitstellung von Office 365 ProPlus die Anleitungen unter [Bewerten der Umgebung und Anforderungen für die Bereitstellung von Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Diese Bewertung umfasst die Systemanforderungen, Details zu Ihren Clientgeräten (z. B. Architekturen und erforderliche Sprachen), Lizenzen, Netzwerkfunktion und Anwendungskompatibilität. Das Abschließen der Bewertung unterstützt Sie bei grundlegender Entscheidungsfindung im Rahmen der Planung Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="ddfc2-p103">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="ddfc2-117">Schritt 2: Planen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="ddfc2-117">Step 2: Plan your deployment</span></span>

<span data-ttu-id="ddfc2-p104">Befolgen Sie nach dem Bewerten der Umgebung die Anleitungen unter [Planen der Bereitstellung von Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) zum Erstellen eines Bereitstellungsplans. Dieser Plan enthält die folgenden Entscheidungen:</span><span class="sxs-lookup"><span data-stu-id="ddfc2-p104">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="ddfc2-120">Bereitstellen von Office, darunter das zu verwendende Tool (z. B. System Center Configuration Manager oder Office-Bereitstellungstool) und Ort der Installation von Office</span><span class="sxs-lookup"><span data-stu-id="ddfc2-120">How to deploy Office, including what tool to use (such as System Center Configuration Manager or the Office Deployment Tool [ODT]) and where to install Office from</span></span>
- <span data-ttu-id="ddfc2-121">Verwalten von Updates für Office</span><span class="sxs-lookup"><span data-stu-id="ddfc2-121">How to manage updates to Office</span></span>
- <span data-ttu-id="ddfc2-122">Zu verwendende Updatekanäle (Updatekanäle für Office steuern, wie häufig die Benutzer Updates von Funktionen in ihren Office-Anwendungen erhalten)</span><span class="sxs-lookup"><span data-stu-id="ddfc2-122">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="ddfc2-123">Zu verwendende Office-Installationspakete und -Bereitstellungsgruppen, darunter die zu installierenden Office-Anwendungen und Sprachen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="ddfc2-123">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="ddfc2-124">Der Artikel zum [Planen](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) enthält die bewährten Methoden für alle diese Optionen, darunter die Verwaltung der Bereitstellung, Verwaltung der Updates, Definition der Installationspakete und Erstellung von Bereitstellungsgruppen.</span><span class="sxs-lookup"><span data-stu-id="ddfc2-124">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="ddfc2-125">Schritt 3: Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="ddfc2-125">Step 3: Deploy</span></span>

<span data-ttu-id="ddfc2-126">Wählen Sie basierend auf Ihrem Bereitstellungsplan aus Schritt 2 die Methode für die Bereitstellung aus:</span><span class="sxs-lookup"><span data-stu-id="ddfc2-126">Based on your deployment plan from step 2, choose how you want to deploy:</span></span>

- <span data-ttu-id="ddfc2-127">**[Bereitstellen von Office 365 ProPlus mithilfe von System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Verwalten der Bereitstellung mit Configuration Manager und Herunterladen und Bereitstellen von Office über Verteilungspunkte im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="ddfc2-127">**[Deploy Office 365 ProPlus with System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="ddfc2-128">**[Bereitstellen von Office 365 ProPlus mit dem Office-Bereitstellungstool aus der Cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Verwalten der Bereitstellung mit dem Office-Bereitstellungstool und direktes Installieren von Office über das Office-CDN auf Clientgeräten</span><span class="sxs-lookup"><span data-stu-id="ddfc2-128">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="ddfc2-129">**[Bereitstellen von Office 365 ProPlus mit dem Office-Bereitstellungstool aus einer lokalen Datenquelle](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** Verwalten der Bereitstellung mit dem Office-Bereitstellungstool und Herunterladen und Bereitstellen von Office über eine lokale Datenquelle im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="ddfc2-129">**[Deploy Office 365 ProPlus with the ODT from a local source](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** Manage your deployment with the ODT, and download and deploy Office from a local source on your network</span></span> 

- <span data-ttu-id="ddfc2-130">**[Installieren von Office 365 ProPlus über das Office-Portal](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Verwalten der Bereitstellung im Office-Portal und direktes Installieren von Office auf Clientgeräten über das Portal durch Benutzer</span><span class="sxs-lookup"><span data-stu-id="ddfc2-130">**[Self-install Office 365 ProPlus from the Office portal](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="ddfc2-p105">Viele Organisationen verwenden für unterschiedliche Benutzer eine Kombination aus diesen Optionen. Eine Organisation kann z. B. Configuration Manager verwenden, um Office für die meisten Benutzer bereitzustellen, einer kleinen Gruppe von Mitarbeitern, die nicht häufig mit dem internen Netzwerk verbunden sind, jedoch ermöglichen, Office selbst zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ddfc2-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="ddfc2-p106">Wenn Ihre Organisation Configuration Manager verwendet, wird empfohlen, ein Upgrade auf Current Branch durchzuführen und auf die aktuelle Version zu aktualisieren. Weitere Informationen finden Sie unter [Welchen Branch von Configuration Manager sollte ich verwenden?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use).</span><span class="sxs-lookup"><span data-stu-id="ddfc2-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="ddfc2-135">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="ddfc2-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="ddfc2-136">Erfahren Sie, wie die Experten bei Microsoft [Updates für Office 365 ProPlus bereitstellen und verwalten](https://www.microsoft.com/de-DE/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span><span class="sxs-lookup"><span data-stu-id="ddfc2-136">Learn how the experts at Microsoft are [deploying and mananging updates for Office 365 ProPlus](https://www.microsoft.com/de-DE/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="ddfc2-137">Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird</span><span class="sxs-lookup"><span data-stu-id="ddfc2-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="ddfc2-138">Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber multinationales, repräsentatives Unternehmen [Office 365 ProPlus bereitgestellt hat](contoso-o365pp.md).</span><span class="sxs-lookup"><span data-stu-id="ddfc2-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="ddfc2-139">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ddfc2-139">Next step</span></span>

[<span data-ttu-id="ddfc2-140">Beendigungskriterien für die Office 365 ProPlus-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="ddfc2-140">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
