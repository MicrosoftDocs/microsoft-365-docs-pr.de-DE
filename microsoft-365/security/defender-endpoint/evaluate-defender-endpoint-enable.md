---
title: Pilotbewertung von Defender für Endpunkt
description: Aktivieren Sie Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung.
keywords: Microsoft 365 Defender Testversion, testen Sie Microsoft 365 Defender, bewerten Sie Microsoft 365 Defender, Microsoft 365 Defender Evaluierungslabor, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458190"
---
# <a name="pilot-mde-evaluation"></a><span data-ttu-id="dc86a-104">MDE-Pilotbewertung</span><span class="sxs-lookup"><span data-stu-id="dc86a-104">Pilot MDE Evaluation</span></span>

>[!NOTE]
><span data-ttu-id="dc86a-105">Um Sie durch eine typische Bereitstellung zu führen, wird in diesem Szenario nur die Verwendung von Microsoft Endpoint Configuration Manager behandelt.</span><span class="sxs-lookup"><span data-stu-id="dc86a-105">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="dc86a-106">Defender für Endpunkt unterstützt die Verwendung anderer Onboarding-Tools, behandelt diese Szenarien jedoch nicht im Bereitstellungshandbuch.</span><span class="sxs-lookup"><span data-stu-id="dc86a-106">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="dc86a-107">Weitere Informationen finden Sie unter [Onboarding von Geräten in Microsoft Defender für Endpunkt.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="dc86a-107">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="step-1-check-license-state"></a><span data-ttu-id="dc86a-108">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="dc86a-108">Step 1.</span></span> <span data-ttu-id="dc86a-109">Überprüfen des Lizenzstatus</span><span class="sxs-lookup"><span data-stu-id="dc86a-109">Check license state</span></span>

<span data-ttu-id="dc86a-110">Die Überprüfung auf den Lizenzstatus und die ordnungsgemäße Bereitstellung kann über das Admin Center oder über das **Microsoft Azure-Portal** erfolgen.</span><span class="sxs-lookup"><span data-stu-id="dc86a-110">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="dc86a-111">Um Ihre Lizenzen anzuzeigen, wechseln Sie zum **Microsoft Azure-Portal,** und navigieren Sie zum [Lizenzabschnitt Microsoft Azure Portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="dc86a-111">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Abbildung der Azure-Lizenzierungsseite](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="dc86a-113">Navigieren Sie alternativ im Admin Center zu **Abrechnungsabonnements.**  >  </span><span class="sxs-lookup"><span data-stu-id="dc86a-113">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="dc86a-114">Auf dem Bildschirm werden alle bereitgestellten Lizenzen und deren aktueller **Status angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="dc86a-114">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Abbildung der Abrechnungslizenzen](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="dc86a-116">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="dc86a-116">Step 2.</span></span> <span data-ttu-id="dc86a-117">Integrieren von Endpunkten mithilfe der unterstützten Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="dc86a-117">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="dc86a-118">Das Thema ["Planbereitstellung"](deployment-strategy.md) beschreibt die allgemeinen Schritte, die Sie zum Bereitstellen von Defender für Endpunkt ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="dc86a-118">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="dc86a-119">Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Onboardingprozess zu erhalten und mehr über die verfügbaren Tools und Methoden zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="dc86a-119">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

<span data-ttu-id="dc86a-120">Nachdem Sie Ihre Architektur identifiziert haben, müssen Sie entscheiden, welche Bereitstellungsmethode verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dc86a-120">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="dc86a-121">Das von Ihnen verwendete Bereitstellungstool beeinflusst, wie Sie Endpunkte in den Dienst integrieren.</span><span class="sxs-lookup"><span data-stu-id="dc86a-121">The deployment tool you choose influences how you onboard endpoints to the service.</span></span>

### <a name="onboarding-tool-options"></a><span data-ttu-id="dc86a-122">Onboarding-Tooloptionen</span><span class="sxs-lookup"><span data-stu-id="dc86a-122">Onboarding tool options</span></span>

<span data-ttu-id="dc86a-123">In der folgenden Tabelle sind die verfügbaren Tools aufgeführt, die auf dem Endpunkt basieren, den Sie integrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="dc86a-123">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="dc86a-124">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="dc86a-124">Endpoint</span></span>     | <span data-ttu-id="dc86a-125">Tooloptionen</span><span class="sxs-lookup"><span data-stu-id="dc86a-125">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="dc86a-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="dc86a-126">**Windows**</span></span>  |  [<span data-ttu-id="dc86a-127">Lokales Skript (bis zu 10 Geräte)</span><span class="sxs-lookup"><span data-stu-id="dc86a-127">Local script (up to 10 devices)</span></span>](../defender-endpoint/configure-endpoints-script.md) <br> [<span data-ttu-id="dc86a-128">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="dc86a-128">Group Policy</span></span>](../defender-endpoint/configure-endpoints-gp.md) <br> [<span data-ttu-id="dc86a-129">Microsoft Endpoint Manager/Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="dc86a-129">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](../defender-endpoint/configure-endpoints-mdm.md) <br> [<span data-ttu-id="dc86a-130">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dc86a-130">Microsoft Endpoint Configuration Manager</span></span>](../defender-endpoint/configure-endpoints-sccm.md) <br> [<span data-ttu-id="dc86a-131">VDI-Skripts</span><span class="sxs-lookup"><span data-stu-id="dc86a-131">VDI scripts</span></span>](../defender-endpoint/configure-endpoints-vdi.md) <br> [<span data-ttu-id="dc86a-132">Integration in Azure Defender</span><span class="sxs-lookup"><span data-stu-id="dc86a-132">Integration with Azure Defender</span></span>](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="dc86a-133">**macOS**</span><span class="sxs-lookup"><span data-stu-id="dc86a-133">**macOS**</span></span>    | [<span data-ttu-id="dc86a-134">Lokale Skripts</span><span class="sxs-lookup"><span data-stu-id="dc86a-134">Local scripts</span></span>](../defender-endpoint/mac-install-manually.md) <br> [<span data-ttu-id="dc86a-135">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="dc86a-135">Microsoft Endpoint Manager</span></span>](../defender-endpoint/mac-install-with-intune.md) <br> [<span data-ttu-id="dc86a-136">JAMF-Pro</span><span class="sxs-lookup"><span data-stu-id="dc86a-136">JAMF Pro</span></span>](../defender-endpoint/mac-install-with-jamf.md) <br> [<span data-ttu-id="dc86a-137">Verwaltung mobiler Geräte - Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="dc86a-137">Mobile Device Management</span></span>](../defender-endpoint/mac-install-with-other-mdm.md) |
| <span data-ttu-id="dc86a-138">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="dc86a-138">**Linux Server**</span></span> | [<span data-ttu-id="dc86a-139">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="dc86a-139">Local script</span></span>](../defender-endpoint/linux-install-manually.md) <br> [<span data-ttu-id="dc86a-140">Puppe</span><span class="sxs-lookup"><span data-stu-id="dc86a-140">Puppet</span></span>](../defender-endpoint/linux-install-with-puppet.md) <br> [<span data-ttu-id="dc86a-141">Ansible</span><span class="sxs-lookup"><span data-stu-id="dc86a-141">Ansible</span></span>](../defender-endpoint/linux-install-with-ansible.md)|
| <span data-ttu-id="dc86a-142">**iOS**</span><span class="sxs-lookup"><span data-stu-id="dc86a-142">**iOS**</span></span>      | [<span data-ttu-id="dc86a-143">App-basiert</span><span class="sxs-lookup"><span data-stu-id="dc86a-143">App-based</span></span>](../defender-endpoint/ios-install.md)                                |
| <span data-ttu-id="dc86a-144">**Android**</span><span class="sxs-lookup"><span data-stu-id="dc86a-144">**Android**</span></span>  | [<span data-ttu-id="dc86a-145">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="dc86a-145">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)               |
