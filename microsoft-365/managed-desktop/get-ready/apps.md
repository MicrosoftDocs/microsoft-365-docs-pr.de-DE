---
title: Apps im Microsoft Managed Desktop
description: Erläutert, wie Apps behandelt werden, einschließlich des Packens, Bereitstellens und Unterstützens von Apps.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028944"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="2a04a-104">Apps im Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2a04a-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="2a04a-105">Apps im Allgemeinen</span><span class="sxs-lookup"><span data-stu-id="2a04a-105">Apps generally</span></span>

<span data-ttu-id="2a04a-106">Microsoft enthält bestimmte wichtige Apps zusammen mit der Microsoft 365 E3- oder E5-Lizenz, die für die Teilnahme an Microsoft Managed Desktop erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2a04a-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="2a04a-107">Obwohl wir diese Apps bereitstellen, müssen Sie dennoch bestimmte Verantwortlichkeiten und Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="2a04a-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="2a04a-108">Sie können ihren Benutzern auch zusätzliche Nicht-Microsoft-Apps für self-service über das Unternehmensportal oder eine erforderliche Hintergrundinstallation bereitstellen, die alle die Bereitstellungspipeline von Microsoft Intune verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a04a-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> 

## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="2a04a-109">Von Microsoft bereitgestellte Apps</span><span class="sxs-lookup"><span data-stu-id="2a04a-109">Apps provided by Microsoft</span></span>

<span data-ttu-id="2a04a-110">Ihre Microsoft Managed Desktop-Lizenz umfasst 64-Bit-Versionen der Apps in der Microsoft 365 Apps for Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business und OneNote).) Click-to-Run-Versionen von Microsoft  Project und Visio sind standardmäßig nicht enthalten, Sie können jedoch anfordern, dass sie hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2a04a-110">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="2a04a-111">Weitere Informationen zu diesen Apps finden Sie unter [Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten.](../get-started/project-visio.md)</span><span class="sxs-lookup"><span data-stu-id="2a04a-111">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="2a04a-112">Was Microsoft zur Unterstützung der von uns zur Verfügung stellten Apps tut</span><span class="sxs-lookup"><span data-stu-id="2a04a-112">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="2a04a-113">Microsoft stellt full service für die Bereitstellung, das Update und den Support für die enthaltenen Microsoft 365 Apps for Enterprise-Apps zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2a04a-113">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="2a04a-114">Click-to-Run-Versionen von Microsoft  Project und Visio sind standardmäßig nicht enthalten, aber Microsoft Managed Desktop stellt Bereitstellungsgruppen zur Verfügung, mit denen Ihr IT-Administrator Lizenzen verwalten und diese Anwendungen entsprechend für Ihre Organisation bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="2a04a-114">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="2a04a-115">Microsoft unterstützt Benutzer dieser Anwendungen über die Microsoft Managed Desktop-Supportkanäle.</span><span class="sxs-lookup"><span data-stu-id="2a04a-115">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="2a04a-116">Was Sie tun müssen, um die von uns zur Verfügung stellten Apps zu unterstützen?</span><span class="sxs-lookup"><span data-stu-id="2a04a-116">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="2a04a-117">Es gibt noch bestimmte Dinge, die Sie mit diesen Apps tun müssen:</span><span class="sxs-lookup"><span data-stu-id="2a04a-117">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="2a04a-118">**Zuweisen von** Lizenzen – Sie sind für das Abrufen und Zuweisen der entsprechenden Lizenzen an Benutzer für Microsoft 365 Apps for Enterprise verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="2a04a-118">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="2a04a-119">**Hinzufügen von Benutzern zu Sicherheitsgruppen** – Wenn Sie Microsoft Project oder Visio verwenden, muss Ihr IT-Administrator diese Benutzer den entsprechenden Bereitstellungsgruppen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2a04a-119">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="2a04a-120">IT-Administratoren sind auch für die Gewinnung von Lizenzen von diesen Benutzern verantwortlich, wenn sie das Unternehmen verlassen.</span><span class="sxs-lookup"><span data-stu-id="2a04a-120">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="2a04a-121">Bereitstellen von **Microsoft 365-Add-Ons** – Wenn Sie Add-Ons für eine der Microsoft 365 Apps for Enterprise-Apps benötigen, stellen Sie sie zentral wie jede andere Windows 32-App zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2a04a-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="2a04a-122">Apps, die Sie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="2a04a-122">Apps you provide</span></span>

<span data-ttu-id="2a04a-123">Wahrscheinlich verfügen Sie über andere Apps, die Sie für Ihre Geschäftsvorgänge benötigen.</span><span class="sxs-lookup"><span data-stu-id="2a04a-123">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="2a04a-124">Diese Apps können nur mithilfe der Bereitstellungspipeline von Microsoft Intune auf Microsoft Managed Desktop-Geräten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2a04a-124">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="2a04a-125">Weitere Informationen zur Anwendungsbereitstellung finden Sie unter Bereitstellen von [Apps auf Microsoft Managed Desktop-Geräten.](../get-started/deploy-apps.md)</span><span class="sxs-lookup"><span data-stu-id="2a04a-125">For more information about application deployment follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="2a04a-126">Vorbereiten Ihrer eigenen Apps für die Integration in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2a04a-126">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="2a04a-127">Überprüfen Sie Ihre Apps, und überprüfen Sie:</span><span class="sxs-lookup"><span data-stu-id="2a04a-127">Review your apps, checking:</span></span>

- <span data-ttu-id="2a04a-128">Keine der Apps ist verboten oder hat ein eingeschränktes Verhalten, wie unter [Microsoft Managed Desktop App Requirements beschrieben.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="2a04a-128">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="2a04a-129">Apps müssen für die Verwaltung durch Microsoft Intune bereit sein.</span><span class="sxs-lookup"><span data-stu-id="2a04a-129">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="2a04a-130">Weitere Informationen zu diesem Thema finden Sie unter [Windows 10-App-Bereitstellung mit Microsoft Intune](/intune/apps-windows-10-app-deploy) und Hinzufügen von Apps zu Microsoft [Intune](/intune/apps-add).</span><span class="sxs-lookup"><span data-stu-id="2a04a-130">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="2a04a-131">Andere Pre-Packaging-Anforderungen, z. B. das Bereitstellen von Lizenzschlüsseln, die Vereinbarung mit Lizenzbedingungen und das Festlegen von Serververbindungen.</span><span class="sxs-lookup"><span data-stu-id="2a04a-131">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="2a04a-132">Schritte für die ersten Schritte</span><span class="sxs-lookup"><span data-stu-id="2a04a-132">Steps to get ready</span></span>

1. <span data-ttu-id="2a04a-133">Überprüfen [Sie Voraussetzungen für Microsoft Managed Desktop](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="2a04a-133">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="2a04a-134">Verwenden [Sie Die Bereitschaftsbewertungstools](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2a04a-134">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="2a04a-135">Voraussetzungen für Gastkonten</span><span class="sxs-lookup"><span data-stu-id="2a04a-135">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="2a04a-136">Netzwerkkonfiguration für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2a04a-136">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="2a04a-137">Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2a04a-137">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="2a04a-138">Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2a04a-138">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="2a04a-139">[Apps in Microsoft Managed Desktop](apps.md) (Dieser Artikel)</span><span class="sxs-lookup"><span data-stu-id="2a04a-139">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="2a04a-140">Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2a04a-140">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="2a04a-141">Vorbereiten der Druckressourcen für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2a04a-141">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
