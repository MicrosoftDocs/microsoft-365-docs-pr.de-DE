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
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 53c38ba2e915cd439c8d7629bc7f9cd56ebc8647
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636675"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="84e09-104">Phase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="84e09-104">Phase 3: Windows 10 Enterprise</span></span>

![Phase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="84e09-106">Microsoft 365 Enterprise umfasst Windows 10 Enterprise, das Ihnen die Tools bietet, um mehr zu tun und sicher zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="84e09-106">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="84e09-107">Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="84e09-107">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="84e09-108">**Ist zur Vereinfachung integriert** – nutzen Sie die Leistungsfähigkeit der Cloud, um die Komplexität der modernen IT-Geräteumgebung, unabhängig von der Größe, zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="84e09-108">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="84e09-109">**Verfügt über eine intelligente Sicherheit** , die die sicherste Version von Windows überhaupt ist, mit intelligenten Sicherheitsfunktionen, die zusammenarbeiten, um Ihre Organisation besser zu schützen.</span><span class="sxs-lookup"><span data-stu-id="84e09-109">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="84e09-110">**Ermöglicht Kreativität und Teamarbeit** – entsperrt Kreativität und Teamarbeit, um die produktivste Erfahrung zu liefern, die die Benutzer und die IT lieben werden.</span><span class="sxs-lookup"><span data-stu-id="84e09-110">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="84e09-111">Sie müssen die verschiedenen Möglichkeiten kennen, wie Sie das Betriebssystem Windows 10 bereitstellen und das richtige für Ihre Organisation auswählen können.</span><span class="sxs-lookup"><span data-stu-id="84e09-111">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="84e09-112">Je nach Ihrem Microsoft 365 Enterprise-Abonnement gibt es auch Windows 10-Dienste und Sicherheitsfeatures, die Sie konfigurieren müssen, um Windows 10 optimal nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="84e09-112">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="84e09-113">Informationen zum Zusammenstellen von Windows 10 Enterprise-und Microsoft 365-Apps für Enterprise und zur Verlagerung auf einen [modernen Desktop](https://www.microsoft.com/microsoft-365/modern-desktop)finden Sie im [modernen Desktop-Bereitstellungs Center](https://aka.ms/howtoshift).</span><span class="sxs-lookup"><span data-stu-id="84e09-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](https://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="84e09-114">Windows 10-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="84e09-114">Windows 10 deployment</span></span>

<span data-ttu-id="84e09-115">Es gibt mehrere Möglichkeiten, wie Sie Windows 10 Enterprise für Ihre Organisation bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="84e09-115">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="84e09-116">Hier konzentrieren wir uns darauf, wie Sie ein Windows 10 Enterprise-Image über diese modernen Bereitstellungsszenarien konfigurieren und bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="84e09-116">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="84e09-117">Bereitstellungsszenario</span><span class="sxs-lookup"><span data-stu-id="84e09-117">Deployment scenario</span></span> | <span data-ttu-id="84e09-118">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="84e09-118">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="84e09-119">Verwenden von Microsoft Endpoint Configuration Manager als direktes Upgrade</span><span class="sxs-lookup"><span data-stu-id="84e09-119">Using Microsoft Endpoint Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="84e09-120">Wählen Sie diese Option aus, wenn Sie Windows 7 oder Windows 8.1 Computer auf die <a href="https://aka.ms/windows-10-release-information" target="_blank">aktuelle Version</a> von Windows 10 Enterprise aktualisieren müssen und ihre Computer derzeit mit <a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Configuration Manager (Current Branch)</a>verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="84e09-120">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="84e09-121">Verwenden von Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="84e09-121">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="84e09-122">Wählen Sie diese Option aus, wenn Sie neue Windows-Computer einrichten, auf denen Windows 10 Enterprise, Version 1703 oder höher, bereits vorinstalliert ist.</span><span class="sxs-lookup"><span data-stu-id="84e09-122">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="84e09-123">Endbenutzer initiieren das Setup mithilfe Ihrer gewünschten Konfiguration, indem Sie die Anmeldeinformationen für Ihr Büro oder Ihr Schulkonto eingeben.</span><span class="sxs-lookup"><span data-stu-id="84e09-123">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="84e09-124">Wenn diese Bereitstellungsszenarien nicht den Anforderungen Ihrer Organisation entsprechen, können Sie sich über andere Szenarien informieren und die Möglichkeiten und Einschränkungen der einzelnen [Windows 10-Bereitstellungsszenarien](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)kennen.</span><span class="sxs-lookup"><span data-stu-id="84e09-124">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="84e09-125">Sie können <a href="https://aka.ms/planforwin10deployment" target="_blank">die Bereitstellung von Windows 10 auch selbst planen</a>.</span><span class="sxs-lookup"><span data-stu-id="84e09-125">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="84e09-126">Weitere Informationen zu Windows 10 finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="84e09-126">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="84e09-127">Microsoft 365 Enterprise product page (Microsoft 365 Enterprise-Produktseite)</span><span class="sxs-lookup"><span data-stu-id="84e09-127">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="84e09-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="84e09-128">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="84e09-129">Bereitstellen und Aktualisieren von Windows 10</span><span class="sxs-lookup"><span data-stu-id="84e09-129">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="84e09-130">Zusätzliche Dienste und Features</span><span class="sxs-lookup"><span data-stu-id="84e09-130">Additional services and features</span></span>
<span data-ttu-id="84e09-131">Im Rahmen der Bereitstellung von Windows 10 Enterprise können Sie diese zusätzlichen Dienste und Features hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="84e09-131">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="84e09-132">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="84e09-132">Windows Analytics</span></span>

<span data-ttu-id="84e09-133">Windows verwendet Diagnosedaten, um umfangreiche, umsetzbare Informationen bereitzustellen, mit denen Sie Tiefe Einblicke in die betriebliche Effizienz und die Integrität von Windows 10-Geräten in Ihrer Umgebung erhalten.</span><span class="sxs-lookup"><span data-stu-id="84e09-133">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="84e09-134">Update Bereitschaft – die Bereitschaft zur Aktualisierung hilft Ihnen, zu Windows 10 zu wechseln und mit neuen Windows 10-Feature-Updates auf dem neuesten Stand zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="84e09-134">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="84e09-135">Update Compliance – Update Compliance richtet sich an den IT-Administrator, der eine ganzheitliche Ansicht aller Windows 10-Geräte ohne zusätzliche Infrastrukturanforderungen erhalten möchte.</span><span class="sxs-lookup"><span data-stu-id="84e09-135">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="84e09-136">Geräte Integrität: Sie können die Geräte Integrität verwenden, um Auswirkungen auf Endbenutzer Probleme proaktiv zu erkennen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="84e09-136">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="84e09-137">Weitere Informationen finden Sie unter [Übersicht über Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) .</span><span class="sxs-lookup"><span data-stu-id="84e09-137">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="84e09-138">Windows-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="84e09-138">Windows security</span></span>

<span data-ttu-id="84e09-139">Windows 10 bietet Funktionen zum Schutz vor Bedrohungen, zur Sicherung Ihrer Geräte und zur Hilfe bei der Zugriffssteuerung.</span><span class="sxs-lookup"><span data-stu-id="84e09-139">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="84e09-140">Mit Windows 10 erhalten Sie wichtige Sicherheitsfeatures, die Ihr Gerät von Anfang an schützen.</span><span class="sxs-lookup"><span data-stu-id="84e09-140">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="84e09-141">Microsoft 365 E3 fügt Sicherheitsfeatures wie Windows Hello for Business, Windows Defender Application Control und Windows Information Protection hinzu.</span><span class="sxs-lookup"><span data-stu-id="84e09-141">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="84e09-142">Mit Microsoft 365 E5 erhalten Sie den gesamten Schutz vor Microsoft 365 E3 Security Plus Cloud-basierten Sicherheitsfeatures und Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="84e09-142">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="84e09-143">Weitere Informationen zu den Sicherheitsfeatures, die Sie mit Windows 10 Enterprise erhalten, finden Sie unter [Schritt 5: Bereitstellen von Windows 10 Enterprise-Sicherheits](windows10-enable-security-features.md)Features, um die Bereitstellung, Verwaltung, Konfiguration und Problembehandlung für drei wichtige Sicherheitsfeatures zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="84e09-143">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key security features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="84e09-144">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="84e09-144">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="84e09-145">Werfen Sie einen Blick in Microsoft, und erfahren Sie, wie das Unternehmen [Windows 10 Enterprise bereitgestellt hat und die starke Authentifizierung, InTune und Microsoft Defender ATP verwendet](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span><span class="sxs-lookup"><span data-stu-id="84e09-145">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="84e09-146">Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird</span><span class="sxs-lookup"><span data-stu-id="84e09-146">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="84e09-147">Sehen Sie sich an, wie die Contoso Corporation, ein fiktives, aber repräsentatives multinationales Unternehmen, [Windows 10 Enterprise bereitgestellt](contoso-win10.md)hat.</span><span class="sxs-lookup"><span data-stu-id="84e09-147">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![Die Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="84e09-149">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="84e09-149">Next step</span></span>

|||
|:-------|:-----|
|![Schritt 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="84e09-151">Vorbereiten Ihrer Organisation auf Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="84e09-151">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
