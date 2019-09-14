---
title: Windows 10 Enterprise-Infrastruktur für Microsoft 365 Enterprise
description: Bietet eine ausführliche Anleitung zu den einzelnen Schritten, die im Rahmen von Microsoft 365 Enterprise für die Bereitstellung von Windows 10 Enterprise auf PCs nötig sind.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-Dokumentation, Windows 10 Enterprise, Bereitstellung
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
ms.author: greglin
ms.openlocfilehash: 0b98e48b128eeaea0e0dd5cb9613ece95e991861
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982746"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="4b365-104">Phase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4b365-104">Phase 3: Windows 10 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="4b365-105">Microsoft 365 Enterprise umfasst Windows 10 Enterprise, das Ihnen die Tools bietet, um mehr zu tun und sicher zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="4b365-105">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="4b365-106">Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="4b365-106">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="4b365-107">**Ist zur Vereinfachung integriert** – nutzen Sie die Leistungsfähigkeit der Cloud, um die Komplexität der modernen IT-Geräteumgebung, unabhängig von der Größe, zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="4b365-107">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="4b365-108">**Verfügt über eine intelligente Sicherheit** , die die sicherste Version von Windows überhaupt ist, mit intelligenten Sicherheitsfunktionen, die zusammenarbeiten, um Ihre Organisation besser zu schützen.</span><span class="sxs-lookup"><span data-stu-id="4b365-108">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="4b365-109">**Ermöglicht Kreativität und Teamarbeit** – entsperrt Kreativität und Teamarbeit, um die produktivste Erfahrung zu liefern, die die Benutzer und die IT lieben werden.</span><span class="sxs-lookup"><span data-stu-id="4b365-109">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="4b365-110">Sie müssen die verschiedenen Möglichkeiten kennen, wie Sie das Betriebssystem Windows 10 bereitstellen und das richtige für Ihre Organisation auswählen können.</span><span class="sxs-lookup"><span data-stu-id="4b365-110">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="4b365-111">Je nach Ihrem Microsoft 365 Enterprise-Abonnement gibt es auch Windows 10-Dienste und Sicherheitsfeatures, die Sie konfigurieren müssen, um Windows 10 optimal nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="4b365-111">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="4b365-112">Um Windows 10 Enterprise und Office 365 ProPlus zusammen zu erstellen und auf einen [modernen Desktop](https://www.microsoft.com/microsoft-365/modern-desktop) umzusteigen, gehen Sie zum [Bereitstellungscenter für modernen Desktop](http://aka.ms/howtoshift).</span><span class="sxs-lookup"><span data-stu-id="4b365-112">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="4b365-113">Windows 10-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="4b365-113">Windows 10 deployment</span></span>

<span data-ttu-id="4b365-114">Es gibt mehrere Möglichkeiten, wie Sie Windows 10 Enterprise für Ihre Organisation bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="4b365-114">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="4b365-115">Hier konzentrieren wir uns darauf, wie Sie ein Windows 10 Enterprise-Image über diese modernen Bereitstellungsszenarien konfigurieren und bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="4b365-115">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="4b365-116">Bereitstellungsszenario</span><span class="sxs-lookup"><span data-stu-id="4b365-116">Deployment scenario</span></span> | <span data-ttu-id="4b365-117">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="4b365-117">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="4b365-118">Verwenden von System Center Configuration Manager als direktes Upgrade</span><span class="sxs-lookup"><span data-stu-id="4b365-118">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="4b365-119">Wählen Sie diese Option aus, wenn Sie Windows 7 oder Windows 8.1 Computer auf die <a href="https://aka.ms/windows-10-release-information" target="_blank">aktuelle Version</a> von Windows 10 Enterprise aktualisieren müssen und ihre Computer derzeit mit <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current Branch)</a>verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4b365-119">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="4b365-120">Verwenden von Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="4b365-120">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="4b365-121">Wählen Sie diese Option aus, wenn Sie neue Windows-Computer einrichten, auf denen Windows 10 Enterprise, Version 1703 oder höher, bereits vorinstalliert ist.</span><span class="sxs-lookup"><span data-stu-id="4b365-121">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="4b365-122">Endbenutzer initiieren das Setup mithilfe Ihrer gewünschten Konfiguration, indem Sie die Anmeldeinformationen für Ihr Büro oder Ihr Schulkonto eingeben.</span><span class="sxs-lookup"><span data-stu-id="4b365-122">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="4b365-123">Wenn diese Bereitstellungsszenarien nicht den Anforderungen Ihrer Organisation entsprechen, können Sie sich über andere Szenarien informieren und die Möglichkeiten und Einschränkungen der einzelnen [Windows 10-Bereitstellungsszenarien](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)kennen.</span><span class="sxs-lookup"><span data-stu-id="4b365-123">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="4b365-124">Sie können auch die <a href="https://aka.ms/planforwin10deployment" target="_blank">Bereitstellung von Windows 10</a> auf eigene Faust planen.</span><span class="sxs-lookup"><span data-stu-id="4b365-124">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="4b365-125">Weitere Informationen zu Windows 10 finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="4b365-125">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="4b365-126">Microsoft 365 Enterprise product page (Microsoft 365 Enterprise-Produktseite)</span><span class="sxs-lookup"><span data-stu-id="4b365-126">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="4b365-127">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4b365-127">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="4b365-128">Bereitstellen und Aktualisieren von Windows 10</span><span class="sxs-lookup"><span data-stu-id="4b365-128">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="4b365-129">Zusätzliche Dienste und Features</span><span class="sxs-lookup"><span data-stu-id="4b365-129">Additional services and features</span></span>
<span data-ttu-id="4b365-130">Im Rahmen der Bereitstellung von Windows 10 Enterprise können Sie diese zusätzlichen Dienste und Features hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4b365-130">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="4b365-131">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="4b365-131">Windows Analytics</span></span>

<span data-ttu-id="4b365-132">Windows verwendet Diagnosedaten, um umfangreiche, umsetzbare Informationen bereitzustellen, mit denen Sie Tiefe Einblicke in die betriebliche Effizienz und die Integrität von Windows 10-Geräten in Ihrer Umgebung erhalten.</span><span class="sxs-lookup"><span data-stu-id="4b365-132">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="4b365-133">Update Bereitschaft – die Bereitschaft zur Aktualisierung hilft Ihnen, zu Windows 10 zu wechseln und mit neuen Windows 10-Feature-Updates auf dem neuesten Stand zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="4b365-133">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="4b365-134">Update Compliance – Update Compliance richtet sich an den IT-Administrator, der eine ganzheitliche Ansicht aller Windows 10-Geräte ohne zusätzliche Infrastrukturanforderungen erhalten möchte.</span><span class="sxs-lookup"><span data-stu-id="4b365-134">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="4b365-135">Geräte Integrität: Sie können die Geräte Integrität verwenden, um Auswirkungen auf Endbenutzer Probleme proaktiv zu erkennen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="4b365-135">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="4b365-136">Weitere Informationen finden Sie unter [Übersicht über Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) .</span><span class="sxs-lookup"><span data-stu-id="4b365-136">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="4b365-137">Windows-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4b365-137">Windows security</span></span>

<span data-ttu-id="4b365-138">Windows 10 bietet Funktionen zum Schutz vor Bedrohungen, zur Sicherung Ihrer Geräte und zur Hilfe bei der Zugriffssteuerung.</span><span class="sxs-lookup"><span data-stu-id="4b365-138">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="4b365-139">Mit Windows 10 erhalten Sie wichtige Sicherheitsfeatures, die Ihr Gerät von Anfang an schützen.</span><span class="sxs-lookup"><span data-stu-id="4b365-139">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="4b365-140">Microsoft 365 E3 fügt Sicherheitsfeatures wie Windows Hello for Business, Windows Defender Application Control und Windows Information Protection hinzu.</span><span class="sxs-lookup"><span data-stu-id="4b365-140">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="4b365-141">Mit Microsoft 365 E5 erhalten Sie den gesamten Schutz vor Microsoft 365 E3 Security Plus Cloud-basierten Sicherheitsfeatures und Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="4b365-141">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="4b365-142">Weitere Informationen zu den Sicherheitsfeatures, die Sie mit Windows 10 Enterprise erhalten, erhalten Sie unter [Schritt 5: Bereitstellen von Windows 10 Enterprise-Sicherheitsfeatures](windows10-enable-security-features.md)für die Bereitstellung, Verwaltung, Konfiguration und Problembehandlung für drei wichtige ecurity-Features.</span><span class="sxs-lookup"><span data-stu-id="4b365-142">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="4b365-143">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b365-143">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4b365-144">Werfen Sie einen Blick in Microsoft, und erfahren Sie, wie das Unternehmen [Windows 10 Enterprise bereitgestellt hat und die starke Authentifizierung, InTune und Microsoft Defender ATP verwendet](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span><span class="sxs-lookup"><span data-stu-id="4b365-144">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="4b365-145">Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird</span><span class="sxs-lookup"><span data-stu-id="4b365-145">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4b365-146">Sehen Sie sich an, wie die Contoso Corporation, ein fiktives, aber repräsentatives multinationales Unternehmen, [Windows 10 Enterprise bereitgestellt](contoso-win10.md)hat.</span><span class="sxs-lookup"><span data-stu-id="4b365-146">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="4b365-147">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="4b365-147">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="4b365-148">Vorbereiten Ihrer Organisation auf Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4b365-148">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
